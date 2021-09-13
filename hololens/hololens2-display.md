---
title: HoloLens 2 Display Troubleshooting
description: Expectativas para HoloLens 2 exposições. Orientação para configurar os ecrãs para uma melhor qualidade de imagem.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: exibição, calibração, conforto, visuais, qualidade, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 38bab16d2d0d4ace5879f00c133d66b9974e4b2a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036441"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens 2 Display Troubleshooting

## <a name="overview"></a>Descrição Geral
O ecrã HoloLens 2 é uma combinação de guias de onda e projetores de luz. Os utilizadores olham através das guias de onda - as lentes dentro da viseira - quando usam o auricular. Os projetores de luz estão dentro do recinto acima da testa. HoloLens 2 utiliza luz laser para iluminar o visor.

## <a name="troubleshooting"></a>Resolução de problemas

Tome as seguintes medidas para garantir a maior qualidade visual dos hologramas apresentados nos ecrãs:

* **Aumente o brilho do visor.** Hologramas ficar melhor quando o visor está no seu nível mais brilhante. Ao usar o HoloLens, os botões de brilho estão no lado esquerdo da viseira perto do seu templo.
* **Aproxime-se dos seus olhos.** Balance a viseira para a posição mais próxima dos seus olhos.
* **Visor de turno para baixo.** Tente mover a almofada da testa para baixo, o que fará com que a viseira se aproxime mais do nariz.
* **[Executar a calibração dos olhos.](hololens-calibration.md#calibrating-your-hololens-2)** O visor utiliza a distância interpupilar (IPD) e o olhar para otimizar as imagens no visor. Se não fizer a calibração dos olhos, a qualidade da imagem pode ser pior. Para executar a calibração dos olhos, vá para **Definições**  >  Calibração do **Sistema** Executar  >    >  **calibração ocular**.
* **Executar a calibração da cor do ecrã**. No [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e em diante, pode **selecionar um perfil de cor alternativo** para o seu ecrã HoloLens 2. Isto pode ajudar as cores a parecerem mais precisas, especialmente em níveis de luminosidade de ecrã mais baixos. A calibração da cor do ecrã pode ser encontrada na aplicação **Definições,** na página **de Calibração system >.**

    > [!NOTE]
    > Uma vez que esta definição guarda um novo perfil de cores para o firmware do ecrã, é uma definição por dispositivo (e não única em cada conta de utilizador).

### <a name="how-to-use-display-color-calibration"></a>Como usar a calibração da cor do ecrã
1. Lançar a app **Definições** e navegar para **a Calibração > Do Sistema.**
1. Na **calibração da cor do Display,** selecione o botão **de calibração da cor do ecrã Run.**
1. A experiência de calibração da cor do visor será lançada e encoraja-o a certificar-se de que a sua viseira está na posição correta.
1. Depois de proceder através das caixas de diálogo de instruções, o seu visor será automaticamente diminuído para 30% de luminosidade.
    > [!TIP]
    > Se tiver dificuldades em ver a cena escurecida no seu ambiente, pode ajustar manualmente o nível de luminosidade do HoloLens 2 utilizando os botões de luminosidade no lado esquerdo do dispositivo.
1. Selecione os botões 1-6 para experimentar instantaneamente cada perfil de cor, e encontre um que fique melhor para os seus olhos (isto geralmente significa o perfil que ajuda a cena a parecer mais neutro, com o padrão em tons de cinza e a pele a parecerem esperados.)

    ![Mostrar cena de calibração de cores.](images/color-cal-ui.png)
    
6. Quando estiver satisfeito com o perfil selecionado, selecione o botão **'Saída &'**
1. Se preferir não fazer alterações, selecione o botão **'Cancelar & Saída'** e as alterações serão revertidas

> [!TIP]
> Aqui ficam algumas dicas úteis a ter em mente durante a utilização da definição de calibração da cor do ecrã:
> - Pode re-executar a calibração de cor do ecrã a partir de Definições sempre que quiser
> - Se alguém no dispositivo tiver usado previamente a definição para alterar perfis de cor, a data/hora da alteração mais recente será refletida na página Definições
> - Quando voltar a executar a calibração de cores do ecrã, o perfil de cor que foi previamente guardado será realçado e o Perfil 0 não aparecerá (uma vez que o Perfil 0 representa o perfil de cor original do visor)
> - Se quiser reverter para o perfil de cor original do visor, pode fazê-lo a partir da página Definições (ver como redefinir o perfil de [cor)](#how-to-reset-color-profile)

### <a name="how-to-reset-color-profile"></a>Como redefinir o perfil de cor

Se estiver insatisfeito com o perfil de cor personalizado guardado para o seu HoloLens 2, pode restaurar o perfil de cor original do dispositivo:
1. Lançar a app **Definições** e navegar para **a Calibração > Do Sistema.**
1. Na **calibração da cor do Display,** selecione o botão reset para o **perfil de cores predefinido.**
1. Quando a caixa de diálogo abrir, selecione **Reiniciar** se estiver pronto para reiniciar HoloLens 2 e aplicar as suas alterações.

### <a name="top-display-color-calibration-known-issues"></a>Principais problemas de calibração de cores de ecrã

- Na página Definições, a cadeia de estado que lhe diz quando o perfil de cor foi alterado ficará desatualizada até recarregar a página de Definições 
    - **Solução alternativa**: Selecione outra página Definições e, em seguida, reescoria a página de Calibração.
- Se o seu HoloLens 2 adormecer enquanto executa a calibração da cor do ecrã, ele retomará mais tarde na casa da realidade mista e o seu nível de luminosidade do ecrã continuará a ser diminuído.
- Pode ter de tentar premir os botões de luminosidade no lado esquerdo do dispositivo para cima/para baixo algumas vezes antes de funcionarem como esperado.
- A localização não está completa para todos os mercados

## <a name="faq"></a>FAQ

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Quais são os padrões que ocasionalmente piscam nos cantos inferiores do visor?

Ocasionalmente, o seu HoloLens 2 mostrará diferentes padrões nos cantos inferiores esquerdo e direito do visor. Exemplos são mostrados abaixo (GIFs animados). Este padrão faz parte do funcionamento normal do seu dispositivo HoloLens 2 para calibrar o ecrã para uma experiência ótima.

![Padrão bifásico.](./images/DAT-Biphase-Fiducial.gif) ![Padrão GEO](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Por que sou incapaz de tirar uma fotografia exata do meu HoloLens 2?

O ecrã HoloLens 2 foi concebido para ser visto pelo olho humano. O dispositivo tem um sistema de correção de cores ativo que se adapta aos olhos de um utilizador. Em comparação com o olho humano, as câmaras vêem ambientes de forma diferente e abaixo são alguns fatores que podem afetar qualquer inconsistência entre o que uma câmara captura e o que um utilizador vê.

* **Posição dos olhos.** O visor HoloLens 2 foi concebido especificamente para a posição ocular do utilizador. O HoloLens 2 emprega tecnologia de rastreio ocular para se adaptar à posição ocular do utilizador. Uma câmara que é mal posicionada por alguns milímetros pode levar a distorções de imagem. O posicionamento preciso com uma câmara é difícil e precisa de corresponder à localização exata e ao alívio ocular para o qual o dispositivo está a executar a correção de cores.
* **Movimento dos olhos.** O visor adapta-se ao movimento do olho de um utilizador para ajustar as cores. O que é mostrado no visor pode diferir dependendo se o utilizador estiver a olhar para o centro, a borda ou o canto do visor. Uma única captura de imagem só poderia, na melhor das hipóteses, mostrar como é o ecrã para o eixo que corresponde à direção de um olhar atento.
* **Visualização binocular.** O ecrã HoloLens 2 foi concebido para ser visto com ambos os olhos. O cérebro adapta-se a ver duas imagens e fundi-las juntas. As imagens de apenas um ecrã ignoram as informações do outro ecrã.
* **Tempo de exposição à câmara.** O tempo de exposição da câmara tem de ser um múltiplo exato de 1/120 de segundo. A taxa de fotogramas de exibição HoloLens é de 120 Hz. Devido à forma como o HoloLens 2 desenha imagens, capturar uma única moldura também não é suficiente para corresponder à experiência visual de um humano. Ao mesmo tempo, se o dispositivo se mover de todo — mesmo micromoovamentos — o sistema reprojeta a imagem no visor para estabilizar hologramas. Capturar vários quadros, mantendo a HoloLens de se mover, requer geralmente uma instalação laboratorial.
* **Tamanho da abertura da câmara.** O tamanho da abertura da câmara deve ser de pelo menos 3 mm para capturar uma imagem precisa. Câmaras de telemóvel com pequenas aberturas integram a luz de uma área menor do que o olho humano. O dispositivo aplica correção de cor para padrões observados por aberturas maiores. Com pequenas aberturas, os padrões de uniformidade são mais nítidos e permanecem visíveis apesar das correções de cor aplicadas pelo sistema.
* **Aluno de entrada da câmara.** A pupila de entrada da câmara deve ter pelo menos 3 mm de diâmetro para capturar uma imagem precisa. Caso contrário, a câmara captura alguns padrões de alta frequência não visíveis ao olho. A posição do aluno de entrada tem de estar em frente à câmara e posicionada à distância de alívio ocular para evitar a introdução de aberrações e outras variações à imagem capturada.
* **Posição da câmara.** As câmaras que satisfazem os requisitos para visualizar o ecrã HoloLens 2 são maiores e é difícil posicionar a câmara suficientemente perto do ecrã HoloLens 2 para observar a imagem corrigida de cor. Se a câmara estiver no local errado, a correção de cor pode afetar negativamente a captura do visor HoloLens 2.
* **Correção de imagem.** Câmaras digitais típicas e câmaras de smartphone aplicam uma curva de reprodução de tom (TRC) que aumenta o contraste e a cor para proporcionar um resultado snappier. Quando aplicada a um visor de HoloLens 2, esta curva de tom amplifica as não uniformidades.

Tudo dito, ainda é possível para câmaras industriais especializadas capturar imagens representativas do ecrã HoloLens 2. Infelizmente, as câmaras de smartphone, consumidor e profissional não irão capturar imagens que correspondam ao que um utilizador vê no HoloLens 2.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>O que faz a calibração dos olhos para mostrar a qualidade da imagem?

O ecrã HoloLens 2 corrige ativamente as imagens com base na posição dos olhos do utilizador. [A calibração](hololens-calibration.md) ocular fornece duas entradas importantes: (1) a distância interpupilar do utilizador (IPD) e (2) a direção que cada olho está a olhar. Sem calibração ocular, o sistema falha numa posição nominal dos olhos sem movimento ocular. A diferença entre a correção ativa da cor contra nenhuma correção depende da fisiologia do próprio utilizador. Por exemplo, os utilizadores que tenham o mesmo IPD que o padrão do sistema verão menos melhorias na correção de cores. Embora os utilizadores que tenham um IPD muito mais estreito ou mais largo do que o padrão do sistema verão mais alterações na imagem do ecrã.

Nota: uma nova funcionalidade na [versão holográfica 20H2 Windows](hololens-release-notes.md#windows-holographic-version-20h2) começará [a detetar automaticamente a posição ocular](hololens-calibration.md#auto-eye-position-support). 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Quais são as diferenças de exibição entre HoloLens (1ª geração) e HoloLens 2?

Entre os principais pedidos que os clientes deram à Microsoft depois de experimentarem HoloLens 1 foi (1) aumentar o campo de visão e (2) aumentar o brilho. Os desenvolvimentos tecnológicos permitiram à Microsoft produzir guias de ondas que duplicaram a área do campo de visão e produziram projetores de luz com um ecrã que é até três vezes mais brilhante. O hardware define a linha de base para um trio de trocas para a qualidade da imagem do ecrã: (1) campo de visão, (2) brilho e (3) uniformidade de cores. O avanço contínuo da tecnologia permite melhorias em todas as áreas sem sacrificar outra área. Entretanto, a tecnologia existente estabelece os limites disponíveis para estas compensações.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Que melhorias estão a chegar que irão melhorar HoloLens qualidade de imagem 2?

Embora tenhamos muitas investigações em curso para melhorar a qualidade da imagem, espera-se que as seguintes áreas cheguem nas próximas atualizações:

* **Posição automática dos olhos.** Esta função permitirá que os procedimentos de calibração ocular sejam realizados em segundo plano. Os utilizadores deixarão de precisar de executar a calibração ocular para que a correção de cor ativa funcione. Em vez disso, só vai funcionar.
* **Melhorias na calibração da cor.** Esta atualização foca-se nos valores de cores de cores mais escuras (por exemplo, cinza escuro). Neste momento, as cores mais fracas captam um tom vermelho. Este problema também acontece à medida que todo o ecrã é escurecido - todo o ecrã capta cores vermelhas. Esta questão é o resultado de muita atividade no canal de cores vermelhas para estas cores mais escuras. Caracterizámos as curvas de iluminação a laser nestas cores mais fracas e estamos a trabalhar para oferecer um procedimento de calibração do utilizador. O resultado será mais precisão de cor em todo o espectro de brilho. Não mudará a aparência de fundos brancos com plena luminosidade. Continuamos a aconselhar o uso de padrões de design de modo escuro em apps.
* **Modo de leitura.** É possível que os desenvolvedores de aplicações troquem o campo de visão do ecrã para alcançar uma resolução angular mais elevada. Os desenvolvedores de aplicações podem sobrepor-se à matriz de projeção para que o conteúdo seja renderizado na resolução de desenho do visor. Esta característica resulta numa redução de 30% no campo de visão e num aumento correspondente da resolução angular. Estão em curso os trabalhos para introduzir esta capacidade no [Conjunto de Ferramentas de Realidade Mista.](https://github.com/Microsoft/MixedRealityToolkit-Unity) Quando disponível, o modo de leitura funcionará em qualquer HoloLens 2 OS — não depende de uma atualização de SO.

As atualizações do sistema operativo são entregues automaticamente. Também pode testar lançamentos antecipados de melhoria de software através do programa de pré-visualização insider.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Que orientação está disponível para os desenvolvedores aplicarem princípios de design de modo escuro?

Os utilizadores terão a melhor experiência ao evitar fundos brancos. O modo escuro é um princípio de design usado por apps para usar fundos de cor preta ou escura. As definições do sistema estão padrão para o modo escuro e podem ser ajustadas **indo** para Definições  >  **System**  >  **Color**.

Os desenvolvedores são aconselhados a seguir a orientação de design do modo escuro:

* [Diretrizes de design do desenvolvedor para exibições de HoloLens](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Tamanhos recomendados de fonte](/windows/mixed-reality/typography#recommended-font-size)

Quando um holograma requer um fundo branco, mantenha o tamanho do holograma menor do que o campo de visão completo do visor do visor. Este tamanho permite que os utilizadores coloquem o holograma no centro do ecrã.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Como se limpa uma exibição de HoloLens 2?

Utilize um pano de microfibra para limpar suavemente a viseira. Para desinfetar a viseira, use 70% de álcool isopropílico para humedecer ligeiramente um pano e, em seguida, limpe a viseira. Leia a orientação completa nas [FAQ de limpeza HoloLens 2](hololens2-maintenance.md).
