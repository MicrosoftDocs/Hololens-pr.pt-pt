---
title: considerações HoloLens ambiente
description: Obtenha a melhor experiência possível usando HoloLens quando otimizar o dispositivo para os seus olhos e ambiente.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: quadro holográfico, campo de visão, fov, calibração, espaços, ambiente, como-a, HoloLens, realidade mista, auscultadores de realidade mista
ms.openlocfilehash: bf70641958d6f29735512182fdf33ae48f40b956f3335643faeb5edb8a26f79f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664171"
---
# <a name="hololens-environment-considerations"></a>considerações HoloLens ambiente

HoloLens mistura o holográfico com o mundo "real", colocando hologramas no seu ambiente. Uma janela de aplicação holográfica "pendura" na parede, uma bailarina holográfica gira na mesa, orelhas de coelho sentam-se em cima da cabeça do seu amigo inconsciente. Quando estiveres a usar um jogo ou app imersivo, o mundo holográfico espalhar-se-á para encher o ambiente, mas ainda podes ver e mover-te pelo espaço.

Os hologramas que colocarem ficarão onde os colocou, mesmo que desligue o dispositivo.

## <a name="setting-up-an-environment"></a>Criação de um ambiente

HoloLens dispositivos sabem como colocar hologramas estáveis e precisos *rastreando* os utilizadores num espaço. Sem o rastreio adequado, o dispositivo não compreende o ambiente ou o utilizador dentro do mesmo. Hologramas podem aparecer nos lugares errados, não aparecer sempre no mesmo local, ou não aparecer. Os dados utilizados para rastrear os utilizadores estão representados no *mapa espacial.*  

O desempenho de rastreio é fortemente influenciado pelo ambiente em que o utilizador se encontra, e sintonizar um ambiente para induzir um rastreio estável e consistente é uma arte e não uma ciência. Muitos fatores ambientais diferentes são fundidos em conjunto para permitir o rastreio, mas como um desenvolvedor de Realidade Mista, existem vários fatores que você pode ter em mente para sintonizar um espaço para um melhor rastreamento.

### <a name="lighting"></a>Iluminação

Windows Mixed Reality utiliza luz visual para rastrear a localização do utilizador. Quando um ambiente é muito luminoso, as câmaras podem ficar saturadas, e nada é visto. Se o ambiente estiver muito escuro, as câmaras não conseguem obter informações suficientes, e nada é visto. A iluminação deve ser uniforme e suficientemente brilhante que um ser humano possa ver sem esforço, mas não tão brilhante que a luz seja dolorosa de se ver.  

As áreas onde há pontos de luz brilhante numa área escura geral também são problemáticas, uma vez que a câmara tem de se ajustar quando se desloca dentro e fora de espaços luminosos. Isto pode fazer com que o dispositivo se "perca" e pense que a mudança de luz equivale a uma mudança de localização. Níveis de luz estáveis numa área levarão a um melhor rastreio.  

Qualquer iluminação exterior também pode causar instabilidade no localizador, uma vez que o sol pode variar consideravelmente ao longo do tempo. Por exemplo, rastrear no mesmo espaço no verão vs. inverno pode produzir resultados drasticamente diferentes, uma vez que a luz de segunda mão no exterior pode ser maior em diferentes épocas do ano.  

Se você tem um luxmeter, um 500-1000 lux estável é um bom lugar para começar.  

#### <a name="types-of-lighting"></a>Tipos de iluminação

Diferentes tipos de luz num espaço também podem influenciar o rastreio. As lâmpadas pulsam com a eletricidade ca a passar por ela - se a frequência de CA for de 50 Hz, então a luz pulsa a 50 Hz. Para um humano, este pulsar não é notado. No entanto, a câmara de 30 fps da HoloLens vê estas alterações - algumas molduras estarão bem iluminadas, algumas estarão mal iluminadas e algumas estarão sobre-expostas à medida que a câmara tenta compensar os pulsos luminosos.  

Nos EUA, o padrão de frequência elétrica é de 60 Hz, pelo que os pulsos da lâmpada são harmonizados com o framerate de HoloLens - 60 impulsos Hz alinhados com o framerate de 30 FPS de HoloLens. No entanto, muitos países têm um padrão de frequência CA de 50 Hz, o que significa que alguns quadros HoloLens serão tomados durante os pulsos, e outros não. Em particular, a iluminação fluorescente na Europa é conhecida por causar problemas.  

Há algumas coisas que pode tentar resolver problemas cintilantes. A temperatura, a idade da lâmpada e os ciclos de aquecimento são causas comuns de cintilação fluorescente e a substituição de lâmpadas pode ajudar. Apertar as lâmpadas e certificar-se de que os desenhos atuais são constantes também podem ajudar.  

