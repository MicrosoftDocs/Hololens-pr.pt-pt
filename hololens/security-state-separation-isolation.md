---
title: Separação do Estado e isolamento
description: Saiba mais sobre a separação do estado, isolamento, assinatura de código e aplicações de defesa no seu dispositivo de realidade mista HoloLens 2.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, separação do Estado, separação do Estado e isolamento, hololens2 segurança, visão geral de segurança, arquitetura de segurança, arquitetura, hololens 2 arquitetura
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 60d6d7c0e281395957ce9158144a5f3d60927682
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379938"
---
# <a name="state-separation-and-isolation"></a>Separação do Estado e isolamento

A separação e o isolamento do Estado protegem partes críticas do sistema operativo Hololens 2 da mudança – como as necessárias para que o sistema operativo seja iniciado num estado de confiança. Com a tecnologia de isolamento, as aplicações não fided quanto às fidedqui nem as que correm são transferidas para um ambiente isolado de caixas de areia, para garantir que não afetam a segurança do sistema.

## <a name="state-separation"></a>Separação do Estado

A separação do Estado no HoloLens 2 melhora consideravelmente a segurança e a capacidade de serviço (atualização) e ajuda a proteger os dados da sua aplicação.  A separação do Estado funciona da seguinte forma:
  * O sistema operativo principal é armazenado no volume do sistema operativo principal (fidedignos ou verificados Microsoft OS atualizando o sistema operativo).
  * As porções do sistema operativo que podem ser alteradas no tempo de execução (como condutores e configurações transferíveis), utilizam a separação do estado para dividir os dados e para os armazenar em locais de armazenamento seguros e separados.
  * Cada local de armazenamento seguro tem políticas de segurança distintas associadas a ele, oferecendo variadas vantagens de segurança conforme detalhado na secção seguinte.

## <a name="state-separation-benefits"></a>Benefícios de separação do Estado

  * Segurança: A separação do estado apresentada no HoloLens 2 melhora significativamente a integridade da plataforma, a resistência ao malware e a proteção de dados dos utilizadores. Ao separar a parte inalterável do sistema operativo e torná-la apenas protegida pela leitura ou pela integridade, a separação do Estado torna extremamente difícil que o malware persista através de um reboot frio. 
  * Atualizações: Com hololens 2, uma vez que o sistema operativo principal é indificável e foi separado do resto dos dados do dispositivo, as atualizações tornam-se simples e fiáveis.  Além disso, a separação do Estado estabelece as bases vitais para atualizações dramaticamente mais rápidas, o que permite que o sistema operativo seja substituído num único passo (unidade atómica).
  * Reset do dispositivo: O reset do HoloLens 2 limpa os dados gerados pelo utilizador e os dados das aplicações dos utilizadores no dispositivo – incluindo locais de armazenamento internos e externos. Preserva as atuais aplicações de SEGURANÇA e aplicações críticas de segurança, e as atuais aplicações personalizadas da Microsoft e OEM (Pré-instaladas). Estas aplicações pré-instaladas podem ser rehidratadas no dispositivo após a conclusão do reset

### <a name="state-separation-states"></a>Estados de separação do Estado

A separação do Estado garante que o sistema operativo só pode ser alterado por componentes de dispositivos fidedignos da Microsoft e apenas o estado de alto valor é permitido persistir através de reboots; outro estado do sistema existe apenas durante a duração da sessão de arranque e é descartado após um reboot. Ter a separação do Estado rapidamente devolve o dispositivo ao estado de fábrica. O Windows Holographic for Business states pode ser dividido nestas categorias distintas:
  * Sistema operativo central – Estado inalterável
  * Dados do Sistema Operativo – Estado alterável 
  * Dados do Utilizador – Estado alterável

Cada um destes estados operacionais HoloLens 2 é descrito na secção seguinte.

#### <a name="core-operating-system"></a>Sistema operativo central

Um estado imutável é composto por ficheiros e dados executáveis que são inalteráveis e só podem ser alterados pela Microsoft durante a instalação de atualizações. Durante esta atualização do sistema operativo principal, está ativada uma nova imagem que contenha o estado operacional mais recente pretendido.
O estado inalterável é marcado como apenas leitura (ou está protegido pela integridade), evitando a persistência de qualquer malware com privilégios elevados. Os seguintes ficheiros e dados executáveis estão protegidos no estado imutável:
  * Controladores de caixa de entrada Holográfico do Windows
  * Binários do sistema operativo
  * Controladores de caixa de entrada do Windows
  * Definições holográficas estáticas do Windows armazenadas na colmeia de registo do Windows (HKLM)
    * Exemplo: A HKLM armazena as informações de configuração das aplicações instaladas numa máquina. Também armazena informações para detetar hardware e os condutores correspondentes.
