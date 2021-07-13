---
title: Reiniciar, reiniciar ou recuperar HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Como utilizar Windows Ferramenta de Recuperação de Dispositivos para mostrar uma imagem a HoloLens 1ª Gen.
keywords: como, reiniciar, reiniciar, recuperar, reset duro, reset suave, ciclo de potência, HoloLens, desligar, wdrt, ferramenta de recuperação do dispositivo windows
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635233"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="85b79-104">Reiniciar, reiniciar ou recuperar HoloLens (1ª Gen)</span><span class="sxs-lookup"><span data-stu-id="85b79-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="85b79-105">Se estiver a ter problemas com o seu HoloLens, pode querer reiniciar ou reiniciar ou até reflash o dispositivo utilizando a recuperação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="85b79-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="85b79-106">Este artigo guia-o através dos passos de recuperação recomendados em ordem.</span><span class="sxs-lookup"><span data-stu-id="85b79-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="85b79-107">Se procura recuperar um HoloLens 2, consulte [Recuperar um HoloLens 2](hololens-recovery.md), uma vez que esse processo difere.</span><span class="sxs-lookup"><span data-stu-id="85b79-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="85b79-108">Este artigo centra-se no dispositivo e software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="85b79-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="85b79-109">Se os seus hologramas não parecerem adequados, consulte **[HoloLens considerações ambientais](hololens-environment-considerations.md)** para obter informações sobre fatores que melhorem a qualidade do holograma.</span><span class="sxs-lookup"><span data-stu-id="85b79-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="85b79-110">Reiniciar</span><span class="sxs-lookup"><span data-stu-id="85b79-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="85b79-111">Faça um reinício seguro utilizando Cortana</span><span class="sxs-lookup"><span data-stu-id="85b79-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="85b79-112">A forma mais segura de reiniciar o HoloLens é usando Cortana, que geralmente é a primeira coisa a tentar quando se experimenta um problema com HoloLens.</span><span class="sxs-lookup"><span data-stu-id="85b79-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="85b79-113">Cortana não está disponível em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="85b79-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="85b79-114">Cortana está disponível em todos os dispositivos HoloLens (1ª Gen).</span><span class="sxs-lookup"><span data-stu-id="85b79-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="85b79-115">Cortana está disponível em HoloLens 2 dispositivos em construções antes da atualização holograpic, versão 2004 da Windows.</span><span class="sxs-lookup"><span data-stu-id="85b79-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="85b79-116">Ligue o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="85b79-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="85b79-117">Certifique-se de que um utilizador está a iniciar sessão e que o dispositivo não está à espera de uma palavra-passe para o desbloquear.</span><span class="sxs-lookup"><span data-stu-id="85b79-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="85b79-118">Diz "Ei Cortana, reinicie" ou "Ei Cortana, reinicie".</span><span class="sxs-lookup"><span data-stu-id="85b79-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="85b79-119">Cortana responderão e pedir-lhe-ão que confirme.</span><span class="sxs-lookup"><span data-stu-id="85b79-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="85b79-120">Espere um som para tocar depois da pergunta, e depois diga "Sim".</span><span class="sxs-lookup"><span data-stu-id="85b79-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="85b79-121">O dispositivo vai reiniciar.</span><span class="sxs-lookup"><span data-stu-id="85b79-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="85b79-122">Use o botão de alimentação para fazer um reinício seguro</span><span class="sxs-lookup"><span data-stu-id="85b79-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="85b79-123">Se ainda não conseguir reiniciar o seu dispositivo, tente reiniciá-lo utilizando o botão **de alimentação:**</span><span class="sxs-lookup"><span data-stu-id="85b79-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="85b79-124">Pressione e segure o botão **de alimentação** durante 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="85b79-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="85b79-125">Após 1 segundo, todos os cinco LEDs iluminar-se-ão e, em seguida, desligar-se-ão lentamente um a um da direita para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="85b79-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="85b79-126">Após 5 segundos, todos os LEDs estarão desligados, indicando uma paragem bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="85b79-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="85b79-127">Pare de premir o botão imediatamente depois de todos os LEDs terem desligado.</span><span class="sxs-lookup"><span data-stu-id="85b79-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="85b79-128">Espere 1 minuto para a paralisação estar completa.</span><span class="sxs-lookup"><span data-stu-id="85b79-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="85b79-129">A paralisação pode ainda estar em curso mesmo depois de os visores estarem desligados.</span><span class="sxs-lookup"><span data-stu-id="85b79-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="85b79-130">Volte a ligar o aparelho premindo e segurando o botão **de alimentação** durante 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="85b79-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="85b79-131">Faça um reinício seguro utilizando o Portal do Dispositivo Windows</span><span class="sxs-lookup"><span data-stu-id="85b79-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="85b79-132">Para este processo, HoloLens tem de ser configurado como um dispositivo de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="85b79-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="85b79-133">Saiba mais no [Portal Windows dispositivo.](/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="85b79-133">Learn more at [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="85b79-134">Se o procedimento anterior não funcionar, tente reiniciar o dispositivo utilizando [Windows Portal do Dispositivo](/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="85b79-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="85b79-135">No canto superior direito, encontre a opção de reiniciar ou desligar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="85b79-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="85b79-136">Faça um reinício forçado inseguro</span><span class="sxs-lookup"><span data-stu-id="85b79-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="85b79-137">Se os métodos anteriores não reiniciarem a sua HoloLens, force um recomeço.</span><span class="sxs-lookup"><span data-stu-id="85b79-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="85b79-138">Este método equivale a remover e reinstalar a bateria.</span><span class="sxs-lookup"><span data-stu-id="85b79-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="85b79-139">É perigoso porque pode deixar o seu dispositivo num estado corrompido.</span><span class="sxs-lookup"><span data-stu-id="85b79-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="85b79-140">Se isso acontecer, terás de mostrar a tua HoloLens.</span><span class="sxs-lookup"><span data-stu-id="85b79-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="85b79-141">Este é um método potencialmente prejudicial e só deve ser usado se os métodos anteriormente citados não funcionarem.</span><span class="sxs-lookup"><span data-stu-id="85b79-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="85b79-142">Pressione e segure o botão **de alimentação** durante pelo menos 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="85b79-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="85b79-143">Não faz mal segurar o botão por mais de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="85b79-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="85b79-144">É seguro ignorar qualquer atividade LED.</span><span class="sxs-lookup"><span data-stu-id="85b79-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="85b79-145">Solte o botão e aguarde 2-3 segundos.</span><span class="sxs-lookup"><span data-stu-id="85b79-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="85b79-146">Pressione e segure o botão **de alimentação** durante 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="85b79-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="85b79-147">Se ainda tiver problemas, prima o botão **de alimentação** durante 4 segundos, até que todos os indicadores da bateria se desvaneçam e o ecrã deixe de exibir hologramas.</span><span class="sxs-lookup"><span data-stu-id="85b79-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="85b79-148">Aguarde 1 minuto e, em seguida, prima novamente o botão **de alimentação** para ligar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="85b79-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="85b79-149">Volte para uma versão anterior - HoloLens (1ª Gen)</span><span class="sxs-lookup"><span data-stu-id="85b79-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="85b79-150">Em alguns casos, é melhor voltar a uma versão anterior do software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="85b79-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="85b79-151">Pode fazê-lo utilizando a Ferramenta de Recuperação do Dispositivo Windows para redefinir o seu HoloLens para a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="85b79-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="85b79-152">Voltar a uma versão anterior elimina os seus ficheiros e configurações pessoais.</span><span class="sxs-lookup"><span data-stu-id="85b79-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="85b79-153">Para voltar a uma versão anterior do HoloLens 1, siga estes passos:</span><span class="sxs-lookup"><span data-stu-id="85b79-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="85b79-154">Certifique-se de que não tem telefones ou dispositivos Windows ligados ao seu PC.</span><span class="sxs-lookup"><span data-stu-id="85b79-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="85b79-155">No seu PC, descarregue a [Ferramenta de Recuperação de Dispositivos Windows (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="85b79-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="85b79-156">Descarregue o [pacote de recuperação da Atualização de Aniversário HoloLens](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="85b79-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="85b79-157">Quando os downloads terminarem, abra o **Explorador de**  >  **Ficheiros Downloads**.</span><span class="sxs-lookup"><span data-stu-id="85b79-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="85b79-158">Clique com o botão direito na pasta com fecho que acabou de descarregar e **selecione Extrair todo** o  >  **Extrato** para desapertá-la.</span><span class="sxs-lookup"><span data-stu-id="85b79-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="85b79-159">Ligação o seu HoloLens para o seu PC utilizando o cabo micro-USB que ele veio.</span><span class="sxs-lookup"><span data-stu-id="85b79-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="85b79-160">(Mesmo que tenha usado outros cabos para ligar o seu HoloLens, este funciona melhor.)</span><span class="sxs-lookup"><span data-stu-id="85b79-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="85b79-161">O WDRT detetará automaticamente o seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="85b79-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="85b79-162">Selecione o **azulejo Microsoft HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="85b79-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="85b79-163">No ecrã seguinte, selecione **Manual** e escolha o ficheiro de instalação contido na pasta que abriu no passo 4.</span><span class="sxs-lookup"><span data-stu-id="85b79-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="85b79-164">(Procure um ficheiro com a extensão .ffu.)</span><span class="sxs-lookup"><span data-stu-id="85b79-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="85b79-165">**Selecione Instalar o software** e seguir as instruções.</span><span class="sxs-lookup"><span data-stu-id="85b79-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="85b79-166">Se o WDRT não detetar a sua HoloLens, tente reiniciar o seu PC.</span><span class="sxs-lookup"><span data-stu-id="85b79-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="85b79-167">Se isso não funcionar, selecione **O meu dispositivo não foi detetado**, selecione **Microsoft HoloLens** e, em seguida, siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="85b79-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="85b79-168">Reset para as definições de fábrica</span><span class="sxs-lookup"><span data-stu-id="85b79-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="85b79-169">A bateria precisa de pelo menos uma carga de 40% para ser reposta.</span><span class="sxs-lookup"><span data-stu-id="85b79-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="85b79-170">Se o seu HoloLens ainda tiver um problema, tente repor o estado da fábrica.</span><span class="sxs-lookup"><span data-stu-id="85b79-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="85b79-171">Este passo mantém a versão do software Holográfico Windows que está instalado no mesmo e devolve tudo o resto às definições de fábrica.</span><span class="sxs-lookup"><span data-stu-id="85b79-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="85b79-172">Se reiniciar o seu dispositivo, todos os seus dados pessoais, aplicações e configurações serão apagados, incluindo informações de reset TPM.</span><span class="sxs-lookup"><span data-stu-id="85b79-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="85b79-173">A reposição só instalará a versão mais recente instalada do Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="85b79-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="85b79-174">Terá de refazer todos os passos de inicialização (calibrar, ligar ao Wi-Fi, criar uma conta de utilizador, descarregar apps, e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="85b79-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="85b79-175">Abra a aplicação Definições e, em seguida, selecione **Update**  >  **Recovery**.</span><span class="sxs-lookup"><span data-stu-id="85b79-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="85b79-176">Selecione a opção **do dispositivo Reset** e leia a mensagem de confirmação.</span><span class="sxs-lookup"><span data-stu-id="85b79-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="85b79-177">Confirme o reset.</span><span class="sxs-lookup"><span data-stu-id="85b79-177">Confirm the reset.</span></span> <span data-ttu-id="85b79-178">O aparelho reiniciará e exibirá um conjunto de engrenagens giratórias e uma barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="85b79-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="85b79-179">Espere cerca de 30 minutos para que este processo esteja concluído.</span><span class="sxs-lookup"><span data-stu-id="85b79-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="85b79-180">Quando estiver feito, o dispositivo reiniciará a experiência "fora da caixa".</span><span class="sxs-lookup"><span data-stu-id="85b79-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="85b79-181">Reinstalar o sistema operativo</span><span class="sxs-lookup"><span data-stu-id="85b79-181">Reinstall the operating system</span></span>

<span data-ttu-id="85b79-182">Se o dispositivo ainda tiver um problema após o reinício e reinicialização, pode utilizar uma ferramenta de recuperação no seu computador para reinstalar o sistema operativo HoloLens e o firmware.</span><span class="sxs-lookup"><span data-stu-id="85b79-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="85b79-183">Os dados que HoloLens necessidades para o reset são embalados numa Atualização Flash Completa (FFU), que é semelhante a um ficheiro .iso, .wim ou .vhd.</span><span class="sxs-lookup"><span data-stu-id="85b79-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="85b79-184">Saiba mais sobre os formatos de ficheiros de imagem FFU.</span><span class="sxs-lookup"><span data-stu-id="85b79-184">Learn about FFU image file formats.</span></span>](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="85b79-185">Pode instalar um novo sistema operativo no seu HoloLens (1º gênero) utilizando a Ferramenta de Recuperação de Dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="85b79-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="85b79-186">Antes de utilizar esta ferramenta, consulte se reiniciar ou reiniciar o seu HoloLens corrige o problema.</span><span class="sxs-lookup"><span data-stu-id="85b79-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="85b79-187">O processo de recuperação pode demorar um pouco.</span><span class="sxs-lookup"><span data-stu-id="85b79-187">The recovery process may take a while.</span></span> <span data-ttu-id="85b79-188">Quando estiver feito, será instalada a versão mais recente do software Holográfico Windows.</span><span class="sxs-lookup"><span data-stu-id="85b79-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="85b79-189">Para utilizar a ferramenta, precisa de um computador a funcionar Windows 10 ou mais tarde com pelo menos 4 GB de espaço de armazenamento gratuito.</span><span class="sxs-lookup"><span data-stu-id="85b79-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="85b79-190">Não podes executar esta ferramenta numa máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="85b79-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="85b79-191">Recupere o seu HoloLens</span><span class="sxs-lookup"><span data-stu-id="85b79-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="85b79-192">Descarregue e instale a [Ferramenta de Recuperação de Dispositivos Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) no seu computador.</span><span class="sxs-lookup"><span data-stu-id="85b79-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="85b79-193">Ligação o HoloLens (1º gênero) ao seu computador utilizando o cabo Micro USB que veio com o seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="85b79-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="85b79-194">Abra a ferramenta de recuperação do dispositivo Windows e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="85b79-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="85b79-195">Se a HoloLens (1ª gen) não for detetada automaticamente, selecione **O meu dispositivo não foi detetado**.</span><span class="sxs-lookup"><span data-stu-id="85b79-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="85b79-196">Em seguida, siga as instruções para colocar o aparelho no modo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="85b79-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="85b79-197">Modo de piscar manual</span><span class="sxs-lookup"><span data-stu-id="85b79-197">Manual flashing mode</span></span>

<span data-ttu-id="85b79-198">Se o seu dispositivo não for detetado, siga estes passos para colocá-lo no modo intermitente:</span><span class="sxs-lookup"><span data-stu-id="85b79-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="85b79-199">Desligue o aparelho de qualquer fonte de energia.</span><span class="sxs-lookup"><span data-stu-id="85b79-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="85b79-200">Se o dispositivo estiver ligado, mantenha premida o botão **de alimentação** até que se desligue completamente.</span><span class="sxs-lookup"><span data-stu-id="85b79-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="85b79-201">Segure o botão **de volume para cima** e toque brevemente no botão de **alimentação.**</span><span class="sxs-lookup"><span data-stu-id="85b79-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="85b79-202">O aparelho deve iniciar e exibir apenas o LED médio.</span><span class="sxs-lookup"><span data-stu-id="85b79-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="85b79-203">Ligue o dispositivo ao seu PC.</span><span class="sxs-lookup"><span data-stu-id="85b79-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="85b79-204">Abra a ferramenta de recuperação do dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="85b79-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="85b79-205">Selecione **O meu dispositivo não foi detetado** e, em seguida, **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="85b79-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="85b79-206">Siga as instruções para recuperar o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="85b79-206">Follow the instructions to recover your device.</span></span>