### <a name="items-in-a-space"></a>Itens em um espaço

HoloLens usa marcos ambientais únicos, também conhecidos como *características,* para se localizar num espaço.  

Um dispositivo quase nunca consegue rastrear numa área pobre de funcionalidades, uma vez que o dispositivo não tem forma de saber onde se encontra no espaço. Adicionar funcionalidades às paredes de um espaço é geralmente uma boa maneira de melhorar o rastreio. Cartazes, símbolos colados a uma parede, plantas, objetos únicos ou outros itens semelhantes ajudam. Uma mesa desarrumada é um bom exemplo de um ambiente que leva a um bom rastreio - há muitas características diferentes numa única área.  

Além disso, use características únicas no mesmo espaço. O mesmo cartaz repetido várias vezes sobre uma parede, por exemplo, causará confusão no dispositivo, uma vez que o HoloLens não saberá qual dos cartazes repetitivos está a olhar. Uma forma comum de adicionar características únicas é usar linhas de fita adesiva para criar padrões únicos e não repetitivos ao longo das paredes e do chão de um espaço.  

Uma boa pergunta a fazer a si mesmo é: se visse apenas uma pequena quantidade da cena, poderia localizar-se no espaço? Caso contrário, é provável que o dispositivo também tenha problemas de rastreio.

#### <a name="wormholes"></a>Buracos de minhoca

Se tiver duas áreas ou regiões que parecem iguais, o localizador pode pensar que são iguais. Isto leva o dispositivo a enganar-se a pensar que está noutro lugar. Chamamos a este tipo de áreas *repetitivas buracos de minhoca.*  

Para evitar buracos de minhoca, tente prevenir áreas idênticas no mesmo espaço. Áreas idênticas podem, por vezes, incluir estações de fábrica, janelas em um edifício, prateleiras de servidores ou estações de trabalho. As áreas de rotulagem ou a adição de características únicas a cada área semelhante podem ajudar a mitigar os buracos de minhoca.

### <a name="movement-in-a-space"></a>Movimento em um espaço

Se o seu ambiente estiver em constante mudança e mudança, o dispositivo não tem funcionalidades estáveis para localizar.  

Quanto mais objetos móveis estiverem num espaço, incluindo pessoas, mais fácil é perder o rasto. As correias transportadoras em movimento, os itens em diferentes estados de construção, e muitas pessoas num espaço são conhecidos por causar problemas de rastreio.

O HoloLens pode adaptar-se rapidamente a estas alterações, mas apenas quando essa área é claramente visível para o dispositivo. Áreas que não são vistas com tanta frequência podem ficar atrás da realidade, o que pode causar erros no mapa espacial. Por exemplo, um utilizador digitaliza um amigo e depois vira-se enquanto o amigo sai da sala. Uma representação 'fantasma' do amigo persistirá nos dados de mapeamento espacial até que o utilizador reescaneie o espaço agora vazio.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Proximidade do utilizador a itens no espaço

Da mesma forma que os humanos não conseguem focar-se bem em objetos próximos dos olhos, HoloLens lutas quando os objetos estão perto das suas câmaras. Se um objeto estiver demasiado próximo de ser visto com ambas as câmaras, ou se um objeto estiver a bloquear uma câmara, o dispositivo terá muito mais problemas com o rastreio contra o objeto.  

As câmaras não podem ver a menos de 15 cm de um objeto.

### <a name="surfaces-in-a-space"></a>Superfícies em um espaço

Superfícies fortemente refletoras provavelmente parecerão diferentes dependendo do ângulo, que afeta o rastreio. Pense num carro novo - quando se move à sua volta, a luz reflete-se e vê diferentes objetos na superfície à medida que se move. Para o rastreador, os diferentes objetos refletidos na superfície representam um ambiente em mudança, e o dispositivo perde o rastreio.

Objetos menos brilhantes são mais fáceis de localizar.

### <a name="wi-fi-fingerprint-considerations"></a>Wi-Fi considerações de impressões digitais

Enquanto Wi-Fi estiver ativado, os dados do mapa serão correlacionados com uma impressão digital Wi-Fi, mesmo quando não estiver ligado a uma rede/router WiFi real. Sem Wi-Fi informação, o espaço e hologramas podem ser ligeiramente mais lentos a reconhecer. Se os sinais Wi-Fi mudarem significativamente, o dispositivo pode pensar que está num espaço completamente diferente.

A identificação da rede (como o endereço SSID ou MAC) não é enviada para a Microsoft, e todas as referências Wi-Fi são mantidas locais no HoloLens.

## <a name="mapping-new-spaces"></a>Mapear novos espaços

