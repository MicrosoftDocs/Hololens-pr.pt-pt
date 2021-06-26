---
title: Prepare um novo HoloLens 2
description: Aprenda a configurar e ajustar o seu dispositivo HoloLens 2 pela primeira vez, incluindo dicas de saúde e segurança e guias de hardware.
keywords: hololens, luzes, ajuste, conforto, partes
ms.assetid: 02692dcf-aa22-4d1e-bd00-f89f51048e32
ms.date: 9/17/2019
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 22b3dad817260175bccdb89faac0bbae7b210038
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924439"
---
# <a name="get-your-hololens-2-ready-to-use"></a>Tenha os hololens 2 prontos a usar

Os procedimentos abaixo irão ajudá-lo a configurar um HoloLens 2 pela primeira vez.

## <a name="charge-your-hololens"></a>Carregue os hololens

Ligue a alimentação à porta de carregamento utilizando o cabo USB-C (incluído). Ligue a alimentação a uma tomada de corrente. A alimentação e o cabo USB-C-a-C que acompanham o dispositivo são a melhor forma de carregar os HoloLens 2. O carregador fornece 18W de potência (9V a 2A). Utilizando o carregador de parede fornecido, os dispositivos HoloLens 2 podem carregar a bateria até à totalidade em menos de 65 minutos quando o dispositivo estiver em modo de espera.

A velocidade e a velocidade de carregamento podem variar consoante o ambiente em que o dispositivo está a funcionar.

- Quando o aparelho está a carregar, o indicador da bateria acende-se para indicar o nível de carga atual.  A última luz desvanece-se para dentro e para fora para indicar o carregamento ativo.
- Quando os HoloLens estiverem ligados, o indicador da bateria mostra o nível da bateria em incrementos.
- Quando apenas uma das cinco luzes está acesa, o nível da bateria está abaixo dos 20%.
- Se o nível da bateria estiver criticamente baixo e tentar ligar o dispositivo, uma luz piscará brevemente e apagar-se-á.

