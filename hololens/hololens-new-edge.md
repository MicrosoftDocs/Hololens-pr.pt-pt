---
title: Apresentamos o novo Microsoft Edge
description: Conheça a nova app Edge
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, borda, internet, navegador
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 8ef73733b9fa4f422335977be860371b9570d549
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189703"
---
# <a name="introducing-the-new-microsoft-edge"></a>Apresentamos o novo Microsoft Edge

![Animação do legado Microsoft Edge logotipo para novo logotipo Microsoft Edge.](images/new-edge.gif)

O novo Microsoft Edge [adota o projeto de código aberto Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) para criar uma melhor compatibilidade para os clientes e menos fragmentação da web para os desenvolvedores web.

Com [Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)o novo Microsoft Edge está disponível para HoloLens 2 clientes pela primeira vez! Por favor, partilhe feedback e bugs com a nossa equipa através da funcionalidade **Enviar feedback** no novo Microsoft Edge ou via [Feedback Hub](hololens-feedback.md).

> [!IMPORTANT]
> Esta nova Microsoft Edge substitui automaticamente o legado Microsoft Edge, que [já não](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) é suportado em novas versões.

![Nova Microsoft Edge imagem.](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Lançamento do novo Microsoft Edge

O novo Microsoft Edge ![novo ícone de Microsoft Edge.](images/new_edge_logo.png) (representado por um ícone de redemoinho azul e verde) está fixado ao menu Iniciar e será automaticamente lançado quando ativar uma ligação web.

> [!NOTE]
> Quando lançar pela primeira vez o novo Microsoft Edge no dia 2 HoloLens, as suas definições e dados serão importados do legado Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configurar definições de política para o novo Microsoft Edge

O novo Microsoft Edge oferece aos administradores de TI um conjunto muito mais alargado de políticas de navegador em HoloLens 2 do que estavam anteriormente disponíveis com Microsoft Edge.

Aqui estão alguns recursos úteis para aprender mais sobre a gestão de configurações políticas para o novo Microsoft Edge:

- [Configurar as definições de política Microsoft Edge com Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Microsoft Edge Legado para Microsoft Edge mapeamento de políticas](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome para Microsoft Edge mapeamento de políticas](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentação completa [da empresa Microsoft Edge](/deployedge/)

> [!IMPORTANT]
> Devido ao volume de políticas de navegador suportadas pelo novo Microsoft Edge, a nossa equipa não consegue garantir que cada nova política funcione no HoloLens 2. No entanto, testámos e confirmamos que o novo equivalente Microsoft Edge de cada legado Microsoft Edge política anteriormente apoiada no trabalho de HoloLens 2, como esperado. Consulte [Microsoft Edge Legado para Microsoft Edge mapeamento de políticas](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) para encontrar o novo equivalente Microsoft Edge de cada legado Microsoft Edge política de navegador que você estava usando com HoloLens 2.
>
> Há pelo menos duas novas políticas Microsoft Edge que sabemos que *não funcionarão* com HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>O que esperar do novo Microsoft Edge no dia 2 HoloLens

Como o novo Microsoft Edge é uma aplicação win32 nativa com uma nova camada de adaptador UWP que lhe permite funcionar em dispositivos apenas UWP como HoloLens 2, algumas funcionalidades podem não estar imediatamente disponíveis. Vamos apoiar novos cenários e funcionalidades ao longo dos próximos meses, por isso, verifique este espaço para obter informações atualizadas.

**Cenários e funcionalidades que se espera que funcionem:**
- Experiência de primeira execução, iniciar sessão no perfil e sincronizar
- Os websites devem renderizar e comportar-se como esperado
- A maioria das funcionalidades do navegador (Favoritos, Histórico, etc.) devem funcionar como esperado
- Dark mode (Modo escuro)
- Instalação de aplicações web para o dispositivo
- Instalação de extensões (por favor, avise-nos se utilizar quaisquer extensões que não funcionem corretamente no HoloLens 2)
- Visualização e marcação de um PDF
- Som espacial a partir de uma única janela de navegador
- Atualização automática e manual do navegador
- Guardar um PDF do menu Imprimir (utilizando a opção "Guardar para PDF")
- Extensão WebXR e 360 Espectador
- Restauração de conteúdo para corrigir janela, ao navegar em várias janelas colocadas no seu ambiente

**Cenários e características não esperados para funcionar:**
- Som espacial de múltiplas janelas com fluxos de áudio simultâneos
- "Vê, diz"
- Impressão

**Principais problemas de navegador conhecidos:**
- A pré-visualização do amplificador no teclado holográfico foi desativada para o novo Microsoft Edge. Esperamos recuperar esta funcionalidade numa futura atualização, uma vez que a ampliação esteja a funcionar corretamente.
- O áudio pode ser reproduzido a partir da janela do navegador errado se tiver outra janela do navegador aberta e ativa. Podes contornar este problema fechando a outra janela ativa que não devia estar a reproduzir áudio.
- Ao reproduzir áudio a partir de uma janela do navegador no modo "Siga-me", o áudio continuará a reproduzir se desativar o modo "Siga-me". Pode contornar este problema interrompendo a reprodução áudio antes de desativar o modo "Siga-me" ou fechando a janela com o botão X.
- Interagir com janelas Microsoft Edge ativas pode fazer com que outras janelas de aplicações 2D fiquem inativas inesperadamente. Pode reativar estas janelas interagindo novamente com elas.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Canais privilegiados

A equipa Microsoft Edge disponibiliza três canais de pré-visualização para a comunidade Edge Insider: Beta, Dev e Canary. A instalação de um canal de pré-visualização não desinstala a versão lançada de Microsoft Edge no seu HoloLens 2, podendo instalar mais do que um ao mesmo tempo. 

Visite a [página inicial do Microsoft Edge Insider](https://www.microsoftedgeinsider.com) para saber mais sobre a comunidade Edge Insider. Para saber mais sobre os diferentes canais Edge Insider e começar, visite a [página de descarregamento](https://www.microsoftedgeinsider.com/download)edge insider .

Existem alguns métodos disponíveis para instalar Microsoft Edge canais Insider para HoloLens 2:

**Instalação direta no dispositivo (atualmente apenas disponível para dispositivos não geridos)**
  1. Na sua HoloLens 2, visite a [página de descarregamento edge insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o botão **Download para HoloLens 2** para o canal Edge Insider que pretende instalar.
  1. Lance o ficheiro .msix descarregado a partir da fila de descarregamento edge ou a partir da pasta "Downloads" do seu dispositivo (utilizando o File Explorer).
  1. [O instalador de aplicações](app-deploy-app-installer.md) será lançado.
  1. Selecione o botão **Instalar.**
  1. Após a instalação com sucesso, encontrará Microsoft Edge Beta, Dev ou Canário como uma entrada separada na lista de **aplicações de Todas** as aplicações da menu Iniciar.

**Instale via PC com Windows Portal do Dispositivo (requer [que o modo de desenvolvimento](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) seja ativado no HoloLens 2)**
  1. No seu PC, visite a [página de descarregamento edge insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o **botão de seta para baixo** ao lado do botão "Descarregue para Windows 10" para o canal Edge Insider que pretende instalar.
  1. Selecione **HoloLens 2** no menu suspenso.
  1. Guarde o ficheiro .msix para a pasta "Downloads" do seu PC (ou outra pasta que possa encontrar facilmente).
  1. Utilize [Windows Portal do Dispositivo](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) no seu PC para instalar o ficheiro .msix descarregado no HoloLens 2.
  1. Após a instalação com sucesso, encontrará Microsoft Edge Beta, Dev ou Canário como uma entrada separada na lista de **aplicações de Todas** as aplicações da menu Iniciar.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Usar o WDAC para bloquear novas Microsoft Edge

Para os Administradores de TI que pretendam atualizar a sua [política WDAC](windows-defender-application-control-wdac.md) para bloquear a nova aplicação Microsoft Edge, terá de adicionar o seguinte à sua política.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gerir pontos finais para o novo Microsoft Edge

Alguns ambientes podem ter restrições de rede para explicar como uma consideração. Para garantir uma experiência suave com o novo Edge, por [favor, ative estes pontos finais da Microsoft.](/deployedge/microsoft-edge-security-endpoints)

Leia mais sobre os [pontos finais](hololens-offline.md)atualmente disponíveis para HoloLens .

## <a name="install-web-apps"></a>Instalar aplicativos web
 > [!Note]
> A partir de [Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)a aplicação web Office deixará de ser pré-instalada. 

Pode utilizar o novo Edge para instalar aplicações web ao lado de aplicações Microsoft Store. Por exemplo, pode instalar a aplicação web Microsoft Office para visualizar e editar ficheiros alojados no SharePoint ou OneDrive. Para instalar a Office aplicação web, visite https://www.office.com e selecione a **app Disponível** ou **instale o** botão Office na barra de endereços. **Selecione Instalar** para confirmar.
> [!IMPORTANT]
> Office funcionalidade da aplicação web só está disponível quando o seu HoloLens 2 tem uma ligação ativa à Internet.

## <a name="webxr-and-360-viewer"></a>WebXR e 360 Espectador


O novo Microsoft Edge inclui suporte para o WebXR, que é o novo padrão para criar experiências web imersivas (substituindo o WebVR). Muitas experiências web imersivas foram projetadas com VR em mente (substituem o seu campo de visão por um ambiente virtual), mas essas experiências também são apoiadas por HoloLens 2. O padrão WebXR também permite experiências web imersivas de realidade aumentada e mista que usam o seu ambiente físico. À medida que os desenvolvedores passam mais tempo com o WebXR, antecipamos novas experiências imersivas de realidade aumentada e mista que chegarão para HoloLens 2 clientes experimentarem!

A extensão 360 Viewer é construída no WebXR e instala-se automaticamente ao lado do novo Microsoft Edge no HoloLens 2. Esta extensão web dá-lhe a capacidade de mergulhar em vídeos de 360 graus. O YouTube oferece a maior seleção de 360 vídeos, por isso encorajamo-lo a começar por aí.

### <a name="how-to-use-webxr"></a>Como utilizar o WebXR

1. Navegue para um site com suporte WebXR.
1. Selecione o botão **Enter VR** no site. A localização e representação visual deste botão podem variar por website, mas pode parecer semelhante a:

    ![Introduza o exemplo do botão VR.](images/75px-enter-vr.png)

1. A primeira vez que tentar lançar uma experiência WebXR num domínio específico, o navegador pedirá consentimento para introduzir uma vista imersiva, selecione **Permitir**.
1. Use [HoloLens 2 gestos](hololens2-basic-usage.md#the-hand-tracking-frame) para manipular a experiência.
1. Se a experiência não tiver um botão **De saída,** use o [gesto Iniciar](hololens2-basic-usage.md#start-gesture) para regressar a casa.

**Amostras webXR recomendadas**
- 360 Espectador (ver secção seguinte)
- [Dinossauros XR](https://www.xrdinosaurs.com/)
- [Expresso Barista](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>Como usar o Espectador 360

1. Navegue para um vídeo de 360 graus no YouTube.
1. Na moldura de vídeo, selecione o botão de auscultador de realidade mista:

    ![Botão para ativar 360 Espectador.](images/enter-360-viewer.jpg)

1. A primeira vez que tentar lançar o 360 Viewer num domínio específico, o navegador pedirá consentimento para introduzir uma vista imersiva. **Selecione Permitir**.
1. [Toque de ar](hololens2-basic-usage.md#select-using-air-tap) para aumentar os controlos de reprodução. Utilize [raios de mão e toque de ar](hololens2-basic-usage.md#select-using-air-tap) para reproduzir/fazer pausa, saltar para a frente/para trás, ligar/desligar as legendas ou parar a experiência (que sai da vista imersiva). Os controlos de reprodução desaparecerão após alguns segundos de inatividade.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Top WebXR e 360 Espectadores conhecidos problemas conhecidos
- Dependendo da complexidade da experiência WebXR, o framerate pode cair ou gaguejar.
- O suporte para articulações articuladas nas articulações de mão no WebXR não é ativado por padrão. Os desenvolvedores podem ativar o suporte através de edge://flags ligando "WebXR Hand Input".
- 360 vídeos de sites que não o YouTube podem não funcionar como esperado.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Fornecendo feedback no WebXR e 360 Viewer

Por favor, partilhe feedback e bugs com a nossa equipa através da funcionalidade **Enviar feedback** na nova Microsoft Edge.
