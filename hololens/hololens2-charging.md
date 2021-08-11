---
title: HoloLens bateria 2 e carregamento
description: Como carregar o seu HoloLens e utilizar baterias externas.
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
ms.openlocfilehash: b117542704968150639a47956a8142d7232fcc66d696feb61ec4fffdaa49df59
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660572"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens bateria 2 e carregamento

Esta página oferece detalhes sobre o carregamento HoloLens 2 e a utilização de baterias externas.

## <a name="charging-the-device"></a>Carregar o dispositivo

Utilize o [carregador e o cabo USB Type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) que veio com o HoloLens 2, pois esta é a melhor maneira de carregar o seu dispositivo. O carregador incluído com HoloLens 2 fornece até 9V @ 2A (18W). Juntamente com o carregador de parede fornecido, HoloLens 2 dispositivos podem carregar a bateria até à totalidade em menos de 65 minutos quando o dispositivo estiver em modo de espera. Se esses acessórios não estiverem disponíveis, certifique-se de que o carregador disponível pode suportar pelo menos 15W de energia.

> [!NOTE]
> Se possível, evite utilizar um PC para carregar o dispositivo em USB, o que é lento.

## <a name="checking-the-battery-charge-level"></a>Verificando o nível de carga da bateria
Se o dispositivo estiver corretamente iniciado e em funcionamento, existem três formas de verificar o nível de carga da bateria:

- A partir do menu principal do dispositivo HoloLens UI.
- Ver o LED perto do botão de alimentação (para uma carga de 40%, deverá ver pelo menos dois LED sólidos).
    - Quando o aparelho está a carregar, o indicador da bateria acende-se para indicar o nível de carga atual.  A última luz desvanece-se para dentro e para fora para indicar o carregamento ativo.
    - Quando o seu HoloLens estiver ligado, o indicador da bateria mostra o nível da bateria em cinco incrementos.
    - Quando apenas uma das cinco luzes está acesa, o nível da bateria está abaixo dos 20%.
    - Se o nível da bateria estiver criticamente baixo e tentar ligar o dispositivo, uma luz piscará brevemente e apagar-se-á.
- No seu PC anfitrião, abra o **File Explorer** e procure o seu dispositivo HoloLens 2 no lado esquerdo sob **este PC**. Clique com o botão direito no dispositivo e selecione **Propriedades**. Uma caixa de diálogo mostrará o nível de carga da bateria.

   ![Um ecrã de HoloLens de 2 propriedades mostra o nível de mudança de bateria](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Especificações de carregamento alternativos

HoloLens 2 podem ser carregados por fontes [usb de entrega de energia](https://www.usb.org/usb-charger-pd) até 27 Watts. Se a fonte for capaz de fornecer pelo menos 10 Watts, HoloLens tempo de funcionamento pode ser prolongado (potencialmente indefinidamente para algumas cargas de trabalho). 

> [!NOTE]
> A utilização de um cabo de carregamento USB-A a USB-C limitará a carga a 7,5 Watts. O tempo de funcionamento continuará a ser prolongado, mas não tanto quanto a utilização usb-C a C.

Quando HoloLens está em modo de espera, 18 Watts é suficiente para atingir a taxa máxima de carga para a bateria interna. Quando HoloLens estiver a ser utilizada, a taxa de carga pode ser reduzida uma vez HoloLens prioriza o funcionamento em vez de cobrar.

> [!IMPORTANT]
> Recomenda-se que HoloLens 2 sejam carregados a 5V/1.5A no mínimo. Os carregadores que não podem fornecer pelo menos 5V/1.5A não devem ser utilizados. 

### <a name="external-battery-packs"></a>Baterias externas

As baterias que satisfaçam as especificações acima podem ser utilizadas com HoloLens 2. No entanto, note que algumas baterias USB-C recarregam e fornecem energia através da mesma porta USB-C. É importante que estas baterias implementem [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) para garantir que cobram HoloLens em vez de cobrar dele. 

### <a name="managing-heat"></a>Gestão do Calor

Como em qualquer dispositivo, o carregamento HoloLens gera calor. Quanto mais rápida for a carga, mais calor é gerado. Além disso, iniciar uma carga a um nível de bateria mais baixo gerará mais calor do que iniciar uma carga quando a bateria está maioritariamente cheia. Os clientes que necessitem de operar HoloLens por longos períodos de tempo em ambientes quentes podem utilizar as seguintes técnicas:

- Não há problema em ligar HoloLens 2 a uma fonte de energia externa, mesmo quando a bateria interna está completamente carregada.
- Quando uma bateria externa estiver esgotada, HoloLens continuará a funcionar na sua bateria interna.    
- Se o calor continuar a ser um problema depois de seguir os passos acima, considere a utilização de um carregador ou bateria que limite o carregamento a 1,5A. Note que esta opção não proporcionará tanto tempo de funcionamento, uma vez que a bateria interna continuará a esgotar-se lentamente.

## <a name="troubleshooting"></a>Resolução de problemas


### <a name="hololens-charges-external-battery"></a>HoloLens Cargas bateria externa
Se HoloLens 2 carregar uma bateria externa em vez de ser carregada por ela, isto indica que a bateria não implementa [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Mudar para uma bateria mais recente é a forma recomendada de resolver este problema, mas em alternativa pode tentar mudar para um cabo USB-A para USB-C. Tenha em mente que isto limitará a taxa de carregamento a 7,5 watts.
