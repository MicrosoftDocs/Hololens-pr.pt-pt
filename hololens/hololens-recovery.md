---
title: Reiniciar, reiniciar ou recuperar HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Como usar o Advanced Recovery Companion para mostrar uma imagem a HoloLens 2.
keywords: como, reiniciar, reiniciar, recuperar, reset duro, reset suave, ciclo de potência, HoloLens, desligado, arco, companheiro de recuperação avançado
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 0124453ef9e3b21722acaf2c6b438ebdfbd65043
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635947"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="08341-104">Reiniciar, reiniciar ou recuperar HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="08341-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="08341-105">Antes de iniciar qualquer procedimento de resolução de problemas, certifique-se de que o seu dispositivo está carregado até **20 a 40%** da capacidade da bateria, se possível.</span><span class="sxs-lookup"><span data-stu-id="08341-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="08341-106">As [luzes indicadoras](hololens2-setup.md#lights-that-indicate-the-battery-level) da bateria localizadas sob o botão de alimentação são uma forma rápida de verificar a capacidade da bateria sem iniciar sessão no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="08341-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="08341-107">Utilize o [carregador e o cabo USB Type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) que veio com o HoloLens 2, pois esta é a melhor maneira de carregar o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="08341-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="08341-108">O carregador fornece 18W de potência (9V a 2A).</span><span class="sxs-lookup"><span data-stu-id="08341-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="08341-109">Utilizando o carregador de parede fornecido, HoloLens 2 dispositivos podem carregar a bateria até à totalidade em menos de 65 minutos quando o dispositivo estiver em modo de espera.</span><span class="sxs-lookup"><span data-stu-id="08341-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="08341-110">Se esses acessórios não estiverem disponíveis, certifique-se de que o carregador disponível pode suportar pelo menos 15W de energia.</span><span class="sxs-lookup"><span data-stu-id="08341-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="08341-111">Se possível, evite utilizar um PC para carregar o dispositivo em USB, o que é lento.</span><span class="sxs-lookup"><span data-stu-id="08341-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="08341-112">Se o dispositivo estiver corretamente iniciado e em funcionamento, existem três formas de verificar o nível de carga da bateria:</span><span class="sxs-lookup"><span data-stu-id="08341-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="08341-113">A partir do menu principal do dispositivo HoloLens UI.</span><span class="sxs-lookup"><span data-stu-id="08341-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="08341-114">Ver o LED perto do botão de alimentação (para uma carga de 40%, deverá ver pelo menos dois LED sólidos).</span><span class="sxs-lookup"><span data-stu-id="08341-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="08341-115">Quando o aparelho está a carregar, o indicador da bateria acende-se para indicar o nível de carga atual.</span><span class="sxs-lookup"><span data-stu-id="08341-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="08341-116">A última luz desvanece-se para dentro e para fora para indicar o carregamento ativo.</span><span class="sxs-lookup"><span data-stu-id="08341-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="08341-117">Quando o seu HoloLens estiver ligado, o indicador da bateria mostra o nível da bateria em cinco incrementos.</span><span class="sxs-lookup"><span data-stu-id="08341-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="08341-118">Quando apenas uma das cinco luzes está acesa, o nível da bateria está abaixo dos 20%.</span><span class="sxs-lookup"><span data-stu-id="08341-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="08341-119">Se o nível da bateria estiver criticamente baixo e tentar ligar o dispositivo, uma luz piscará brevemente e apagar-se-á.</span><span class="sxs-lookup"><span data-stu-id="08341-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="08341-120">No seu PC anfitrião, abra o **File Explorer** e procure o seu dispositivo HoloLens 2 no lado esquerdo sob **este PC**.</span><span class="sxs-lookup"><span data-stu-id="08341-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="08341-121">Clique com o botão direito no dispositivo e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="08341-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="08341-122">Uma caixa de diálogo mostrará o nível de carga da bateria.</span><span class="sxs-lookup"><span data-stu-id="08341-122">A dialog box will show the battery charge level.</span></span>

   ![Um ecrã de HoloLens de 2 propriedades mostra o nível de mudança de bateria](images/ResetRecovery2.png)

