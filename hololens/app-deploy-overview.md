---
title: Visão geral - Gestão de Aplicações
description: Começa com uma visão geral da gestão de aplicações de realidade mista com a gestão de dispositivos móveis, loja da Microsoft para negócios e pacotes de provisionamento.
keywords: HoloLens, utilizador, conta, app, gestão de aplicações,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635556"
---
# <a name="app-management-overview"></a><span data-ttu-id="b0e4b-104">Gestão de Aplicativos: Visão geral</span><span class="sxs-lookup"><span data-stu-id="b0e4b-104">App Management: Overview</span></span>

<span data-ttu-id="b0e4b-105">Pode implementar aplicações em quatro caminhos diferentes: **Mobile Device Management (MDM)**, **Microsoft Store para Empresas**, **Microsoft Store**, ou instalando-as através **do Provisioning**.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="b0e4b-106">Gestão de Dispositivos Móveis (MDM)</span><span class="sxs-lookup"><span data-stu-id="b0e4b-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="b0e4b-107">Uma solução MDM permite que os decisores e administradores de TI instalem (empurrem) as suas aplicações internamente, linha de negócios ou comprem aplicações através da loja para um grupo de utilizadores.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="b0e4b-108">HoloLens dispositivos funcionam melhor com Microsoft Endpoint Manager (Intune) para [gestão de aplicações.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="b0e4b-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="b0e4b-109">A Intune também oferece aos utilizadores um controlo mais fino sobre aplicações geridas por TI através da experiência Portal da Empresa transferível.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e4b-110">As seguintes instruções são para os utilizadores que pretendam gerir as suas aplicações com o Intune.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="b0e4b-111">A Microsoft recomenda a utilização do Intune para a gestão de aplicações e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="b0e4b-112">A Gestão de Dispositivos Móveis (MDM) é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="b0e4b-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="b0e4b-113">MDM implantado + Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="b0e4b-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="b0e4b-114">Aplicativos line of Business (não públicos)</span><span class="sxs-lookup"><span data-stu-id="b0e4b-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="b0e4b-115">Instalação manual de aplicações disponíveis através de Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="b0e4b-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="b0e4b-116">Administração empurra através da política do MDM</span><span class="sxs-lookup"><span data-stu-id="b0e4b-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="b0e4b-117">Atualização automática através do MDM</span><span class="sxs-lookup"><span data-stu-id="b0e4b-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="b0e4b-118">Loja Microsoft para Empresas</span><span class="sxs-lookup"><span data-stu-id="b0e4b-118">Microsoft Store for Business</span></span>

