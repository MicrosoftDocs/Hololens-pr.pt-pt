---
title: Controlo de aplicações do Windows Defender - WDAC
description: Visão geral sobre o que é o Controlo de Aplicações do Windows Defender e como usá-lo para gerir dispositivos de realidade mista HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378559"
---
# <a name="windows-defender-application-control---wdac"></a>Controlo de aplicações do Windows Defender - WDAC

O WDAC permite que um Administrador de TI configuure os seus dispositivos para bloquear o lançamento de aplicações em dispositivos. Isto é diferente dos métodos de restrição do dispositivo, como o modo Quiosque, onde o utilizador é apresentado com uma UI que esconde as aplicações no dispositivo mas que ainda podem ser lançadas. Apesar de o WDAC estar implementado, as aplicações ainda estão visíveis na lista de Todas as Aplicações, mas o WDAC impede que essas aplicações e processos possam ser lançados pelo utilizador do dispositivo.

Um dispositivo pode ser atribuído mais do que uma política WDAC. Se várias políticas do WDAC forem definidas num sistema, as mais restritivas fazem efeito. 

> [!NOTE]
> Quando os utilizadores finais tentarem lançar uma aplicação que é bloqueada pelo WDAC, no HoloLens não receberão uma notificação sobre não poderem lançar essa aplicação.

O seguinte é um guia para os utilizadores aprenderem a [usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicações em dispositivos HoloLens 2 com o Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

Quando os utilizadores procuram aplicações instaladas no seu PC Windows 10 utilizando o primeiro passo de exemplo, poderão precisar de fazer algumas tentativas para reduzir os resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Se não souber o nome completo do pacote, poderá ter de executar 'Get-AppxPackage -name \* YourBestGuess' \* algumas vezes para o encontrar. Em seguida, uma vez que você tem o nome executar '$package 1 = Get-AppxPackage -name Atual.PackageName'

Por exemplo, executar o seguinte para o Microsoft Edge irá devolver mais do que um resultado, mas a partir dessa lista pode identificar que o nome completo de que precisa é Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Pacote nomes de família para aplicativos em HoloLens

No guia acima indicado, pode editar manualmente newPolicy.xml e adicionar regras para aplicações que só são instaladas em HoloLens com os seus nomes de família pacote. Por vezes, existem aplicações que pode usar para usar que não estão no seu PC de secretária que deseja adicionar à política.

Aqui está uma lista de aplicações comumente usadas e In-Box para dispositivos HoloLens 2.

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
| Fotografias                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Definições                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Sugestões                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - Bloquear o Instalador de Aplicações apenas bloqueará a aplicação App Installer, e não aplicações instaladas a partir de outras fontes, como a Microsoft Store ou a partir da sua solução MDM.

### <a name="how-to-find-a-package-family-name"></a>Como encontrar um nome de família pacote

Se uma aplicação não estiver nesta lista, então um utilizador poderá utilizar o Portal do Dispositivo, ligado a um HoloLens 2 que instalou a aplicação desejada para ser bloqueada, para determinar o PackageRelativeID e a partir daí obter o Nome Demóly.

1. Instale a aplicação no seu dispositivo HoloLens 2. 
1. Abrir definições -> atualizações & segurança -> Para os desenvolvedores e ativar **o modo de programação** e, em seguida, **o portal do dispositivo**. 
    1. Mais informações para ler mais sobre [a configuração e utilização do portal do dispositivo aqui](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Assim que o Portal do Dispositivo estiver ligado, navegue para **Visualizações** e depois **para apps**. 
1. Dentro do painel de Aplicações Instaladas, utilize o dropdown para selecionar a aplicação instalada. 
1. Localize o PackageRelativeID. 
1. Copiar caracteres de aplicativos antes do !, estes caracteres serão o seu Nome Demôndio Pacote.


