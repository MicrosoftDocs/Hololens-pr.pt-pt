---
title: plataforma móvel HoloLens 2
description: Como usá HoloLens em plataformas móveis
keywords: plataformas em movimento, movimento dinâmico, hololens, modo de plataforma em movimento
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ae9090409b9c357f7d7ced8ddd477fbebea62e1e3912a9d3691d5585ad79239c
ms.sourcegitcommit: 9615ed824bdf3f1747ec346da6136704d8eed015
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/11/2021
ms.locfileid: "120389211"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Modo de plataforma móvel em plataformas de movimento de movimento de movimento de movimento de baixo dinâmico

Na **build insider 20348.1411,** adicionámos suporte beta para rastrear plataformas de movimento de baixa dinâmica em HoloLens 2. Depois de instalar o modo de plataforma móvel, poderá utilizar o seu HoloLens 2 em ambientes anteriormente inacessíveis, como grandes navios e grandes embarcações marinhas. Atualmente, a funcionalidade destina-se a ativar estas plataformas móveis específicas apenas. Embora nada o impeça de tentar utilizar a funcionalidade em outros ambientes, a funcionalidade está focada em adicionar suporte a estes ambientes em primeiro lugar.

> [!NOTE]
> Esta funcionalidade só está disponível através de Windows [Insiders.](hololens-insider.md)

Este artigo abrange:

1. [Por que a plataforma móvel é necessária](#why-moving-platform-mode-is-necessary)
1. [Ativar o modo de plataforma móvel](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Por que o modo de plataforma móvel é necessário

HoloLens precisa de ser capaz de rastrear a sua posição de cabeça com [6 graus de liberdade](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) (X, Y, tradução z e rolo, pitch, rotação de bocejo) para mostrar hologramas estáveis. Para isso, HoloLens rastreia duas informações semelhantes de duas fontes distintas:

1. Câmaras de luz visíveis – que acompanham o ambiente, por exemplo, a sala física em que está a utilizar o HoloLens
1. Unidade de Medição Inercial (IMU), que consiste num acelerómetro, giroscópio e magnetómetro que rastreia o movimento e orientação da cabeça em relação à Terra

A informação destas duas fontes é composta para rastrear a sua posição na cabeça com baixa latência e frequência suficientemente alta para tornar os hologramas lisos.

No entanto, esta abordagem baseia-se num pressuposto crítico; o ambiente (rastreado pelas câmaras) permanece estacionário em relação à Terra (contra o qual a IMU pode efetuar medições). Quando não é esse o caso, como num barco na água, a informação de ambas as fontes pode entrar em conflito entre si e fazer com que o localizador se perca. Este conflito produz informações de posição incorretas e resulta em hologramas de natação ou até mesmo em perdas de rastreamento.

O Modo plataforma móvel resolve este problema. Quando ativa o Modo plataforma móvel, isso é uma dica para o nosso localizador que não podemos confiar nas nossas entradas de sensores para concordarmos completamente uns com os outros em todos os momentos. Em vez disso, temos de confiar mais fortemente no rastreio visual e identificar rapidamente dados de movimento incongruentes inércias e filtrá-los em conformidade antes de&#39;a reutilizar a entrada da IMU.

## <a name="supported-environments-and-known-limitations"></a>Ambientes Apoiados e Limitações Conhecidas

Enquanto o Modo plataforma móvel foi desenvolvido para lidar inteligentemente com casos de conflito de dados inercial e visual, atualmente é telescópio para grandes embarcações marinhas que experimentam movimentos de baixa dinâmica. O que significa que há certamente limitações e cenários não apoiados.

### <a name="known-limitations"></a>Limitações Conhecidas

- Os únicos ambientes suportados para o modo de plataforma móvel (MPM) são grandes navios marinhos que experimentam movimentos de baixa dinâmica. Por outras palavras, muitos ambientes/situações comuns ainda **não** são suportados devido ao seu movimento de alta frequência e elevados níveis de aceleração e [empurrão](https://en.wikipedia.org/wiki/Jerk_(physics)). Por exemplo: aviões, comboios, carros, bicicletas, autocarros, pequenos barcos, elevadores, etc.
- Hologramas podem oscilar ligeiramente quando o MPM está ativado, especialmente quando se está em água picada.
- Nada impede que os utilizadores tentem utilizar MPM em ambientes não suportados, no entanto, os utilizadores podem experimentar efeitos colaterais indesejáveis se o dispositivo for capaz de manter o rastreio no espaço não suportado. Por exemplo, com o MPM, os utilizadores podem achar&#39;possível de usar num elevador enquanto mudam de piso, enquanto que isso era anteriormente impossível. Infelizmente, embora o MPM permita que o dispositivo mantenha o rastreio, não lida com a gestão do mapa neste momento. Assim, os utilizadores vão descobrir que mudar de andar num elevador fará com que o dispositivo confunda os andares superiores e inferiores e afete negativamente a qualidade do mapa.

## <a name="prerequisites"></a>Pré-requisitos

O suporte beta para o modo plataforma móvel requer apenas alguns pré-requisitos:

1. Instale a construção 20348.1411 ou mais [recente, piscando os mais recentes Insiders construídos via ARC](hololens-insider.md#ffu-download-and-flash-directions) ou [inscrevendo e atualizando o seu dispositivo](hololens-insider.md#start-receiving-insider-builds).
   - Nota: Esta construção só está disponível no [Canal Insider Dev](hololens-insider.md#start-receiving-insider-builds).
2. Ativar [o modo de desenvolvimento e o portal do dispositivo](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Ativar o modo de plataforma móvel

Para ativar o modo plataforma móvel, [primeiro ative o Portal do Dispositivo](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Selecione o acordeão **do Sistema** no menu à esquerda
2. Selecione a página **modo plataforma móvel** e verifique a caixa de **verificação do modo de plataforma móvel**

![Primeira imagem](.\images\moving-platform-1.png) ![Segunda imagem](.\images\moving-platform-2.png)

3. Quando solicitado com uma advertência, selecione **OK**

![Terceira imagem](.\images\moving-platform-3.png)

4. Reinicie o seu dispositivo, que pode ser feito através do menu Device Portal **Power** no canto superior direito ou emitindo o seguinte comando de voz &quot; Reinicie o dispositivo &quot; e selecione &quot; Sim &quot; .

![Quarta imagem](.\images\moving-platform-4.png)

Se não conseguir ver a opção Modo plataforma móvel no Portal do Dispositivo, então é provável que ainda não esteja na construção adequada. Consulte a secção [Pré-Requisitos.](#prerequisites)