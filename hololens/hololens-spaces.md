---
title: Mapear espaços físicos com HoloLens
description: HoloLens aprende como é um espaço ao longo do tempo. Os utilizadores podem facilitar este processo movendo os HoloLens de determinada forma através do espaço.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, design, mapeamento espacial, HoloLens, reconstrução de superfície, malha, rastreio de cabeça, mapeamento
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379899"
---
# <a name="map-physical-spaces-with-hololens"></a><span data-ttu-id="29e58-105">Mapear espaços físicos com HoloLens</span><span class="sxs-lookup"><span data-stu-id="29e58-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="29e58-106">HoloLens mistura hologramas com o seu mundo físico.</span><span class="sxs-lookup"><span data-stu-id="29e58-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="29e58-107">Para isso, os HoloLens têm de aprender sobre o mundo físico que te rodeia e lembrar-te onde colocas hologramas dentro desse espaço.</span><span class="sxs-lookup"><span data-stu-id="29e58-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="29e58-108">Com o tempo, os HoloLens constroem um *mapa espacial* do ambiente que tem visto.</span><span class="sxs-lookup"><span data-stu-id="29e58-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="29e58-109">HoloLens atualiza o mapa à medida que o ambiente muda.</span><span class="sxs-lookup"><span data-stu-id="29e58-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="29e58-110">Desde que esteja iniciado e o dispositivo esteja ligado, o HoloLens cria e atualiza os seus mapas espaciais.</span><span class="sxs-lookup"><span data-stu-id="29e58-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="29e58-111">Se segurar ou usar o dispositivo com as câmaras apontadas para um espaço, os HoloLens tentam mapear a área.</span><span class="sxs-lookup"><span data-stu-id="29e58-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="29e58-112">Enquanto os HoloLens aprendem um espaço naturalmente ao longo do tempo, existem maneiras de ajudar hololens a mapear o seu espaço de forma mais rápida e eficiente.</span><span class="sxs-lookup"><span data-stu-id="29e58-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="29e58-113">Se os hololens não conseguirem mapear o seu espaço ou estiverem fora de calibração, os HoloLens podem entrar no modo Limited.</span><span class="sxs-lookup"><span data-stu-id="29e58-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="29e58-114">No modo Limited, não poderá colocar hologramas ao seu redor.</span><span class="sxs-lookup"><span data-stu-id="29e58-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="29e58-115">Este artigo explica como holoLens mapeia espaços, como melhorar o mapeamento espacial, e como gerir os dados espaciais que holoLens recolhe.</span><span class="sxs-lookup"><span data-stu-id="29e58-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <a name="choosing-and-setting-up-and-your-space"></a><span data-ttu-id="29e58-116">Escolher e configurar e o seu espaço</span><span class="sxs-lookup"><span data-stu-id="29e58-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="29e58-117">As características do seu ambiente podem dificultar a interpretação de um espaço pelos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="29e58-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="29e58-118">Níveis de luz, materiais no espaço, a disposição dos objetos, e muito mais podem afetar a forma como holoLens mapeiam uma área.</span><span class="sxs-lookup"><span data-stu-id="29e58-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="29e58-119">HoloLens funciona melhor em certos tipos de ambientes.</span><span class="sxs-lookup"><span data-stu-id="29e58-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="29e58-120">Para produzir o melhor mapa espacial, escolha um quarto com luz adequada e muito espaço.</span><span class="sxs-lookup"><span data-stu-id="29e58-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="29e58-121">Evite espaços e quartos escuros que tenham muitas superfícies escuras, brilhantes ou translúcidas (por exemplo, espelhos ou cortinas gauzy).</span><span class="sxs-lookup"><span data-stu-id="29e58-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="29e58-122">HoloLens está otimizado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="29e58-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="29e58-123">O mapeamento espacial também funciona melhor quando Wi-Fi é ligado, embora não tenha que ser conectado a uma rede.</span><span class="sxs-lookup"><span data-stu-id="29e58-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="29e58-124">Os HoloLens podem obter Wi-Fi pontos de acesso mesmo que não esteja ligado ou autenticado.</span><span class="sxs-lookup"><span data-stu-id="29e58-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="29e58-125">A funcionalidade HoloLens não altera se os pontos de acesso estão ligados à Internet ou apenas intranet/local.</span><span class="sxs-lookup"><span data-stu-id="29e58-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="29e58-126">Utilize hololens apenas em lugares seguros sem perigo de tropeçar.</span><span class="sxs-lookup"><span data-stu-id="29e58-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="29e58-127">[Mais em matéria de segurança.](https://support.microsoft.com/help/4023454/safety-information)</span><span class="sxs-lookup"><span data-stu-id="29e58-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <a name="mapping-your-space"></a><span data-ttu-id="29e58-128">Mapear o seu espaço</span><span class="sxs-lookup"><span data-stu-id="29e58-128">Mapping your space</span></span>

