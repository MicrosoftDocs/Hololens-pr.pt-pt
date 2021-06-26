---
title: Pré-visualização insider para Microsoft HoloLens
description: Saiba como começar com as construções insider e forneça feedback valioso para a nossa próxima grande atualização do sistema operativo para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977239"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Pré-visualização insider para Microsoft HoloLens

Bem-vindos às mais recentes construções insider preview para HoloLens! É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer feedback valioso para a nossa próxima grande atualização do sistema operativo para holoLens.

## <a name="windows-insider-release-notes"></a>Notas de lançamento do Windows Insider

Estamos entusiasmados por voltar a voar novas funcionalidades para o Windows Insiders. Novas construções serão voadas para os Canais Dev e Beta para as últimas atualizações. Continuaremos a atualizar esta página à medida que adicionamos mais funcionalidades e atualizações às nossas construções do Windows Insider. Fique animado e pronto para misturar estas atualizações na sua realidade.

| Funcionalidade                 | Descrição                | Utilizadores-alvo | Construção introduzida |
|-------------------------|----------------------------|--------------|------------------|
| Alterações do CSP nos HoloLens | Novos CSPs para consulta de dados | Administradores de TI    | 20348.1403                 |

### <a name="csp-changes-on-hololens"></a>Alterações no CSP nos HoloLens

- Introduzido na construção do Windows Insider, 20348.1403

#### <a name="devdetail-csp"></a>DevDetail CSP

O DevDetail CSP também reporta espaço de armazenamento gratuito no dispositivo HoloLens. Isto deve corresponder aproximadamente ao valor mostrado na página de Armazenamento da App de Definições. Segue-se o nó específico que contém esta informação.

- ./DevDetail/Ext/Microsoft/FreeStorage (apenas operação GET)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

DeviceStatus CSP agora também reporta SSID e BSSID da rede Wifi com a qual holoLens está ativamente conectado. Seguem-se os nós específicos que contêm esta informação.

- ./Fornecedor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address do adaptador de Wi-Fi*/SSID
- ./Fornecedor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address do adaptador Wi-Fi*/BSSID

Blob de sincronização de exemplo (para fornecedores de MDM) para consulta para NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a>Correções e melhorias:

