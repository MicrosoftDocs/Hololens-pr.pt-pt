---
title: Intune e Portal da Empresa
description: Aprenda a configurar, atribuir e criar uma experiência de utilizador confortável com a Intune, a gestão de dispositivos móveis e o portal da empresa.
keywords: intune, gestão de aplicativos, app, portal da empresa, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635505"
---
# <a name="intune--company-portal"></a><span data-ttu-id="039b2-104">& Portal da Empresa intune</span><span class="sxs-lookup"><span data-stu-id="039b2-104">Intune & Company Portal</span></span>

<span data-ttu-id="039b2-105">Com a Mobile Device Management (MDM), pode utilizar as suas próprias aplicações personalizadas através [de Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) para a implementar diretamente nos seus dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="039b2-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="039b2-106">Microsoft Intune é um serviço baseado na nuvem que se foca na gestão de dispositivos móveis (MDM) e na gestão de aplicações móveis (MAM).</span><span class="sxs-lookup"><span data-stu-id="039b2-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="039b2-107">O Intune está incluído na [suite Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)da Microsoft, e permite que os utilizadores sejam produtivos, mantendo os dados da sua organização protegidos.</span><span class="sxs-lookup"><span data-stu-id="039b2-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="039b2-108">Para saber mais sobre Intune, leia [O Que é Intune.](/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="039b2-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="039b2-109">Configuração</span><span class="sxs-lookup"><span data-stu-id="039b2-109">Setup</span></span>

1. <span data-ttu-id="039b2-110">Faça upload de uma aplicação para uma Linha de Negócios ou faça upload de uma aplicação personalizada para o seu inquilino Intune.</span><span class="sxs-lookup"><span data-stu-id="039b2-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="039b2-111">Ver também: [Gestão de aplicações da Enterprise](/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="039b2-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="039b2-112">[Atribua a sua aplicação a um grupo.](/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="039b2-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="039b2-113">Com base no tipo de atribuição que escolher, a aplicação pode ser entregue automaticamente ou disponível para ser prontamente puxada para baixo se tiver uma seleção de aplicações.</span><span class="sxs-lookup"><span data-stu-id="039b2-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="039b2-114">Ao construir o seu pacote appx, certifique-se de que inclui a arquitetura para os dispositivos para os dispositivos a que está a implementar.</span><span class="sxs-lookup"><span data-stu-id="039b2-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="039b2-115">HoloLens 2 é ARM64, e HoloLens (1ª Gen) é x86.</span><span class="sxs-lookup"><span data-stu-id="039b2-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="039b2-116">Pode incluir ambos num único pacote de aplicações se pretender ter um ambiente de dispositivos mistos.</span><span class="sxs-lookup"><span data-stu-id="039b2-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="039b2-117">Tipos de atribuição</span><span class="sxs-lookup"><span data-stu-id="039b2-117">Assignment types</span></span>

<span data-ttu-id="039b2-118">Para que a sua aplicação seja automaticamente instalada no dispositivo após a inscrição, deverá selecionar **o Requerido** para esse grupo.</span><span class="sxs-lookup"><span data-stu-id="039b2-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="039b2-119">Para disponibilizar a sua aplicação para download para dispositivos matriculados através do portal da empresa, selecione **Disponível para dispositivos inscritos.**</span><span class="sxs-lookup"><span data-stu-id="039b2-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="039b2-120">experiência End-User</span><span class="sxs-lookup"><span data-stu-id="039b2-120">End-User Experience</span></span>

<span data-ttu-id="039b2-121">Depois de configurar a configuração no Intune, está pronto para que os utilizadores finais recebam as suas aplicações selecionadas.</span><span class="sxs-lookup"><span data-stu-id="039b2-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="039b2-122">Siga estes passos para obter automaticamente a sua(s) aplicação):</span><span class="sxs-lookup"><span data-stu-id="039b2-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="039b2-123">Inscreva o seu dispositivo com o seu inquilino.</span><span class="sxs-lookup"><span data-stu-id="039b2-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="039b2-124">Uma vez concluída a inscrição do seu dispositivo, deverá receber a aplicação no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="039b2-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="039b2-125">Se não estiver a vê-lo imediatamente, vá a **Definições**  >  **Contas**  >  **Trabalhar ou Estudar a** sua  >  *conta* Informação, e desça para ver informações sobre o estado da aplicação instalada.</span><span class="sxs-lookup"><span data-stu-id="039b2-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="039b2-126">Como chegar a aplicativos através do Portal da Empresa:</span><span class="sxs-lookup"><span data-stu-id="039b2-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="039b2-127">Abra o **Menu Iniciar** e selecione **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="039b2-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="039b2-128">Procure **Portal da Empresa** e descarregue a aplicação.</span><span class="sxs-lookup"><span data-stu-id="039b2-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="039b2-129">Inscreva-se na sua conta.</span><span class="sxs-lookup"><span data-stu-id="039b2-129">Sign into your account.</span></span>
4. <span data-ttu-id="039b2-130">Selecione a aplicação que deseja receber e descarregue-a.</span><span class="sxs-lookup"><span data-stu-id="039b2-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="039b2-131">Saiba mais sobre [a instalação automática do Portal da Empresa](/mem/intune/apps/company-portal-app) e a [implementação e gestão de aplicações no Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="039b2-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