<span data-ttu-id="b0e4b-119">O [Microsoft Store para Empresas](app-deploy-store-business.md) fornece aos decisores e administradores de TI nas empresas para encontrar, adquirir, gerir e distribuir aplicações gratuitas e pagas.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="b0e4b-120">Os administradores de TI podem gerir Microsoft Store aplicações e aplicações privadas de linha de negócios num único inventário, além de atribuir e reutilizar licenças conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="b0e4b-121">Para mais informações, visite [Pré-requisitos para a utilização do Microsoft Store para Empresas](/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="b0e4b-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="b0e4b-122">O Microsoft Store para Empresas é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="b0e4b-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="b0e4b-123">Aplicativos públicos ou de linha de negócios</span><span class="sxs-lookup"><span data-stu-id="b0e4b-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="b0e4b-124">Instalação automática de aplicações necessárias através da associação MDM</span><span class="sxs-lookup"><span data-stu-id="b0e4b-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="b0e4b-125">Utilizador descarrega manualmente apps</span><span class="sxs-lookup"><span data-stu-id="b0e4b-125">User manually downloads apps</span></span>
* <span data-ttu-id="b0e4b-126">Atualização automática</span><span class="sxs-lookup"><span data-stu-id="b0e4b-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="b0e4b-127">Aplicações da Loja Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0e4b-127">Microsoft Store apps</span></span>

<span data-ttu-id="b0e4b-128">O Microsoft Store fornece aos decisores e administradores de TI nas empresas para encontrar, adquirir, gerir e distribuir aplicações públicas.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="b0e4b-129">Esta Microsoft Store é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="b0e4b-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="b0e4b-130">Apenas aplicações públicas</span><span class="sxs-lookup"><span data-stu-id="b0e4b-130">Public apps only</span></span>
* <span data-ttu-id="b0e4b-131">Utilizador descarrega manualmente apps</span><span class="sxs-lookup"><span data-stu-id="b0e4b-131">User manually downloads apps</span></span>
* <span data-ttu-id="b0e4b-132">Atualização automática se estiver ligado à Internet</span><span class="sxs-lookup"><span data-stu-id="b0e4b-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="b0e4b-133">Para mais informações, visite [as Aplicações da Loja Holográfica.](/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="b0e4b-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="b0e4b-134">Instalar através de Pacotes de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="b0e4b-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="b0e4b-135">[O Provisioning Packages](app-deploy-provisioning-package.md) permite instalar aplicações personalizadas ou de Linha de Negócios, permitindo que profissionais e administradores de TI instalem rapidamente aplicações num(s) dispositivo(s) local via USB.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="b0e4b-136">Esta instalação pode ser feita sem ligação à Internet e para qualquer tipo de identidade.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="b0e4b-137">A instalação através de Pacotes de Provisionamento é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="b0e4b-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="b0e4b-138">Linha de aplicações de Negócios / Auto-desenvolvidas (não públicas)</span><span class="sxs-lookup"><span data-stu-id="b0e4b-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="b0e4b-139">Aplicativos públicos (se o instalador offline estiver disponível)</span><span class="sxs-lookup"><span data-stu-id="b0e4b-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="b0e4b-140">Apenas carregamento lateral USB</span><span class="sxs-lookup"><span data-stu-id="b0e4b-140">USB side-loading only</span></span>
* <span data-ttu-id="b0e4b-141">Nenhuma atualização automática (requer atualizações manuais através do Pacote de Provisionamento)</span><span class="sxs-lookup"><span data-stu-id="b0e4b-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="b0e4b-142">Instale apps no HoloLens 2 através do Instalador de Aplicações</span><span class="sxs-lookup"><span data-stu-id="b0e4b-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="b0e4b-143">A utilização do [App Installer](app-deploy-app-installer.md) pode ter uma experiência simples de instalar apps em dispositivos locais ou partilhar uma aplicação com outra pessoa que não esteja familiarizada com outros métodos de instalação de aplicações em HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="b0e4b-144">Isto pode ser feito sem necessidade de ativar o Modo de Desenvolvimento ou utilizar o Portal do Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="b0e4b-145">Este é um método simples de distribuir uma aplicação completamente construída.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="b0e4b-146">Independentemente de pretender simplesmente despromupro ser a sua app para outro utilizador com um HoloLens, ou se pretende implementar a sua app, este método funciona facilmente.</span><span class="sxs-lookup"><span data-stu-id="b0e4b-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="b0e4b-147">A instalação através do Instalador de Aplicações é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="b0e4b-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="b0e4b-148">Linha de Negócios / Self desenvolvido (não público) apps</span><span class="sxs-lookup"><span data-stu-id="b0e4b-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="b0e4b-149">Apenas carga lateral</span><span class="sxs-lookup"><span data-stu-id="b0e4b-149">Side-load only</span></span>
* <span data-ttu-id="b0e4b-150">Não requer modo de desenvolvimento ou portal do dispositivo</span><span class="sxs-lookup"><span data-stu-id="b0e4b-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="b0e4b-151">Fácil de instalar o utilizador final</span><span class="sxs-lookup"><span data-stu-id="b0e4b-151">Easy for end user to install</span></span>
