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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428330"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>Usando beta do espectador 3D em HoloLens (1ª geração)

A Beta do Espectador 3D permite-lhe ver os modelos 3D no HoloLens (1ª geração). Pode abrir e visualizar ficheiros .fbx *suportados* a partir de Microsoft Edge, OneDrive e outras aplicações.

>[!NOTE]
>Este artigo aplica-se à imersiva aplicação **Unity 3D Viewer Beta,** que suporta ficheiros .fbx e só está disponível em HoloLens (1ª geração). A aplicação **3D Viewer** pré-instalada no HoloLens 2 suporta a abertura de modelos 3D personalizados na casa de realidade mista (ver [visão geral dos requisitos do Ativo](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) para mais detalhes.

>[!IMPORTANT]
>Embora a Beta do Espectador 3D possa permanecer disponível no Microsoft Store para HoloLens (1ª gen), já não está em desenvolvimento ativo e já não está suportada.

Se tiver dificuldade em abrir um modelo 3D em Beta do Espectador 3D, ou certas funcionalidades do seu modelo 3D não forem [suportadas,](#supported-content-specifications) consulte as especificações de conteúdo suportado abaixo.

Para construir ou otimizar modelos 3D para uso com Beta do Espectador 3D, consulte [otimizar os modelos 3D para Beta do Espectador 3D](#optimizing-3d-models-for-3d-viewer-beta) abaixo.

Há duas formas de abrir um modelo 3D na HoloLens. Consulte [os ficheiros FBX de visualização no HoloLens](#viewing-fbx-files-on-hololens) abaixo para saber mais.

Se tiver problemas depois de ler estes tópicos, consulte [a resolução de problemas abaixo.](#troubleshooting)

## <a name="supported-content-specifications"></a>Especificações de conteúdo suportado

### <a name="file-format"></a>Formato do ficheiro

- Formato FBX
- Libertação máxima de FBX 2015.1.0

### <a name="file-size"></a>Tamanho dos ficheiros

- Mínimo de 5 KB
- Máximo 500 MB

### <a name="geometry"></a>Geometria

- Só modelos poligonais. Sem superfícies de subdivisão ou NURBs
- Sistema de coordenadas destro
- A tesoura na transformação das matrizes não é suportada

### <a name="textures"></a>Texturas

- Os mapas de textura devem ser incorporados no ficheiro FBX
- Formatos de imagem suportados
  - Imagens JPEG e PNG
  - Imagens BMP (24 bits RGB de cor verdadeira)
  - Imagens TGA (RGB de 24 bits e 32-bit RGBQ de cor verdadeira)
- Resolução máxima de textura de 2048x2048
- Máximo de um mapa difuso, um mapa normal e um mapa de cubo de reflexão por malha
- Canal alfa em texturas difusas faz com que os pixéis sejam descartados se abaixo de 50%

### <a name="animation"></a>Animação

- Animação de escala/rotação/tradução em objetos individuais
- Animação esquelética (manipulada) com esfolar
  - Máximo de 4 influências por vértice

### <a name="materials"></a>Materiais

- Os materiais Lambert e Phong são suportados, com parâmetros ajustáveis
- Propriedades de material suportado para Lambert
  - Textura principal (RGB + Teste Alfa)
  - Cor difusa (RGB)
  - Cor ambiente (RGB)
- Propriedades de material suportado para Phong
  - Textura principal (RGB + Teste Alfa)
  - Cor difusa (RGB)
  - Cor ambiente (RGB)
  - Cor Specular (RGB)
  - Shininess
  - Refletividade
- Os materiais personalizados não são suportados
- Máximo de um material por malha
- Máximo de uma camada de material
- Máximo de 8 materiais por ficheiro

### <a name="file-and-model-limitations"></a>Limitações de arquivos e modelos

Existem limites rígidos no tamanho dos ficheiros, bem como no número de modelos, vértices e malhas que podem ser abertos simultaneamente em Beta do Espectador 3D:

- 500 MB tamanho máximo de ficheiro por modelo
- Vértices: 600.000 combinados em todos os modelos abertos
- Malhas: 1.600 combinados em todos os modelos abertos
- Máximo de 40 modelos abertos de uma vez

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>Otimização de modelos 3D para Beta do Espectador 3D

### <a name="special-considerations"></a>Considerações especiais

- Evite materiais pretos ou áreas pretas em mapas de textura. Hologramas são feitas de luz, HoloLens torna o preto (a ausência de luz) transparente.
- Antes de exportar para FBX a partir da sua ferramenta de criação, certifique-se de que toda a geometria é visível e desbloqueada e que nenhuma camada que contenha geometria seja desligada ou modelo. A visibilidade não é respeitada.
- Evite compensações de tradução muito grandes entre nós (por exemplo, 100.000 unidades). Isto pode fazer com que o modelo se aquelida enquanto é movido/escalado/rodado.

### <a name="performance-optimization"></a>Otimização do desempenho

Tenha em mente o desempenho enquanto autoriza os conteúdos e valide na aplicação Beta do Espectador 3D em HoloLens durante o processo de autoria para obter os melhores resultados. O 3D Viewer Beta torna o conteúdo em tempo real e o desempenho está sujeito a HoloLens capacidades de hardware.  

Existem muitas variáveis num modelo 3D que podem impactar o desempenho. O 3D Viewer Beta mostrará um aviso sobre a carga se houver mais de 150.000 vértices ou mais de 400 malhas. As animações podem ter impacto no desempenho de outros modelos abertos. Existem também limites rígidos nos modelos totais de números, vértices e malhas que podem ser abertos simultaneamente em Beta do Espectador 3D (ver [limitações de ficheiros e modelos).](#file-and-model-limitations)  

Se o modelo 3D não estiver a funcionar bem devido à complexidade do modelo, considere:

- Redução da contagem de polígono
- Redução do número de ossos em animação manipulada
- Evitando a auto-oclusão

A renderização de dupla face é suportada em Beta do Espectador 3D, embora seja desligada por padrão por razões de desempenho. Isto pode ser ligado através do botão **Double Sided** na página **Detalhes.** Para um melhor desempenho, evite a necessidade de renderização dupla no seu conteúdo.

### <a name="validating-your-3d-model"></a>Validando o seu modelo 3D

Valide o seu modelo abrindo-o em Beta 3D Viewer no HoloLens. Selecione o botão **Detalhes** para visualizar as características do seu modelo e avisos de conteúdo não suportado (se estiver presente).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Renderização de modelos 3D com dimensões verdadeiras à vida

Por predefinição, o 3D Viewer Beta exibe modelos 3D com um tamanho e posição confortáveis em relação ao utilizador. No entanto, se a prestação de um modelo 3D com medições verdadeiras à vida for importante (por exemplo, ao avaliar os modelos de mobiliário numa sala), o criador de conteúdo pode colocar uma bandeira nos metadados do ficheiro para evitar o redimensionamento desse modelo tanto pela aplicação como pelo utilizador.

Para evitar o escalonamento do modelo, adicione um atributo personalizado Boolean a qualquer objeto da cena chamado Microsoft_DisableScale e desajei-o como verdadeiro. A Beta do Espectador 3D respeitará então as informações da FbxSystemUnit incorporadas no ficheiro FBX. A escala em Beta do Espectador 3D é de 1 metro por unidade FBX.

## <a name="viewing-fbx-files-on-hololens"></a>Visualização de ficheiros FBX em HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Abra um ficheiro FBX a partir de Microsoft Edge

Os ficheiros FBX podem ser abertos diretamente a partir de um website utilizando Microsoft Edge em HoloLens.

1. Em Microsoft Edge, navegue para a página web que contém o ficheiro FBX que pretende visualizar.
1. Selecione o ficheiro para o descarregar.
1. Quando o download estiver concluído, selecione o botão **'Abrir'** em Microsoft Edge para abrir o ficheiro em Beta do Espectador 3D.

O ficheiro descarregado pode ser acedido e aberto novamente mais tarde, utilizando Downloads em Microsoft Edge. Para guardar um modelo 3D e garantir o acesso continuado, descarregue o ficheiro no seu PC e guarde-o para a sua conta OneDrive. O ficheiro pode então ser aberto a partir da aplicação OneDrive no HoloLens.

> [!NOTE]
> Alguns sites com modelos FBX transferíveis fornecem-nos em formato ZIP comprimido. A Beta do Espectador 3D não pode abrir ficheiros ZIP diretamente. Em vez disso, utilize o seu PC para extrair o ficheiro FBX e guarde-o na sua conta OneDrive. O ficheiro pode então ser aberto a partir da aplicação OneDrive no HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Abra um ficheiro FBX a partir de OneDrive

Os ficheiros FBX podem ser abertos a partir de OneDrive utilizando a aplicação OneDrive no HoloLens. Certifique-se de que instalou OneDrive usando Microsoft Store aplicação no HoloLens e que já carregou o ficheiro FBX para OneDrive no seu PC.

Uma vez em OneDrive, os ficheiros FBX podem ser abertos no HoloLens utilizando a Beta do Espectador 3D de uma de duas maneiras:

- Lançar OneDrive no HoloLens e selecione o ficheiro FBX para o abrir em Beta do Espectador 3D.
- Lançar Beta do Espectador 3D, toque de ar para mostrar a barra de ferramentas e selecione **Open File**. OneDrive será lançado, permitindo-lhe selecionar um ficheiro FBX.

## <a name="troubleshooting"></a>Resolução de problemas

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>Vejo um aviso quando abro um modelo 3D

Verá um aviso se tentar abrir um modelo 3D que contenha funcionalidades que não sejam suportadas por Beta do Espectador 3D, ou se o modelo for demasiado complexo e o desempenho possa ser afetado. O 3D Viewer Beta ainda carregará o modelo 3D, mas o desempenho ou a fidelidade visual podem ser comprometidos.

Para obter mais informações, consulte [as especificações de conteúdo suportados](#supported-content-specifications) e [otimizando os modelos 3D para beta do espectador 3D.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Vejo um aviso e o modelo 3D não carrega

Verá uma mensagem de erro quando a Beta do Observador 3D não pode carregar um modelo 3D devido à complexidade ou ao tamanho do ficheiro, ou se o ficheiro FBX for corrupto ou inválido. Também verá uma mensagem de erro se tiver atingido o limite do número total de modelos, vértices ou malhas que podem ser abertas simultaneamente.  

Para obter mais informações, consulte [as especificações de conteúdo suportado e as](#supported-content-specifications) [limitações do arquivo e do modelo.](#file-and-model-limitations)

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>O meu modelo 3D carrega, mas não aparece como esperado

Se o seu modelo 3D não parecer como esperado na Beta do Visualizador 3D, toque de ar para mostrar a barra de ferramentas e, em seguida, selecione **Detalhes**. Os aspetos do ficheiro que não são suportados pela Beta do Espectador 3D serão destacados como avisos.

A questão mais comum que pode ver é a falta de texturas, provavelmente porque não estão incorporadas no ficheiro FBX. Neste caso, o modelo aparecerá branco. Este problema pode ser abordado no processo de criação exportando da sua ferramenta de criação para FBX com a opção de texturas incorporadas selecionada.

Para obter mais informações, consulte [as especificações de conteúdo suportados](#supported-content-specifications) e [otimizando os modelos 3D para beta do espectador 3D.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Eu experimento quedas de desempenho ao ver o meu modelo 3D

O desempenho ao carregar e visualizar um modelo 3D pode ser afetado pela complexidade do modelo, número de modelos abertos simultaneamente ou número de modelos com animações ativas.

Para obter mais informações, consulte [a Otimização de modelos 3D para beta](#optimizing-3d-models-for-3d-viewer-beta) e ficheiro 3D do espectador e [limitações de modelos.](#file-and-model-limitations)

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Quando abro um ficheiro FBX no HoloLens, não abre em Beta do Espectador 3D

A Beta do Espectador 3D está automaticamente associada à extensão de ficheiro .fbx quando esta é instalada.

Se tentar abrir um ficheiro FBX e ver uma caixa de diálogo que o direcione para Microsoft Store, não tem atualmente uma aplicação associada à extensão de ficheiro .fbx no HoloLens.

Verifique se a Beta do Visualizador 3D está instalada. Se não estiver instalado, descarregue-o a partir de Microsoft Store no HoloLens.

Se o 3D Viewer Beta já estiver instalado, lance o 3D Viewer Beta e tente abrir novamente o ficheiro. Se o problema persistir, desinstale e reinstale a Beta do Visualizador 3D. Isto irá reassutar a extensão de ficheiro .fbx com beta do espectador 3D.

Se tentar abrir um ficheiro FBX abre uma aplicação que não seja a Beta do Espectador 3D, essa aplicação foi provavelmente instalada após a Beta do Espectador 3D e assumiu a associação com a extensão do ficheiro .fbx. Se preferir que o 3D Viewer Beta esteja associado à extensão do ficheiro .fbx, desinstale e reinstale a Beta do Observador 3D.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>O botão Open File em Beta do Espectador 3D não lança uma aplicação

O botão **Ficheiro Aberto** abrirá a aplicação associada à função de selecionador de ficheiros no HoloLens. Se OneDrive estiver instalado, o botão **Ficheiro Aberto** deverá OneDrive. No entanto, se não existir atualmente nenhuma aplicação associada à função de selecionador de ficheiros instalada no HoloLens, será direcionado para Microsoft Store.

Se o botão **Open File** lançar uma aplicação que não OneDrive, essa aplicação foi provavelmente instalada após OneDrive e assumiu a associação com a função de selecionador de ficheiros. Se preferir OneDrive lançar ao selecionar o botão **Ficheiro Aberto** em Beta do Visualizador 3D, desinstale e reinstale OneDrive.

Se o botão **'Ficheiro Aberto'** não estiver ativo, é possível que tenha atingido o limite de modelos que podem ser abertos em Beta do Espectador 3D de uma só vez. Se tiver 40 modelos abertos em Beta 3D Viewer, terá de fechar alguns antes de conseguir abrir modelos adicionais.

## <a name="additional-resources"></a>Recursos adicionais

- [Fóruns de apoio](http://forums.hololens.com/categories/3d-viewer-beta) - Apenas para fins de arquivo. Este fórum já não está ativo.
- [Avisos de terceiros](https://www.microsoft.com/{lang-locale}/legal/products)
