---
title: Encontre e guarde ficheiros sobre HoloLens
description: Aprenda a usar o File Explorer no HoloLens para abrir, visualizar e gerir ficheiros no seu dispositivo de realidade mista.
keywords: como, picker de ficheiros, ficheiros, fotos, vídeos, imagens, OneDrive, armazenamento, explorador de ficheiros, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636185"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="4412c-104">Encontre, abra e guarde ficheiros sobre HoloLens</span><span class="sxs-lookup"><span data-stu-id="4412c-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="4412c-105">Os ficheiros que cria no HoloLens, incluindo fotos e vídeos, são guardados diretamente no seu dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4412c-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="4412c-106">Veja-os e gere-os da mesma forma que geriria ficheiros em Windows 10:</span><span class="sxs-lookup"><span data-stu-id="4412c-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="4412c-107">Utilizar a aplicação File Explorer para aceder a pastas locais.</span><span class="sxs-lookup"><span data-stu-id="4412c-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="4412c-108">Dentro do armazenamento de uma aplicação.</span><span class="sxs-lookup"><span data-stu-id="4412c-108">Within an app's storage.</span></span>
- <span data-ttu-id="4412c-109">Numa pasta especial (como a biblioteca de vídeo ou música).</span><span class="sxs-lookup"><span data-stu-id="4412c-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="4412c-110">Utilizar um serviço de armazenamento que inclua uma aplicação e um selecionador de ficheiros (como OneDrive).</span><span class="sxs-lookup"><span data-stu-id="4412c-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="4412c-111">Utilizando um PC de secretária ligado ao seu HoloLens utilizando um cabo USB, utilizando o suporte MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="4412c-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="4412c-112">Ver ficheiros em HoloLens usando o Explorador de Ficheiros</span><span class="sxs-lookup"><span data-stu-id="4412c-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="4412c-113">Aplica-se a todos os HoloLens 2 dispositivos e HoloLens (1ª gen) a partir da [Windows 10 atualização de abril de 2018 (RS4) para HoloLens](/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="4412c-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="4412c-114">Utilize o File Explorer no HoloLens para visualizar e gerir ficheiros no seu dispositivo, incluindo objetos 3D, documentos e imagens.</span><span class="sxs-lookup"><span data-stu-id="4412c-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="4412c-115">Vá para **iniciar**   >  **todas as aplicações**   >  **File Explorer** para começar.</span><span class="sxs-lookup"><span data-stu-id="4412c-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="4412c-116">Se não houver ficheiros listados no Explorador de Ficheiros, selecione **Este Dispositivo** no painel superior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="4412c-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="4412c-117">Se não vir ficheiros no File Explorer, o filtro "Recente" pode estar ativo (o ícone do relógio é realçado no painel esquerdo).</span><span class="sxs-lookup"><span data-stu-id="4412c-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="4412c-118">Para corrigir isto, selecione o ícone do documento **deste dispositivo** no painel esquerdo (por baixo do ícone do relógio) ou abra o menu e selecione **Este Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="4412c-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="4412c-119">Encontre e veja as suas fotos e vídeos</span><span class="sxs-lookup"><span data-stu-id="4412c-119">Find and view your photos and videos</span></span>

<span data-ttu-id="4412c-120">[A captura de realidade mista](holographic-photos-and-videos.md) permite-lhe tirar fotos e vídeos de realidade mista no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4412c-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="4412c-121">Estas fotos e vídeos são guardados na pasta Camera Roll do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4412c-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="4412c-122">Pode aceder a fotos e vídeos tirados com HoloLens:</span><span class="sxs-lookup"><span data-stu-id="4412c-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="4412c-123">aceder à Câmara Rolar diretamente através da [aplicação Fotos](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="4412c-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="4412c-124">o upload de fotos e vídeos para o armazenamento em nuvem sincronizando as suas fotos e vídeos para OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4412c-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="4412c-125">utilizando a página de Captura de Realidade Mista do Portal do [Dispositivo Windows](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="4412c-125">using the Mixed Reality Capture page of the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="4412c-126">Aplicação Fotografias</span><span class="sxs-lookup"><span data-stu-id="4412c-126">Photos app</span></span>

<span data-ttu-id="4412c-127">A aplicação Fotos é uma das aplicações predefinidos no menu **Iniciar,** e vem incorporada com HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4412c-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="4412c-128">Saiba mais sobre [a utilização da aplicação Fotos para visualizar o conteúdo.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="4412c-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="4412c-129">Também pode instalar a [aplicação OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) a partir do Microsoft Store para sincronizar fotos para outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4412c-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="4412c-130">OneDrive app</span><span class="sxs-lookup"><span data-stu-id="4412c-130">OneDrive app</span></span>

<span data-ttu-id="4412c-131">[OneDrive](https://onedrive.live.com/) permite-lhe aceder, gerir e partilhar as suas fotos e vídeos com qualquer dispositivo e com qualquer utilizador.</span><span class="sxs-lookup"><span data-stu-id="4412c-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="4412c-132">Para aceder às fotos e vídeos capturados no HoloLens, descarregue a [aplicação OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) a partir do Microsoft Store no seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4412c-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="4412c-133">Uma vez descarregado, abra a aplicação OneDrive e selecione **Definições**  >  **upload da Câmara**, e ligue o upload da **Câmara**.</span><span class="sxs-lookup"><span data-stu-id="4412c-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="4412c-134">Ligação para um PC</span><span class="sxs-lookup"><span data-stu-id="4412c-134">Connect to a PC</span></span>

<span data-ttu-id="4412c-135">Se o seu HoloLens estiver a executar a [atualização Windows 10 abril de 2018](/windows/mixed-reality/release-notes-april-2018) ou mais tarde, pode ligar o seu HoloLens a um PC Windows 10 utilizando um cabo USB para navegar em fotografias e vídeos no dispositivo utilizando MTP (protocolo de transferência de meios).</span><span class="sxs-lookup"><span data-stu-id="4412c-135">If your HoloLens is running the [Windows 10 April 2018 update](/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="4412c-136">Terá de se certificar de que o dispositivo está desbloqueado para navegar em ficheiros se tiver um PIN ou uma palavra-passe configurado no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4412c-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="4412c-137">Se tiver ativado o Portal do [Dispositivo Windows,](/windows/mixed-reality/using-the-windows-device-portal)pode usá-lo para navegar, recuperar e gerir as fotos e vídeos armazenados no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4412c-137">If you have enabled the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="4412c-138">Aceder a ficheiros dentro de uma aplicação</span><span class="sxs-lookup"><span data-stu-id="4412c-138">Access files within an app</span></span>

<span data-ttu-id="4412c-139">Se uma aplicação guardar ficheiros no seu dispositivo, pode utilizar essa aplicação para aceder aos mesmos.</span><span class="sxs-lookup"><span data-stu-id="4412c-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="4412c-140">Solicitando ficheiros de outra app</span><span class="sxs-lookup"><span data-stu-id="4412c-140">Requesting files from another app</span></span>

<span data-ttu-id="4412c-141">Uma aplicação pode solicitar para guardar um ficheiro ou abrir um ficheiro de outra aplicação utilizando [pickers de ficheiros](/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="4412c-141">An application can request to save a file or open a file from another app by using [file pickers](/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="4412c-142">Pastas conhecidas</span><span class="sxs-lookup"><span data-stu-id="4412c-142">Known folders</span></span>

<span data-ttu-id="4412c-143">HoloLens suporta uma série de [pastas conhecidas](/windows/mixed-reality/app-model#known-folders) que as aplicações podem solicitar permissão para aceder.</span><span class="sxs-lookup"><span data-stu-id="4412c-143">HoloLens supports a number of [known folders](/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="4412c-144">Ver ficheiros HoloLens no seu PC</span><span class="sxs-lookup"><span data-stu-id="4412c-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="4412c-145">Semelhante a outros dispositivos móveis, conecte-se HoloLens ao seu PC de secretária utilizando MTP (Media Transfer Protocol) e abra o File Explorer no PC para aceder às suas bibliotecas HoloLens para facilitar a transferência.</span><span class="sxs-lookup"><span data-stu-id="4412c-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="4412c-146">Para ver os seus ficheiros HoloLens no Explorador de Ficheiros no seu PC:</span><span class="sxs-lookup"><span data-stu-id="4412c-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="4412c-147">Inscreva-se para HoloLens e, em seguida, ligue-o ao PC utilizando o cabo USB que veio com o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4412c-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="4412c-148">Selecione **Dispositivo Aberto para visualizar ficheiros com o Explorador de Ficheiros,** ou abra o Explorador de Ficheiros no PC e navegue para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4412c-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="4412c-149">Para ver informações sobre o seu HoloLens, clique com o botão direito no nome do dispositivo no Explorador de Ficheiros no seu PC e, em seguida, selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4412c-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="4412c-150">HoloLens (1º gênero) não suporta a ligação a discos rígidos externos ou cartões SD.</span><span class="sxs-lookup"><span data-stu-id="4412c-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="4412c-151">Sincronizar com a nuvem</span><span class="sxs-lookup"><span data-stu-id="4412c-151">Sync to the cloud</span></span>

<span data-ttu-id="4412c-152">Para sincronizar fotos e outros ficheiros do seu HoloLens para a nuvem, instale e instale OneDrive no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4412c-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="4412c-153">Para obter OneDrive, procure-o no Microsoft Store na sua HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4412c-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="4412c-154">HoloLens não faz o back-up de ficheiros e dados de aplicações, por isso é uma boa ideia guardar as suas coisas importantes para OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4412c-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="4412c-155">Desta forma, se reiniciar o seu dispositivo ou desinstalar uma aplicação, a sua informação será apoiada.</span><span class="sxs-lookup"><span data-stu-id="4412c-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
