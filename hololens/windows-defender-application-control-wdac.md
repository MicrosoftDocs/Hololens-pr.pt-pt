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
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="930f7-103">Controlo de aplicações do Windows Defender - WDAC</span><span class="sxs-lookup"><span data-stu-id="930f7-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="930f7-104">O WDAC permite que um Administrador de TI configuure os seus dispositivos para bloquear o lançamento de aplicações em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="930f7-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="930f7-105">Isto é diferente dos métodos de restrição do dispositivo, como o modo Quiosque, onde o utilizador é apresentado com uma UI que esconde as aplicações no dispositivo mas que ainda podem ser lançadas.</span><span class="sxs-lookup"><span data-stu-id="930f7-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="930f7-106">Apesar de o WDAC estar implementado, as aplicações ainda estão visíveis na lista de Todas as Aplicações, mas o WDAC impede que essas aplicações e processos possam ser lançados pelo utilizador do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="930f7-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="930f7-107">Um dispositivo pode ser atribuído mais do que uma política WDAC.</span><span class="sxs-lookup"><span data-stu-id="930f7-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="930f7-108">Se várias políticas do WDAC forem definidas num sistema, as mais restritivas fazem efeito.</span><span class="sxs-lookup"><span data-stu-id="930f7-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="930f7-109">Quando os utilizadores finais tentarem lançar uma aplicação que é bloqueada pelo WDAC, no HoloLens não receberão uma notificação sobre não poderem lançar essa aplicação.</span><span class="sxs-lookup"><span data-stu-id="930f7-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="930f7-110">O seguinte é um guia para os utilizadores aprenderem a [usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicações em dispositivos HoloLens 2 com o Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)</span><span class="sxs-lookup"><span data-stu-id="930f7-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="930f7-111">Quando os utilizadores procuram aplicações instaladas no seu PC Windows 10 utilizando o primeiro passo de exemplo, poderão precisar de fazer algumas tentativas para reduzir os resultados.</span><span class="sxs-lookup"><span data-stu-id="930f7-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="930f7-112">Se não souber o nome completo do pacote, poderá ter de executar 'Get-AppxPackage -name \* YourBestGuess' \* algumas vezes para o encontrar.</span><span class="sxs-lookup"><span data-stu-id="930f7-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="930f7-113">Em seguida, uma vez que você tem o nome executar '$package 1 = Get-AppxPackage -name Atual.PackageName'</span><span class="sxs-lookup"><span data-stu-id="930f7-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="930f7-114">Por exemplo, executar o seguinte para o Microsoft Edge irá devolver mais do que um resultado, mas a partir dessa lista pode identificar que o nome completo de que precisa é Microsoft.MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="930f7-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="930f7-115">Pacote nomes de família para aplicativos em HoloLens</span><span class="sxs-lookup"><span data-stu-id="930f7-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="930f7-116">No guia acima indicado, pode editar manualmente newPolicy.xml e adicionar regras para aplicações que só são instaladas em HoloLens com os seus nomes de família pacote.</span><span class="sxs-lookup"><span data-stu-id="930f7-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="930f7-117">Por vezes, existem aplicações que pode usar para usar que não estão no seu PC de secretária que deseja adicionar à política.</span><span class="sxs-lookup"><span data-stu-id="930f7-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="930f7-118">Aqui está uma lista de aplicações comumente usadas e In-Box para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="930f7-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="930f7-119">Nome da Aplicação</span><span class="sxs-lookup"><span data-stu-id="930f7-119">App Name</span></span>                   | <span data-ttu-id="930f7-120">Nome da família do pacote</span><span class="sxs-lookup"><span data-stu-id="930f7-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="930f7-121">Espectador 3D</span><span class="sxs-lookup"><span data-stu-id="930f7-121">3D Viewer</span></span>                  | <span data-ttu-id="930f7-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="930f7-123">Instalador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="930f7-123">App Installer</span></span>              | <span data-ttu-id="930f7-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="930f7-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="930f7-125">Calendário</span><span class="sxs-lookup"><span data-stu-id="930f7-125">Calendar</span></span>                   | <span data-ttu-id="930f7-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="930f7-127">Câmara</span><span class="sxs-lookup"><span data-stu-id="930f7-127">Camera</span></span>                     | <span data-ttu-id="930f7-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="930f7-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="930f7-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="930f7-129">Cortana</span></span>                    | <span data-ttu-id="930f7-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="930f7-131">Dinâmica 365 Guias</span><span class="sxs-lookup"><span data-stu-id="930f7-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="930f7-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="930f7-133">Dinâmico 365 Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="930f7-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="930f7-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="930f7-135">Centro de Feedback</span><span class="sxs-lookup"><span data-stu-id="930f7-135">Feedback Hub</span></span>               | <span data-ttu-id="930f7-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="930f7-137">Explorador de Ficheiros</span><span class="sxs-lookup"><span data-stu-id="930f7-137">File Explorer</span></span>              | <span data-ttu-id="930f7-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="930f7-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="930f7-139">Correio</span><span class="sxs-lookup"><span data-stu-id="930f7-139">Mail</span></span>                       | <span data-ttu-id="930f7-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="930f7-141">Loja Microsoft</span><span class="sxs-lookup"><span data-stu-id="930f7-141">Microsoft Store</span></span>            | <span data-ttu-id="930f7-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="930f7-143">Filmes & TV</span><span class="sxs-lookup"><span data-stu-id="930f7-143">Movies & TV</span></span>                | <span data-ttu-id="930f7-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="930f7-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="930f7-145">OneDrive</span></span>                   | <span data-ttu-id="930f7-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="930f7-147">Fotografias</span><span class="sxs-lookup"><span data-stu-id="930f7-147">Photos</span></span>                     | <span data-ttu-id="930f7-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="930f7-149">Definições</span><span class="sxs-lookup"><span data-stu-id="930f7-149">Settings</span></span>                   | <span data-ttu-id="930f7-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="930f7-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="930f7-151">Sugestões</span><span class="sxs-lookup"><span data-stu-id="930f7-151">Tips</span></span>                       | <span data-ttu-id="930f7-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="930f7-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="930f7-153">1 - Bloquear o Instalador de Aplicações apenas bloqueará a aplicação App Installer, e não aplicações instaladas a partir de outras fontes, como a Microsoft Store ou a partir da sua solução MDM.</span><span class="sxs-lookup"><span data-stu-id="930f7-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="930f7-154">Como encontrar um nome de família pacote</span><span class="sxs-lookup"><span data-stu-id="930f7-154">How to find a Package Family Name</span></span>

