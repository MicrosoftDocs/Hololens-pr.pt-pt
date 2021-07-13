---
title: Guia de implementação - Implementação HoloLens 2 ligada à nuvem em escala com Assistência Remota - Configuração
description: Saiba como configurar configurações para inscrever HoloLens dispositivos sobre uma rede Cloud Connected em escala com Remote Assist.
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635148"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="edd2a-104">Configuração - Guia ligado à nuvem</span><span class="sxs-lookup"><span data-stu-id="edd2a-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="edd2a-105">Nesta secção do guia,&#39;vamos analisar como configurar a Inscrição Automática para o seu inquilino, e como aplicar licenças tanto para o Intune como para a Assistência Remota.</span><span class="sxs-lookup"><span data-stu-id="edd2a-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="edd2a-106">Utilizadores e Grupos Azure</span><span class="sxs-lookup"><span data-stu-id="edd2a-106">Azure Users and Groups</span></span>

<span data-ttu-id="edd2a-107">Azure, e Intune por essa extensão, usa utilizadores e grupos para ajudar a atribuir configurações e licenças.</span><span class="sxs-lookup"><span data-stu-id="edd2a-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="edd2a-108">Para validar este fluxo de implementação e ser capaz de fazer uma chamada de Assistência Remota de um utilizador para outro,&#39;vai precisar de duas contas de utilizador.</span><span class="sxs-lookup"><span data-stu-id="edd2a-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="edd2a-109">Podemos fazer um único grupo de utilizadores com o propósito de atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="edd2a-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="edd2a-110">Podemos juntar ambos os utilizadores ao mesmo grupo e aplicar uma licença para Intune e Remote Assist a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="edd2a-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="edd2a-111">Se não&#39;já não tem acesso a duas contas AD Azure num grupo de utilizadores que pode utilizar; aqui estão os guias de arranque rápido para:</span><span class="sxs-lookup"><span data-stu-id="edd2a-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="edd2a-112">Como criar um utilizador</span><span class="sxs-lookup"><span data-stu-id="edd2a-112">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="edd2a-113">Como criar um grupo</span><span class="sxs-lookup"><span data-stu-id="edd2a-113">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="edd2a-114">[Adicionar utilizadores a um grupo](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Adicionar utilizadores criados para criar grupo</span><span class="sxs-lookup"><span data-stu-id="edd2a-114">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="edd2a-115">[Configure Ad AD para permitir que um Grupo de Utilizadores se junte a dispositivos](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Certifique-se de que o novo grupo de utilizadores tem permissão para inscrever dispositivos no Azure AD</span><span class="sxs-lookup"><span data-stu-id="edd2a-115">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="edd2a-116">Inscrição automática no HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="edd2a-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="edd2a-117">Para ter uma experiência suave e sem emenda, a criação de Azure Ative Directory Join (AADJ) e a Inscrição Automática para a Intune para HoloLens 2 dispositivos é o caminho a seguir.</span><span class="sxs-lookup"><span data-stu-id="edd2a-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="edd2a-118">Isto permitirá que os utilizadores insiram as suas credenciais de login da organização durante o OOBE e se registem automaticamente com a Azure AD e inscrevam o dispositivo no MDM.</span><span class="sxs-lookup"><span data-stu-id="edd2a-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="edd2a-119">Ao utilizar [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/#home)podemos selecionar serviços e navegar algumas páginas até podermos selecionar Obter um Premium teste.</span><span class="sxs-lookup"><span data-stu-id="edd2a-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="edd2a-120">Pode notar que há Azure Ative Directory Premium 1 e 2, pois a Inscrição Automática P1 é suficiente.</span><span class="sxs-lookup"><span data-stu-id="edd2a-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="edd2a-121">Podemos selecionar Intune e selecionar o âmbito do utilizador para a inscrição automática e selecionar o grupo que foi previamente criado.</span><span class="sxs-lookup"><span data-stu-id="edd2a-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="edd2a-122">Para mais detalhes e passos, leia o guia sobre [como permitir a inscrição automática para o Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)</span><span class="sxs-lookup"><span data-stu-id="edd2a-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="edd2a-123">Licenças de Inscrição</span><span class="sxs-lookup"><span data-stu-id="edd2a-123">Application Licenses</span></span>

<span data-ttu-id="edd2a-124">Uma licença de aplicação permite a um utilizador instalar apps adquiridas pela empresa ou atualizar de um teste gratuito para a versão completa de uma aplicação.</span><span class="sxs-lookup"><span data-stu-id="edd2a-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="edd2a-125">As licenças de aplicação podem ser aplicadas a utilizadores, grupos de utilizadores ou grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="edd2a-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="edd2a-126">&#39;vai precisar de licenças de Assistência Remota para os utilizadores da sua organização utilizarem o Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="edd2a-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="edd2a-127">Para efeitos deste guia, atribuiremos licenças de Assistência Remota ao grupo de utilizadores que criámos acima em [Utilizadores e Grupos Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="edd2a-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="edd2a-128">Os requisitos para licenças podem ser diferentes dependendo se o utilizador irá fazer a chamada de Assistência Remota a partir de um dispositivo ou será um colaborador remoto de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="edd2a-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="edd2a-129">Por predefinição, as caixas de assistência remota e Teams estão marcadas.</span><span class="sxs-lookup"><span data-stu-id="edd2a-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="edd2a-130">Para efeitos deste guia, sugerimos deixar as caixas predefinidas verificadas.</span><span class="sxs-lookup"><span data-stu-id="edd2a-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="edd2a-131">Saiba mais sobre os [diferentes requisitos de licenciamento e produto por função.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)</span><span class="sxs-lookup"><span data-stu-id="edd2a-131">Learn more about the different [Licensing and product requirements per role](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="edd2a-132">Existem alguns tipos diferentes de licenças de Assistência Remota, por isso certifique-se de obter as corretas para as suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="edd2a-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="edd2a-133">Terá&#39;de adquirir a [licença.](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="edd2a-133">You&#39;ll need to [acquire the license](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="edd2a-134">[Aplique as suas licenças](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) no grupo.</span><span class="sxs-lookup"><span data-stu-id="edd2a-134">[Apply your licenses](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="edd2a-135">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="edd2a-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="edd2a-136">Implementação ligada à nuvem - Implementar</span><span class="sxs-lookup"><span data-stu-id="edd2a-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)