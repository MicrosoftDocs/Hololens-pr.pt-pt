---
title: Guia de Implementação - HoloLens 2 conectado corporativo com Dinâmica 365 Guias - Visão geral
description: Saiba como inscrever HoloLens 2 dispositivos com Dinâmica 365 Guides sobre uma rede conectada corporativa.
keywords: HoloLens, gestão, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Device Management
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637018"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="a84de-104">Guia de Implementação - Corporate Connected HoloLens 2 com Dinâmica 365 Guias - Visão geral</span><span class="sxs-lookup"><span data-stu-id="a84de-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="a84de-105">Este guia ajudará os profissionais de TI a planear e implementar Microsoft HoloLens 2 dispositivos com Guias Dinâmicos 365 (Guias) para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="a84de-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="a84de-106">Este guia é ótimo para pilotos, bem como implementações de produção e é semelhante ao Cenário B: Implementar dentro do guia [de rede da sua organização.](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network)</span><span class="sxs-lookup"><span data-stu-id="a84de-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="a84de-107">Depois de testar a sua prova de conceito, utilize este guia para avançar com a integração HoloLens na sua organização.</span><span class="sxs-lookup"><span data-stu-id="a84de-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="a84de-108">Neste guia, vamos cobrir como inscrever os seus dispositivos na gestão de dispositivos existentes, aplicar licenças conforme necessário, e validar que os seus utilizadores finais são capazes de operar um Guia Dinâmico 365, bem como usar a linha personalizada de aplicações empresariais, após a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a84de-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a84de-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a84de-109">Prerequisites</span></span>

<span data-ttu-id="a84de-110">As infraestruturas que se seguem já devem estar em vigor:</span><span class="sxs-lookup"><span data-stu-id="a84de-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="a84de-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a84de-111">Wi-Fi</span></span>
    - <span data-ttu-id="a84de-112">Rede corporativa interna com acesso a recursos internos e acesso limitado aos serviços da Internet ou Cloud</span><span class="sxs-lookup"><span data-stu-id="a84de-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="a84de-113">Autenticação de certificados baseado em dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a84de-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="a84de-114">Azure Ative Directory (Azure AD) Junte-se à inscrição automática do MDM[(Azure AD P1](/azure/active-directory/fundamentals/active-directory-whatis) necessária)</span><span class="sxs-lookup"><span data-stu-id="a84de-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="a84de-115">MDM (Intune) Gerido</span><span class="sxs-lookup"><span data-stu-id="a84de-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="a84de-116">Uma ou mais aplicações são implementadas via MDM.</span><span class="sxs-lookup"><span data-stu-id="a84de-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="a84de-117">Rede</span><span class="sxs-lookup"><span data-stu-id="a84de-117">Network</span></span> 
    - <span data-ttu-id="a84de-118">Certificados (SCEP ou PKCS)</span><span class="sxs-lookup"><span data-stu-id="a84de-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="a84de-119">Configuração do proxy</span><span class="sxs-lookup"><span data-stu-id="a84de-119">Proxy configuration</span></span>
- <span data-ttu-id="a84de-120">Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="a84de-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="a84de-121">É suportado um único ou múltiplo por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a84de-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="a84de-122">Níveis variados de configurações de bloqueio do dispositivo aplicados com base em casos de utilização específicos, desde o Quiosque de Aplicações Totalmente Abertos a Single App.</span><span class="sxs-lookup"><span data-stu-id="a84de-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="a84de-123">Guias licenciamento e requisitos</span><span class="sxs-lookup"><span data-stu-id="a84de-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="a84de-124">Conta do Azure AD</span><span class="sxs-lookup"><span data-stu-id="a84de-124">Azure AD account</span></span>
- <span data-ttu-id="a84de-125">Dinâmica 365 Guias aplicações PC e HoloLens</span><span class="sxs-lookup"><span data-stu-id="a84de-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="a84de-126">Assinatura dinâmica 365 guias</span><span class="sxs-lookup"><span data-stu-id="a84de-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="a84de-127">Microsoft Dataverse (incluído)</span><span class="sxs-lookup"><span data-stu-id="a84de-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="a84de-128">Power Apps (incluído)</span><span class="sxs-lookup"><span data-stu-id="a84de-128">Power Apps (included)</span></span>
- <span data-ttu-id="a84de-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="a84de-129">Power BI Desktop</span></span>
- <span data-ttu-id="a84de-130">Conectividade da rede</span><span class="sxs-lookup"><span data-stu-id="a84de-130">Network Connectivity</span></span>

