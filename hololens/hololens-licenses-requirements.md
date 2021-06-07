---
title: Requisitos de licença
description: Mantenha-se atualizado com todos os requisitos e diretrizes de licenciamento necessários para a gestão de dispositivos móveis, HoloLens e Remote Assist.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379913"
---
# <a name="license-requirements"></a><span data-ttu-id="c9308-103">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="c9308-103">License requirements</span></span>

## <a name="mobile-device-management-mdm-licenses-guidance"></a><span data-ttu-id="c9308-104">Orientação para as licenças de gestão de dispositivos móveis (MDM)</span><span class="sxs-lookup"><span data-stu-id="c9308-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="c9308-105">Se planeia gerir os seus dispositivos HoloLens, precisará do Azure AD e de um MDM.</span><span class="sxs-lookup"><span data-stu-id="c9308-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="c9308-106">O Ative Diretor (AD) não pode ser utilizado para gerir dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9308-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="c9308-107">Se planeia utilizar um MDM diferente do Intune, é necessário um [Diretório Ativo Azure.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="c9308-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="c9308-108">Se planeia usar o Intune como seu MDM, leia a [lista de suites](https://docs.microsoft.com/intune/fundamentals/licenses) que incluem licenças Intune.</span><span class="sxs-lookup"><span data-stu-id="c9308-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> <span data-ttu-id="c9308-109">**Por favor, note que a Azure AD está incluída na maioria destas suites.**</span><span class="sxs-lookup"><span data-stu-id="c9308-109">**Please note that Azure AD is included in the majority of these suites.**</span></span>

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a><span data-ttu-id="c9308-110">Identifique as licenças necessárias para o seu cenário e produtos</span><span class="sxs-lookup"><span data-stu-id="c9308-110">Identify the licenses needed for your scenario and products</span></span>

### <a name="hololens-1st-gen-licenses-requirements"></a><span data-ttu-id="c9308-111">Requisitos de licenças hololens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="c9308-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="c9308-112">Poderá ser necessário atualizar o seu dispositivo HoloLens (1º género) para o Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="c9308-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="c9308-113">(Consulte [as funcionalidades comerciais da HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) para determinar se precisa de fazer upgrade).</span><span class="sxs-lookup"><span data-stu-id="c9308-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="c9308-114">Em caso afirmativo, terá de fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c9308-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="c9308-115">Adquirir um ficheiro XML de licença da HoloLens Enterprise</span><span class="sxs-lookup"><span data-stu-id="c9308-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="c9308-116">Aplique o ficheiro XML nos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9308-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="c9308-117">Pode fazê-lo através de um [pacote de Provisioning](hololens-provisioning.md) ou através do seu [Gestor de Dispositivos Móveis](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="c9308-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <a name="remote-assist-license-requirements"></a><span data-ttu-id="c9308-118">Requisitos de licença de assistência remota</span><span class="sxs-lookup"><span data-stu-id="c9308-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="c9308-119">Certifique-se de que tem o licenciamento e o dispositivo necessários, que pode consultar a documentação dos [requisitos.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)</span><span class="sxs-lookup"><span data-stu-id="c9308-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="c9308-120">Licença de Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="c9308-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="c9308-121">Ou tente um [julgamento de Assistência Remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="c9308-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="c9308-122">Equipas Freemium/Equipas</span><span class="sxs-lookup"><span data-stu-id="c9308-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="c9308-123">Licença Azure Ative Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c9308-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="c9308-124">Se planeia implementar **[este cenário de inquilinos cruzados,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** poderá necessitar de uma licença de Barreiras de Informação.</span><span class="sxs-lookup"><span data-stu-id="c9308-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="c9308-125">Consulte [este artigo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se é necessária uma Licença de Barreira de Informação.</span><span class="sxs-lookup"><span data-stu-id="c9308-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="guides-license-requirements"></a><span data-ttu-id="c9308-126">Requisitos de licença de guias</span><span class="sxs-lookup"><span data-stu-id="c9308-126">Guides License Requirements</span></span>

<span data-ttu-id="c9308-127">Confira os [requisitos de licenciamento e dispositivo atualizados.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)</span><span class="sxs-lookup"><span data-stu-id="c9308-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="c9308-128">Licença Azure Ative Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c9308-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="c9308-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="c9308-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="c9308-130">Guides</span><span class="sxs-lookup"><span data-stu-id="c9308-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
