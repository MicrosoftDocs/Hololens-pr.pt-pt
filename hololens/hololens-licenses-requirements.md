---
title: Requisitos de licença
description: Mantenha-se atualizado com todos os requisitos e diretrizes de licenciamento necessários para a gestão de dispositivos móveis, HoloLens e Assistência Remota.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635896"
---
# <a name="license-requirements"></a><span data-ttu-id="39365-103">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="39365-103">License requirements</span></span>

## <a name="hololens-2-device-managed"></a><span data-ttu-id="39365-104">HoloLens 2 Dispositivo (gerido)</span><span class="sxs-lookup"><span data-stu-id="39365-104">HoloLens 2 Device (managed)</span></span>

[<span data-ttu-id="39365-105">Conta Azure AD</span><span class="sxs-lookup"><span data-stu-id="39365-105">Azure AD Account</span></span>](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> <span data-ttu-id="39365-106">O Ative Directory (AD) não pode ser utilizado para gerir HoloLens dispositivos.</span><span class="sxs-lookup"><span data-stu-id="39365-106">Active Directory (AD) cannot be used to manage HoloLens devices.</span></span>

<span data-ttu-id="39365-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) ou outro MDM.</span><span class="sxs-lookup"><span data-stu-id="39365-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) or another MDM.</span></span>
- <span data-ttu-id="39365-108">[Windows Autopilot para HoloLens 2](hololens2-autopilot.md)- simplifica a experiência de fornecimento tanto para administradores de TI como para utilizadores finais.</span><span class="sxs-lookup"><span data-stu-id="39365-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)- simplifies the provisioning experience for both IT admins and end users.</span></span> <span data-ttu-id="39365-109">Os administradores de TI podem pré-configurar HoloLens 2 políticas, e após o primeiro arranque, os dispositivos serão implantados em estado de preparação para o negócio com zero interação do utilizador final.</span><span class="sxs-lookup"><span data-stu-id="39365-109">IT admins can preconfigure HoloLens 2 policies, and upon first boot, devices will be deployed in business-ready state with zero end-user interaction.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="39365-110">Windows O piloto automático requer que [o Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) e a [inscrição automática](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) sejam configurados primeiro para o fluxo de piloto automático de baixo toque e para a implementação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="39365-110">Windows Autopilot requires [Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) and [Auto-enrollment](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) to be configured first for the low-touch Autopilot flow and device deployment.</span></span> 

### <a name="business-use-case"></a><span data-ttu-id="39365-111">Caso de utilização de negócios:</span><span class="sxs-lookup"><span data-stu-id="39365-111">Business Use Case:</span></span> 

