---
title: Acesso Global Atribuído
description: Começa com o nosso guia para usar o OMA-URI para quiosques de acesso atribuído global com intune e designer de configuração de janelas.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, acesso atribuído, quiosque
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b86d88c7487043c6fcb057f03f353a57e44ef781
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379914"
---
# <a name="global-assigned-access--kiosk"></a><span data-ttu-id="07e61-104">Acesso Global Atribuído - Quiosque</span><span class="sxs-lookup"><span data-stu-id="07e61-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="07e61-105">Esta funcionalidade configura o dispositivo HoloLens 2 para o modo de quiosque de várias aplicações, que é aplicável a nível do sistema, não possui qualquer afinidade com qualquer identidade no sistema e aplica-se a todos os que assinam no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07e61-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="07e61-106">Atualmente esta funcionalidade apenas se encontra disponível nas criações do Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="07e61-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="07e61-107">Se quiser experimentar esta funcionalidade antes de estar disponível geralmente nas versões hololens, leia mais sobre as construções [do Windows Insider.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="07e61-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <a name="how-to-use-global-assigned-access-in-intune"></a><span data-ttu-id="07e61-108">Como utilizar o Acesso Global Atribuído em Intune?</span><span class="sxs-lookup"><span data-stu-id="07e61-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="07e61-109">Por favor, esteja atento às áreas marcadas com "<!-".</span><span class="sxs-lookup"><span data-stu-id="07e61-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="07e61-110">Estas áreas exigirão que faça modificações com base nas suas preferências.</span><span class="sxs-lookup"><span data-stu-id="07e61-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="07e61-111">Crie um perfil de configuração de dispositivo OMA URI personalizado da seguinte forma e aplique-o no grupo de dispositivos HoloLens:</span><span class="sxs-lookup"><span data-stu-id="07e61-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="07e61-112">Valor URI: ./Dispositivo/Fornecedor/MSFT/AtribuiçãoAccess/Configuração</span><span class="sxs-lookup"><span data-stu-id="07e61-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="07e61-113">![Acesso Global Atribuído OMA-URI em Intune](images/global-assigned-access-omauri.png)</span><span class="sxs-lookup"><span data-stu-id="07e61-113">![Global Assigned Access OMA-URI in Intune](images/global-assigned-access-omauri.png)</span></span>

2. <span data-ttu-id="07e61-114">Para valor, atualização e pasta de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="07e61-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a><span data-ttu-id="07e61-115">Como utilizar o Global Assigned Access no Windows Configuration Designer?</span><span class="sxs-lookup"><span data-stu-id="07e61-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="07e61-116">Atualize e guarde a bolha XML acima mencionada como ficheiro XML.</span><span class="sxs-lookup"><span data-stu-id="07e61-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="07e61-117">Siga os passos na [Utilização de um pacote de provisionamento para configurar um quiosque de aplicações únicas ou multi-aplicações](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), especificamente a secção "Prov.</span><span class="sxs-lookup"><span data-stu-id="07e61-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="07e61-118">pacote, passo 2 - Adicione o ficheiro XML de configuração de quiosque a um pacote de provisionamento" e consulte o ficheiro XML que foi guardado no passo anterior.</span><span class="sxs-lookup"><span data-stu-id="07e61-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a><span data-ttu-id="07e61-119">Posso criar uma configuração em que o global se aplica a todos e a configuração separada se aplica a 1 conta AD Azure ou grupo AD Azure?</span><span class="sxs-lookup"><span data-stu-id="07e61-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="07e61-120">Sim, consulte o exemplo de bolha XML abaixo.</span><span class="sxs-lookup"><span data-stu-id="07e61-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="07e61-121">O perfil de Acesso Atribuído Global é aplicado em HoloLens quando não é encontrado um específico para o utilizador assinado no utilizador, pelo que é a configuração padrão do modo de quiosque para o utilizador inscrito.</span><span class="sxs-lookup"><span data-stu-id="07e61-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="07e61-122">Aqui está um exemplo de bolha XML a ser usado:</span><span class="sxs-lookup"><span data-stu-id="07e61-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="07e61-123">Por favor, esteja atento às áreas destacadas com `<!-` .</span><span class="sxs-lookup"><span data-stu-id="07e61-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="07e61-124">Estas áreas exigirão que faça modificações com base nas suas preferências.</span><span class="sxs-lookup"><span data-stu-id="07e61-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a><span data-ttu-id="07e61-125">Excluindo os DeviceOwners do Perfil de Acesso Global Atribuído</span><span class="sxs-lookup"><span data-stu-id="07e61-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="07e61-126">Esta funcionalidade permite que um utilizador considerado "[Proprietário do Dispositivo](security-adminless-os.md)" em HoloLens seja excluído do Global Assigned Access.</span><span class="sxs-lookup"><span data-stu-id="07e61-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="07e61-127">Para tirar partido desta funcionalidade, na bolha XML para configuração de quiosque de várias aplicações, certifique-se de que são adicionadas linhas destacadas:</span><span class="sxs-lookup"><span data-stu-id="07e61-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a><span data-ttu-id="07e61-128">Exemplos adicionais de acesso atribuídos globalmente</span><span class="sxs-lookup"><span data-stu-id="07e61-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="07e61-129">Este é um exemplo do quiosque global de acesso atribuído que quando qualquer utilizador assina, terá um quiosque multi-aplicações com a App de Definições, Feedback Hub e Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="07e61-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="07e61-130">Este exemplo é um quiosque de Acesso Atribuído Global que exclui o proprietário do dispositivo, quando qualquer outro utilizador AZure AD assina em que terá um quiosque multi-aplicações com a App de Definições, Feedback Hub e Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="07e61-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="07e61-131">Este quiosque também inclui uma configuração de quiosque secundário para uma conta do Visitante, que pode ser assinada por qualquer pessoa no ecrã de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="07e61-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="07e61-132">Quando um utilizador assina na conta do Visitante, terá um quiosque multi-aplicações que só tem a aplicação Feedback Hub.</span><span class="sxs-lookup"><span data-stu-id="07e61-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
