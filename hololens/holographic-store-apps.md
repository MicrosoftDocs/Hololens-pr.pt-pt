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
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="66ada-105">Localizar, instalar e desinstalar aplicações a partir da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="66ada-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="66ada-106">A Microsoft Store é a sua fonte de aplicações e jogos que funcionam com holoLens.</span><span class="sxs-lookup"><span data-stu-id="66ada-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="66ada-107">Quando for à Loja dos seus HoloLens, quaisquer aplicações que vejas lá serão executadas.</span><span class="sxs-lookup"><span data-stu-id="66ada-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="66ada-108">As aplicações nos HoloLens utilizam a vista 2D ou a vista holográfica.</span><span class="sxs-lookup"><span data-stu-id="66ada-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="66ada-109">As aplicações que usam vista 2D parecem janelas e podem ser posicionadas à sua volta.</span><span class="sxs-lookup"><span data-stu-id="66ada-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="66ada-110">As aplicações que usam vista holográfica rodeiam-no e tornam-se a única aplicação que vê.</span><span class="sxs-lookup"><span data-stu-id="66ada-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="66ada-111">O HoloLens suporta muitas aplicações existentes a partir da Microsoft Store, e novas aplicações construídas especificamente para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="66ada-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="66ada-112">Este artigo centra-se em aplicações holográficas da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="66ada-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="66ada-113">Para saber mais sobre a instalação e execução de aplicações [personalizadas, leia aplicações holográficas personalizadas.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="66ada-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="66ada-114">Localizar aplicações</span><span class="sxs-lookup"><span data-stu-id="66ada-114">Find apps</span></span>

<span data-ttu-id="66ada-115">Abra a Microsoft Store a partir do menu **Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="66ada-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="66ada-116">Em seguida, navegue por aplicativos e jogos.</span><span class="sxs-lookup"><span data-stu-id="66ada-116">Then browse for apps and games.</span></span> <span data-ttu-id="66ada-117">Pode utilizar [comandos de voz](hololens-cortana.md) para pesquisar dizendo "Procurar", uma vez que a janela de pesquisa abre, diga "Comece a ditar" e, em seguida, quando solicitado comece a dizer os seus termos de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="66ada-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="66ada-118">Os requisitos do sistema para dispositivos HoloLens baseiam-se na arquitetura da construção de aplicações.</span><span class="sxs-lookup"><span data-stu-id="66ada-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="66ada-119">Se uma construção de uma aplicação para HoloLens (1ª geração) não tiver sido atualizada para um Novo UWP na loja para incluir o pacote de arquitetura ARM, então não estará disponível para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="66ada-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="66ada-120">Da mesma forma, se uma aplicação HoloLens 2 não incluir o pacote de arquitetura x86, não estará disponível para dispositivos HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="66ada-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="66ada-121">Arquiteturas de dispositivos HoloLens:</span><span class="sxs-lookup"><span data-stu-id="66ada-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="66ada-122">x86 = HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="66ada-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="66ada-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="66ada-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="66ada-124">No dia 12 de janeiro de 2021, as seguintes aplicações chegarão ao Fim do Suporte em dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="66ada-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="66ada-125">Encorajamo-lo a usar o seguinte link no seu dispositivo para usar a versão web da aplicação.</span><span class="sxs-lookup"><span data-stu-id="66ada-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="66ada-126">Aplicação</span><span class="sxs-lookup"><span data-stu-id="66ada-126">App</span></span>        | <span data-ttu-id="66ada-127">Ligação</span><span class="sxs-lookup"><span data-stu-id="66ada-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="66ada-128">Excel móvel</span><span class="sxs-lookup"><span data-stu-id="66ada-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="66ada-129">Palavra móvel</span><span class="sxs-lookup"><span data-stu-id="66ada-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="66ada-130">PowerPoint móvel</span><span class="sxs-lookup"><span data-stu-id="66ada-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="66ada-131">Instalar aplicações</span><span class="sxs-lookup"><span data-stu-id="66ada-131">Install apps</span></span>

<span data-ttu-id="66ada-132">Para descarregar aplicativos, terá de ser assinado com uma conta microsoft.</span><span class="sxs-lookup"><span data-stu-id="66ada-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="66ada-133">Algumas aplicações são gratuitas e podem ser descarregadas imediatamente.</span><span class="sxs-lookup"><span data-stu-id="66ada-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="66ada-134">Para aplicações que necessitem de uma compra, tem de ser inscrito na Loja com a sua conta Microsoft e ter um método de pagamento válido.</span><span class="sxs-lookup"><span data-stu-id="66ada-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>

> [!NOTE]
> <span data-ttu-id="66ada-135">A conta que utiliza na Microsoft Store não tem de ser a mesma que a conta com a que está inscrito.</span><span class="sxs-lookup"><span data-stu-id="66ada-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="66ada-136">Se estiver a utilizar uma conta De Trabalho ou Escola nos seus HoloLens, poderá ter de iniciar sôss com a sua conta pessoal na App da Loja para efetuar uma compra.</span><span class="sxs-lookup"><span data-stu-id="66ada-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="66ada-137">Para configurar um método de pagamento, vá a [account.microsoft.com](https://account.microsoft.com/) e selecione **Opções de** pagamento & pagamento  >    >  **Adicione uma opção de pagamento.**</span><span class="sxs-lookup"><span data-stu-id="66ada-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="66ada-138">Para abrir o menu [ **Iniciar,**](holographic-home.md)realize um [gesto Iniciar](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) ou [bloom](hololens1-basic-usage.md) gesture em HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="66ada-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="66ada-139">Selecione a aplicação Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="66ada-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="66ada-140">Depois da aplicação Store abrir:</span><span class="sxs-lookup"><span data-stu-id="66ada-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="66ada-141">Utilize a barra de pesquisa para procurar aplicações.</span><span class="sxs-lookup"><span data-stu-id="66ada-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="66ada-142">Selecione aplicativos ou aplicativos essenciais feitos especificamente para HoloLens de uma das categorias com curadoria.</span><span class="sxs-lookup"><span data-stu-id="66ada-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="66ada-143">No topo à direita da aplicação Store, selecione o botão **"..."** e, em seguida, selecione **A Minha Biblioteca** para ver quaisquer aplicações previamente adquiridas.</span><span class="sxs-lookup"><span data-stu-id="66ada-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>

1. <span data-ttu-id="66ada-144">Selecione **Get** or **Install** na página da aplicação (pode ser necessária uma compra).</span><span class="sxs-lookup"><span data-stu-id="66ada-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="66ada-145">Atualizar aplicativos</span><span class="sxs-lookup"><span data-stu-id="66ada-145">Update Apps</span></span>

<span data-ttu-id="66ada-146">Para atualizar uma aplicação que instalou a partir da Microsoft Store, pode atualizar a aplicação a partir da aplicação da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="66ada-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="66ada-147">Para aplicações instaladas para a Microsoft Store para negócios, também pode atualizar essas aplicações a partir da Microsoft Store para business.</span><span class="sxs-lookup"><span data-stu-id="66ada-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 

1. <span data-ttu-id="66ada-148">Para abrir o menu [ **Iniciar,**](holographic-home.md)realize um [gesto Iniciar](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) ou [bloom](hololens1-basic-usage.md) gesture em HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="66ada-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="66ada-149">Selecione a aplicação Store.</span><span class="sxs-lookup"><span data-stu-id="66ada-149">Select the Store app.</span></span>

1. <span data-ttu-id="66ada-150">Olhe para o topo direito da aplicação Store.</span><span class="sxs-lookup"><span data-stu-id="66ada-150">Look to the top right of the Store app.</span></span> 

1. <span data-ttu-id="66ada-151">Selecione o botão **"..."** ou "Ver mais".</span><span class="sxs-lookup"><span data-stu-id="66ada-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="66ada-152">![Imagem de imagem de aplicativo da Microsoft Store.](images/store-update-1.png)</span><span class="sxs-lookup"><span data-stu-id="66ada-152">![Microsoft Store app screenshot.](images/store-update-1.png)</span></span>

1. <span data-ttu-id="66ada-153">Selecione **Downloads e atualizações**.</span><span class="sxs-lookup"><span data-stu-id="66ada-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="66ada-154">Se o seu dispositivo tiver previamente identificado atualizações, pode haver uma seta para baixo e um número que representa atualizações pendentes.</span><span class="sxs-lookup"><span data-stu-id="66ada-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>

1. <span data-ttu-id="66ada-155">**Selecione Obter atualizações**.</span><span class="sxs-lookup"><span data-stu-id="66ada-155">Select **Get updates**.</span></span> <span data-ttu-id="66ada-156">O seu dispositivo irá agora procurar por atualizações e defini-las para descarregar e instalar.</span><span class="sxs-lookup"><span data-stu-id="66ada-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="66ada-157">![Imagem de imagem de aplicação da Microsoft Store para obter atualizações..](images/store-update-2.png.jpg)</span><span class="sxs-lookup"><span data-stu-id="66ada-157">![Microsoft Store app screenshot of getting updates..](images/store-update-2.png.jpg)</span></span>

> [!NOTE]
> <span data-ttu-id="66ada-158">Se as aplicações no seu dispositivo foram distribuídas pela sua organização, podem ser atualizadas através dos mesmos métodos de gestão de aplicações comerciais.</span><span class="sxs-lookup"><span data-stu-id="66ada-158">If the apps on your device were distributed by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="66ada-159">Se isto se aplica à sua situação, leia mais através da nossa [visão geral da implementação de aplicações comerciais.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="66ada-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="66ada-160">Se quiser atualizar uma aplicação personalizada que tenha sido carregada ou implementada, terá de utilizar o mesmo método com a versão atualizada da sua app.</span><span class="sxs-lookup"><span data-stu-id="66ada-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="66ada-161">Para saber mais sobre a instalação e execução de aplicações [personalizadas, leia aplicações holográficas personalizadas.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="66ada-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="66ada-162">Desinstalar aplicações</span><span class="sxs-lookup"><span data-stu-id="66ada-162">Uninstall apps</span></span>

<span data-ttu-id="66ada-163">Há três formas de desinstalar as aplicações.</span><span class="sxs-lookup"><span data-stu-id="66ada-163">There are three ways to uninstall applications.</span></span> <span data-ttu-id="66ada-164">Pode desinstalar aplicações através do menu Microsoft Store, Iniciar ou a partir de Definições.</span><span class="sxs-lookup"><span data-stu-id="66ada-164">You can uninstall applications through the Microsoft Store, Start menu or from Settings.</span></span> 

> [!WARNING]
> <span data-ttu-id="66ada-165">Não é possível desinstalar uma aplicação do sistema ou a própria Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="66ada-165">You can not uninstall a system app or the Microsoft Store itself.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66ada-166">Se o HoloLens 2 tiver vários utilizadores, tem de iniciar sessão como o utilizador que instalou a aplicação para desinstalar a aplicação.</span><span class="sxs-lookup"><span data-stu-id="66ada-166">If your HoloLens 2 has multiple users, you must be logged in as the user who installed the app to uninstall it.</span></span> 

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="66ada-167">Desinstalar da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="66ada-167">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="66ada-168">Abra a Microsoft Store a partir do menu **Iniciar** e, em seguida, navegue para a aplicação que pretende desinstalar.</span><span class="sxs-lookup"><span data-stu-id="66ada-168">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="66ada-169">Na página 'Guardar' (Loja), cada aplicação instalada tem um botão **Desinstalar.**</span><span class="sxs-lookup"><span data-stu-id="66ada-169">On the Store page, each installed application has an **Uninstall** button.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="66ada-170">Desinstalar a partir do menu Iniciar</span><span class="sxs-lookup"><span data-stu-id="66ada-170">Uninstall from the Start menu</span></span>

<span data-ttu-id="66ada-171">No menu **Iniciar** ou na lista **de todas as aplicações,** navegue para a aplicação.</span><span class="sxs-lookup"><span data-stu-id="66ada-171">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="66ada-172">Selecione e mantenha até que o menu apareça e, em seguida, selecione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="66ada-172">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-settings"></a><span data-ttu-id="66ada-173">Desinstalar a partir de Definições</span><span class="sxs-lookup"><span data-stu-id="66ada-173">Uninstall from Settings</span></span>
<span data-ttu-id="66ada-174">No menu **Iniciar,** selecione **Definições -> Apps.**</span><span class="sxs-lookup"><span data-stu-id="66ada-174">On the **Start** menu, select **Settings -> Apps.**</span></span> <span data-ttu-id="66ada-175">Encontre a aplicação na lista, selecione-a e clique em **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="66ada-175">Find the app from the list, select it and then click **Uninstall**.</span></span>

<span data-ttu-id="66ada-176">Se não conseguir desinstalar uma aplicação, por favor, arquive o [feedback](https://docs.microsoft.com/hololens/hololens-feedback) utilizando o Feedback Hub.</span><span class="sxs-lookup"><span data-stu-id="66ada-176">If you are unable to uninstall an app, please file [feedback](https://docs.microsoft.com/hololens/hololens-feedback) using the Feedback Hub.</span></span>
