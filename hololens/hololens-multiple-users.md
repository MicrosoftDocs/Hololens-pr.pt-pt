---
title: Partilhe os seus HoloLens com várias pessoas
description: Pode configurar holoLens para ser partilhado por várias contas do Azure Ative Directory ou por vários utilizadores que usam uma única conta.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378594"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="55443-103">Partilhe os seus HoloLens com várias pessoas</span><span class="sxs-lookup"><span data-stu-id="55443-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="55443-104">É comum partilhar um HoloLens com muitas pessoas ou ter muitas pessoas a partilhar um conjunto de dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55443-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="55443-105">Este artigo descreve as diferentes formas de partilhar um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="55443-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="55443-106">Partilhe com várias pessoas, cada uma usando a sua própria conta</span><span class="sxs-lookup"><span data-stu-id="55443-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="55443-107">**Pré-requisito**: O dispositivo HoloLens deve estar a executar o Windows 10, versão 1803 ou mais tarde.</span><span class="sxs-lookup"><span data-stu-id="55443-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="55443-108">HoloLens (1º gênero) também precisa de ser [atualizado para Windows Holographic for Business](hololens-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="55443-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="55443-109">Quando utilizam as suas próprias contas Azure Ative Directory (Azure AD), vários utilizadores podem manter as suas próprias definições de utilizador e dados do utilizador no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="55443-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="55443-110">Para garantir que várias pessoas possam usar as suas próprias contas nos seus HoloLens, siga estes passos para configurar:</span><span class="sxs-lookup"><span data-stu-id="55443-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="55443-111">Certifique-se de que o dispositivo está a executar o Windows 10, versão 1803 ou mais tarde.</span><span class="sxs-lookup"><span data-stu-id="55443-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="55443-112">Se estiver a utilizar um dispositivo HoloLens (1ª geração), [atualize o dispositivo para Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="55443-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="55443-113">Quando configurar o dispositivo, selecione O meu trabalho ou escola é dono dele e **inscreva-se** utilizando uma conta AD Azure.</span><span class="sxs-lookup"><span data-stu-id="55443-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="55443-114">Depois de terminar a configuração, certifique-se de que as definições da conta **(Contas de Definições)**  >  incluem **outros** **utilizadores**.</span><span class="sxs-lookup"><span data-stu-id="55443-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="55443-115">Para utilizar hololens, cada utilizador segue estes passos:</span><span class="sxs-lookup"><span data-stu-id="55443-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="55443-116">Se outro utilizador tiver usado o dispositivo, faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="55443-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="55443-117">Pressione o botão de alimentação uma vez para ir para o standby e, em seguida, pressione o botão de alimentação novamente para voltar ao ecrã de bloqueio</span><span class="sxs-lookup"><span data-stu-id="55443-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="55443-118">Os utilizadores do HoloLens 2 podem selecionar o azulejo do utilizador a partir do menu Iniciar para assinar o utilizador atual.</span><span class="sxs-lookup"><span data-stu-id="55443-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="55443-119">Utilize as suas credenciais de conta AZure AD para iniciar scontabilidade no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="55443-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="55443-120">Se esta é a primeira vez que usas o dispositivo, tens de [calibrar](hololens-calibration.md) os HoloLens aos teus próprios olhos.</span><span class="sxs-lookup"><span data-stu-id="55443-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="55443-121">Para ver uma lista dos utilizadores do dispositivo ou para remover um utilizador do dispositivo, aceda a **Contas de Definições**  >    >  **Outros utilizadores**.</span><span class="sxs-lookup"><span data-stu-id="55443-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="55443-122">Partilhar com várias pessoas, todos usando a mesma conta</span><span class="sxs-lookup"><span data-stu-id="55443-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="55443-123">Vários utilizadores também podem partilhar um dispositivo HoloLens enquanto utilizam uma única conta de utilizador.</span><span class="sxs-lookup"><span data-stu-id="55443-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="55443-124">**No HoloLens 2**, quando um novo utilizador coloca o dispositivo na cabeça pela primeira vez (mantendo a mesma conta assinada), o dispositivo solicita ao novo utilizador que calibra e personalize rapidamente a experiência de visualização.</span><span class="sxs-lookup"><span data-stu-id="55443-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="55443-125">O dispositivo pode armazenar a informação de calibração para que, no futuro, o dispositivo possa otimizar automaticamente a qualidade e o conforto da experiência de visualização de cada utilizador.</span><span class="sxs-lookup"><span data-stu-id="55443-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="55443-126">Os utilizadores não precisam de voltar a calibrar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="55443-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="55443-127">**No HoloLens (1º género)** os utilizadores que partilham uma conta terão de pedir para recalibrar na aplicação Definições.</span><span class="sxs-lookup"><span data-stu-id="55443-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="55443-128">Leia mais sobre [a calibração.](hololens-calibration.md)</span><span class="sxs-lookup"><span data-stu-id="55443-128">Read more about [calibration](hololens-calibration.md).</span></span>
