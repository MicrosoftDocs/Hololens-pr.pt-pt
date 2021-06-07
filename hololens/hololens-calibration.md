---
title: Melhorar a qualidade visual e o conforto
description: Aprenda a calibrar a sua distância interpupilar (IPD) para melhorar a qualidade dos seus visuais nos dispositivos HoloLens.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: calibração, conforto, visuais, qualidade, ipd, HoloLens, Windows Mixed Reality, auscultadores VR
ms.openlocfilehash: e975e2ccd978d4ec6b5331af0ae566af116711c5
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379843"
---
# <a name="improve-visual-quality-and-comfort"></a>Melhorar a qualidade visual e o conforto

HoloLens 2 e HoloLens (1ª geração) funcionam melhor quando estão calibrados para os seus olhos únicos.

Embora ambos os dispositivos precisem de calibrar para obter a melhor experiência de visualização de hologramas, eles usam diferentes tecnologias e técnicas de calibração.  Salte para a [calibração HoloLens 2](#calibrating-your-hololens-2) ou [para a calibração HoloLens (1ª gen).](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>Calibrar os hololens 2

HoloLens 2 usa tecnologia de rastreio visual para melhorar a sua experiência de ver e interagir com o ambiente virtual. Calibrar os HoloLens 2 garante que consegue rastrear com precisão os seus olhos (e os olhos de qualquer outra pessoa que utilize o dispositivo). Também ajuda no conforto do utilizador, alinhamento holograma e rastreio de mãos. Após a calibração, os hologramas aparecerão corretamente, mesmo quando a viseira se desloca na sua cabeça.

O HoloLens 2 solicita ao utilizador que calibra o dispositivo nas seguintes circunstâncias:

- O utilizador está a usar o dispositivo pela primeira vez
- O utilizador anteriormente optou por não fazer o processo de calibração
- O processo de calibração não teve sucesso na última vez que o utilizador usou o dispositivo
- O utilizador apagou os seus perfis de calibração
- O dispositivo é retirado e volta a colocar e qualquer uma das circunstâncias acima aplicável 


![Pedido de calibração para se ajustar aos olhos.](./images/07-et-adjust-for-your-eyes.png)

Durante este processo, você vai olhar para um conjunto de alvos (gemas). Tudo bem se piscar durante a calibração, mas tente manter-se focado nas joias em vez de outros objetos na sala.  Focar-se nas joias permite que hololensaa a sua posição ocular para tornar o seu mundo holográfico.

![Aviso de calibração a dizer ao utilizador para manter a cabeça imóvel e seguir pontos com os olhos.](./images/07-et-hold-head-still.png)

![Pronta de calibração com exemplo de gema.](./images/08-et-gems.png)

![Ajuste rápido de calibração.](./images/09-et-adjusting.png)

Se a calibração foi bem sucedida, verá um ecrã de sucesso.  Caso contrário, leia mais sobre [o diagnóstico de falhas de calibração](#troubleshooting-hololens-2-calibration).

![Calibração pronta sucesso.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Calibração ao partilhar um dispositivo ou sessão

Vários utilizadores podem partilhar um dispositivo HoloLens 2, sem necessidade de cada pessoa passar pela configuração do dispositivo. Quando um novo utilizador coloca o dispositivo na cabeça pela primeira vez, o HoloLens 2 solicita automaticamente ao utilizador que calibra os visuais. Quando um utilizador que já calibrado visualiza o dispositivo coloca o dispositivo na cabeça, o visor ajusta-se perfeitamente para a qualidade e uma experiência de visualização confortável.  

### <a name="manually-starting-the-calibration-process"></a>Iniciar manualmente o processo de calibração

1. Utilize o gesto inicial para abrir o menu [ **Iniciar**](hololens2-basic-usage.md#start-gesture).
1. Se a aplicação Definições não estiver fixada para **iniciar**, selecione **Todas as Aplicações**.
1. Selecione **Definições** e, em seguida, selecione **Calibração do Olho**  >  **de Calibração** do Sistema Executar  >    >  **calibração ocular**.

   ![A aplicação Definições, mostrando a opção de calibração para os olhos Run](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Suporte à posição dos olhos automáticos

Nos HoloLens 2, as posições oculares permitem um posicionamento preciso do holograma, uma experiência de visualização confortável e uma melhor qualidade de exibição. As posições oculares são calculadas internamente como parte da computação de rastreio ocular. No entanto, isto requer que cada utilizador passe por uma calibração de rastreio visual, mesmo quando a experiência pode não necessitar de uma entrada de olhares oculares.

**A Auto Eye Position (AEP)** permite estes cenários com uma forma livre de interação de calcular posições oculares para o utilizador. A Auto Eye Position começa a funcionar automaticamente em segundo plano a partir do momento em que o utilizador coloca o dispositivo. Se o utilizador não tiver uma calibração prévia de rastreio ocular, a Auto Eye Position começará a fornecer as posições oculares do utilizador ao sistema de visualização após um tempo de processamento de 20 a 30 segundos. Os dados do utilizador não são persistidos no dispositivo e este processo é repetido se o utilizador descolar e voltar a colocar o dispositivo ou se o dispositivo reiniciar ou acordar do sono.

Existem algumas alterações de comportamento do sistema com a função Auto Eye Position quando um utilizador não calibrado coloca no dispositivo. Neste contexto, um utilizador não calibrado refere-se a alguém que não passou pelo processo de calibração de rastreio ocular no dispositivo anteriormente.

| Aplicação Ativa | Comportamento Anterior | Comportamento do Windows Holographic, versão 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| App não-gaze habilitada ou Concha Holográfica |É apresentado um diálogo de solicitação de calibração de rastreio ocular. | Não é apresentada nenhuma solicitação. |
| App ativada pelo olhar | É apresentado um diálogo de solicitação de calibração de rastreio ocular. | A indicação de calibração do rastreio dos olhos só é apresentada quando a aplicação acede ao fluxo de olhares. |

Se o utilizador transitar de uma aplicação não ativada para uma que aceda aos dados do olhar, o aviso de calibração será apresentado. 

Todos os outros comportamentos do sistema serão semelhantes aos de quando o utilizador atual não tem uma calibração ativa de rastreio de olhos. Por exemplo, o gesto de Início com uma mão não será ativado. Não haverá alteração da Experiência Out-Of-Box para a configuração inicial.

Para experiências que requerem dados de olhares oculares ou posicionamento preciso do holograma, recomendamos que os utilizadores não calibrados para executar a calibração de rastreio de olhos. É acessível a partir da pronta de calibração de rastreio ocular ou lançando a aplicação Definições a partir do menu inicial e, em seguida, selecionando **System > Calibration > Calibração ocular > Calibração ocular Run**.

#### <a name="deferred-calibration-prompt"></a>Pedido de calibração diferido

Com a posição auto-olho, o diálogo de calibração de rastreio de olhos é adiado até que uma aplicação solicite dados de Eye Gaze. Isto garante que não há nenhuma solicitação para o utilizador quando a aplicação ativa não requer olhar. Se a aplicação necessitar de dados de gaze e o utilizador atual não estiver calibrado, o utilizador é apresentado com uma solicitação de calibração. Este comportamento pode ser usado para exibir uma solicitação de calibração de rastreio ocular num momento adequado para a experiência. Este método é recomendado pelas seguintes razões

1.  O diálogo de calibração de calibração de rastreio de olhos fornece ao utilizador detalhes sobre o porquê do rastreio ocular ser necessário.
2.  Apresenta ao utilizador uma forma de recusar ter os olhos calibrados.

Se o utilizador optar por lançar a Calibração de Rastreio de Olhos, o foco deve voltar à aplicação original após a conclusão da calibração. 

### <a name="troubleshooting-hololens-2-calibration"></a>Resolução de problemas Da calibração hololens 2

A calibração deve funcionar para a maioria das pessoas, mas há casos em que a calibração falha.
  
Algumas razões potenciais para a falha de calibração incluem:

- Distrair-se e não seguir os objetivos de calibração
- Visor de dispositivo sujo ou riscado não posicionado corretamente
- Óculos sujos ou riscados
- Certos tipos de lentes de contacto e óculos (lentes de contacto coloridas, algumas lentes de contacto toric, óculos de bloqueio de INFRAVERMELHOS, alguns óculos de prescrição elevada, óculos de sol ou similares)
- Maquilhagem mais pronunciada e algumas extensões de pestanas
- Cabelo ou molduras de vidro grosso se estiverem bloqueando o dispositivo de ver os seus olhos
- Certas fisiologia ocular, condições oculares ou cirurgia ocular, tais como olhos estreitos, pestanas longas, amblyopia, nystagmus, alguns casos de LASIK ou outras cirurgias oculares

Se a calibração não for bem sucedida, tente:

- Limpeza da viseira do dispositivo
- Limpando os óculos
- Empurrando a viseira do dispositivo o mais próximo possível dos olhos
- Movendo objetos na sua viseira para fora do caminho (como o cabelo)
- Acendendo uma luz no seu quarto ou saindo da luz direta do sol

Se seguir todas as diretrizes e a calibração continuar a falhar, pode desativar a indicação de calibração em Definições. Informe-nos também ao arquivar feedback no [Feedback Hub.](hololens-feedback.md)

Consulte também informações relacionadas para [a cor da imagem ou resolução de problemas de luminosidade.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

A definição de IPD não é aplicável para hololens 2, uma vez que as posições oculares são calculadas pelo sistema. 

### <a name="calibration-data-and-security"></a>Dados de calibração e segurança

As informações de calibração são armazenadas localmente no dispositivo e não estão associadas a qualquer informação da conta. Não há registo de quem usou o dispositivo sem calibração. Isto significa que os novos utilizadores serão solicitados a calibrar os visuais quando utilizarem o dispositivo pela primeira vez, e os utilizadores que optaram por não calibrar previamente ou se a calibração não foi bem sucedida.

O dispositivo pode armazenar localmente até 50 perfis de calibração. Depois de alcançado este número, o dispositivo elimina automaticamente o perfil não reutilizado mais antigo.

As informações de calibração podem sempre ser **eliminadas** do dispositivo no  >    >  **localizador** Privacy Eye .  

### <a name="disable-calibration"></a>Desativar a calibração

Também pode desativar a indicação de calibração seguindo estes passos:

1. Selecione **calibração**  >  **do sistema**  >  **de definições**.
1. Desligue **Quando uma nova pessoa utilizar este HoloLens, peça automaticamente para executar a calibração dos olhos**.

> [!IMPORTANT]
> Esta definição pode afetar negativamente a qualidade e conforto do holograma.  Quando desliga esta definição, as funcionalidades que dependem do rastreio dos olhos (como o scrolling de texto) já não funcionam em aplicações imersivas.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 tecnologia de rastreio de olhos

O dispositivo utiliza a sua tecnologia de rastreio de olhos para melhorar a qualidade do ecrã e para garantir que todos os hologramas estão posicionados com precisão e confortável para ver em 3D. Como utiliza os olhos como marcos históricos, o dispositivo pode ajustar-se a cada utilizador e afinar os seus visuais à medida que os auscultadores se deslocam ligeiramente ao longo do uso.  Todos os ajustes acontecem na mosca sem necessidade de afinação manual.
> [!NOTE]
> A definição do IPD não é aplicável aos Hololens 2, uma vez que as posições oculares são calculadas pelo sistema.

As aplicações hololens usam rastreio de olhos para rastrear onde você está procurando em tempo real. Esta é a principal capacidade que os desenvolvedores podem usar para permitir um novo nível de contexto, compreensão humana e interações dentro da experiência holográfica. Os desenvolvedores não precisam de fazer nada para usar esta capacidade.

## <a name="calibrating-your-hololens-1st-gen"></a>Calibrar os hololens (1ª geração)

HoloLens (1º gênero) ajusta o ecrã do holograma de acordo com a [distância interpupilar](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Se o IPD não estiver correto, os hologramas podem parecer instáveis ou a uma distância incorreta. Pode melhorar a qualidade dos seus visuais calibrando o dispositivo à sua distância interpupilar (IPD).

Quando configuras o teu dispositivo HoloLens (1ª geração), ele pede para calibrar os teus visuais depois da Cortana se apresentar. Recomenda-se que complete o passo de calibração durante esta fase de configuração. Seja como for, podes ignorá-lo esperando até que cortana te indique e depois diga "Salta".

Durante o processo de calibração, o HoloLens pede-lhe para alinhar o dedo com uma série de seis alvos por olho. HoloLens usa este processo para definir o IPD corretamente para os seus olhos.

![Tela de alinhamento de dedos IPD no segundo passo](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Iniciar manualmente o processo de calibração

Se precisar de atualizar a calibração ou se um novo utilizador precisar de a ajustar, pode executar manualmente a aplicação calibração a qualquer momento. A aplicação calibração é instalada por predefinição. Pode aceder-lhe utilizando o menu **Iniciar** ou a aplicação Definições.

Para utilizar o menu **Iniciar** para executar a aplicação calibração, siga estes passos:

1. Use o gesto [de floração](hololens1-basic-usage.md) para abrir o menu **Iniciar.**
1. Para ver todas as aplicações, selecione **+** .
1. Selecione **calibração**.

![Aceder à aplicação de calibração a partir da concha](./images/calibration-shell.png)

![A aplicação de calibração exibida como um Cubo Vivo após ser lançada](./images/calibration-livecube-200px.png)

Para utilizar a aplicação Definições para executar a app calibração, siga estes passos:

1. Use o gesto [de floração](hololens1-basic-usage.md) para abrir o menu **Iniciar.**
1. Se **as Definições** não estiverem presas ao **Arranque,** selecione **+** para ver todas as aplicações.
1. Selecione **Definições**.
1. Selecione   >  **System Utilities**  >  **Open Calibration**.

![Lançamento da app de calibração a partir da aplicação de definições](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Auscultadores imersivos

Alguns auscultadores imersivos proporcionam a capacidade de personalizar a definição ipd. Para alterar o IPD para os seus auscultadores, abra a aplicação Definições e selecione o ecrã de auscultadores **de realidade mista**  >  e, em seguida, mova o controlo do slider. Verá as mudanças em tempo real nos auscultadores. Se conhece o seu IPD, talvez de uma visita ao optometrista, também pode inscrevê-lo diretamente.

Também pode ajustar esta definição no seu PC selecionando **Definições**  >  **Ambientes Imagem de realidade Mista** Auricular  >  **.**

Se o auricular não suportar a personalização do IPD, esta definição será desativada.
