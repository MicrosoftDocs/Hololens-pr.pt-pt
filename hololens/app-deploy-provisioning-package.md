---
title: Pacote de Provisionamento
description: Saiba mais sobre a embalagem de aplicativos, provisão, implementação e implementação de aplicativos empresariais para dispositivos HoloLens.
keywords: aplicação, implementação de aplicativos, implementação de aplicativos empresariais, provisionamento
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378560"
---
# <a name="provisioning-package"></a><span data-ttu-id="e01ae-104">Pacote de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="e01ae-104">Provisioning Package</span></span>

<span data-ttu-id="e01ae-105">Os pacotes de provisionamento podem ser utilizados para preparar e configurar dispositivos num ambiente sem acesso à gestão de pontos finais.</span><span class="sxs-lookup"><span data-stu-id="e01ae-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="e01ae-106">Podem também ser implantados num dispositivo independentemente da identidade do utilizador, do estado de inscrição, durante a Experiência out of Box (OOBE), ou através da [aplicação de um pacote de provisionamento durante a configuração](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="e01ae-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="e01ae-107">Considerações relativas aos pacotes de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="e01ae-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="e01ae-108">Aplicativos não públicos</span><span class="sxs-lookup"><span data-stu-id="e01ae-108">Non-Public apps</span></span>
* <span data-ttu-id="e01ae-109">Carga lateral USB apenas</span><span class="sxs-lookup"><span data-stu-id="e01ae-109">USB side-load only</span></span>
* <span data-ttu-id="e01ae-110">Nenhuma atualização automática (requer atualizações manuais via PPKGs)</span><span class="sxs-lookup"><span data-stu-id="e01ae-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="e01ae-111">As aplicações instaladas através de um pacote de provisionamento devem ser assinadas por um certificado na loja de máquinas local.</span><span class="sxs-lookup"><span data-stu-id="e01ae-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="e01ae-112">O fornecimento de pacotes só pode instalar certificados na loja do dispositivo (máquina local), pelo que uma aplicação e certificado podem ser instalados através do mesmo pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="e01ae-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="e01ae-113">Se estiver a implementar o seu certificado a partir do MDM ou a instalar através do [Gestor de Certificados,](certificate-manager.md)certifique-se de que implementa o certificado na loja de máquinas local para assinar as aplicações instaladas desta forma.</span><span class="sxs-lookup"><span data-stu-id="e01ae-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="e01ae-114">Para conhecer os fundamentos da criação de um pacote de provisionamento para dispositivos HoloLens, visite [holoLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="e01ae-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="e01ae-115">Para implementar uma aplicação, tem de começar com o provisionamento avançado.</span><span class="sxs-lookup"><span data-stu-id="e01ae-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="e01ae-116">A HoloLens (1ª gen) tem aplicações de instalação de suporte limitado **(UniversalAppInstall**) utilizando um pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="e01ae-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="e01ae-117">Os dispositivos HoloLens (1ª geração) só suportam a instalação de uma aplicação via PPKG apenas durante o OOBE e apenas com instalações de contexto do utilizador.</span><span class="sxs-lookup"><span data-stu-id="e01ae-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="e01ae-118">Configuração</span><span class="sxs-lookup"><span data-stu-id="e01ae-118">Setup</span></span>

<span data-ttu-id="e01ae-119">Dentro [do Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) dê quatro passos seguidos.</span><span class="sxs-lookup"><span data-stu-id="e01ae-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="e01ae-120">Definir ApplicationManagement/AllowAllTrustedApps para "Sim".</span><span class="sxs-lookup"><span data-stu-id="e01ae-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="e01ae-121">Ver: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="e01ae-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="e01ae-122">Navegue para **UniversalAppInstall**  >  **UserContextAppLicense** insira o **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="e01ae-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="e01ae-123">Consulte [a UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="e01ae-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="e01ae-124">Ver também: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="e01ae-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="e01ae-125">Pode utilizar o Portal do Dispositivo num dispositivo ao que já instalou a sua aplicação.</span><span class="sxs-lookup"><span data-stu-id="e01ae-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="e01ae-126">Visite a página apps, e olhe para a linha PackageRelativeID, todas as informações antes do "!" É o seu **Nome De Família Pacote.**</span><span class="sxs-lookup"><span data-stu-id="e01ae-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="e01ae-127">Em seguida, verá que tem uma nova secção, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="e01ae-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="e01ae-128">Use esta área para carregar o seu pacote de aplicações.</span><span class="sxs-lookup"><span data-stu-id="e01ae-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="e01ae-129">Dependendo se adquiriu a sua aplicação ou construiu a sua própria aplicação LOB, terá de carregar o ficheiro de licença ou certificado de segurança.</span><span class="sxs-lookup"><span data-stu-id="e01ae-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="e01ae-130">Para o ficheiro de licença: navegue para **UniversalAppInstall**  >  **UserContextAppLicence** e navegue até à localização da sua licença e faça o upload.</span><span class="sxs-lookup"><span data-stu-id="e01ae-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="e01ae-131">Para o ficheiro de segurança, navegue em **Certificados** e selecione o seu certificado para instalar ao lado do seu pacote .appx.</span><span class="sxs-lookup"><span data-stu-id="e01ae-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="e01ae-132">Certifique-se de guardar o seu projeto para um local seguro.</span><span class="sxs-lookup"><span data-stu-id="e01ae-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="e01ae-133">Em **seguida,** exporte-o como um **pacote de provisionamento.**</span><span class="sxs-lookup"><span data-stu-id="e01ae-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="e01ae-134">Ver também: [Aplicar o seu pacote de provisionamento à HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="e01ae-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
