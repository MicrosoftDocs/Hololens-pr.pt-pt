---
title: HoloLens Resolução de problemas do dispositivo
description: Mantenha-se atualizado sobre as soluções mais comuns para HoloLens problemas com o dispositivo e técnicas de resolução de problemas.
author: evmill
ms.author: v-evmill
ms.date: 10/7/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemas, bug, resolução de problemas, correção, ajuda, suporte, HoloLens, emulador
ms.openlocfilehash: afbbc1ab0e018f668381137849738ec7d274fe37
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924369"
---
# <a name="device-troubleshooting"></a>Resolução de problemas do dispositivo

Este artigo descreve como resolver várias questões comuns HoloLens.

>[!IMPORTANT]
> Antes de iniciar qualquer procedimento de resolução de problemas, certifique-se de que o seu dispositivo está carregado até **20 a 40%** da capacidade da bateria, se possível. As [luzes indicadoras](hololens2-setup.md#lights-that-indicate-the-battery-level) da bateria localizadas sob o botão de alimentação são uma forma rápida de verificar a capacidade da bateria sem iniciar sessão no dispositivo.

<a id="list"></a>

**Problemas Conhecidos**
- [Cada vez que a energia vai para 18%, o dispositivo desliga-se automaticamente](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive Aplicação UWP não funciona para utilizadores AD Azure](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Por que vejo 0x80180014 durante o Piloto Automático?](#why-do-i-see-0x80180014-during-autopilot)
- [Vídeo de Assistência Remota congela após 20 minutos](#remote-assist-video-freezes-after-20-minutes)
- [O login automático pede o login](#auto-login-asks-for-log-in)
- [Microsoft Edge falha no lançamento](#microsoft-edge-fails-to-launch)
- [O teclado não muda para personagens especiais](#keyboard-doesnt-switch-to-special-characters)
- [Descarregar ficheiros bloqueados não mostra erro](#downloading-locked-files-doesnt-error)
- [Upload/download de tempos de carregamento/descarregamento de ficheiros do Portal do Dispositivo](#device-portal-file-uploaddownload-times-out)
- [Ecrã azul após desenrolar a pré-visualização do Insider num dispositivo que piscou com uma construção Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive não faz upload automática de imagens](#onedrive-doesnt-automatically-upload-pictures)

**Geral**
- [HoloLens não responde ou não começa](#hololens-is-unresponsive-or-wont-start)
- [Erro do "Espaço baixo do Disco"](#low-disk-space-error)
- [Falha de calibração](#calibration-fails)
- [Não posso entrar porque o meu HoloLens foi previamente criado para outra pessoa.](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [A unidade não está a funcionar.](#unity-isnt-working)
- [Windows O Portal do Dispositivo não está a funcionar corretamente](#windows-device-portal-isnt-working-correctly)
- [O HoloLens Emulator não está a funcionar.](#the-hololens-emulator-isnt-working)

**Entrada**
- [Os comandos de voz não estão a funcionar.](#voice-commands-arent-working)
- [A entrada da mão não está a funcionar.](#hand-input-isnt-working)

**Conetividade**
- [Não se pode ligar ao Wi-Fi](#cant-connect-to-wi-fi)

**Dispositivos Externos** 
- [Bluetooth dispositivos não estão a emparelhar](#bluetooth-devices-arent-pairing)
- [O microfone USB-C não está a funcionar.](#usb-c-microphone-isnt-working)
- [Dispositivos listados como disponíveis em Definições não funcionam](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Cada vez que a energia vai para 18%, o dispositivo desliga-se automaticamente

Há um problema conhecido em que quando o dispositivo atinge a bateria de 18%, irá desligar-se inesperadamente. Trata-se de um problema de software, não de hardware ou de bateria, por isso, por favor, não troquem dispositivos por isso. Se não tiver a certeza se o seu problema corresponde a este erro, por favor:

1. Certifique-se de que os diagnósticos opcionais estão ativados nos seus dispositivos
1. Reproduzir o problema
1. Envie um problema [de Feedback Hub](hololens-feedback.md)
1. Partilhar o artigo URL de emissão de feedback
1. [Suporte de contato](https://aka.ms/hololenssupport)

[De volta à lista](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive Aplicação UWP não funciona para utilizadores AD Azure

Se utilizar OneDrive For Business utilizando a sua conta Azure AD, poderá ter encontrado erro ao iniciar sação na sua aplicação de OneDrive de caixa de entrada. Não conseguir entrar na OneDrive aplicação não afeta uploads automáticos de imagens e vídeos capturados pela aplicação Camera. Os seus ficheiros ainda podem ser guardados e acedidos a partir do armazenamento em nuvem OneDrive para Empresas. As equipas OneDrive e HoloLens estão a trabalhar no assunto.

### <a name="workarounds"></a>Soluções

Pré-requisito: Os clientes podem utilizar Microsoft Edge e o dispositivo OS é atualizado para um Windows construção Holográfica, 21H1 ou mais recente.

Se estiver a passar por este problema, experimente um dos seguintes:

- Os utilizadores podem aceder diretamente OneDrive For Business a partir de Microsoft Edge e interagir com os seus ficheiros no website a partir do seu navegador.
- Os utilizadores podem instalar a aplicação OneDrive PWA para HoloLens, descarregando-a a partir de Microsoft Edge. Isto irá permitir que os utilizadores voltem a visualizar e gerir ficheiros no dispositivo. Leia e siga estas [instruções para instalar a aplicação OneDrive PWA no seu HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[De volta à lista](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Por que vejo 0x80180014 durante o Piloto Automático?

Este erro é normalmente encontrado durante o reset do dispositivo e os fluxos de reutilização onde um dispositivo HoloLens passou pelo Autopilot pelo menos uma vez. Para resolver este problema, [elimine o dispositivo de Microsoft Intune](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) e volte a reiniciá-lo para completar o fluxo do Autopilot.

Para mais informações, consulte os [passos de resolução de problemas na página do piloto automático.](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Vídeo de Assistência Remota congela após 20 minutos

> [!NOTE]
> Existe uma versão mais recente do Remote Assist que tem uma correção para este problema. Por [favor, atualize](holographic-store-apps.md#update-apps) o Remote Assist para a versão mais recente para evitar este problema.

> [!NOTE]
> Devido à gravidade desta Edição Conhecida, tínhamos interrompido temporariamente a disponibilidade de Windows Holographic, versão 21H1. A construção 21H1 está agora novamente disponível, pelo que os dispositivos poderão ser novamente atualizados para a mais recente construção de 21H1.

No mais recente lançamento de [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), alguns utilizadores do Remote Assist experimentaram o congelamento de vídeos durante as chamadas ao longo de 20 minutos. Esta é uma **questão conhecida.**

### <a name="workarounds"></a>Soluções

Se não conseguir atualizar o Remote Assist para uma construção mais recente, experimente o seguinte trabalho.

#### <a name="restart-in-between-calls"></a>Reiniciar entre chamadas

Se as suas chamadas forem de mais de 20 minutos e estiver a experimentar este problema, tente reiniciar o seu dispositivo. Reiniciar o seu dispositivo entre chamadas de Assistência Remota irá refrescar o seu dispositivo e colocá-lo de volta em bom estado.

Para reiniciar rapidamente um dispositivo Windows [Holographic, a versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) abre o menu inicial e selecione o ícone do utilizador e, em seguida, selecione **Restart**.

[De volta à lista](#list)

## <a name="auto-login-asks-for-log-in"></a>O login automático pede o login

Um dispositivo HoloLens 2 pode ser configurado para iniciar sessão automaticamente através **de**  ->  **opções** de início de Definições contas  ->   -> e sob a definição **necessária** do valor para **Nunca**. Alguns utilizadores poderão ser obrigados a fazer login novamente no dispositivo ao atualizarem um dispositivo com uma atualização substancialmente grande, como é o caso de uma atualização de funcionalidades. Esta é uma **questão conhecida.**

Exemplo de quando isto pode ocorrer:

- Atualização de um dispositivo de Windows Holographic, versão 2004 (Build 19041.xxxx) a Windows Holographic, versão 21H1 (Build 20346.xxxx)
- Atualizar um dispositivo para fazer uma grande atualização sobre a mesma grande construção, por exemplo, Windows Holographic, versão 2004 para Windows Holographic, versão 20H2
- Atualizar um dispositivo de uma imagem de fábrica para a imagem mais recente

Isto não deve ocorrer durante:

- Dispositivos que tomam uma atualização mensal de manutenção

Trabalhar em torno de métodos:

- Métodos de entrada como PIN, Password, Íris, Autenticação Web ou teclas FIDO2.
- Se o dispositivo PIN não puder ser lembrado e não estiverem disponíveis outros métodos de autenticação, então um utilizador pode utilizar [o modo de reflashing manual](hololens-recovery.md#manual-procedure).

[De volta à lista](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge falha no lançamento

> [!NOTE]
> Esta questão foi originalmente criada com a versão de envio de Microsoft Edge em mente. Esta questão pode ser resolvida na [nova Microsoft Edge.](hololens-new-edge.md) Se não for, por favor, arquive o feedback.

Alguns clientes relataram um problema em que Microsoft Edge não é lançado. Para estes clientes, o problema persiste através do reboot e não é resolvido com Windows ou atualizações de aplicações. Se estiver a experimentar este problema e tiver confirmado [Windows está atualizado](hololens-updates.md#manually-check-for-updates), por favor, arquive um bug da [aplicação Feedback Hub](hololens-feedback.md) com a seguinte categoria e subcategoria: Instalar e atualizar > descarregar, instalar e configurar Windows Update.

Não há soluções alternativas conhecidas, pois não conseguimos enraizar a questão até agora. Arquivar um bug via Feedback Hub ajudará a nossa investigação! Esta é uma **questão conhecida.**

[De volta à lista](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>O teclado não muda para personagens especiais

Existe um problema durante o OOBE, em que uma vez que o utilizador escolheu uma conta de trabalho ou escola e está a introduzir a sua palavra-passe, tentando mudar para os caracteres especiais no teclado, tocando no botão &123 não se altera para caracteres especiais. Esta é uma **questão conhecida.**

Work-arounds:

- Feche o teclado e reabra-o tocando no campo de texto.
- Introduza incorretamente a sua palavra-passe. Quando o teclado for relançado da próxima vez, funcionará como esperado.
- Autenticação web, feche o teclado e selecione **Iniciar sôs-te de outro dispositivo**.
- Se introduzir apenas números, um utilizador pode premir e segurar certas chaves para abrir um menu expandido.
- Utilizando um teclado USB.

Isto não afeta:

- Utilizadores que optam por utilizar uma conta pessoal.

[De volta à lista](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Descarregar ficheiros bloqueados não é erro

> [!NOTE]
> Esta é uma **questão conhecida** que foi corrigida em [Windows Holographic, versão 21H1 - julho 2021 Atualização](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update).

Em construções anteriores de Windows Holographic, ao tentar descarregar um ficheiro bloqueado, o resultado seria uma página de erro HTTP. Na Windows a atualização Holográfica, versão 21H1, tentando descarregar um ficheiro bloqueado resulta em nada visível a acontecer - o ficheiro não descarrega e não há erro.

[De volta à lista](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Upload/download de tempos de carregamento/descarregamento de ficheiros do Portal do Dispositivo
> [!NOTE]
> Esta é uma **questão conhecida** que foi corrigida em [Windows Holographic, versão 21H1 - julho 2021 Atualização](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update). Se desativou previamente a SSL Connection como parte da solução alternativa, recomendamos vivamente que a reative.

Alguns clientes descobriram que, ao tentar carregar ou descarregar ficheiros, a operação pode parecer pendurar e, em seguida, sair ou nunca completar. Isto é separado da questão conhecida do['ficheiro bloqueado'](#downloading-locked-files-doesnt-error) -- isto afeta Windows construções holográficas, versões 2004, 20H2 e 21H1 no mercado. O problema tem sido causado por um erro no tratamento do Portal do Dispositivo de determinadas solicitações, e é mais consistentemente atingido quando se utiliza https, que é o padrão.

### <a name="workaround"></a>Solução

Esta solução, que se aplica igualmente à Wi-Fi e usbNcm, consiste em desativar a opção "necessária" em "Ligação SSL". Para tal, navegue para o Portal do Dispositivo, **Sistema** e selecione a página **Preferências.** Na secção de Segurança do **Dispositivo,** localizar **a Ligação SSL** e desativar para desativar **a Necessária**.

O utilizador deve então ir para http://, não https:// (endereço IP) e funcionalidades como upload de ficheiros e descarregamento funcionarão.

[De volta à lista](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Ecrã azul após desenrolar a pré-visualização do Insider num dispositivo que piscou com uma construção Insider

Este é um problema que afeta os utilizadores que se encontram numa pré-visualização insider, relançou os seus HoloLens 2 com uma nova construção de pré-visualização insider e, em seguida, não rolou do programa Insider. Esta é uma **questão conhecida.**

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

    1. Coloque o [HoloLens 2 no modo intermitente](hololens-recovery.md) manualmente, ligando completamente sem ligar. Em seguida, enquanto segura o volume, toque no botão De alimentação.

    1. Ligação para o PC e abra o Advanced Recovery Companion.

    1. Flash o HoloLens 2 para a construção predefinitiva.

[De volta à lista](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive não faz upload automática de imagens

A aplicação OneDrive para HoloLens não suporta o upload automático de câmaras para trabalho ou contas escolares. Esta é uma **questão conhecida.**

Soluções alternativas:

- Se for viável para o seu negócio, o upload automático de câmaras é suportado nas contas da Microsoft do consumidor. Pode iniciar sôms na sua conta Microsoft para além do seu trabalho ou conta escolar (a aplicação OneDrive suporta o duplo s-in). A partir do seu perfil de conta Microsoft dentro de OneDrive pode ativar o upload automático do rolo de câmara de fundo.

- Se não conseguir utilizar com segurança uma conta de consumidor da Microsoft para fazer o upload das suas fotos automaticamente, pode enviar manualmente fotografias para o seu trabalho ou conta escolar a partir da aplicação OneDrive. Para isso, certifique-se de que está inscrito na sua conta de trabalho ou escola na aplicação OneDrive. Selecione o **+** botão e escolha **Upload**. Encontre as fotos ou vídeos que pretende fazer o upload navegando para **o Pictures > Camera Roll**. Selecione as fotos ou vídeos que pretende carregar e, em seguida, selecione o botão **Abrir.**

[De volta à lista](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens não responde ou não começa

Se o seu HoloLens não começar:

- Se os LEDs ao lado do botão de alimentação não se acenderem ou apenas um LED piscar brevemente, poderá ter de [carregar o seu HoloLens.](hololens2-charging.md#charging-the-device)
- Se os LEDs acenderem quando premir o botão de alimentação, mas não conseguir ver nada nos visores, [faça um reset duro do dispositivo](hololens-recovery.md#hard-reset-procedure).

Se o seu HoloLens ficar congelado ou sem resposta:

- Desligue o HoloLens premindo o botão de alimentação até que os cinco LEDs se desliguem, ou durante 15 segundos se os LEDs não responderem. Para iniciar a HoloLens, prima novamente o botão de alimentação.

Se estes passos não [funcionarem,](hololens-recovery.md) pode tentar recuperar o seu dispositivo HoloLens 2 ou [HoloLens (1ª geração).](hololens1-recovery.md)

[De volta à lista](#list)

## <a name="low-disk-space-error"></a>Erro do "Espaço baixo do Disco"

Você precisará libertar algum espaço de armazenamento fazendo um ou mais dos seguintes:

- Apague alguns espaços não-reutilizados. Vá a **Definições**  >    >  **System Spaces,** selecione um espaço que já não precisa e, em seguida, selecione **Remover**.
- Retire alguns dos hologramas que colocou.
- Elimine algumas fotos e vídeos da aplicação Fotos.
- Desinstale algumas aplicações do seu HoloLens. Na lista **de aplicações de Todas,** toque e mantenha a aplicação que pretende desinstalar e, em seguida, selecione **Desinstalar**.

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
- Objetos móveis na sua viseira fora do caminho (como o cabelo)
- Acendendo uma luz no seu quarto ou saindo da luz direta do sol

Se seguir todas as diretrizes e a calibração continuar a falhar, pode desativar a indicação de calibração em Definições. Informe-nos também ao arquivar feedback no [Feedback Hub.](hololens-feedback.md)

Consulte também informações relacionadas para [a cor da imagem ou resolução de problemas de luminosidade.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

A definição de IPD não é aplicável para HoloLens 2, uma vez que as posições oculares são calculadas pelo sistema. 

[De volta à lista](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Não posso entrar porque o meu HoloLens foi previamente criado para outra pessoa.

Pode [colocar o dispositivo no **Modo intermitente** e utilizar](hololens-recovery.md#clean-reflash-the-device) o Advanced Recovery Companion para recuperar o dispositivo.

[De volta à lista](#list)


## <a name="unity-isnt-working"></a>A unidade não está a funcionar.

- Consulte [a instalação das ferramentas](/windows/mixed-reality/install-the-tools) para a versão mais atualizada da Unidade recomendada para HoloLens desenvolvimento.
- As questões conhecidas com a Pré-visualização técnica HoloLens de unidade estão documentadas nos [fóruns da Unidade HoloLens](https://forum.unity3d.com/threads/known-issues.394627/).

[De volta à lista](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows O Portal do Dispositivo não está a funcionar corretamente

- A funcionalidade de visualização ao vivo na captura de Realidade Mista pode apresentar vários segundos de latência.

- Na página Entrada Virtual, os controlos de Gesto e Pergaminho sob a secção Gestos Virtuais não estão funcionais. Usá-los não terá efeito. O teclado virtual na página de entrada virtual funciona corretamente.

- Depois de ativar o Modo de Desenvolvimento em Definições, pode demorar alguns segundos até que o interruptor ligue o Portal do Dispositivo.

[De volta à lista](#list)

## <a name="the-hololens-emulator-isnt-working"></a>O HoloLens Emulator não está a funcionar.

A informação sobre o emulador HoloLens está localizada na nossa documentação do desenvolvedor.  Leia mais sobre [a resolução de problemas do emulador HoloLens.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Nem todas as aplicações do Microsoft Store são compatíveis com o emulador. Por exemplo, Young Conker e Fragmentos não são jogáveis no emulador.
- Não é possível utilizar a webcam do PC no Emulator.
- A funcionalidade de pré-visualização ao vivo do Portal do Dispositivo Windows não funciona com o emulador. Ainda é possível capturar vídeos e imagens da Realidade Mista.

[De volta à lista](#list)

## <a name="voice-commands-arent-working"></a>Os comandos de voz não estão a funcionar.

Se Cortana não responder aos comandos de voz, certifique-se de Cortana está ligado. Na lista de aplicações All, selecione **Cortana**  >    >  **Menu Notebook**  >  **Definições** para fazer alterações. Para saber mais sobre o que pode dizer, consulte [use a sua voz com HoloLens](hololens-cortana.md).

Na HoloLens (1º género), o reconhecimento da fala incorporada não é configurável. Está sempre ligado. No dia 2 HoloLens, pode escolher se liga tanto o reconhecimento da fala como a Cortana durante a configuração do dispositivo.

Se o seu HoloLens 2 não estiver a responder à sua voz, certifique-se de que o reconhecimento da fala está ligado. Comece **Definições**  >    >    >  **Discurso de** Privacidade e ligue o reconhecimento **da fala**.

[De volta à lista](#list)

## <a name="hand-input-isnt-working"></a>A entrada da mão não está a funcionar.

Para garantir que HoloLens consegue ver as suas mãos, é necessário mantê-las na moldura do gesto.  O Mixed Reality Home fornece feedback que lhe permite saber quando as suas mãos são rastreadas.  O feedback é diferente em diferentes versões de HoloLens:

- Em HoloLens (1º gênero), o cursor de olhar muda de um ponto para um anel
- No HoloLens 2, um cursor da ponta do dedo aparece quando a sua mão está perto de uma ardósia, e um raio de mão aparece quando as ardósias estão mais longe

Muitas aplicações imersivas seguem padrões de entrada semelhantes ao Mixed Reality Home.  Saiba mais sobre a utilização da entrada manual no [HoloLens (1ª geração)](hololens1-basic-usage.md#use-hololens-with-your-hands) e [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se estiver a usar luvas, note que alguns tipos de luvas não funcionam com o rastreio da mão.  Um exemplo comum são as luvas de borracha pretas, que tendem a absorver a luz infravermelha e não são captadas pela câmara de profundidade.  Se o seu trabalho envolve luvas de borracha, recomendamos experimentar uma cor mais clara, como azul ou cinza.  Outro exemplo são as grandes luvas largas, que tendem a obscurecer a forma da sua mão. Recomendamos a utilização de luvas que sejam o mais adequadas possível para obter os melhores resultados.

Se a sua viseira tiver impressões digitais ou manchas, utilize o pano de limpeza de microfibras que acompanha a HoloLens para limpar suavemente a viseira.

[De volta à lista](#list)

## <a name="cant-connect-to-wi-fi"></a>Não consigo ligar-me a Wi-Fi

Aqui estão algumas coisas a experimentar se não consegue ligar o seu HoloLens a uma rede Wi-Fi:

- Certifique-se de que Wi-Fi está ligado. Para verificar, use o gesto Iniciar e, em seguida, selecione **Definições**  >  **Internet &amp;**  >  **Wi-Fi da** Rede . Se Wi-Fi estiver ligado, tente desligá-lo e depois ligado novamente.
- Aproxime o computador do router ou do ponto de acesso.
- Reinicie o router Wi-Fi e [reinicie HoloLens](hololens-recovery.md). Tente ligar novamente.
- Se nenhuma destas coisas funcionar, verifique se o seu router está a utilizar o mais recente firmware. Pode encontrar esta informação no site do fabricante.

[De volta à lista](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth dispositivos não estão a emparelhar

Se tiver problemas [em emparelhar um dispositivo Bluetooth,](hololens-connect-devices.md)experimente o seguinte:

- Vá a  >  **Definições Dispositivos**, e certifique-se de que Bluetooth está ligado. Se for, desligue e volte a ligá-lo.
- Certifique-se de que o seu Bluetooth dispositivo está completamente carregado ou tem pilhas frescas.
- Se ainda não conseguir ligar, [reinicie a HoloLens](hololens-recovery.md).

[De volta à lista](#list)

## <a name="usb-c-microphone-isnt-working"></a>O microfone USB-C não está a funcionar.

Esteja ciente de que alguns microfones USB-C se reportam incorretamente como um microfone *e* um altifalante. Este é um problema com o microfone e não com HoloLens. Ao ligar um destes microfones a HoloLens, o som pode perder-se. Felizmente, há uma simples correção.  

No **Definições**  ->  **System**  ->  **Sound,** coloque explicitamente os altifalantes incorporados **(Controlador de áudio de recurso analógico)** como o **dispositivo Predefinido**. HoloLens deve lembrar-se desta definição mesmo que o microfone seja removido e reconectado mais tarde.

![Resolução de problemas dos microfones USB-C.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Dispositivos listados como disponíveis em Definições não funcionam

HoloLens (1º género) não suporta Bluetooth perfis de áudio. Bluetooth dispositivos de áudio, como altifalantes e auscultadores, podem aparecer como disponíveis em HoloLens configurações, mas não são suportados.

HoloLens 2 suporta o perfil de áudio A2DP Bluetooth para reprodução estéreo. O perfil Bluetooth Mãos Livres que permite a captura do microfone a partir de uma Bluetooth periférico não é suportado no HoloLens 2.

Se tiver problemas em usar um dispositivo Bluetooth, certifique-se de que é um dispositivo suportado. Os dispositivos suportados incluem:

- QWERTY em inglês Bluetooth teclados (pode usá-los em qualquer lugar que utilize o teclado holográfico).
- Bluetooth ratos.
- O [HoloLens clicker](hololens1-clicker.md).

Pode emparelhar outros dispositivos HID e GATT Bluetooth juntamente com o seu HoloLens. No entanto, poderá ter de instalar aplicações de acompanhantes correspondentes a partir de Microsoft Store para utilizar os dispositivos.

[De volta à lista](#list)