- Corrigiu um [problema conhecido para o Portal do Dispositivo onde não havia qualquer solicitação de descarregamento de ficheiros bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Corrigi um [problema conhecido para o Portal do Dispositivo com upload de ficheiros e descarregamento de tempo.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Comece a receber construções insider
> [!NOTE]
> Se ainda não foi atualizado recentemente, por favor reinicie o seu dispositivo para atualizar o estado e obter a mais recente construção.
> - O comando de voz "Reboot device" funciona bem. 
> - Também pode escolher o botão de reinício em Definições/Programa Insider do Windows.
>
> Tivemos uma escuta na parte de trás que podes ter encontrado e isto vai pôr-te de volta aos trilhos.

Num dispositivo HoloLens 2 aceda a **Definições**  >  **Atualizar & Programa de Segurança** Do Windows  >  **Insider** e **selecione Iniciar**. Ligue a conta que usou para registar como Um Insider do Windows.
O insider do Windows está agora a mudar-se para os Canais. O anel **Rápido** tornar-se-á o **Canal Dev**, o anel **Lento** passará a ser o **Canal Beta**, e o anel **de pré-visualização** de lançamento tornar-se-á o **Canal de Pré-visualização de Lançamento**. Eis o que esse mapeamento parece: ![ explicação dos canais Insider do Windows ](images/WindowsInsiderChannels.png) Para obter mais informações, consulte [a introdução dos canais Insider do Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nos blogs do Windows.
Em seguida, selecione **Ative development of Windows**, escolha se gostaria de receber construções de **Dev Channel** ou Beta **Channel** e reveja os termos do programa.
**Selecione Confirm > Reinicie agora** para terminar. Depois de o seu dispositivo ter sido reiniciado, vá a **Definições > Atualizar & Segurança > Verifique se há atualizações** para obter a mais recente construção.
### <a name="update-error-0x80070490-work-around"></a>Atualizar erro 0x80070490 trabalho
Se encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, experimente o seguinte trabalho de curto prazo. Envolve mover o seu canal de insider, pegar na atualização e, em seguida, mover o seu canal Insider de volta.
#### <a name="stage-one---release-preview"></a>Fase um - Visualização de lançamento
1.  Definições, Atualizar & Segurança, Programa De Insider do Windows, selecione **Release Preview Channel**.
2.  Definições, Atualizar & Segurança, Atualização do Windows, **Verificar atualizações**. Depois da atualização, continue para a fase dois.
#### <a name="stage-two---dev-channel"></a>Fase dois - Canal Dev
1. Definições, Atualizar & Segurança, Programa De Insider do Windows, selecione **Dev Channel**.
2. Definições, Atualizar & Segurança, Atualização do Windows, **Verificar atualizações**.
## <a name="ffu-download-and-flash-directions"></a>Direções de descarregamento e flash da FFU
Para testar com um voo assinado ffu, primeiro tem de voar desbloqueando o seu dispositivo antes de piscar o voo assinado ffu.
1. No PC:
    1. Faça o download para o seu PC a partir de [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale o ARC (Advanced Recovery Companion) a partir da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. No HoloLens - Desbloqueio de voo: Atualização de **definições abertas**  >  **& Programa de Segurança** Do Windows  >  **Insider,** em seguida, inscreva-se, reinicie o dispositivo.
1. Flash FFU - Agora pode piscar o voo assinado FFU usando ARC.
### <a name="provide-feedback-and-report-issues"></a>Fornecer problemas de feedback e relatório
Por favor, use [a aplicação Feedback Hub](hololens-feedback.md) nos seus HoloLens para fornecer problemas de feedback e relatório. A utilização do Feedback Hub garante que todas as informações necessárias de diagnóstico estão incluídas para ajudar os nossos engenheiros a depurar e resolver rapidamente o problema.  Os problemas com a versão chinesa e japonesa dos HoloLens devem ser relatados da mesma forma.
> [!NOTE]
> Não se esqueça de aceitar a solicitação que pergunta se pretende que o Feedback Hub aceda à pasta Documentos (selecione **Sim** quando solicitado).
## <a name="note-for-developers"></a>Nota para desenvolvedores
É bem-vindo e encorajado a tentar desenvolver as suas aplicações usando as construções Insider da HoloLens.  Consulte a [Documentação do Desenvolvedor holoLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar. As mesmas instruções funcionam com as construções insider dos HoloLens.  Pode utilizar as mesmas construções de Unidade e Estúdio Visual que já está a usar para o desenvolvimento do HoloLens.
## <a name="stop-receiving-insider-builds"></a>Pare de receber builds Insider
Se já não pretender receber as construções insider do Windows Holographic, pode optar por sair quando os hololes estiverem a executar uma produção, ou pode recuperar o [seu dispositivo](hololens-recovery.md) utilizando o Advanced Recovery Companion para recuperar o seu dispositivo para uma versão não-Insider do Windows Holographic.
> [!CAUTION]
> Existe um problema conhecido em que os utilizadores que não se matriculam no Insider Preview constroem depois de reinstalarem manualmente uma nova construção de pré-visualização experimentariam um ecrã azul. Depois, devem recuperar manualmente o seu dispositivo. Para mais detalhes sobre se você seria impactado ou não, por favor, veja mais sobre esta [Edição Conhecida.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
Para verificar se os seus HoloLens estão a executar uma construção de produção:
1. Vá a **Definições > System > Sobre**, e encontre o número de construção.
1. [Consulte as notas de lançamento para os números de construção de produção](hololens-release-notes.md).
Para excluir as construções insider:
1. Num HoloLens que executa uma construção de produção, vá a **Definições > Atualização & Security > Programa Do Windows Insider**, e selecione **builds Stop Insider**.
1. Siga as instruções para desativar o seu dispositivo.
