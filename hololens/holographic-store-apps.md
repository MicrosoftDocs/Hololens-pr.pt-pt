---
title: Localizar, instalar e desinstalar aplicações
description: O Microsoft Store é a sua fonte de apps e jogos que funcionam com HoloLens.  Saiba mais sobre encontrar, instalar e desinstalar aplicações holográficas.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: hololens, loja, uwp, app, instalar
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f7d4ddf41f02b083000c1e57f5140c38527826d7
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364410"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Localizar, instalar e desinstalar aplicações a partir do Microsoft Store

O Microsoft Store é a sua fonte de aplicações e jogos que funcionam com HoloLens. Quando for à Loja no seu HoloLens, quaisquer aplicações que veja lá serão executadas.

As aplicações em HoloLens utilizam a vista 2D ou a vista holográfica. As aplicações que usam vista 2D parecem janelas e podem ser posicionadas à sua volta. As aplicações que usam vista holográfica rodeiam-no e tornam-se a única aplicação que vê.

HoloLens suporta muitas aplicações existentes a partir do Microsoft Store, e novas aplicações construídas especificamente para HoloLens.  Este artigo centra-se nas aplicações holográficas do Microsoft Store.

Para saber mais sobre a instalação e execução de aplicações [personalizadas, leia aplicações holográficas personalizadas.](holographic-custom-apps.md)

## <a name="find-apps"></a>Localizar aplicações

Abra a Microsoft Store do menu **Iniciar.** Em seguida, navegue por aplicativos e jogos. Pode utilizar [comandos de voz](hololens-cortana.md) para pesquisar dizendo "Procurar", uma vez que a janela de pesquisa abre, diga "Comece a ditar" e, em seguida, quando solicitado comece a dizer os seus termos de pesquisa.

> [!NOTE]
> Os requisitos do sistema para dispositivos HoloLens baseiam-se na arquitetura da construção de aplicações. Se uma aplicação construída para HoloLens (1ª geração) não tiver sido atualizada para um Novo UWP na loja para incluir o pacote de arquitetura ARM, então não estará disponível para HoloLens 2 dispositivos. Da mesma forma, se uma aplicação HoloLens 2 não incluir o pacote de arquitetura x86, não estará disponível para dispositivos HoloLens (1ª geração). HoloLens arquiteturas de dispositivos:
>
> - x86 = HoloLens (1ª geração)
> - ARM = HoloLens 2

> [!NOTE]
> No dia 12 de janeiro de 2021, as seguintes aplicações chegarão ao Fim do Suporte em dispositivos HoloLens. Encorajamo-lo a usar o seguinte link no seu dispositivo para usar a versão web da aplicação.

| Aplicação        | Ligação                                          |
|------------|-----------------------------------------------|
| Excel móvel      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Palavra móvel       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint móvel | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> A aplicação OneDrive não é suportada atualmente para contas AZure AD em HoloLens. Recomendamos o download da aplicação Microsoft OneDrive PWA. [Siga estes passos para descarregar a app.]

## <a name="install-apps"></a>Instalar aplicações

Para descarregar aplicativos, terá de ser assinado com uma conta microsoft. Algumas aplicações são gratuitas e podem ser descarregadas imediatamente. Para aplicações que necessitem de uma compra, tem de ser inscrito na Loja com a sua conta Microsoft e ter um método de pagamento válido.

> [!NOTE]
> A conta que usa no Microsoft Store não tem de ser a mesma que a conta com a quais está inscrito. Se estiver a utilizar uma conta de Trabalho ou Escola no seu HoloLens, poderá ter de iniciar sôss com a sua conta pessoal na App da Loja para efetuar uma compra.