<span data-ttu-id="a84de-131">[![Diagrama de rede ligado à corp, fase 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a84de-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="a84de-132">[![Diagrama de rede ligado à corp, fase 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a84de-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="a84de-133">Neste guia:</span><span class="sxs-lookup"><span data-stu-id="a84de-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="a84de-134">Preparação</span><span class="sxs-lookup"><span data-stu-id="a84de-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="a84de-135">Conheça os elementos essenciais da infraestrutura para HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a84de-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="a84de-136">Saiba mais sobre o AZure AD e crie um se não o tiver.</span><span class="sxs-lookup"><span data-stu-id="a84de-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="a84de-137">Saiba mais sobre a gestão de identidade e como configurar melhor as contas AD da Azure.</span><span class="sxs-lookup"><span data-stu-id="a84de-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="a84de-138">Saiba mais sobre o MDM e prepare-se com o Intune se ainda não tiver um pronto.</span><span class="sxs-lookup"><span data-stu-id="a84de-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="a84de-139">Familiarize-se com Wi-Fi baseado em certificados.</span><span class="sxs-lookup"><span data-stu-id="a84de-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="a84de-140">Familiarize-se com Proxy.</span><span class="sxs-lookup"><span data-stu-id="a84de-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="a84de-141">Compreenda como pode usar a Linha de Aplicações Empresariais.</span><span class="sxs-lookup"><span data-stu-id="a84de-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="a84de-142">Saiba mais sobre como pode usar guias para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="a84de-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="a84de-143">Configurar</span><span class="sxs-lookup"><span data-stu-id="a84de-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="a84de-144">Como criar utilizadores e grupos.</span><span class="sxs-lookup"><span data-stu-id="a84de-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="a84de-145">Como configurar a Inscrição Automática.</span><span class="sxs-lookup"><span data-stu-id="a84de-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="a84de-146">Como configurar certificados e perfis Wi-Fi para a Conectividade Wi-Fi Corporativa.</span><span class="sxs-lookup"><span data-stu-id="a84de-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="a84de-147">Pacotes de aplicações upload e Assign Line of Business (LOB).</span><span class="sxs-lookup"><span data-stu-id="a84de-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="a84de-148">Configurar Dinâmicos 365 Guias.</span><span class="sxs-lookup"><span data-stu-id="a84de-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="a84de-149">Como configurar o modo quiosque (opcional).</span><span class="sxs-lookup"><span data-stu-id="a84de-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="a84de-150">Como configurar o WDAC (opcional).</span><span class="sxs-lookup"><span data-stu-id="a84de-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="a84de-151">Implementar</span><span class="sxs-lookup"><span data-stu-id="a84de-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="a84de-152">Validar a inscrição através do dispositivo e do MDM.</span><span class="sxs-lookup"><span data-stu-id="a84de-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="a84de-153">Validar Wi-Fi certificados.</span><span class="sxs-lookup"><span data-stu-id="a84de-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="a84de-154">Validar a instalação da aplicação LOB.</span><span class="sxs-lookup"><span data-stu-id="a84de-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="a84de-155">Validar Guias através da autoria e funcionamento.</span><span class="sxs-lookup"><span data-stu-id="a84de-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="a84de-156">Manter</span><span class="sxs-lookup"><span data-stu-id="a84de-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="a84de-157">Atualização HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a84de-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="a84de-158">Como atualizar Guias (aplicações de loja).</span><span class="sxs-lookup"><span data-stu-id="a84de-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="a84de-159">Como atualizar aplicações LOB.</span><span class="sxs-lookup"><span data-stu-id="a84de-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="a84de-160">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="a84de-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="a84de-161">A fazer um plano de apoio.</span><span class="sxs-lookup"><span data-stu-id="a84de-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="a84de-162">Opções de gestão de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a84de-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="a84de-163">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="a84de-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="a84de-164">Implementação conectada corporativa - Prepare-se</span><span class="sxs-lookup"><span data-stu-id="a84de-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
