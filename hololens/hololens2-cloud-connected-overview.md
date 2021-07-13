---
title: Visão geral da Nuvem conectada HoloLens 2 com Assistência Remota
description: Saiba como inscrever HoloLens 2 dispositivos através de uma rede Cloud Connected utilizando o Dynamics 365 Remote Assist.
keywords: HoloLens, gestão, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Device Management
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635131"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="15fce-104">Guia de Implementação - Cloud conectado HoloLens 2 com Assistência Remota – Visão Geral</span><span class="sxs-lookup"><span data-stu-id="15fce-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="15fce-105">Este guia ajudará os profissionais de TI a planear e implementar Microsoft HoloLens 2 dispositivos com Assistência Remota à sua organização.</span><span class="sxs-lookup"><span data-stu-id="15fce-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="15fce-106">Isto servirá como um modelo para implementações de prova de conceito para a sua organização em vários casos de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="15fce-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="15fce-107">A configuração é semelhante ao [cenário A: Implementar para dispositivos de ligação em nuvem](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span><span class="sxs-lookup"><span data-stu-id="15fce-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="15fce-108">Durante o guia, iremos cobrir como inscrever os seus dispositivos na gestão do seu dispositivo, aplicar licenças conforme necessário e validar que os seus utilizadores finais são capazes de utilizar imediatamente o Remote Assist após a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15fce-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="15fce-109">Para isso, vamos analisar as importantes infraestruturas necessárias para se instalar e funcionar – conseguir a implantação em escala com HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="15fce-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="15fce-110">Nenhuma outra restrição ou configurações do dispositivo será aplicada neste guia, no entanto, encorajamos-o a explorar essas opções após o acabamento.</span><span class="sxs-lookup"><span data-stu-id="15fce-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15fce-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="15fce-111">Prerequisites</span></span>

<span data-ttu-id="15fce-112">Devem estar em vigor as infraestruturas que se seguem para implantar o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="15fce-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="15fce-113">Caso contrário, a criação de Azure e Intune está incluída neste guia:</span><span class="sxs-lookup"><span data-stu-id="15fce-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="15fce-114">Esta é uma configuração semelhante ao [cenário A: Implementar para dispositivos de ligação em nuvem](/hololens/common-scenarios#scenario-a), que é uma boa opção para muitas implementações de Prova de Conceito, que incluirá:</span><span class="sxs-lookup"><span data-stu-id="15fce-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="15fce-115">Wi-Fi redes estão tipicamente totalmente abertas aos serviços da Internet e cloud</span><span class="sxs-lookup"><span data-stu-id="15fce-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="15fce-116">Azure AD Junte-se à Inscrição automática do MDM -- MDM (Intune) Gerido</span><span class="sxs-lookup"><span data-stu-id="15fce-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="15fce-117">Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="15fce-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="15fce-118">É suportado um único ou múltiplo por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15fce-118">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Cenário conectado à nuvem" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="15fce-120">Saiba mais sobre assistência remota</span><span class="sxs-lookup"><span data-stu-id="15fce-120">Learn about Remote Assist</span></span>

<span data-ttu-id="15fce-121">O Remote Assist permite a manutenção e reparação colaborativa, inspeção remota, bem como partilha e formação de conhecimentos.</span><span class="sxs-lookup"><span data-stu-id="15fce-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="15fce-122">Ao ligar pessoas em diferentes funções e locais, um técnico que usa Assistência Remota pode ligar-se a um colaborador remoto em Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="15fce-122">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="15fce-123">Podem combinar vídeo, imagens e anotações para resolver problemas em tempo real, mesmo quando são&#39;não no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="15fce-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="15fce-124">Os colaboradores remotos podem inserir imagens de referência, esquemas e outras informações úteis que o técnico&#39;espaço físico para que possam consultar o esquema enquanto trabalham no heads-up e mãos-livres no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="15fce-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="15fce-125">Licenciamento e Requisitos de Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="15fce-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="15fce-126">Conta AZURE AD (necessária para a aquisição da subscrição e atribuição de licenças)</span><span class="sxs-lookup"><span data-stu-id="15fce-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="15fce-127">[Subscrição de Assistência Remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [Ensaio de Assistência Remota)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="15fce-127">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="15fce-128">Dynamics 365 Remote Assist utilizador</span><span class="sxs-lookup"><span data-stu-id="15fce-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="15fce-129">Licença de Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="15fce-129">Remote Assist license</span></span>
- <span data-ttu-id="15fce-130">Conectividade da rede</span><span class="sxs-lookup"><span data-stu-id="15fce-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="15fce-131">Microsoft Teams utilizador</span><span class="sxs-lookup"><span data-stu-id="15fce-131">Microsoft Teams user</span></span>

- <span data-ttu-id="15fce-132">Microsoft Teams ou [Teams Freemium.](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="15fce-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="15fce-133">Conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="15fce-133">Network connectivity</span></span>

<span data-ttu-id="15fce-134">Se planeia implementar este [cenário de inquilinos cruzados,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)poderá necessitar de uma licença de Barreiras de Informação.</span><span class="sxs-lookup"><span data-stu-id="15fce-134">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="15fce-135">Consulte [este artigo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se é necessária uma Licença de Barreira de Informação.</span><span class="sxs-lookup"><span data-stu-id="15fce-135">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="15fce-136">Neste guia:</span><span class="sxs-lookup"><span data-stu-id="15fce-136">In this guide you will:</span></span>

<span data-ttu-id="15fce-137">Preparar:</span><span class="sxs-lookup"><span data-stu-id="15fce-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="15fce-138">Conheça os elementos essenciais da infraestrutura para HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="15fce-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="15fce-139">Saiba mais sobre o Azure AD e crie um se não&#39;o tiver.</span><span class="sxs-lookup"><span data-stu-id="15fce-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="15fce-140">Saiba mais sobre a gestão de identidade e como configurar melhor as contas AD da Azure.</span><span class="sxs-lookup"><span data-stu-id="15fce-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="15fce-141">Saiba mais sobre o MDM e prepare-se com o Intune se não&#39;já não tenha um pronto.</span><span class="sxs-lookup"><span data-stu-id="15fce-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="15fce-142">Conheça os requisitos de networking do Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="15fce-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="15fce-143">Opcionalmente: VPN para ligar aos recursos organizacionais</span><span class="sxs-lookup"><span data-stu-id="15fce-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="15fce-144">Configure:</span><span class="sxs-lookup"><span data-stu-id="15fce-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="15fce-145">Como criar Utilizadores e Grupos.</span><span class="sxs-lookup"><span data-stu-id="15fce-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="15fce-146">Como configurar a inscrição automática dentro do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="15fce-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="15fce-147">Como atribuir as suas licenças de inscrição.</span><span class="sxs-lookup"><span data-stu-id="15fce-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="15fce-148">Implementação:</span><span class="sxs-lookup"><span data-stu-id="15fce-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="15fce-149">Crie o seu HoloLens 2 e valide a inscrição.</span><span class="sxs-lookup"><span data-stu-id="15fce-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="15fce-150">Valide que pode esporar uma chamada de Assistência Remota.</span><span class="sxs-lookup"><span data-stu-id="15fce-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="15fce-151">Manter:</span><span class="sxs-lookup"><span data-stu-id="15fce-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="15fce-152">Como atualizar o Remote Assist utilizando a aplicação Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="15fce-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="15fce-153">A fazer um plano de apoio.</span><span class="sxs-lookup"><span data-stu-id="15fce-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="15fce-154">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="15fce-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="15fce-155">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="15fce-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="15fce-156">Implementação ligada à nuvem - Prepare-se</span><span class="sxs-lookup"><span data-stu-id="15fce-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

