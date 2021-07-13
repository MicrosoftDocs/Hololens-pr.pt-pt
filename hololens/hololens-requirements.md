---
title: Cenários comuns de implantação
description: Saiba mais sobre a implementação e gestão de HoloLens em ambientes empresariais, incluindo infraestruturas, Azure Ative Directory e gestão de dispositivos móveis.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639833"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="af7d4-103">Cenários comuns de implantação</span><span class="sxs-lookup"><span data-stu-id="af7d4-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="af7d4-104">Descrição Geral</span><span class="sxs-lookup"><span data-stu-id="af7d4-104">Overview</span></span>

<span data-ttu-id="af7d4-105">Esta página fornece uma visão geral de arquitetura de alto nível para três cenários comuns ao implementar e gerir Microsoft HoloLens 2 dispositivos dentro da empresa.</span><span class="sxs-lookup"><span data-stu-id="af7d4-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="af7d4-106">Muitas vezes, a forma como gere os seus dispositivos e acede aos recursos da sua organização é em grande parte determinada por fatores já em vigor.</span><span class="sxs-lookup"><span data-stu-id="af7d4-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="af7d4-107">Com base na sua infraestrutura existente, convidamo-lo a rever o estilo comum de gestão de dispositivos (MDM) nos seguintes cenários e depois ler [Planeamento HoloLens 2 implementações em ambiente comercial](hololens-core-components.md) para determinar que cenário corresponde às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="af7d4-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="af7d4-108">Existem também três guias correspondentes disponíveis para utilização durante a sua implantação.</span><span class="sxs-lookup"><span data-stu-id="af7d4-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="af7d4-109">Guia de implementação de ambiente conectado com nuvem</span><span class="sxs-lookup"><span data-stu-id="af7d4-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="af7d4-110">Guia de implementação de ambiente conectado em nuvem (clientes externos)</span><span class="sxs-lookup"><span data-stu-id="af7d4-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="af7d4-111">Guia de implementação de rede corporativa</span><span class="sxs-lookup"><span data-stu-id="af7d4-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="af7d4-112">Guia de implementação de ambiente seguro offline</span><span class="sxs-lookup"><span data-stu-id="af7d4-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="af7d4-113">Cenário A: Implementar para dispositivos ligados à nuvem</span><span class="sxs-lookup"><span data-stu-id="af7d4-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="af7d4-114">Este cenário é comparável à implementação de dispositivos móveis geridos dentro de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="af7d4-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="af7d4-115">HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="af7d4-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="af7d4-116">Os recursos corporativos não são acedidos ou podem ser limitados através da VPN.</span><span class="sxs-lookup"><span data-stu-id="af7d4-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="af7d4-117">Configurações comuns básicas</span><span class="sxs-lookup"><span data-stu-id="af7d4-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="af7d4-118">Wi-Fi redes estão normalmente totalmente abertas aos serviços da Internet e da Cloud.</span><span class="sxs-lookup"><span data-stu-id="af7d4-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="af7d4-119">Azure AD Junte-se à Gestão de Dispositivos Móveis (MDM) Inscrição automática--MDM (Intune) Gerido</span><span class="sxs-lookup"><span data-stu-id="af7d4-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="af7d4-120">Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="af7d4-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="af7d4-121">Utilizadores únicos ou múltiplos por dispositivo suportado</span><span class="sxs-lookup"><span data-stu-id="af7d4-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="af7d4-122">Níveis variados de configurações de bloqueio do dispositivo são aplicados com base em casos de utilização específicos, desde o Quiosque de Aplicações Totalmente Abertos a Single App.</span><span class="sxs-lookup"><span data-stu-id="af7d4-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="af7d4-123">Uma ou mais aplicações são implementadas via MDM</span><span class="sxs-lookup"><span data-stu-id="af7d4-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="af7d4-124">Desafios Comuns</span><span class="sxs-lookup"><span data-stu-id="af7d4-124">Common Challenges</span></span>
   * <span data-ttu-id="af7d4-125">Determinar quais as configurações do MDM a aplicar ao HoloLens 2 com base nos requisitos do cenário.</span><span class="sxs-lookup"><span data-stu-id="af7d4-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="af7d4-126">[![Cenário Um diagrama ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="af7d4-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="af7d4-127">O guia ligado à Cloud correspondente cobre como inscrever HoloLens 2 na gestão do dispositivo, aplicar licenças conforme necessário e validar que os seus utilizadores finais podem utilizar imediatamente o Remote Assist após a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af7d4-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="af7d4-128">Utilize o guia de Clientes Externos para implantar dispositivos num local remoto para utilização externa a curto ou longo prazo.</span><span class="sxs-lookup"><span data-stu-id="af7d4-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="af7d4-129">Guia de implementação de ambiente conectado com nuvem</span><span class="sxs-lookup"><span data-stu-id="af7d4-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="af7d4-130">Guia de implementação de ambiente conectado em nuvem (clientes externos)</span><span class="sxs-lookup"><span data-stu-id="af7d4-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="af7d4-131">Cenário B: Implementar dentro da rede da sua organização</span><span class="sxs-lookup"><span data-stu-id="af7d4-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="af7d4-132">Este cenário é idêntico a uma implantação clássica para a maioria dos PCs Windows 10.</span><span class="sxs-lookup"><span data-stu-id="af7d4-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="af7d4-133">HoloLens 2 é implementado para uso principalmente na rede corporativa com acesso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="af7d4-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="af7d4-134">Os serviços de internet e nuvem podem ser limitados.</span><span class="sxs-lookup"><span data-stu-id="af7d4-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="af7d4-135">Configurações comuns básicas</span><span class="sxs-lookup"><span data-stu-id="af7d4-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="af7d4-136">Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado aos serviços de internet ou Cloud.</span><span class="sxs-lookup"><span data-stu-id="af7d4-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="af7d4-137">Azure AD Junte-se à Inscrição Automática do MDM</span><span class="sxs-lookup"><span data-stu-id="af7d4-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="af7d4-138">MDM (Intune) Gerido</span><span class="sxs-lookup"><span data-stu-id="af7d4-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="af7d4-139">Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="af7d4-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="af7d4-140">Utilizadores únicos ou múltiplos por dispositivo suportado</span><span class="sxs-lookup"><span data-stu-id="af7d4-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="af7d4-141">Níveis variados de configurações de bloqueio do dispositivo são aplicados com base em casos de utilização específicos, desde o Quiosque de Aplicações Totalmente Abertos a Single App.</span><span class="sxs-lookup"><span data-stu-id="af7d4-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="af7d4-142">Uma ou mais aplicações são implementadas via MDM</span><span class="sxs-lookup"><span data-stu-id="af7d4-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="af7d4-143">Desafios Comuns</span><span class="sxs-lookup"><span data-stu-id="af7d4-143">Common Challenges</span></span>
   * <span data-ttu-id="af7d4-144">HoloLens 2 não suporta em instalações a AD ou SCCM.</span><span class="sxs-lookup"><span data-stu-id="af7d4-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="af7d4-145">Apenas a Azure AD se junta ao MDM.</span><span class="sxs-lookup"><span data-stu-id="af7d4-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="af7d4-146">Muitas empresas ainda hoje implantam PCs Windows 10 neste cenário como nas instalações AD aderiram a dispositivos, geridos pela System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerir dispositivos de Windows 10 internos através de soluções MDM baseadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="af7d4-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="af7d4-147">Como HoloLens 2 é um primeiro dispositivo em nuvem, depende fortemente de serviços ligados à internet e cloud para autenticação do utilizador, atualizações de SISTEMA, gestão de MDM, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="af7d4-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="af7d4-148">Ao ligar-se a uma rede corporativa, as regras Proxy/Firewall provavelmente terão de ser ajustadas para permitir o acesso a HoloLens 2 e as aplicações que nela funcionam.</span><span class="sxs-lookup"><span data-stu-id="af7d4-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="af7d4-149">A conectividade Wi-Fi corporativa normalmente requer certificados para autenticar o dispositivo ou o utilizador para a rede.</span><span class="sxs-lookup"><span data-stu-id="af7d4-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="af7d4-150">A infraestrutura ou configurações necessárias para a implementação de certificados para Windows 10 dispositivos através do MDM podem ser desafiantes à configuração.</span><span class="sxs-lookup"><span data-stu-id="af7d4-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="af7d4-151">[Diagrama do cenário ![ ](images/deployment-guides-revised-scenario-b-01-1.png) B1 ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="af7d4-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="af7d4-152">[Diagrama do cenário ![ ](images/deployment-guides-revised-scenario-b-02-1.png) B2 ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="af7d4-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="af7d4-153">O guia de rede Corporativo correspondente instrui como inscrever HoloLens 2 na gestão do dispositivo existente, aplicar licenças conforme necessário, e validar que os seus utilizadores finais são capazes de operar um Guia Dinâmico 365, bem como usar a linha personalizada de aplicações empresariais, após a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af7d4-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="af7d4-154">Guia de implementação de rede corporativa</span><span class="sxs-lookup"><span data-stu-id="af7d4-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="af7d4-155">Cenário C: Implementar em ambiente offline seguro</span><span class="sxs-lookup"><span data-stu-id="af7d4-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="af7d4-156">Esta é uma implementação típica para locais altamente seguros ou confidenciais.</span><span class="sxs-lookup"><span data-stu-id="af7d4-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="af7d4-157">HoloLens 2 é implementado para uso principalmente offline sem rede ou acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="af7d4-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="af7d4-158">Configurações comuns básicas</span><span class="sxs-lookup"><span data-stu-id="af7d4-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="af7d4-159">Wi-Fi conectividade é desativada.</span><span class="sxs-lookup"><span data-stu-id="af7d4-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="af7d4-160">Se necessário, o Ethernet via USB pode ser ativado para a conectividade LAN.</span><span class="sxs-lookup"><span data-stu-id="af7d4-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="af7d4-161">Não consegui.</span><span class="sxs-lookup"><span data-stu-id="af7d4-161">Not Managed.</span></span>
   * <span data-ttu-id="af7d4-162">Conta de utilizador local para o sômin do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af7d4-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="af7d4-163">HoloLens 2 suporta apenas uma conta local.</span><span class="sxs-lookup"><span data-stu-id="af7d4-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="af7d4-164">Níveis variados de configurações de bloqueio do dispositivo são aplicados através de Pacotes de Provisionamento com base em casos de utilização específicos.</span><span class="sxs-lookup"><span data-stu-id="af7d4-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="af7d4-165">Estas configurações são normalmente restritas devido a requisitos ambientais seguros.</span><span class="sxs-lookup"><span data-stu-id="af7d4-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="af7d4-166">Uma ou mais aplicações são implementadas através do Pacote de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="af7d4-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="af7d4-167">Desafios Comuns</span><span class="sxs-lookup"><span data-stu-id="af7d4-167">Common Challenges</span></span>
   * <span data-ttu-id="af7d4-168">Há um conjunto limitado de configurações disponíveis através de Pacotes de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="af7d4-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="af7d4-169">Os serviços em nuvem não são capazes de ser utilizados, limitando assim as capacidades HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="af7d4-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="af7d4-170">Sobrecarga administrativa mais elevada, uma vez que estes dispositivos têm de ser configurados, configurados e atualizados manualmente.</span><span class="sxs-lookup"><span data-stu-id="af7d4-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="af7d4-171">[![Diagrama de segurança offline 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="af7d4-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="af7d4-172">O guia de segurança offline correspondente fornece instruções para a aplicação de uma embalagem de provisão de amostra que bloqueie um HoloLens 2 para utilização em ambientes seguros.</span><span class="sxs-lookup"><span data-stu-id="af7d4-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="af7d4-173">Guia de implementação de ambiente seguro offline</span><span class="sxs-lookup"><span data-stu-id="af7d4-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


