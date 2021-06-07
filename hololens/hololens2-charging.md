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
# <a name="battery-and-charging"></a>Bateria e carregamento

Esta página oferece detalhes sobre o carregamento de HoloLens 2 e a utilização de baterias externas.

## <a name="included-charger"></a>Carregador Incluído

O carregador incluído com HoloLens 2 fornece até 9V @ 2A (18W). Quando possível, é altamente recomendado carregar usando o carregador incluído.  

## <a name="specifications"></a>Especificações

HoloLens 2 pode ser carregado por fontes [usb de entrega de energia](https://www.usb.org/usb-charger-pd) até 27 Watts. Se a fonte for capaz de fornecer pelo menos 10 Watts, o tempo de funcionamento do HoloLens pode ser prolongado (potencialmente indefinidamente para algumas cargas de trabalho). 

> [!NOTE]
> A utilização de um cabo de carregamento USB-A a USB-C limitará a carga a 7,5 Watts. O tempo de funcionamento continuará a ser prolongado, mas não tanto quanto a utilização usb-C a C.

Quando o HoloLens está em modo de espera, 18 Watts é suficiente para atingir a taxa máxima de carga para a bateria interna. Quando holoLens está em uso, a taxa de carga pode ser reduzida uma vez que HoloLens prioriza o funcionamento sobre o carregamento.

> [!IMPORTANT]
> Recomenda-se que hololens 2 sejam carregados a 5V/1.5A no mínimo. Os carregadores que não podem fornecer pelo menos 5V/1.5A não devem ser utilizados. 

## <a name="external-battery-packs"></a>Baterias externas

As baterias que satisfaçam as especificações acima podem ser utilizadas com HoloLens 2. No entanto, note que algumas baterias USB-C recarregam e fornecem energia através da mesma porta USB-C. É importante que estas baterias implementem [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) para garantir que cobram HoloLens em vez de cobrar dele. 

## <a name="managing-heat"></a>Gestão do Calor

Como em qualquer dispositivo, o carregamento holoLens gera calor. Quanto mais rápida for a carga, mais calor é gerado. Além disso, iniciar uma carga a um nível de bateria mais baixo gerará mais calor do que iniciar uma carga quando a bateria está maioritariamente cheia. Os clientes que precisam de operar HoloLens por longos períodos de tempo em ambientes quentes podem utilizar as seguintes técnicas:

- Não há problema em ligar o HoloLens 2 a uma fonte de energia externa, mesmo quando a bateria interna está completamente carregada.
- Quando uma bateria externa estiver esgotada, a HoloLens continuará a operar na sua bateria interna.    
- Se o calor continuar a ser um problema depois de seguir os passos acima, considere a utilização de um carregador ou bateria que limite o carregamento a 1,5A. Note que esta opção não proporcionará tanto tempo de funcionamento, uma vez que a bateria interna continuará a esgotar-se lentamente.

## <a name="troubleshooting"></a>Resolução de problemas


### <a name="hololens-charges-external-battery"></a>HoloLens carrega bateria externa
Se o HoloLens 2 carregar uma bateria externa em vez de ser carregada por ela, isto indica que a bateria não implementa [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Mudar para uma bateria mais recente é a forma recomendada de resolver este problema, mas em alternativa pode tentar mudar para um cabo USB-A para USB-C. Tenha em mente que isto limitará a taxa de carregamento a 7,5 watts.
