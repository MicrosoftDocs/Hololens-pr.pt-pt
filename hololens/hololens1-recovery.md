---
title: Reiniciar, reiniciar ou recuperar HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Como utilizar a Ferramenta de Recuperação de Dispositivos do Windows para mostrar uma imagem ao HoloLens 1st Gen.
keywords: como, reiniciar, reiniciar, recuperar, reset duro, reset suave, ciclo de potência, HoloLens, desligado, wdrt, ferramenta de recuperação de dispositivos windows
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
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378556"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="1e469-104">Reiniciar, reiniciar ou recuperar HoloLens (1ª Gen)</span><span class="sxs-lookup"><span data-stu-id="1e469-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="1e469-105">Se estiver a ter problemas com os hololens, pode querer reiniciar ou reiniciar ou mesmo relançar o dispositivo utilizando a recuperação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1e469-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="1e469-106">Este artigo guia-o através dos passos de recuperação recomendados em ordem.</span><span class="sxs-lookup"><span data-stu-id="1e469-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="1e469-107">Se procura recuperar um HoloLens 2, veja [a Recuperação de um HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), uma vez que esse processo difere.</span><span class="sxs-lookup"><span data-stu-id="1e469-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="1e469-108">Este artigo centra-se no dispositivo e software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1e469-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="1e469-109">Se os seus hologramas não parecerem **[adequados, consulte considerações ambientais do HoloLens](hololens-environment-considerations.md)** para obter informações sobre fatores que melhorem a qualidade do holograma.</span><span class="sxs-lookup"><span data-stu-id="1e469-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="1e469-110">Reiniciar</span><span class="sxs-lookup"><span data-stu-id="1e469-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="1e469-111">Faça um reinício seguro usando cortana</span><span class="sxs-lookup"><span data-stu-id="1e469-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="1e469-112">A forma mais segura de reiniciar os HoloLens é usando cortana, que geralmente é a primeira coisa a tentar quando você experimenta um problema com HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1e469-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="1e469-113">Cortana não está disponível em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1e469-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="1e469-114">Cortana está disponível em todos os dispositivos HoloLens (1ª Gen).</span><span class="sxs-lookup"><span data-stu-id="1e469-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="1e469-115">Cortana está disponível em dispositivos HoloLens 2 em construções antes da atualização Do Windows Holograpic, Versão 2004.</span><span class="sxs-lookup"><span data-stu-id="1e469-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="1e469-116">Liga os HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1e469-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="1e469-117">Certifique-se de que um utilizador está a iniciar sessão e que o dispositivo não está à espera de uma palavra-passe para o desbloquear.</span><span class="sxs-lookup"><span data-stu-id="1e469-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="1e469-118">Diz "Hey Cortana, reinicie" ou "Hey Cortana, reinicie".</span><span class="sxs-lookup"><span data-stu-id="1e469-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="1e469-119">Cortana responderá e pedirá que confirme.</span><span class="sxs-lookup"><span data-stu-id="1e469-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="1e469-120">Espere um som para tocar depois da pergunta, e depois diga "Sim".</span><span class="sxs-lookup"><span data-stu-id="1e469-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="1e469-121">O dispositivo vai reiniciar.</span><span class="sxs-lookup"><span data-stu-id="1e469-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="1e469-122">Use o botão de alimentação para fazer um reinício seguro</span><span class="sxs-lookup"><span data-stu-id="1e469-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="1e469-123">Se ainda não conseguir reiniciar o seu dispositivo, tente reiniciá-lo utilizando o botão **de alimentação:**</span><span class="sxs-lookup"><span data-stu-id="1e469-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="1e469-124">Pressione e segure o botão **de alimentação** durante 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="1e469-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="1e469-125">Após 1 segundo, todos os cinco LEDs iluminar-se-ão e, em seguida, desligar-se-ão lentamente um a um da direita para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="1e469-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="1e469-126">Após 5 segundos, todos os LEDs estarão desligados, indicando uma paragem bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="1e469-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="1e469-127">Pare de premir o botão imediatamente depois de todos os LEDs terem desligado.</span><span class="sxs-lookup"><span data-stu-id="1e469-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="1e469-128">Espere 1 minuto para a paralisação estar completa.</span><span class="sxs-lookup"><span data-stu-id="1e469-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="1e469-129">A paralisação pode ainda estar em curso mesmo depois de os visores estarem desligados.</span><span class="sxs-lookup"><span data-stu-id="1e469-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="1e469-130">Volte a ligar o aparelho premindo e segurando o botão **de alimentação** durante 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="1e469-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="1e469-131">Faça um reinício seguro utilizando o Portal do Dispositivo Do Windows</span><span class="sxs-lookup"><span data-stu-id="1e469-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="1e469-132">Para este processo, o HoloLens tem de ser configurado como um dispositivo de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="1e469-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="1e469-133">Saiba mais no [Portal do Dispositivo Windows.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="1e469-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="1e469-134">Se o procedimento anterior não funcionar, tente reiniciar o dispositivo utilizando o [Portal do Dispositivo Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="1e469-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="1e469-135">No canto superior direito, encontre a opção de reiniciar ou desligar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1e469-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="1e469-136">Faça um reinício forçado inseguro</span><span class="sxs-lookup"><span data-stu-id="1e469-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="1e469-137">Se os métodos anteriores não reiniciarem os hololens, forcem um recomeço.</span><span class="sxs-lookup"><span data-stu-id="1e469-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="1e469-138">Este método equivale a remover e reinstalar a bateria.</span><span class="sxs-lookup"><span data-stu-id="1e469-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="1e469-139">É perigoso porque pode deixar o seu dispositivo num estado corrompido.</span><span class="sxs-lookup"><span data-stu-id="1e469-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="1e469-140">Se isso acontecer, terás de mostrar os teus HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1e469-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="1e469-141">Este é um método potencialmente prejudicial e só deve ser usado se os métodos anteriormente citados não funcionarem.</span><span class="sxs-lookup"><span data-stu-id="1e469-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="1e469-142">Pressione e segure o botão **de alimentação** durante pelo menos 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="1e469-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="1e469-143">Não faz mal segurar o botão por mais de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="1e469-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="1e469-144">É seguro ignorar qualquer atividade LED.</span><span class="sxs-lookup"><span data-stu-id="1e469-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="1e469-145">Solte o botão e aguarde 2-3 segundos.</span><span class="sxs-lookup"><span data-stu-id="1e469-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="1e469-146">Pressione e segure o botão **de alimentação** durante 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="1e469-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="1e469-147">Se ainda tiver problemas, prima o botão **de alimentação** durante 4 segundos, até que todos os indicadores da bateria se desvaneçam e o ecrã deixe de exibir hologramas.</span><span class="sxs-lookup"><span data-stu-id="1e469-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="1e469-148">Aguarde 1 minuto e, em seguida, prima novamente o botão **de alimentação** para ligar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1e469-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="1e469-149">Reset para as definições de fábrica</span><span class="sxs-lookup"><span data-stu-id="1e469-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="1e469-150">A bateria precisa de pelo menos uma carga de 40% para ser reposta.</span><span class="sxs-lookup"><span data-stu-id="1e469-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="1e469-151">Se os seus HoloLens ainda tão problemáticos, tente repor o estado da fábrica.</span><span class="sxs-lookup"><span data-stu-id="1e469-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="1e469-152">Este passo mantém a versão do software Holográfico do Windows que está instalado no mesmo e devolve tudo o resto às definições de fábrica.</span><span class="sxs-lookup"><span data-stu-id="1e469-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="1e469-153">Se reiniciar o seu dispositivo, todos os seus dados pessoais, aplicações e configurações serão apagados, incluindo informações de reset TPM.</span><span class="sxs-lookup"><span data-stu-id="1e469-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="1e469-154">A reposição só instalará a mais recente versão instalada do Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="1e469-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="1e469-155">Terá de refazer todos os passos de inicialização (calibrar, ligar ao Wi-Fi, criar uma conta de utilizador, descarregar apps, e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="1e469-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="1e469-156">Abra a aplicação Definições e, em seguida, selecione  >  **Update Recovery**.</span><span class="sxs-lookup"><span data-stu-id="1e469-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="1e469-157">Selecione a opção **do dispositivo Reset** e leia a mensagem de confirmação.</span><span class="sxs-lookup"><span data-stu-id="1e469-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="1e469-158">Confirme o reset.</span><span class="sxs-lookup"><span data-stu-id="1e469-158">Confirm the reset.</span></span> <span data-ttu-id="1e469-159">O aparelho reiniciará e exibirá um conjunto de engrenagens giratórias e uma barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="1e469-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="1e469-160">Espere cerca de 30 minutos para que este processo esteja concluído.</span><span class="sxs-lookup"><span data-stu-id="1e469-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="1e469-161">Quando estiver feito, o dispositivo reiniciará a experiência "fora da caixa".</span><span class="sxs-lookup"><span data-stu-id="1e469-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="1e469-162">Reinstalar o sistema operativo</span><span class="sxs-lookup"><span data-stu-id="1e469-162">Reinstall the operating system</span></span>

<span data-ttu-id="1e469-163">Se o dispositivo ainda tiver um problema após o reinício e reinicialização, pode utilizar uma ferramenta de recuperação no seu computador para reinstalar o sistema operativo HoloLens e o firmware.</span><span class="sxs-lookup"><span data-stu-id="1e469-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="1e469-164">Os dados de que o HoloLens necessita para o reset são embalados numa Atualização Flash Completa (FFU), que é semelhante a um ficheiro .iso, .wim ou .vhd.</span><span class="sxs-lookup"><span data-stu-id="1e469-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="1e469-165">Saiba mais sobre os formatos de ficheiros de imagem FFU.</span><span class="sxs-lookup"><span data-stu-id="1e469-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="1e469-166">Pode instalar um novo sistema operativo nos HoloLens (1ª geração) utilizando a Ferramenta de Recuperação de Dispositivos windows.</span><span class="sxs-lookup"><span data-stu-id="1e469-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="1e469-167">Antes de utilizar esta ferramenta, veja se reiniciar ou reiniciar os HoloLens corrige o problema.</span><span class="sxs-lookup"><span data-stu-id="1e469-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="1e469-168">O processo de recuperação pode demorar um pouco.</span><span class="sxs-lookup"><span data-stu-id="1e469-168">The recovery process may take a while.</span></span> <span data-ttu-id="1e469-169">Quando estiver feito, será instalada a versão mais recente do software Holográfico do Windows.</span><span class="sxs-lookup"><span data-stu-id="1e469-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="1e469-170">Para utilizar a ferramenta, precisa de um computador que execute o Windows 10 ou mais tarde com pelo menos 4 GB de espaço de armazenamento gratuito.</span><span class="sxs-lookup"><span data-stu-id="1e469-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="1e469-171">Não podes executar esta ferramenta numa máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="1e469-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="1e469-172">Recupere os holoLens</span><span class="sxs-lookup"><span data-stu-id="1e469-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="1e469-173">Descarregue e instale a [Ferramenta de Recuperação de Dispositivos do Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) no seu computador.</span><span class="sxs-lookup"><span data-stu-id="1e469-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="1e469-174">Ligue os HoloLens (1º gênero) ao seu computador utilizando o cabo Micro USB que veio com os seus HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1e469-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="1e469-175">Abra a Ferramenta de Recuperação do Dispositivo do Windows e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="1e469-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="1e469-176">Se os HoloLens (1º gênero) não forem detetados automaticamente, selecione **O meu dispositivo não foi detetado**.</span><span class="sxs-lookup"><span data-stu-id="1e469-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="1e469-177">Em seguida, siga as instruções para colocar o aparelho no modo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="1e469-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="1e469-178">Modo de piscar manual</span><span class="sxs-lookup"><span data-stu-id="1e469-178">Manual flashing mode</span></span>

<span data-ttu-id="1e469-179">Se o seu dispositivo não for detetado, siga estes passos para colocá-lo no modo intermitente:</span><span class="sxs-lookup"><span data-stu-id="1e469-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="1e469-180">Desligue o aparelho de qualquer fonte de energia.</span><span class="sxs-lookup"><span data-stu-id="1e469-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="1e469-181">Se o dispositivo estiver ligado, mantenha premida o botão **de alimentação** até que se desligue completamente.</span><span class="sxs-lookup"><span data-stu-id="1e469-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="1e469-182">Segure o botão **de volume para cima** e toque brevemente no botão de **alimentação.**</span><span class="sxs-lookup"><span data-stu-id="1e469-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="1e469-183">O aparelho deve iniciar e exibir apenas o LED médio.</span><span class="sxs-lookup"><span data-stu-id="1e469-183">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="1e469-184">Ligue o dispositivo ao seu PC.</span><span class="sxs-lookup"><span data-stu-id="1e469-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="1e469-185">Abra a ferramenta de recuperação do dispositivo windows.</span><span class="sxs-lookup"><span data-stu-id="1e469-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="1e469-186">Selecione **O meu dispositivo não foi detetado** e, em seguida, **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="1e469-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="1e469-187">Siga as instruções para recuperar o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1e469-187">Follow the instructions to recover your device.</span></span>
