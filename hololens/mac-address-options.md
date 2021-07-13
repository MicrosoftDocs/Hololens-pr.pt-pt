---
title: Inscrição empresarial de dispositivos de HoloLens em endereço MAC restrito Wi-Fi Ambiente
description: Como endereçar MAC para rede em HoloLens 2 dispositivos
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7938a433921a096913986f5eccff953fd17f1534
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639442"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Inscrição empresarial de dispositivos de HoloLens em endereço MAC restrito Wi-Fi Ambiente

Este documento descreverá um cenário comum que identificamos em ambientes de clientes onde o Wi-Fi é restrito por endereços MAC, ou os certificados são obrigados a aderir a redes sem fios.

## <a name="example-scenario"></a>Cenário de Exemplo

Muitos clientes em ambientes seguros têm restrições nas suas redes sem fios ou com fios que apenas permitirão que dispositivos aprovados (baseados em endereços MAC) se conectem com sucesso. Isto pode ser aplicado através da filtragem do Endereço MAC num Ponto de Acesso Sem Fios ou através de um servidor DHCP. Além disso, algumas redes sem fios podem ser protegidas com PEAP, o que requer que um certificado seja aplicado ao dispositivo antes de autenticar na rede Sem Fios.

Neste cenário, dois requisitos-chave podem introduzir atrasos ou exigir intervenção manual ao juntar HoloLens dispositivos à rede:

- O certificado PEAP sem fios deve ser aplicado ao dispositivo antes de o dispositivo se juntar com sucesso à rede sem fios.
- O endereço MAC do adaptador HoloLens Wi-Fi deve estar registado.

Os principais desafios com os requisitos acima referidos são:

1. Atualmente, o Endereço MAC só pode ser identificado a partir da aplicação Definições no dispositivo, ou do Intune após uma inscrição bem sucedida.

2. Sem o endereço MAC, o dispositivo não pode aderir à Rede Wi-Fi para iniciar a inscrição.

3. As soluções manuais para estes desafios requerem que um técnico interaja com o dispositivo.

## <a name="solutions"></a>Soluções

Existem muitas formas de melhorar esta situação, dependendo das infraestruturas disponíveis no ambiente.

| Solução | Benefícios | Requisitos |
| --- | --- | --- |
| Pacote de Provisionamento com Adaptador Ethernet | Melhora a experiência da OOBE e permite uma experiência técnica mais rápida. | HoloLens adaptador USB-C Hub + Ethernet compatível e o técnico ainda terá de interagir com o dispositivo para captura MAC e finalização OOBE |
| Piloto automático com registo intune sobre ethernet | Trata-se de uma ligação e registo único do dispositivo ao ambiente do cliente. A captura mac pode ser concluída sem necessidade de interagir com o dispositivo | Intune habilitado para o cliente AAD inquilino e um adaptador ethernet USB-C compatível HoloLens |
| Relatório automatizado de endereços MAC | Quando os dispositivos são registados no inquilino Intune, um script pode reportar o endereço MAC ao técnico. | Cmdlets Intune PowerShell |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Pacote de Provisionamento com Adaptador Ethernet

> [!NOTE] 
> Se a rede com fios também estiver sujeita a restrições MAC, então o endereço MAC do adaptador USB-C Hub + Ethernet também terá de ser pré-aprovado. Deve ter-se cuidado com este adaptador, pois permitirá o acesso à rede a partir de outros dispositivos.

### <a name="requirements"></a>Requisitos

- Porta de rede com fios com acesso à rede de clientes
- HoloLens O Hub USB-C compatível com o adaptador Ethernet — Qualquer adaptador que não exija controladores ou instalações adicionais deve ser adequado.
- Pacote de provisionamento que contenha:
  - Contendo informações e certificados de rede sem fios
  - Opcionalmente contendo informações de inscrição para o Azure AD da Organização
  - Contendo quaisquer outras definições de provisionamento necessárias

### <a name="process"></a>Processo

