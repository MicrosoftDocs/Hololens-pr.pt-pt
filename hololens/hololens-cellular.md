---
title: Ligação para Celular e 5G
description: Conectar-se a redes celulares a partir do seu HoloLens dispositivos de realidade mista.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635845"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="a2568-103">Ligação para Celular e 5G</span><span class="sxs-lookup"><span data-stu-id="a2568-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="a2568-104">HoloLens 2 suporta dois métodos de ligação às redes celulares e 5G:</span><span class="sxs-lookup"><span data-stu-id="a2568-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="a2568-105">Uma rede WiFi ad hoc fornecida pelo dispositivo celular, vulgarmente referida como um "Hotspot"</span><span class="sxs-lookup"><span data-stu-id="a2568-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="a2568-106">Suporte limitado para dispositivos com tethers USB-C</span><span class="sxs-lookup"><span data-stu-id="a2568-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="a2568-107">Hotspot (WiFi)</span><span class="sxs-lookup"><span data-stu-id="a2568-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="a2568-108">A maioria das necessidades de conectividade celular pode ser satisfeita com um hotspot.</span><span class="sxs-lookup"><span data-stu-id="a2568-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="a2568-109">HoloLens 2 Wi-Fi suporta 802.11ac, que pode fornecer os requisitos de largura de banda e latência necessários para a maioria dos casos de uso comum.</span><span class="sxs-lookup"><span data-stu-id="a2568-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="a2568-110">O Wi-Fi também é livre de cabos e oferece compatibilidade com o maior número de dispositivos celulares.</span><span class="sxs-lookup"><span data-stu-id="a2568-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="a2568-111">Ligação a um hotspot</span><span class="sxs-lookup"><span data-stu-id="a2568-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="a2568-112">Consulte o manual do seu dispositivo sobre como ativar o modo hotspot.</span><span class="sxs-lookup"><span data-stu-id="a2568-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="a2568-113">Ativar o modo hotspot, fornecendo um nome para a rede, bem como uma palavra-passe conhecida.</span><span class="sxs-lookup"><span data-stu-id="a2568-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="a2568-114">Nas definições HoloLens 2 de Rede, localiza a rede WiFi criada no passo 2 e junta-te a ela.</span><span class="sxs-lookup"><span data-stu-id="a2568-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="a2568-115">USB-C Tethering</span><span class="sxs-lookup"><span data-stu-id="a2568-115">USB-C Tethering</span></span>

<span data-ttu-id="a2568-116">A tethering USB-C pode fornecer uma latência mais baixa para cargas de trabalho avançadas que precisam dela.</span><span class="sxs-lookup"><span data-stu-id="a2568-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="a2568-117">[A renderização remota Azure,](https://azure.microsoft.com/services/remote-rendering)por exemplo, pode beneficiar da amarra.</span><span class="sxs-lookup"><span data-stu-id="a2568-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="a2568-118">Note que a amarração requer um cabo entre o dispositivo celular e HoloLens, e a amarração é suportada por um número limitado de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a2568-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="a2568-119">Compatibilidade USB-C</span><span class="sxs-lookup"><span data-stu-id="a2568-119">USB-C compatibility</span></span>

<span data-ttu-id="a2568-120">Um número limitado de dispositivos que se apresentam como um adaptador ethernet pode ser usado com Windows versão Holográfica 2004 e posterior.</span><span class="sxs-lookup"><span data-stu-id="a2568-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="a2568-121">Os dispositivos que não se apresentam como adaptador ethernet devem suportar o controlador genérico do Microsoft [RNDIS.](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-)</span><span class="sxs-lookup"><span data-stu-id="a2568-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="a2568-122">Mas, apenas um número limitado desses dispositivos são compatíveis com HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a2568-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="a2568-123">Consulte o fabricante do seu dispositivo para obter mais informações sobre se suporta o controlador genérico do Microsoft RNDIS.</span><span class="sxs-lookup"><span data-stu-id="a2568-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="a2568-124">Os dispositivos que não são compatíveis com o RNDIS, ou que exigem a instalação de um controlador ou aplicação.</span><span class="sxs-lookup"><span data-stu-id="a2568-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="a2568-125">Embora a Microsoft não mantenha uma lista de dispositivos compatíveis, há uma discussão comunitária sobre o tema [aqui.](https://aka.ms/HLCommunityCell)</span><span class="sxs-lookup"><span data-stu-id="a2568-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="a2568-126">Ligação a um dispositivo amarrado</span><span class="sxs-lookup"><span data-stu-id="a2568-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="a2568-127">Consulte o manual do seu dispositivo sobre como permitir a partilha de dados em USB.</span><span class="sxs-lookup"><span data-stu-id="a2568-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="a2568-128">Esta definição é frequentemente referida como "USB Tethering", "Data Sharing" ou "USB Modem".</span><span class="sxs-lookup"><span data-stu-id="a2568-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="a2568-129">Ativar a partilha de dados em USB.</span><span class="sxs-lookup"><span data-stu-id="a2568-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="a2568-130">Ligação o seu dispositivo para a porta USB-C HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2568-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="a2568-131">Nas definições de HoloLens 2 rede, o dispositivo aparecerá automaticamente como uma ligação Ethernet.</span><span class="sxs-lookup"><span data-stu-id="a2568-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
