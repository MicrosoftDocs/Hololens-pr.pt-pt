---
title: Orientações sobre infraestruturas para HoloLens
description: Conheça as diretrizes de infraestrutura para dispositivos HoloLens, incluindo suporte à rede sem fios, assistência remota e gestão de dispositivos móveis.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639289"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="16f89-103">Configure a sua rede para HoloLens</span><span class="sxs-lookup"><span data-stu-id="16f89-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="16f89-104">Esta parte do documento requer as seguintes pessoas:</span><span class="sxs-lookup"><span data-stu-id="16f89-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="16f89-105">Administração de rede com permissões para estois para fazer alterações no proxy/firewall</span><span class="sxs-lookup"><span data-stu-id="16f89-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="16f89-106">Azure Active Directory Administrador</span><span class="sxs-lookup"><span data-stu-id="16f89-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="16f89-107">Administrador de Dispositivos Móveis</span><span class="sxs-lookup"><span data-stu-id="16f89-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="16f89-108">Requisitos de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="16f89-108">Infrastructure Requirements</span></span>

<span data-ttu-id="16f89-109">HoloLens é, no fundo, um Windows dispositivo móvel integrado ao Azure.</span><span class="sxs-lookup"><span data-stu-id="16f89-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="16f89-110">Funciona melhor em ambientes comerciais com disponibilidade de rede sem fios (wi-fi) e acesso a serviços Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16f89-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="16f89-111">Os serviços de nuvem crítica incluem:</span><span class="sxs-lookup"><span data-stu-id="16f89-111">Critical cloud services include:</span></span>

