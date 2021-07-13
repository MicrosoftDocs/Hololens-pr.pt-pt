---
title: Usando beta do espectador 3D em HoloLens (1ª geração)
description: Descreve os tipos de ficheiros e funcionalidades que a Beta do Espectador 3D suporta HoloLens (1ª gen) e como usar e resolver problemas da aplicação.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635488"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a><span data-ttu-id="f6b47-103">Usando beta do espectador 3D em HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="f6b47-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="f6b47-104">A Beta do Espectador 3D permite-lhe ver os modelos 3D no HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="f6b47-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="f6b47-105">Pode abrir e visualizar ficheiros .fbx *suportados* a partir de Microsoft Edge, OneDrive e outras aplicações.</span><span class="sxs-lookup"><span data-stu-id="f6b47-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="f6b47-106">Este artigo aplica-se à imersiva aplicação **Unity 3D Viewer Beta,** que suporta ficheiros .fbx e só está disponível em HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="f6b47-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="f6b47-107">A aplicação **3D Viewer** pré-instalada no HoloLens 2 suporta a abertura de modelos 3D personalizados na casa de realidade mista (ver [visão geral dos requisitos do Ativo](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="f6b47-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="f6b47-108">Embora a Beta do Espectador 3D possa permanecer disponível no Microsoft Store para HoloLens (1ª gen), já não está em desenvolvimento ativo e já não está suportada.</span><span class="sxs-lookup"><span data-stu-id="f6b47-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="f6b47-109">Se tiver dificuldade em abrir um modelo 3D em Beta do Espectador 3D, ou certas funcionalidades do seu modelo 3D não forem [suportadas,](#supported-content-specifications) consulte as especificações de conteúdo suportado abaixo.</span><span class="sxs-lookup"><span data-stu-id="f6b47-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="f6b47-110">Para construir ou otimizar modelos 3D para uso com Beta do Espectador 3D, consulte [otimizar os modelos 3D para Beta do Espectador 3D](#optimizing-3d-models-for-3d-viewer-beta) abaixo.</span><span class="sxs-lookup"><span data-stu-id="f6b47-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="f6b47-111">Há duas formas de abrir um modelo 3D na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f6b47-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="f6b47-112">Consulte [os ficheiros FBX de visualização no HoloLens](#viewing-fbx-files-on-hololens) abaixo para saber mais.</span><span class="sxs-lookup"><span data-stu-id="f6b47-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="f6b47-113">Se tiver problemas depois de ler estes tópicos, consulte [a resolução de problemas abaixo.](#troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="f6b47-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <a name="supported-content-specifications"></a><span data-ttu-id="f6b47-114">Especificações de conteúdo suportado</span><span class="sxs-lookup"><span data-stu-id="f6b47-114">Supported content specifications</span></span>

### <a name="file-format"></a><span data-ttu-id="f6b47-115">Formato do ficheiro</span><span class="sxs-lookup"><span data-stu-id="f6b47-115">File format</span></span>

- <span data-ttu-id="f6b47-116">Formato FBX</span><span class="sxs-lookup"><span data-stu-id="f6b47-116">FBX format</span></span>
- <span data-ttu-id="f6b47-117">Libertação máxima de FBX 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="f6b47-117">Maximum FBX release 2015.1.0</span></span>

### <a name="file-size"></a><span data-ttu-id="f6b47-118">Tamanho dos ficheiros</span><span class="sxs-lookup"><span data-stu-id="f6b47-118">File size</span></span>

- <span data-ttu-id="f6b47-119">Mínimo de 5 KB</span><span class="sxs-lookup"><span data-stu-id="f6b47-119">Minimum 5 KB</span></span>
- <span data-ttu-id="f6b47-120">Máximo 500 MB</span><span class="sxs-lookup"><span data-stu-id="f6b47-120">Maximum 500 MB</span></span>

### <a name="geometry"></a><span data-ttu-id="f6b47-121">Geometria</span><span class="sxs-lookup"><span data-stu-id="f6b47-121">Geometry</span></span>

- <span data-ttu-id="f6b47-122">Só modelos poligonais.</span><span class="sxs-lookup"><span data-stu-id="f6b47-122">Polygonal models only.</span></span> <span data-ttu-id="f6b47-123">Sem superfícies de subdivisão ou NURBs</span><span class="sxs-lookup"><span data-stu-id="f6b47-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="f6b47-124">Sistema de coordenadas destro</span><span class="sxs-lookup"><span data-stu-id="f6b47-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="f6b47-125">A tesoura na transformação das matrizes não é suportada</span><span class="sxs-lookup"><span data-stu-id="f6b47-125">Shear in transformation matrices is not supported</span></span>

### <a name="textures"></a><span data-ttu-id="f6b47-126">Texturas</span><span class="sxs-lookup"><span data-stu-id="f6b47-126">Textures</span></span>

- <span data-ttu-id="f6b47-127">Os mapas de textura devem ser incorporados no ficheiro FBX</span><span class="sxs-lookup"><span data-stu-id="f6b47-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="f6b47-128">Formatos de imagem suportados</span><span class="sxs-lookup"><span data-stu-id="f6b47-128">Supported image formats</span></span>
  - <span data-ttu-id="f6b47-129">Imagens JPEG e PNG</span><span class="sxs-lookup"><span data-stu-id="f6b47-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="f6b47-130">Imagens BMP (24 bits RGB de cor verdadeira)</span><span class="sxs-lookup"><span data-stu-id="f6b47-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="f6b47-131">Imagens TGA (RGB de 24 bits e 32-bit RGBQ de cor verdadeira)</span><span class="sxs-lookup"><span data-stu-id="f6b47-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="f6b47-132">Resolução máxima de textura de 2048x2048</span><span class="sxs-lookup"><span data-stu-id="f6b47-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="f6b47-133">Máximo de um mapa difuso, um mapa normal e um mapa de cubo de reflexão por malha</span><span class="sxs-lookup"><span data-stu-id="f6b47-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="f6b47-134">Canal alfa em texturas difusas faz com que os pixéis sejam descartados se abaixo de 50%</span><span class="sxs-lookup"><span data-stu-id="f6b47-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <a name="animation"></a><span data-ttu-id="f6b47-135">Animação</span><span class="sxs-lookup"><span data-stu-id="f6b47-135">Animation</span></span>

- <span data-ttu-id="f6b47-136">Animação de escala/rotação/tradução em objetos individuais</span><span class="sxs-lookup"><span data-stu-id="f6b47-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="f6b47-137">Animação esquelética (manipulada) com esfolar</span><span class="sxs-lookup"><span data-stu-id="f6b47-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="f6b47-138">Máximo de 4 influências por vértice</span><span class="sxs-lookup"><span data-stu-id="f6b47-138">Maximum of 4 influences per vertex</span></span>

### <a name="materials"></a><span data-ttu-id="f6b47-139">Materiais</span><span class="sxs-lookup"><span data-stu-id="f6b47-139">Materials</span></span>

- <span data-ttu-id="f6b47-140">Os materiais Lambert e Phong são suportados, com parâmetros ajustáveis</span><span class="sxs-lookup"><span data-stu-id="f6b47-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="f6b47-141">Propriedades de material suportado para Lambert</span><span class="sxs-lookup"><span data-stu-id="f6b47-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="f6b47-142">Textura principal (RGB + Teste Alfa)</span><span class="sxs-lookup"><span data-stu-id="f6b47-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="f6b47-143">Cor difusa (RGB)</span><span class="sxs-lookup"><span data-stu-id="f6b47-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="f6b47-144">Cor ambiente (RGB)</span><span class="sxs-lookup"><span data-stu-id="f6b47-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="f6b47-145">Propriedades de material suportado para Phong</span><span class="sxs-lookup"><span data-stu-id="f6b47-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="f6b47-146">Textura principal (RGB + Teste Alfa)</span><span class="sxs-lookup"><span data-stu-id="f6b47-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="f6b47-147">Cor difusa (RGB)</span><span class="sxs-lookup"><span data-stu-id="f6b47-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="f6b47-148">Cor ambiente (RGB)</span><span class="sxs-lookup"><span data-stu-id="f6b47-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="f6b47-149">Cor Specular (RGB)</span><span class="sxs-lookup"><span data-stu-id="f6b47-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="f6b47-150">Shininess</span><span class="sxs-lookup"><span data-stu-id="f6b47-150">Shininess</span></span>
  - <span data-ttu-id="f6b47-151">Refletividade</span><span class="sxs-lookup"><span data-stu-id="f6b47-151">Reflectivity</span></span>
- <span data-ttu-id="f6b47-152">Os materiais personalizados não são suportados</span><span class="sxs-lookup"><span data-stu-id="f6b47-152">Custom materials are not supported</span></span>
- <span data-ttu-id="f6b47-153">Máximo de um material por malha</span><span class="sxs-lookup"><span data-stu-id="f6b47-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="f6b47-154">Máximo de uma camada de material</span><span class="sxs-lookup"><span data-stu-id="f6b47-154">Maximum of one material layer</span></span>
- <span data-ttu-id="f6b47-155">Máximo de 8 materiais por ficheiro</span><span class="sxs-lookup"><span data-stu-id="f6b47-155">Maximum of 8 materials per file</span></span>

### <a name="file-and-model-limitations"></a><span data-ttu-id="f6b47-156">Limitações de arquivos e modelos</span><span class="sxs-lookup"><span data-stu-id="f6b47-156">File and model limitations</span></span>

<span data-ttu-id="f6b47-157">Existem limites rígidos no tamanho dos ficheiros, bem como no número de modelos, vértices e malhas que podem ser abertos simultaneamente em Beta do Espectador 3D:</span><span class="sxs-lookup"><span data-stu-id="f6b47-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="f6b47-158">500 MB tamanho máximo de ficheiro por modelo</span><span class="sxs-lookup"><span data-stu-id="f6b47-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="f6b47-159">Vértices: 600.000 combinados em todos os modelos abertos</span><span class="sxs-lookup"><span data-stu-id="f6b47-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="f6b47-160">Malhas: 1.600 combinados em todos os modelos abertos</span><span class="sxs-lookup"><span data-stu-id="f6b47-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="f6b47-161">Máximo de 40 modelos abertos de uma vez</span><span class="sxs-lookup"><span data-stu-id="f6b47-161">Maximum of 40 models open at one time</span></span>

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a><span data-ttu-id="f6b47-162">Otimização de modelos 3D para Beta do Espectador 3D</span><span class="sxs-lookup"><span data-stu-id="f6b47-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <a name="special-considerations"></a><span data-ttu-id="f6b47-163">Considerações especiais</span><span class="sxs-lookup"><span data-stu-id="f6b47-163">Special considerations</span></span>

- <span data-ttu-id="f6b47-164">Evite materiais pretos ou áreas pretas em mapas de textura.</span><span class="sxs-lookup"><span data-stu-id="f6b47-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="f6b47-165">Hologramas são feitas de luz, HoloLens torna o preto (a ausência de luz) transparente.</span><span class="sxs-lookup"><span data-stu-id="f6b47-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="f6b47-166">Antes de exportar para FBX a partir da sua ferramenta de criação, certifique-se de que toda a geometria é visível e desbloqueada e que nenhuma camada que contenha geometria seja desligada ou modelo.</span><span class="sxs-lookup"><span data-stu-id="f6b47-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="f6b47-167">A visibilidade não é respeitada.</span><span class="sxs-lookup"><span data-stu-id="f6b47-167">Visibility is not respected.</span></span>
- <span data-ttu-id="f6b47-168">Evite compensações de tradução muito grandes entre nós (por exemplo, 100.000 unidades).</span><span class="sxs-lookup"><span data-stu-id="f6b47-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="f6b47-169">Isto pode fazer com que o modelo se aquelida enquanto é movido/escalado/rodado.</span><span class="sxs-lookup"><span data-stu-id="f6b47-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <a name="performance-optimization"></a><span data-ttu-id="f6b47-170">Otimização do desempenho</span><span class="sxs-lookup"><span data-stu-id="f6b47-170">Performance optimization</span></span>

<span data-ttu-id="f6b47-171">Tenha em mente o desempenho enquanto autoriza os conteúdos e valide na aplicação Beta do Espectador 3D em HoloLens durante o processo de autoria para obter os melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="f6b47-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="f6b47-172">O 3D Viewer Beta torna o conteúdo em tempo real e o desempenho está sujeito a HoloLens capacidades de hardware.</span><span class="sxs-lookup"><span data-stu-id="f6b47-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="f6b47-173">Existem muitas variáveis num modelo 3D que podem impactar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="f6b47-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="f6b47-174">O 3D Viewer Beta mostrará um aviso sobre a carga se houver mais de 150.000 vértices ou mais de 400 malhas.</span><span class="sxs-lookup"><span data-stu-id="f6b47-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="f6b47-175">As animações podem ter impacto no desempenho de outros modelos abertos.</span><span class="sxs-lookup"><span data-stu-id="f6b47-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="f6b47-176">Existem também limites rígidos nos modelos totais de números, vértices e malhas que podem ser abertos simultaneamente em Beta do Espectador 3D (ver [limitações de ficheiros e modelos).](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="f6b47-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="f6b47-177">Se o modelo 3D não estiver a funcionar bem devido à complexidade do modelo, considere:</span><span class="sxs-lookup"><span data-stu-id="f6b47-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="f6b47-178">Redução da contagem de polígono</span><span class="sxs-lookup"><span data-stu-id="f6b47-178">Reducing polygon count</span></span>
- <span data-ttu-id="f6b47-179">Redução do número de ossos em animação manipulada</span><span class="sxs-lookup"><span data-stu-id="f6b47-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="f6b47-180">Evitando a auto-oclusão</span><span class="sxs-lookup"><span data-stu-id="f6b47-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="f6b47-181">A renderização de dupla face é suportada em Beta do Espectador 3D, embora seja desligada por padrão por razões de desempenho.</span><span class="sxs-lookup"><span data-stu-id="f6b47-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="f6b47-182">Isto pode ser ligado através do botão **Double Sided** na página **Detalhes.**</span><span class="sxs-lookup"><span data-stu-id="f6b47-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="f6b47-183">Para um melhor desempenho, evite a necessidade de renderização dupla no seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f6b47-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <a name="validating-your-3d-model"></a><span data-ttu-id="f6b47-184">Validando o seu modelo 3D</span><span class="sxs-lookup"><span data-stu-id="f6b47-184">Validating your 3D model</span></span>

<span data-ttu-id="f6b47-185">Valide o seu modelo abrindo-o em Beta 3D Viewer no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f6b47-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="f6b47-186">Selecione o botão **Detalhes** para visualizar as características do seu modelo e avisos de conteúdo não suportado (se estiver presente).</span><span class="sxs-lookup"><span data-stu-id="f6b47-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a><span data-ttu-id="f6b47-187">Renderização de modelos 3D com dimensões verdadeiras à vida</span><span class="sxs-lookup"><span data-stu-id="f6b47-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="f6b47-188">Por predefinição, o 3D Viewer Beta exibe modelos 3D com um tamanho e posição confortáveis em relação ao utilizador.</span><span class="sxs-lookup"><span data-stu-id="f6b47-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="f6b47-189">No entanto, se a prestação de um modelo 3D com medições verdadeiras à vida for importante (por exemplo, ao avaliar os modelos de mobiliário numa sala), o criador de conteúdo pode colocar uma bandeira nos metadados do ficheiro para evitar o redimensionamento desse modelo tanto pela aplicação como pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="f6b47-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="f6b47-190">Para evitar o escalonamento do modelo, adicione um atributo personalizado Boolean a qualquer objeto da cena chamado Microsoft_DisableScale e desajei-o como verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="f6b47-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="f6b47-191">A Beta do Espectador 3D respeitará então as informações da FbxSystemUnit incorporadas no ficheiro FBX.</span><span class="sxs-lookup"><span data-stu-id="f6b47-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="f6b47-192">A escala em Beta do Espectador 3D é de 1 metro por unidade FBX.</span><span class="sxs-lookup"><span data-stu-id="f6b47-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <a name="viewing-fbx-files-on-hololens"></a><span data-ttu-id="f6b47-193">Visualização de ficheiros FBX em HoloLens</span><span class="sxs-lookup"><span data-stu-id="f6b47-193">Viewing FBX files on HoloLens</span></span>

### <a name="open-an-fbx-file-from-microsoft-edge"></a><span data-ttu-id="f6b47-194">Abra um ficheiro FBX a partir de Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f6b47-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="f6b47-195">Os ficheiros FBX podem ser abertos diretamente a partir de um website utilizando Microsoft Edge em HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f6b47-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="f6b47-196">Em Microsoft Edge, navegue para a página web que contém o ficheiro FBX que pretende visualizar.</span><span class="sxs-lookup"><span data-stu-id="f6b47-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="f6b47-197">Selecione o ficheiro para o descarregar.</span><span class="sxs-lookup"><span data-stu-id="f6b47-197">Select the file to download it.</span></span>
1. <span data-ttu-id="f6b47-198">Quando o download estiver concluído, selecione o botão **'Abrir'** em Microsoft Edge para abrir o ficheiro em Beta do Espectador 3D.</span><span class="sxs-lookup"><span data-stu-id="f6b47-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="f6b47-199">O ficheiro descarregado pode ser acedido e aberto novamente mais tarde, utilizando Downloads em Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="f6b47-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="f6b47-200">Para guardar um modelo 3D e garantir o acesso continuado, descarregue o ficheiro no seu PC e guarde-o para a sua conta OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f6b47-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="f6b47-201">O ficheiro pode então ser aberto a partir da aplicação OneDrive no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f6b47-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="f6b47-202">Alguns sites com modelos FBX transferíveis fornecem-nos em formato ZIP comprimido.</span><span class="sxs-lookup"><span data-stu-id="f6b47-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="f6b47-203">A Beta do Espectador 3D não pode abrir ficheiros ZIP diretamente.</span><span class="sxs-lookup"><span data-stu-id="f6b47-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="f6b47-204">Em vez disso, utilize o seu PC para extrair o ficheiro FBX e guarde-o na sua conta OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f6b47-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="f6b47-205">O ficheiro pode então ser aberto a partir da aplicação OneDrive no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f6b47-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <a name="open-an-fbx-file-from-onedrive"></a><span data-ttu-id="f6b47-206">Abra um ficheiro FBX a partir de OneDrive</span><span class="sxs-lookup"><span data-stu-id="f6b47-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="f6b47-207">Os ficheiros FBX podem ser abertos a partir de OneDrive utilizando a aplicação OneDrive no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f6b47-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="f6b47-208">Certifique-se de que instalou OneDrive usando Microsoft Store aplicação no HoloLens e que já carregou o ficheiro FBX para OneDrive no seu PC.</span><span class="sxs-lookup"><span data-stu-id="f6b47-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="f6b47-209">Uma vez em OneDrive, os ficheiros FBX podem ser abertos no HoloLens utilizando a Beta do Espectador 3D de uma de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="f6b47-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="f6b47-210">Lançar OneDrive no HoloLens e selecione o ficheiro FBX para o abrir em Beta do Espectador 3D.</span><span class="sxs-lookup"><span data-stu-id="f6b47-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="f6b47-211">Lançar Beta do Espectador 3D, toque de ar para mostrar a barra de ferramentas e selecione **Open File**.</span><span class="sxs-lookup"><span data-stu-id="f6b47-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="f6b47-212">OneDrive será lançado, permitindo-lhe selecionar um ficheiro FBX.</span><span class="sxs-lookup"><span data-stu-id="f6b47-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f6b47-213">Resolução de problemas</span><span class="sxs-lookup"><span data-stu-id="f6b47-213">Troubleshooting</span></span>

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a><span data-ttu-id="f6b47-214">Vejo um aviso quando abro um modelo 3D</span><span class="sxs-lookup"><span data-stu-id="f6b47-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="f6b47-215">Verá um aviso se tentar abrir um modelo 3D que contenha funcionalidades que não sejam suportadas por Beta do Espectador 3D, ou se o modelo for demasiado complexo e o desempenho possa ser afetado.</span><span class="sxs-lookup"><span data-stu-id="f6b47-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="f6b47-216">O 3D Viewer Beta ainda carregará o modelo 3D, mas o desempenho ou a fidelidade visual podem ser comprometidos.</span><span class="sxs-lookup"><span data-stu-id="f6b47-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="f6b47-217">Para obter mais informações, consulte [as especificações de conteúdo suportados](#supported-content-specifications) e [otimizando os modelos 3D para beta do espectador 3D.](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="f6b47-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a><span data-ttu-id="f6b47-218">Vejo um aviso e o modelo 3D não carrega</span><span class="sxs-lookup"><span data-stu-id="f6b47-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="f6b47-219">Verá uma mensagem de erro quando a Beta do Observador 3D não pode carregar um modelo 3D devido à complexidade ou ao tamanho do ficheiro, ou se o ficheiro FBX for corrupto ou inválido.</span><span class="sxs-lookup"><span data-stu-id="f6b47-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="f6b47-220">Também verá uma mensagem de erro se tiver atingido o limite do número total de modelos, vértices ou malhas que podem ser abertas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="f6b47-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="f6b47-221">Para obter mais informações, consulte [as especificações de conteúdo suportado e as](#supported-content-specifications) [limitações do arquivo e do modelo.](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="f6b47-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a><span data-ttu-id="f6b47-222">O meu modelo 3D carrega, mas não aparece como esperado</span><span class="sxs-lookup"><span data-stu-id="f6b47-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="f6b47-223">Se o seu modelo 3D não parecer como esperado na Beta do Visualizador 3D, toque de ar para mostrar a barra de ferramentas e, em seguida, selecione **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f6b47-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="f6b47-224">Os aspetos do ficheiro que não são suportados pela Beta do Espectador 3D serão destacados como avisos.</span><span class="sxs-lookup"><span data-stu-id="f6b47-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="f6b47-225">A questão mais comum que pode ver é a falta de texturas, provavelmente porque não estão incorporadas no ficheiro FBX.</span><span class="sxs-lookup"><span data-stu-id="f6b47-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="f6b47-226">Neste caso, o modelo aparecerá branco.</span><span class="sxs-lookup"><span data-stu-id="f6b47-226">In this case, the model will appear white.</span></span> <span data-ttu-id="f6b47-227">Este problema pode ser abordado no processo de criação exportando da sua ferramenta de criação para FBX com a opção de texturas incorporadas selecionada.</span><span class="sxs-lookup"><span data-stu-id="f6b47-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="f6b47-228">Para obter mais informações, consulte [as especificações de conteúdo suportados](#supported-content-specifications) e [otimizando os modelos 3D para beta do espectador 3D.](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="f6b47-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a><span data-ttu-id="f6b47-229">Eu experimento quedas de desempenho ao ver o meu modelo 3D</span><span class="sxs-lookup"><span data-stu-id="f6b47-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="f6b47-230">O desempenho ao carregar e visualizar um modelo 3D pode ser afetado pela complexidade do modelo, número de modelos abertos simultaneamente ou número de modelos com animações ativas.</span><span class="sxs-lookup"><span data-stu-id="f6b47-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="f6b47-231">Para obter mais informações, consulte [a Otimização de modelos 3D para beta](#optimizing-3d-models-for-3d-viewer-beta) e ficheiro 3D do espectador e [limitações de modelos.](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="f6b47-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a><span data-ttu-id="f6b47-232">Quando abro um ficheiro FBX no HoloLens, não abre em Beta do Espectador 3D</span><span class="sxs-lookup"><span data-stu-id="f6b47-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="f6b47-233">A Beta do Espectador 3D está automaticamente associada à extensão de ficheiro .fbx quando esta é instalada.</span><span class="sxs-lookup"><span data-stu-id="f6b47-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="f6b47-234">Se tentar abrir um ficheiro FBX e ver uma caixa de diálogo que o direcione para Microsoft Store, não tem atualmente uma aplicação associada à extensão de ficheiro .fbx no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f6b47-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="f6b47-235">Verifique se a Beta do Visualizador 3D está instalada.</span><span class="sxs-lookup"><span data-stu-id="f6b47-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="f6b47-236">Se não estiver instalado, descarregue-o a partir de Microsoft Store no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f6b47-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="f6b47-237">Se o 3D Viewer Beta já estiver instalado, lance o 3D Viewer Beta e tente abrir novamente o ficheiro.</span><span class="sxs-lookup"><span data-stu-id="f6b47-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="f6b47-238">Se o problema persistir, desinstale e reinstale a Beta do Visualizador 3D.</span><span class="sxs-lookup"><span data-stu-id="f6b47-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="f6b47-239">Isto irá reassutar a extensão de ficheiro .fbx com beta do espectador 3D.</span><span class="sxs-lookup"><span data-stu-id="f6b47-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="f6b47-240">Se tentar abrir um ficheiro FBX abre uma aplicação que não seja a Beta do Espectador 3D, essa aplicação foi provavelmente instalada após a Beta do Espectador 3D e assumiu a associação com a extensão do ficheiro .fbx.</span><span class="sxs-lookup"><span data-stu-id="f6b47-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="f6b47-241">Se preferir que o 3D Viewer Beta esteja associado à extensão do ficheiro .fbx, desinstale e reinstale a Beta do Observador 3D.</span><span class="sxs-lookup"><span data-stu-id="f6b47-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a><span data-ttu-id="f6b47-242">O botão Open File em Beta do Espectador 3D não lança uma aplicação</span><span class="sxs-lookup"><span data-stu-id="f6b47-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="f6b47-243">O botão **Ficheiro Aberto** abrirá a aplicação associada à função de selecionador de ficheiros no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f6b47-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="f6b47-244">Se OneDrive estiver instalado, o botão **Ficheiro Aberto** deverá OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f6b47-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="f6b47-245">No entanto, se não existir atualmente nenhuma aplicação associada à função de selecionador de ficheiros instalada no HoloLens, será direcionado para Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="f6b47-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="f6b47-246">Se o botão **Open File** lançar uma aplicação que não OneDrive, essa aplicação foi provavelmente instalada após OneDrive e assumiu a associação com a função de selecionador de ficheiros.</span><span class="sxs-lookup"><span data-stu-id="f6b47-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="f6b47-247">Se preferir OneDrive lançar ao selecionar o botão **Ficheiro Aberto** em Beta do Visualizador 3D, desinstale e reinstale OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f6b47-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="f6b47-248">Se o botão **'Ficheiro Aberto'** não estiver ativo, é possível que tenha atingido o limite de modelos que podem ser abertos em Beta do Espectador 3D de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="f6b47-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="f6b47-249">Se tiver 40 modelos abertos em Beta 3D Viewer, terá de fechar alguns antes de conseguir abrir modelos adicionais.</span><span class="sxs-lookup"><span data-stu-id="f6b47-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f6b47-250">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f6b47-250">Additional resources</span></span>

- <span data-ttu-id="f6b47-251">[Fóruns de apoio](http://forums.hololens.com/categories/3d-viewer-beta) - Apenas para fins de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f6b47-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="f6b47-252">Este fórum já não está ativo.</span><span class="sxs-lookup"><span data-stu-id="f6b47-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="f6b47-253">Avisos de terceiros</span><span class="sxs-lookup"><span data-stu-id="f6b47-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
