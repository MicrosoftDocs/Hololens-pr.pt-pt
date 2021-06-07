---
title: Visão geral da Cloud conectada HoloLens 2 com Assistência Remota
description: Saiba como inscrever os dispositivos HoloLens 2 através de uma rede Cloud Connected utilizando o Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378484"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="29913-104">Guia de Implementação - HoloLens ligado à nuvem 2 com Assistência Remota – Visão geral</span><span class="sxs-lookup"><span data-stu-id="29913-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="29913-105">Este guia ajuda os profissionais de TI a planear e implementar dispositivos Microsoft HoloLens 2 para a sua organização com o objetivo geral de ter esses dispositivos em nuvem ligados à sua organização com o Dynamics 365 Remote Assist prontos a usar.</span><span class="sxs-lookup"><span data-stu-id="29913-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="29913-106">Tenha em mente que este servirá como um modelo para implementações de prova de conceito para a sua organização em vários casos de utilização hololens 2.</span><span class="sxs-lookup"><span data-stu-id="29913-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="29913-107">Durante o guia, iremos cobrir como inscrever os seus dispositivos na gestão do dispositivo, aplicar licenças conforme necessário e validar que os seus utilizadores finais podem utilizar imediatamente o Remote Assist após a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="29913-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="29913-108">Para isso, iremos analisar as importantes peças de infraestrutura necessárias para se instalar e funcionar – conseguindo a implantação em escala com hololens 2.</span><span class="sxs-lookup"><span data-stu-id="29913-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="29913-109">[![Cenário conectado à ](./images/deployment-guides-revised-scenario-a.png) nuvem](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="29913-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="29913-110">Neste Guia</span><span class="sxs-lookup"><span data-stu-id="29913-110">In this Guide</span></span>

<span data-ttu-id="29913-111">Este guia tem como objetivo específico a criação de Assistência Remota dentro da sua organização nos seus dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="29913-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="29913-112">Cobriremos as necessidades necessárias para atingir esse objetivo.</span><span class="sxs-lookup"><span data-stu-id="29913-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="29913-113">De forma a manter o foco neste objetivo, determinadas preparações e configurações serão pré-selecionadas de forma a otimizar esta implementação ou reduzir os itens necessários à configuração.</span><span class="sxs-lookup"><span data-stu-id="29913-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="29913-114">Você será informado destas escolhas, e pode personalizar a sua implementação com base nas necessidades do seu negócio.</span><span class="sxs-lookup"><span data-stu-id="29913-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="29913-115">Esta é uma configuração semelhante ao [cenário A: Implementar para dispositivos de ligação em nuvem](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), que é uma boa opção para muitas implementações de Prova de Conceito, que incluirá:</span><span class="sxs-lookup"><span data-stu-id="29913-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="29913-116">Wi-Fi redes estão tipicamente totalmente abertas aos serviços da Internet e cloud</span><span class="sxs-lookup"><span data-stu-id="29913-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="29913-117">Azure AD Junte-se à Inscrição automática do MDM -- MDM (Intune) Gerido</span><span class="sxs-lookup"><span data-stu-id="29913-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="29913-118">Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="29913-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="29913-119">Utilizadores únicos ou múltiplos por dispositivo suportado</span><span class="sxs-lookup"><span data-stu-id="29913-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="29913-120">Níveis variados de configurações de bloqueio de dispositivos são aplicados com base em casos de utilização específico, de Quiosque de Aplicações Totalmente Abertos a Únicos</span><span class="sxs-lookup"><span data-stu-id="29913-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="29913-121">Nenhuma outra restrição ou configurações do dispositivo será aplicada neste guia, no entanto encorajamos-o a explorar essas opções após o acabamento.</span><span class="sxs-lookup"><span data-stu-id="29913-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="29913-122">Saiba mais sobre assistência remota</span><span class="sxs-lookup"><span data-stu-id="29913-122">Learn about Remote Assist</span></span>

<span data-ttu-id="29913-123">O Remote Assist permite a manutenção e reparação colaborativa, inspeção remota, bem como partilha e formação de conhecimentos.</span><span class="sxs-lookup"><span data-stu-id="29913-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="29913-124">Ao ligar pessoas em diferentes funções e locais, um técnico que usa o Remote Assist pode ligar-se a um colaborador remoto nas Equipas microsoft.</span><span class="sxs-lookup"><span data-stu-id="29913-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="29913-125">Podem combinar vídeo, imagens e anotações para resolver problemas em tempo real, mesmo quando são&#39;não no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="29913-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="29913-126">Os colaboradores remotos podem inserir imagens de referência, esquemas e outras informações úteis que o técnico&#39;espaço físico para que possam consultar o esquema enquanto trabalham heads-up e mãos-livres nos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="29913-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="29913-127">Neste guia:</span><span class="sxs-lookup"><span data-stu-id="29913-127">In this guide you will:</span></span>

<span data-ttu-id="29913-128">Preparar:</span><span class="sxs-lookup"><span data-stu-id="29913-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="29913-129">Conheça o essencial da infraestrutura para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="29913-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="29913-130">Saiba mais sobre o Azure AD e crie um se não&#39;o tiver.</span><span class="sxs-lookup"><span data-stu-id="29913-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="29913-131">Saiba mais sobre a gestão de identidade e como configurar melhor as contas AD da Azure.</span><span class="sxs-lookup"><span data-stu-id="29913-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="29913-132">Saiba mais sobre o MDM e prepare-se com o Intune se não&#39;já não tenha um pronto.</span><span class="sxs-lookup"><span data-stu-id="29913-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="29913-133">Conheça os requisitos de networking do Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="29913-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="29913-134">Opcionalmente: VPN para ligar aos recursos organizacionais</span><span class="sxs-lookup"><span data-stu-id="29913-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="29913-135">Configure:</span><span class="sxs-lookup"><span data-stu-id="29913-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="29913-136">Como criar Utilizadores e Grupos.</span><span class="sxs-lookup"><span data-stu-id="29913-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="29913-137">Como configurar a inscrição automática dentro do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="29913-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="29913-138">Como atribuir as suas licenças de inscrição.</span><span class="sxs-lookup"><span data-stu-id="29913-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="29913-139">Implementação:</span><span class="sxs-lookup"><span data-stu-id="29913-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="29913-140">Configurar os hololens 2 e validar a inscrição.</span><span class="sxs-lookup"><span data-stu-id="29913-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="29913-141">Valide que pode esporar uma chamada de Assistência Remota.</span><span class="sxs-lookup"><span data-stu-id="29913-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="29913-142">Manter:</span><span class="sxs-lookup"><span data-stu-id="29913-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="29913-143">Como atualizar o Remote Assist utilizando a aplicação Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="29913-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="29913-144">A fazer um plano de apoio.</span><span class="sxs-lookup"><span data-stu-id="29913-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="29913-145">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="29913-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="29913-146">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="29913-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="29913-147">Implementação ligada à nuvem - Prepare-se</span><span class="sxs-lookup"><span data-stu-id="29913-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