<span data-ttu-id="29e58-129">Agora está pronto para começar a mapear o seu sobressalente.</span><span class="sxs-lookup"><span data-stu-id="29e58-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="29e58-130">Quando holoLens começar a mapear o seu ambiente, você verá um gráfico de malha espalhando-se pelo espaço.</span><span class="sxs-lookup"><span data-stu-id="29e58-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="29e58-131">Em casa de realidade mista, você pode desencadear o mapa para mostrar selecionando em uma superfície mapeada.</span><span class="sxs-lookup"><span data-stu-id="29e58-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="29e58-132">Aqui estão as diretrizes para a construção de um grande mapa espacial.</span><span class="sxs-lookup"><span data-stu-id="29e58-132">Here are guidelines for building a great spatial map.</span></span>

### <a name="understand-the-scenarios-for-the-area"></a><span data-ttu-id="29e58-133">Compreender os cenários para a área</span><span class="sxs-lookup"><span data-stu-id="29e58-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="29e58-134">É importante passar o maior tempo onde você vai usar os HoloLens, para que o mapa seja relevante e completo.</span><span class="sxs-lookup"><span data-stu-id="29e58-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="29e58-135">Por exemplo, se um cenário de utilizador para HoloLens envolver mover-se do ponto A para o ponto B, caminhe nesse caminho duas a três vezes, olhando em todas as direções à medida que se move.</span><span class="sxs-lookup"><span data-stu-id="29e58-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <a name="walk-slowly-around-the-space"></a><span data-ttu-id="29e58-136">Caminhe lentamente pelo espaço</span><span class="sxs-lookup"><span data-stu-id="29e58-136">Walk slowly around the space</span></span>

<span data-ttu-id="29e58-137">Se andar muito rápido pela área, é provável que os HoloLens percam as áreas de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="29e58-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="29e58-138">Caminhe lentamente pelo espaço, parando a cada 1,5 m para olhar ao redor.</span><span class="sxs-lookup"><span data-stu-id="29e58-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="29e58-139">Movimentos suaves também ajudam os HoloLens a mapear de forma mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="29e58-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <a name="look-in-all-directions"></a><span data-ttu-id="29e58-140">Olhe em todas as direções</span><span class="sxs-lookup"><span data-stu-id="29e58-140">Look in all directions</span></span>

<span data-ttu-id="29e58-141">Olhando ao redor à medida que mapeia o espaço dá aos HoloLens mais dados sobre onde os pontos são relativos uns aos outros.</span><span class="sxs-lookup"><span data-stu-id="29e58-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="29e58-142">Se não olhar para cima, por exemplo, os HoloLens podem não saber onde fica o teto de uma sala.</span><span class="sxs-lookup"><span data-stu-id="29e58-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="29e58-143">Não se esqueça de olhar para o chão enquanto mapeia o espaço.</span><span class="sxs-lookup"><span data-stu-id="29e58-143">Don't forget to look down at the floor as you map the space.</span></span>

### <a name="cover-key-areas-multiple-times"></a><span data-ttu-id="29e58-144">Cobrir áreas-chave várias vezes</span><span class="sxs-lookup"><span data-stu-id="29e58-144">Cover key areas multiple times</span></span>