> [!TIP]
> Para configurar um método de pagamento, vá a [account.microsoft.com](https://account.microsoft.com/) e selecione **Opções de** pagamento & pagamento  >    >  **Adicione uma opção de pagamento.**

1. Para abrir o menu [ **Iniciar**](holographic-home.md), realize um [gesto Iniciar](/hololens/hololens2-basic-usage#start-gesture) ou [bloom](hololens1-basic-usage.md) gesture no HoloLens (1ª geração).

1. Selecione a aplicação Microsoft Store. Depois da aplicação Store abrir:
   1. Utilize a barra de pesquisa para procurar aplicações.
   1. Selecione aplicações essenciais ou aplicações feitas especificamente para HoloLens de uma das categorias com curadoria.
   1. No topo direito da aplicação Store, selecione o botão **"..."** e, em seguida, selecione **A Minha Biblioteca** para ver quaisquer aplicações previamente adquiridas.

1. **Selecione Get** or **Install** na página da aplicação (pode ser necessária uma compra).

### <a name="install-microsoft-onedrive-pwa-app"></a>Instalar Microsoft OneDrive PWA App

Pré-Requisitos: O utilizador já se juntou ao dispositivo HoloLens 2 ao seu inquilino de trabalho.

1. Abra o menu inicial e lance o navegador Edge.

    ![Menu Iniciar](images/office-pwa-1.jpg)

1. Na sua HoloLens entrar [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) nas credenciais da sua conta de trabalho

    ![Sinal de trabalho em](images/office-pwa-2.jpg)

1. Depois de ter iniciado sessão no seu portal web OneDrive, aguarde 30 a 60 segundos para PWA botão de descarregamento aparecer

    ![PWA botão de instalação](images/office-pwa-3.jpg)

1. Selecione o botão de descarregamento PWA e instale a aplicação

    ![Instalar o pedido](images/office-pwa-4.jpg)

1. Feche o navegador Edge e a partir do menu Iniciar, selecione o botão **All Apps** e lance a App OneDrive PWA com a Microsoft OneDrive 

    ![Todas as aplicações que mostram ambas as aplicações.](images/office-pwa-5.jpg)

    > [!NOTE]
    > O "Microsoft OneDrive" é a app PWA onde como "OneDrive" é o UWP mais velho.

1. Poderá então ver os seus ficheiros OneDrive.

    ![OneDrive PWA](images/office-pwa-6.jpg)

Ver também: [Permitir que os uploads automáticos OneDrive para o negócio](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Atualizar aplicativos

### <a name="manual-updates"></a>Atualizações manuais

Para atualizar uma aplicação que instalou a partir do Microsoft Store, pode atualizar a aplicação a partir da aplicação Microsoft Store. Para aplicações instaladas para o Microsoft Store para Empresas, também pode atualizar essas aplicações a partir do Microsoft Store para Empresas.

1. Para abrir o menu [ **Iniciar**](holographic-home.md), realize um [gesto Iniciar](/hololens/hololens2-basic-usage#start-gesture) ou [bloom](hololens1-basic-usage.md) gesture no HoloLens (1ª geração).

1. Selecione a aplicação Store.

1. Olhe para o topo direito da aplicação Store.

1. Selecione o botão **"..."** ou "Ver mais".

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store imagem de aplicação.](images/store-update-1.png)

1. Selecione **Downloads e atualizações**.
    1. Se o seu dispositivo tiver previamente identificado atualizações, pode haver uma seta para baixo e um número que representa atualizações pendentes.

1. **Selecione Obter atualizações**. O seu dispositivo irá agora procurar por atualizações e defini-las para descarregar e instalar.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store imagem de aplicação de obter atualizações..](images/store-update-2.png.jpg)

> [!NOTE]
> Se as aplicações no seu dispositivo foram distribuídas pela sua organização, podem ser atualizadas através dos mesmos métodos de gestão de aplicações comerciais. Se isto se aplica à sua situação, leia mais através da nossa [visão geral da implementação de aplicações comerciais.](app-deploy-overview.md)
>
> Se pretender atualizar uma aplicação personalizada que tenha sido sideloaded ou implementada, terá de utilizar o mesmo método com a versão atualizada da sua aplicação. Para saber mais sobre a instalação e execução de aplicações [personalizadas, leia aplicações holográficas personalizadas.](holographic-custom-apps.md)

### <a name="automatic-app-updates"></a>Atualizações automáticas de aplicativos

As atualizações automáticas aplicam-se a aplicações Microsoft Store ou Microsoft Store para Empresas, e só podem ser atualizadas automaticamente se tiverem sido instaladas diretamente a partir da Loja. Se instalado a partir do Intune, o TI pode empurrar as atualizações para baixo do MDM sincronizando com o Microsoft Store para Empresas para a versão mais recente disponível para a aplicação.

> [!NOTE]
> Para aplicações provenientes do Microsoft Store para Empresas, você deve ser assinado na Loja e autenticado com o mesmo inquilino que está associado ao catálogo Microsoft Store para Empresas utilizado no dispositivo.

#### <a name="how-automatic-updates-work"></a>Como funcionam as atualizações automáticas

Estão previstas atualizações automáticas de aplicações diárias (aproximadamente a cada 24 horas) sujeitas à disponibilidade da rede. Mantenha o seu dispositivo ativo ou ligado ao AR para receber atualizações. Mesmo que as atualizações de aplicações sejam descarregadas durante o uso diário ativo, elas só serão aplicadas quando a aplicação a ser atualizada já não estiver em uso.

> [!TIP]
> Se possível, carregue o seu dispositivo durante a noite enquanto estiver ligado à rede corporativa. Se as atualizações puderem ser descarregadas e instaladas durante a noite, são menos propensos a interromper o uso do dispositivo ativo.

#### <a name="how-it-administrators-can-control-automatic-updates"></a>Como os administradores de TI podem controlar atualizações automáticas

Os administradores de TI podem controlar atualizações automáticas de aplicações através da política [ApplicationManagement/AllowAppStoreAutoUpdate.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) Esta política permite-lhes ativar ou desativar completamente as atualizações automáticas de aplicações, mas não controla quando ocorrem atualizações.

A partir de [21H2,](hololens-release-notes.md#windows-holographic-version-21h1)os administradores de TI também podem utilizar a política [scheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) para controlar quando as aplicações que estavam a ser utilizadas, mas que não puderam ser atualizadas em tentativas anteriores, devem ser reiniciadas à força.

## <a name="uninstall-apps"></a>Desinstalar aplicações

Há três formas de desinstalar as aplicações. Pode desinstalar aplicações através do Microsoft Store, menu Iniciar ou a partir de Definições.

> [!WARNING]
> Não é possível desinstalar uma aplicação do sistema ou a Microsoft Store si mesma.

> [!IMPORTANT]
> Se o seu HoloLens 2 tiver vários utilizadores, tem de iniciar sessão como o utilizador que instalou a aplicação para desinstalar a aplicação.

### <a name="uninstall-from-the-microsoft-store"></a>Desinstalar do Microsoft Store

Abra o Microsoft Store do menu **Iniciar** e, em seguida, navegue para a aplicação que pretende desinstalar.  Na página 'Guardar' (Loja), cada aplicação instalada tem um botão **Desinstalar.**

### <a name="uninstall-from-the-start-menu"></a>Desinstalar do menu Iniciar

No menu **Iniciar** ou na lista **de todas as aplicações,** navegue para a aplicação. Selecione e mantenha até que o menu apareça e, em seguida, **selecione Desinstalar**.

### <a name="uninstall-from-settings"></a>Desinstalar a partir de Definições

No menu **Iniciar,** selecione **Definições > Apps.** Encontre a aplicação na lista, selecione-a e clique em **Desinstalar**.

Se não conseguir desinstalar uma aplicação, por favor, arquive [o feedback](/hololens/hololens-feedback) utilizando o Feedback Hub.
