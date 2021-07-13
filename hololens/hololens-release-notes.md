---
title: HoloLens 2 notas de lançamento
description: Mantenha-se atualizado com todas as atualizações de cada nova versão HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 73d89619498c61f2809702d788ffafc532afa67e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640054"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 notas de lançamento

Para garantir que tem uma experiência produtiva com os seus HoloLens dispositivos, continuamos a lançar atualizações de funcionalidades, bugs e segurança. Nesta página, pode ver o que há de novo para HoloLens todos os meses. Para obter a mais recente atualização HoloLens 2, pode [verificar se há atualizações e atualizações manuais](hololens-update-hololens.md#check-for-updates-and-manually-update) ou obter a Atualização Flash Completa (FFU) para [piscar o seu dispositivo através do Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device). O [download](https://aka.ms/hololens2download) é mantido atualizado e fornece a mais recente construção geralmente disponível.

> [!NOTE]
> O anúncio recente Windows 11 foi focado na versão para PC de Windows. Lançamos recentemente uma [grande atualização de OS](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) para HoloLens 2 em maio de 2021, e estamos a trabalhar num próximo lançamento baseado no feedback do cliente para este outono.

> [!IMPORTANT]
> Devido a um problema agora resolvido [conhecido na nossa construção 21H1 que estava a afetar os utilizadores do Remote Assist](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes), interrompemos temporalmente a oferta de Windows atualizações Holográficas, versão 21H1. Também tínhamos alterado a construção padrão do Advanced Recovery Companion (ARC) para o [Windows Holographic, versão 20H2 – junho 2021 Atualização](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update). A construção do ARC vai agora retomar a 21H1.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holográfico, versão 21H1 - junho 2021 Atualização
- Construção 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive para o trabalho ou para o upload do Rolo de Câmara escolar

Adicionámos uma nova funcionalidade à aplicação HoloLens 2 Definições, que permite aos clientes carregarem automaticamente fotos e vídeos de realidade mista da pasta Pictures > Camera Roll do dispositivo para o OneDrive correspondente para trabalho ou pasta escolar. Esta funcionalidade aborda uma [lacuna de funcionalidade dentro da aplicação OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) no HoloLens 2, que suporta apenas o upload automático do Camera Roll para a conta pessoal da Microsoft (e não para o seu trabalho ou conta escolar).

**Como funciona**

- Visite **Definições > System > Mixed Reality Camera** para ativar o "upload da câmara".
- Ao definir esta função para a posição **On,** quaisquer fotografias ou vídeos de realidade mista capturados no seu dispositivo serão automaticamente enviados para o upload para a pasta Do Rolo de Câmara > imagens do seu OneDrive para trabalho ou conta escolar.
    >[!NOTE]
    >As fotos e vídeos capturados antes de ativar esta funcionalidade *não serão* enviados para upload e ainda terão de ser carregados manualmente.
- Uma mensagem de estado na página Definições mostrará o número de ficheiros pendentes de upload (ou lerá "OneDrive está atualizado" quando todos os ficheiros pendentes tiverem sido carregados).
- Se estiver preocupado com a largura de banda ou quiser "fazer uma pausa" no upload por qualquer motivo, pode mudar a função para a posição **Off.** Desativar temporariamente a funcionalidade garante que a fila de upload continuará a aumentar à medida que adiciona novos ficheiros à pasta Do Rolo da Câmara, mas os ficheiros não serão carregados até que volte a ativar a funcionalidade.
- Os ficheiros mais recentes serão carregados primeiro (o último a entrar, o primeiro a sair).
- Se a sua conta OneDrive tiver problemas (por exemplo, após a alteração da palavra-passe), aparecerá na página **Definições.**
- Não existe o tamanho máximo do ficheiro, mas note que os ficheiros grandes demorarão mais tempo a ser carregados (especialmente se a largura de banda do upload estiver limitada). Se "parar" ou desligar o upload enquanto um ficheiro grande está a ser carregado, o upload parcial será preservado. Se o upload for re-activado dentro de várias horas após ser "pausado" ou desligado, o upload continuará de onde parou. No entanto, se o upload for re-activado após várias horas, o upload do grande ficheiro recomeçará desde o início.

**Questões e ressalvas conhecidas**

- Esta definição não tem nenhuma configuração construída em estrangulamento com base no uso atual da largura de banda. Se precisar de maximizar a largura de banda para outro cenário, desligue a definição manualmente. O upload será interrompido, mas a funcionalidade continuará a monitorizar ficheiros recém-adicionados para o Camera Roll. Re-activar o upload quando estiver pronto para continuar.
- Esta funcionalidade deve ser ativada para cada conta de utilizador no dispositivo, e apenas pode fazer upload de ficheiros para o utilizador que se encontra atualmente inscrito no dispositivo.
- Se estiver a tirar fotografias ou vídeos enquanto vê a contagem de upload na página Definições em tempo real, note que a contagem de ficheiros pendentes não pode ser alterada até que o ficheiro atual tenha concluído o upload.
- O upload fará uma pausa se o seu dispositivo adormecer ou estiver desligado. Para garantir que os uploads pendentes estão completos, utilize ativamente o dispositivo até que a página Definições se leia "OneDrive está atualizado" ou ajuste as definições **de & de alimentação.**
### <a name="added-support-for-some-telemetry-policies"></a>Apoio adicional a algumas políticas de telemetria

As seguintes políticas de telemetria são agora apoiadas no HoloLens 2:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- PermitirDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Tanto o Sistema\AllowTelemetry e System\ConfigureTelemetryOptInSettingsUx devem ser utilizados em conjunto para ter controlo total sobre a Telemetria e o comportamento na aplicação Definições.

Melhorias e correções na atualização:
- Corrige a grande corrupção de vídeo com a calibração de cores.
- Aborda um problema em que o texto pode ser truncado no menu Power.
- Permite o suporte para a política RequerPrivateStoreOnly.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holográfico, versão 20H2 - junho 2021 Atualização
- Construção 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Apoio adicional a algumas políticas de telemetria

As seguintes políticas de telemetria são agora apoiadas no HoloLens 2:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- PermitirDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Tanto o Sistema\AllowTelemetry e System\ConfigureTelemetryOptInSettingsUx devem ser utilizados em conjunto para ter controlo total sobre a Telemetria e o comportamento na aplicação Definições.

Encorajamo-lo a experimentar a nossa mais recente construção, Windows Holographic, versão 21H1.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holográfico, versão 1903 - junho 2021 Atualização
- Construção 18362.1116

Melhorias e correções na atualização:
- Esta atualização mensal de qualidade não contém quaisquer alterações notáveis, encorajamos-te a experimentar a nossa mais recente construção, Windows Holographic, versão 21H1.

>[!IMPORTANT]
> Esta construção deixará de ser servida.

## <a name="windows-holographic-version-21h1"></a>Windows Holográfico, versão 21H1
- Construção 20346.1002

Esta atualização contém funcionalidades para dois públicos-alvo; funcionalidades que podem ser utilizadas por qualquer pessoa num dispositivo pelo Utilizador Final, e novas opções de gestão de dispositivos que podem ser configuradas por Administrações de TI. A tabela abaixo especifica as características que são relevantes para cada público. Se você é um administrador de TI, por favor dê uma olhada na nossa [lista de informações de TI - Update Checklist](#it-admin---update-checklist).
>[!IMPORTANT]
>Para atualizar esta construção, HoloLens 2 dispositivos devem estar atualmente a executar a atualização de fevereiro de 2021 (build 19041.1136) ou mais recente. Se não estiver a ver esta atualização disponível, por favor atualize o seu dispositivo primeiro e tente novamente.

>[!NOTE]
>Hoje, Microsoft HoloLens 2 suporta atualizações mensais de manutenção (correções de erros e segurança) para as seguintes versões:
>- Windows Holográfico, versão 20H2 (Construção 19041.1128+)
>- Windows Holográfico, versão 2004 (Build 19041.1103+)
>- Windows Holográfico, versão 1903 (Construção 18362+) 
>
> Com a introdução da versão holográfica 21H1 Windows, **estamos a descontinuar atualizações mensais de manutenção para Windows versão Holográfica 1903**. Isto permite-nos focar em lançamentos mais recentes e continuar a oferecer melhorias valiosas. 


| Nome do recurso                                              | Breve descrição                                                                      | Público-alvo | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nova Microsoft Edge](#introducing-the-new-microsoft-edge)  | O novo Microsoft Edge, baseado em Chromium, está agora disponível para HoloLens 2. | Utilizador Final | 
[WebXR e 360 Espectador](#webxr-and-360-viewer) | Experimente experiências web imersivas e 360 reprodução de vídeo. | Utilizador Final | 
[App New Definições](#new-settings-app) | O legado Definições aplicação está a ser substituído por uma versão atualizada com novas funcionalidades e configurações. | Utilizador Final |
[Mostrar calibração de cores](#display-color-calibration) | Selecione um perfil de cores alternativo para o seu ecrã HoloLens 2. | Utilizador Final |
[Selecionador de aplicativos predefinido](#default-app-picker) | Escolha qual aplicativo deve ser lançado para cada ficheiro ou tipo de ligação. | Utilizador Final |
[Por controlo de volume de aplicações](#per-app-volume-control) | Controle o volume de nível da aplicação independentemente do volume do sistema. | Utilizador Final |
[Instalar aplicativos web](#install-web-apps) | Instale aplicativos web no HoloLens 2, como Microsoft Office, com o novo navegador Microsoft Edge. | Utilizador Final |
[Passe para escrever](#swipe-to-type) | Use a ponta do dedo para "passar" palavras no teclado holográfico. | Utilizador Final |
[Menu de energia a partir do início](#power-menu-from-start) | No Menu Iniciar, reinicie e desligue HoloLens dispositivo. | Utilizador Final |
[Vários utilizadores listados no Sinal no ecrã](#multiple-users-listed-on-sign-in-screen) | Apresentar várias contas de utilizador no ecrã 'Sinal'. | Utilizador Final |
[Suporte externo do microfone USB-C](#usb-c-external-microphone-support) | Utilize microfones USB-C para aplicações e/ou Assistência Remota. | Utilizador Final |
[Visitante Auto-logon para quiosques](#visitor-auto-logon-for-kiosks) | Permite que o início de sítido automático nas contas do Visitante seja utilizado para os modos quiosque. | Administrador de TI |
[Novos AUMIDs para novas apps em modo Quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs para novas aplicações Definições e Edge. | Administrador de TI |
[Falha no modo quiosque melhorada](#kiosk-mode-behavior-changes-for-handling-of-failures) | O modo quiosque procura o Global Assigned Access antes do menu inicial vazio. | Administrador de TI |
[Novas definiçõesURIs para visibilidade Definições página](#new-settings-uris-for-page-settings-visibility) | 20+ novas DefiniçõesURIs para a política Definições/PageVisibilityList. | Administrador de TI |
[Configurar diagnósticos de recuo](#configuring-fallback-diagnostics-via-settings-app) | Definição do comportamento de diagnóstico do recuo na aplicação Definições. | Administrador de TI |
[Partilhar coisas com dispositivos próximos](#share-things-with-nearby-devices) | Partilhe ficheiros ou URLs de uma HoloLens para um PC. | Todos |
[Novos vestígios de diagnóstico de SO](#new-os-diagnostic-traces) | Novo resolução de problemas em Definições para atualizações do SO. | Administrador de TI |
[Pré-visualização da otimização de entregas](#delivery-optimization-preview) | Reduza o consumo de largura de banda para downloads de vários dispositivos HoloLens. | Administrador de TI |

Confira as notas de lançamento relacionadas:

- [Visite o arquivo HoloLens Emulator](/windows/mixed-reality/hololens-emulator-archive)
- [Dinâmico 365 Assistência Remota](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dinâmica 365 Guias](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Apresentamos o novo Microsoft Edge

![Animação do logotipo Microsoft Edge do legado para o novo logotipo Microsoft Edge](images/new-edge.gif)

O novo Microsoft Edge [adota o projeto de código aberto Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) para criar uma melhor compatibilidade para os clientes e menos fragmentação da web para os desenvolvedores web.

> [!IMPORTANT]
> Esta nova Microsoft Edge substitui automaticamente o legado Microsoft Edge, que [já não](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) é suportado em novas versões.

![Imagem de nova Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Lançamento do novo Microsoft Edge

O novo Microsoft Edge ![novo ícone de Microsoft Edge](images/new_edge_logo.png) (representado por um ícone de redemoinho azul e verde) está fixado ao menu Iniciar e será automaticamente lançado quando ativar uma ligação web.

> [!NOTE]
> Quando lançar pela primeira vez o novo Microsoft Edge no dia 2 HoloLens, as suas definições e dados serão importados do legado Microsoft Edge. Se continuar a utilizar o legado Microsoft Edge depois de lançar o novo Microsoft Edge, esses novos dados não serão sincronizados desde o legado Microsoft Edge até ao novo Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configurar definições de política para o novo Microsoft Edge

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

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>O que esperar do novo Microsoft Edge no dia 2 HoloLens

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

**Principais problemas conhecidos do navegador:**

- A pré-visualização do amplificador no teclado holográfico foi desativada para o novo Microsoft Edge. Esperamos recuperar esta funcionalidade numa futura atualização, uma vez que a ampliação esteja a funcionar corretamente.
- O áudio pode ser reproduzido a partir da janela do navegador errado se tiver outra janela do navegador aberta e ativa. Podes contornar este problema fechando a outra janela ativa que não devia estar a reproduzir áudio.
- Ao reproduzir áudio a partir de uma janela do navegador no [modo "Siga-me",](hololens2-basic-usage.md#follow-me-stop-following)o áudio continuará a reproduzir se desativar o modo "Siga-me". Pode contornar este problema interrompendo a reprodução áudio antes de desativar o modo "Siga-me" ou fechando a janela com o botão **X.**
- Interagir com janelas Microsoft Edge ativas pode fazer com que outras janelas de aplicações 2D fiquem inativas inesperadamente. Pode reativar estas janelas interagindo novamente com elas.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Canais privilegiados

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

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Usar o WDAC para bloquear novas Microsoft Edge

Para os Administradores de TI que pretendam atualizar a sua [política WDAC](windows-defender-application-control-wdac.md) para bloquear a nova aplicação Microsoft Edge, terá de adicionar o seguinte à sua política.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gerir pontos finais para o novo Microsoft Edge

Alguns ambientes podem ter restrições de rede para explicar como uma consideração. Para garantir uma experiência suave com o novo Edge, por [favor, ative estes pontos finais da Microsoft.](/deployedge/microsoft-edge-security-endpoints)

Leia mais sobre os [pontos finais](hololens-offline.md)atualmente disponíveis para HoloLens .

### <a name="install-web-apps"></a>Instalar aplicativos web
 > [!Note]
>A partir de [Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)a aplicação web Office deixará de ser pré-instalada.

Pode utilizar o novo Edge para instalar aplicações web ao lado de aplicações Microsoft Store. Por exemplo, pode instalar a aplicação web Microsoft Office para visualizar e editar ficheiros alojados no SharePoint ou OneDrive. Para instalar a Office aplicação web, visite https://www.office.com e selecione a **app Disponível** ou **instale o** botão Office na barra de endereços. **Selecione Instalar** para confirmar.

> [!IMPORTANT]
> Office funcionalidade da aplicação web só está disponível quando o seu HoloLens 2 tem uma ligação ativa à Internet.

### <a name="webxr-and-360-viewer"></a>WebXR e 360 Espectador

O novo Microsoft Edge inclui suporte para o WebXR, que é o novo padrão para criar experiências web imersivas (substituindo o WebVR). Muitas experiências web imersivas foram projetadas com VR em mente (substituem o seu campo de visão por um ambiente virtual), mas essas experiências também são apoiadas por HoloLens 2. O padrão WebXR também permite experiências web imersivas de realidade aumentada e mista que usam o seu ambiente físico. À medida que os desenvolvedores passam mais tempo com o WebXR, antecipamos novas experiências imersivas de realidade aumentada e mista que chegarão para HoloLens 2 clientes experimentarem!

A extensão 360 Viewer é construída no WebXR e instala-se automaticamente ao lado do novo Microsoft Edge no HoloLens 2. Esta extensão web dá-lhe a capacidade de mergulhar em vídeos de 360 graus. O YouTube oferece a maior seleção de 360 vídeos, por isso encorajamo-lo a começar por aí.

#### <a name="how-to-use-webxr"></a>Como utilizar o WebXR

1. Navegue para um site com suporte WebXR.
1. Selecione o botão **Enter VR** no site. A localização e representação visual deste botão podem variar por website, mas pode parecer semelhante a:

    ![Introduza o exemplo do botão VR](images/75px-enter-vr.png)

1. A primeira vez que tentar lançar uma experiência WebXR num domínio específico, o navegador pedirá consentimento para introduzir uma vista imersiva, selecione **Permitir**.
1. Use [HoloLens 2 gestos](hololens2-basic-usage.md#the-hand-tracking-frame) para manipular a experiência.
1. Se a experiência não tiver um botão **De saída,** use o [gesto Iniciar](hololens2-basic-usage.md#start-gesture) para regressar a casa.

**Amostras webXR recomendadas**
- 360 Espectador (ver secção seguinte)
- [Dinossauros XR](https://www.xrdinosaurs.com/)
- [Expresso Barista](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Como usar o Espectador 360

1. Navegue para um vídeo de 360 graus no YouTube.
1. Na moldura de vídeo, selecione o botão de auscultador de realidade mista:

    ![Botão para ativar 360 Espectador](images/enter-360-viewer.jpg)

1. A primeira vez que tentar lançar o 360 Viewer num domínio específico, o navegador pedirá consentimento para introduzir uma vista imersiva. **Selecione Permitir**.
1. [Toque de ar](hololens2-basic-usage.md#select-using-air-tap) para aumentar os controlos de reprodução. Utilize [raios de mão e toque de ar](hololens2-basic-usage.md#select-using-air-tap) para reproduzir/fazer pausa, saltar para a frente/para trás, ligar/desligar as legendas ou parar a experiência (que sai da vista imersiva). Os controlos de reprodução desaparecerão após alguns segundos de inatividade.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Top WebXR e 360 Espectadores conhecidos problemas conhecidos
- Dependendo da complexidade da experiência WebXR, o framerate pode cair ou gaguejar.
- O suporte para articulações articuladas nas articulações de mão no WebXR não é ativado por padrão. Os desenvolvedores podem ativar o suporte através `edge://flags` da ativação "WebXR Hand Input".
- 360 vídeos de sites que não o YouTube podem não funcionar como esperado.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Fornecendo feedback no WebXR e 360 Viewer

Por favor, partilhe feedback e bugs com a nossa equipa através da funcionalidade **Enviar feedback** na nova Microsoft Edge.

### <a name="new-settings-app"></a>App New Definições

Com este lançamento, estamos a introduzir uma nova versão da aplicação Definições. A nova aplicação Definições inclui novas funcionalidades e configurações expandidas para HoloLens 2 nas seguintes áreas: Som, Energia & sono, Rede & Internet, Apps, Contas, Facilidade de Acesso e muito mais.

> [!NOTE]
> Uma vez que a nova aplicação Definições é distinta da aplicação legacy Definições, qualquer Definições janelas que tenha colocado anteriormente em torno do seu ambiente será removida após a atualização.

![Página inicial da aplicação new Definições](images/new-settings-app.png)

**Novas funcionalidades e configurações**
- Definições pesquisa: procure configurações a partir da página inicial Definições usando palavras-chave ou o nome da definição.
- Som > do sistema:
  - Dispositivos de áudio de entrada e saída: escolha independentemente os seus dispositivos de áudio de entrada e saída (por exemplo, ouça áudio através de auscultadores Bluetooth ou utilize um microfone USB-C para entrada de áudio).
    > [!NOTE]
    > Bluetooth microfones não são suportados por HoloLens 2.
  - Volume de aplicação: ajuste de forma independente o volume de cada aplicação. Consulte [por controlo de volume de aplicação](#per-app-volume-control).
- Sistema > O & o sono: escolha quando o dispositivo deve ir dormir após um período de inatividade.
- Sistema > Bateria: ativar manualmente o modo de poupança de bateria ou definir um limiar de bateria em que o modo de poupança de bateria se liga automaticamente.
- Dispositivos > USB: pode desativar as ligações USB por defeito.
- Rede & Internet:
  - Os adaptadores USB-C Ethernet vão agora aparecer na Rede & Internet.
  - As definições do adaptador USB-C Ethernet já estão disponíveis, incluindo o seu endereço IP.
  - Agora pode ativar o modo avião no HoloLens 2.
- Aplicações: pode redefinir as aplicações predefinidos utilizadas para tipos de ficheiros e ligações. Para obter mais informações consulte [o selecionador de aplicações Predefinido.](#default-app-picker)
- Contas > Outros utilizadores: os proprietários de dispositivos podem adicionar utilizadores, atualizar os utilizadores padrão aos proprietários dos dispositivos, reduzir os proprietários de dispositivos para utilizadores padrão e remover os utilizadores.
- Facilidade de acesso: alterar o tamanho do texto e alguns efeitos visuais.

**Problemas conhecidos**
- As janelas Definições previamente colocadas serão removidas (ver nota acima).
- Já não é possível mudar o nome do seu dispositivo com a aplicação Definições. Os administradores de TI podem renomear os dispositivos utilizando o Windows Autopilot para HoloLens modelo de nome do dispositivo [2](hololens2-autopilot.md) ou o nó [DEDSP CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName DOM.
- A página Ethernet mostra sempre um dispositivo Ethernet virtual ("UsbNcm") em todos os momentos.
- O uso da bateria para o novo Microsoft Edge pode não ser exato, devido à sua natureza como uma aplicação de ambiente de trabalho Win32 suportada por uma camada de adaptador UWP (nenhuma correção antecipada em breve).

#### <a name="display-color-calibration"></a>Mostrar calibração de cores



Com esta nova definição, pode selecionar um perfil de cores alternativo para o seu ecrã HoloLens 2. Isto pode ajudar as cores a parecerem mais precisas, especialmente em níveis de luminosidade de ecrã mais baixos. A calibração da cor do ecrã pode ser encontrada na aplicação Definições, na página de Calibração system >.

> [!NOTE]
> Uma vez que esta definição guarda um novo perfil de cores para o firmware do ecrã, é uma definição por dispositivo (e não única em cada conta de utilizador).

##### <a name="how-to-use-display-color-calibration"></a>Como usar a calibração da cor do ecrã

1. Lançar a app **Definições** e navegar para **a Calibração > Do Sistema.**
1. Na **calibração da cor do Display,** selecione o botão **de calibração da cor do ecrã Run.**
1. A experiência de calibração da cor do visor será lançada e encoraja-o a certificar-se de que a sua viseira está na posição correta.
1. Depois de proceder através das caixas de diálogo de instruções, o seu visor será automaticamente diminuído para 30% de luminosidade.
    > [!TIP]
    > Se tiver dificuldades em ver a cena escurecida no seu ambiente, pode ajustar manualmente o nível de luminosidade do HoloLens 2 utilizando os botões de luminosidade no lado esquerdo do dispositivo.
1. Selecione os botões 1-6 para experimentar instantaneamente cada perfil de cor, e encontre um que fique melhor para os seus olhos (isto geralmente significa o perfil que ajuda a cena a parecer mais neutro, com o padrão em tons de cinza e a pele a parecerem esperados.)

    ![Cena de calibração de cores de exibição](images/color-cal-ui.png)
    
1. Quando estiver satisfeito com o perfil selecionado, selecione o botão **'Saída &'**
1. Se preferir não fazer alterações, selecione o botão **'Cancelar & Saída'** e as alterações serão revertidas

> [!TIP]
> Aqui ficam algumas dicas úteis a ter em mente durante a utilização da definição de calibração da cor do ecrã:
> - Pode re-executar a calibração de cor do ecrã a partir de Definições sempre que quiser
> - Se alguém no dispositivo tiver usado previamente a definição para alterar perfis de cor, a data/hora da alteração mais recente será refletida na página Definições
> - Quando voltar a executar a calibração de cores do ecrã, o perfil de cor que foi previamente guardado será realçado e o Perfil 0 não aparecerá (uma vez que o Perfil 0 representa o perfil de cor original do visor)
> - Se quiser reverter para o perfil de cor original do visor, pode fazê-lo a partir da página Definições (ver como redefinir o perfil de [cor)](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Como redefinir o perfil de cor 

Se estiver insatisfeito com o perfil de cor personalizado guardado para o seu HoloLens 2, pode restaurar o perfil de cor original do dispositivo:
1. Lançar a app **Definições** e navegar para **a Calibração > Do Sistema.**
1. Na **calibração da cor do Display,** selecione o botão reset para o **perfil de cores predefinido.**
1. Quando a caixa de diálogo abrir, selecione **Reiniciar** se estiver pronto para reiniciar HoloLens 2 e aplicar as suas alterações.

#### <a name="top-display-color-calibration-known-issues"></a>Principais problemas de calibração de cores de ecrã

- Na página Definições, a cadeia de estado que lhe diz quando o perfil de cor foi alterado ficará desatualizada até recarregar a página de Definições.
    - Solução: Selecione outra página Definições e, em seguida, reescoria a página de Calibração.

#### <a name="default-app-picker"></a>Selecionador de aplicativos predefinido

Quando ativar uma hiperligação ou abrir um tipo de ficheiro com mais de uma aplicação instalada, que a suporta, verá uma nova janela aberta, levando-o a selecionar qual a aplicação instalada que deve lidar com o ficheiro ou o tipo de ligação. Nesta janela, também pode optar por ter a aplicação selecionada a manusear o ficheiro ou o tipo de ligação "Uma vez" ou "Sempre".

Se escolher "Always" mas mais tarde quiser alterar qual a aplicação que lida com um determinado ficheiro ou tipo de ligação, pode redefinir as suas predefinições guardadas em **Definições > Apps**. Desloque-se para a parte inferior da página e selecione o botão **Limpar** em "Aplicações predefinidos para tipos de ficheiros" e/ou "Aplicações predefinidos para tipos de ligação". Ao contrário da definição semelhante nos computadores de secretária, não é possível redefinir os predefinidos individuais do tipo de ficheiro.

#### <a name="per-app-volume-control"></a>Por controlo de volume de aplicações

Agora, nesta construção Windows, os utilizadores podem ajustar manualmente o nível de volume de cada aplicação. Isto permite que os utilizadores se concentrem melhor nas apps que precisam, ou melhor ouvir quando usam várias apps. Como a necessidade de diminuir o volume de uma aplicação enquanto chama outra pessoa para assistência remota noutra.

Para definir o volume de uma aplicação individual navegue para **Definições**  ->  **System**  ->  **Sound**, e em opções de som avançadas selecione **volume de aplicação e preferências do dispositivo**.<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Passe para escrever

Alguns clientes acham mais rápido "escrever" em teclados virtuais, deslizando a forma da palavra que pretendem escrever, e estamos a visualizar esta funcionalidade para o teclado holográfico. Pode passar uma palavra de cada vez passando a ponta do seu dedo através do plano do teclado holográfico, deslizando a forma da palavra e, em seguida, retirando a ponta do seu dedo do plano do teclado. Pode passar palavras de seguimento sem precisar de pressionar a barra espacial removendo o dedo do teclado entre as palavras. Saberá que a funcionalidade está a funcionar se vir um rasto de swipe seguindo o movimento do dedo no teclado.

Por favor, note que esta funcionalidade pode ser complicada de usar e dominar devido à natureza de um teclado holográfico onde não sente resistência contra o dedo (ao contrário de um ecrã de telemóvel). 

### <a name="power-menu-from-start"></a>Menu de energia a partir do início

Um novo menu que permite ao utilizador assinar, desligar e reiniciar o dispositivo. Um indicador no ecrã start HoloLens que mostra quando uma atualização do sistema está disponível.

#### <a name="how-to-use"></a>Como utilizar

1. Abra o ecrã iniciar HoloLens usando o [gesto Iniciar](hololens2-basic-usage.md#start-gesture) ou dizendo "Vai para começar".

2. Note o ícone de elipsis (...) ao lado da imagem do perfil do utilizador:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Selecione a imagem do perfil do utilizador utilizando as mãos ou o comando de voz "Power".

4. Um menu aparece com opções para iniciar, reiniciar ou desligar o dispositivo:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Selecione as opções do menu para iniciar, reiniciar ou desligar o seu HoloLens. A opção Sign out pode não estar disponível, se o dispositivo estiver configurado para uma [única Conta Microsoft (MSA) ou conta local](hololens-identity.md).

6. Desprezem o menu tocando em qualquer outro lugar ou fechando o menu Iniciar com o gesto Iniciar.

#### <a name="update-indicator"></a>Indicador de atualização

Quando uma atualização estiver disponível, o ícone da elipse acende-se para indicar que um reinício irá instalar a atualização As opções do menu também mudam para refletir a presença da atualização.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Vários utilizadores listados no Sinal no ecrã

Anteriormente, o ecrã Sign In apresentava apenas o mais recentemente assinado no utilizador, bem como um ponto de entrada "Outro utilizador". Recebemos o feedback do cliente de que isso não é suficiente se vários utilizadores se inscreverem no dispositivo. Ainda eram obrigados a reescrever o seu nome de utilizador, etc.

Introduzido neste Windows construção, ao selecionar **Outro utilizador** que está localizado à direita do campo de entrada PIN, o Sinal no ecrã apresentará vários utilizadores com o qual já se tenham inscrito no dispositivo. Isto permite que os utilizadores selecionem o seu perfil de utilizador e, em seguida, inscrevam-se utilizando as suas credenciais de Windows Hello. Um novo utilizador também pode ser adicionado ao dispositivo a partir desta página de Outros utilizadores através do botão **de conta Adicionar.**

Quando estiver no menu Outros utilizadores, o botão Outros utilizadores apresentará o último utilizador assinado no dispositivo. Selecione este botão para voltar ao Sinal no ecrã para este utilizador.

![Predefinição do ecrã de inscrição](./images/multiusers1.jpg)

<br>

![Ecrã de inscrição de outros utilizadores](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Suporte externo do microfone USB-C

> [!IMPORTANT]
> A ligação **de um microfone USB não o definirá automaticamente como o dispositivo de entrada**. Ao ligar um conjunto de auscultadores USB-C, os utilizadores observarão que o áudio do auscultador será automaticamente redirecionado para os auscultadores, mas o HoloLens OS prioriza a matriz interna do microfone acima de qualquer outro dispositivo de entrada. **Para utilizar um microfone USB-C, siga os passos abaixo.**

Os utilizadores podem selecionar microfones externos ligados a USB-C utilizando o painel de definições **de som.** Os microfones USB-C podem ser utilizados para chamadas, gravações, etc.

Abra a aplicação **Definições** e selecione **System**  >  **Sound**.

![Som Definições](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para utilizar microfones externos com **Assistência Remota,** os utilizadores terão de clicar na hiperligação "Gerir dispositivos de som".
>
> Em seguida, utilize o drop-down para definir o microfone externo como **Predefinido** ou **Padrão de Comunicações.** Escolher **o Predefinido** significa que o microfone externo será utilizado em todo o lado.
>
> Escolher o **Padrão de Comunicações** significa que o microfone externo será utilizado em aplicações de Assistência Remota e outras aplicações de comunicações, mas o HoloLens conjunto de microfones ainda pode ser usado para outras tarefas.

![Gerir dispositivos de som](images/usbc-mic-2.png)

<br>

![Definir padrão do microfone](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>E Bluetooth suporte ao microfone?

Infelizmente, Bluetooth microfones ainda não estão suportados no HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Resolução de problemas dos microfones USB-C

Esteja ciente de que alguns microfones USB-C se reportam incorretamente como um microfone *e* um altifalante. Este é um problema com o microfone e não com HoloLens. Ao ligar um destes microfones a HoloLens, o som pode perder-se. Felizmente, há uma solução simples.  

No **Definições**  ->  **System**  ->  **Sound,** coloque explicitamente os altifalantes incorporados **(Controlador de áudio de recurso analógico)** como o **dispositivo Predefinido**. HoloLens deve lembrar-se desta definição mesmo que o microfone seja removido e reconectado mais tarde.

![Resolução de problemas dos microfones USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Início de visita Auto para quiosques

Esta nova funcionalidade permite que a apresentação automática nas contas do Visitante seja utilizada para os modos quiosque.

Para uma configuração não-AAD, para configurar um dispositivo para o visitante automaticamente logon:

1. Criar um pacote de provisionamento que:
    1. Configurações de **tempo de execução/Atribuição De Acesso** para permitir contas do Visitante.
    1. Inativamente inscreve o dispositivo em MDM **(definições de tempo de execução/Local de Trabalho/Inscrições)** para que possa ser gerido mais tarde.
    1. Não crie uma conta local
1. [Aplicar o pacote de provisionamento.](hololens-provisioning.md)

Para uma configuração AAD, os utilizadores podem alcançar algo semelhante a isso hoje sem esta alteração. Os dispositivos de aad configurados para o modo quiosque podem assinar numa conta do Visitante com um único toque de botão a partir do sinal no ecrã. Uma vez iniciado na conta do visitante, o dispositivo não solicitará novamente o início até que o Visitante seja explicitamente assinado a partir do menu inicial ou o dispositivo seja reiniciado.

O início de sísmis do Visitor Auto pode ser gerido através da política [personalizada OMA-URI:](/mem/intune/configuration/custom-settings-windows-10)

- Valor URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Política  | Description   | Configurações  |
|---|---|---|
| Realidade Mista/VisitanteAutoLogon  | Permite um visitante a passar por um quiosque   | 1 (Sim), 0 (Não, padrão.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Use as novas aplicações Definições e Edge nos modos Kiosk

Ao incluir aplicações em quiosques, um administrador de TI [muitas vezes](hololens-kiosk.md)adiciona a aplicação ao Quiosque, mas utilizando o seu ID de Modelo de Utilizador de Aplicações (AUMID). Uma vez que tanto a aplicação Definições como Microsoft Edge aplicação são consideradas novas apps e diferentes das aplicações mais antigas, os quiosques que utilizam AUMIDs para essas aplicações terão de ser atualizados para utilizar o novo AUMID.

Ao modificar um quiosque para incluir as novas aplicações, recomendamos adicionar o novo AUMID, bem como sair da antiga. Isto criará uma transição fácil quando os utilizadores atualizarem o SO e não precisarem de receber novas políticas para continuarem a utilizar o Quiosque como pretendido.

| Aplicação                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| App old Definições       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Nova app de Definições       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Aplicativo de Microsoft Edge antigo | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| App new Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Mudanças de comportamento no modo quiosque para lidar com falhas

Em construções mais antigas, se um dispositivo tivesse uma configuração de quiosque, que é uma combinação de acesso global atribuído e membro do grupo AAD atribuído acesso, se determinar a adesão ao grupo AAD falhou, o utilizador veria "[nada mostrado no](hololens-kiosk.md#kiosk-mode-behavior-changes-for-handling-of-failures)menu inicial ".

A partir deste Windows lançamento, a experiência do quiosque irá recorrer à configuração global do quiosque (se presente) em caso de falhas durante o modo quiosque do grupo AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>UrIs de nova Definições para visibilidade Definições página

Em [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) adicionamos a [política Definições/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas dentro da aplicação Definições. PageVisibilityList é uma política que permite que os administradores de TI impeçam que páginas específicas no Sistema Definições aplicação sejam visíveis ou acessíveis, ou que o façam para todas as páginas, exceto as especificadas.

Se visitar [a Página Definições Visibilidade,](settings-uri-list.md)pode encontrar instruções para utilizar este CSP e a lista de URIs disponíveis em versões anteriores.

Estamos a expandir a lista de Definições URIs disponíveis, que os administradores de TI podem gerir. Algumas destas URIs são para áreas recém-disponíveis dentro da nova app Definições. Se estiver a utilizar a política Definições/PageVisibilityList, reveja a seguinte lista e ajuste as páginas permitidas ou bloqueadas conforme necessário.

> [!NOTE]
> **Precado: ms-settings:network-proxy**
>
> Uma página de definições é depreciada nestas construções mais recentes. A antiga **página de Proxy da Rede & Internet** já não está  >   disponível como um cenário global. As novas definições de procuração por ligação podem ser encontradas na **Rede &** propriedades  >  **Wi-Fi** da Internet ou na Rede &  >   **Internet**  >  **Ethernet**  >  **Properties**.

<br>

| Página de definições                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Apps > apps & funcionalidades                               | `ms-settings:appsfeatures`                         |
| Apps > Apps & funcionalidades > Opções Avançadas          | `ms-settings:appsfeatures-app`                     |
| Apps > mapas offline                                  | `ms-settings:maps`                                 |
| Apps > mapas offline > mapas de descarregamento                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivos > Rato                                      | `ms-settings:mouse`                                |
| Dispositivos > USB                                        | `ms-settings:usb`                                  |
| Rede & Internet > Modo avião                   | `ms-settings:network-airplanemode`                 |
| Privacidade > Geral                                    | `ms-settings:privacy-general`                      |
| Privacidade > a & a personalização dactilografia             | `ms-settings:privacy-speechtyping`                 |
| Movimento > de Privacidade                                     | `ms-settings:privacy-motion`                       |
| Privacidade > fronteiras de Screenshot                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Imagems e aplicativos privacy >                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Bateria > do sistema                                     | `ms-settings:batterysaver`                         |
| Bateria > do sistema                                     | `ms-settings:batterysaver-settings`                |
| Som > do sistema                                       | `ms-settings:sound`                                |
| System > Sound > As preferências de aplicações e dispositivos | `ms-settings:apps-volume`                          |
| Sistema > > de som Gerencie dispositivos de som              | `ms-settings:sound-devices`                        |
| Configurar > Armazenamento > sistema Armazenamento Sense         | `ms-settings:storagepolicies`                      |
| Data > & linguagem & do tempo                        | `ms-settings:dateandtime`                          |
| Teclado > de linguagem & tempo                           | `ms-settings:keyboard`                             |
| Linguagem & tempo >                           | `ms-settings:language`                             |
| Linguagem & tempo >                           | `ms-settings:regionlanguage-languageoptions`       |
| Atualização & > de segurança repor a recuperação &               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URIs atualizados

Anteriormente, os dois URIs seguintes não levariam um utilizador diretamente para as páginas indicadas, mas apenas bloqueavam a página principal de atualizações. Os seguintes itens foram atualizados para dirigir para as suas páginas:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configurar diagnósticos de retorno de outono através de Definições app

Agora, na Definições App, um utilizador pode configurar o comportamento do [Diagnóstico de Retorno.](hololens-diagnostic-logs.md) Na Definições aplicação navegar para a página  ->  **de resolução de problemas de** privacidade para configurar esta definição.

> [!NOTE]
> Se houver uma política de MDM configurada para o dispositivo, o utilizador não poderá anular esse comportamento.  

### <a name="share-things-with-nearby-devices"></a>Partilhar coisas com dispositivos próximos

Partilhe coisas com dispositivos de Windows 10 próximos, incluindo computadores e outros dispositivos HoloLens 2. Pode experimentá-lo em **Definições**  ->    ->  **Experiências Partilhadas** do Sistema para partilhar ficheiros ou URLs de uma HoloLens para um PC. Para mais detalhes, leia mais sobre como [partilhar as coisas com dispositivos próximos em Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Esta funcionalidade pode ser gerida através [da Conectividade/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Novos vestígios de diagnóstico de SO

Além dos anteriores troubleshooters dentro da aplicação Definições, foi adicionado um novo troubleshooter com a adição da nova app Definições para atualizações do OS. Navegue para **Definições**  ->  atualizar a resolução **&amp; de**  >  **problemas** de segurança  >  **Windows atualização** e selecione **Start**. Isto permite-lhe recolher vestígios enquanto reproduz o seu problema com as Atualizações de OS para ajudar melhor na resolução de problemas com o seu TI ou suporte.

### <a name="delivery-optimization-preview"></a>Pré-visualização da otimização de entregas

Com esta HoloLens atualização, Windows Holographic for Business permite configurações de otimização de entrega para reduzir o consumo de largura de banda para downloads de vários dispositivos HoloLens. Uma descrição mais completa desta funcionalidade juntamente com a configuração recomendada da rede está disponível aqui: [Otimização de Entrega para atualizações Windows 10](/windows/deployment/update/waas-delivery-optimization).

As seguintes definições são ativadas como parte da superfície de gestão e [podem ser configuradas a partir de Intune](/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Algumas ressalvas sobre esta oferta de pré-visualização:

- HoloLens suporte é limitado apenas nesta pré-visualização às atualizações do SO.
- Windows Holographic for Business suporta apenas os modos de descarregamento HTTP e downloads a partir de um ponto final da [Cache Conectada microsoft](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); os modos de descarregamento peer-to-peer e as atribuições de grupo não são suportados para dispositivos HoloLens neste momento.
- HoloLens não suporta a otimização de implementação ou entrega para Windows Server Update Services pontos finais.
- A resolução de problemas requer diagnósticos no servidor Cache Conectado ou a recolha de vestígios de HoloLens no HoloLens através **de Definições**  >  **Atualização &**  >   **resolução de problemas de** segurança  >   **Windows Update**.

### <a name="it-admin---update-checklist"></a>Administração de TI - Lista de Verificação de Atualização

Esta lista de verificação irá ajudá-lo a conhecer os novos itens que estão a ser adicionados nesta atualização de funcionalidade que pode afetar as configurações de gestão do dispositivo atuais, ou novas funcionalidades que poderá pretender começar a utilizar.

#### <a name="updates-to-kiosk-mode"></a>Atualizações para o modo quiosque

✔️ Novos [**AUMIDs para novas aplicações no modo Kiosk:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Se anteriormente estava a usar a app Definições ou Microsoft Edge app num Quiosque, substituímos estas aplicações por novas apps que utilizam um ID de aplicações diferente. Encorajamo-lo a ler [Novos AUMIDs para novas aplicações no modo Quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes) abaixo. Isto irá garantir que ou continua a ter a aplicação Definições no seu Quiosque, ou inclui a nova app Microsoft Edge. Estas alterações podem ser feitas agora e implementadas em todos os dispositivos e permitem uma transição mais suave na atualização.

✔️ visitor [**auto-logon para quiosques:**](#visitor-auto-logon-for-kiosks) 

Os visitantes podem agora ser automaticamente acedidos a um quiosque. Este comportamento é por defeito, mas pode ser gerido e desativado.

✔️ [**falha do modo quiosque melhorado:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Se a adesão do grupo AAD ao utilizador AAD não for determinada com sucesso, então a configuração global do quiosque é usada para o menu inicial (se presente) caso contrário, o utilizador é apresentado com menu de início vazio. Embora o menu inicial vazio não seja uma configuração que possa definir diretamente, este novo manuseamento pode ser algo para informar o seu departamento de suporte de se estiver a utilizar quiosques, uma vez que isso pode aplicar-se às suas configurações ou pode querer fazer novos ajustes nas configurações de acesso atribuídas.

#### <a name="updates-to-page-settings-visibility"></a>Atualizações para página Definições visibilidade

✔️ [**URIs nova Definições para visibilidade Definições página**](#new-settings-uris-for-page-settings-visibility)

Se estiver atualmente a utilizar [a Página Definições Visibilidade,](settings-uri-list.md) então poderá desejar fazer ajustes nos URIs existentes que permitiu ou bloqueou.

#### <a name="updates-for-your-wdac-policy"></a>Atualizações para a sua política WDAC
✔️ Se já estava a bloquear Microsoft Edge via WDAC, vai querer atualizar a sua política do WDAC. Por favor, reveja o seguinte e use o código de amostra fornecido.
#### <a name="enable-new-endpoints-for-edge"></a>Ativar novos pontos finais para edge
✔️ Se tiver uma infraestrutura que envolva configurar pontos finais de rede como proxy ou firewall, por favor, ative estes novos pontos finais para a nova aplicação Microsoft Edge.

#### <a name="newly-configurable-items"></a>Itens recentemente configuráveis

✔️ [Configurar diagnósticos de recuo](#configuring-fallback-diagnostics-via-settings-app): Pode configurar se e quem pode recolher Diagnósticos de Recuo.

✔️ Partilhe[coisas com dispositivos próximos](#share-things-with-nearby-devices): Pode desativar a nova funcionalidade de partilha nas proximidades.

✔️ [Configurar definições políticas para o novo Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge): Reveja as novas configurações disponíveis para Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nova ferramenta de diagnóstico

✔️[novos vestígios de diagnóstico do SO](#new-os-diagnostic-traces): Recolher registos relacionados com atualizações do SISTEMA.

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- [Os diagnósticos offline](hololens-diagnostic-logs.md#offline-diagnostics) também incluirão informações adicionais do dispositivo para o número de série e versão OS.
- Corrige um problema em torno da implementação de linhas de aplicações empresariais através de pacotes de provisionamento de tempo de execução.
- Corrige um problema em torno da linha de relatórios de estado de instalação de aplicações empresariais.
- Corrige um problema em torno da persistência de novos pacotes de aplicações através de resets de dispositivos.
- Corrige um problema que pode levar a que símbolos incorretos sejam digitado em Edge para clientes japoneses.
- Melhora a resiliência das atualizações de SO em torno de aplicações pré-instaladas, como o Edge. 
- Aborda uma fiabilidade de atualização com impacto na instalação de Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holográfico, versão 20H2 – Atualização de maio de 2021
- Construção 19041.1146

Melhorias e correções na atualização:
- Esta atualização mensal de qualidade não contém quaisquer alterações notáveis, encorajamos-te a experimentar a nossa mais recente construção, Windows Holographic, versão 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holográfico, versão 1903 - Atualização de maio de 2021
- Construção 18362.1110

Melhorias e correções na atualização:
- Esta atualização mensal de qualidade não contém alterações notáveis. **Esta construção deixará de receber atualizações mensais de serviços.** Encorajamo-lo a experimentar a nossa mais recente construção, Windows Holographic, versão 21H1.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holográfico, versão 20H2 - Atualização abril 2021
- Construção 19041.1144

Melhorias e correções na atualização:

- Corrige um problema em torno da linha de relatórios de estado de instalação de aplicações empresariais.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holográfico, versão 1903 - Atualização abril 2021
- Construção 18362.1108

Melhorias e correções na atualização:

- Aborda um problema em que a aplicação Definições falha ao tentar alterar uma palavra-passe para uma conta local.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holográfico, versão 20H2 - março 2021 Atualização
- Construção 19041.1140

Melhorias e correções na atualização:

- Os clientes que usam AdvancedPhotoCapture ou LowLagPhotoCapture para capturar fotos com HoloLens 2 são agora capazes de recuperar a pose da câmara até 3 segundos após a foto ter sido capturada.
- Correção de uma fuga de memória no Serviço portal do Dispositivo, o problema causou um aumento do uso da memória pelo serviço que fez com que outras aplicações falhassem na alocação de memória.
- Corrigiu um problema em que os utilizadores inscritos no Lançamento Encenado não conseguem entrar no dispositivo.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holográfico, versão 1903 - março 2021 Atualização
- Construção 18362.1102

Melhorias e correções na atualização:

- Correção de uma fuga de memória no Serviço portal do Dispositivo, o problema causou um aumento do uso da memória pelo serviço que fez com que outras aplicações falhassem na alocação de memória.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holográfico, versão 20H2 - Atualização de fevereiro de 2021
- Construção 19041.1136

Melhorias e correções na atualização:

- Corrige um problema em torno da configuração inicial do dispositivo e das atualizações de aplicações da loja.
- Aborda um problema em torno de upgrades e voos para lançamentos posteriores HoloLens.
- Removidos certificados pré-instalados não instalados da loja de raiz eSIM de HoloLens dispositivos.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holográfico, versão 1903 - Atualização de fevereiro de 2021
- Construção 18362.1098

Esta atualização mensal de qualidade não contém quaisquer alterações notáveis, encorajamo-lo a experimentar as nossas mais recentes construções para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holográfico, versão 20H2 - Atualização janeiro 2021
- Construção 19041.1134

Melhorias e correções na atualização:

- Melhor desempenho durante o arranque, currículo e comutação do utilizador quando há muitos utilizadores no dispositivo.
- Apoio arm32 adicionado para [modo de investigação.](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holográfico, versão 1903 - janeiro 2021 Atualização
- Construção 18362.1091

Esta atualização mensal de qualidade não contém quaisquer alterações notáveis, encorajamo-lo a experimentar as nossas mais recentes construções para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holográfico, versão 20H2 – Atualização de dezembro de 2020
- Construção 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instale apps no HoloLens 2 através do Instalador de Aplicações

Estamos **a adicionar uma nova capacidade (App Installer) para permitir a instalação de aplicações de forma mais perfeita** nos seus HoloLens 2 dispositivos. A funcionalidade será **on-by predefinida para dispositivos não geridos**. Para evitar perturbações nas empresas, o instalador de aplicações **não estará disponível para dispositivos geridos** neste momento.  

Um dispositivo é considerado "gerido" se **algum** dos seguintes for verdadeiro:
- MDM [Inscrito](hololens-enroll-mdm.md)
- Configurado com [pacote de provisionamento](hololens-provisioning.md)
- [Identidade](hololens-identity.md) do utilizador é Azure AD

Agora é possível instalar apps sem necessidade de ativar o Modo de Desenvolvimento ou de utilizar o Portal do Dispositivo.  Basta baixar (através de USB ou através do Edge) o Pacote Appx para o seu dispositivo e navegar para o Pacote Appx no Explorador de Ficheiros para ser solicitado para iniciar a instalação.  Em alternativa, [inicie uma instalação a partir de uma página web](/windows/msix/app-installer/installing-windows10-apps-web).  Tal como as aplicações que instala a partir do Microsoft Store ou sideload utilizando a capacidade de implementação da App LOB do MDM, as aplicações precisam de ser assinadas digitalmente com a [Ferramenta de Sinais](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado utilizado para assinar deve ser confiável](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo HoloLens antes de a aplicação poder ser implementada.

**Instruções de instalação da aplicação.**

1.  Certifique-se de que o seu dispositivo não é considerado gerido
1.  Certifique-se de que o seu dispositivo HoloLens 2 está ligado e ligado ao seu PC
1.  Certifique-se de que está inscrito no dispositivo HoloLens 2
1.  No seu PC, navegue para a sua aplicação personalizada e copie o seu appapp.appxbundle para o seu nome dedevicename\Internal Armazenamento\Downloads.   Depois de ter terminado de copiar o seu ficheiro, pode desligar o seu dispositivo
1.  A partir do seu HoloLens 2 dispositivo Abra o Menu Iniciar, selecione Todas as aplicações e lance a aplicação File Explorer.
1.  Navegue para a pasta Downloads. Pode ser necessário no painel esquerdo da aplicação selecionar este dispositivo primeiro e, em seguida, navegar para Downloads.
1.  Selecione o ficheiro appxbundle do seuapp.appxbundle.
1.  O Instalador de Aplicações será lançado. Selecione o botão Instalar para instalar a sua aplicação.
A aplicação instalada será lançada automaticamente após a conclusão da instalação.

Pode encontrar aplicativos de amostras em [Windows GitHub de Amostras Universais](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para testar este fluxo.

Leia sobre o processo completo de instalação de [apps no HoloLens 2 com o Instalador de Aplicações.](app-deploy-app-installer.md)  

![Instalação de exemplos MRTK através do Instalador de Aplicações](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- O rastreio manual mantém-se agora a acompanhar em muitos casos novos onde a mão anteriormente teria sido perdida.  Em alguns destes novos casos, apenas a posição da palma da mão continua a ser atualizada com base na mão real do utilizador, enquanto as outras articulações são deduzidas com base numa pose anterior.  Esta mudança ajuda a melhorar a consistência do rastreio em movimentos como bater, atirar, colher e bater palmas.  Também ajuda nos casos em que a mão está perto de uma superfície ou segurando um objeto.  Quando as articulações das mãos estiverem a ser inferidas, o valor [de precisão por articulação](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) será definido como "Aproximado" em vez de "Alto".
- Corrigiu um problema em que o RESET PIN para as contas AZure AD mostraria um erro "Algo correu mal.
- Os utilizadores devem ver muito menos falhas pós-boot OOBE ao lançar ET, Iris a partir de configurações app, novo utilizador ou torrada de notificação.
- Os utilizadores devem ter um fuso horário correto proveniente do OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holográfico, versão 1903 - Atualização de dezembro de 2020
- Construção 18362.1088

Esta atualização mensal de qualidade não contém quaisquer alterações notáveis, incentivamos-te a experimentar o nosso mais recente Windows Holographic, versão 20H2 – dezembro de 2020 e a nova funcionalidade de Instalação de Aplicações adicionadas na construção.


## <a name="windows-holographic-version-20h2"></a>Windows Holográfico, versão 20H2
- Construção 19041.1128

Windows Holográfico, a versão 20H2 já está disponível e traz um grande conjunto de novas funcionalidades para HoloLens 2 utilizadores e profissionais de TI. Desde o Posicionamento Auto Eye, ao Gestor de Certificados em Definições, à melhoria da funcionalidade do Modo Quiosque e às novas capacidades de configuração do Autopilot. Esta nova atualização permite que as equipas de TI tomem mais controlo granular para configurar e gerir dispositivos HoloLens, e oferece aos utilizadores experiências holográficas ainda mais perfeitas. 

Esta última versão é uma atualização mensal para a versão de 2004, mas desta vez estamos a incluir novas funcionalidades. O maior número de construção permanecerá o mesmo e Windows Update indicará um lançamento mensal para a versão 2004 (build 19041). Pode ver o seu Número de Construção no seu Definições > Sobre o ecrã para confirmar que está na mais recente construção disponível 19041.1128+. Para atualizar para a versão mais recente, abra a aplicação Definições, aceda a Update & Security e toque em Check for Updates. Para obter mais informações sobre como gerir HoloLens atualizações, visite [Gerir HoloLens atualizações](hololens-updates.md).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Novidades em Windows Holographic, versão 20H2  

| Funcionalidade                                              | Descrição                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Suporte à posição dos olhos automáticos](hololens-release-notes.md#auto-eye-position-support) | Calcula ativamente as posições dos olhos sem que os utilizadores passem pela calibração de rastreio de olhos.   |
| [Gestor de Certificados](hololens-release-notes.md#certificate-manager)   | Permite novos métodos mais simples para instalar e remover certificados da aplicação Definições.     |
| [Provisão de lançamento automático a partir de USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | O provisionamento de pacotes em unidades USB solicita automaticamente a página de provisionamento no OOBE.                                                         |
| [Pacotes de provisão automática em OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Os pacotes de provisionamento são automaticamente aplicados durante o OOBE a partir da página de aferição.                                                         |
| [Provisionamento automático sem utilização de UI](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Como combinar o fornecimento automático de lançamento e confirmar automaticamente. |
| [Utilização de Piloto Automático com ligação Wi-Fi](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Utilize o piloto automático do dispositivo Wi-Fi sem necessidade de adaptador ethernet. |
| [Inquilinolockdown CSP e Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Após a inscrição do inquilino e a apólice é aplicada, o dispositivo só pode ser matriculado nesse inquilino sempre que o dispositivo for reiniciado ou re-piscado. |
| [Acesso Global Atribuído](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Novo método de configuração para vários quiosques de aplicações que aplica o quiosque ao nível do sistema, tornando-o aplicável a todos.                  |
| [Lançar automaticamente uma aplicação em quiosque multi-aplicações](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Define uma aplicação para lançar automaticamente ao iniciar uma sessão num modo de quiosque de várias aplicações.                                                        |
| [Mudanças de comportamento no modo quiosque para lidar com falhas](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | A falha no modo quiosque tem agora um recuo restritivo.                                                                                                |
| [HoloLens Políticas](hololens-release-notes.md#hololens-policies)                                    | Novas políticas para HoloLens.     |
| [Adesão ao Grupo AD cache Azure para quiosque offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | A nova política permite que os utilizadores utilizem cache de membros do grupo para utilizar o modo Quiosque offline durante o número definido de dias.                                        |
| [Novas políticas de restrição de dispositivos para HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | As políticas de gestão de dispositivos ativaram-se recentemente para HoloLens 2.                                                                                |
| [Novas políticas de poder para HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Políticas recentemente apoiadas para definições de tempo de energia.  |
| [Atualizar Políticas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Políticas recentemente ativadas que permitem o controlo de atualizações.           |
| [Visibilidade de página de Definições ativada para HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Política para escolher quais páginas são vistas em Definições app.             |
| [Modo de investigação](hololens-release-notes.md#research-mode) | Utilizar o modo de investigação no HoloLens 2. |
| [O comprimento da gravação aumentou](hololens-release-notes.md#recording-length-increased) | As gravações do MRC já não estão limitadas a 5 minutos. |
| [Melhorias e correções na atualização](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correções adicionais na atualização.   |

### <a name="auto-eye-position-support"></a>Suporte à posição dos olhos automáticos

Em HoloLens 2, as posições oculares permitem um posicionamento preciso do holograma, uma experiência de visualização confortável e uma melhor qualidade de exibição. As posições oculares são calculadas internamente como parte da computação de rastreio ocular. No entanto, isto requer que cada utilizador passe por uma calibração de rastreio visual, mesmo quando a experiência pode não necessitar de uma entrada de olhares oculares.

**A Auto Eye Position (AEP)** permite estes cenários com uma forma livre de interação de calcular posições oculares para o utilizador. A Auto Eye Position começa a funcionar automaticamente em segundo plano a partir do momento em que o utilizador coloca o dispositivo. Se o utilizador não tiver uma calibração prévia de rastreio ocular, a Auto Eye Position começará a fornecer as posições oculares do utilizador ao sistema de visualização após um tempo de processamento de 20 a 30 segundos. Os dados do utilizador não são persistidos no dispositivo e, por isso, este processo é repetido se o utilizador levantar e voltar a colocar o dispositivo ou se o dispositivo reiniciar ou acordar do sono.

Existem algumas alterações de comportamento do sistema com a função Auto Eye Position quando um utilizador não calibrado coloca no dispositivo. Neste contexto, um utilizador não calibrado refere-se a alguém que não passou pelo processo de calibração de rastreio ocular no dispositivo anteriormente.

| Aplicação Ativa | Comportamento Anterior | Comportamento de Windows Holographic, versão 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| App não-gaze habilitada ou Concha Holográfica |É apresentado um diálogo de solicitação de calibração de rastreio ocular. | Não é apresentada nenhuma solicitação. |
| App ativada pelo olhar | É apresentado um diálogo de solicitação de calibração de rastreio ocular. | A indicação de calibração do rastreio dos olhos só é apresentada quando a aplicação acede ao fluxo de olhares. |

Se o utilizador transitar de uma aplicação não ativada para uma que aceda aos dados do olhar, o aviso de calibração será apresentado. 

Todos os outros comportamentos do sistema serão semelhantes aos de quando o utilizador atual não tiver uma calibração ativa de rastreio de olhos. Por exemplo, o gesto de arranque com uma mão não será ativado. Não haverá alteração da Experiência Out-Of-Box para a configuração inicial.

Para experiências que requerem dados de olhares oculares ou posicionamento holograma muito preciso, recomendamos que os utilizadores não calibrados para executar a calibração de rastreio de olhos. É acessível a partir da pronta de calibração de rastreio ocular ou lançando a aplicação Definições a partir do menu inicial e, em seguida, selecionando **System > Calibration > Calibração ocular > Executar calibração ocular**.

Estas informações podem ser encontradas mais tarde com [outras informações de calibração](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Gestor de Certificados

- Melhoria da auditoria, diagnóstico e validação da segurança do dispositivo e cumprimento através do novo Gestor de Certificados. Esta capacidade permitir-lhe-á implantar, resolver problemas e validar os seus certificados em escala em ambientes comerciais.

Na Windows versão holográfica 20H2, estamos a adicionar um Certificate Manager na aplicação HoloLens 2 Definições. Aceda aos **certificados de > de segurança & Definições > de Definições >.** Esta funcionalidade fornece uma forma simples e fácil de visualizar, instalar e remover certificados no seu dispositivo. Com o novo Gestor de Certificados, os administradores e utilizadores têm agora uma ferramenta melhorada de auditoria, diagnóstico e validação para garantir que os dispositivos se mantenham seguros e conformes. 

-   **Auditoria:** Capacidade de validar que um certificado é implantado corretamente ou de confirmar que foi removido adequadamente. 
-   **Diagnóstico:** Quando surgem problemas, validar que os certificados adequados existem no dispositivo poupa tempo e ajuda na resolução de problemas. 
-   **Validação:** Verificar se um certificado serve o fim pretendido e é funcional, pode economizar tempo significativo, particularmente em ambientes comerciais antes de implantar certificados em maior escala.

Para encontrar rapidamente um certificado específico na lista, existem opções para classificar pelo nome, loja ou data de validade. Os utilizadores também podem procurar diretamente um certificado. Para ver as propriedades individuais do certificado, selecione o certificado e clique em **Informação**. 

A instalação do certificado suporta atualmente ficheiros .cer e .crt. Os Proprietários de Dispositivos podem instalar certificados na Máquina Local e no Utilizador Atual;  todos os outros utilizadores só podem instalar-se no Utilizador Atual. Os utilizadores só podem remover certificados instalados diretamente da UI Definições. Se um certificado tiver sido instalado através de outros meios, deve também ser removido pelo mesmo mecanismo.

#### <a name="to-install-a-certificate"></a>Para instalar um certificado: 

1.  Ligação o seu HoloLens 2 para um PC.
1.  Coloque o ficheiro de certificado que pretende instalar num local na sua HoloLens 2.
1.  Navegue para **Definições App > Atualizar & Certificados de segurança >** e selecione Instalar um certificado.
1.  Clique em **'Importar' e** navegue para o local onde guardou o certificado.
1.  Selecione **a localização da loja**.
1.  Selecione **Certificate Store**.
1.  Clique em **Install** (Instalar).

O certificado deve agora ser instalado no aparelho.

#### <a name="to-remove-a-certificate"></a>Para remover um certificado: 
1. Navegue para **Definições App > atualização e certificados de > de segurança.**
1. Procure o certificado pelo nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique **em Remover**
1. Selecione **Sim** quando solicitado para confirmação.

![Espectador de certificado na app Definições](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar o Certificado UI para instalar um certificado](images/certificate-device-install.jpg)

Esta informação pode ser encontrada mais tarde [numa nova página do Gestor de Certificados.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Provisão de lançamento automático a partir de USB

- Processos automatizados que permitem uma menor interação do utilizador, quando as unidades USB com Pacotes de Provisionamento são utilizadas durante o OOBE.

Antes desta libertação, os utilizadores tiveram de lançar manualmente o ecrã de provisionamento durante o OOBE para obterem uma combinação de botões. Agora os utilizadores podem saltar a combinação de botões, utilizando um Pacote de Provisionamento numa unidade de armazenamento USB. 

1. Ligue a unidade USB com o pacote de provisionamento durante o primeiro momento interagivel da OOBE
1. Quando o dispositivo estiver pronto para ser a provisionado, abrirá automaticamente o pedido com a página de provisionamento. 

Nota: Se uma unidade USB for deixada ligada durante o arranque do dispositivo, então o OOBE enumerará o dispositivo de armazenamento USB existente, bem como o relógio para outros que estão ligados.

Para obter mais informações sobre a aplicação de pacotes de provisionamento durante a OOBE, visite a [documentação de provisionamento HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Informações adicionais sobre [o fornecimento automático de lançamento a partir de um USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) podem ser encontradas na documentação de provisionamento HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Pacotes de provisão automática em OOBE
- O processo automatizado permite uma menor interação do utilizador, quando a página 'Pacote de Provisionamento' for apresentada, aplicará automaticamente todos os pacotes listados.

Quando o ecrã principal de provisionamento aparecer, o OOBE irá contar 10 segundos antes de começar automaticamente a aplicar todos os pacotes de provisionamento. Os utilizadores ainda podem [confirmar ou cancelar](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) dentro destes 10 segundos depois de verificarem as embalagens que esperavam.

### <a name="automatic-provisioning-without-using-ui"></a>Provisionamento automático sem utilização de UI
- Processos automáticos combinados para interações reduzidas do dispositivo para o provisionamento. 

Ao combinar o lançamento automático do fornecimento de dispositivos USB e a confirmação automática de pacotes de provisionamento, um utilizador pode providenciar HoloLens 2 dispositivos automaticamente sem utilizar o UI do dispositivo ou mesmo usar o dispositivo. Pode continuar a utilizar a mesma unidade USB e pacote de provisionamento para vários dispositivos. Isto é útil para a implementação de vários dispositivos ao mesmo tempo na mesma área. 

1. [Crie um pacote de provisionamento](hololens-provisioning.md) utilizando [Windows Designer de Configuração](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie a embalagem para uma unidade de armazenamento USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) a [19041.1361 ou construção mais recente](https://aka.ms/hololens2previewdownload). 
1. Quando [o Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) tiver completado o piscar, o seu dispositivo desliga o cabo USB-C. 
1. Ligue a sua unidade USB ao dispositivo.
1. Quando o HoloLens 2 botas de dispositivo para o OOBE, irá detetar automaticamente o pacote de provisionamento na unidade USB e lançar a página de provisionamento.
1. Após 10 segundos, o dispositivo aplicará automaticamente o pacote de provisionamento. 

O seu dispositivo está agora configurado e [apresentará o ecrã "Provisioning Successful".](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Utilização de Piloto Automático com ligação Wi-Fi
- Removida necessidade de adaptadores USB-C para a ethernet reduzindo as necessidades de hardware, permitindo ao Autopilot funcionar em dispositivos Wi-Fi ligados.

Agora, durante o OOBE, uma vez que conecte HoloLens 2 com Wi-Fi, o OOBE verificará se há um perfil de piloto automático para o dispositivo. Se for encontrado, será usado para completar o resto da junção da AAD e do fluxo de inscrição. Por outras palavras, a utilização do ethernet para USB-C ou Wi-Fi para o adaptador USB-C já não é um requisito, no entanto continuam a funcionar se forem fornecidas no início do OOBE. Saiba mais sobre [o Autopilot para HoloLens 2 dispositivos](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>Inquilinolockdown CSP e Autopilot
- Mantém os dispositivos no inquilino da organização, trancando-os ao arrendatário mesmo através do reset ou reflash do dispositivo. Com mais segurança, ao desafetar a criação de conta através do provisionamento. 

HoloLens 2 dispositivos suportam agora o TenantLockdown CSP a partir da [versão holográfica 20H2 da Windows](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) A CSP permite que HoloLens 2 estejam ligados à inscrição de MDM usando apenas o Autopilot. Uma vez que o nó requere de CSP do TenantLockdown CSP é definido para o valor verdadeiro ou falso (inicialmente definido) no HoloLens 2, esse valor permanece no dispositivo apesar de re-piscar, atualizações de SO, etc. 

Uma vez que o nó requere de CSPs do TenantLockdown CSPs É definido como verdadeiro no HoloLens 2, o OOBE espera indefinidamente para que o perfil do Piloto Automático seja descarregado e aplicado com sucesso, após a conectividade da rede. 

Uma vez que o nó de RequerenetworkInOOBE do TenantLockdown cSPs seja definido para ser verdadeiro em HoloLens 2, as seguintes operações são proibidas em OOBE: 
- Criar o utilizador local utilizando o fornecimento de tempo de execução 
- Realização Azure AD aderir operação através de provisionamento de tempo de execução 
- Selecionando quem é o dono do dispositivo na experiência OOBE 

#### <a name="how-to-set-this-using-intune"></a>Como definir isto usando o Intune? 
1. Crie um perfil de configuração de dispositivo OMA URI personalizado e especifique o caso true for RequireNetworkInOOBE, conforme mostrado abaixo.
O valor OMA-URI deve ser ./Fornecedor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Fixação do bloqueio do tennant via OMA-URI](images/hololens-tenant-lockdown.png)

1. Crie um grupo e atribua o perfil de configuração do dispositivo a esse grupo de dispositivos. 

1. Faça o HoloLens 2 membro do dispositivo do grupo criado em sincronização de passo e gatilho anteriores.  

Verifique no portal Intune que a configuração do dispositivo foi aplicada com sucesso. Uma vez que esta configuração do dispositivo se aplique com sucesso no dispositivo HoloLens 2, os efeitos do TenantLockdown estarão ativos.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Como desaparassar o TenantLockdown's RequireNetworkInOOBE em HoloLens 2 usando o Intune? 
1. Remova o HoloLens 2 do grupo de dispositivos ao qual a configuração do dispositivo acima foi atribuída anteriormente. 

1. Crie um perfil de configuração de dispositivo baseado em OMA URI personalizado e especifique falso para RequireNetworkInOOBE, como mostrado abaixo. O valor OMA-URI deve ser ./Fornecedor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot de definição RequerNetworkInOOBE falso via OMA URI em Intune](images/hololens-tenant-lockdown-false.png)

1. Crie um grupo e atribua o perfil de configuração do dispositivo a esse grupo de dispositivos. 

1. Faça o HoloLens 2 membro do dispositivo do grupo criado em sincronização de passo e gatilho anteriores.

Verifique no portal Intune que a configuração do dispositivo foi aplicada com sucesso. Uma vez que esta configuração do dispositivo se aplique com sucesso no dispositivo HoloLens 2, os efeitos do TenantLockdown ficarão inativos. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>O que aconteceria durante o OOBE, se o perfil do Piloto Automático não fosse atribuído a uma HoloLens depois do TenantLockdown ter sido definido como verdadeiro? 
A OOBE aguardará indefinidamente o download do perfil do Piloto Automático e será apresentado o diálogo seguinte. Para eliminar os efeitos do TenantLockdown, o dispositivo deve ser matriculado com o seu inquilino original primeiro usando o Autopilot e o RequireNetworkInOOBE deve ser desatado como descrito no passo anterior antes de as restrições introduzidas pelo TenantLockdown CSP serem removidas. 

![Vista no dispositivo para quando a política é aplicada no dispositivo.](images/hololens-autopilot-lockdown.png)

Esta informação pode agora ser encontrada ao lado do resto do Autopilot sob [o CSP e o Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Global Assigned Access – Modo Quiosque
- Gestão de identidade reduzida para quiosque, permitindo o novo método do quiosque que aplica o modo quiosque ao nível do sistema.

Esta nova funcionalidade permite que um Administrador de TI configuure um dispositivo HoloLens 2 para o modo de quiosque de várias aplicações, que é aplicável a nível do sistema, não possui qualquer afinidade com qualquer identidade no sistema e aplica-se a todos os que assinam no dispositivo. Leia sobre esta nova funcionalidade em detalhe no [HoloLens quiosque de acesso global atribuído.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Lançamento automático de uma aplicação em modo quiosque de várias aplicações 
- Experiência focada no lançamento automático de aplicações, aumentando ainda mais as seleções de UI e apps escolhidas para experiências em modo quiosque.

Aplica-se apenas ao modo quiosque de várias aplicações e apenas uma aplicação pode ser designada para lançamento automático utilizando o atributo realçado abaixo na configuração de Acesso Atribuído. 

A aplicação é lançada automaticamente quando o utilizador se inscreve. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Mudanças de comportamento no modo quiosque para lidar com falhas
- Modo quiosque mais seguro eliminando aplicações disponíveis em falhas no modo Kiosk. 

Anteriormente, ao encontrar falhas na aplicação do modo quiosque, HoloLens usado para mostrar todas as aplicações no menu inicial. Agora, em Windows versão Holográfica 20H2 no caso de falhas nenhuma aplicação será mostrada no menu inicial como abaixo: 

![Imagem do que o modo Quiosque agora parece quando falha.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Políticas
- Opções de gestão de dispositivos especificamente para HoloLens criadas para gerir o dispositivo. 

Foram criadas novas políticas de realidade mista para HoloLens 2 dispositivos na versão holográfica 20H2 Windows. As novas definições controláveis incluem: luminosidade de definição, volume de definição, gravação de áudio incapacitante em capturas de realidade mista, definição quando os diagnósticos podem ser recolhidos e cache de membro do grupo AAD.  

| Política de nova HoloLens                                | Description                                                                               | Notas                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Realidade Mista\BrightnessButtonDisabled              | Permite que os botões de luminosidade sejam desativados de modo a premir, não altere o brilho.       | 1 Sim, 0 Não (padrão)                                                |
| Realidade Mista\VolumeButtonDisabled                  | Permite que os botões de volume sejam desativados de modo a que a pressão não altere o volume.               | 1 Sim, 0 Não (padrão)                                                |
| Realidade Mista\MicrofoneDisabled                    | Desativa o microfone para que não seja possível gravar áudio no HoloLens 2.                      | 1 Sim, 0 Não (padrão)                                                |
| MixedReality\FallbackDiagnostics                   | Controla o comportamento de quando os registos de diagnóstico podem ser recolhidos.                               | 0 Desativado, 1 Habilitado para Os Proprietários de Dispositivos, 2 Habilitado para todos (Predefinido) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla quantos dias a cache de membro do grupo Azure AD é usada para quiosques direcionados para grupos AD Azure. | Veja abaixo.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Adesão ao Grupo AD cache Azure para quiosque offline
- Os quiosques offline habilitados a serem utilizados com grupos AAD por um tempo até 60 dias.

Esta política controla por quantos dias, a cache de membro do grupo AD Azure é permitida para configurações de acesso atribuído direcionadas para grupos AD Azure para serem assinados no utilizador. Uma vez que este valor de política é definido para valor superior a 0 apenas, então cache é usado de outra forma não.  

Nome: AADGroupMembershipCacheValidityInDays valor: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 dias  
Máximo - 60 dias 

Medidas para utilizar corretamente esta política: 
1. Crie um perfil de configuração do dispositivo para quiosques direcionados para os grupos AZure AD e atribua-o a HoloLens dispositivos). 
1. Crie uma configuração personalizada do dispositivo baseado em OMA URI que define este valor de política para o número de dias desejado (> 0) e atribua-o a HoloLens dispositivos). 
    1. O valor URI deve ser introduzido na caixa de texto OMA-URI como ./Fornecedor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode ser entre min/max permitido.
1. Inscreva HoloLens dispositivos e verifique se ambas as configurações são aplicadas no dispositivo. 
1. Deixe o utilizador AD AD 1 iniciar sposição quando a internet estiver disponível, uma vez que a subscrição do grupo AD do utilizador é confirmada com sucesso, a cache será criada. 
1. Agora, o utilizador AD AD 1 pode tirar HoloLens offline e usá-lo para o modo quiosque, desde que o valor da política permita o número de dias X. 
1. Os passos 4 e 5 podem ser repetidos para qualquer outro utilizador Azure AD N. O ponto chave aqui é que qualquer utilizador AD AD Azure deve iniciar sação para o dispositivo usando a Internet para que pelo menos uma vez que possamos determinar que eles são membros do grupo AZure AD para o qual a configuração do Quiosque é alvo. 
 
> [!NOTE]
> Até que o passo 4 seja realizado para um utilizador AD Azure irá experimentar o comportamento de falha mencionado em ambientes "desligados". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Novas políticas de restrição de dispositivos para HoloLens 2
- Permite que os utilizadores gerem políticas específicas de gestão de dispositivos, tais como bloquear a adição ou remoção de pacotes de provisionamento.

Políticas recentemente ativadas que permitem mais opções de gestão de HoloLens 2 dispositivos. 
- [Permitir a Embalagem deProvisão](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [Permitir a Embalagem deProvisão deRemove](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

Estas duas novas polícias para AllowAddProvisioningPackage e AllowRemoveProvisioningPackage estão a ser adicionadas às [nossas Restrições Comuns de Dispositivos](hololens-common-device-restrictions.md).

> [!NOTE]
> No que diz respeito ao [RemoteLock,](/windows/client-management/mdm/remotelock-csp)HoloLens apenas suportam a configuração ./Fornecedor/MSFT/RemoteLock/Lock. As configurações que lidam com PIN como reset e recuperação não são suportadas.

### <a name="new-power-policies-for-hololens-2"></a>Novas políticas de poder para HoloLens 2
- Mais opções para quando HoloLens dorme ou bloqueia através de políticas de energia. 

Estas novas políticas adicionais permitem que os administradores controlem estados de poder, como o tempo limite. Para ler mais sobre cada política individual clique no link para essa política.

|     Ligação de documentação de política                |     Notas                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de exemplo a utilizar no Windows Configuration Designer, ou seja,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de exemplo a utilizar no Windows Configuration Designer, ou seja,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de exemplo a utilizar no Windows Configuration Designer, ou seja, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de exemplo a utilizar no Windows Configuration Designer, ou seja, 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de exemplo a utilizar no Windows Configuration Designer, ou seja,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de exemplo a utilizar no Windows Configuration Designer, ou seja,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Estas duas novas polícias para displayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn estão a ser adicionadas às [nossas Restrições Comuns de Dispositivos](hololens-common-device-restrictions.md).

> [!NOTE]
> Para uma experiência consistente no HoloLens 2, certifique-se de que os valores tanto para o DisplayOffTimeoutOnBattery como para o StandbyTimeoutOnBattery são definidos como o mesmo valor. O mesmo se aplica ao DisplayOffTimeoutPluggedIn e ao StandbyTimeoutPluggedIn. Consulte os [temporizadores display, sleep e hibernar](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) para obter mais detalhes sobre o moderno standby.

### <a name="newly-enabled-update-policies-for-hololens"></a>Políticas de atualização recentemente ativadas para HoloLens
- Mais opções para quando as atualizações são instaladas ou desativando o botão 'Atualizações de Pausa' para garantir atualizações.

Estas políticas de atualização estão agora ativadas em HoloLens 2 dispositivos:
-   [Atualização/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Atualização/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Atualização/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Atualização/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Todos os detalhes sobre estas políticas de atualização e como usá-las para HoloLens dispositivos podem ser lidos aqui em [Gerir HoloLens atualizações](hololens-updates.md).

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Visibilidade de página de Definições ativada para HoloLens 2
- O aumento do controlo de UI na App Definições, que pode ser confundido para mostrar uma seleção limitada de páginas.

Agora permitimos que uma política que permite aos administradores de TI impedir que páginas específicas no Sistema Definições aplicação sejam visíveis ou acessíveis, ou para fazê-lo para todas as páginas, exceto as especificadas. Para aprender a personalizar totalmente esta funcionalidade clique no link abaixo.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber quais as definições de página que pode personalizar no HoloLens 2, visite a nossa [página uris Definições](settings-uri-list.md). 
 
![Screenshot de horas ativas a ser modificada na app Definições](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modo de investigação
Enquanto em Modo de Investigação, o HoloLens 2 torna-se uma ferramenta potente para a pesquisa de visão computacional. Em comparação com edições anteriores, o Modo de Investigação para HoloLens 2 tem as seguintes vantagens:
-   Além dos sensores expostos no modo de pesquisa HoloLens (1ª geração), agora fornecemos acesso a sensores IMU, incluindo um acelerómetro, giroscópio e magnetómetro.
-   HoloLens 2 fornece novas capacidades que podem ser usadas juntamente com o Modo de Pesquisa. Especificamente, o acesso a APIs articulados de rastreio manual e rastreio de olhos que pode proporcionar um conjunto mais rico de experiências.

Os investigadores têm agora a opção de permitir que o Modo de Investigação nos seus HoloLens dispositivos acedam a todos estes fluxos de sensores de imagem cruas externos. O modo de pesquisa para HoloLens 2 também fornece acesso ao acelerómetro, giroscópio e leituras magnetómetro. Para proteger a privacidade dos utilizadores, as imagens de câmaras de rastreio de olhos crus não estão disponíveis através do Modo de Pesquisa, mas a direção do olhar dos olhos está disponível através das APIs existentes.

Consulte a documentação do [Modo de Investigação](/windows/mixed-reality/research-mode) para mais detalhes técnicos.

### <a name="recording-length-increased"></a>O comprimento da gravação aumentou
Devido ao feedback do cliente, aumentámos o comprimento de gravação das capturas de [realidade mista.](holographic-photos-and-videos.md) As capturas de realidade mista deixarão de ser limitadas a 5 minutos por padrão, mas calcularão o comprimento máximo de gravação com base no espaço disponível do disco. O dispositivo estimará a duração máxima da gravação de vídeo com base no espaço disponível do disco até 80% do espaço total do disco.

> [!NOTE]
> O HoloLens utilizará o comprimento de gravação de vídeo predefinido (5 minutos) se ocorrer um dos seguintes:
> - A duração máxima estimada de gravação é menor do que os 5 minutos padrão.
> - O espaço disponível em disco é menos de 20% do espaço total do disco.

Pode encontrar todos os requisitos na documentação [de fotos e vídeos holográficos.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:
- Mais ecrãs no OOBE estão agora em modo escuro.
- Saiba mais conteúdo deve apontar para a mais recente Declaração de Privacidade online.
- Abordou uma questão em que os utilizadores não podiam prever perfis VPN através de pacotes de provisionamento.
- Problema de configuração de procuração fixo para ligação VPN.
- Política atualizada para desativar a enumeração das funções USB através do MDM para NCM para AllowUsbConnection.
- Abordou um problema que impediu que um dispositivo HoloLens aparecesse no File Explorer over Media Transfer Protocol (MTP) quando o dispositivo é configurado como um [quiosque de uma única aplicação](hololens-kiosk.md). Note que a ligação MTP (e a ligação USB em geral) ainda podem ser desativadas utilizando a política [AllowUSBConnection.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Corrigiu um problema em que os ícones da menu Iniciar foram dimensionado corretamente no modo quiosque.
- Corrigiu um problema devido à interferência de caching HTTP com o modo quiosque direcionado para os grupos AD Azure.
- Corrigiu um problema em que os utilizadores não podiam utilizar o botão Par depois de permitirem o modo desenvolvedor com pacotes de provisionamento, a menos que desativem e reativem o modo developer.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holográfico, versão 1903 - novembro 2020 Atualização
- Construção 18362.1085

Esta atualização mensal de qualidade não contém quaisquer alterações notáveis, encorajamos-te a experimentar a nossa mais recente versão Windows Holographic, versão 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holográfico, versão 2004 - outubro 2020 Atualização
- Construção 19041.1124
 
Melhorias e correções na atualização:

- Removido uma verificação desnecessária que causou falha no sistema de tempo de execução.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holográfico, versão 1903 - outubro 2020 Atualização
- Construção 18362.1081

Esta atualização mensal de qualidade não contém quaisquer alterações notáveis, encorajamo-lo a experimentar as nossas mais recentes construções para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holográfico, versão 2004 - setembro 2020 Atualização
- Construção 19041.1117

Melhorias e correções na atualização:

- Aborda um problema que impediu Visual Studio de depurar uma aplicação quando supportsMultipleInstances="true" está presente no appxmanifest.
- Esta versão inclui a correção de deteção de procuração NCSI para resolver a deteção falhada da Internet através de procuração de rede. O NCSI pode utilizar o proxy da máquina e o proxy por perfil para a deteção da conectividade da Internet. O proxy por utilizador será suportado pelo NCSI em futuras versões.
- Na maioria dos dispositivos Windows Mixed Reality, o vetor de direção dianteira é paralelo ao solo quando a cabeça do utilizador está numa posição neutra olhando para a frente. No entanto, versões anteriores de HoloLens 2 alinharam o vetor para ser perpendicular aos painéis de exibição, que é inclinado para baixo alguns graus em relação à orientação ideal. Versões mais recentes de HoloLens 2 corrigiram isto para garantir a consistência semântica entre fatores de forma.
- Uma maior robustez no rastreio da mão, o que resultará em menos perdas de rastreamento em cenários específicos.
- Esta versão contém uma correção para melhorar a qualidade do relógio de áudio que pode ter contribuído para problemas de captura de vídeo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holográfico, versão 1903 - Atualização de setembro de 2020
- Construção 18362.1079

Melhorias e correções na atualização:

- Na maioria dos dispositivos Windows Mixed Reality, o vetor de direção dianteira é paralelo ao solo quando a cabeça do utilizador está numa posição neutra olhando para a frente. No entanto, versões anteriores de HoloLens 2 alinharam o vetor para ser perpendicular aos painéis de exibição, que é inclinado para baixo alguns graus em relação à orientação ideal. Versões mais recentes de HoloLens 2 corrigiram isto para garantir a consistência semântica entre fatores de forma.
- Uma maior robustez no rastreio da mão, o que resultará em menos perdas de rastreamento em cenários específicos.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holográfico, versão 2004 - agosto 2020 Atualização
- Construção 19041.1113

Melhorias e correções na atualização:

- Definições aplicação deixará de seguir o utilizador para experiências de Inscrição iris ou de calibração de rastreio de olhos.
- Fixar um bug quando aplicar um pacote de provisionamento durante o OOBE que renomeia o dispositivo e executa outras ações (como a ligação a uma rede) não executaria as outras ações após o reboot do dispositivo devido ao renomeamento.
- Esquema de cores modificado dos fluxos iniciais de configuração do dispositivo para melhorar a qualidade visual.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holográfico, versão 1903 - agosto 2020 Atualização
- Construção 18362.1074

Esta atualização mensal de qualidade não contém quaisquer alterações notáveis, encorajamo-lo a experimentar as nossas mais recentes construções para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holográfico, versão 2004 - julho 2020 Atualização
- Construção 19041.1109

Melhorias e correções na atualização:

- Os desenvolvedores podem agora escolher entre ativar ou desativar ter o Portal do Dispositivo a exigir uma ligação segura.
- A fiabilidade melhorou para os lançamentos de aplicações após as atualizações do SISTEMA.
- Alterou o brilho da caixa de entrada padrão para 100%.
- Abordou um problema sobre o encaminhamento do HTTPS para o Portal do Dispositivo Windows no HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holográfico, versão 1903 - julho 2020 Atualização
- Construção 18362.1071

Melhorias e correções na atualização:

- Corrigiu um problema que poderia fazer com que os hologramas desaparecessem nas aplicações de Unidade ao perder ou recuperar o rastreio.
- Corrigiu um problema que fez com que as aplicações exclusivas HoloLens voltassem a cair na casca enquanto utilizavam o HoloLens Emulator com aceleração de hardware em determinados dispositivos.
- Abordou um problema relativo ao encaminhamento do HTTPS para o Portal do Dispositivo Windows no HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holográfico, versão 2004 - junho 2020 Atualização
- Construção 19041.1106

Melhorias e correções na atualização:

- Os gravadores MRC personalizados têm agora novos valores predefinidos para determinadas propriedades se não forem especificados.
  - No *efeito de vídeo MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (auriculares imersivos))
  - Sobre o *efeito áudio MRC:*
    - LoopbackGain (o valor atual "App Audio Gain" na página de captura de realidade mista no Portal Windows Dispositivo)
    - MicrofoneGain (o valor atual "Mic Audio Gain" na página de captura de realidade mista no portal Windows dispositivo)
- Fixou um bug para melhorar a qualidade do áudio em cenários de captura de realidade mista. Especificamente, esta correção deve eliminar falhas de áudio na gravação quando o menu **Iniciar** é apresentado.
- Melhor estabilidade do holograma em vídeos gravados.
- Resolveu um problema em que a captura de realidade mista não conseguiu gravar vídeos depois de o dispositivo ter ficado em estado de espera durante vários dias.
- A API HolographicSpace.UserPresence é geralmente desativada para aplicações de Unidade. Este comportamento evita um problema que fez com que algumas aplicações parassem quando a viseira foi virada para cima, mesmo que a definição de "executar em segundo plano" estivesse ativada. A API está agora habilitada para as versões Unidade 2018.4.18 e posteriormente e 2019.3.4 e posterior.
- Ao aceder ao Portal do Dispositivo sobre uma ligação Wi-Fi, um navegador web pode impedir o acesso devido a um certificado inválido. O navegador pode relatar um erro como "ERR_SSL_PROTOCOL_ERROR", mesmo que o certificado do dispositivo fosse previamente confiável. Neste caso, não é possível progredir para o Portal do Dispositivo, uma vez que não há opção para ignorar os avisos de segurança. Esta atualização resolveu o problema. Se o certificado do dispositivo foi previamente descarregado e confiado num PC para remover avisos de segurança do navegador, e o erro SSL ocorrer, o novo certificado tem de ser descarregado e fidedigno para responder aos avisos de segurança do navegador.
- Permitiu criar um pacote de provisionamento de tempo de execução que pode instalar uma aplicação utilizando pacotes MSIX.
- Adicionou uma definição no **Hologramas**  >  **do Sistema**  >  **Definições** que permite aos utilizadores remover automaticamente todos os hologramas da Casa da Realidade Mista quando o dispositivo é desligado.
- Corrigiu um problema que fez com que HoloLens aplicações que alterassem o seu formato de pixels se tornassem pretas no emulador HoloLens.
- Consertou um erro que causou um acidente durante o login da Iris.
- Corrigi um problema sobre transferências repetidas de lojas para aplicações já atuais.
- Corrigiu um bug para evitar que as aplicações imersivas abrissem Microsoft Edge repetidamente.
- Corrigiu um problema com os lançamentos da aplicação Photos nas botas iniciais após a atualização da versão de 1903.
- Melhor desempenho e fiabilidade.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holográfico, versão 1903 - junho 2020 Atualização
- Construção 18362.1064

Melhorias e correções na atualização:

- Os gravadores MRC personalizados têm novos valores predefinidos para determinadas propriedades se não forem especificados.
  - No *efeito de vídeo MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (auriculares imersivos))
  - Sobre o *efeito áudio MRC:*
    - LoopbackGain (o valor atual "App Audio Gain" na página de captura de realidade mista no Portal Windows Dispositivo)
    - MicrofoneGain (o valor atual "Mic Audio Gain" na página de captura de realidade mista no portal Windows dispositivo)
- A API HolographicSpace.UserPresence é geralmente desativada para aplicações de Unidade. Este comportamento evita um problema que faz com que algumas aplicações façam uma pausa quando a viseira é virada para cima, mesmo que a definição a ser executada em segundo plano esteja ativada. A API está agora habilitada para as versões Unidade 2018.4.18 e posterior, e 2019.3.4 e posterior.
- Corrigiu um problema que fez com que HoloLens aplicações que alterassem o seu formato de pixels se tornassem pretas no HoloLens Emulator.
- Corrigi um problema sobre lançamentos da aplicação Fotos em botas iniciais após a atualização a partir do lançamento de 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holográfico, versão 2004  
- Construção - 19041.1103

A grande atualização de software de maio de 2020 para HoloLens 2, *Windows Holographic, versão 2004* inclui uma série de novas capacidades emocionantes, como suporte para Windows Autopilot, modo escuro de aplicação, suporte USB Ethernet para hotspots 5G/LTE, e muito mais. Para atualizar a versão mais recente, abra a   aplicação Definições, vá a **Update & Security** e selecione o botão Check for **Updates.**   

|             Funcionalidade                              |          Descrição                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pré-configuração e configuração perfeita de novos dispositivos para produção utilizando Windows AutoPilot                 |
|       Suporte FIDO 2                             |          Suporte para Chaves de Segurança FIDO2 para permitir a autenticação rápida e segura para dispositivos partilhados            |
|       Melhoria do a provisionamento                      |          Aplique perfeitamente um pacote de provisionamento de uma unidade USB para o seu HoloLens                              |
|       Estado de instalação de aplicações                 |          Verifique o estado da instalação na aplicação Definições para apps foram empurradas para HoloLens 2 via MDM               |
|       Prestadores de serviços de configuração (CSPs)   |          Adicionou novos fornecedores de serviços de configuração para aumentar as capacidades de controlo de administração                 |
|       Suporte USB 5G/LTE                       |          Capacidade de Ethernet USB expandida permite suporte para 5G/LTE                                    |
|       Modo aplicativo escuro                              |          Modo aplicativo escuro disponível para apps que suportam modos escuros e claros, melhorando a experiência de visualização        |
|       Comandos de voz                             |          Suporte para comandos de voz adicionais do sistema para controlar HoloLens mãos livres                           |
|       Melhorias no rastreio de mãos                 |          As melhorias no rastreio manual tornam os botões e as interações de ardósia 2D mais precisas                        |
|       Melhorias e correções de qualidade                 |          Várias melhorias no desempenho do sistema e na fiabilidade em toda a plataforma                            |

### <a name="support-for-windows-autopilot"></a>Suporte para Windows Autopilot

Windows O piloto automático para HoloLens 2 permite que o canal de vendas do dispositivo pré-inscreva HoloLens no seu inquilino Intune. Quando os dispositivos chegarem, estão prontos para se implantarem como dispositivos partilhados sob o seu inquilino. Para tirar partido da auto-implantação, o dispositivo deve ligar-se a uma rede durante o primeiro ecrã em configuração utilizando uma USB-C-para-Ethernet.

Depois de um utilizador iniciar o processo de auto-implantação do Autopilot, o processo completa os seguintes passos:

1. Junte o dispositivo para Azure Ative Directory (Azure AD).
1. Utilize a Azure AD para inscrever o dispositivo em Microsoft Intune (ou noutro serviço MDM).
1. Descarregue as políticas, certificados e perfis de rede direcionados para o dispositivo.
1. A provisione o dispositivo.
1. Apresente o ecrã de inscrição ao utilizador.

Saiba mais com o [Windows Autopilot para HoloLens guia de avaliação 2](hololens2-autopilot.md).

*Contacte o seu Gestor de Conta para se juntar à pré-visualização do AutoPilot agora. Os dispositivos prontos para o piloto automático começarão a ser enviados em breve.*

### <a name="fido2-security-key-support"></a>Suporte chave de segurança FIDO2

Alguns utilizadores partilham um dispositivo HoloLens com outros em ambiente de trabalho ou escola. Por isso, é importante que os utilizadores possam facilmente sem digitar nomes de utilizadores longos e senhas. A Fast Identity Online (FIDO) permite que qualquer pessoa da sua organização (Azure AD insira perfeitamente para HoloLens sem introduzir um nome de utilizador ou senha.

As chaves de segurança FIDO2 são um método de autenticação sem palavras-passe "infishable" baseado em padrões que pode vir em qualquer fator de forma. O FIDO é um padrão aberto para a autenticação sem palavras-passe. Permite que utilizadores e organizações inscrevam-se nos seus recursos sem nome de utilizador ou senha. Em vez disso, usam uma chave de segurança externa ou uma chave de plataforma incorporada num dispositivo.

Para começar, consulte [Ativar o início do sôming da chave de segurança sem palavras-passe](/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Melhor inscrição do MDM através de pacote de provisionamento

Os pacotes de provisionamento permitem-lhe definir HoloLens configuração através de um ficheiro config e não através da experiência fora de caixa HoloLens. Anteriormente, os pacotes de provisionamento tinham de ser copiados para a memória interna HoloLens. Agora podem estar numa unidade USB para que sejam mais fáceis de reutilizar em vários dispositivos HoloLens e você pode providenciar dispositivos em paralelo. Os pacotes de provisionamento agora também suportam um campo para se inscrever na gestão do dispositivo para que não haja configuração manual após o provisionamento.

Para experimentá-lo:

1. Descarregue a versão mais recente do Windows Configuration Designer da loja Windows para o seu PC.
1. **Selecione disposição HoloLens dispositivos**  >  **HoloLens 2 dispositivos**.
2. Construa o seu perfil de configuração. Em seguida, copie todos os ficheiros que foram criados para um dispositivo de armazenamento USB-C.
3. Ligue o dispositivo USB-C a qualquer HoloLens recentemente intermitente. Em seguida, pressione os botões de potência **para baixo** do volume para aplicar o seu pacote de  +   provisionamento.

### <a name="line-of-business-application-install-status"></a>Estado de instalação de aplicações em linha de negócio

A implementação e gestão de aplicações de MDM para aplicações de linha de negócios é fundamental para HoloLens. Os administradores e os utilizadores precisam de visualizar o estado de instalação da aplicação para auditoria e diagnóstico. Nesta versão, adicionámos mais detalhes no **Definições**  >  **Contas**  >  **Access ou escola Clique** na sua  >  **conta**  >  **Informações.**

### <a name="additional-csps-and-policies"></a>CSPs adicionais e políticas

Um [fornecedor de serviços de configuração (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) é uma interface para ler, definir, modificar ou eliminar definições de configuração num dispositivo. Nesta versão, adicionamos suporte a mais políticas para aumentar os administradores de controlo que têm sobressaem HoloLens dispositivos. Para a lista de CSPs apoiados por HoloLens, consulte [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

Novidades neste lançamento:

**Política CSP** 

O prestador de serviços de configuração de política permite à empresa configurar políticas em dispositivos Windows. Neste comunicado, adicionámos novas políticas para HoloLens, que estão listadas aqui. Para saber mais, consulte [os CSPs de Política apoiados por HoloLens 2](/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- Permitir aWiFi 

**NetworkQoSPolicy CSP**

O prestador de serviços de configuração NetworkQoSPolicy cria políticas de qualidade de serviço de rede (QoS). Uma política QoS executa um conjunto de ações no tráfego de rede com base num conjunto de condições de correspondência. Para saber mais, consulte [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Suporte USB Ethernet expandido para dispositivos amarrados 5G/LTE

O suporte foi adicionado para permitir certos dispositivos de banda larga móvel, como telefones 5G/LTE e hotspots Wi-Fi, quando estão ligados ao HoloLens 2 via USB. Estes dispositivos são agora apresentados nas **definições de rede** como outra ligação Ethernet. (Os dispositivos de banda larga móveis que requerem um condutor externo não são suportados.) Esta funcionalidade permite ligações de alta largura de banda quando Wi-Fi não está disponível e Wi-Fi a amarra não é suficientemente executante. Para saber mais sobre dispositivos USB suportados, consulte [Ligação para dispositivos Bluetooth e USB-C](hololens-connect-devices.md).  

### <a name="hand-tracking-improvements"></a>Melhorias no rastreio de mãos

Esta versão inclui várias melhorias no rastreio de mãos:

- **Apontar a estabilidade da pose:** O sistema resiste agora a dobrar o dedo indicador quando é obstruído pela palma da mão. Esta alteração melhora a precisão quando pressiona botões, tipo, conteúdo de deslocação e muito mais! 
- **Torneiras de ar acidentais reduzidas:** Melhorámos a deteção do gesto da torneira de ar. Há agora menos ativações acidentais em vários cenários comuns, como quando baixas as mãos para os lados.
- **Fiabilidade do interruptor do utilizador:** O sistema é agora mais rápido e fiável na atualização do tamanho da mão quando partilha um dispositivo.
- **Roubo de mãos reduzido:** Melhoramos o tratamento dos casos em que há mais de duas mãos tendo em conta os sensores. Se várias pessoas estão a trabalhar juntas, há agora uma hipótese muito menor de que a mão rastreada "salte" do utilizador para a mão de outra pessoa na cena.
- **Fiabilidade do sistema:** Corrigiu um problema que fez com que o rastreio da mão deixasse de funcionar quando o dispositivo está sob carga elevada.

### <a name="dark-mode"></a>Dark mode (Modo escuro)

Muitas aplicações Windows suportam agora modos escuros e claros. HoloLens 2 utilizadores podem escolher o modo padrão para aplicações que suportam ambas. Após a atualização, o modo de aplicação predefinido é "escuro", mas pode facilmente alterar esta definição: Navegar para **Definições**  >  **Sistema**  >  **Colors**  >  **Escolha o seu modo de aplicação padrão**. 

Estas aplicações "in-box" suportam o modo escuro: 

- Definições 
- Loja Microsoft 
- Correio 
- Calendário 
- Explorador de Ficheiros 
- Centro de Feedback 
- OneDrive 
- Fotografias 
- Espectador 3D 
- Filmes & TV 

![Janelas de modo escuro em azulejo](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Comandos de voz do sistema

Agora pode utilizar comandos de voz com qualquer aplicação no dispositivo. Para obter mais informações, consulte [use a sua voz para operar HoloLens](hololens-cortana.md). Consulte também [as línguas suportadas para HoloLens 2](hololens2-language-support.md).  

### <a name="cortana-updates"></a>Atualizações Cortana

A aplicação atualizada integra-se com Microsoft 365 para ajudá-lo a fazer mais através dos seus dispositivos (atualmente apenas em US-English). No dia 2 HoloLens, Cortana já não suporta certos comandos específicos do dispositivo, como ajustar o volume ou reiniciar. Estas opções são agora suportadas pelos novos comandos de voz do sistema. Saiba mais sobre a nova app Cortana no nosso [blog.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Melhorias e correções de qualidade

Melhorias e correções também na atualização:  
- Introduziu um sistema de calibração de ecrã ativo. Esta funcionalidade melhora a estabilidade e o alinhamento dos hologramas. Agora ficam no lugar quando se move a cabeça de um lado para o outro.
- Corrigiu um bug onde Wi-Fi o streaming para HoloLens foi interrompido periodicamente. Se uma aplicação indicar que necessita de um streaming de latência baixa, implemente a correção chamando a [função SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Fixou um dispositivo pendurado que ocorreu durante o streaming em modo de pesquisa.
- Corrigiu um bug onde, em alguns casos, o utilizador certo não seria apresentado no ecrã de inscrição ao retomar uma sessão.
- Corrigiu um problema em que os utilizadores não podiam exportar registos de MDM através **de Definições**.
- Corrigiu um problema em que a precisão do rastreio ocular imediatamente após a configuração fora da caixa poderia ser inferior ao esperado.
- Corrigiu um problema em que o subsistema de rastreio ocular não iniciaisou ou efetuou a calibração sob determinadas condições.
- Corrigiu um problema em que a calibração ocular seria solicitada para um utilizador já calibrado.
- Corrigiu um problema em que um condutor se despenharia durante a calibração dos olhos.
- Corrigiu um problema em que premir o botão de alimentação repetido poderia causar uma pausa de 60 segundos no sistema e uma falha na concha.
- Melhor estabilidade para os amortecedores de profundidade.
- Adicionei um botão **Partilhar** no Centro de Comentários para que os utilizadores possam partilhar mais facilmente o feedback.
- Consertiu o bug onde o RoboRaid não está instalado corretamente.

### <a name="known-issues"></a>Problemas conhecidos

- Um problema com a linguagem do sistema zh-CN impede que os comandos de voz tomem uma captura de realidade mista ou apresentem o endereço IP do dispositivo.
- Um problema requer que lance a aplicação Cortana depois de iniciar o dispositivo para utilizar a ativação de voz "Hey Cortana". Se for atualizado a partir de uma construção de 18362, poderá também ver um segundo azulejo de aplicação para a versão anterior da aplicação Cortana que já não funciona no **Start**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holográfico, versão 1903 - Atualização de maio de 2020 
- Construção 18362.1061

Esta atualização mensal de qualidade não contém alterações notáveis porque a equipa estava a trabalhar na versão holográfica Windows 2004, como descrito anteriormente.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holográfico, versão 1903 - Atualização de abril de 2020
- Construção 18362.1059

**Modo escuro para aplicações suportadas** 

Muitas aplicações Windows suportam o modo escuro e o modo de luz. HoloLens 2 clientes podem agora escolher o modo padrão para aplicações que suportam ambos os esquemas de cores. Com base no feedback do cliente, definimos o modo de aplicação padrão para "escuro", mas pode facilmente alterar esta definição a qualquer momento: Navegar para **Definições > System > Colors** para encontrar **"Escolha o modo de aplicação padrão".**

Estas aplicações "in-box" suportam o modo escuro:
- Definições
- Loja Microsoft
- Correio
- Calendário
- Explorador de Ficheiros
- Centro de Feedback
- OneDrive
- Fotografias
- Espectador 3D
- Filmes & TV

**Melhorias e correções também na atualização:** 
- Assegurou-se que as sobreposições da concha são incluídas em capturas de realidade mista.
- Os desenvolvedores irreais podem agora usar a página 3D View no Portal do Dispositivo para testar e depurar as suas aplicações.
- Melhoria da estabilidade do holograma na captura de realidade mista quando o algoritmo *holográfico DeepthRejectionMethod DepthReprojection* é usado.
- Corrigiu o erro "WinRT IStreamSocketListener API Class não registado" em aplicações ARM de 32 bits.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holográfico, versão 1903 - março 2020 Atualização 
- Construção 18362.1056

Melhorias e correções na atualização:

- Melhoria da estabilidade do holograma na captura de realidade mista quando o algoritmo *HolographicDepthReprojection MethPlanar* é usado.
- Assegurou-se de que o sistema de coordenadas ligado a uma amostra de MF de profundidade é consistente com a documentação pública.
- Melhor produtividade do desenvolvedor, permitindo aos clientes colar grandes quantidades de texto através do portal do dispositivo.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holográfico, versão 1903 - Atualização de fevereiro de 2020 
- Construção 18362.1053

Melhorias e correções na atualização:

- Desativou temporariamente a API HolographicSpace.UserPresence para aplicações de unidade. Esta alteração evita um problema que fez com que algumas aplicações parassem quando a viseira foi virada para cima, mesmo que a definição de "executar em segundo plano" estivesse ativada.
- Corrigiu um acidente aleatório de HUP causado por rastreamento manual, no qual o utilizador notou um congelamento de UI e depois voltou a ser bombardeado após vários segundos.
- Um rastreio de mão melhorado para que quando você pica com o seu dedo indicador, a parte superior desse dedo é menos provável de enrolar inesperadamente.
- Melhor fiabilidade do rastreio da cabeça, mapeamento espacial e outros tempos de execução.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holográfico, versão 1903 - janeiro 2020 Atualização 
- Construção 18362.1043
 
Melhorias e correções na atualização:

- Melhor estabilidade para aplicações exclusivas ao trabalhar com o emulador HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holográfico, versão 1903 - Atualização de dezembro de 2019 
- Construção 18362.1042

Melhorias e correções na atualização:

- Introduziu correções de reprodução de última fase (LSR). Uma melhor renderização visual dos hologramas parece mais estável e crispada, contabilizando com mais precisão a sua profundidade. Este sintoma será mais percetível após esta atualização se as aplicações não definirem a profundidade dos hologramas corretamente.
- Estabilidade fixa de aplicações exclusivas e navegação entre aplicações exclusivas.
- Resolveu um problema em que a captura de realidade mista não conseguiu gravar vídeos depois de o dispositivo estar em estado de espera durante vários dias.
- Melhor estabilidade do holograma.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holográfico, versão 1903 - novembro 2019 Atualização 
- Construção 18362.1039

Melhorias e correções na atualização:

- Funcionalidade fixa dos comandos de voz **Select** durante a configuração inicial para en-CA e en-AU.
- Melhor qualidade visual dos objetos colocados longe nas mais recentes versões Unity e Mixed Reality Toolkit (MRTK).
- Resolver problemas fixos com aplicações holográficas ficando presos em estado de pausa no arranque até que o menu Iniciar foi aberto e depois fechado.
- Correção de conformidade de execução OpenXR e melhorias para HoloLens 2 e o emulador.
