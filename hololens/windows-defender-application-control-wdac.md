---
title: Windows Defender Controlo de Aplicações - WDAC
description: Visão geral sobre o que é Windows Defender Application Control e como usá-lo para gerir HoloLens dispositivos de realidade mista.
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639935"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="882e0-103">Windows Defender Controlo de Aplicações - WDAC</span><span class="sxs-lookup"><span data-stu-id="882e0-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="882e0-104">O WDAC permite que um Administrador de TI configuure os seus dispositivos para bloquear o lançamento de aplicações em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="882e0-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="882e0-105">Isto é diferente dos métodos de restrição do dispositivo, como o modo Quiosque, onde o utilizador é apresentado com uma UI que esconde as aplicações no dispositivo mas que ainda podem ser lançadas.</span><span class="sxs-lookup"><span data-stu-id="882e0-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="882e0-106">Apesar de o WDAC estar implementado, as aplicações ainda estão visíveis na lista de Todas as Aplicações, mas o WDAC impede que essas aplicações e processos possam ser lançados pelo utilizador do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="882e0-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="882e0-107">Um dispositivo pode ser atribuído mais do que uma política WDAC.</span><span class="sxs-lookup"><span data-stu-id="882e0-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="882e0-108">Se várias políticas do WDAC forem definidas num sistema, as mais restritivas fazem efeito.</span><span class="sxs-lookup"><span data-stu-id="882e0-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="882e0-109">Quando os utilizadores finais tentarem lançar uma aplicação que é bloqueada pelo WDAC, na HoloLens não receberão uma notificação sobre não poderem lançar essa aplicação.</span><span class="sxs-lookup"><span data-stu-id="882e0-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="882e0-110">O seguinte é um guia para que os utilizadores aprendam a [usar o WDAC e Windows PowerShell para permitir ou bloquear aplicações em HoloLens 2 dispositivos com Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="882e0-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="882e0-111">Quando os utilizadores procuram aplicações instaladas no seu PC Windows 10 usando o primeiro passo de exemplo, podem precisar de fazer algumas tentativas para reduzir os resultados.</span><span class="sxs-lookup"><span data-stu-id="882e0-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="882e0-112">Se não souber o nome completo do pacote, poderá ter de executar 'Get-AppxPackage -name \* YourBestGuess' \* algumas vezes para o encontrar.</span><span class="sxs-lookup"><span data-stu-id="882e0-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="882e0-113">Em seguida, uma vez que você tem o nome executar '$package 1 = Get-AppxPackage -name Atual.PackageName'</span><span class="sxs-lookup"><span data-stu-id="882e0-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="882e0-114">Por exemplo, executar o seguinte para Microsoft Edge retornará mais do que um resultado, mas dessa lista pode identificar que o nome completo de que precisa é Microsoft.MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="882e0-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="882e0-115">Pacote nomes de família para aplicativos em HoloLens</span><span class="sxs-lookup"><span data-stu-id="882e0-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="882e0-116">No guia acima indicado, pode editar manualmente newPolicy.xml e adicionar regras para aplicações que só são instaladas em HoloLens com os nomes da família do pacote.</span><span class="sxs-lookup"><span data-stu-id="882e0-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="882e0-117">Por vezes, existem aplicações que pode usar para usar que não estão no seu PC de secretária que deseja adicionar à política.</span><span class="sxs-lookup"><span data-stu-id="882e0-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="882e0-118">Aqui está uma lista de aplicações comumente usadas e In-Box para HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="882e0-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="882e0-119">Nome da Aplicação</span><span class="sxs-lookup"><span data-stu-id="882e0-119">App Name</span></span>                   | <span data-ttu-id="882e0-120">Nome da família do pacote</span><span class="sxs-lookup"><span data-stu-id="882e0-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="882e0-121">Espectador 3D</span><span class="sxs-lookup"><span data-stu-id="882e0-121">3D Viewer</span></span>                  | <span data-ttu-id="882e0-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="882e0-123">Instalador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="882e0-123">App Installer</span></span>              | <span data-ttu-id="882e0-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="882e0-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="882e0-125">Calendário</span><span class="sxs-lookup"><span data-stu-id="882e0-125">Calendar</span></span>                   | <span data-ttu-id="882e0-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="882e0-127">Câmara</span><span class="sxs-lookup"><span data-stu-id="882e0-127">Camera</span></span>                     | <span data-ttu-id="882e0-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="882e0-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="882e0-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="882e0-129">Cortana</span></span>                    | <span data-ttu-id="882e0-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="882e0-131">Dinâmica 365 Guias</span><span class="sxs-lookup"><span data-stu-id="882e0-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="882e0-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="882e0-133">Dinâmico 365 Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="882e0-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="882e0-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="882e0-135">Centro de Feedback</span><span class="sxs-lookup"><span data-stu-id="882e0-135">Feedback Hub</span></span>               | <span data-ttu-id="882e0-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="882e0-137">Explorador de Ficheiros</span><span class="sxs-lookup"><span data-stu-id="882e0-137">File Explorer</span></span>              | <span data-ttu-id="882e0-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="882e0-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="882e0-139">Correio</span><span class="sxs-lookup"><span data-stu-id="882e0-139">Mail</span></span>                       | <span data-ttu-id="882e0-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="882e0-141">Loja Microsoft</span><span class="sxs-lookup"><span data-stu-id="882e0-141">Microsoft Store</span></span>            | <span data-ttu-id="882e0-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="882e0-143">Filmes & TV</span><span class="sxs-lookup"><span data-stu-id="882e0-143">Movies & TV</span></span>                | <span data-ttu-id="882e0-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="882e0-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="882e0-145">OneDrive</span></span>                   | <span data-ttu-id="882e0-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="882e0-147">Fotografias</span><span class="sxs-lookup"><span data-stu-id="882e0-147">Photos</span></span>                     | <span data-ttu-id="882e0-148">A Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="882e0-149">Definições</span><span class="sxs-lookup"><span data-stu-id="882e0-149">Settings</span></span>                   | <span data-ttu-id="882e0-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="882e0-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="882e0-151">Sugestões</span><span class="sxs-lookup"><span data-stu-id="882e0-151">Tips</span></span>                       | <span data-ttu-id="882e0-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="882e0-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="882e0-153">1 - Bloquear o Instalador de Aplicações apenas bloqueará a aplicação App Installer, e não aplicações instaladas a partir de outras fontes, como a Microsoft Store ou a partir da sua solução MDM.</span><span class="sxs-lookup"><span data-stu-id="882e0-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="882e0-154">Como encontrar um nome de família pacote</span><span class="sxs-lookup"><span data-stu-id="882e0-154">How to find a Package Family Name</span></span>

<span data-ttu-id="882e0-155">Se uma aplicação não estiver nesta lista, então um utilizador poderá utilizar o Portal do Dispositivo, ligado a um HoloLens 2 que instalou a aplicação desejada para ser bloqueada, para determinar o PackageRelativeID e a partir daí obter o Nome Dedesempaly.</span><span class="sxs-lookup"><span data-stu-id="882e0-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="882e0-156">Instale a aplicação no seu dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="882e0-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="882e0-157">Abrir Definições -> Atualizações & Segurança -> Para os desenvolvedores e ativar **o modo de programação** e, em seguida, **o portal do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="882e0-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="882e0-158">Mais informações para ler mais sobre [a configuração e utilização do portal do dispositivo aqui](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="882e0-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="882e0-159">Assim que o Portal do Dispositivo estiver ligado, navegue para **Visualizações** e depois **para apps**.</span><span class="sxs-lookup"><span data-stu-id="882e0-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="882e0-160">Dentro do painel de Aplicações Instaladas, utilize o dropdown para selecionar a aplicação instalada.</span><span class="sxs-lookup"><span data-stu-id="882e0-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="882e0-161">Localize o PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="882e0-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="882e0-162">Copiar caracteres de aplicativos antes do !, estes caracteres serão o seu Nome Demôndio Pacote.</span><span class="sxs-lookup"><span data-stu-id="882e0-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


