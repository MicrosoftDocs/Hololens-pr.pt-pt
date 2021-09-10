---
title: HoloLens informações de referência do quiosque
description: Informações e amostras de quiosques em dispositivos HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427362"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Informações de referência do quiosque

Esta página contém informações úteis para configurar o modo de quiosque do seu HoloLens dispositivo. Estas referências incluem AUMIDs para aplicações de caixa de entrada e localização das suas, e várias amostras de XML para o modo Quiosque, que estão apenas a algumas edições de estar prontas para usar para vários cenários diferentes. Para obter informações sobre a criação de um quiosque, leia a [configuração de uma página de quiosque.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens IDs de modelo de utilizador de aplicação (AUMIDs)  

Para obter informações gerais sobre como escolher aplicações de quiosque, consulte [Diretrizes para escolher uma aplicação para acesso atribuído (modo quiosque)](/windows/configuration/guidelines-for-assigned-access-app).

Se utilizar um sistema de Gestão de Dispositivos Móveis (MDM) ou um pacote de provisionamento para configurar o modo quiosque, utilize o [Fornecedor de Serviços de Configuração de Configuração de Acordos (CSP)](/windows/client-management/mdm/assignedaccess-csp) atribuído para especificar aplicações. O CSP utiliza [IDs de Modelo de Utilizador de Aplicações (AUMIDs)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) para identificar aplicações. A tabela que se segue lista os AUMIDs de algumas aplicações na caixa que pode utilizar num quiosque multi-aplicações.

<a id="aumids"></a>

|Nome da Aplicação |AUMID |
| --- | --- |
|Espectador 3D |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Calendário |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Câmara<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Picker de dispositivo em HoloLens (1ª geração) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Picker do dispositivo no HoloLens 2 |A Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DispositivosFlowHost |
|Dinâmica 365 Guias |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dinâmico 365 Assistência Remota |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Centro de Feedback &nbsp; |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Explorador de Ficheiros |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Correio |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Nova Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Loja Microsoft |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> | &nbsp; |
|Filmes & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Fotografias |A Microsoft. Windows. Fotos \_ 8wekyb3d8bbwe \! App |
|Definições |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nova Definições |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Sugestões |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Para ativar a captura de fotografias ou vídeos, tem de ativar a aplicação Camera como uma aplicação de quiosque.  
> <sup>2</sup> Quando ativar a aplicação Camera, esteja atento às seguintes condições:
> - O menu Quick Actions inclui os botões Fotografia e Vídeo.
> - Também deve ativar uma aplicação (como Fotos, Correio ou OneDrive) que possa interagir ou recuperar fotografias.  
>  
> <sup>3</sup> Mesmo que não ative Cortana como uma aplicação de quiosque, os comandos de voz incorporados estão ativados. No entanto, os comandos que estão relacionados com funcionalidades desativadas não têm qualquer efeito.  
> <sup>4</sup> Não é possível ativar diretamente Miracast. Para permitir Miracast como uma aplicação de quiosque, ativar a aplicação Camera e a app Device Picker.

Além disso, o Mixed Reality Home não pode ser definido como uma aplicação de quiosque.

Regresso a [cenários suportados para modo quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Amostras de código do quiosque XML

1. [Vários aplicativos global atribuídos perfil de acesso](#multiple-app-global-assigned-access-profile)
1. [Vários aplicativos globais atribuídos perfil de acesso, excluindo os proprietários de dispositivos](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Vários aplicativos atribuídos perfil de acesso para uma conta local ou conta de utilizador AAD](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Vários perfis de acesso atribuídos a várias aplicações para dois utilizadores AAD ou mais](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Vários aplicativos atribuídos perfil de acesso para um grupo AAD](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Vários aplicativos atribuídos perfil de acesso para dois grupos AAD ou mais](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Vários aplicativos atribuídos perfil de acesso para uma conta AAD e um grupo AAD](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Vários aplicativos atribuídos perfil de acesso para visitantes](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Substitua as ações DOE de acordo com os seus requisitos.

### <a name="multiple-app-global-assigned-access-profile"></a>Vários aplicativos global atribuídos perfil de acesso

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[De volta à lista](#kiosk-xml-code-samples) <br>
Regresso a [cenários suportados para modo quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Vários aplicativos globais atribuídos perfil de acesso, excluindo os proprietários de dispositivos

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[De volta à lista](#kiosk-xml-code-samples) <br>
Regresso a [cenários suportados para modo quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Vários aplicativos atribuídos perfil de acesso para uma conta local ou conta de utilizador AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[De volta à lista](#kiosk-xml-code-samples) <br>
Regresso a [cenários suportados para modo quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Vários perfis de acesso atribuídos a várias aplicações para dois utilizadores AAD ou mais

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[De volta à lista](#kiosk-xml-code-samples) <br>
Regresso a [cenários suportados para modo quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Vários aplicativos atribuídos perfil de acesso para um grupo AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[De volta à lista](#kiosk-xml-code-samples) <br>
Regresso a [cenários suportados para modo quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Vários aplicativos atribuídos perfil de acesso para dois grupos AAD ou mais

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[De volta à lista](#kiosk-xml-code-samples) <br>
Regresso a [cenários suportados para modo quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Vários aplicativos atribuídos perfil de acesso para uma conta AAD e um grupo AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[De volta à lista](#kiosk-xml-code-samples) <br>
Regresso a [cenários suportados para modo quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Vários aplicativos atribuídos perfil de acesso para visitantes

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[De volta à lista](#kiosk-xml-code-samples) <br>
Regresso a [cenários suportados para modo quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
