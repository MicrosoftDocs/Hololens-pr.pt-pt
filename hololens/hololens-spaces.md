---
title: Mapear espaços físicos com HoloLens
description: HoloLens aprende como é um espaço ao longo do tempo. Os utilizadores podem facilitar este processo movendo a HoloLens de determinadas formas através do espaço.
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
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640046"
---
# <a name="map-physical-spaces-with-hololens"></a>Mapear espaços físicos com HoloLens

HoloLens mistura hologramas com o seu mundo físico. Para isso, HoloLens tem de aprender sobre o mundo físico que nos rodeia e lembrar-se de onde coloca hologramas dentro desse espaço.

Com o tempo, o HoloLens constrói um *mapa espacial* do ambiente que tem visto.  HoloLens atualiza o mapa à medida que o ambiente muda. Desde que esteja iniciado e o dispositivo esteja ligado, HoloLens cria e atualiza os seus mapas espaciais. Se segurar ou usar o dispositivo com as câmaras apontadas para um espaço, o HoloLens tenta mapear a área. Enquanto o HoloLens aprende um espaço naturalmente ao longo do tempo, existem formas de ajudar HoloLens mapear o seu espaço de forma mais rápida e eficiente.  

> [!NOTE]
> Se o seu HoloLens não conseguir mapear o seu espaço ou estiver fora de calibração, HoloLens pode entrar no modo Limited. No modo Limited, não poderá colocar hologramas ao seu redor.

Este artigo explica como HoloLens mapear espaços, como melhorar o mapeamento espacial e como gerir os dados espaciais que HoloLens recolhe.

## <a name="choosing-and-setting-up-and-your-space"></a>Escolher e configurar e o seu espaço

As características do seu ambiente podem dificultar a interpretação de um espaço por parte da HoloLens. Níveis de luz, materiais no espaço, a disposição dos objetos, e muito mais podem afetar a forma como HoloLens mapear uma área.

HoloLens funciona melhor em certos tipos de ambientes. Para produzir o melhor mapa espacial, escolha um quarto com luz adequada e muito espaço. Evite espaços e quartos escuros que tenham muitas superfícies escuras, brilhantes ou translúcidas (por exemplo, espelhos ou cortinas gauzy).

HoloLens é otimizado para uso interno. O mapeamento espacial também funciona melhor quando Wi-Fi é ligado, embora não tenha que ser conectado a uma rede. HoloLens podem obter Wi-Fi pontos de acesso mesmo que não esteja ligado ou autenticado. HoloLens funcionalidade não altera se os pontos de acesso estão ligados à Internet ou apenas intranet/local.

