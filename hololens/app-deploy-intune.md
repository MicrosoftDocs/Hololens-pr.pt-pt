---
title: Portal intune e da empresa
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
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378631"
---
# <a name="intune--company-portal"></a><span data-ttu-id="2db51-104">Portal da Empresa Intune &</span><span class="sxs-lookup"><span data-stu-id="2db51-104">Intune & Company Portal</span></span>

<span data-ttu-id="2db51-105">Com a Mobile Device Management (MDM), pode utilizar as suas próprias aplicações personalizadas através [do Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para a implementar diretamente nos seus dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2db51-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="2db51-106">O Microsoft Intune é um serviço baseado na nuvem que se foca na gestão de dispositivos móveis (MDM) e na gestão de aplicações móveis (MAM).</span><span class="sxs-lookup"><span data-stu-id="2db51-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="2db51-107">O Intune está incluído na [suite Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)da Microsoft, e permite que os utilizadores sejam produtivos, mantendo os dados da sua organização protegidos.</span><span class="sxs-lookup"><span data-stu-id="2db51-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="2db51-108">Para saber mais sobre Intune, leia [O Que é Intune.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="2db51-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="2db51-109">Configuração</span><span class="sxs-lookup"><span data-stu-id="2db51-109">Setup</span></span>

1. <span data-ttu-id="2db51-110">Faça upload de uma aplicação para uma Linha de Negócios ou faça upload de uma aplicação personalizada para o seu inquilino Intune.</span><span class="sxs-lookup"><span data-stu-id="2db51-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="2db51-111">Ver também: [Gestão de aplicações da Enterprise](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="2db51-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="2db51-112">[Atribua a sua aplicação a um grupo.](https://docs.microsoft.com/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="2db51-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="2db51-113">Com base no tipo de atribuição que escolher, a aplicação pode ser entregue automaticamente ou disponível para ser prontamente puxada para baixo se tiver uma seleção de aplicações.</span><span class="sxs-lookup"><span data-stu-id="2db51-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="2db51-114">Ao construir o seu pacote appx, certifique-se de que inclui a arquitetura para os dispositivos para os dispositivos a que está a implementar.</span><span class="sxs-lookup"><span data-stu-id="2db51-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="2db51-115">HoloLens 2 é ARM64, e HoloLens (1ª Gen) é x86.</span><span class="sxs-lookup"><span data-stu-id="2db51-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="2db51-116">Pode incluir ambos num único pacote de aplicações se pretender ter um ambiente de dispositivos mistos.</span><span class="sxs-lookup"><span data-stu-id="2db51-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="2db51-117">Tipos de atribuição</span><span class="sxs-lookup"><span data-stu-id="2db51-117">Assignment types</span></span>

<span data-ttu-id="2db51-118">Para que a sua aplicação seja automaticamente instalada no dispositivo após a inscrição, deverá selecionar **o Requerido** para esse grupo.</span><span class="sxs-lookup"><span data-stu-id="2db51-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="2db51-119">Para disponibilizar a sua aplicação para download para dispositivos matriculados através do portal da empresa, selecione **Disponível para dispositivos inscritos.**</span><span class="sxs-lookup"><span data-stu-id="2db51-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="2db51-120">experiência End-User</span><span class="sxs-lookup"><span data-stu-id="2db51-120">End-User Experience</span></span>

<span data-ttu-id="2db51-121">Depois de configurar a configuração no Intune, está pronto para que os utilizadores finais recebam as suas aplicações selecionadas.</span><span class="sxs-lookup"><span data-stu-id="2db51-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="2db51-122">Siga estes passos para obter automaticamente a sua(s) aplicação):</span><span class="sxs-lookup"><span data-stu-id="2db51-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="2db51-123">Inscreva o seu dispositivo com o seu inquilino.</span><span class="sxs-lookup"><span data-stu-id="2db51-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="2db51-124">Uma vez concluída a inscrição do seu dispositivo, deverá receber a aplicação no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2db51-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="2db51-125">Se não estiver a vê-lo imediatamente, vá a **Definições**  >  **Contas**  >  **Trabalhar ou Escola a** sua  >  *conta* Informação, e desloque-se para ver informações sobre o estado da aplicação instalada.</span><span class="sxs-lookup"><span data-stu-id="2db51-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="2db51-126">Como chegar a apps através do Portal da Empresa:</span><span class="sxs-lookup"><span data-stu-id="2db51-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="2db51-127">Abra o **Menu Iniciar** e selecione **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="2db51-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="2db51-128">Procure no **Portal da Empresa** e descarregue a aplicação.</span><span class="sxs-lookup"><span data-stu-id="2db51-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="2db51-129">Inscreva-se na sua conta.</span><span class="sxs-lookup"><span data-stu-id="2db51-129">Sign into your account.</span></span>
4. <span data-ttu-id="2db51-130">Selecione a aplicação que deseja receber e descarregue-a.</span><span class="sxs-lookup"><span data-stu-id="2db51-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="2db51-131">Saiba mais sobre [a instalação automática do Portal da Empresa](https://docs.microsoft.com/mem/intune/apps/company-portal-app) e a [implementação e gestão de aplicações no Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="2db51-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
