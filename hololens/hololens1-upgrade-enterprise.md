---
title: Desbloqueie as funcionalidades Holográficas do Windows para negócios
description: Ao fazer o upgrade para o Windows Holographic for Business, o HoloLens fornece funcionalidades extra que são projetadas para o negócio.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378578"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="49bcc-103">Desbloqueie as funcionalidades Holográficas do Windows para negócios</span><span class="sxs-lookup"><span data-stu-id="49bcc-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49bcc-104">Esta página aplica-se apenas ao HoloLens 1st Gen.</span><span class="sxs-lookup"><span data-stu-id="49bcc-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="49bcc-105">O Microsoft HoloLens está disponível na *Development Edition*, que executa o Windows Holographic (uma edição do Windows 10 que é projetado para HoloLens) e na [Suite Comercial](hololens-commercial-features.md), que fornece funcionalidades extra desenhadas para o negócio.</span><span class="sxs-lookup"><span data-stu-id="49bcc-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="49bcc-106">Ao adquirir a Suite Comercial, recebe uma licença que atualiza o Windows Holographic para o Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="49bcc-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="49bcc-107">Pode aplicar esta licença ao dispositivo, utilizando o fornecedor de gestão de [dispositivos móveis (MDM)](#edition-upgrade-by-using-mdm) da organização ou um [pacote de provisionamento.](#edition-upgrade-by-using-a-provisioning-package)</span><span class="sxs-lookup"><span data-stu-id="49bcc-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="49bcc-108">No Windows 10, versão 1803, pode verificar se os HoloLens foram atualizados para a edição de negócios selecionando o **Sistema de Definições**  >  .</span><span class="sxs-lookup"><span data-stu-id="49bcc-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="49bcc-109">Upgrade de edição usando MDM</span><span class="sxs-lookup"><span data-stu-id="49bcc-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="49bcc-110">A licença da empresa pode ser aplicada por qualquer fornecedor de MDM que suporte o [prestador de serviços de configuração WindowsLicensing (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span><span class="sxs-lookup"><span data-stu-id="49bcc-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="49bcc-111">A versão mais recente da API do Microsoft MDM irá suportar o WindowsLicensing CSP.</span><span class="sxs-lookup"><span data-stu-id="49bcc-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="49bcc-112">Para obter instruções passo a passo para atualizar hololens utilizando o Microsoft Intune, consulte [os dispositivos de upgrade que executam o Windows Holographic para Windows Holographic para o Negócios](https://docs.microsoft.com/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="49bcc-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="49bcc-113">Em outros fornecedores de MDM, as medidas específicas para a criação e implementação da política podem variar.</span><span class="sxs-lookup"><span data-stu-id="49bcc-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="49bcc-114">Upgrade de edição usando um pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="49bcc-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="49bcc-115">Os pacotes de provisionamento são ficheiros criados pela ferramenta Design de Configuração do Windows que aplicam uma configuração especificada a um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49bcc-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="49bcc-116">Crie um pacote de provisionamento que atualize a edição holográfica do Windows</span><span class="sxs-lookup"><span data-stu-id="49bcc-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="49bcc-117">Crie um pacote de provisões para hololens.</span><span class="sxs-lookup"><span data-stu-id="49bcc-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="49bcc-118">Vá às **definições de tempo de**  >  **execução EditionUpgrade** e selecione **EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="49bcc-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Edição de upgrade com definição de licença selecionada](images/icd1.png)

1. <span data-ttu-id="49bcc-120">Encontre o ficheiro de licença XML que foi fornecido quando adquiriu a Suite Comercial.</span><span class="sxs-lookup"><span data-stu-id="49bcc-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="49bcc-121">Pode configurar [definições adicionais no pacote de provisionamento](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="49bcc-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="49bcc-122">No menu **File** (Ficheiro), selecione **Save** (Guardar).</span><span class="sxs-lookup"><span data-stu-id="49bcc-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="49bcc-123">Leia o aviso de que os ficheiros do projeto podem conter informações sensíveis e clicar **em OK**.</span><span class="sxs-lookup"><span data-stu-id="49bcc-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="49bcc-124">Ao construir um pacote de provisionamento, poderá incluir informações sensíveis nos ficheiros do projeto e no ficheiro do pacote de provisionamento (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="49bcc-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="49bcc-125">Embora tenha a opção de encriptar o ficheiro .ppkg, os ficheiros do projeto não estão encriptados.</span><span class="sxs-lookup"><span data-stu-id="49bcc-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="49bcc-126">Deve armazenar os ficheiros do projeto num local seguro e eliminar os ficheiros do projeto quando já não for necessário.</span><span class="sxs-lookup"><span data-stu-id="49bcc-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="49bcc-127">No menu **Exportar,** selecione **Pacote de Provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="49bcc-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="49bcc-128">Alterar **Proprietário** para **IT Admin,** que define a precedência deste pacote de provisionamento para ser superior a outros aplicados a este dispositivo de diferentes fontes, e, em seguida, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="49bcc-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="49bcc-129">Desa estação de valor para **a versão pacote**.</span><span class="sxs-lookup"><span data-stu-id="49bcc-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="49bcc-130">Pode escoar alterações nos pacotes existentes e alterar o número da versão para atualizar pacotes previamente aplicados.</span><span class="sxs-lookup"><span data-stu-id="49bcc-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="49bcc-131">Em **Detalhes de segurança selecionados para o pacote de provisionamento**, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="49bcc-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="49bcc-132">Selecione **Next** para especificar o local de saída onde deseja que o pacote de provisionamento vá assim que for construído.</span><span class="sxs-lookup"><span data-stu-id="49bcc-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="49bcc-133">Por predefinição, o Windows ICD utiliza a pasta do projeto como localização de saída.</span><span class="sxs-lookup"><span data-stu-id="49bcc-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="49bcc-134">Opcionalmente, pode selecionar **procurar** para alterar o local de saída predefinido.</span><span class="sxs-lookup"><span data-stu-id="49bcc-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="49bcc-135">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="49bcc-135">Select **Next**.</span></span>

1. <span data-ttu-id="49bcc-136">Selecione **Build** para começar a construir o pacote.</span><span class="sxs-lookup"><span data-stu-id="49bcc-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="49bcc-137">A página de construção exibe a informação do projeto, e a barra de progresso indica o estado de construção.</span><span class="sxs-lookup"><span data-stu-id="49bcc-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="49bcc-138">Quando a construção terminar, **selecione Acabamento**.</span><span class="sxs-lookup"><span data-stu-id="49bcc-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="49bcc-139">Aplicar o pacote de provisionamento aos HoloLens</span><span class="sxs-lookup"><span data-stu-id="49bcc-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="49bcc-140">Utilizando o cabo USB, ligue o dispositivo a um PC.</span><span class="sxs-lookup"><span data-stu-id="49bcc-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="49bcc-141">Inicie o dispositivo, mas não continue além da página **de ajuste** da experiência inicial de configuração (a primeira página com a caixa azul).</span><span class="sxs-lookup"><span data-stu-id="49bcc-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="49bcc-142">No PC, holoLens aparece como um dispositivo no File Explorer.</span><span class="sxs-lookup"><span data-stu-id="49bcc-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="49bcc-143">Se o dispositivo HoloLens estiver a executar o Windows 10, versão 1607 ou mais cedo, abra o File Explorer premindo e libertando simultaneamente os botões **Volume Down** e **Power** no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49bcc-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="49bcc-144">No File Explorer, arraste e deixe cair o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49bcc-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="49bcc-145">Enquanto holoLens ainda estiver na página **de ajuste,** prima e solte brevemente os botões **Volume Down** e **Power** simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="49bcc-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="49bcc-146">O HoloLens pergunta-lhe se confia no pacote e gostaria de aplicá-lo.</span><span class="sxs-lookup"><span data-stu-id="49bcc-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="49bcc-147">Confirme que confia no pacote.</span><span class="sxs-lookup"><span data-stu-id="49bcc-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="49bcc-148">Verá se o pacote foi aplicado com sucesso ou não.</span><span class="sxs-lookup"><span data-stu-id="49bcc-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="49bcc-149">Se não foi aplicado com sucesso, pode consertar a sua encomenda e tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="49bcc-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="49bcc-150">Se for bem sucedido, proceda à configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49bcc-150">If successful, proceed with device setup.</span></span>
