---
title: Atualizar HoloLens 2
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
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924116"
---
# <a name="update-hololens-2"></a><span data-ttu-id="fc3c2-104">Atualizar HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="fc3c2-104">Update HoloLens 2</span></span>

<span data-ttu-id="fc3c2-105">O HoloLens utiliza o Windows Update, tal como outros dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="fc3c2-106">Os holoLens descarregarão e instalarão automaticamente atualizações do sistema sempre que estiver ligado à energia e ligado à Internet, mesmo quando este se encontra em modo de espera.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="fc3c2-107">Este artigo irá percorrer as ferramentas HoloLens para:</span><span class="sxs-lookup"><span data-stu-id="fc3c2-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="fc3c2-108">visualizando a sua versão atual do sistema operativo (número de construção)</span><span class="sxs-lookup"><span data-stu-id="fc3c2-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="fc3c2-109">verificação de atualizações</span><span class="sxs-lookup"><span data-stu-id="fc3c2-109">checking for updates</span></span>
- <span data-ttu-id="fc3c2-110">atualizar manualmente HoloLens</span><span class="sxs-lookup"><span data-stu-id="fc3c2-110">manually updating HoloLens</span></span>
- <span data-ttu-id="fc3c2-111">voltando para uma atualização mais antiga</span><span class="sxs-lookup"><span data-stu-id="fc3c2-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="fc3c2-112">Verifique a versão do seu sistema operativo (número de construção)</span><span class="sxs-lookup"><span data-stu-id="fc3c2-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="fc3c2-113">Pode verificar o número da versão do sistema (número de construção) abrindo a aplicação Definições e selecionando **System**  >  **About**.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="fc3c2-114">Verifique as atualizações e atualização manual</span><span class="sxs-lookup"><span data-stu-id="fc3c2-114">Check for updates and manually update</span></span>

<span data-ttu-id="fc3c2-115">Pode verificar se há atualizações a qualquer momento nas definições.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="fc3c2-116">Para ver as atualizações disponíveis e verificar novas atualizações:</span><span class="sxs-lookup"><span data-stu-id="fc3c2-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="fc3c2-117">Abra a aplicação **Definições**.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="fc3c2-118">Navegue para **atualizar & atualização do** Windows de segurança  >  .</span><span class="sxs-lookup"><span data-stu-id="fc3c2-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="fc3c2-119">Selecione **Procurar atualizações**.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-119">Select **Check for updates**.</span></span>

<span data-ttu-id="fc3c2-120">Se houver uma atualização disponível, começará a descarregar a nova versão.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="fc3c2-121">Depois de concluída a transferência, selecione o botão **Restart Now** para ativar a instalação.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="fc3c2-122">Se o seu dispositivo estiver abaixo dos 40% e não estiver ligado, o reinício não começará a instalar a atualização.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="fc3c2-123">Enquanto os HoloLens estiverem a instalar a atualização, apresentará engrenagens giratórias e um indicador de progresso.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="fc3c2-124">Não desligue os HoloLens durante este tempo.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="fc3c2-125">Reiniciar-se-á automaticamente depois de concluída a instalação.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="fc3c2-126">HoloLens aplica uma atualização de cada vez.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="fc3c2-127">Se o seu HoloLens estiver a mais de uma versão por trás da mais recente, poderá ter de passar várias vezes pelo processo de atualização para o atualizar completamente.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="fc3c2-128">Volte para uma versão anterior</span><span class="sxs-lookup"><span data-stu-id="fc3c2-128">Go back to a previous version</span></span>

<span data-ttu-id="fc3c2-129">Em alguns casos, talvez queira voltar a uma versão anterior do software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="fc3c2-130">Os passos recomendados são:</span><span class="sxs-lookup"><span data-stu-id="fc3c2-130">The recommended steps are:</span></span>

