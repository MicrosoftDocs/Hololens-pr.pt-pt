---
title: HoloLens modo de plataforma móvel 2
description: Como usá HoloLens em plataformas móveis
keywords: plataformas em movimento, movimento dinâmico, hololens, modo de plataforma móvel
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 10/12/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7c636cd97e31c74d4976e71ec3f41ac5afe5bdcc
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924431"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Modo de plataforma móvel em plataformas de movimento de movimento de movimento de baixo dinâmico

Em [Windows Holographic, versão 21H2,](hololens-release-notes.md#windows-holographic-version-21h2) adicionámos suporte beta para rastrear plataformas de movimento de baixa dinâmica em HoloLens 2. Depois de instalar o modo de plataforma móvel e de construção, poderá utilizar o seu HoloLens 2 em ambientes anteriormente inacessíveis, como grandes navios e grandes embarcações marinhas. Atualmente, a funcionalidade destina-se a ativar estas plataformas móveis específicas apenas. Apesar de nada o impedir de tentar utilizar a funcionalidade em outros ambientes, a funcionalidade está focada em adicionar suporte a estes ambientes em primeiro lugar.

![Exemplo de plataforma em movimento.](./images/mpm-compare.gif)

Este artigo abrange:

1. [Por que a plataforma móvel é necessária](#why-moving-platform-mode-is-necessary)
1. [Ativar o modo de plataforma móvel](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Por que o modo de plataforma móvel é necessário

HoloLens precisa de ser capaz de rastrear a sua posição de cabeça com [6 graus de liberdade](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) (X, Y, Z, tradução e rolo, pitch, rotação de bocejo) para mostrar hologramas estáveis. Para isso, HoloLens rastreia duas informações semelhantes de duas fontes distintas:

1. **Câmaras de luz visíveis.** Estas câmaras rastreiam o ambiente, por exemplo, a sala física em que está a usar o HoloLens
1. **Unidade de Medição por Inércia (IMU).** O IMU consiste num acelerómetro, giroscópio e magnetómetro que rastreia o movimento da cabeça e a orientação em relação à Terra.

A informação destas duas fontes é composta para rastrear a sua posição na cabeça com baixa latência e frequência suficientemente alta para tornar os hologramas lisos.

No entanto, esta abordagem baseia-se num pressuposto crítico; o ambiente (rastreado pelas câmaras) permanece estacionário em relação à Terra (contra o qual a IMU pode efetuar medições). Quando não é esse o caso, como num barco na água, a informação de ambas as fontes pode entrar em conflito entre si e fazer com que o localizador se perca. Este conflito produz informações de posição incorretas e resulta em hologramas de natação ou até mesmo em perda de rastreamento.

O Modo plataforma móvel resolve este problema. Quando ativa o Modo plataforma móvel, isso é uma dica para o nosso localizador de que não podemos confiar nas nossas entradas de sensores para concordarmos completamente uns com os outros em todos os momentos. Em vez disso, precisamos confiar mais fortemente no rastreio visual e identificar rapidamente dados de movimento incongruentes inércias e filtrá-los em conformidade antes de podermos usar a entrada do IMU.

## <a name="supported-environments-and-known-limitations"></a>Ambientes Apoiados e Limitações Conhecidas

Embora o Modo plataforma móvel tenha sido desenvolvido para lidar inteligentemente com casos de conflito de dados inercial e visual, atualmente é localizado em grandes embarcações marinhas que experimentam movimentos de baixa dinâmica. O que significa que há certamente limitações e cenários não apoiados.

### <a name="known-limitations"></a>Limitações Conhecidas

- Os únicos ambientes suportados para o modo de plataforma móvel (MPM) são grandes navios marinhos que experimentam movimentos de baixa dinâmica. Por outras palavras, muitos ambientes/situações comuns ainda **não** são suportados devido ao seu movimento de alta frequência e elevados níveis de aceleração e [empurrão.](https://en.wikipedia.org/wiki/Jerk_(physics)) Por exemplo: aviões, comboios, carros, bicicletas, autocarros, pequenos barcos, elevadores, etc.
- Hologramas podem oscilar ligeiramente quando o MPM estiver ativado, especialmente quando estiver em água picada.
- Nada impede que os utilizadores tentem utilizar MPM em ambientes não suportados, no entanto, os utilizadores podem experimentar efeitos colaterais indesejáveis se o dispositivo for capaz de manter o rastreio no espaço não suportado. Por exemplo, com o MPM, os utilizadores podem descobrir que é possível usar num elevador enquanto mudam de piso, enquanto que isso era anteriormente impossível. Infelizmente, embora o MPM permita que o dispositivo mantenha o rastreio, não lida com a gestão do mapa neste momento. Os utilizadores descobrirão que mudar de piso num elevador fará com que o dispositivo confunda os andares superiores e inferiores e afete negativamente a qualidade do mapa.

## <a name="prerequisites"></a>Pré-requisitos

O suporte beta para o modo plataforma móvel requer apenas alguns pré-requisitos:

1. Instale [Windows Holographic, versão 21H2](hololens-release-notes.md#windows-holographic-version-21h2) ou mais recente, atualizando ou piscando a [mais recente construção](https://aka.ms/hololens2download) [via ARC](hololens-recovery.md#clean-reflash-the-device).

2. Ativar [o modo de desenvolvimento e o portal do dispositivo](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Ativar o modo de plataforma móvel

Para ativar o modo plataforma móvel, [primeiro ative o Portal do Dispositivo](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Selecione o acordeão **do Sistema** no menu à esquerda

   ![Primeira imagem.](.\images\mpm-01.png)

2. Selecione a página **modo plataforma móvel** e verifique a caixa de **verificação do modo de plataforma móvel**

    ![Segunda imagem.](.\images\mpm-02.png)

3. Quando solicitado com uma advertência, selecione **OK**

   ![Terceira imagem.](.\images\mpm-03.png)

4. Reinicie o seu dispositivo, que pode ser feito através do **menu** 'Poder do Portal do Dispositivo' no canto superior direito ou através da emissão do seguinte comando de voz &quot; Reinicie o dispositivo &quot; e selecione &quot; Sim &quot; .

   ![Quarta imagem.](.\images\mpm-04.png)

Se não conseguir ver a opção Modo plataforma móvel no Portal do Dispositivo, então é provável que ainda não esteja na construção adequada. Consulte a secção [Pré-Requisitos.](#prerequisites)

## <a name="reporting-issues"></a>Questões de Reporte

Como mencionado acima, esta funcionalidade é uma funcionalidade beta disponível apenas no Modo Desenvolvedor, o que significa que pode atingir problemas. Se isso acontecer, podemos investigar e melhorar o produto:

1. Reportar o problema através do [Feedback Hub](hololens-feedback.md) sob a categoria **de precisão, estabilidade e fiabilidade** do Holograma e incluir:
    1. Uma descrição do problema, incluindo o comportamento esperado e comportamento experimentado
    1. Uma captura de [vídeo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) da Realidade Mista da questão
2.  Abra um caso de suporte [https://aka.ms/hlsupport](https://aka.ms/hlsupport) e partilhe o URL do Feedback Hub, para que possamos chegar ao caso de termos questões de acompanhamento