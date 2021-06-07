---
title: Atualizar HoloLens
description: Saiba como verificar o número de construção dos HoloLens, mantenha-se atualizado com as atualizações do dispositivo, junte-se ao Programa Insiders e reverta as atualizações.
keywords: como, atualizar, reverter, HoloLens, verificar construção, número de construção
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378585"
---
# <a name="update-hololens"></a><span data-ttu-id="63a9f-104">Atualizar HoloLens</span><span class="sxs-lookup"><span data-stu-id="63a9f-104">Update HoloLens</span></span>

<span data-ttu-id="63a9f-105">O HoloLens utiliza o Windows Update, tal como outros dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="63a9f-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="63a9f-106">Os holoLens descarregarão e instalarão automaticamente atualizações do sistema sempre que estiver ligado à energia e ligado à Internet, mesmo quando este se encontra em modo de espera.</span><span class="sxs-lookup"><span data-stu-id="63a9f-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="63a9f-107">Este artigo irá percorrer as ferramentas HoloLens para:</span><span class="sxs-lookup"><span data-stu-id="63a9f-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="63a9f-108">visualizando a sua versão atual do sistema operativo (número de construção)</span><span class="sxs-lookup"><span data-stu-id="63a9f-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="63a9f-109">verificação de atualizações</span><span class="sxs-lookup"><span data-stu-id="63a9f-109">checking for updates</span></span>
- <span data-ttu-id="63a9f-110">atualizar manualmente HoloLens</span><span class="sxs-lookup"><span data-stu-id="63a9f-110">manually updating HoloLens</span></span>
- <span data-ttu-id="63a9f-111">voltando para uma atualização mais antiga</span><span class="sxs-lookup"><span data-stu-id="63a9f-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="63a9f-112">Verifique a versão do seu sistema operativo (número de construção)</span><span class="sxs-lookup"><span data-stu-id="63a9f-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="63a9f-113">Pode verificar o número da versão do sistema (número de construção) abrindo a aplicação Definições e selecionando **System**  >  **About**.</span><span class="sxs-lookup"><span data-stu-id="63a9f-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="63a9f-114">Verifique as atualizações e atualização manual</span><span class="sxs-lookup"><span data-stu-id="63a9f-114">Check for updates and manually update</span></span>

<span data-ttu-id="63a9f-115">Pode verificar se há atualizações a qualquer momento nas definições.</span><span class="sxs-lookup"><span data-stu-id="63a9f-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="63a9f-116">Para ver as atualizações disponíveis e verificar novas atualizações:</span><span class="sxs-lookup"><span data-stu-id="63a9f-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="63a9f-117">Abra a aplicação **Definições**.</span><span class="sxs-lookup"><span data-stu-id="63a9f-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="63a9f-118">Navegue para **atualizar & atualização do** Windows de segurança  >  .</span><span class="sxs-lookup"><span data-stu-id="63a9f-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="63a9f-119">Selecione **Procurar atualizações**.</span><span class="sxs-lookup"><span data-stu-id="63a9f-119">Select **Check for updates**.</span></span>

