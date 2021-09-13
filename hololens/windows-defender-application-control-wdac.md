---
title: Windows Defender Controlo de Aplicações (WDAC)
description: Visão geral sobre o que é Windows Defender Application Control e como usá-lo para gerir HoloLens dispositivos de realidade mista.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5c3b55273346f330580b07e5294e7e8e65ea12d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033944"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Controlo de Aplicações - WDAC

## <a name="overview"></a>Descrição Geral

O WDAC permite-lhe configurar HoloLens para bloquear o lançamento de apps. É diferente do modo Quiosque, onde a UI esconde as aplicações, mas ainda podem ser lançadas. Com o WDAC, pode ver as aplicações, mas não podem ser lançadas.

> [!NOTE]
> Quando os utilizadores finais tentarem lançar uma aplicação que é bloqueada pelo WDAC na HoloLens, não serão notificados sobre não poderem lançar a app.

Um dispositivo pode ser atribuído mais do que uma política WDAC. Se várias políticas do WDAC forem definidas num sistema, as mais restritivas fazem efeito. 

O seguinte é um guia para que os utilizadores aprendam a [usar o WDAC e Windows PowerShell para permitir ou bloquear aplicações em HoloLens 2 dispositivos com Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

Quando os utilizadores procuram aplicações instaladas no seu PC Windows 10 usando o primeiro passo de exemplo, podem precisar de fazer algumas tentativas para reduzir os resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Se não souber o nome completo do pacote, poderá ter de executar 'Get-AppxPackage -name \* YourBestGuess' \* algumas vezes para o encontrar. Em seguida, uma vez que você tem o nome executar '$package 1 = Get-AppxPackage -name Atual.PackageName'

Por exemplo, executar o seguinte código para Microsoft Edge retornará mais do que um resultado, mas dessa lista pode identificar que o nome completo de que precisa é Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Pacote nomes de família para aplicativos em HoloLens

No guia acima indicado, pode editar manualmente newPolicy.xml e adicionar regras para aplicações que só são instaladas em HoloLens com os nomes da família do pacote. Por vezes, existem aplicações que pode usar para usar que não estão no seu PC de secretária que deseja adicionar à política.

Aqui está uma lista de aplicações comumente usadas e In-Box para HoloLens 2 dispositivos.

| Nome da Aplicação                   | Nome da família do pacote                                |
|----------------------------|----------------------------------------------------|
| Espectador 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Instalador de aplicativos              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Calendário                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Câmara                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dinâmica 365 Guias        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dinâmico 365 Assistência Remota | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Centro de Feedback               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Explorador de Ficheiros              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Correio                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Loja Microsoft            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filmes & TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotografias                     | A Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Definições                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Sugestões                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - Bloquear o Instalador de Aplicações apenas bloqueará a aplicação App Installer, e não aplicações instaladas a partir de outras fontes, como a Microsoft Store ou a partir da sua solução MDM.

### <a name="how-to-find-a-package-family-name"></a>Como encontrar um nome de família pacote

Se uma aplicação não estiver nesta lista, então um utilizador poderá utilizar o Portal do Dispositivo, ligado a um HoloLens 2 que instalou a aplicação desejada para ser bloqueada, para determinar o PackageRelativeID e a partir daí obter o Nome Dedesempaly.

1. Instale a aplicação no seu dispositivo HoloLens 2. 
1. Abrir Definições -> Atualizações & Segurança -> Para os desenvolvedores e ativar **o modo de programação** e, em seguida, **o portal do dispositivo**. 
    1. Mais informações para ler mais sobre [a configuração e utilização do portal do dispositivo aqui](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Assim que o Portal do Dispositivo estiver ligado, navegue para **Visualizações** e depois **para apps**. 
1. Dentro do painel de Aplicações Instaladas, utilize o dropdown para selecionar a aplicação instalada. 
1. Localize o PackageRelativeID. 
1. Copiar caracteres de aplicativos antes do `!` , estes caracteres serão o seu Nome DeMily Package.