- <span data-ttu-id="16f89-112">Diretório ativo Azure (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="16f89-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="16f89-113">Windows Atualização (WU)</span><span class="sxs-lookup"><span data-stu-id="16f89-113">Windows Update (WU)</span></span>

<span data-ttu-id="16f89-114">Os clientes comerciais precisarão de uma infraestrutura de gestão da mobilidade empresarial (EMM) ou de gestão de dispositivos móveis (MDM) para gerir HoloLens dispositivos em escala.</span><span class="sxs-lookup"><span data-stu-id="16f89-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="16f89-115">Este guia utiliza [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) como exemplo, embora qualquer fornecedor com suporte total para a Microsoft Policy possa suportar HoloLens.</span><span class="sxs-lookup"><span data-stu-id="16f89-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="16f89-116">Pergunte ao seu fornecedor de gestão de dispositivos móveis se eles suportam HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="16f89-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="16f89-117">HoloLens suporta um conjunto limitado de experiências desligadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="16f89-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="16f89-118">Suporte eAP de rede sem fios</span><span class="sxs-lookup"><span data-stu-id="16f89-118">Wireless network EAP support</span></span>

- <span data-ttu-id="16f89-119">PEAP-MS-CHAPV2</span><span class="sxs-lookup"><span data-stu-id="16f89-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="16f89-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="16f89-120">PEAP-TLS</span></span>
- <span data-ttu-id="16f89-121">TLS</span><span class="sxs-lookup"><span data-stu-id="16f89-121">TLS</span></span>
- <span data-ttu-id="16f89-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="16f89-122">TTLS-CHAP</span></span>
- <span data-ttu-id="16f89-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="16f89-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="16f89-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="16f89-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="16f89-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="16f89-125">TTLS-PAP</span></span>
- <span data-ttu-id="16f89-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="16f89-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="16f89-127">HoloLens Requisitos específicos da rede</span><span class="sxs-lookup"><span data-stu-id="16f89-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="16f89-128">Certifique-se de que [esta lista](hololens-offline.md) de pontos finais é permitida na sua firewall de rede.</span><span class="sxs-lookup"><span data-stu-id="16f89-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="16f89-129">Isto permitirá que HoloLens funcionem corretamente.</span><span class="sxs-lookup"><span data-stu-id="16f89-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="16f89-130">Requisitos de rede específico de assistência remota</span><span class="sxs-lookup"><span data-stu-id="16f89-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="16f89-131">A largura de banda recomendada para um melhor desempenho do Remote Assist é de 1,5Mbps.</span><span class="sxs-lookup"><span data-stu-id="16f89-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="16f89-132">Consulte os [requisitos de rede detalhados](/MicrosoftTeams/prepare-network) para obter informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="16f89-132">See the [detailed network requirements](/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="16f89-133">**(Por favor, note que se não tiver velocidades de rede de pelo menos 1,5Mbps, o Remote Assist continuará a funcionar. No entanto, a qualidade pode sofrer).**</span><span class="sxs-lookup"><span data-stu-id="16f89-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="16f89-134">Certifique-se de que estas portas e URLs são permitidos na sua firewall de rede para permitir que Microsoft Teams funcionem.</span><span class="sxs-lookup"><span data-stu-id="16f89-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="16f89-135">Mantenha-se atualizado com a [última lista de portos.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="16f89-135">Stay up to date with the [latest list of ports](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="16f89-136">Saiba mais sobre os [requisitos específicos da rede para assistência remota.](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)</span><span class="sxs-lookup"><span data-stu-id="16f89-136">Learn more about the specific [Network Requirements for Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="16f89-137">Saiba mais sobre como preparar a [rede da sua organização para Microsoft Teams](/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="16f89-137">Learn more about how to [prepare your organization's network for Microsoft Teams](/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="16f89-138">Guia requisitos específicos de rede</span><span class="sxs-lookup"><span data-stu-id="16f89-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="16f89-139">Os guias apenas requerem acesso à rede para descarregar e usar a aplicação.</span><span class="sxs-lookup"><span data-stu-id="16f89-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="16f89-140">Azure Active Directory Orientação</span><span class="sxs-lookup"><span data-stu-id="16f89-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="16f89-141">Este passo só é necessário se a sua empresa planeia gerir o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="16f89-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="16f89-142">Certifique-se de que tem uma Licença AD Azure.</span><span class="sxs-lookup"><span data-stu-id="16f89-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="16f89-143">Por [favor, HoloLens requisitos de licenças](hololens-licenses-requirements.md) para obter informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="16f89-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="16f89-144">Se planeia utilizar a Inscrição Automática, terá de configurar a [inscrição Azure AD.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="16f89-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="16f89-145">Certifique-se de que os utilizadores da sua empresa estão em Azure Ative Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="16f89-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="16f89-146">Consulte as [seguintes instruções](/azure/active-directory/fundamentals/add-users-azure-active-directory) para adicionar os utilizadores.</span><span class="sxs-lookup"><span data-stu-id="16f89-146">See the following [instructions](/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="16f89-147">Sugerimos que os utilizadores que precisam de licenças semelhantes sejam adicionados ao mesmo grupo.</span><span class="sxs-lookup"><span data-stu-id="16f89-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="16f89-148">Criar um Grupo</span><span class="sxs-lookup"><span data-stu-id="16f89-148">Create a Group</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="16f89-149">Adicionar utilizadores a grupos</span><span class="sxs-lookup"><span data-stu-id="16f89-149">Add users to groups</span></span>](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="16f89-150">Certifique-se de que os utilizadores da sua empresa (ou grupo de utilizadores) recebem as licenças necessárias.</span><span class="sxs-lookup"><span data-stu-id="16f89-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="16f89-151">Se precisar de atribuir licenças, siga estas [instruções.](/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="16f89-151">If you need to assign licenses, follow these [directions](/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="16f89-152">Só faça este passo se se espera que os utilizadores inscrevam o seu dispositivo HoloLens/Mobile em si (Existem três opções) Estes passos garantem que os utilizadores da sua empresa (ou um grupo de utilizadores) podem adicionar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="16f89-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="16f89-153">**Opção 1:** Dê permissão a todos os utilizadores para se juntarem a dispositivos ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="16f89-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="16f89-154">**Inscreva-se no portal Azure como administrador**  >  **Azure Ative Directory**  >  **Dispositivos**  >  **Definições do dispositivo**  >
 **Definir Utilizadores podem juntar dispositivos para Azure AD a *Todos***</span><span class="sxs-lookup"><span data-stu-id="16f89-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="16f89-155">**Opção 2:** Dar aos utilizadores/grupos selecionados permissão para juntar dispositivos para Azure AD **Iniciar sação no portal Azure como administrador**  >  **Azure Ative Directory** dispositivo dispositivo de  >  **dispositivos**  >  **Definições**  >
 **Utilizadores definidos podem juntar dispositivos para Azure AD a imagem *selecionada*** 
 ![ que mostra Configuração de Dispositivos AD AD Azure](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="16f89-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="16f89-156">**Opção 3:** Pode impedir que todos os utilizadores juntem os seus dispositivos ao domínio.</span><span class="sxs-lookup"><span data-stu-id="16f89-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="16f89-157">Isto significa que todos os dispositivos terão de ser matriculados manualmente.</span><span class="sxs-lookup"><span data-stu-id="16f89-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="16f89-158">Orientação do gestor de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="16f89-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="16f89-159">Gestão contínua de dispositivos</span><span class="sxs-lookup"><span data-stu-id="16f89-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="16f89-160">Este passo só é necessário se a sua empresa planeia gerir o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="16f89-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="16f89-161">A gestão contínua de dispositivos dependerá da sua infraestrutura de gestão de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="16f89-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="16f89-162">A maioria tem a mesma funcionalidade geral, mas a interface do utilizador pode variar muito.</span><span class="sxs-lookup"><span data-stu-id="16f89-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="16f89-163">[O CSPs (Fornecedores de Serviços de Configuração)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) permite criar e implementar definições de gestão para os dispositivos da sua rede.</span><span class="sxs-lookup"><span data-stu-id="16f89-163">[CSPs (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="16f89-164">Consulte a [lista de HoloLens CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) para referência.</span><span class="sxs-lookup"><span data-stu-id="16f89-164">See the [list of HoloLens CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="16f89-165">[As políticas de conformidade](/intune/device-compliance-get-started) são regras e configurações que os dispositivos devem cumprir para serem compatíveis com a sua infraestrutura corporativa.</span><span class="sxs-lookup"><span data-stu-id="16f89-165">[Compliance policies](/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="16f89-166">Utilize estas políticas com Acesso Condicional para bloquear o acesso aos recursos da empresa para dispositivos que não estejam em conformidade.</span><span class="sxs-lookup"><span data-stu-id="16f89-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="16f89-167">Por exemplo, pode criar uma política que exija que o Bitlocker esteja ativado.</span><span class="sxs-lookup"><span data-stu-id="16f89-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="16f89-168">[Criar Política de Conformidade](/intune/protect/compliance-policy-create-windows).</span><span class="sxs-lookup"><span data-stu-id="16f89-168">[Create Compliance Policy](/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="16f89-169">O Acesso Condicional permite/nega dispositivos móveis e aplicações móveis a partir do acesso aos recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="16f89-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="16f89-170">Dois documentos que poderá achar úteis são [planear a sua implantação](/azure/active-directory/conditional-access/plan-conditional-access) e [boas práticas.](/azure/active-directory/conditional-access/best-practices)</span><span class="sxs-lookup"><span data-stu-id="16f89-170">Two documents you may find helpful are [Plan your CA Deployment](/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="16f89-171">[Este artigo](/intune/fundamentals/windows-holographic-for-business) fala sobre as ferramentas de gestão da Intune para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="16f89-171">[This article](/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="16f89-172">Criar um perfil de dispositivo</span><span class="sxs-lookup"><span data-stu-id="16f89-172">Create a device profile</span></span>](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="16f89-173">Gerir atualizações</span><span class="sxs-lookup"><span data-stu-id="16f89-173">Manage updates</span></span>

<span data-ttu-id="16f89-174">O Intune inclui uma funcionalidade chamada Update rings for Windows 10 devices, incluindo HoloLens 2 e HoloLens v1 (com Holographic for Business).</span><span class="sxs-lookup"><span data-stu-id="16f89-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="16f89-175">Os anéis de atualização incluem um grupo de definições que determinam como e quando as atualizações são instaladas.</span><span class="sxs-lookup"><span data-stu-id="16f89-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="16f89-176">Por exemplo, pode criar uma janela de manutenção para instalar atualizações ou pode optar por reiniciar após as atualizações serem instaladas.</span><span class="sxs-lookup"><span data-stu-id="16f89-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="16f89-177">Também pode optar por interromper indefinidamente as atualizações até estar pronto para atualizar.</span><span class="sxs-lookup"><span data-stu-id="16f89-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="16f89-178">Leia mais sobre [a configuração dos anéis de atualização com o Intune](/intune/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="16f89-178">Read more about [configuring update rings with Intune](/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="16f89-179">Gestão de aplicações</span><span class="sxs-lookup"><span data-stu-id="16f89-179">Application management</span></span>

<span data-ttu-id="16f89-180">Gerir HoloLens aplicações através de:</span><span class="sxs-lookup"><span data-stu-id="16f89-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="16f89-181">Loja Microsoft</span><span class="sxs-lookup"><span data-stu-id="16f89-181">Microsoft Store</span></span>  
  <span data-ttu-id="16f89-182">O Microsoft Store é a melhor forma de distribuir e consumir aplicações na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="16f89-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="16f89-183">Existe um grande conjunto de aplicações de HoloLens já disponíveis na loja ou pode publicar as [suas próprias.](/windows/uwp/publish/)</span><span class="sxs-lookup"><span data-stu-id="16f89-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="16f89-184">Todas as aplicações na loja estão disponíveis publicamente para todos, mas se não for aceitável, o check-out da Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="16f89-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="16f89-185">Loja Microsoft para Empresas</span><span class="sxs-lookup"><span data-stu-id="16f89-185">Microsoft Store for Business</span></span>](/microsoft-store/)  
  <span data-ttu-id="16f89-186">Microsoft Store para Empresas e Educação é uma loja personalizada para o seu ambiente corporativo.</span><span class="sxs-lookup"><span data-stu-id="16f89-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="16f89-187">Permite-lhe usar o Microsoft Store incorporado em Windows 10 e HoloLens para encontrar, adquirir, distribuir e gerir apps para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="16f89-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="16f89-188">Também permite implementar aplicações específicas para o seu ambiente comercial, mas não para o mundo.</span><span class="sxs-lookup"><span data-stu-id="16f89-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="16f89-189">Implementação e gestão de aplicações via Intune ou outra solução de gestão de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="16f89-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="16f89-190">A maioria das soluções de gestão de dispositivos móveis, incluindo a Intune, fornecem uma forma de implementar uma linha de aplicações empresariais diretamente para um conjunto de dispositivos matriculados.</span><span class="sxs-lookup"><span data-stu-id="16f89-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="16f89-191">Consulte este artigo para [instalar aplicações Intune.](/intune/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="16f89-191">See this article for [Intune app install](/intune/apps-deploy).</span></span>

1. <span data-ttu-id="16f89-192">_não recomendado_ Portal do Dispositivo</span><span class="sxs-lookup"><span data-stu-id="16f89-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="16f89-193">As aplicações também podem ser instaladas no HoloLens utilizando diretamente o Portal do Dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="16f89-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="16f89-194">Isto não é recomendado, uma vez que o Modo de Desenvolvimento tem de ser ativado para utilizar o portal do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="16f89-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="16f89-195">Leia mais sobre [a instalação de aplicações no HoloLens.](hololens-install-apps.md)</span><span class="sxs-lookup"><span data-stu-id="16f89-195">Read more about [installing apps on HoloLens](hololens-install-apps.md).</span></span>

### <a name="certificates"></a><span data-ttu-id="16f89-196">Certificados</span><span class="sxs-lookup"><span data-stu-id="16f89-196">Certificates</span></span>

<span data-ttu-id="16f89-197">Pode distribuir certificados através do seu fornecedor DEDM.</span><span class="sxs-lookup"><span data-stu-id="16f89-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="16f89-198">Se a sua empresa necessitar de certificados, a Intune suporta PKCS, PFX e SCEP.</span><span class="sxs-lookup"><span data-stu-id="16f89-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="16f89-199">É importante entender qual o certificado certo para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="16f89-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="16f89-200">Visite a documentação das [configurações](/intune/protect/certificates-configure) do certificado para determinar qual o cert que é o melhor para si.</span><span class="sxs-lookup"><span data-stu-id="16f89-200">Please visit the [certificate configurations](/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="16f89-201">Se pretender utilizar certificados para HoloLens Autenticação, PFX ou SCEP pode ser adequado para si.</span><span class="sxs-lookup"><span data-stu-id="16f89-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="16f89-202">Consulte os seguintes passos para a utilização [do SCEP](/intune/protect/certificates-profile-scep).</span><span class="sxs-lookup"><span data-stu-id="16f89-202">See the following steps for using [SCEP](/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="16f89-203">Como fazer upgrade para Holographics para Business Commercial Suite</span><span class="sxs-lookup"><span data-stu-id="16f89-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="16f89-204">Windows A Holographics for Business (suite comercial) destina-se apenas a dispositivos de 1ª geração HoloLens.</span><span class="sxs-lookup"><span data-stu-id="16f89-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="16f89-205">O perfil não será aplicado a HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="16f89-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="16f89-206">Você pode encontrar direções para upgrade para a suíte comercial na documentação [de upgrade holográfico.](/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="16f89-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="16f89-207">Como configurar o modo quiosque usando Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="16f89-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="16f89-208">Sincronizar Microsoft Store a Intune (Ver as [seguintes instruções).](/intune/apps/windows-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="16f89-208">Sync Microsoft Store to Intune (See the following [instructions](/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="16f89-209">Verifique as definições da sua aplicação</span><span class="sxs-lookup"><span data-stu-id="16f89-209">Check your app settings</span></span>
    1. <span data-ttu-id="16f89-210">Inicie sessão na sua conta Microsoft Store Negócios</span><span class="sxs-lookup"><span data-stu-id="16f89-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="16f89-211">**Gerir > Produtos e Serviços > Aplicações e > de Software Selecione a aplicação que pretende sincronizar > Disponibilidade de Lojas Privadas > Selecione "Todos" ou "Grupos Específicos"**</span><span class="sxs-lookup"><span data-stu-id="16f89-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="16f89-212">Se não vir a app que pretende, terá de "obter" a aplicação procurando na loja a sua aplicação.</span><span class="sxs-lookup"><span data-stu-id="16f89-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="16f89-213">**Clique na barra "Search" no canto superior direito > tipo no nome da aplicação > clicar na aplicação > selecionar "Get".**</span><span class="sxs-lookup"><span data-stu-id="16f89-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="16f89-214">Se não vir as suas apps no **Intune > aplicações de > aplicações** do cliente, poderá ter de [sincronizar novamente as suas aplicações.](/intune/apps/windows-store-for-business#synchronize-apps)</span><span class="sxs-lookup"><span data-stu-id="16f89-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="16f89-215">Criar um perfil de dispositivo para o modo quiosque</span><span class="sxs-lookup"><span data-stu-id="16f89-215">Create a device profile for Kiosk mode</span></span>](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="16f89-216">Pode configurar diferentes utilizadores para terem diferentes experiências do Modo Quiosque utilizando o "Azure AD" como o "tipo de início de súprico do utilizador".</span><span class="sxs-lookup"><span data-stu-id="16f89-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="16f89-217">No entanto, esta opção apenas está disponível no modo quiosque Multi-App.</span><span class="sxs-lookup"><span data-stu-id="16f89-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="16f89-218">O modo quiosque multi-App funcionará com apenas uma aplicação, bem como com várias aplicações.</span><span class="sxs-lookup"><span data-stu-id="16f89-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Imagem que mostra configuração do modo quiosque em Intune](images/aad-kioskmode.png)

<span data-ttu-id="16f89-220">Para outros serviços de MDM, consulte a documentação do seu fornecedor para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="16f89-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="16f89-221">Consulte as instruções [de quiosque HoloLens](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) se precisar de utilizar uma configuração personalizada e uma configuração XML completa para configurar um quiosque no seu serviço MDM.</span><span class="sxs-lookup"><span data-stu-id="16f89-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="16f89-222">Certificados e Autenticação</span><span class="sxs-lookup"><span data-stu-id="16f89-222">Certificates and Authentication</span></span>

<span data-ttu-id="16f89-223">Os certificados podem ser implantados através do seu MDM (ver "certificados" na [secção MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)</span><span class="sxs-lookup"><span data-stu-id="16f89-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="16f89-224">Os certificados também podem ser distribuídos para o HoloLens através do fornecimento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="16f89-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="16f89-225">Consulte [HoloLens Provisioning](hololens-provisioning.md) para obter informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="16f89-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="16f89-226">Ligações rápidas intune adicionais</span><span class="sxs-lookup"><span data-stu-id="16f89-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="16f89-227">[Criar Perfis:](/intune/configuration/device-profile-create) Os perfis permitem-lhe adicionar e configurar definições que serão empurradas para os dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="16f89-227">[Create Profiles:](/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

