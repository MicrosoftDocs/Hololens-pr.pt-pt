---
title: Segurança do sistema operativo sem administração
description: Saiba mais sobre sistemas operativos sem administração, proprietários de dispositivos e segurança em dispositivos de realidade mista HoloLens.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, administradores, sem administração, sistema operativo, sistema operativo sem administração, administrador-os, administração-sem-os, hololens 2, hololens2 segurança,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379877"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="66bff-104">Sistema operativo sem administração</span><span class="sxs-lookup"><span data-stu-id="66bff-104">Admin-less operating system</span></span>

<span data-ttu-id="66bff-105">O HoloLens 2 minimiza a área de superfície para a escalada de privilégios, desativando o suporte ao grupo de Administradores e limitando todo o código de aplicação UWP de terceiros para executar apenas como utilizadores padrão dentro da caixa de areia AppContainer.</span><span class="sxs-lookup"><span data-stu-id="66bff-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="66bff-106">Este código só tem acesso aos recursos protegidos por capacidades expressamente manifestadas na aplicação de um utilizador não levítico, para além dos recursos acessíveis a todos os AppContainers.</span><span class="sxs-lookup"><span data-stu-id="66bff-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="66bff-107">Estas capacidades de aplicação continuam a ter o modelo de classificação de três níveis:</span><span class="sxs-lookup"><span data-stu-id="66bff-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="66bff-108">Geral</span><span class="sxs-lookup"><span data-stu-id="66bff-108">General</span></span>
  * <span data-ttu-id="66bff-109">Restrito</span><span class="sxs-lookup"><span data-stu-id="66bff-109">Restricted</span></span>
  * <span data-ttu-id="66bff-110">Windows</span><span class="sxs-lookup"><span data-stu-id="66bff-110">Windows</span></span>

<span data-ttu-id="66bff-111">Os componentes do Windows também podem alavancar a caixa de areia AppContainer através de UWPs do sistema.</span><span class="sxs-lookup"><span data-stu-id="66bff-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="66bff-112">Para saber mais sobre a Universal Windows Platform (UWP), consulte [a documentação do UWP](https://docs.microsoft.com/windows/uwp/).</span><span class="sxs-lookup"><span data-stu-id="66bff-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](https://docs.microsoft.com/windows/uwp/).</span></span> <span data-ttu-id="66bff-113">Além disso, os componentes windows com maior necessidade de redução de privilégios (como páginas de conteúdos de navegador ou parsers) utilizam a caixa de areia Menos Privilegiada appContainer (LPAC), que corta o acesso ao conjunto de recursos acessíveis a todos os AppContainers.</span><span class="sxs-lookup"><span data-stu-id="66bff-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="66bff-114">Proprietário do dispositivo</span><span class="sxs-lookup"><span data-stu-id="66bff-114">Device owner</span></span>

<span data-ttu-id="66bff-115">Por último, a execução de operações específicas a nível do dispositivo, como a junção do dispositivo a um inquilino ou à gestão do utilizador, só é permitida para "proprietários de dispositivos".</span><span class="sxs-lookup"><span data-stu-id="66bff-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="66bff-116">Este grupo é preenchido por utilizadores no dispositivo através de um dos seguintes passos:</span><span class="sxs-lookup"><span data-stu-id="66bff-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="66bff-117">O primeiro utilizador do dispositivo é sempre designado como Proprietário.</span><span class="sxs-lookup"><span data-stu-id="66bff-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="66bff-118">Para os utilizadores AD Azure, a exceção a esta regra é que se o dispositivo for Azure AD aderido através de inscrição em AD Azure ou a granel, que utiliza um utilizador não real.</span><span class="sxs-lookup"><span data-stu-id="66bff-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="66bff-119">Neste caso, o primeiro utilizador AAD a assinar no dispositivo não pode ser feito automaticamente pelo proprietário do dispositivo, a menos que esse utilizador tenha a função de "administrador global" ou "administrador de dispositivos" atribuída no portal Azure.</span><span class="sxs-lookup"><span data-stu-id="66bff-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="66bff-120">Para mais informações, consulte a nota abaixo.</span><span class="sxs-lookup"><span data-stu-id="66bff-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="66bff-121">Quando um utilizador é promovido a proprietário do UX de definições por outro Proprietário no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66bff-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="66bff-122">Se o proprietário do dispositivo já não estiver disponível (sai da empresa) e o dispositivo for a aderido ao Azure AD, o Administrador Inquilino pode mudar o proprietário do dispositivo para um novo utilizador no portal Azure.</span><span class="sxs-lookup"><span data-stu-id="66bff-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="66bff-123">Os Administradores Globais e Administradores de Dispositivos de um inquilino AZURE AD são implicitamente inscritos como Proprietários no dispositivo sem exigir qualquer um dos passos anteriores.</span><span class="sxs-lookup"><span data-stu-id="66bff-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="66bff-124">Os administradores de TI podem gerir o que as aplicações podem aceder através das políticas [de Privacidade.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy)</span><span class="sxs-lookup"><span data-stu-id="66bff-124">IT administrators can manage what apps can access through [Privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="66bff-125">Para saber mais sobre quem é o proprietário de um dispositivo de ação AD Azure, consulte [a documentação "Atribuir a Administração Local"](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (mas leia "administrador local" como "proprietário de dispositivos" uma vez que a administração não existe no HoloLens).</span><span class="sxs-lookup"><span data-stu-id="66bff-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>