Protegendo-os no estado imutável (integridade e apenas de leitura) do estado, garantimos que o sistema operativo central sempre entra num estado de confiança. Além disso, quando um dispositivo é reiniciado, podemos garantir que o dispositivo se inspeda apenas nos componentes que se encontram nesta secção imutável. 

#### <a name="operating-system-data"></a>Dados do sistema operativo 

É importante notar que ficheiros e dados executáveis que são mutáveis em tempo de execução (e não são críticos para a função do sistema operativo), podem ser descartados e recriados quando os dados são corrompidos ou comprometidos. Um estado alterável de alto valor é necessário funcionalmente para persistir pelo sistema operativo, ou espera-se que persista em todo o sistema operativo, e/ou através de reboots por sistema operativo e cenários de dispositivos suportados pelo Windows. Exemplos de estado mutável de alto valor são:
  * Definições globais de dispositivos configurados pela Amin, tais como desativar a localização para todos os utilizadores.
  * A ligação wi-fi de rede acede a redes de dados e senhas de ligação associadas.
  * Depósitos de colisão, incluindo configurações, troncos.
  * Os condutores descarregaram a pedido de dispositivos recém-descobertos.
Um estado alterável de alto valor no HoloLens 2 reside no sistema operativo Localização de segurança de dados, seja como um ficheiro guardado no disco ou numa colmeia de registo persistido.

#### <a name="user-data"></a>Dados de utilizador

A última categoria de estado representa dados de utilizador produzidos ou persistidos por aplicações UWP ou pelo sistema operativo. Todas as pastas conhecidas do utilizador, tais como Downloads, Documentos, Vídeos, perfis de utilizador e HKEY_CURRENT_USER colmeia também estão armazenadas neste local. Estes dados não podem ser extraídos sem credenciais adequadas; para saber mais sobre como os seus dados são protegidos, consulte [encriptação e proteção de dados.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Isolamento

Para alcançar este equilíbrio, o HoloLens 2 tem um sistema operativo central que é utilizado para funções primárias como o arranque, controlo de hardware, login, etc. Existem apenas dois conjuntos de aplicações que funcionam no sistema operativo principal – aplicações pré-instaladas e aplicações UWP.

## <a name="code-signing"></a>Assinatura de código

O código de assinatura digital permite fundamentar que os executáveis e scripts não foram modificados desde que foram assinados por uma fonte de confiança, fornecendo assim autenticidade e integridade. As autoridades que holoLens 2 confiam por padrão são a Microsoft e a Microsoft Store. Os administradores de TI podem adicionar novos certificados ao dispositivo através do [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) e [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) CSPs. Também podem usar a [política AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) para confiar em aplicações adicionais sideloaded ou [Line-of-business](https://docs.microsoft.com/intune/apps/lob-apps-windows). Os certificados residem na loja de certificados de máquina local que é armazenada em HKLM/Root se utilizar "Dispositivo" ou em HKCU se utilizar "Utilizador".

## <a name="defender-protections"></a>Proteções do Defender
HoloLens 2 utiliza os serviços da Microsoft para dar aos utilizadores um nível avançado de segurança:

* [O Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) é ativado automaticamente no Windows Holographic pelo SISTEMA e protege contra phishing e malware, bem como o download de ficheiros potencialmente maliciosos, no Edge. Não pode ser desligado pelo utilizador, mas pode ser desativado através da política.

* [O Defender Firewall](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) bloqueia o tráfego de rede não autorizado de e para o seu dispositivo. É ativado por defeito e não configurável pelo cliente através de ações ou políticas locais. 

* [Controlo de aplicações do Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview): O HoloLens 2 suporta o WDAC que permite que o administrador de TI pressione as políticas de controlo de aplicações para o dispositivo. Mais informações podem ser encontradas no [Use WDAC em dispositivos HoloLens 2 com MSFT Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens). 

Os administradores de TI podem gerir o comportamento do SmartScreen através [do AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) e do comportamento do navegador através [destas políticas.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) 