1. <span data-ttu-id="fc3c2-131">Contacte o Suporte para ver se eles podem corrigir o seu problema.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="fc3c2-132">Certifique-se de que a telemetria **Opcional** ou **Completa** está ativada - isto torna o seu bug mais accuível e mais fácil para os engenheiros diagnosticarem.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="fc3c2-133">[O feedback do ficheiro](hololens-feedback.md) é o mais descritivo possível.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="fc3c2-134">Tome nota do título ou use a funcionalidade de partilha para que possa partilhar o seu bug com o Suporte.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="fc3c2-135">[Suporte de](https://aka.ms/hlsupport)contato .</span><span class="sxs-lookup"><span data-stu-id="fc3c2-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="fc3c2-136">Se o seu problema for um problema que precisa de ser resolvido retornando a uma versão anterior, eles podem fornecer-lhe a FFU para piscar o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="fc3c2-137">Se isso não funcionar, em seguida, [reinicie ou reflash seus HoloLens 2 com o Companheiro de Recuperação Avançado](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="fc3c2-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="fc3c2-138">No seu PC, descarregue o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="fc3c2-139">Certifique-se de que não tem telefones ou dispositivos Windows ligados ao seu PC.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="fc3c2-140">Escolha a versão a que pretende piscar:</span><span class="sxs-lookup"><span data-stu-id="fc3c2-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="fc3c2-141">Você pode baixar o [mais recente lançamento HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="fc3c2-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="fc3c2-142">Pode utilizar a construção padrão que o ARC acolhe.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="fc3c2-143">(Se escolher esta opção, salte o passo seguinte.)</span><span class="sxs-lookup"><span data-stu-id="fc3c2-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="fc3c2-144">Você pode usar uma construção Suporte fornecido com você.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="fc3c2-145">Quando terminar estes downloads, abra as  >  **transferências do** File Explorer .</span><span class="sxs-lookup"><span data-stu-id="fc3c2-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="fc3c2-146">Clique com o botão direito na pasta com fecho que acabou de descarregar e **selecione Extrair todo** o  >  **Extrato** para desapertá-la.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="fc3c2-147">Ligue os HoloLens ao seu PC utilizando um cabo USB-A a USB-C.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="fc3c2-148">(Mesmo que tenha usado outros cabos para ligar os hololens, este funciona melhor.)</span><span class="sxs-lookup"><span data-stu-id="fc3c2-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="fc3c2-149">O Companheiro de Recuperação Avançada deteta automaticamente os seus HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="fc3c2-150">Selecione o azulejo **microsoft HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="fc3c2-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="fc3c2-151">No ecrã seguinte, selecione **Manual** e, em seguida, selecione o ficheiro de instalação contido na pasta que abriu no passo 4.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="fc3c2-152">(Procure um ficheiro com a extensão .ffu.)</span><span class="sxs-lookup"><span data-stu-id="fc3c2-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="fc3c2-153">**Selecione Instalar o software** e seguir as instruções.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="fc3c2-154">Voltar a uma versão anterior elimina os seus ficheiros e configurações pessoais.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="fc3c2-155">Além disso, se pretender manter-se no seu desbloqueio instalado atualmente, também pode interromper manualmente [as atualizações](hololens-updates.md#pause-updates-via-device).</span><span class="sxs-lookup"><span data-stu-id="fc3c2-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="fc3c2-156">Isto dará tempo à Equipa de Engenharia para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="fc3c2-157">Programa Insider do Windows em HoloLens</span><span class="sxs-lookup"><span data-stu-id="fc3c2-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="fc3c2-158">Quer ver as últimas funcionalidades em HoloLens?</span><span class="sxs-lookup"><span data-stu-id="fc3c2-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="fc3c2-159">Em caso afirmativo, junte-se ao Programa Insider do Windows; terá acesso a pré-visualizações de atualizações de software HoloLens antes de estarem disponíveis para o público em geral.</span><span class="sxs-lookup"><span data-stu-id="fc3c2-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="fc3c2-160">[Obtenha a pré-visualização do Windows Insider para o Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="fc3c2-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
