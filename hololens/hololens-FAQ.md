---
title: Perguntas frequentes sobre dispositivos HoloLens e hologramas
description: Tem alguma pergunta rápida sobre hololens ou interagindo com hologramas?  Este artigo fornece uma resposta rápida e mais recursos.
keywords: hololens, faq, questão conhecida, ajuda
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924031"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologramas e interações resolução de problemas

Este artigo resoluções de problemas com a colocação de hologramas, trabalhando com espaços e reportando problemas com hologramas.

Sempre que tiver problemas, certifique-se:
- Tente [reiniciá-lo](hololens-restart-recover.md) para ver se isso corrige as coisas.
- Antes de resolver problemas, certifique-se de que os HoloLens [estão carregados](hololens2-charging.md) (carregados durante pelo menos uma hora). 


Por favor, utilize a aplicação Feedback para nos enviar informações sobre o assunto. Encontrará a aplicação Feedback no menu [ **Iniciar.**](holographic-home.md) 

Para obter dicas sobre como usar os hololens, consulte [Adjust Fit](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Novos espaços não podem ser criados](#new-spaces-cant-be-created)
- [Os espaços não podem ser identificados ou carregados](#spaces-cant-be-identified-or-loaded)
- [Como apago todos os espaços?](#how-do-i-delete-all-spaces)
- [Hologramas não parecem certos ou estão a mover-se](#holograms-dont-look-right-or-are-moving-around)
- [Mensagem "Encontrar o seu espaço"](#finding-your-space-message)
- [Hologramas esperados não estão a aparecer no meu espaço](#expected-holograms-arent-showing-in-my-space)
- [Não pode colocar hologramas ou ver hologramas previamente colocados](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramas desaparecem ou estão envoltos em outros hologramas ou objetos](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramas estão aparecendo do outro lado de uma parede](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Depois de colocar um holograma na parede, parece flutuar](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [As aplicações parecem muito próximas depois de movê-las](#apps-appear-too-close-after-moving-them)
- [Problemas de reporte com hologramas instáveis ou inexatos](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Novos espaços não podem ser criados

O problema mais provável é que estejas a ficar sem espaço de armazenamento. [Liberte algum espaço em disco](hololens-troubleshooting.md#low-disk-space-error) e depois redaça.

[De volta à lista](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Os espaços não podem ser identificados ou carregados

Se os hololens não conseguirem identificar e carregar o espaço em que se encontre automaticamente, verifique os seguintes fatores:

- Certifique-se de que está ligado a Wi-Fi
- Certifique-se de que há muita luz no quarto.
- Certifique-se de que não houve grandes alterações nos arredores.

Também pode carregar um espaço manualmente ou gerir os seus espaços indo para Os Espaços do Sistema **de Definições.**  >    >  

[De volta à lista](#list)

## <a name="how-do-i-delete-all-spaces"></a>Como apago todos os espaços?

*Brevemente*

[De volta à lista](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramas não parecem certos ou estão a mover-se

Se os hologramas não parecerem certos (por exemplo, estão nervosos ou tremidos, ou se vir manchas pretas em cima deles), experimente uma destas correções:

- [Limpe a viseira do dispositivo](hololens1-hardware.md#care-and-cleaning) e certifique-se de que nada bloqueia os sensores.
- Certifique-se de que está numa sala bem iluminada que não tem muita luz solar direta.
- Tente andar por aí e olhar para o que o rodeia para que os HoloLens possam digitalizá-los mais completamente.
- Se colocou muitos hologramas, tente remover alguns.

Se ainda tiver problemas, tente executar a aplicação de Calibração. Esta aplicação calibra os seus HoloLens apenas para ajudar a manter os hologramas no seu melhor. Para isso, aceda aos   >    >  **Utilitários** do Sistema de Definições . Em **Calibração,** selecione **Calibração Aberta**.

[De volta à lista](#list)

## <a name="finding-your-space-message"></a>Mensagem "Encontrar o seu espaço"

Quando o HoloLens está a aprender ou a carregar um espaço, podes ver uma breve mensagem que diz "Encontrar o teu espaço". Se esta mensagem for exibida por mais de alguns segundos, verá outra mensagem no menu Iniciar que diz "Ainda à procura do seu espaço".

Estas mensagens significam que os HoloLens estão com dificuldades em mapear o seu espaço. Quando isso acontece, pode abrir apps, mas não pode colocar hologramas no seu ambiente.

Se vir estas mensagens com frequência, experimente uma ou mais das seguintes correções:

- Certifique-se de que está numa sala bem iluminada que não tem muita luz solar direta.
- Certifique-se de que a viseira do dispositivo está limpa. [Aprenda a limpar a viseira.](hololens1-hardware.md#care-and-cleaning)
- Certifique-se de que tem um sinal Wi-Fi forte. Se você entrar num novo ambiente que não tem Wi-Fi ou um sinal fraco Wi-Fi, holoLens não será capaz de encontrar o seu espaço. Verifique a sua ligação Wi-Fi indo para **o**  >  **&amp;**  >  **Wi-Fi** de Internet da Rede de Definições.
- Tente mover-se mais devagar.

[De volta à lista](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Hologramas esperados não estão a aparecer no meu espaço

Se não vir os hologramas que colocou, ou se estiver a ver alguns que não espera, experimente uma ou mais das seguintes correções:

- Acende umas luzes. HoloLens funciona melhor num espaço bem iluminado.
- Remova hologramas de que não necessita indo para Hologramas do Sistema **de Definições**  >    >    >  **Remova hologramas nas proximidades**. Ou, se necessário, **selecione Remover todos os hologramas.**

  > [!NOTE]
  > Se o layout ou iluminação no seu espaço mudar significativamente, o seu dispositivo pode ter dificuldade em identificar o seu espaço e mostrar os hologramas.

[De volta à lista](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Não pode colocar hologramas ou ver hologramas previamente colocados

Se o HoloLens não conseguir mapear ou carregar o seu espaço, ele entra no modo Limited e não poderá colocar hologramas ou ver hologramas que colocou. Seguem-se algumas soluções que pode experimentar:

- Certifique-se de que há luz suficiente no seu ambiente para que os HoloLens possam ver e mapear o espaço.
- Fique entre um e três metros de onde está tentando colocar o holograma.
- Não coloque hologramas em superfícies pretas ou refletoras.
- Certifique-se de que está ligado a uma rede Wi-Fi. Se não estiver ligado ao Wi-Fi, os HoloLens não conseguem identificar e carregar um espaço conhecido.
- Caminhe pelos quartos para que hololens possam rescanar o que o rodeia. Para ver o que já foi digitalizado, toque de ar para revelar o gráfico de malha de mapeamento.
- Se precisar de criar um novo espaço, ligue-se ao Wi-Fi e reinicie os HoloLens.
- Para ver se o espaço correto está ativo, ou para carregar manualmente um espaço, vá para Os Espaços do Sistema **de Definições**  >    >  .
- Se o espaço correto estiver carregado e ainda tiver problemas, o espaço pode ser corrupto. Para corrigir este problema, selecione o espaço e, em seguida, **selecione Remover**. Depois de remover o espaço, holoLens começa a mapear o seu ambiente e criar um novo espaço.

[De volta à lista](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramas desaparecem ou estão envoltos em outros hologramas ou objetos

Se te aproximares demasiado de um holograma, ele desaparecerá temporariamente &mdash; para restaurar o holograma, afastando-se dele. Além disso, se tiver colocado vários hologramas juntos, alguns podem desaparecer. Tente remover alguns.

Os hologramas também podem ser bloqueados ou envoltos por outros hologramas ou por objetos como paredes. Se isto acontecer, experimente uma das seguintes correções:

- Se o holograma estiver envolto noutro holograma, mova o holograma envolto para outro local. Para isso, **selecione Ajuste,** toque e segure para posicioná-lo.
- Se o holograma estiver envolto numa parede, selecione **Ajuste,** em seguida, caminhe em direção à parede até que o holograma apareça. Toque e segure, em seguida, puxe o holograma para a frente e para fora da parede.
- Se não conseguir mover o holograma usando gestos, use a sua voz para removê-lo. Olhe para o holograma, e depois diga "Remova". Em seguida, reabra o holograma e coloque-o em um novo local.

[De volta à lista](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramas estão aparecendo do outro lado de uma parede

Se estiver muito perto de uma parede, ou se holoLens ainda não digitalizou a parede, você pode ver hologramas que estão na sala ao lado. Para digitalizar a parede, fique entre um e três metros da parede e olhe para ela.

Um objeto preto ou refletor (por exemplo, um sofá preto ou um frigorífico de aço inoxidável) perto da parede pode causar problemas quando holoLens tenta digitalizar a parede. Se houver tal objeto, verifique o outro lado da parede.

[De volta à lista](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Depois de colocar um holograma na parede, parece flutuar

Um holograma que se coloca numa parede normalmente parece estar a cerca de 2,5 cm da parede. Se parecer estar mais longe, experimente uma ou mais das seguintes correções:

- Quando colocar um holograma numa parede, fique entre um e três metros da parede e fique de frente para a parede.
- Toque de ar na parede para revelar o gráfico da malha de mapeamento. Certifique-se de que a malha está alinhada com a parede. Se não, retire o holograma, volte a escanear a parede e tente de novo.
- Se o problema persistir, execute a aplicação calibração. Encontrará-o em **Sistemas**  >    >  **de Definições Utilities**.

[De volta à lista](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>As aplicações parecem muito próximas depois de movê-las

Tente passear e olhar para a área onde está colocando a app para que holoLens digitalize a área de diferentes ângulos. [A limpeza da viseira do dispositivo](hololens1-hardware.md#care-and-cleaning) também pode ajudar.

[De volta à lista](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Problemas de reporte com hologramas instáveis ou inexatos
 
1. Por favor, grave e um [vídeo de Captura](holographic-photos-and-videos.md#capture-a-mixed-reality-video) de Realidade Mista da edição. Este vídeo pode ser posteriormente carregado através do Feedback Hub como um ficheiro anexo.  
1. Ativar a telemetria completa através da aplicação **Definições** -> o feedback & **de diagnóstico** de privacidade e em  ->   **dados de diagnóstico opcionais** certifique-se de que o toggle está definido para **On**
1. Obtenha as mais recentes correções de escala e estabilidade do holograma atualizando o mais recente [SISTEMA Holográfico do Windows (20H2 ou superior)](hololens-release-notes.md#windows-holographic-version-20h2). Após a atualização, execute o seguinte:
    1. Remova todos os Hologramas através da aplicação **Settings** -> **Hologramas do Sistema**  ->   ->, em seguida, selecione Remover todos **os hologramas** e começar com um mapa novo.
    1. Crie um novo mapa do seu espaço usando os HoloLens e andando pelo seu quarto e olhando para todas as áreas e superfícies do espaço. Faça isto por 2-3 minutos.
    1. Executar a calibração IPD. Ir para **Configurações**  >  **Sistema**  >  **Utilities**. Em **Calibração,** selecione **Calibração Aberta**.
    1. Re-teste o cenário e ver se ainda persiste.
1. Se a atualização não corrigir o problema, por favor, preencha um [problema do Feedback Hub](hololens-feedback.md). Depois de ter preenchido o feedback, pode utilizar o botão **Partilhar,** para criar um link fácil de partilhar que pode ser enviado ao contactar o suporte.

[De volta à lista](#list)