<span data-ttu-id="63a9f-120">Se houver uma atualização disponível, começará a descarregar a nova versão.</span><span class="sxs-lookup"><span data-stu-id="63a9f-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="63a9f-121">Depois de concluída a transferência, selecione o botão **Restart Now** para ativar a instalação.</span><span class="sxs-lookup"><span data-stu-id="63a9f-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="63a9f-122">Se o seu dispositivo estiver abaixo dos 40% e não estiver ligado, o reinício não começará a instalar a atualização.</span><span class="sxs-lookup"><span data-stu-id="63a9f-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="63a9f-123">Enquanto os HoloLens estiverem a instalar a atualização, apresentará engrenagens giratórias e um indicador de progresso.</span><span class="sxs-lookup"><span data-stu-id="63a9f-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="63a9f-124">Não desligue os HoloLens durante este tempo.</span><span class="sxs-lookup"><span data-stu-id="63a9f-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="63a9f-125">Reiniciar-se-á automaticamente depois de concluída a instalação.</span><span class="sxs-lookup"><span data-stu-id="63a9f-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="63a9f-126">HoloLens aplica uma atualização de cada vez.</span><span class="sxs-lookup"><span data-stu-id="63a9f-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="63a9f-127">Se o seu HoloLens estiver a mais de uma versão por trás da mais recente, poderá ter de passar várias vezes pelo processo de atualização para o atualizar completamente.</span><span class="sxs-lookup"><span data-stu-id="63a9f-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="63a9f-128">Volte para uma versão anterior - HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="63a9f-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="63a9f-129">Em alguns casos, talvez queira voltar a uma versão anterior do software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="63a9f-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="63a9f-130">Pode fazê-lo utilizando o Advanced Recovery Companion para redefinir os hololens para a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="63a9f-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="63a9f-131">Voltar a uma versão anterior elimina os seus ficheiros e configurações pessoais.</span><span class="sxs-lookup"><span data-stu-id="63a9f-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="63a9f-132">Para voltar a uma versão anterior do HoloLens 2, siga estes passos:</span><span class="sxs-lookup"><span data-stu-id="63a9f-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="63a9f-133">Certifique-se de que não tem telefones ou dispositivos Windows ligados ao seu PC.</span><span class="sxs-lookup"><span data-stu-id="63a9f-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="63a9f-134">No seu PC, descarregue o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="63a9f-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="63a9f-135">Descarregue o [mais recente lançamento holoLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="63a9f-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="63a9f-136">Quando terminar estes downloads, abra os downloads **do Explorador de**  >  **Ficheiros**.</span><span class="sxs-lookup"><span data-stu-id="63a9f-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="63a9f-137">Clique com o botão direito na pasta com fecho que acabou de descarregar e **selecione Extrair todo** o  >  **Extrato** para desapertá-la.</span><span class="sxs-lookup"><span data-stu-id="63a9f-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="63a9f-138">Ligue os HoloLens ao seu PC utilizando um cabo USB-A a USB-C.</span><span class="sxs-lookup"><span data-stu-id="63a9f-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="63a9f-139">(Mesmo que tenha usado outros cabos para ligar os hololens, este funciona melhor.)</span><span class="sxs-lookup"><span data-stu-id="63a9f-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="63a9f-140">O Companheiro de Recuperação Avançada deteta automaticamente os seus HoloLens.</span><span class="sxs-lookup"><span data-stu-id="63a9f-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="63a9f-141">Selecione o azulejo **microsoft HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="63a9f-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="63a9f-142">No ecrã seguinte, selecione **Manual** e, em seguida, selecione o ficheiro de instalação contido na pasta que abriu no passo 4.</span><span class="sxs-lookup"><span data-stu-id="63a9f-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="63a9f-143">(Procure um ficheiro com a extensão .ffu.)</span><span class="sxs-lookup"><span data-stu-id="63a9f-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="63a9f-144">**Selecione Instalar o software** e seguir as instruções.</span><span class="sxs-lookup"><span data-stu-id="63a9f-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="63a9f-145">Volte para uma versão anterior - HoloLens (1ª Gen)</span><span class="sxs-lookup"><span data-stu-id="63a9f-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="63a9f-146">Em alguns casos, talvez queira voltar a uma versão anterior do software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="63a9f-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="63a9f-147">Pode fazê-lo utilizando a Ferramenta de Recuperação de Dispositivos do Windows para redefinir os HoloLens para a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="63a9f-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="63a9f-148">Voltar a uma versão anterior elimina os seus ficheiros e configurações pessoais.</span><span class="sxs-lookup"><span data-stu-id="63a9f-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="63a9f-149">Para voltar a uma versão anterior do HoloLens 1, siga estes passos:</span><span class="sxs-lookup"><span data-stu-id="63a9f-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="63a9f-150">Certifique-se de que não tem telefones ou dispositivos Windows ligados ao seu PC.</span><span class="sxs-lookup"><span data-stu-id="63a9f-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="63a9f-151">No seu PC, descarregue a [Ferramenta de Recuperação de Dispositivos windows (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="63a9f-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="63a9f-152">Descarregue o pacote de recuperação da [Atualização de Aniversário holoLens](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="63a9f-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="63a9f-153">Quando os downloads terminarem, abra o **Explorador de**  >  **Ficheiros Downloads**.</span><span class="sxs-lookup"><span data-stu-id="63a9f-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="63a9f-154">Clique com o botão direito na pasta com fecho que acabou de descarregar e **selecione Extrair todo** o  >  **Extrato** para desapertá-la.</span><span class="sxs-lookup"><span data-stu-id="63a9f-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="63a9f-155">Ligue os HoloLens ao seu PC utilizando o cabo micro-USB que ele veio.</span><span class="sxs-lookup"><span data-stu-id="63a9f-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="63a9f-156">(Mesmo que tenha usado outros cabos para ligar os hololens, este funciona melhor.)</span><span class="sxs-lookup"><span data-stu-id="63a9f-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="63a9f-157">O WDRT detetará automaticamente os seus HoloLens.</span><span class="sxs-lookup"><span data-stu-id="63a9f-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="63a9f-158">Selecione o azulejo **microsoft HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="63a9f-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="63a9f-159">No ecrã seguinte, selecione **Manual** e escolha o ficheiro de instalação contido na pasta que abriu no passo 4.</span><span class="sxs-lookup"><span data-stu-id="63a9f-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="63a9f-160">(Procure um ficheiro com a extensão .ffu.)</span><span class="sxs-lookup"><span data-stu-id="63a9f-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="63a9f-161">**Selecione Instalar o software** e seguir as instruções.</span><span class="sxs-lookup"><span data-stu-id="63a9f-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="63a9f-162">Se o WDRT não detetar os hololens, tente reiniciar o seu PC.</span><span class="sxs-lookup"><span data-stu-id="63a9f-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="63a9f-163">Se isso não funcionar, selecione **O meu dispositivo não foi detetado**, selecione Microsoft **HoloLens** e, em seguida, siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="63a9f-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="63a9f-164">Programa Insider do Windows em HoloLens</span><span class="sxs-lookup"><span data-stu-id="63a9f-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="63a9f-165">Quer ver as últimas funcionalidades em HoloLens?</span><span class="sxs-lookup"><span data-stu-id="63a9f-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="63a9f-166">Em caso afirmativo, junte-se ao Programa Insider do Windows; terá acesso a pré-visualizações de atualizações de software HoloLens antes de estarem disponíveis para o público em geral.</span><span class="sxs-lookup"><span data-stu-id="63a9f-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="63a9f-167">[Obtenha a pré-visualização do Windows Insider para o Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="63a9f-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
