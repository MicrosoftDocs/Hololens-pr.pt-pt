---
title: Resolução de problemas do dispositivo HoloLens
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
keywords: problemas, bug, resolução de problemas, correção, ajuda, suporte, HoloLens, emulador
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924626"
---
# <a name="device-troubleshooting"></a>Resolução de problemas do dispositivo

Este artigo descreve como resolver vários problemas comuns do HoloLens.

>[!IMPORTANT]
> Antes de iniciar qualquer procedimento de resolução de problemas, certifique-se de que o seu dispositivo está carregado até **20 a 40%** da capacidade da bateria, se possível. As [luzes indicadoras](hololens2-setup.md#lights-that-indicate-the-battery-level) da bateria localizadas sob o botão de alimentação são uma forma rápida de verificar a capacidade da bateria sem iniciar sessão no dispositivo.

<a id="list"></a>

**Problemas Conhecidos**
- [Vídeo de Assistência Remota congela após 20 minutos](#remote-assist-video-freezes-after-20-minutes)
- [O login automático pede o login](#auto-login-asks-for-log-in)
- [Microsoft Edge falha no lançamento](#microsoft-edge-fails-to-launch)
- [O teclado não muda para caracteres especiais](#keyboard-doesnt-switch-to-special-characters)
- [Descarregar ficheiros bloqueados não mostra erro](#downloading-locked-files-doesnt-error)
- [Upload/download de tempos de carregamento/descarregamento de ficheiros do Portal do Dispositivo](#device-portal-file-uploaddownload-times-out)
- [Ecrã azul após desenrolar da pré-visualização insider em um dispositivo piscado com uma construção Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive não faz upload automática de imagens](#onedrive-doesnt-automatically-upload-pictures)

**Geral**
- [HoloLens não responde ou não começa](#hololens-is-unresponsive-or-wont-start)
- [Erro do "Espaço baixo do Disco"](#low-disk-space-error)
- [Falhas de calibração](#calibration-fails)
- [Não posso assinar porque o meu HoloLens foi previamente criado para outra pessoa.](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [A unidade não está a funcionar.](#unity-isnt-working)
- [O Portal do Dispositivo windows não está a funcionar corretamente](#windows-device-portal-isnt-working-correctly)
- [O Emulador HoloLens não está a funcionar.](#the-hololens-emulator-isnt-working)

**Entrada**
- [Os comandos de voz não estão a funcionar.](#voice-commands-arent-working)
- [A entrada da mão não está a funcionar.](#hand-input-isnt-working)

**Conetividade**
- [Não se liga a Wi-Fi](#cant-connect-to-wi-fi)

**Dispositivos Externos** 
- [Os dispositivos Bluetooth não estão a emparelhar](#bluetooth-devices-arent-pairing)
- [O microfone USB-C não está a funcionar.](#usb-c-microphone-isnt-working)
- [Os dispositivos listados como disponíveis em Definições não funcionam](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Vídeo de Assistência Remota congela após 20 minutos

> [!NOTE]
> Devido à gravidade desta Questão Conhecida, temos atualmente uma pausa na disponibilidade do Windows Holographic, versão 21H1. Se ainda pretender atualizar os seus dispositivos para 21H1, consulte [as instruções das nossas notas de lançamento no topo da página.](hololens-release-notes.md)

Na mais recente versão do [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), alguns utilizadores do Remote Assist experimentaram o congelamento de vídeos durante as chamadas ao longo de 20 minutos. Esta é uma **questão conhecida.**

### <a name="workarounds"></a>Soluções

#### <a name="restart-in-between-calls"></a>Reiniciar entre chamadas

Se as suas chamadas forem de mais de 20 minutos e estiver a experimentar este problema, tente reiniciar o seu dispositivo. Reiniciar o seu dispositivo entre chamadas de Assistência Remota irá refrescar o seu dispositivo e colocá-lo novamente em bom estado.

Para reiniciar rapidamente um dispositivo no [Windows Holographic, a versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) abre o menu inicial e selecione o ícone do utilizador e, em seguida, selecione **Restart**.

#### <a name="revert-to-an-older-build"></a>Reverter para uma construção mais antiga

Alguns clientes descobriram que ao reverter para uma versão anterior do SO já não experimentam este problema. Se descobriu que os seus dispositivos estão a passar por este problema, experimente estes passos:


Soluções alternativas:

- Se for viável para o seu negócio, o upload automático de câmaras é suportado nas contas da Microsoft do consumidor. Pode iniciar sôms na sua conta Microsoft para além do seu trabalho ou conta escolar (a aplicação OneDrive suporta o duplo s-in). A partir do seu perfil de conta Microsoft dentro do OneDrive pode ativar o upload automático do rolo de câmara de fundo.

- Se não conseguir utilizar com segurança uma conta de consumidor da Microsoft para o upload das suas fotos automaticamente, pode enviar manualmente fotografias para o seu trabalho ou conta escolar a partir da aplicação OneDrive. Para isso, certifique-se de que está inscrito no seu trabalho ou na conta escolar na aplicação OneDrive. Selecione o **+** botão e escolha **Upload**. Encontre as fotos ou vídeos que pretende fazer o upload navegando para **o Pictures > Camera Roll**. Selecione as fotos ou vídeos que pretende carregar e, em seguida, selecione o botão **Abrir.**


1. [Descarregue a construção para Windows Holographic, versão 20H2 – Atualização de maio de 2021](https://aka.ms/hololens2download/10.0.19041.1146)
1. Siga as [instruções de volta para uma versão oss anterior](hololens-update-hololens.md#go-back-to-a-previous-version)
1. Faça [uma pausa nas atualizações do SISTEMA no dispositivo manualmente](hololens-updates.md#pause-updates-via-device) ou para muitos dispositivos utilize o [diferimento através do MDM](hololens-updates.md#configure-an-update-deferral-policy).

[De volta à lista](#list)

## <a name="auto-login-asks-for-log-in"></a>O login automático pede o login

Um dispositivo HoloLens 2 pode ser configurado para iniciar sessão automaticamente através de **Definições**  ->  **Opções**  ->  **de início de Sessão** -> e sob a definição **necessária** do valor para **Nunca**. Alguns utilizadores poderão ser obrigados a fazer login novamente no dispositivo ao atualizarem um dispositivo com uma atualização substancialmente grande, como é o caso de uma atualização de funcionalidades. Esta é uma **questão conhecida.**

Exemplo de quando isto pode ocorrer:

- Atualização de um dispositivo do Windows Holographic, versão 2004 (Build 19041.xxxx) para Windows Holographic, versão 21H1 (Build 20346.xxxx)
- Atualizar um dispositivo para levar uma grande atualização sobre a mesma grande construção, por exemplo, Windows Holographic, versão 2004 para Windows Holographic, versão 20H2
- Atualizar um dispositivo de uma imagem de fábrica para a imagem mais recente

Isto não deve ocorrer durante:

- Dispositivos que tomam uma atualização mensal de manutenção

Trabalhar em torno de métodos:

- Métodos de entrada como PIN, Password, Íris, Autenticação Web ou teclas FIDO2.
- Se o DISPOSITIVO PIN não puder ser lembrado e não estiverem disponíveis outros métodos de autenticação, então um utilizador pode utilizar [o modo de reflashing manual](hololens-recovery.md#manual-procedure).

[De volta à lista](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge falha no lançamento

> [!NOTE]
> Este problema foi originalmente criado com a versão de envio do Microsoft Edge in-mind. Este problema pode ser resolvido no [novo Microsoft Edge](hololens-new-edge.md). Se não for, por favor, arquive o feedback.

Alguns clientes relataram um problema em que o Microsoft Edge não é lançado. Para estes clientes, o problema persiste através do reboot e não é resolvido com atualizações do Windows ou aplicações. Se estiver a experimentar este problema e tiver confirmado que o [Windows está atualizado,](hololens-updates.md#manually-check-for-updates)por favor, arquive um bug da [aplicação Feedback Hub](hololens-feedback.md) com a seguinte categoria e subcategoria: Instalar e atualizar > descarregar, instalar e configurar o Windows Update.

Não há soluções alternativas conhecidas, pois não conseguimos enraizar a questão até agora. Arquivar um bug via Feedback Hub ajudará a nossa investigação! Esta é uma **questão conhecida.**

[De volta à lista](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>O teclado não muda para caracteres especiais

Existe um problema durante o OOBE, em que uma vez que o utilizador escolheu uma conta de trabalho ou escola e está a introduzir a sua palavra-passe, tentando mudar para os caracteres especiais no teclado, tocando no botão &123 não se altera para caracteres especiais. Esta é uma **questão conhecida.**

Work-arounds:
-   Feche o teclado e reabra-o tocando no campo de texto.
-   Introduza incorretamente a sua palavra-passe. Quando o teclado for relançado da próxima vez, funcionará como esperado.
- Autenticação web, feche o teclado e selecione **Iniciar sôm nas costas de outro dispositivo**.
-   Se introduzir apenas números, um utilizador pode premir e segurar certas chaves para abrir um menu expandido.
-   Utilizando um teclado USB.

Isto não afeta:
- Utilizadores que optem por utilizar uma conta pessoal.

[De volta à lista](#list)


## <a name="downloading-locked-files-doesnt-error"></a>Descarregar ficheiros bloqueados não é erro
> ! NOTA Este é um **problema conhecido** que é corrigido na construção do Windows Insider, versão 20348.1403.


Em construções anteriores do Windows Holographic, ao tentar descarregar um ficheiro bloqueado, o resultado seria uma página de erro HTTP. Na atualização Holográfica do Windows, versão 21H1, tentar descarregar um ficheiro bloqueado resulta em nada visível - o ficheiro não descarrega e não há erro. 

[De volta à lista](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Upload/download de tempos de carregamento/descarregamento de ficheiros do Portal do Dispositivo
> ! NOTA Este é um **problema conhecido** que é corrigido na construção do Windows Insider, versão 20348.1403. Se desativou previamente a Ligação SSL como parte da solução alternativa, recomendamos vivamente que a reative.


Alguns clientes descobriram que, ao tentar carregar ou descarregar ficheiros, a operação pode parecer pendurar e, em seguida, sair ou nunca completar. Isto é separado do problema conhecido do['ficheiro bloqueado'](#downloading-locked-files-doesnt-error) -- isto afeta o Windows Holographic, versões 2004, 20H2 e 21H1 no mercado. O problema tem sido causado por um bug no tratamento do Portal do Dispositivo de determinadas solicitações, e é mais consistentemente atingido quando se utiliza https, que é o padrão. 

### <a name="workaround"></a>Solução

Esta solução, que se aplica igualmente à Wi-Fi e usbNcm, consiste em desativar a opção "necessária" em "Ligação SSL". Para tal, navegue para o Portal do Dispositivo, **Sistema** e selecione a página **Preferências.** Na secção de Segurança do **Dispositivo,** localizar **a Ligação SSL** e desativar para desativar **a necessária**.

O utilizador deve então ir para http://, não https:// (endereço IP) e funcionalidades como upload de ficheiros e descarregamento funcionarão.

[De volta à lista](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Ecrã azul após desenrolar da pré-visualização insider em um dispositivo piscado com uma construção Insider

Este é um problema que afeta os utilizadores que se encontram numa pré-visualização insider, relançou os seus HoloLens 2 com uma nova construção de pré-visualização insider e, em seguida, não foi inscrito no programa Insider. Esta é uma **questão conhecida.**

Isto não afeta:
- Utilizadores que não estão inscritos no Windows Insider 
- Insiders:
    - Se um dispositivo foi matriculado desde as construções insider foram a versão 18362.x
    - Se eles mostraram um Insider assinado 19041.x construir e ficar inscrito no programa Insider

Trabalho: 
- Evite a questão 
    - Flash uma construção não-insider. Uma das atualizações mensais regulares.
    - Fique na pré-visualização do Insider
- Reflash o dispositivo

    1. Coloque os [HoloLens 2 no modo intermitente](hololens-recovery.md) manualmente, ligando completamente sem ligar. Em seguida, enquanto segura o volume, toque no botão De alimentação.
    
    1. Ligue-se ao PC e abra o Advanced Recovery Companion.
    
    1. Flash the HoloLens 2 para a construção padrão.

[De volta à lista](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive não faz upload automática de imagens

A aplicação OneDrive para HoloLens não suporta o upload automático de câmaras para trabalho ou contas escolares. Esta é uma **questão conhecida.**

Soluções alternativas:

- Se for viável para o seu negócio, o upload automático de câmaras é suportado nas contas da Microsoft do consumidor. Pode iniciar sôms na sua conta Microsoft para além do seu trabalho ou conta escolar (a aplicação OneDrive suporta o duplo s-in). A partir do seu perfil de conta Microsoft dentro do OneDrive pode ativar o upload automático do rolo de câmara de fundo.

- Se não conseguir utilizar com segurança uma conta de consumidor da Microsoft para o upload das suas fotos automaticamente, pode enviar manualmente fotografias para o seu trabalho ou conta escolar a partir da aplicação OneDrive. Para isso, certifique-se de que está inscrito no seu trabalho ou na conta escolar na aplicação OneDrive. Selecione o **+** botão e escolha **Upload**. Encontre as fotos ou vídeos que pretende fazer o upload navegando para **o Pictures > Camera Roll**. Selecione as fotos ou vídeos que pretende carregar e, em seguida, selecione o botão **Abrir.**

[De volta à lista](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens não responde ou não começa

Se os seus HoloLens não começarem:

- Se os LEDs ao lado do botão de alimentação não se acenderem ou apenas um LED piscar brevemente, poderá ter de [carregar os HoloLens.](hololens2-charging.md#charging-the-device)
- Se os LEDs acenderem quando premir o botão de alimentação, mas não conseguir ver nada nos visores, [faça um reset duro do dispositivo](hololens-recovery.md#hard-reset-procedure).

Se os seus HoloLens ficar congelados ou sem resposta:

- Desligue os HoloLens premindo o botão de alimentação até que os cinco LEDs se desliguem, ou durante 15 segundos se os LEDs não responderem. Para ligar os HoloLens, prima novamente o botão de alimentação.

Se estes passos não funcionarem, pode tentar [recuperar o dispositivo HoloLens 2](hololens-recovery.md) ou [HoloLens (1ª geração).](hololens1-recovery.md)

[De volta à lista](#list)

## <a name="low-disk-space-error"></a>Erro do "Espaço baixo do Disco"

Você precisará libertar algum espaço de armazenamento fazendo um ou mais dos seguintes:

- Apague alguns espaços não-reutilizados. Vá aos Espaços do Sistema **de Definições,**  >    >  selecione um espaço que já não necessita e, em seguida, selecione **Remover**.
- Retire alguns dos hologramas que colocou.
- Elimine algumas fotos e vídeos da aplicação Fotos.
- Desinstale algumas aplicações dos seus HoloLens. Na lista **de aplicações Desinstalar,** toque e mantenha a aplicação que pretende desinstalar e, em seguida, selecione **Desinstalar**.

[De volta à lista](#list)

## <a name="calibration-fails"></a>Falha na calibração

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

[De volta à lista](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Não posso assinar porque o meu HoloLens foi previamente criado para outra pessoa.

Pode [colocar o dispositivo no **Modo intermitente** e utilizar](hololens-recovery.md#clean-reflash-the-device) o Advanced Recovery Companion para recuperar o dispositivo.

[De volta à lista](#list)


## <a name="unity-isnt-working"></a>A unidade não está a funcionar.

- Consulte [instalar as ferramentas](/windows/mixed-reality/install-the-tools) para a versão mais atualizada da Unidade recomendada para o desenvolvimento do HoloLens.
- Os problemas conhecidos com a Pré-visualização técnica da Unidade HoloLens estão documentados nos [fóruns hololelens da Unidade.](https://forum.unity3d.com/threads/known-issues.394627/)

[De volta à lista](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>O Portal do Dispositivo windows não está a funcionar corretamente

- A funcionalidade de visualização ao vivo na captura de Realidade Mista pode apresentar vários segundos de latência.

- Na página Entrada Virtual, os controlos Gesture e Scroll na secção Gestos Virtuais não estão funcionais. Usá-los não terá efeito. O teclado virtual na página de entrada virtual funciona corretamente.

- Depois de ativar o modo de desenvolvimento em Definições, pode demorar alguns segundos até que o interruptor ligue o Portal do Dispositivo.

[De volta à lista](#list)

## <a name="emulator"></a>Emulador
### <a name="the-hololens-emulator-isnt-working"></a>O Emulador HoloLens não está a funcionar.

A informação sobre o emulador HoloLens está localizada na nossa documentação do desenvolvedor.  Leia mais sobre [a resolução de problemas do emulador HoloLens.](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)


- Nem todas as aplicações na Microsoft Store são compatíveis com o emulador. Por exemplo, Young Conker e Fragmentos não são jogáveis no emulador.
- Não é possível utilizar a webcam do PC no Emulador.
- A funcionalidade de pré-visualização ao vivo do Portal do Dispositivo Windows não funciona com o emulador. Ainda é possível capturar vídeos e imagens da Realidade Mista.

[De volta à lista](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Não consigo encontrar ou usar o teclado para escrever no Emulador HoloLens 2

*Brevemente*

[De volta à lista](#list)

## <a name="voice-commands-arent-working"></a>Os comandos de voz não estão a funcionar.

Se cortana não está respondendo aos seus comandos de voz, certifique-se de que Cortana está ligada. Na lista de todas as aplicações, selecione **Definições** de Caderno do Menu Cortana  >    >    >   para escoar alterações. Para saber mais sobre o que pode dizer, consulte [Use a sua voz com HoloLens.](hololens-cortana.md)

No HoloLens (1º género), o reconhecimento de voz incorporado não é configurável. Está sempre ligado. No HoloLens 2, pode escolher se liga tanto o reconhecimento de voz como o Cortana durante a configuração do dispositivo.

Se o seu HoloLens 2 não estiver a responder à sua voz, certifique-se de que o reconhecimento da fala está ligado. Inicie **o Discurso de** Privacidade  >  **das Definições**  >    >   e ligue o **reconhecimento da fala**.

[De volta à lista](#list)

## <a name="hand-input-isnt-working"></a>A entrada da mão não está a funcionar.

Para garantir que os HoloLens possam ver as suas mãos, precisa mantê-las na moldura do gesto.  O Mixed Reality Home fornece feedback que lhe permite saber quando as suas mãos são rastreadas.  O feedback é diferente em diferentes versões de HoloLens:
- Em HoloLens (1º gênero), o cursor de olhar muda de um ponto para um anel
- No HoloLens 2, um cursor de ponta dos dedos aparece quando a sua mão está perto de uma ardósia, e um raio de mão aparece quando as ardósias estão mais longe

Muitas aplicações imersivas seguem padrões de entrada semelhantes ao Mixed Reality Home.  Saiba mais sobre a utilização da entrada manual nos [HoloLens (1º gênero)](hololens1-basic-usage.md#use-hololens-with-your-hands) e [holoLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se estiver a usar luvas, note que alguns tipos de luvas não funcionam com o rastreio da mão.  Um exemplo comum são as luvas de borracha pretas, que tendem a absorver a luz infravermelha e não são captadas pela câmara de profundidade.  Se o seu trabalho envolve luvas de borracha, recomendamos experimentar uma cor mais clara, como azul ou cinza.  Outro exemplo são as grandes luvas largas, que tendem a obscurecer a forma da sua mão. Recomendamos a utilização de luvas que sejam o mais adequadas possível para obter os melhores resultados.

Se a sua viseira tiver impressões digitais ou manchas, utilize o pano de limpeza de microfibras que veio com os HoloLens para limpar suavemente a viseira.

[De volta à lista](#list)

## <a name="cant-connect-to-wi-fi"></a>Não consigo ligar-se a Wi-Fi

Aqui estão algumas coisas a experimentar se não consegue ligar os hololens a uma rede Wi-Fi:

- Certifique-se de que Wi-Fi está ligado. Para verificar, use o gesto Iniciar e, em seguida, selecione  >  **Definições Rede &amp;**  >  **Internet Wi-Fi**. Se Wi-Fi estiver ligado, tente desligá-lo e depois ligado novamente.
- Aproxime o computador do router ou do ponto de acesso.
- Reinicie o router Wi-Fi e [reinicie os HoloLens](hololens-recovery.md). Tente ligar de novo.
- Se nenhuma destas coisas funcionar, verifique se o seu router está a utilizar o firmware mais recente. Pode encontrar esta informação no site do fabricante.

[De volta à lista](#list)
## <a name="bluetooth-devices-arent-pairing"></a>Os dispositivos Bluetooth não estão a emparelhar

Se tiver problemas [em emparelhar um dispositivo Bluetooth,](hololens-connect-devices.md)experimente o seguinte:

- Aceda aos **dispositivos de definição**  >  e certifique-se de que o Bluetooth está ligado. Se for, desligue e volte a ligá-lo.
- Certifique-se de que o seu dispositivo Bluetooth está completamente carregado ou que possui pilhas frescas.
- Se ainda não conseguir ligar, [reinicie os HoloLens.](hololens-recovery.md)

[De volta à lista](#list)

## <a name="usb-c-microphone-isnt-working"></a>O microfone USB-C não está a funcionar.
Esteja ciente de que alguns microfones USB-C se reportam incorretamente como um microfone *e* um altifalante. Isto é um problema com o microfone e não com os HoloLens. Ao ligar um destes microfones aos HoloLens, o som pode perder-se. Felizmente, há uma solução simples.  

No Som do Sistema **de Definições,**  ->    ->  coloque explicitamente os altifalantes incorporados **(Controlador de áudio de recurso analógico)** como o **dispositivo Predefinido**. Os HoloLens devem lembrar-se desta definição mesmo que o microfone seja removido e reconectado mais tarde.

![Resolução de problemas dos microfones USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Os dispositivos listados como disponíveis em Definições não funcionam

HoloLens (1º gêger) não suporta perfis de áudio Bluetooth. Os dispositivos de áudio Bluetooth, como altifalantes e auscultadores, podem aparecer como disponíveis nas definições de HoloLens, mas não são suportados.

HoloLens 2 suporta o perfil de áudio Bluetooth A2DP para reprodução estéreo. O perfil Bluetooth Hands Free que permite a captura do microfone a partir de um periférico Bluetooth não é suportado nos HoloLens 2.

Se tiver problemas em utilizar um dispositivo Bluetooth, certifique-se de que é um dispositivo suportado. Os dispositivos suportados incluem:

- Teclados QWERTY Bluetooth em inglês (pode usá-los em qualquer lugar que utilize o teclado holográfico).
- Ratos bluetooth.
- O [clicker HoloLens.](hololens1-clicker.md)

Pode emparelhar outros dispositivos Bluetooth HID e GATT juntamente com os hololens. No entanto, poderá ter de instalar aplicações de acompanhantes correspondentes da Microsoft Store para utilizar os dispositivos.

[De volta à lista](#list)