- <span data-ttu-id="39365-112">[Cenário de implantação A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - prova de conceito ou implantação de pilotos.</span><span class="sxs-lookup"><span data-stu-id="39365-112">[Deployment Scenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - proof-of-concept or pilot deployment.</span></span>

- <span data-ttu-id="39365-113">[Cenário de implantação B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - implantação à escala.</span><span class="sxs-lookup"><span data-stu-id="39365-113">[Deployment Scenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - deployment at scale.</span></span>

## <a name="hololens-2-device-only-non-managed"></a><span data-ttu-id="39365-114">HoloLens 2 Apenas dispositivo (não gerido)</span><span class="sxs-lookup"><span data-stu-id="39365-114">HoloLens 2 Device-only (non-managed)</span></span>

<span data-ttu-id="39365-115">Ao utilizar uma conta Microsoft (MSA) ou uma conta local não são necessárias licenças adicionais para estas contas.</span><span class="sxs-lookup"><span data-stu-id="39365-115">When using either a Microsoft Account (MSA) or Local account no additional licenses are required for these accounts.</span></span>

[<span data-ttu-id="39365-116">Conta Local</span><span class="sxs-lookup"><span data-stu-id="39365-116">Local Account</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- <span data-ttu-id="39365-117">Esta conta deve ser [disponibilizada](hololens-provisioning.md#provisioning-package-hololens-wizard) com antecedência com Windows Designer de Configuração (WCD).</span><span class="sxs-lookup"><span data-stu-id="39365-117">This account must be [provisioned](hololens-provisioning.md#provisioning-package-hololens-wizard) ahead of time with Windows Configuration Designer (WCD).</span></span>

[<span data-ttu-id="39365-118">Conta Microsoft (MSA)</span><span class="sxs-lookup"><span data-stu-id="39365-118">Microsoft Account (MSA)</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> <span data-ttu-id="39365-119">Vários utilizadores não são suportados por um dispositivo que utilize qualquer uma destas contas.</span><span class="sxs-lookup"><span data-stu-id="39365-119">Multiple users are not supported for a device using either of these accounts.</span></span>

### <a name="business-use-case"></a><span data-ttu-id="39365-120">Caso de utilização de negócios:</span><span class="sxs-lookup"><span data-stu-id="39365-120">Business Use Case:</span></span> 

- <span data-ttu-id="39365-121">[Cenário de implantação C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - implantação offline ou segura.</span><span class="sxs-lookup"><span data-stu-id="39365-121">[Deployment Scenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - offline or secure deployment.</span></span>
 
## <a name="dynamics-365-licensing-and-requirements"></a><span data-ttu-id="39365-122">Dinâmica 365 Licenciamento e Requisitos</span><span class="sxs-lookup"><span data-stu-id="39365-122">Dynamics 365 Licensing and Requirements</span></span>

### <a name="dynamics-365-remote-assist"></a><span data-ttu-id="39365-123">Dinâmico 365 Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="39365-123">Dynamics 365 Remote Assist</span></span> 

#### <a name="admin"></a><span data-ttu-id="39365-124">Admin</span><span class="sxs-lookup"><span data-stu-id="39365-124">Admin</span></span>

- <span data-ttu-id="39365-125">Conta AZURE AD (necessária para a aquisição da subscrição e atribuição de licenças)</span><span class="sxs-lookup"><span data-stu-id="39365-125">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="39365-126">[Subscrição de Assistência Remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [Ensaio de Assistência Remota)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="39365-126">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="39365-127">Dynamics 365 Remote Assist utilizador</span><span class="sxs-lookup"><span data-stu-id="39365-127">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="39365-128">Conta do Azure AD</span><span class="sxs-lookup"><span data-stu-id="39365-128">Azure AD account</span></span>

- <span data-ttu-id="39365-129">Licença de Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="39365-129">Remote Assist license</span></span> 

  > [!NOTE]
  > <span data-ttu-id="39365-130">Microsoft Teams está agregado com assistência remota</span><span class="sxs-lookup"><span data-stu-id="39365-130">Microsoft Teams is bundled with Remote Assist</span></span>

- <span data-ttu-id="39365-131">Conectividade da rede</span><span class="sxs-lookup"><span data-stu-id="39365-131">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="39365-132">Microsoft Teams utilizador</span><span class="sxs-lookup"><span data-stu-id="39365-132">Microsoft Teams user</span></span>

- <span data-ttu-id="39365-133">Conta do Azure AD</span><span class="sxs-lookup"><span data-stu-id="39365-133">Azure AD account</span></span>

- <span data-ttu-id="39365-134">Microsoft Teams ou [Teams Freemium.](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="39365-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>

- <span data-ttu-id="39365-135">Conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="39365-135">Network connectivity</span></span>

<span data-ttu-id="39365-136">Se planeia implementar este [cenário de inquilinos cruzados,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)poderá necessitar de uma licença de Barreiras de Informação.</span><span class="sxs-lookup"><span data-stu-id="39365-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="39365-137">Consulte [este artigo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se é necessária uma Licença de Barreira de Informação.</span><span class="sxs-lookup"><span data-stu-id="39365-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="dynamics-365-guides"></a><span data-ttu-id="39365-138">Dinâmica 365 Guias</span><span class="sxs-lookup"><span data-stu-id="39365-138">Dynamics 365 Guides</span></span> 

#### <a name="admin"></a><span data-ttu-id="39365-139">Admin</span><span class="sxs-lookup"><span data-stu-id="39365-139">Admin</span></span>

- <span data-ttu-id="39365-140">Conta AZURE AD (necessária para a aquisição da subscrição e atribuição de licenças)</span><span class="sxs-lookup"><span data-stu-id="39365-140">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="39365-141">Subscrição de [Guias Dinâmicos](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) 365 ou teste gratuito</span><span class="sxs-lookup"><span data-stu-id="39365-141">Dynamics 365 [Guides subscription or free trial](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span></span>

#### <a name="guides-author"></a><span data-ttu-id="39365-142">Autor de Guias</span><span class="sxs-lookup"><span data-stu-id="39365-142">Guides Author</span></span>

1. <span data-ttu-id="39365-143">Conta do Azure AD</span><span class="sxs-lookup"><span data-stu-id="39365-143">Azure AD account</span></span>
1. [<span data-ttu-id="39365-144">Licença de Guias Dinâmicos 365</span><span class="sxs-lookup"><span data-stu-id="39365-144">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="39365-145">Aplicação Dinâmica 365 Guias instalada num PC ou HoloLens</span><span class="sxs-lookup"><span data-stu-id="39365-145">Dynamics 365 Guides application installed on a PC or HoloLens</span></span>
1. <span data-ttu-id="39365-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (usado para ver o painel de instrumentos Analytics)</span><span class="sxs-lookup"><span data-stu-id="39365-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (used to view the Analytics dashboard)</span></span>
1. <span data-ttu-id="39365-147">Papel de autor (para criar guias)</span><span class="sxs-lookup"><span data-stu-id="39365-147">Author role (for creating guides)</span></span>
1. <span data-ttu-id="39365-148">Conectividade da rede</span><span class="sxs-lookup"><span data-stu-id="39365-148">Network Connectivity</span></span>

#### <a name="guides-user"></a><span data-ttu-id="39365-149">Guias Utilizador</span><span class="sxs-lookup"><span data-stu-id="39365-149">Guides User</span></span>

1. <span data-ttu-id="39365-150">Conta do Azure AD</span><span class="sxs-lookup"><span data-stu-id="39365-150">Azure AD account</span></span>
1. [<span data-ttu-id="39365-151">Licença de Guias Dinâmicos 365</span><span class="sxs-lookup"><span data-stu-id="39365-151">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="39365-152">Aplicação Dynamics 365 Guides instalada num HoloLens</span><span class="sxs-lookup"><span data-stu-id="39365-152">Dynamics 365 Guides app installed on a HoloLens</span></span>
1. <span data-ttu-id="39365-153">Função do operador (para testar ou utilizar guias)</span><span class="sxs-lookup"><span data-stu-id="39365-153">Operator role (for testing or using guides)</span></span>
1. <span data-ttu-id="39365-154">Conectividade da rede</span><span class="sxs-lookup"><span data-stu-id="39365-154">Network Connectivity</span></span>