Utilize HoloLens em locais seguros sem perigo de tropeçar. [Mais em matéria de segurança.](https://support.microsoft.com/help/4023454/safety-information)

## <a name="mapping-your-space"></a>Mapear o seu espaço

Agora está pronto para começar a mapear o seu sobressalente.  Quando HoloLens começar a mapear o seu ambiente, você verá um gráfico de malha espalhando-se pelo espaço.  Em casa de realidade mista, você pode desencadear o mapa para mostrar selecionando em uma superfície mapeada.

Aqui estão as diretrizes para a construção de um grande mapa espacial.

### <a name="understand-the-scenarios-for-the-area"></a>Compreender os cenários para a área

É importante passar o maior tempo onde você vai usar o HoloLens, para que o mapa seja relevante e completo. Por exemplo, se um cenário de utilizador para HoloLens envolve mover-se do ponto A para o ponto B, caminhe nesse caminho duas a três vezes, olhando em todas as direções à medida que se move.  

### <a name="walk-slowly-around-the-space"></a>Caminhe lentamente pelo espaço

Se andar muito rápido pela área, é provável que o HoloLens perca áreas de mapeamento. Caminhe lentamente pelo espaço, parando a cada 1,5 m para olhar ao redor.  

Os movimentos suaves também ajudam a HoloLens mapear de forma mais eficiente.

### <a name="look-in-all-directions"></a>Olhe em todas as direções

Olhando ao redor à medida que mapeia o espaço dá ao HoloLens mais dados sobre onde os pontos são relativos uns aos outros.  

Se não olhar para cima, por exemplo, o HoloLens pode não saber onde fica o teto de uma sala.  

Não se esqueça de olhar para o chão enquanto mapeia o espaço.

### <a name="cover-key-areas-multiple-times"></a>Cobrir áreas-chave várias vezes

Mover-se através de uma área várias vezes ajudará a captar funcionalidades que pode ter perdido na primeira passagem. Para construir um mapa ideal, tente atravessar uma área duas a três vezes.

Se possível, enquanto repete estes movimentos, passe o tempo a caminhar por uma área numa direção, depois vire-se e caminhe por onde veio.

### <a name="take-your-time-mapping-the-area"></a>Leve o seu tempo a mapear a área

Pode levar entre 15 e 20 minutos para que o HoloLens mapear e se ajustar ao seu meio envolvente. Se você tem um espaço no qual você planeja usar um HoloLens frequentemente, tomar esse tempo na frente para mapear o espaço pode prevenir problemas mais tarde.  

## <a name="possible-errors-in-the-spatial-map"></a>Possíveis erros no mapa espacial

Os erros nos dados de mapeamento espacial enquadram-se em algumas categorias:

- *Buracos*: Faltam superfícies do mundo real dos dados de mapeamento espacial.
- *Alucinações*: Existem superfícies nos dados de mapeamento espacial que não existem no mundo real.
- *Wormholes*: HoloLens 'perde' parte do mapa espacial pensando que está numa parte diferente do mapa do que realmente é.
- *Viés*: As superfícies dos dados de mapeamento espacial estão imperfeitamente alinhadas com superfícies do mundo real, empurradas para dentro ou retiradas.

Se vir algum destes erros, utilize o [FeedbackHub](hololens-feedback.md) para enviar feedback.

## <a name="security-and-storage-for-spatial-data"></a>Segurança e armazenamento para dados espaciais

Windows 10 atualização da versão 1803 para Microsoft HoloLens e posteriormente armazena dados de mapeamento numa base de dados local (on-device).

HoloLens utilizadores não podem aceder diretamente à base de dados do mapa, mesmo quando o dispositivo está ligado a um PC ou quando utiliza a aplicação Do Explorador de Ficheiros. Quando o BitLocker é ativado no HoloLens, os dados do mapa armazenados também são encriptados juntamente com todo o volume.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Remova os dados do mapa e espaços conhecidos de HoloLens

Existem duas opções para eliminar dados de mapas em **Definições > System > Hologramas:**

- Para eliminar hologramas próximos, **selecione Remova os hologramas próximos.** Este comando limpa os dados do mapa e os hologramas ancorados para o espaço atual. Se continuar a utilizar o dispositivo no mesmo espaço, cria e armazena uma nova secção de mapas para substituir as informações eliminadas.

   > [!NOTE]
   > Hologramas "próximos" são hologramas que estão ancorados dentro da mesma secção de mapas no espaço atual.

   Por exemplo, pode usar esta opção para limpar dados de mapas relacionados com o trabalho sem afetar quaisquer dados do mapa relacionado com a casa.

- Para eliminar todos os hologramas, **selecione Remover todos os hologramas**. Este comando limpa todos os dados do mapa que são armazenados no dispositivo, bem como todos os hologramas ancorados. Terá de colocar explicitamente quaisquer hologramas. Não será capaz de redescobrir os hologramas anteriormente colocados.

> [!NOTE]
> Depois de remover nas proximidades ou em todos os hologramas, HoloLens começa imediatamente a digitalizar e mapear o espaço atual.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi dados em mapas espaciais

HoloLens armazena características Wi-Fi para ajudar a correlacionar as localizações do holograma e as secções de mapas que são armazenadas dentro da base de dados HoloLens de espaços conhecidos. As informações sobre Wi-Fi características não são acessíveis aos utilizadores, e não são enviadas para a Microsoft usando a nuvem ou usando telemetria.

Enquanto Wi-Fi estiver ativado, HoloLens correlaciona os dados do mapa com os pontos de acesso Wi-Fi próximos. Não há diferença de comportamento se uma rede está conectada ou apenas detetada nas proximidades. Se Wi-Fi estiver desativado, HoloLens ainda procura no espaço. No entanto, HoloLens tem de pesquisar mais dados do mapa dentro da base de dados dos espaços, e pode precisar de mais tempo para encontrar hologramas. Sem a Wi-Fi informação, o HoloLens tem de comparar as análises ativas a todas as âncoras de hologramas e secções de mapa que são armazenadas no dispositivo de forma a localizar a parte correta do mapa.

## <a name="related-topics"></a>Tópicos relacionados

- [Design de mapeamento espacial](/windows/mixed-reality/spatial-mapping)
