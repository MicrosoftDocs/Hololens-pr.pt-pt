---
title: Localizar, instalar e desinstalar aplicações
description: A Microsoft Store é a sua fonte de apps e jogos que funcionam com holoLens.  Saiba mais sobre encontrar, instalar e desinstalar aplicações holográficas.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
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
ms.openlocfilehash: b44ee3f9ce5aa31205feb9bb27202351e0014364
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379851"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Localizar, instalar e desinstalar aplicações a partir da Microsoft Store

A Microsoft Store é a sua fonte de aplicações e jogos que funcionam com holoLens. Quando for à Loja dos seus HoloLens, quaisquer aplicações que vejas lá serão executadas.

As aplicações nos HoloLens utilizam a vista 2D ou a vista holográfica. As aplicações que usam vista 2D parecem janelas e podem ser posicionadas à sua volta. As aplicações que usam vista holográfica rodeiam-no e tornam-se a única aplicação que vê.

O HoloLens suporta muitas aplicações existentes a partir da Microsoft Store, e novas aplicações construídas especificamente para HoloLens.  Este artigo centra-se em aplicações holográficas da Microsoft Store.

Para saber mais sobre a instalação e execução de aplicações [personalizadas, leia aplicações holográficas personalizadas.](holographic-custom-apps.md)

## <a name="find-apps"></a>Localizar aplicações

Abra a Microsoft Store a partir do menu **Iniciar.** Em seguida, navegue por aplicativos e jogos. Pode utilizar [comandos de voz](hololens-cortana.md) para pesquisar dizendo "Procurar", uma vez que a janela de pesquisa abre, diga "Comece a ditar" e, em seguida, quando solicitado comece a dizer os seus termos de pesquisa.

> [!NOTE]
> Os requisitos do sistema para dispositivos HoloLens baseiam-se na arquitetura da construção de aplicações. Se uma construção de uma aplicação para HoloLens (1ª geração) não tiver sido atualizada para um Novo UWP na loja para incluir o pacote de arquitetura ARM, então não estará disponível para dispositivos HoloLens 2. Da mesma forma, se uma aplicação HoloLens 2 não incluir o pacote de arquitetura x86, não estará disponível para dispositivos HoloLens (1ª geração). Arquiteturas de dispositivos HoloLens:
> - x86 = HoloLens (1ª geração)
> - ARM = HoloLens 2

> [!NOTE]
> No dia 12 de janeiro de 2021, as seguintes aplicações chegarão ao Fim do Suporte em dispositivos HoloLens. Encorajamo-lo a usar o seguinte link no seu dispositivo para usar a versão web da aplicação.

| Aplicação        | Ligação                                          |
|------------|-----------------------------------------------|
| Excel móvel      | https://office.live.com/start/Excel.aspx      |
| Palavra móvel       | https://office.live.com/start/Word.aspx       |
| PowerPoint móvel | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a>Instalar aplicações

Para descarregar aplicativos, terá de ser assinado com uma conta microsoft. Algumas aplicações são gratuitas e podem ser descarregadas imediatamente. Para aplicações que necessitem de uma compra, tem de ser inscrito na Loja com a sua conta Microsoft e ter um método de pagamento válido.

> [!NOTE]
> A conta que utiliza na Microsoft Store não tem de ser a mesma que a conta com a que está inscrito. Se estiver a utilizar uma conta De Trabalho ou Escola nos seus HoloLens, poderá ter de iniciar sôss com a sua conta pessoal na App da Loja para efetuar uma compra.

