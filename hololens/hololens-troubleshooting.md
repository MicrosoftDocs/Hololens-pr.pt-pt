---
title: Resolução de problemas
description: Mantenha-se atualizado sobre as soluções mais comuns para problemas de dispositivo HoloLens e técnicas de resolução de problemas.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemas, bug, resolução de problemas, correção, ajuda, suporte, HoloLens
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378586"
---
# <a name="troubleshoot-common-issues"></a>Resolver problemas comuns

Este artigo descreve como resolver vários problemas comuns do HoloLens.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>Os meus HoloLens não respondem ou não vão começar.

Se os seus HoloLens não começarem:

- Se os LEDs ao lado do botão de alimentação não se acenderem ou apenas um LED piscar brevemente, poderá ter de [carregar os HoloLens.](hololens-recovery.md#charge-the-device)
- Se os LEDs acenderem quando premir o botão de alimentação, mas não conseguir ver nada nos visores, [pré-aja um reset duro do dispositivo](hololens-recovery.md#hard-reset-procedure).

Se os seus HoloLens ficar congelados ou sem resposta:

- Desligue os HoloLens premindo o botão de alimentação até que os cinco LEDs se desliguem, ou durante 15 segundos se os LEDs não responderem. Para ligar os HoloLens, prima novamente o botão de alimentação.

Se estes passos não funcionarem, pode tentar [recuperar o dispositivo HoloLens 2](hololens-recovery.md) ou [HoloLens (1ª geração).](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>Hologramas não parecem bons.

Se os seus hologramas estiverem instáveis, nervosos ou não parecerem bem, tente:

- Limpeza da viseira do dispositivo e barra de sensor na parte da frente dos HoloLens.
- Aumentando a luz no seu quarto.
- Andando e olhando para o seu ambiente para que hololens possam digitalizá-los mais completamente.
- Calibrando os HoloLens para os seus olhos. Ir para **Configurações**  >  **Sistema**  >  **Utilities**. Em **Calibração,** selecione **Calibração Aberta**.
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Reportar problemas onde hologramas são instáveis ou não parecem certos
 
1. Por favor, grave e um [vídeo de Captura](holographic-photos-and-videos.md#capture-a-mixed-reality-video) de Realidade Mista da edição. Este vídeo pode ser posteriormente carregado através do Feedback Hub como um ficheiro anexo.  
1. Ativar a telemetria completa através da aplicação **Definições** -> o feedback & **de diagnóstico** de privacidade e em  ->   **dados de diagnóstico opcionais** certifique-se de que o toggle está definido para **On**
1. Obtenha as mais recentes correções de escala e estabilidade do holograma atualizando o mais recente [SISTEMA Holográfico do Windows (20H2 ou superior)](hololens-release-notes.md#windows-holographic-version-20h2). Após a atualização, execute o seguinte:
    1. Remova todos os Hologramas através da aplicação **Settings** -> **Hologramas do Sistema**  ->   ->, em seguida, selecione Remover todos **os hologramas** e começar com um mapa novo.
    1. Crie um novo mapa do seu espaço usando os HoloLens e andando pelo seu quarto e olhando para todas as áreas e superfícies do espaço. Faça isto por 2-3 minutos.
    1. Executar a calibração IPD. Ir para **Configurações**  >  **Sistema**  >  **Utilities**. Em **Calibração,** selecione **Calibração Aberta**.
    1. Re-teste o cenário e ver se ainda persiste.
1. Se a atualização não corrigir o problema, por favor, preencha um [problema do Feedback Hub](hololens-feedback.md). Depois de ter preenchido o feedback, pode utilizar o botão **Partilhar,** para criar um link fácil de partilhar que pode ser enviado ao contactar o suporte.

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens não responde à entrada da mão

Para garantir que os HoloLens possam ver as suas mãos, precisa mantê-las na moldura do gesto.  O Mixed Reality Home fornece feedback que lhe permite saber quando as suas mãos são rastreadas.  O feedback é diferente em diferentes versões de HoloLens:
- Em HoloLens (1º gênero), o cursor de olhar muda de um ponto para um anel
- No HoloLens 2, um cursor de ponta dos dedos aparece quando a sua mão está perto de uma ardósia, e um raio de mão aparece quando as ardósias estão mais longe

Muitas aplicações imersivas seguem padrões de entrada semelhantes ao Mixed Reality Home.  Saiba mais sobre a utilização da entrada manual nos [HoloLens (1º gênero)](hololens1-basic-usage.md#use-hololens-with-your-hands) e [holoLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se estiver a usar luvas, note que alguns tipos de luvas não funcionam com o rastreio da mão.  Um exemplo comum são as luvas de borracha pretas, que tendem a absorver a luz infravermelha e não são captadas pela câmara de profundidade.  Se o seu trabalho envolve luvas de borracha, recomendamos experimentar uma cor mais clara, como azul ou cinza.  Outro exemplo são as grandes luvas largas, que tendem a obscurecer a forma da sua mão. Recomendamos a utilização de luvas que sejam o mais adequadas possível para obter os melhores resultados.

Se a sua viseira tiver impressões digitais ou manchas, utilize o pano de limpeza de microfibras que veio com os HoloLens para limpar suavemente a viseira.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens não responde aos meus comandos de voz

Se cortana não está respondendo aos seus comandos de voz, certifique-se de que Cortana está ligada. Na lista de todas as aplicações, selecione **Definições** de Caderno do Menu Cortana  >    >    >   para escoar alterações. Para saber mais sobre o que pode dizer, consulte [Use a sua voz com HoloLens.](hololens-cortana.md)

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Não posso colocar hologramas ou ver hologramas que coloquei anteriormente.

Se o HoloLens não conseguir mapear ou carregar o seu espaço, ele entra no modo Limited e não poderá colocar hologramas ou ver hologramas que colocou. Seguem-se algumas soluções que pode experimentar:

- Certifique-se de que há luz suficiente no seu ambiente para que os HoloLens possam ver e mapear o espaço.
- Certifique-se de que está ligado a uma rede Wi-Fi. Se não estiver ligado ao Wi-Fi, os HoloLens não conseguem identificar e carregar um espaço conhecido.
- Se precisar de criar um novo espaço, ligue-se ao Wi-Fi e reinicie os HoloLens.
- Para ver se o espaço correto está ativo, ou para carregar manualmente um espaço, vá para Os Espaços do Sistema **de Definições**  >    >  .
- Se o espaço correto estiver carregado e ainda tiver problemas, o espaço pode ser corrupto. Para corrigir este problema, selecione o espaço e, em seguida, **selecione Remover**. Depois de remover o espaço, holoLens começa a mapear o seu ambiente e criar um novo espaço.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>Os meus HoloLens não conseguem dizer em que espaço estou.

Se os hololens não conseguirem identificar e carregar o espaço em que se encontre automaticamente, verifique os seguintes fatores:

- Certifique-se de que está ligado a Wi-Fi
- Certifique-se de que há muita luz no quarto.
- Certifique-se de que não houve grandes alterações nos arredores.

Também pode carregar um espaço manualmente ou gerir os seus espaços indo para Os Espaços do Sistema **de Definições.**  >    >  

## <a name="im-getting-a-low-disk-space-error"></a>Estou a receber um erro de "espaço em disco baixo".

Você precisará libertar algum espaço de armazenamento fazendo um ou mais dos seguintes:

- Apague alguns espaços não-reutilizados. Vá aos Espaços do Sistema **de Definições,**  >    >  selecione um espaço que já não necessita e, em seguida, selecione **Remover**.
- Retire alguns dos hologramas que colocou.
- Elimine algumas fotos e vídeos da aplicação Fotos.
- Desinstale algumas aplicações dos seus HoloLens. Na lista **de aplicações Desinstalar,** toque e mantenha a aplicação que pretende desinstalar e, em seguida, selecione **Desinstalar**.

## <a name="my-hololens-cant-create-a-new-space"></a>Os meus HoloLens não podem criar um novo espaço

O problema mais provável é que estejas a ficar sem espaço de armazenamento. Experimente uma das [dicas anteriores](#im-getting-a-low-disk-space-error) para libertar algum espaço em disco.

## <a name="the-hololens-emulator-isnt-working"></a>O emulador HoloLens não está a funcionar.

A informação sobre o emulador HoloLens está localizada na nossa documentação do desenvolvedor.  Leia mais sobre [a resolução de problemas do emulador HoloLens.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
