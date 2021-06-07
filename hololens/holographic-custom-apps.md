---
title: Gerir aplicativos personalizados para HoloLens (1ª gen)
description: Aprenda a instalar, desinstalar e carregar as aplicações holográficas personalizadas em dispositivos HoloLens utilizando o Portal do Dispositivo e o Estúdio Visual.
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378535"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="20003-104">Gerir aplicativos personalizados para HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="20003-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="20003-105">O HoloLens suporta muitas aplicações existentes a partir da Microsoft Store, bem como novas aplicações construídas especificamente para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="20003-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="20003-106">Este artigo centra-se em aplicações holográficas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="20003-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="20003-107">Para obter mais informações sobre aplicações da loja, consulte [Gerir aplicações com a loja.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="20003-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20003-108">A seguinte informação foi criada para os HoloLens (1º género), também chamada de HoloLens Developer Edition na época.</span><span class="sxs-lookup"><span data-stu-id="20003-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="20003-109">Como tal, as aplicações de sideloading através do portal do dispositivo e a instalação de apps via Visual Studio eram comuns na altura.</span><span class="sxs-lookup"><span data-stu-id="20003-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="20003-110">Para implementações empresariais não recomendamos o modo de desenvolvimento, que ambos os métodos utilizam.</span><span class="sxs-lookup"><span data-stu-id="20003-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="20003-111">Se estiver interessado num método de implementação de aplicações seguras, por favor reveja a nossa [App Management: Overview](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="20003-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="20003-112">Se estiver à procura de um dos métodos de instalação de aplicações para dispositivos HoloLens 2, consulte:</span><span class="sxs-lookup"><span data-stu-id="20003-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="20003-113">Portal do Dispositivo: Instalar uma App</span><span class="sxs-lookup"><span data-stu-id="20003-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="20003-114">Utilização do Estúdio Visual para implementar e depurar apps</span><span class="sxs-lookup"><span data-stu-id="20003-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="20003-115">Instalar aplicações personalizadas</span><span class="sxs-lookup"><span data-stu-id="20003-115">Install custom apps</span></span>

<span data-ttu-id="20003-116">Pode instalar as suas próprias aplicações no HoloLens, quer utilizando o Portal do Dispositivo, quer implantando as aplicações a partir do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="20003-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="20003-117">Instalar um pacote de aplicações com o Portal do Dispositivo</span><span class="sxs-lookup"><span data-stu-id="20003-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="20003-118">Estabeleça uma ligação do Portal do [Dispositivo](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) ao HoloLens alvo.</span><span class="sxs-lookup"><span data-stu-id="20003-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="20003-119">Na navegação à esquerda, navegue para a página **Apps.**</span><span class="sxs-lookup"><span data-stu-id="20003-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="20003-120">No **Âmbito do Pacote de Aplicações,** consulte o ficheiro .appx que está associado à sua aplicação.</span><span class="sxs-lookup"><span data-stu-id="20003-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="20003-121">Certifique-se de que faz referência a quaisquer ficheiros de dependência e certificados associados.</span><span class="sxs-lookup"><span data-stu-id="20003-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="20003-122">Selecione **Go**.</span><span class="sxs-lookup"><span data-stu-id="20003-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="20003-123">![Instale o formulário de aplicação no Portal do Dispositivo Windows no Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="20003-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="20003-124">Implementação do Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="20003-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="20003-125">Abra a solução visual studio da sua aplicação (.sln ficheiro).</span><span class="sxs-lookup"><span data-stu-id="20003-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="20003-126">Abra as **Propriedades** do projeto.</span><span class="sxs-lookup"><span data-stu-id="20003-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="20003-127">Selecione a seguinte configuração de construção: **Master/x86/Remote Machine**.</span><span class="sxs-lookup"><span data-stu-id="20003-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="20003-128">Quando seleciona **máquina remota:**</span><span class="sxs-lookup"><span data-stu-id="20003-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="20003-129">Certifique-se de que o endereço aponta para o endereço IP Wi-Fi dos seus HoloLens.</span><span class="sxs-lookup"><span data-stu-id="20003-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="20003-130">Definir a autenticação para a Universal (Protocolo Não **Encriptado)**.</span><span class="sxs-lookup"><span data-stu-id="20003-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="20003-131">Construa a sua solução.</span><span class="sxs-lookup"><span data-stu-id="20003-131">Build your solution.</span></span>

1. <span data-ttu-id="20003-132">Para implementar a aplicação do seu PC de desenvolvimento para os hololens, selecione **Remote Machine**.</span><span class="sxs-lookup"><span data-stu-id="20003-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="20003-133">Se já tem uma construção existente nos HoloLens, selecione **Sim** para instalar esta versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="20003-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Implementação de máquina remota para apps para Microsoft HoloLens em Estúdio Visual](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="20003-135">A aplicação instalará e lançará automaticamente nos seus HoloLens.</span><span class="sxs-lookup"><span data-stu-id="20003-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="20003-136">Depois de instalar uma aplicação, vai encontrá-la na lista **de aplicações All** **(Start**  >  **All apps).**</span><span class="sxs-lookup"><span data-stu-id="20003-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
