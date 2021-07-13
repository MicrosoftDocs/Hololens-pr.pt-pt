---
title: Gerir aplicativos personalizados para HoloLens (1ª gen)
description: Aprenda a instalar, desinstalar e carregar as aplicações holográficas personalizadas em dispositivos HoloLens utilizando o Portal do Dispositivo e Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635913"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="fcca7-104">Gerir aplicativos personalizados para HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="fcca7-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="fcca7-105">HoloLens suporta muitas aplicações existentes a partir do Microsoft Store, bem como novas aplicações construídas especificamente para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fcca7-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="fcca7-106">Este artigo centra-se em aplicações holográficas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="fcca7-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="fcca7-107">Para obter mais informações sobre aplicações da loja, consulte [Gerir aplicações com a loja.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="fcca7-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcca7-108">Foram criadas as seguintes informações para o HoloLens (1º género), também chamada de HoloLens Developer Edition na época.</span><span class="sxs-lookup"><span data-stu-id="fcca7-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="fcca7-109">Como tal, as aplicações de sideloading através do portal do dispositivo e a instalação de apps através de Visual Studio eram comuns na altura.</span><span class="sxs-lookup"><span data-stu-id="fcca7-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="fcca7-110">Para implementações empresariais não recomendamos o modo de desenvolvimento, que ambos os métodos utilizam.</span><span class="sxs-lookup"><span data-stu-id="fcca7-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="fcca7-111">Se estiver interessado num método de implementação de aplicações seguras, por favor reveja a nossa [App Management: Overview](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fcca7-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="fcca7-112">Se estiver à procura de um dos métodos de instalação de aplicações para HoloLens 2 dispositivos, consulte:</span><span class="sxs-lookup"><span data-stu-id="fcca7-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
>
> - [<span data-ttu-id="fcca7-113">Portal do Dispositivo: Instalar uma App</span><span class="sxs-lookup"><span data-stu-id="fcca7-113">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="fcca7-114">Utilizar Visual Studio para implementar e depurar apps</span><span class="sxs-lookup"><span data-stu-id="fcca7-114">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="fcca7-115">Instalar aplicações personalizadas</span><span class="sxs-lookup"><span data-stu-id="fcca7-115">Install custom apps</span></span>

<span data-ttu-id="fcca7-116">Pode instalar as suas próprias aplicações no HoloLens, quer através do Portal do Dispositivo, quer através da implementação das aplicações a partir de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fcca7-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="fcca7-117">Instalar um pacote de aplicações com o Portal do Dispositivo</span><span class="sxs-lookup"><span data-stu-id="fcca7-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="fcca7-118">Estabeleça uma ligação do Portal do [Dispositivo](/windows/mixed-reality/using-the-windows-device-portal) ao HoloLens-alvo.</span><span class="sxs-lookup"><span data-stu-id="fcca7-118">Establish a connection from [Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="fcca7-119">Na navegação à esquerda, navegue para a página **Apps.**</span><span class="sxs-lookup"><span data-stu-id="fcca7-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="fcca7-120">No **Âmbito do Pacote de Aplicações,** consulte o ficheiro .appx que está associado à sua aplicação.</span><span class="sxs-lookup"><span data-stu-id="fcca7-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="fcca7-121">Certifique-se de que faz referência a quaisquer ficheiros de dependência e certificados associados.</span><span class="sxs-lookup"><span data-stu-id="fcca7-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="fcca7-122">Selecione **Go**.</span><span class="sxs-lookup"><span data-stu-id="fcca7-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fcca7-123">![Instale o formulário de aplicação no Portal do Dispositivo Windows no Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="fcca7-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="fcca7-124">Implementação a partir de Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="fcca7-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="fcca7-125">Abra a solução de Visual Studio da sua aplicação (.sln ficheiro).</span><span class="sxs-lookup"><span data-stu-id="fcca7-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="fcca7-126">Abra as **Propriedades** do projeto.</span><span class="sxs-lookup"><span data-stu-id="fcca7-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="fcca7-127">Selecione a seguinte configuração de construção: **Master/x86/Remote Machine**.</span><span class="sxs-lookup"><span data-stu-id="fcca7-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="fcca7-128">Quando seleciona **máquina remota:**</span><span class="sxs-lookup"><span data-stu-id="fcca7-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="fcca7-129">Certifique-se de que o endereço aponta para o endereço IP Wi-Fi do seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fcca7-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="fcca7-130">Definir a autenticação para a Universal (Protocolo Não **Encriptado)**.</span><span class="sxs-lookup"><span data-stu-id="fcca7-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="fcca7-131">Construa a sua solução.</span><span class="sxs-lookup"><span data-stu-id="fcca7-131">Build your solution.</span></span>

1. <span data-ttu-id="fcca7-132">Para implementar a aplicação do seu PC de desenvolvimento para o seu HoloLens, selecione **Remote Machine**.</span><span class="sxs-lookup"><span data-stu-id="fcca7-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="fcca7-133">Se já tiver uma construção existente sobre o HoloLens, selecione **Sim** para instalar esta versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="fcca7-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Implementação de Máquinas Remotas para apps para Microsoft HoloLens em Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="fcca7-135">A aplicação instalará e lançará automaticamente no seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fcca7-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="fcca7-136">Depois de instalar uma aplicação, vai encontrá-la na lista **de aplicações All** **(Start**  >  **All apps).**</span><span class="sxs-lookup"><span data-stu-id="fcca7-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
