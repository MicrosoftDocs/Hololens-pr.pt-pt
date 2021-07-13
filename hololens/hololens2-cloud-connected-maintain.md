---
title: Guia de implementação - Implementação HoloLens 2 ligada à nuvem em escala com assistência remota - Manter
description: Mantenha-se atualizado com as nossas dicas para manter e suportar HoloLens dispositivos numa rede Cloud Connected.
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635165"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="fb6db-104">Manter - Guia ligado à nuvem</span><span class="sxs-lookup"><span data-stu-id="fb6db-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="fb6db-105">Atualizações</span><span class="sxs-lookup"><span data-stu-id="fb6db-105">Updates</span></span>

<span data-ttu-id="fb6db-106">A Microsoft desenhou Windows Update for Business para fornecer aos administradores de TI capacidades adicionais de gestão centradas na Windows atualização, tais como a capacidade de implementar atualizações em grupos de dispositivos e definir janelas de manutenção para instalar atualizações.</span><span class="sxs-lookup"><span data-stu-id="fb6db-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="fb6db-107">Saiba como [gerir HoloLens atualizações,](/hololens/hololens-updates) incluindo dias programados, hora programada e definição de horas ativas no dispositivo para que seja atualizado fora do horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fb6db-107">Learn how to [manage HoloLens updates](/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="fb6db-108">O Remote Assist é uma aplicação In-Box e pode ser atualizado através da aplicação Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="fb6db-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="fb6db-109">Para todas as aplicações que são descarregadas através do Microsoft Store podem ser [atualizadas através da própria](/hololens/holographic-store-apps#update-apps) aplicação Microsoft Store manualmente.</span><span class="sxs-lookup"><span data-stu-id="fb6db-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="fb6db-110">Plano de Suporte</span><span class="sxs-lookup"><span data-stu-id="fb6db-110">Support Plan</span></span>

<span data-ttu-id="fb6db-111">Um plano de apoio é uma coisa excelente para se ter em prática.</span><span class="sxs-lookup"><span data-stu-id="fb6db-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="fb6db-112">Ter alguém, ou um grupo treinado para resolver problemas no processo de inscrição em dispositivos HoloLens e também uso geral do dispositivo de HoloLens dentro da sua organização é útil.</span><span class="sxs-lookup"><span data-stu-id="fb6db-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="fb6db-113">De forma a permitir que os seus utilizadores tenham uma resolução mais rápida dos seus problemas, sugerimos que o seu processo de escalada seja tratado de forma semelhante a esta ordem:</span><span class="sxs-lookup"><span data-stu-id="fb6db-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="fb6db-114">Sua mesa de apoio.</span><span class="sxs-lookup"><span data-stu-id="fb6db-114">Your Support desk.</span></span>
2. <span data-ttu-id="fb6db-115">A sua equipa de peritos em HoloLens</span><span class="sxs-lookup"><span data-stu-id="fb6db-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="fb6db-116">[HoloLens Docs](/hololens/)  /  [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="fb6db-116">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="fb6db-117">Suporte de contato</span><span class="sxs-lookup"><span data-stu-id="fb6db-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="fb6db-118">Plano de Desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="fb6db-118">Development Plan</span></span>

<span data-ttu-id="fb6db-119">Com o seu dispositivo matriculado com sucesso, está agora preparado para implementar aplicações da Linha de Negócios (apps LOB) para os seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fb6db-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="fb6db-120">Estes são aplicativos personalizados construídos para a sua organização&#39;necessidades.</span><span class="sxs-lookup"><span data-stu-id="fb6db-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="fb6db-121">Se já tem uma linha de aplicação de negócios, então&#39;pronto para implementar a [sua aplicação através do MDM.](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="fb6db-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="fb6db-122">Se&#39;prefere um método diferente, em seguida, reveja a visão geral da implementação da [aplicação para HoloLens 2](/hololens/app-deploy-overview) para aprender mais métodos de implementação da sua app LOB nos seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fb6db-122">If you&#39;d prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="fb6db-123">Se ainda&#39;ter criado a sua própria app LOB ou ainda estiver em processo de criação, então reveja os nossos docs de desenvolvimento de realidade mista para [começar a desenhar e prototipar](/windows/mixed-reality/design/design) ou aprender os conceitos fundamentais para começar com o desenvolvimento da realidade [mista.](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="fb6db-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="fb6db-124">Gestão de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="fb6db-124">Device Management</span></span> 

<span data-ttu-id="fb6db-125">Embora este guia falasse sobre a criação de Mobile Device Management (MDM) não foi utilizado para aplicar restrições de dispositivos ou políticas aplicadas aos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fb6db-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="fb6db-126">A gestão do dispositivo pode ser usada para permitir o acesso, empurrando certificados ou restringindo o acesso com uma variedade de restrições ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb6db-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="fb6db-127">Em muitos casos, os dispositivos podem ter restrições de conectividade como Bluetooth, VPN, USB ou até mesmo desligar o acesso à câmara ou microfone.</span><span class="sxs-lookup"><span data-stu-id="fb6db-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="fb6db-128">Se algum destes interesses o encorajar então a ler a nossa [página comum de restrições](hololens-common-device-restrictions.md)de dispositivos .</span><span class="sxs-lookup"><span data-stu-id="fb6db-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="fb6db-129">Existem outras restrições mais complexas do dispositivo que pode utilizar.</span><span class="sxs-lookup"><span data-stu-id="fb6db-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="fb6db-130">Como:</span><span class="sxs-lookup"><span data-stu-id="fb6db-130">Such as:</span></span>

- <span data-ttu-id="fb6db-131">Limitar as páginas que podem ser visualizadas na aplicação Definições utilizando [a DefiniçõesPageVisibilidade](settings-uri-list.md), permitindo aos utilizadores acederem apenas às definições de que necessitam para se ajustarem, tais como alterar a sua ligação Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="fb6db-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="fb6db-132">Utilize [o modo Quiosque](hololens-kiosk.md) para limitar a UI apresentada aos utilizadores num dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb6db-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="fb6db-133">Pode definir Quiosques para mostrar uma única aplicação, ou várias aplicações com uma página de início personalizada.</span><span class="sxs-lookup"><span data-stu-id="fb6db-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="fb6db-134">Os quiosques também podem apresentar diferentes experiências a diferentes utilizadores.</span><span class="sxs-lookup"><span data-stu-id="fb6db-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="fb6db-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) para impedir que aplicações ou processos específicos se desempam totalmente.</span><span class="sxs-lookup"><span data-stu-id="fb6db-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="fb6db-136">Se quiser aprender sobre métodos mais diferentes de gestão de dispositivos ou restrições de dispositivos, então dê o próximo passo e leia a nossa Visão Geral de Gestão de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fb6db-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="fb6db-137">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="fb6db-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fb6db-138">Leia a visão geral dos CSPs e da Gestão de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="fb6db-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)