<span data-ttu-id="29e58-145">Mover-se através de uma área várias vezes ajudará a captar funcionalidades que pode ter perdido na primeira passagem.</span><span class="sxs-lookup"><span data-stu-id="29e58-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="29e58-146">Para construir um mapa ideal, tente atravessar uma área duas a três vezes.</span><span class="sxs-lookup"><span data-stu-id="29e58-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="29e58-147">Se possível, enquanto repete estes movimentos, passe o tempo a caminhar por uma área numa direção, depois vire-se e caminhe por onde veio.</span><span class="sxs-lookup"><span data-stu-id="29e58-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <a name="take-your-time-mapping-the-area"></a><span data-ttu-id="29e58-148">Leve o seu tempo a mapear a área</span><span class="sxs-lookup"><span data-stu-id="29e58-148">Take your time mapping the area</span></span>

<span data-ttu-id="29e58-149">Pode levar entre 15 e 20 minutos para os HoloLens mapearem e ajustarem-se ao seu meio envolvente.</span><span class="sxs-lookup"><span data-stu-id="29e58-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="29e58-150">Se você tem um espaço no qual você planeja usar um HoloLens frequentemente, tomar esse tempo na frente para mapear o espaço pode prevenir problemas mais tarde.</span><span class="sxs-lookup"><span data-stu-id="29e58-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <a name="possible-errors-in-the-spatial-map"></a><span data-ttu-id="29e58-151">Possíveis erros no mapa espacial</span><span class="sxs-lookup"><span data-stu-id="29e58-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="29e58-152">Os erros nos dados de mapeamento espacial enquadram-se em algumas categorias:</span><span class="sxs-lookup"><span data-stu-id="29e58-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="29e58-153">*Buracos*: Faltam superfícies do mundo real dos dados de mapeamento espacial.</span><span class="sxs-lookup"><span data-stu-id="29e58-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="29e58-154">*Alucinações*: Existem superfícies nos dados de mapeamento espacial que não existem no mundo real.</span><span class="sxs-lookup"><span data-stu-id="29e58-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="29e58-155">*Buracos de minhoca*: HoloLens 'perde' parte do mapa espacial pensando que está numa parte diferente do mapa do que realmente é.</span><span class="sxs-lookup"><span data-stu-id="29e58-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="29e58-156">*Viés*: As superfícies dos dados de mapeamento espacial estão imperfeitamente alinhadas com superfícies do mundo real, empurradas para dentro ou retiradas.</span><span class="sxs-lookup"><span data-stu-id="29e58-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="29e58-157">Se vir algum destes erros, utilize o [FeedbackHub](hololens-feedback.md) para enviar feedback.</span><span class="sxs-lookup"><span data-stu-id="29e58-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <a name="security-and-storage-for-spatial-data"></a><span data-ttu-id="29e58-158">Segurança e armazenamento para dados espaciais</span><span class="sxs-lookup"><span data-stu-id="29e58-158">Security and storage for spatial data</span></span>

