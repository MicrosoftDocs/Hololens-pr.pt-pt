---
title: Planeamento HoloLens 2 implantação em ambiente comercial
description: Conheça as principais necessidades de implantação e gestão de HoloLens em ambientes empresariais, incluindo infraestruturas, diretório ativo azul e gestão de dispositivos móveis.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 2fb58345f623a0b70c1fda10b9fb550de70f4c6d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635794"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="b6271-103">Planeamento HoloLens 2 implantação em ambiente comercial</span><span class="sxs-lookup"><span data-stu-id="b6271-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="b6271-104">Descrição Geral</span><span class="sxs-lookup"><span data-stu-id="b6271-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="b6271-105">Esta visão geral destina-se a ajudar os profissionais de TI a compreender considerações para implementar e gerir Microsoft HoloLens 2 dispositivos dentro de uma organização.</span><span class="sxs-lookup"><span data-stu-id="b6271-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="b6271-106">Para os utilizadores finais do dispositivo, consulte [obter o seu HoloLens 2 pronto a usar para](hololens2-setup.md) começar.</span><span class="sxs-lookup"><span data-stu-id="b6271-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="b6271-107">HoloLens 2 funciona em Windows 10 Holographic que fornece às organizações tecnologias robustas, flexíveis, incorporadas para dispositivos móveis e gestão de aplicações.</span><span class="sxs-lookup"><span data-stu-id="b6271-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="b6271-108">Windows 10 Holographic suporta a gestão do ciclo de vida do dispositivo de ponta a ponta para dar às empresas o controlo sobre os seus dispositivos, dados e apps.</span><span class="sxs-lookup"><span data-stu-id="b6271-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="b6271-109">O HoloLens 2 pode ser facilmente incorporado em práticas padrão de ciclo de vida, desde a inscrição, configuração e gestão de aplicações do dispositivo até à manutenção e reforma utilizando uma solução abrangente de gestão de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="b6271-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="b6271-110">Os seguintes passos e vídeo podem ajudá-lo a guiá-lo através do processo de adoção de HoloLens 2 dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b6271-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![Passo 1](images/1green.png)| <br/> <span data-ttu-id="b6271-112">**[Cenários de implantação comuns](hololens-requirements.md)**: Compreenda os cenários de implantação e explore os componentes centrais necessários para implantar HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b6271-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Passo 2](images/2green.png)| <br/> <span data-ttu-id="b6271-114">**[Preparar](#prepare)**: Familiarize-se com os elementos essenciais da infraestrutura necessários para HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b6271-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Passo 3](images/3green.png) | <br/> <span data-ttu-id="b6271-116">**[Configurar](#configure)**: Aprenda a configurar os seus componentes essenciais para uma implantação baseada na nuvem.</span><span class="sxs-lookup"><span data-stu-id="b6271-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Passo 4](images/4green.png) | <br/> <span data-ttu-id="b6271-118">**[Implementar](#deploy)**: Descubra como implantar os seus dispositivos e distribuir as suas aplicações de forma segura e eficiente.</span><span class="sxs-lookup"><span data-stu-id="b6271-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Passo 5](images/5green.png) | <br/> <span data-ttu-id="b6271-120">**[Manter](#maintain)**: Descubra o que é necessário para manter corretamente o estado dos seus HoloLens 2 dispositivos e garantir o cumprimento da política corporativa.</span><span class="sxs-lookup"><span data-stu-id="b6271-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="b6271-121">Preparação</span><span class="sxs-lookup"><span data-stu-id="b6271-121">Prepare</span></span>

<span data-ttu-id="b6271-122">Conheça os serviços essenciais de infraestrutura necessários para suportar todo o conjunto de capacidades HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b6271-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="b6271-123">Componente</span><span class="sxs-lookup"><span data-stu-id="b6271-123">Component</span></span> | <span data-ttu-id="b6271-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6271-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="b6271-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="b6271-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="b6271-126">Fornece gestão de identidade e acesso para o HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="b6271-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="b6271-127">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="b6271-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="b6271-128">Gere HoloLens 2 dispositivos ligados ao seu inquilino</span><span class="sxs-lookup"><span data-stu-id="b6271-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="b6271-129">Rede Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="b6271-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="b6271-130">Wi-Fi está disponível e os dispositivos podem ser ligados à Internet</span><span class="sxs-lookup"><span data-stu-id="b6271-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="b6271-131">Configurar</span><span class="sxs-lookup"><span data-stu-id="b6271-131">Configure</span></span>

<span data-ttu-id="b6271-132">Utilize o Intune e o Autopilot como soluções de baixo toque para inscrever e configurar HoloLens 2 para o inquilino AZure AD da sua organização e MDM.</span><span class="sxs-lookup"><span data-stu-id="b6271-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="b6271-133">Componente</span><span class="sxs-lookup"><span data-stu-id="b6271-133">Component</span></span> | <span data-ttu-id="b6271-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6271-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="b6271-135">Inscrição automática</span><span class="sxs-lookup"><span data-stu-id="b6271-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="b6271-136">Após o início de sessão, os dispositivos registam-se automaticamente com a Azure AD e inscrevem-se no MDM</span><span class="sxs-lookup"><span data-stu-id="b6271-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="b6271-137">Licenças de Inscrição</span><span class="sxs-lookup"><span data-stu-id="b6271-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="b6271-138">Pode ser aplicado a utilizadores, grupos de utilizadores ou grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b6271-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="b6271-139">Utilizadores e Grupos Azure</span><span class="sxs-lookup"><span data-stu-id="b6271-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="b6271-140">Ajuda a atribuir configurações e licenças para o HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="b6271-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="b6271-141">Implementar</span><span class="sxs-lookup"><span data-stu-id="b6271-141">Deploy</span></span>

<span data-ttu-id="b6271-142">Distribua os seus HoloLens 2 dispositivos e valide a sua configuração.</span><span class="sxs-lookup"><span data-stu-id="b6271-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="b6271-143">Componente</span><span class="sxs-lookup"><span data-stu-id="b6271-143">Component</span></span> | <span data-ttu-id="b6271-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6271-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="b6271-145">Validação de Inscrição</span><span class="sxs-lookup"><span data-stu-id="b6271-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="b6271-146">Validar o dispositivo tem AZure AD Unidos a partir de Definições ou do Portal Azure</span><span class="sxs-lookup"><span data-stu-id="b6271-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="b6271-147">Validação de Certificados</span><span class="sxs-lookup"><span data-stu-id="b6271-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="b6271-148">Verifique as definições e valide-as foram distribuídas corretamente</span><span class="sxs-lookup"><span data-stu-id="b6271-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="b6271-149">Validar instalações de aplicações</span><span class="sxs-lookup"><span data-stu-id="b6271-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="b6271-150">Confirme que a aplicação está presente e que está a trabalhar no seu HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="b6271-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="b6271-151">Manter</span><span class="sxs-lookup"><span data-stu-id="b6271-151">Maintain</span></span>

<span data-ttu-id="b6271-152">Utilize Windows Update for Business juntamente com o seu sistema MDM ou o Microsoft Store para manter a sua frota de HoloLens 2 e aplicações atualizadas.</span><span class="sxs-lookup"><span data-stu-id="b6271-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="b6271-153">Componente</span><span class="sxs-lookup"><span data-stu-id="b6271-153">Component</span></span> | <span data-ttu-id="b6271-154">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6271-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="b6271-155">Atualização HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="b6271-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="b6271-156">Configurar atualizações conforme necessário através de Windows Atualizações para Negócios</span><span class="sxs-lookup"><span data-stu-id="b6271-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="b6271-157">Atualizar aplicações</span><span class="sxs-lookup"><span data-stu-id="b6271-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="b6271-158">Configure através do seu sistema MDM ou do Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b6271-158">Configure through your MDM system or the Microsoft Store</span></span>