<span data-ttu-id="08341-124">Se o dispositivo não conseguir arrancar no menu de arranque, note a aparência LED e a enumeração do dispositivo no PC anfitrião.</span><span class="sxs-lookup"><span data-stu-id="08341-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="08341-125">Em seguida, siga o [guia de resolução de problemas](hololens-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="08341-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="08341-126">Se o estado do dispositivo não corresponder a nenhum dos estados listados no guia de resolução de problemas, execute o [procedimento de reset duro](hololens-recovery.md#hard-reset-procedure) com o dispositivo ligado à alimentação elétrica e não com o seu PC anfitrião.</span><span class="sxs-lookup"><span data-stu-id="08341-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="08341-127">Espere pelo menos uma hora para o dispositivo carregar.</span><span class="sxs-lookup"><span data-stu-id="08341-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="08341-128">Reiniciar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="08341-128">Reset the device</span></span>

<span data-ttu-id="08341-129">Em determinadas circunstâncias, poderá ter de reiniciar manualmente o dispositivo sem utilizar o UI do software.</span><span class="sxs-lookup"><span data-stu-id="08341-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="08341-130">Procedimento padrão</span><span class="sxs-lookup"><span data-stu-id="08341-130">Standard procedure</span></span>

1. <span data-ttu-id="08341-131">Desligue o cabo Type-C para desligar o dispositivo da alimentação ou do PC de hospedeiro.</span><span class="sxs-lookup"><span data-stu-id="08341-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="08341-132">Pressione e segure o botão **de alimentação** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="08341-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="08341-133">Todos os LEDs devem estar desligados.</span><span class="sxs-lookup"><span data-stu-id="08341-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="08341-134">Aguarde 2-3 segundos e, em seguida, pressione o botão **de alimentação.**</span><span class="sxs-lookup"><span data-stu-id="08341-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="08341-135">Os LEDs perto do botão de alimentação acendem-se e o dispositivo começará a arrancar.</span><span class="sxs-lookup"><span data-stu-id="08341-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="08341-136">Ligação o dispositivo para o PC anfitrião e, em seguida, abra o Gestor de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="08341-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="08341-137">(Para Windows 10, prima a **tecla Windows** e, em seguida, a tecla **X** e, em seguida, selecione o Gestor **de Dispositivos**.) Certifique-se de que o dispositivo enumera corretamente como *Microsoft HoloLens* como mostrado na seguinte imagem:</span><span class="sxs-lookup"><span data-stu-id="08341-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery gestor devive](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="08341-139">Procedimento de reset difícil</span><span class="sxs-lookup"><span data-stu-id="08341-139">Hard-reset procedure</span></span>

<span data-ttu-id="08341-140">Se o procedimento de reset padrão não funcionar, utilize o procedimento de reset rígido:</span><span class="sxs-lookup"><span data-stu-id="08341-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="08341-141">Desligue o cabo Type-C para desligar o dispositivo da alimentação ou do PC de hospedeiro.</span><span class="sxs-lookup"><span data-stu-id="08341-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="08341-142">Mantenha **premidos** os  +  botões **de potência** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="08341-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="08341-143">O aparelho reiniciará automaticamente.</span><span class="sxs-lookup"><span data-stu-id="08341-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="08341-144">Ligação o dispositivo para o PC anfitrião.</span><span class="sxs-lookup"><span data-stu-id="08341-144">Connect the device to the host PC.</span></span>


5. <span data-ttu-id="08341-145">Abra o Gestor de Dispositivos (para Windows 10 prima a **tecla Windows** e, em seguida, a tecla **X** e, em seguida, selecione **o Gestor de Dispositivos).**</span><span class="sxs-lookup"><span data-stu-id="08341-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="08341-146">Certifique-se de que o dispositivo enumera corretamente como *Microsoft HoloLens* como mostrado na seguinte imagem:</span><span class="sxs-lookup"><span data-stu-id="08341-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 Dispositivo MicrosoftHoloLensRecovery maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="08341-148">Limpar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="08341-148">Clean-reflash the device</span></span>

<span data-ttu-id="08341-149">Em situações extraordinárias, pode ter de "limpar" o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="08341-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="08341-150">Por favor, note que não se espera que o reflash limpo afete os seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="08341-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="08341-151">Uniforme de cor do ecrã</span><span class="sxs-lookup"><span data-stu-id="08341-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="08341-152">Arranque com som mas sem saída de exibição</span><span class="sxs-lookup"><span data-stu-id="08341-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="08341-153">Padrão de 1-3-5-LED</span><span class="sxs-lookup"><span data-stu-id="08341-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="08341-154">Sobreaquecimento</span><span class="sxs-lookup"><span data-stu-id="08341-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="08341-155">Acidentes de SO (que são distintos de falhas de aplicação)</span><span class="sxs-lookup"><span data-stu-id="08341-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="08341-156">Há duas maneiras de reflash o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="08341-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="08341-157">Para ambos, deve primeiro [instalar o Advanced Recovery Companion a partir da Loja Windows.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="08341-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="08341-158">Se voltar a colocar o seu dispositivo, todos os seus dados pessoais, aplicações e configurações serão apagados, incluindo informações de reset TPM.</span><span class="sxs-lookup"><span data-stu-id="08341-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="08341-159">Por predefinição, Advanced Recovery Companion está programado para descarregar a mais recente construção de lançamento de funcionalidades, consulte aqui para ler as [nossas notas de Lançamento](hololens-release-notes.md#) para saber mais sobre a versão mais recente da funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="08341-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="08341-160">Para obter o mais recente pacote HoloLens 2 Full Flash Update (FFU) para relançar o seu dispositivo através do Advanced Recovery Companion, [clique aqui para descarregar a mais recente imagem mensal HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="08341-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="08341-161">Esta versão é a mais recente construção geralmente disponível.</span><span class="sxs-lookup"><span data-stu-id="08341-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="08341-162">Antes de iniciar o procedimento de reflash, certifique-se de que a aplicação está instalada e a funcionar no seu PC Windows 10 e pronta para detetar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="08341-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="08341-163">Certifique-se também de que o seu HoloLens é cobrado até um mínimo de 40%.</span><span class="sxs-lookup"><span data-stu-id="08341-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 imagens de tela de reflash limpa](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="08341-165">Procedimento normal</span><span class="sxs-lookup"><span data-stu-id="08341-165">Normal procedure</span></span>

1. <span data-ttu-id="08341-166">Enquanto o HoloLens dispositivo estiver em execução, conecte-o ao PC Windows 10 onde abriu previamente a aplicação Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="08341-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="08341-167">O dispositivo será detetado automaticamente e a UI da aplicação Advanced Recovery Companion iniciará o processo de atualização:</span><span class="sxs-lookup"><span data-stu-id="08341-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens ecrã inicial de reflash limpo de 2](images/ARC2.png)

3. <span data-ttu-id="08341-169">Selecione o dispositivo HoloLens 2 na UI da aplicação Advanced Recovery Companion e siga as instruções para completar o reflash.</span><span class="sxs-lookup"><span data-stu-id="08341-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="08341-170">Procedimento manual</span><span class="sxs-lookup"><span data-stu-id="08341-170">Manual procedure</span></span>

<span data-ttu-id="08341-171">Se o HoloLens 2 não arrancar corretamente ou se o Avançado Recovery Companion não conseguir detetar o dispositivo, poderá ter de colocar o dispositivo no modo de recuperação:</span><span class="sxs-lookup"><span data-stu-id="08341-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="08341-172">Desligue o cabo Type-C para desligar o dispositivo da alimentação ou do PC de hospedeiro.</span><span class="sxs-lookup"><span data-stu-id="08341-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="08341-173">Pressione e segure o botão **de alimentação** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="08341-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="08341-174">Todos os LEDs devem desligar.</span><span class="sxs-lookup"><span data-stu-id="08341-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="08341-175">Enquanto pressiona o botão **de volume para cima,** prima e liberte o botão **de alimentação** para ligar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="08341-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="08341-176">Aguarde 15 segundos e, em seguida, liberte o botão **de volume para cima.**</span><span class="sxs-lookup"><span data-stu-id="08341-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="08341-177">Apenas o LED médio dos cinco LEDs acende-se.</span><span class="sxs-lookup"><span data-stu-id="08341-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="08341-178">Ligação o dispositivo para o PC anfitrião e abra o Gestor de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="08341-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="08341-179">(Para Windows 10 prima a **tecla Windows** e, em seguida, a tecla **X** e, em seguida, selecione **O Gestor de Dispositivos**.) Certifique-se de que o dispositivo enumera corretamente Microsoft HoloLens como mostrado na seguinte imagem:</span><span class="sxs-lookup"><span data-stu-id="08341-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="08341-181">O dispositivo será detetado automaticamente e a UI da aplicação Advanced Recovery Companion iniciará o processo de atualização:</span><span class="sxs-lookup"><span data-stu-id="08341-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens ecrã de reflash limpo de 2](images/ARC2.png)

6. <span data-ttu-id="08341-183">Selecione o dispositivo HoloLens 2 na UI da aplicação Advanced Recovery Companion e, em seguida, siga as instruções para completar o reflash.</span><span class="sxs-lookup"><span data-stu-id="08341-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="08341-184">Troubleshoot Advanced Recovery Companion</span><span class="sxs-lookup"><span data-stu-id="08341-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="08341-185">Certifique-se de que o seu dispositivo está carregado até 40% ou mais antes de tentar piscar.</span><span class="sxs-lookup"><span data-stu-id="08341-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="08341-186">Verifique se o seu dispositivo está desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="08341-186">Check your device is unlocked.</span></span>

1. <span data-ttu-id="08341-187">Verifique se o seu dispositivo está ligado diretamente ao PC anfitrião, não a um hub.</span><span class="sxs-lookup"><span data-stu-id="08341-187">Check your device is plugged directly into the host PC, not a hub.</span></span>

1. <span data-ttu-id="08341-188">Se o seu dispositivo não estiver a aparecer como um dispositivo de recuperação HoloLens/HoloLens sob a Universal Serial Bus Drivers, verifique:</span><span class="sxs-lookup"><span data-stu-id="08341-188">If your device is not showing as a HoloLens/HoloLens Recovery device under Universal Serial Bus Drivers, check:</span></span>
    1. <span data-ttu-id="08341-189">**Portas**, como um dispositivo Qualcomm HS-USB</span><span class="sxs-lookup"><span data-stu-id="08341-189">**Ports**, as a Qualcomm HS-USB device</span></span>
    1.   <span data-ttu-id="08341-190">**Outros Dispositivos**, como QUSB_BULK dispositivo – o seu PC anfitrião está a perder os controladores necessários para detetar o seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="08341-190">**Other Devices**, as a QUSB_BULK device - your host PC is missing the necessary drivers to detect your HoloLens.</span></span> <span data-ttu-id="08341-191">Clique e selecione Update Driver e procure por condutores on-line ou [verifique atualizações opcionais nas definições de Atualização Windows](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674).</span><span class="sxs-lookup"><span data-stu-id="08341-191">Right click and select Update Driver and search for drivers online or [check Optional Updates in your Windows Update settings](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674).</span></span> <span data-ttu-id="08341-192">Depois de o controlador ser descarregado, a ARC deverá ser capaz de detetá-lo.</span><span class="sxs-lookup"><span data-stu-id="08341-192">After the driver is downloaded, ARC should be able to detect it.</span></span>
 
1. <span data-ttu-id="08341-193">Se o ARC não detetar o seu dispositivo, certifique-se de que pode ligar-se ao seu dispositivo através do File Explorer no seu PC.</span><span class="sxs-lookup"><span data-stu-id="08341-193">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="08341-194">Se não puder;</span><span class="sxs-lookup"><span data-stu-id="08341-194">If you cannot;</span></span>

    1.  <span data-ttu-id="08341-195">É possível que o seu dispositivo possa ter políticas USB que desativem essa ligação.</span><span class="sxs-lookup"><span data-stu-id="08341-195">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="08341-196">Em caso afirmativo, experimente [o modo de piscar manual](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="08341-196">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="08341-197">Se não houver políticas, experimente um cabo USB diferente.</span><span class="sxs-lookup"><span data-stu-id="08341-197">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="08341-198">Verifique se o seu dispositivo não apresenta um [padrão de 1-3-5 LED](hololens2-setup.md#lights-to-indicate-problems).</span><span class="sxs-lookup"><span data-stu-id="08341-198">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="08341-199">Descarregue o ARC sem utilizar a loja de aplicações</span><span class="sxs-lookup"><span data-stu-id="08341-199">Download ARC without using the app store</span></span>

<span data-ttu-id="08341-200">Se o ambiente de TI impedir a utilização da app Windows Store ou limitar o acesso à loja de retalho, o administrador de TI pode disponibilizar esta aplicação através de uma via de implementação "offline".</span><span class="sxs-lookup"><span data-stu-id="08341-200">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="08341-201">Os administradores de TI também podem distribuir esta aplicação através de System Center Configuration Manager (SCCM) ou Intune.</span><span class="sxs-lookup"><span data-stu-id="08341-201">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="08341-202">Este guia foca-se no Advanced Recovery Companion, mas o processo também pode ser usado para outras aplicações "offline".</span><span class="sxs-lookup"><span data-stu-id="08341-202">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="08341-203">Siga estes passos para permitir a via de implantação:</span><span class="sxs-lookup"><span data-stu-id="08341-203">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="08341-204">Vá ao [Microsoft Store para Empresas](https://businessstore.microsoft.com) e inscreva-se usando uma identidade Azure Ative Directory.</span><span class="sxs-lookup"><span data-stu-id="08341-204">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="08341-205">Ir para **Gerir – Definições.**</span><span class="sxs-lookup"><span data-stu-id="08341-205">Go to **Manage – Settings**.</span></span> <span data-ttu-id="08341-206">Ligue **as aplicações offline do Show** sob **experiência de Compras.**</span><span class="sxs-lookup"><span data-stu-id="08341-206">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="08341-207">Vá às **compras para o meu grupo** e procure o Avançado Recovery [**_Companion._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="08341-207">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="08341-208">Altere o **Tipo de Licença** para \**_offline_*_, e selecione _\* Gerir\*\*.</span><span class="sxs-lookup"><span data-stu-id="08341-208">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="08341-209">Em **Descarregue o pacote para uso offline,** selecione o segundo botão azul **Descarregar.**</span><span class="sxs-lookup"><span data-stu-id="08341-209">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="08341-210">Certifique-se de que a extensão do ficheiro é *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="08341-210">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="08341-211">Nesta fase, se o Pc desktop tiver acesso à Internet, clique duas vezes no pacote para instalar a aplicação.</span><span class="sxs-lookup"><span data-stu-id="08341-211">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="08341-212">Se o destino PC não tiver conectividade com a Internet, siga estes passos:</span><span class="sxs-lookup"><span data-stu-id="08341-212">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="08341-213">Selecione a licença não codificada e, em seguida, **selecione Gerar licença**.</span><span class="sxs-lookup"><span data-stu-id="08341-213">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="08341-214">Nos **quadros necessários**, selecione **Download**.</span><span class="sxs-lookup"><span data-stu-id="08341-214">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="08341-215">Utilize o DISM para aplicar a embalagem com a dependência e a licença.</span><span class="sxs-lookup"><span data-stu-id="08341-215">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="08341-216">A partir de um pedido de comando do administrador, executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="08341-216">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="08341-217">O número da versão neste exemplo de código pode não corresponder à versão atualmente disponível.</span><span class="sxs-lookup"><span data-stu-id="08341-217">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="08341-218">Você também pode ter escolhido um local de descarregamento diferente do que no exemplo.</span><span class="sxs-lookup"><span data-stu-id="08341-218">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="08341-219">Faça quaisquer alterações ao comando conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="08341-219">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="08341-220">Quando planeia utilizar o Advanced Recovery Companion para instalar um FFU offline, pode ser útil descarregar a sua imagem flash.</span><span class="sxs-lookup"><span data-stu-id="08341-220">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="08341-221">[**Descarregue a imagem atual para HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="08341-221">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="08341-222">Outros recursos:</span><span class="sxs-lookup"><span data-stu-id="08341-222">Other resources:</span></span>
- [<span data-ttu-id="08341-223">Distribuir aplicativos offline</span><span class="sxs-lookup"><span data-stu-id="08341-223">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="08341-224">Pacote de aplicativos DISM (.appx ou .appxbundle) opções de linha de comando</span><span class="sxs-lookup"><span data-stu-id="08341-224">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