O Processo pode variar dependendo do nível de software do dispositivo. Se o dispositivo tiver a [atualização de maio de 2004,](hololens-release-notes.md#windows-holographic-version-2004)siga os passos abaixo.

1. Coloque o pacote de provisionamento na raiz de uma pen USB e ligue-o ao Hub.
2. Ligação Cabo Ethernet para o adaptador Hub + Ethernet.
3. Ligação USB-C Hub para HoloLens dispositivo.
4. Ligue a HoloLens e coloque o dispositivo.
5. Pressione o **botão Volume Down e Power** para aplicar o pacote de provisionamento.
6. O técnico pode agora seguir o OOBE e, quando estiver concluído, abrir a App Definições para recuperar o Endereço MAC do dispositivo.

Se o dispositivo tiver um sistema operativo antes da [atualização de maio de 2004,](hololens-release-notes.md#windows-holographic-version-2004)siga os passos abaixo.

1. Ligue o HoloLens e ligue o dispositivo a um PC.
2. O dispositivo deve aparecer no PC como um dispositivo de armazenamento de ficheiros.
3. Copiar o pacote de provisionamento para o dispositivo
4. Ligação Cabo Ethernet para o centro.
5. Ligação USB-C Hub para HoloLens dispositivo.
6. Coloque o HoloLens
7. Pressione o botão **Volume Down e Power** para aplicar o pacote de provisionamento.
8. O técnico pode agora seguir o OOBE e, quando estiver concluído, abrir a App Definições para recuperar o Endereço MAC do dispositivo.

### <a name="benefits"></a>Benefícios

Isto permitirá que um "único toque" do dispositivo, aplique o pacote de provisionamento correto e recolha o endereço MAC do dispositivo. [Os pacotes de provisionamento podem ser criados seguindo as orientações aqui.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Piloto automático com inscrição intune

### <a name="requirements"></a>Requisitos

- Porta de rede com fios com acesso à rede de clientes
- HoloLens dispositivos em execução Windows Holographic 2004
- HoloLens Adaptador ethernet USB-C compatível
- Intune configurado e habilitado para o cliente Inquilino
- Dispositivo registado para Piloto Automático e importado para o Cliente Inquilino
- Políticas intune definidas para o dispositivo:
   - Contendo informações e certificados de rede sem fios
   - Contendo quaisquer outras definições de provisionamento necessárias

Isto permitirá a um cliente com requisitos avançados de networking inscrever os dispositivos numa abordagem prática e escalável

Serão necessários pré-requisitos adicionais, como abaixo:
1. [Ativar o Inquilino para a pré-visualização do Piloto Automático](hololens2-autopilot.md).
1. Crie as políticas HoloLens para substituir o Pacote de Provisionamento no Intune.
1. Crie as políticas HoloLens Intune.
1. Atribua os dispositivos ao grupo correto.

### <a name="process"></a>Processo

1. Ligação o cabo ethernet ao adaptador e ligue o adaptador à porta USB-C no dispositivo HoloLens 2.

2. Ligue a HoloLens.

3. O dispositivo deve ligar-se automaticamente à internet durante o OOBE através do adaptador Ethernet. Deve detetar a configuração do Piloto Automático e registar-se automaticamente com Azure AD e Intune.

4. O Dispositivo aplicará os certificados de Wi-Fi necessários e outras configurações, conforme necessário através do Intune.

5. Quando estiver concluído, o técnico pode carregar o Portal Intune (Endpoint Manager) e perfurar a página de propriedades do dispositivo no **Home -> Dispositivos -> DispositivoName -> Hardware**.

6. O endereço MAC Wi-Fi será visível dentro do Portal Intune.

   ![Endereço MAC via Intune](images/mac-address-intune.jpg)

7. O técnico adicionará este endereço MAC como um dispositivo permitido.

### <a name="benefits"></a>Benefícios

Isto permitirá uma experiência de implantação "Heads off" para o Técnico, com o dispositivo a poder ir da caixa para se matricular em AD e Intune sem que o técnico tenha de usar o dispositivo ou interagir manualmente com o ambiente HoloLens.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Comunicação de endereços MAC ao Técnico

### <a name="requirements"></a>Requisitos

- Autorização do "Intune Graph PowerShell" contra o cliente Inquilino
- Instalação do Intune Graph PowerShell na máquina de técnicos.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Leia o acesso aos elementos "Dispositivos Geridos" do Intune. (Operador de mesa de ajuda ou superior, ou um papel personalizado)

Atualmente, não existe uma forma "simples" de desencadear um comando de automação baseado na inscrição de um novo dispositivo dentro do Intune. Portanto, este comando fornecerá ao técnico uma forma simples de recuperar o endereço MAC sem precisar de entrar no portal e recuperá-lo manualmente.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Isto devolverá o nome e o endereço MAC de quaisquer dispositivos HoloLens que tenham sido matriculados nos últimos 30 dias.

![Endereço MAC via PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a>Processo

Após a inscrição intune concluída, o Técnico executaria o script acima para recuperar o endereço MAC.
