---
title: Bateria e carregamento
description: Como carregar os hololens e utilizar baterias externas.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379976"
---
# <a name="battery-and-charging"></a><span data-ttu-id="08662-103">Bateria e carregamento</span><span class="sxs-lookup"><span data-stu-id="08662-103">Battery and Charging</span></span>

<span data-ttu-id="08662-104">Esta página oferece detalhes sobre o carregamento de HoloLens 2 e a utilização de baterias externas.</span><span class="sxs-lookup"><span data-stu-id="08662-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="included-charger"></a><span data-ttu-id="08662-105">Carregador Incluído</span><span class="sxs-lookup"><span data-stu-id="08662-105">Included Charger</span></span>

<span data-ttu-id="08662-106">O carregador incluído com HoloLens 2 fornece até 9V @ 2A (18W).</span><span class="sxs-lookup"><span data-stu-id="08662-106">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="08662-107">Quando possível, é altamente recomendado carregar usando o carregador incluído.</span><span class="sxs-lookup"><span data-stu-id="08662-107">When possible, it's highly recommended to charge using the included charger.</span></span>  

## <a name="specifications"></a><span data-ttu-id="08662-108">Especificações</span><span class="sxs-lookup"><span data-stu-id="08662-108">Specifications</span></span>

<span data-ttu-id="08662-109">HoloLens 2 pode ser carregado por fontes [usb de entrega de energia](https://www.usb.org/usb-charger-pd) até 27 Watts.</span><span class="sxs-lookup"><span data-stu-id="08662-109">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="08662-110">Se a fonte for capaz de fornecer pelo menos 10 Watts, o tempo de funcionamento do HoloLens pode ser prolongado (potencialmente indefinidamente para algumas cargas de trabalho).</span><span class="sxs-lookup"><span data-stu-id="08662-110">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="08662-111">A utilização de um cabo de carregamento USB-A a USB-C limitará a carga a 7,5 Watts.</span><span class="sxs-lookup"><span data-stu-id="08662-111">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="08662-112">O tempo de funcionamento continuará a ser prolongado, mas não tanto quanto a utilização usb-C a C.</span><span class="sxs-lookup"><span data-stu-id="08662-112">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="08662-113">Quando o HoloLens está em modo de espera, 18 Watts é suficiente para atingir a taxa máxima de carga para a bateria interna.</span><span class="sxs-lookup"><span data-stu-id="08662-113">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="08662-114">Quando holoLens está em uso, a taxa de carga pode ser reduzida uma vez que HoloLens prioriza o funcionamento sobre o carregamento.</span><span class="sxs-lookup"><span data-stu-id="08662-114">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08662-115">Recomenda-se que hololens 2 sejam carregados a 5V/1.5A no mínimo.</span><span class="sxs-lookup"><span data-stu-id="08662-115">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="08662-116">Os carregadores que não podem fornecer pelo menos 5V/1.5A não devem ser utilizados.</span><span class="sxs-lookup"><span data-stu-id="08662-116">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

## <a name="external-battery-packs"></a><span data-ttu-id="08662-117">Baterias externas</span><span class="sxs-lookup"><span data-stu-id="08662-117">External Battery Packs</span></span>

<span data-ttu-id="08662-118">As baterias que satisfaçam as especificações acima podem ser utilizadas com HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="08662-118">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="08662-119">No entanto, note que algumas baterias USB-C recarregam e fornecem energia através da mesma porta USB-C.</span><span class="sxs-lookup"><span data-stu-id="08662-119">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="08662-120">É importante que estas baterias implementem [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) para garantir que cobram HoloLens em vez de cobrar dele.</span><span class="sxs-lookup"><span data-stu-id="08662-120">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

## <a name="managing-heat"></a><span data-ttu-id="08662-121">Gestão do Calor</span><span class="sxs-lookup"><span data-stu-id="08662-121">Managing Heat</span></span>

<span data-ttu-id="08662-122">Como em qualquer dispositivo, o carregamento holoLens gera calor.</span><span class="sxs-lookup"><span data-stu-id="08662-122">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="08662-123">Quanto mais rápida for a carga, mais calor é gerado.</span><span class="sxs-lookup"><span data-stu-id="08662-123">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="08662-124">Além disso, iniciar uma carga a um nível de bateria mais baixo gerará mais calor do que iniciar uma carga quando a bateria está maioritariamente cheia.</span><span class="sxs-lookup"><span data-stu-id="08662-124">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="08662-125">Os clientes que precisam de operar HoloLens por longos períodos de tempo em ambientes quentes podem utilizar as seguintes técnicas:</span><span class="sxs-lookup"><span data-stu-id="08662-125">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="08662-126">Não há problema em ligar o HoloLens 2 a uma fonte de energia externa, mesmo quando a bateria interna está completamente carregada.</span><span class="sxs-lookup"><span data-stu-id="08662-126">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="08662-127">Quando uma bateria externa estiver esgotada, a HoloLens continuará a operar na sua bateria interna.</span><span class="sxs-lookup"><span data-stu-id="08662-127">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="08662-128">Se o calor continuar a ser um problema depois de seguir os passos acima, considere a utilização de um carregador ou bateria que limite o carregamento a 1,5A.</span><span class="sxs-lookup"><span data-stu-id="08662-128">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="08662-129">Note que esta opção não proporcionará tanto tempo de funcionamento, uma vez que a bateria interna continuará a esgotar-se lentamente.</span><span class="sxs-lookup"><span data-stu-id="08662-129">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="08662-130">Resolução de problemas</span><span class="sxs-lookup"><span data-stu-id="08662-130">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="08662-131">HoloLens carrega bateria externa</span><span class="sxs-lookup"><span data-stu-id="08662-131">HoloLens Charges External Battery</span></span>
<span data-ttu-id="08662-132">Se o HoloLens 2 carregar uma bateria externa em vez de ser carregada por ela, isto indica que a bateria não implementa [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span><span class="sxs-lookup"><span data-stu-id="08662-132">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="08662-133">Mudar para uma bateria mais recente é a forma recomendada de resolver este problema, mas em alternativa pode tentar mudar para um cabo USB-A para USB-C.</span><span class="sxs-lookup"><span data-stu-id="08662-133">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="08662-134">Tenha em mente que isto limitará a taxa de carregamento a 7,5 watts.</span><span class="sxs-lookup"><span data-stu-id="08662-134">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