> [!TIP]
> Para configurar um método de pagamento, vá a [account.microsoft.com](https://account.microsoft.com/) e selecione **Opções de** pagamento & pagamento  >    >  **Adicione uma opção de pagamento.**

1. Para abrir o menu [ **Iniciar,**](holographic-home.md)realize um [gesto Iniciar](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) ou [bloom](hololens1-basic-usage.md) gesture em HoloLens (1ª geração).

1. Selecione a aplicação Microsoft Store. Depois da aplicação Store abrir:
   1. Utilize a barra de pesquisa para procurar aplicações. 
   1. Selecione aplicativos ou aplicativos essenciais feitos especificamente para HoloLens de uma das categorias com curadoria.
   1. No topo à direita da aplicação Store, selecione o botão **"..."** e, em seguida, selecione **A Minha Biblioteca** para ver quaisquer aplicações previamente adquiridas.

1. Selecione **Get** or **Install** na página da aplicação (pode ser necessária uma compra).

## <a name="update-apps"></a>Atualizar aplicativos

Para atualizar uma aplicação que instalou a partir da Microsoft Store, pode atualizar a aplicação a partir da aplicação da Microsoft Store. Para aplicações instaladas para a Microsoft Store para negócios, também pode atualizar essas aplicações a partir da Microsoft Store para business. 

1. Para abrir o menu [ **Iniciar,**](holographic-home.md)realize um [gesto Iniciar](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) ou [bloom](hololens1-basic-usage.md) gesture em HoloLens (1ª geração).

1. Selecione a aplicação Store.

1. Olhe para o topo direito da aplicação Store. 

1. Selecione o botão **"..."** ou "Ver mais".

   > [!div class="mx-imgBorder"]
   > ![Imagem de imagem de aplicativo da Microsoft Store.](images/store-update-1.png)

1. Selecione **Downloads e atualizações**.
    1. Se o seu dispositivo tiver previamente identificado atualizações, pode haver uma seta para baixo e um número que representa atualizações pendentes.

1. **Selecione Obter atualizações**. O seu dispositivo irá agora procurar por atualizações e defini-las para descarregar e instalar. 
 
   > [!div class="mx-imgBorder"]
   > ![Imagem de imagem de aplicação da Microsoft Store para obter atualizações..](images/store-update-2.png.jpg)

> [!NOTE]
> Se as aplicações no seu dispositivo foram distribuídas pela sua organização, podem ser atualizadas através dos mesmos métodos de gestão de aplicações comerciais. Se isto se aplica à sua situação, leia mais através da nossa [visão geral da implementação de aplicações comerciais.](app-deploy-overview.md)
>
> Se quiser atualizar uma aplicação personalizada que tenha sido carregada ou implementada, terá de utilizar o mesmo método com a versão atualizada da sua app. Para saber mais sobre a instalação e execução de aplicações [personalizadas, leia aplicações holográficas personalizadas.](holographic-custom-apps.md)

## <a name="uninstall-apps"></a>Desinstalar aplicações

Há três formas de desinstalar as aplicações. Pode desinstalar aplicações através do menu Microsoft Store, Iniciar ou a partir de Definições. 

> [!WARNING]
> Não é possível desinstalar uma aplicação do sistema ou a própria Microsoft Store.

> [!IMPORTANT]
> Se o HoloLens 2 tiver vários utilizadores, tem de iniciar sessão como o utilizador que instalou a aplicação para desinstalar a aplicação. 

### <a name="uninstall-from-the-microsoft-store"></a>Desinstalar da Microsoft Store

Abra a Microsoft Store a partir do menu **Iniciar** e, em seguida, navegue para a aplicação que pretende desinstalar.  Na página 'Guardar' (Loja), cada aplicação instalada tem um botão **Desinstalar.**

### <a name="uninstall-from-the-start-menu"></a>Desinstalar a partir do menu Iniciar

No menu **Iniciar** ou na lista **de todas as aplicações,** navegue para a aplicação. Selecione e mantenha até que o menu apareça e, em seguida, selecione **Desinstalar**.

### <a name="uninstall-from-settings"></a>Desinstalar a partir de Definições
No menu **Iniciar,** selecione **Definições -> Apps.** Encontre a aplicação na lista, selecione-a e clique em **Desinstalar**.

Se não conseguir desinstalar uma aplicação, por favor, arquive o [feedback](https://docs.microsoft.com/hololens/hololens-feedback) utilizando o Feedback Hub.