<span data-ttu-id="930f7-155">Se uma aplicação não estiver nesta lista, então um utilizador poderá utilizar o Portal do Dispositivo, ligado a um HoloLens 2 que instalou a aplicação desejada para ser bloqueada, para determinar o PackageRelativeID e a partir daí obter o Nome Demóly.</span><span class="sxs-lookup"><span data-stu-id="930f7-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="930f7-156">Instale a aplicação no seu dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="930f7-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="930f7-157">Abrir definições -> atualizações & segurança -> Para os desenvolvedores e ativar **o modo de programação** e, em seguida, **o portal do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="930f7-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="930f7-158">Mais informações para ler mais sobre [a configuração e utilização do portal do dispositivo aqui](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="930f7-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="930f7-159">Assim que o Portal do Dispositivo estiver ligado, navegue para **Visualizações** e depois **para apps**.</span><span class="sxs-lookup"><span data-stu-id="930f7-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="930f7-160">Dentro do painel de Aplicações Instaladas, utilize o dropdown para selecionar a aplicação instalada.</span><span class="sxs-lookup"><span data-stu-id="930f7-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="930f7-161">Localize o PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="930f7-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="930f7-162">Copiar caracteres de aplicativos antes do !, estes caracteres serão o seu Nome Demôndio Pacote.</span><span class="sxs-lookup"><span data-stu-id="930f7-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


