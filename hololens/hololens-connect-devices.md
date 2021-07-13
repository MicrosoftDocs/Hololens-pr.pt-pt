---
title: Ligação para dispositivos Bluetooth e USB-C
description: Começa a ligar-te a dispositivos e acessórios Bluetooth e USB-C dos seus HoloLens dispositivos de realidade mista.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639102"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="de25c-103">Ligação para dispositivos Bluetooth e USB-C</span><span class="sxs-lookup"><span data-stu-id="de25c-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="de25c-104">Emparelhar dispositivos Bluetooth</span><span class="sxs-lookup"><span data-stu-id="de25c-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="de25c-105">HoloLens 2 suporta as seguintes classes de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="de25c-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="de25c-106">[HID:](/windows-hardware/drivers/hid/)</span><span class="sxs-lookup"><span data-stu-id="de25c-106">[HID](/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="de25c-107">Rato</span><span class="sxs-lookup"><span data-stu-id="de25c-107">Mouse</span></span>
    - <span data-ttu-id="de25c-108">Teclado</span><span class="sxs-lookup"><span data-stu-id="de25c-108">Keyboard</span></span>
- <span data-ttu-id="de25c-109">Dispositivos de saída de áudio (A2DP)</span><span class="sxs-lookup"><span data-stu-id="de25c-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="de25c-110">HoloLens 2 suporta as seguintes APIs Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="de25c-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="de25c-111">[Servidor](/windows/uwp/devices-sensors/gatt-server) e [Cliente](/windows/uwp/devices-sensors/gatt-client) do GATT</span><span class="sxs-lookup"><span data-stu-id="de25c-111">GATT [Server](/windows/uwp/devices-sensors/gatt-server) and [Client](/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="de25c-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="de25c-112">RFCOMM</span></span>](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="de25c-113">Poderá ter de instalar aplicações de acompanhantes correspondentes a partir de Microsoft Store para utilizar os dispositivos HID e GATT.</span><span class="sxs-lookup"><span data-stu-id="de25c-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="de25c-114">HoloLens (1ª geração) suporta as seguintes classes de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="de25c-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="de25c-115">Rato</span><span class="sxs-lookup"><span data-stu-id="de25c-115">Mouse</span></span>
- <span data-ttu-id="de25c-116">Teclado</span><span class="sxs-lookup"><span data-stu-id="de25c-116">Keyboard</span></span>
- [<span data-ttu-id="de25c-117">clicker HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="de25c-117">HoloLens (1st gen) clicker</span></span>](hololens1-clicker.md)

> [!NOTE]
> <span data-ttu-id="de25c-118">Outros tipos de dispositivos Bluetooth, como altifalantes, auscultadores, smartphones e almofadas de jogo, podem estar listados como disponíveis em HoloLens configurações.</span><span class="sxs-lookup"><span data-stu-id="de25c-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="de25c-119">No entanto, estes dispositivos não são suportados em HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="de25c-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="de25c-120">Para mais informações, consulte [HoloLens Definições lista os dispositivos disponíveis, mas os dispositivos não funcionam](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span><span class="sxs-lookup"><span data-stu-id="de25c-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="de25c-121">Emparelhar um teclado ou rato Bluetooth</span><span class="sxs-lookup"><span data-stu-id="de25c-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="de25c-122">Ligue o teclado ou o rato e torne-o detetável.</span><span class="sxs-lookup"><span data-stu-id="de25c-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="de25c-123">Para aprender a tornar o dispositivo detetável, procure informações sobre o dispositivo (ou a sua documentação) ou visite o site do fabricante.</span><span class="sxs-lookup"><span data-stu-id="de25c-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="de25c-124">Utilize o gesto de floração (HoloLens (1º gen)) ou o gesto de partida (HoloLens 2) para ir para **Iniciar**, e, em seguida, selecione **Definições**.</span><span class="sxs-lookup"><span data-stu-id="de25c-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="de25c-125">Selecione **Dispositivos** e certifique-se de que Bluetooth está ligado.</span><span class="sxs-lookup"><span data-stu-id="de25c-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="de25c-126">Quando vir o nome do dispositivo, selecione **Emparelhar** e, em seguida, siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="de25c-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="de25c-127">Desativar Bluetooth</span><span class="sxs-lookup"><span data-stu-id="de25c-127">Disable Bluetooth</span></span>

<span data-ttu-id="de25c-128">Este procedimento desliga os componentes RF do rádio Bluetooth e desativa todas as funcionalidades Bluetooth no Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="de25c-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="de25c-129">Utilize o gesto de floração (HoloLens (1º gen)) ou o gesto de partida (HoloLens 2) para ir para **iniciar**, e, em seguida, selecione   >  **Definições Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="de25c-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="de25c-130">Desloque o interruptor de deslize para **Bluetooth** para a posição **desligada.**</span><span class="sxs-lookup"><span data-stu-id="de25c-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="de25c-131">HoloLens 2: Ligação dispositivos USB-C</span><span class="sxs-lookup"><span data-stu-id="de25c-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="de25c-132">HoloLens 2 suporta as seguintes classes de dispositivos USB-C:</span><span class="sxs-lookup"><span data-stu-id="de25c-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="de25c-133">Dispositivos de armazenamento em massa (como pendrives)</span><span class="sxs-lookup"><span data-stu-id="de25c-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="de25c-134">Adaptadores Ethernet (incluindo ethernet mais carregamento)</span><span class="sxs-lookup"><span data-stu-id="de25c-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="de25c-135">Adaptadores de áudio digitais USB-C-a-3.5mm</span><span class="sxs-lookup"><span data-stu-id="de25c-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="de25c-136">Auscultadores de áudio digitais USB-C (incluindo adaptadores de auscultadores mais carregamento)</span><span class="sxs-lookup"><span data-stu-id="de25c-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="de25c-137">Microfones Externos USB-C[(Windows Holográfico, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e superior)</span><span class="sxs-lookup"><span data-stu-id="de25c-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="de25c-138">Rato com fios</span><span class="sxs-lookup"><span data-stu-id="de25c-138">Wired mouse</span></span>
- <span data-ttu-id="de25c-139">Teclado com fios</span><span class="sxs-lookup"><span data-stu-id="de25c-139">Wired keyboard</span></span>
- <span data-ttu-id="de25c-140">Conjunto de cubos de PD (carregamento USB A mais PD)</span><span class="sxs-lookup"><span data-stu-id="de25c-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="de25c-141">Em resposta ao feedback do cliente, permitimos um suporte limitado para a conectividade celular diretamente ao HoloLens via USB-C.</span><span class="sxs-lookup"><span data-stu-id="de25c-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="de25c-142">Consulte [Ligação celular e 5G](hololens-cellular.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="de25c-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="de25c-143">Suporte externo do microfone USB-C</span><span class="sxs-lookup"><span data-stu-id="de25c-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de25c-144">A ligação **de um microfone USB não o definirá automaticamente como o dispositivo de entrada**.</span><span class="sxs-lookup"><span data-stu-id="de25c-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="de25c-145">Ao ligar um conjunto de auscultadores USB-C, os utilizadores observarão que o áudio do auscultador será automaticamente redirecionado para os auscultadores, mas o HoloLens OS prioriza a matriz interna do microfone acima de qualquer outro dispositivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="de25c-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="de25c-146">**Para utilizar um microfone USB-C, siga os passos abaixo.**</span><span class="sxs-lookup"><span data-stu-id="de25c-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="de25c-147">Os microfones externos não podem ser utilizados em construções antes [de Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e superior.</span><span class="sxs-lookup"><span data-stu-id="de25c-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="de25c-148">Os utilizadores podem selecionar microfones externos ligados a USB-C utilizando o painel de definições **de som.**</span><span class="sxs-lookup"><span data-stu-id="de25c-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="de25c-149">Os microfones USB-C podem ser utilizados para chamadas, gravações, etc.</span><span class="sxs-lookup"><span data-stu-id="de25c-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="de25c-150">Abra a aplicação **Definições** e selecione **System**  >  **Sound**.</span><span class="sxs-lookup"><span data-stu-id="de25c-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Som Definições](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="de25c-152">Para utilizar microfones externos com **Assistência Remota,** os utilizadores terão de clicar na hiperligação "Gerir dispositivos de som".</span><span class="sxs-lookup"><span data-stu-id="de25c-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="de25c-153">Em seguida, utilize o drop-down para definir o microfone externo como **Predefinido** ou **Padrão de Comunicações.**</span><span class="sxs-lookup"><span data-stu-id="de25c-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="de25c-154">Escolher **o Predefinido** significa que o microfone externo será utilizado em todo o lado.</span><span class="sxs-lookup"><span data-stu-id="de25c-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="de25c-155">Escolher o **Padrão de Comunicações** significa que o microfone externo será utilizado em aplicações de Assistência Remota e outras aplicações de comunicações, mas o HoloLens conjunto de microfones ainda pode ser usado para outras tarefas.</span><span class="sxs-lookup"><span data-stu-id="de25c-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Gerir dispositivos de som](images/usbc-mic-2.png)

<br>

![Definir padrão do microfone](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="de25c-158">E Bluetooth suporte ao microfone?</span><span class="sxs-lookup"><span data-stu-id="de25c-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="de25c-159">Infelizmente, Bluetooth microfones ainda não estão suportados no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="de25c-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="de25c-160">USB-C Hubs</span><span class="sxs-lookup"><span data-stu-id="de25c-160">USB-C Hubs</span></span>

<span data-ttu-id="de25c-161">Alguns utilizadores podem precisar de ligar vários dispositivos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="de25c-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="de25c-162">Para os utilizadores que gostariam de utilizar um [microfone USB-C](#usb-c-external-microphone-support) juntamente com outro dispositivo conectado, os hubs USB-C podem corresponder às necessidades do cliente.</span><span class="sxs-lookup"><span data-stu-id="de25c-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="de25c-163">A Microsoft não testou estes dispositivos, nem podemos recomendar marcas específicas.</span><span class="sxs-lookup"><span data-stu-id="de25c-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="de25c-164">**Requisitos para o hub USB-C e dispositivos conectados:**</span><span class="sxs-lookup"><span data-stu-id="de25c-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="de25c-165">Os dispositivos ligados não devem exigir a instalação de um controlador.</span><span class="sxs-lookup"><span data-stu-id="de25c-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="de25c-166">A potência total de todos os dispositivos ligados deve ser inferior a 4,5 Watts.</span><span class="sxs-lookup"><span data-stu-id="de25c-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="de25c-167">Ligação para Miracast</span><span class="sxs-lookup"><span data-stu-id="de25c-167">Connect to Miracast</span></span>

<span data-ttu-id="de25c-168">Para utilizar Miracast, siga estes passos:</span><span class="sxs-lookup"><span data-stu-id="de25c-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="de25c-169">Faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="de25c-169">Do one of the following:</span></span>  

   - <span data-ttu-id="de25c-170">Abra o menu **Iniciar** e selecione o ícone **'Mostrar'.**</span><span class="sxs-lookup"><span data-stu-id="de25c-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="de25c-171">Diga "Ligação" enquanto olha para o menu **Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="de25c-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="de25c-172">Na lista de dispositivos que aparecem, selecione um dispositivo disponível.</span><span class="sxs-lookup"><span data-stu-id="de25c-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="de25c-173">Complete o emparelhamento para começar a projetar.</span><span class="sxs-lookup"><span data-stu-id="de25c-173">Complete the pairing to begin projecting.</span></span>