Todos os [detalhes sobre o carregamento do dispositivo podem ser lidos aqui](hololens2-charging.md#charging-the-device) se forem necessárias mais informações. 

## <a name="adjust-fit"></a>Ajuste o ajuste

Coloque os HoloLens 2 na sua cabeça. Se usar óculos, deixe-os ligados.  A almofada de sobrancelha deve sentar-se confortavelmente na testa e a banda traseira deve sentar-se no meio da sua cabeça.

Se necessário, estenda a fita da cabeça rodando a roda de regulação e, em seguida, desaperte a correia superior.

![HoloLens 2 ajustes e ajustes](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>Prenda e retire a correia superior

A correia superior não é necessária, mas pode tornar o uso de HoloLens 2 mais confortável durante longos períodos de utilização.

Para desprender a parte frontal da correia superior, desaperte a correia e deslize-a através do laço retrátil na almofada de sobrancelhas. Para voltar a ligá-lo, puxe o laço e deslize a correia para trás.

Para desprender a parte de trás da correia superior, pressione o botão abaixo de cada separador de ligação e puxe suavemente. Para voltar a ligá-lo, empurre as linguetas de ligação de volta para as ranhuras até que clicem.

![prender ou remover a correia da cabeça HoloLens 2](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>Ligue os HoloLens 2

Para ligar os HoloLens 2, prima o botão De alimentação.  Os LEDs abaixo do botão de alimentação exibem o nível da bateria.

> [!NOTE]
> Para ligar o HoloLens 2 pela primeira vez, depois de desboxe, prima e segure o botão de alimentação durante pelo menos 4 segundos para o ligar. Da próxima vez que ligar os HoloLens 2, começará depois de um curto botão de energia premir.

### <a name="power-button-actions-for-different-power-transitions"></a>Ações de botão de potência para diferentes transições de potência

| Para efetuar isto | Realizar esta ação | Os HoloLens 2 vão fazer isto. |
| - | - | - |
| Para ligar | Pressione um único botão. | Todas as cinco luzes acendem-se e depois mudam para indicar o nível da bateria. Após quatro segundos, um som toca. |
| Para dormir | Pressione um único botão. | Todas as cinco luzes acendem-se e depois desaparecem uma de cada vez. Depois de as luzes se apagarem, um som reproduz-se e o ecrã exibe "Adeus". |
| Para acordar do sono | Pressione um único botão. | Todas as cinco luzes acendem-se e depois mudam para indicar o nível da bateria. Um som toca imediatamente. |
| Para desligar | Pressione e espere por 5s. |  Todas as cinco luzes acendem-se e depois desaparecem uma de cada vez. Depois de as luzes se apagarem, um som reproduz-se e o ecrã exibe "Adeus". |
| Para forçar os HoloLens a reiniciar se não responder | Pressione e espere por 10. | Todas as cinco luzes acendem-se e depois desaparecem uma de cada vez. Depois que as luzes se apagarem. |

## <a name="hololens-behavior-reference"></a>Referência de comportamento hololens

Não sabe o que significam as luzes indicadoras nos seus HoloLens? Quer saber como os HoloLens devem comportar-se durante o carregamento?  Aqui está uma ajuda!

### <a name="charging-behavior"></a>Comportamento de cobrança

| Estado do Dispositivo | Ação | HoloLens 2 vai fazer isto |
| - | - | - |
| OFF | Ligue o cabo USB | As transições do dispositivo para ON com luzes indicadoras que mostram o nível da bateria e o dispositivo começa a carregar.
| ON | Remover cabo USB | Dispositivo deixa de carregar
| ON | Ligue o cabo USB | Dispositivo começa a carregar
| SONO | Ligue o cabo USB | Dispositivo começa a carregar
| SONO | Remover cabo USB | Dispositivo deixa de carregar
| ON com cabo USB ligado | Desligar dispositivo | Transições do dispositivo para ON com luzes indicadoras que mostram o nível da bateria e dispositivo começará a carregar |

### <a name="lights-that-indicate-the-battery-level"></a>Luzes que indicam o nível da bateria

| Número de luzes | Nível de bateria |
| - | - |
| Quatro luzes sólidas, uma luz desaparecendo dentro e fora | Entre 100% e 81% (totalmente carregado) |
| Três luzes sólidas, uma luz desaparecendo dentro e fora | Entre 80% e 61% |
| Duas luzes sólidas, uma luz desaparecendo dentro e fora | Entre 60% e 41% |
| Uma luz sólida, uma luz desaparecendo dentro e fora | Entre 40% e 21% |
| Uma luz a desvanecer-se dentro e fora | Entre 20% e 5% ou menos (bateria crítica) |

### <a name="sleep-behavior"></a>Comportamento do sono

| Estado do Dispositivo | Ação | HoloLens 2 vai fazer isto |
| - | - | - |
| ON | Botão de potência única | Transições do dispositivo para SLEEP e desliga todas as luzes indicadoras |
| ON | Sem movimento por 3 minutos | Transição do dispositivo para SLEEP e desliga todas as luzes indicadoras |
| SONO | Botão de potência única Pressione | Transições do dispositivo para ON e acende luzes indicadoras |

### <a name="lights-to-indicate-problems"></a>Luzes para indicar problemas

| Quando fizer isto | As luzes fazem isto. | Significa que isto |
| - | - | - |
| Carrega no botão De alimentação. | Uma luz pisca cinco vezes e depois apaga-se. | A bateria HoloLens está criticamente fraca. Carregue os hololens. |
| Carrega no botão De alimentação. | Todas as cinco luzes piscam cinco vezes e depois apagam-se. |  Os HoloLens não podem começar corretamente e estão num estado de erro. [Reinstalar o sistema operativo](hololens-recovery.md) para recuperar o seu dispositivo. |
| Carrega no botão De alimentação. | As 1ª, 3ª e 5ª luzes piscam juntas continuamente. |  HoloLens pode ter uma falha de hardware. Suporte [de contacto](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb). |

## <a name="safety-and-comfort"></a>Segurança e conforto

### <a name="use-hololens-in-safe-surroundings"></a>Use HoloLens em ambientes seguros

Utilize os seus HoloLens num espaço seguro, livre de obstruções e perigos de tropeçar. Não o utilize quando precisa de um campo de visão claro ou não pode dedicar toda a sua atenção, como durante a condução de um veículo ou a fazer outras atividades potencialmente perigosas.

### <a name="stay-comfortable"></a>Mantenha-se confortável

Mantenha as suas primeiras sessões com holoLens breves e certifique-se de fazer pausas. Se sentir desconforto, pare e descanse até se sentir melhor. Isto pode incluir sentimentos temporários de náusea, enjoo, tonturas, desorientação, dor de cabeça, fadiga, tensão ocular ou olhos secos.

Consulte [as advertências e instruções de segurança do produto](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions).

> [!div class="nextstepaction"]
> [Configurar os seus HoloLens 2](hololens2-start.md)
