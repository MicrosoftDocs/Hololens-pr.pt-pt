---
title: Inscreva-se HoloLens no MDM
description: Saiba como inscrever HoloLens na gestão de dispositivos móveis (MDM) para uma gestão mais fácil de vários dispositivos.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640411"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="6ce81-103">Inscreva-se HoloLens no MDM</span><span class="sxs-lookup"><span data-stu-id="6ce81-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="6ce81-104">Pode gerir vários dispositivos de Microsoft HoloLens simultaneamente utilizando soluções como [Microsoft Intune](/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="6ce81-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="6ce81-105">Poderá gerir as definições, selecionar aplicações para instalar e definir configurações de segurança adaptadas às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6ce81-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="6ce81-106">Consulte [gerir os dispositivos em execução Windows Holográfico com Microsoft Intune,](/intune/windows-holographic-for-business) [os prestadores de serviços de configuração (CSPs) que são suportados em Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), e as [políticas apoiadas por Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="6ce81-106">See [Manage devices running Windows Holographic with Microsoft Intune](/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="6ce81-107">A gestão de dispositivos móveis (MDM), incluindo as funcionalidades do modo VPN, Bitlocker e modo quiosque, só está disponível quando [fizer o upgrade para Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6ce81-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="6ce81-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ce81-108">Requirements</span></span>

 <span data-ttu-id="6ce81-109">A sua organização terá de ter a Gestão de Dispositivos Móveis (MDM) configurada para gerir HoloLens dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6ce81-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="6ce81-110">O seu fornecedor DEM pode ser Microsoft Intune ou um fornecedor de terceiros que utiliza APIs do Microsoft MDM.</span><span class="sxs-lookup"><span data-stu-id="6ce81-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="6ce81-111">Diferentes formas de se inscrever</span><span class="sxs-lookup"><span data-stu-id="6ce81-111">Different ways to enroll</span></span>

<span data-ttu-id="6ce81-112">Dependendo do tipo de [identidade](hololens-identity.md) escolhida durante o OOBE ou pós-in, existem diferentes métodos de inscrição.</span><span class="sxs-lookup"><span data-stu-id="6ce81-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="6ce81-113">Se a identidade for Azure AD, então durante o OOBE ou Definições o botão de acesso à **aplicação**  ->  **ou**  ->  **Ligação** escolar.</span><span class="sxs-lookup"><span data-stu-id="6ce81-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="6ce81-114">Para a Azure AD, [a inscrição automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) só ocorre se a Azure AD tiver sido configurada com URLs de inscrição.</span><span class="sxs-lookup"><span data-stu-id="6ce81-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="6ce81-115">Se a Identidade for AZure AD e o dispositivo tiver sido pré-registado no servidor INtune MDM com perfil de configuração específico atribuído a ele, então a Azure AD-Join e [a inscrição automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) ocorrerão durante o OOBE.</span><span class="sxs-lookup"><span data-stu-id="6ce81-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="6ce81-116">Também chamado [de fluxo autopiloto](hololens2-autopilot.md) Disponível em [19041.1103+ constrói.](hololens-release-notes.md#windows-holographic-version-2004)</span><span class="sxs-lookup"><span data-stu-id="6ce81-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="6ce81-117">Se a identidade for MSA, então utilize Definições o trabalho de acesso à **aplicação**  ->  ou o botão de Ligação **escolar.**  ->  </span><span class="sxs-lookup"><span data-stu-id="6ce81-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="6ce81-118">Também chamado fluxo de Conta de Trabalho Adicionar (AWA).</span><span class="sxs-lookup"><span data-stu-id="6ce81-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="6ce81-119">Se a Identidade for Utilizador Local, então utilize Definições Trabalho de Acesso à **Aplicação**  ->  **ou Inscrição escolar**  ->  apenas no link de **gestão de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="6ce81-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="6ce81-120">Também chamado fluxo de inscrição de MDM puro.</span><span class="sxs-lookup"><span data-stu-id="6ce81-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="6ce81-121">Uma vez que o dispositivo esteja matriculado com o seu servidor MDM, a aplicação Definições irá agora refletir que o dispositivo está inscrito na gestão do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6ce81-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="6ce81-122">Inscrição automática em MDM</span><span class="sxs-lookup"><span data-stu-id="6ce81-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="6ce81-123">Se a sua organização tiver uma [subscrição Azure Premium,](https://azure.microsoft.com/overview/)está a utilizar Azure Ative Directory (Azure AD) e uma solução MDM que aceita um token AD Azure para autenticação (atualmente, apenas suportado em Microsoft Intune e AirWatch), o seu administrador de TI pode configurar a Azure AD para permitir automaticamente a inscrição do MDM após o utilizador assinar com a sua conta Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6ce81-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="6ce81-124">Saiba como configurar a inscrição em Ad Azure.</span><span class="sxs-lookup"><span data-stu-id="6ce81-124">Learn how to configure Azure AD enrollment.</span></span>](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="6ce81-125">Quando a inscrição automática está ativada, não é necessária nenhuma inscrição manual extra.</span><span class="sxs-lookup"><span data-stu-id="6ce81-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="6ce81-126">Quando o utilizador assina com uma conta AD Azure, o dispositivo é matriculado em MDM após completar a experiência de primeira execução.</span><span class="sxs-lookup"><span data-stu-id="6ce81-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="6ce81-127">Quando um dispositivo é Azure AD AD Se junta, pode afetar quem considerou o proprietário do [dispositivo](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="6ce81-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="6ce81-128">Unenroll HoloLens de Intune</span><span class="sxs-lookup"><span data-stu-id="6ce81-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="6ce81-129">Dependendo do método de inscrição, a não inscrição do seu dispositivo pode não estar disponível.</span><span class="sxs-lookup"><span data-stu-id="6ce81-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="6ce81-130">Se o seu dispositivo foi matriculado com uma conta AD Azure ou Autopilot, não pode ser desenrolado a partir de Intune.</span><span class="sxs-lookup"><span data-stu-id="6ce81-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="6ce81-131">Se desejar desacompra HoloLens da Azure AD ou voltar a juntar-se a um inquilino diferente do AD AZure, tem de [reiniciar/reflash](hololens-recovery.md#reset-the-device) o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6ce81-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](hololens-recovery.md#reset-the-device) the device.</span></span>

<span data-ttu-id="6ce81-132">Se o seu dispositivo foi matriculado a partir de uma conta MSA que adicionou uma conta de trabalho ou de uma conta Local que se inscreveu apenas na gestão do dispositivo, então pode desacordá-lo.</span><span class="sxs-lookup"><span data-stu-id="6ce81-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="6ce81-133">Abra a menu Iniciar e, em seguida, selecione Definições o "Trabalho de Acesso à **Aplicação"**  ->  ou o botão **"Desligar a Contagem**  ->    ->   escolar".</span><span class="sxs-lookup"><span data-stu-id="6ce81-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>