Quando você entra num novo espaço (ou carrega um existente), você verá um gráfico de malha espalhando-se pelo espaço. Isto significa que o seu dispositivo está a mapear o que o rodeia. Enquanto um HoloLens aprenderá um espaço ao longo do tempo, há dicas e truques para mapear espaços.

## <a name="environment-management"></a>Gestão do ambiente

Existem duas configurações, que permitem aos utilizadores "limpar" hologramas e fazer com que HoloLens "esqueçam" um espaço. Existem em **Hologramas e ambientes** na aplicação de configurações, com a segunda definição também a aparecer em **Privacidade** na aplicação de definições.  

1. **Elimine hologramas próximos.** Quando selecionar esta definição, HoloLens apagará todos os hologramas ancorados e todos os dados do mapa armazenados para o "espaço atual" onde o dispositivo está localizado. Uma nova secção de mapas seria criada e armazenada na base de dados para esse local assim que os hologramas fossem novamente colocados nesse mesmo espaço.

1. **Elimine todos os hologramas.** Ao selecionar esta definição, HoloLens apagará todos os dados do mapa e hologramas ancorados em todas as bases de dados dos espaços. Nenhum holograma será redescoberto e quaisquer hologramas precisam de ser novamente colocados para armazenar novamente secções de mapas na base de dados.

## <a name="hologram-quality"></a>Qualidade do holograma

Hologramas pode ser colocado em todo o seu ambiente - alto, baixo e ao seu redor - mas você vai vê-los através de uma [moldura holográfica](/windows/mixed-reality/holographic-frame) que fica na frente dos seus olhos. Para obter a melhor vista, certifique-se de ajustar o seu dispositivo para que possa ver toda a moldura. E não hesite em passear pelo seu ambiente e explorar!

Para que os seus hologramas pareçam estaladiços, [claros](/windows/mixed-reality/hologram) e estáveis, o seu HoloLens precisa de ser calibrado apenas para si. Quando configurar o seu HoloLens, será guiado através deste processo. Mais tarde, se os hologramas não parecerem bem ou se estiveres a ver inúmeros erros, podes fazer ajustes.

Se você está tendo espaços de mapeamento de problemas, tente apagar hologramas próximos e remapeamento do espaço.

### <a name="calibration"></a>Calibração

Se os seus hologramas parecerem nervosos ou tremidos, ou se tiver problemas em colocar hologramas, a primeira coisa a experimentar é a [aplicação calibração](hololens-calibration.md). Esta aplicação também pode ajudar se estiver a sentir algum desconforto durante a utilização do seu HoloLens.

Para chegar à aplicação de calibração, vá a **Definições**  >    >  **System Utilities**. Selecione **Abrir a Calibração** e siga as instruções.

Se alguém estiver a usar o seu HoloLens, deve executar primeiro a aplicação calibração para que o dispositivo seja configurado corretamente para eles.

## <a name="temperature-and-regulatory-information"></a>Informação sobre temperatura e regulação

[HoloLens Informações regulamentares](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): Inclui informações sobre a gama de temperaturas, eliminação, interferência de rádio e TV, entre outras.

Consulte os detalhes relativos a "HoloLens" em [Materiais e substâncias](https://www.microsoft.com/legal/compliance/materials-substances) > REACH Artigo 33º Divulgação sobre conformidade ambiental (PDF).

Aqui ficam algumas diretrizes a seguir ao utilizar o seu dispositivo:

1. Guarde o dispositivo num ambiente dentro do intervalo de temperatura (em Standby ou Off) durante uma hora antes de utilizar o aparelho.
1. Utilize o dispositivo num ambiente dentro do intervalo de temperatura.
1. Utilize o dispositivo dentro de casa.
1. Utilizar o dispositivo à sombra; mesmo dentro de casa evitar a luz solar direta embora janelas ou claraboias.
1. Se seguir as diretrizes acima, mas experimentar problemas inesperados de sobreaquecimento, siga os passos abaixo para submeter [feedback](hololens-feedback.md). 
    1. Certifique-se de que a telemetria **completa** ou **opcional** está ativada no seu aparelho. Se não for, ative-o. 
    >[!CAUTION]
    > A telemetria não é retroativa para eventos térmicos - deve ser ativada durante o sobreaquecimento ou os dados necessários não serão capturados.
    
    2. Reproduza a questão do aquecimento.
    3. Inclua a data e a hora do sobreaquecimento.
    4. Enviar [feedback](hololens-feedback.md).

## <a name="see-also"></a>Ver também

- [Design de mapeamento espacial](/windows/mixed-reality/spatial-mapping)
- [Hologramas](/windows/mixed-reality/hologram)