<span data-ttu-id="29e58-159">Atualização da versão 1803 do Windows 10 para o Microsoft HoloLens e posteriormente armazena dados de mapeamento numa base de dados local (on-device).</span><span class="sxs-lookup"><span data-stu-id="29e58-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="29e58-160">Os utilizadores do HoloLens não podem aceder diretamente à base de dados do mapa, mesmo quando o dispositivo está ligado a um PC ou quando utiliza a aplicação Do Explorador de Ficheiros.</span><span class="sxs-lookup"><span data-stu-id="29e58-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="29e58-161">Quando o BitLocker está ativado nos HoloLens, os dados do mapa armazenados também são encriptados juntamente com todo o volume.</span><span class="sxs-lookup"><span data-stu-id="29e58-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <a name="remove-map-data-and-known-spaces-from-hololens"></a><span data-ttu-id="29e58-162">Remova os dados do mapa e espaços conhecidos dos HoloLens</span><span class="sxs-lookup"><span data-stu-id="29e58-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="29e58-163">Existem duas opções para eliminar **dados de mapas em Configurações > System > Hologramas**:</span><span class="sxs-lookup"><span data-stu-id="29e58-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="29e58-164">Para eliminar hologramas próximos, **selecione Remova os hologramas próximos.**</span><span class="sxs-lookup"><span data-stu-id="29e58-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="29e58-165">Este comando limpa os dados do mapa e os hologramas ancorados para o espaço atual.</span><span class="sxs-lookup"><span data-stu-id="29e58-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="29e58-166">Se continuar a utilizar o dispositivo no mesmo espaço, cria e armazena uma nova secção de mapas para substituir as informações eliminadas.</span><span class="sxs-lookup"><span data-stu-id="29e58-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="29e58-167">Hologramas "próximos" são hologramas que estão ancorados dentro da mesma secção de mapas no espaço atual.</span><span class="sxs-lookup"><span data-stu-id="29e58-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="29e58-168">Por exemplo, pode usar esta opção para limpar dados de mapas relacionados com o trabalho sem afetar quaisquer dados do mapa relacionado com a casa.</span><span class="sxs-lookup"><span data-stu-id="29e58-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="29e58-169">Para eliminar todos os hologramas, **selecione Remover todos os hologramas**.</span><span class="sxs-lookup"><span data-stu-id="29e58-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="29e58-170">Este comando limpa todos os dados do mapa que são armazenados no dispositivo, bem como todos os hologramas ancorados.</span><span class="sxs-lookup"><span data-stu-id="29e58-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="29e58-171">Terá de colocar explicitamente quaisquer hologramas.</span><span class="sxs-lookup"><span data-stu-id="29e58-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="29e58-172">Não será capaz de redescobrir os hologramas anteriormente colocados.</span><span class="sxs-lookup"><span data-stu-id="29e58-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="29e58-173">Depois de remover nas proximidades ou todos os hologramas, holoLens começa imediatamente a digitalizar e mapear o espaço atual.</span><span class="sxs-lookup"><span data-stu-id="29e58-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <a name="wi-fi-data-in-spatial-maps"></a><span data-ttu-id="29e58-174">Wi-Fi dados em mapas espaciais</span><span class="sxs-lookup"><span data-stu-id="29e58-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="29e58-175">HoloLens armazena características Wi-Fi para ajudar a correlacionar localizações de hologramas e secções de mapa que são armazenadas dentro da base de dados HoloLens de espaços conhecidos.</span><span class="sxs-lookup"><span data-stu-id="29e58-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="29e58-176">As informações sobre Wi-Fi características não são acessíveis aos utilizadores, e não são enviadas para a Microsoft usando a nuvem ou usando telemetria.</span><span class="sxs-lookup"><span data-stu-id="29e58-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="29e58-177">Enquanto Wi-Fi estiver ativado, holoLens correlaciona dados do mapa com pontos de acesso Wi-Fi próximos.</span><span class="sxs-lookup"><span data-stu-id="29e58-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="29e58-178">Não há diferença de comportamento se uma rede está conectada ou apenas detetada nas proximidades.</span><span class="sxs-lookup"><span data-stu-id="29e58-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="29e58-179">Se Wi-Fi estiver desativado, holoLens ainda procura no espaço.</span><span class="sxs-lookup"><span data-stu-id="29e58-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="29e58-180">No entanto, holoLens tem que pesquisar mais dos dados do mapa dentro da base de dados dos espaços, e pode precisar de mais tempo para encontrar hologramas.</span><span class="sxs-lookup"><span data-stu-id="29e58-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="29e58-181">Sem a Wi-Fi informação, os HoloLens têm de comparar as análises ativas a todas as âncoras de hologramas e secções de mapa que são armazenadas no dispositivo de forma a localizar a parte correta do mapa.</span><span class="sxs-lookup"><span data-stu-id="29e58-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <a name="related-topics"></a><span data-ttu-id="29e58-182">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="29e58-182">Related topics</span></span>

- [<span data-ttu-id="29e58-183">Design de mapeamento espacial</span><span class="sxs-lookup"><span data-stu-id="29e58-183">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
