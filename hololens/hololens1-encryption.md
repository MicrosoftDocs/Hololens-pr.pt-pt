---
title: HoloLens Encriptação BitLocker
description: Saiba como ativar a encriptação do dispositivo BitLocker para proteger ficheiros armazenados nos seus HoloLens dispositivos de realidade mista.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635250"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="147d6-103">encriptação bitLocker HoloLens (1ª Gen)</span><span class="sxs-lookup"><span data-stu-id="147d6-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="147d6-104">HoloLens (1º gênero) e HoloLens 2 ambos suportam encriptação do dispositivo usando BitLocker, no entanto, o BitLocker está sempre ativado no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="147d6-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="147d6-105">Este artigo irá ajudá-lo a ativar e gerir o BitLocker em HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="147d6-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="147d6-106">No HoloLens (1º gênero) pode ativar a encriptação do dispositivo BitLocker manualmente ou utilizar a gestão de dispositivos móveis (MDM).</span><span class="sxs-lookup"><span data-stu-id="147d6-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="147d6-107">Siga estas instruções para permitir a [encriptação do dispositivo BitLocker](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) para proteger ficheiros e informações armazenados no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="147d6-107">Follow these instructions to enable [BitLocker device encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="147d6-108">A encriptação do dispositivo ajuda a proteger os seus dados utilizando o método de encriptação AES-CBC 128, que é equivalente ao [método 3 do Método EncryptionMethodByDriveType](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) no fornecedor de serviços de configuração BitLocker (CSP).</span><span class="sxs-lookup"><span data-stu-id="147d6-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="147d6-109">O pessoal que tiver a chave de encriptação correta (como uma palavra-passe) pode desencriptar ou efetuar uma recuperação de dados.</span><span class="sxs-lookup"><span data-stu-id="147d6-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="147d6-110">Ativar a encriptação do dispositivo usando o MDM</span><span class="sxs-lookup"><span data-stu-id="147d6-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="147d6-111">Pode utilizar o seu fornecedor de Gestão de Dispositivos Móveis (MDM) para aplicar uma política que exija encriptação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="147d6-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="147d6-112">A política a utilizar é a [definição de Segurança/RequerDeviceEncrição](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) na Política CSP.</span><span class="sxs-lookup"><span data-stu-id="147d6-112">The policy to use is the [Security/RequireDeviceEncryption setting](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="147d6-113">Consulte as instruções para ativar a encriptação do dispositivo utilizando Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="147d6-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="147d6-114">Para outras ferramentas DEDM, consulte a documentação do seu fornecedor de MDM para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="147d6-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="147d6-115">Se o seu fornecedor DEMS necessitar de URI personalizado para encriptação do dispositivo, utilize a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="147d6-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="147d6-116">**Nome**: um nome à sua escolha</span><span class="sxs-lookup"><span data-stu-id="147d6-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="147d6-117">**Descrição**: opcional</span><span class="sxs-lookup"><span data-stu-id="147d6-117">**Description**: optional</span></span>
- <span data-ttu-id="147d6-118">**OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="147d6-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="147d6-119">Tipo de **dados**: inteiro</span><span class="sxs-lookup"><span data-stu-id="147d6-119">**Data type**: integer</span></span>
- <span data-ttu-id="147d6-120">**Valor:**`1`</span><span class="sxs-lookup"><span data-stu-id="147d6-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="147d6-121">Ativar a encriptação do dispositivo utilizando um pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="147d6-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="147d6-122">Os pacotes de provisionamento são ficheiros criados pela ferramenta Windows Configuration Designer que aplicam uma configuração especificada a um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="147d6-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="147d6-123">Crie um pacote de provisionamento que atualize a edição holográfica Windows e permita encriptação</span><span class="sxs-lookup"><span data-stu-id="147d6-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="147d6-124">Crie um pacote de provisionamento para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="147d6-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="147d6-125">Vá para **configurações de tempo de**  >    >  **execução Segurança** políticas e selecione **RequireDeviceEncryption**.</span><span class="sxs-lookup"><span data-stu-id="147d6-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Requerer a configuração de encriptação do dispositivo configurado para sim](images/device-encryption.png)

1. <span data-ttu-id="147d6-127">Encontre o ficheiro de licença XML que foi fornecido quando adquiriu a Suite Comercial.</span><span class="sxs-lookup"><span data-stu-id="147d6-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="147d6-128">Navegue e selecione o ficheiro de licença XML que foi fornecido quando adquiriu a Suite Comercial.</span><span class="sxs-lookup"><span data-stu-id="147d6-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="147d6-129">Pode configurar [definições adicionais no pacote de provisionamento](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="147d6-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="147d6-130">No menu **Ficheiro**, clique em **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="147d6-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="147d6-131">Leia o aviso explicando que os ficheiros do projeto podem conter informações sensíveis e clicar **em OK**.</span><span class="sxs-lookup"><span data-stu-id="147d6-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="147d6-132">Ao construir um pacote de provisionamento, poderá incluir informações sensíveis nos ficheiros do projeto e no ficheiro do pacote de provisionamento (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="147d6-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="147d6-133">Embora tenha a opção de encriptar o ficheiro .ppkg, os ficheiros do projeto não estão encriptados.</span><span class="sxs-lookup"><span data-stu-id="147d6-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="147d6-134">Deve armazenar os ficheiros do projeto num local seguro e eliminar os ficheiros do projeto quando já não for necessário.</span><span class="sxs-lookup"><span data-stu-id="147d6-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="147d6-135">No menu **Exportação,** clique no **pacote De provisionamento.**</span><span class="sxs-lookup"><span data-stu-id="147d6-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="147d6-136">Alterar **Proprietário** para **IT Admin,** que definirá a precedência deste pacote de provisionamento superior ao que os pacotes de provisionamento aplicados a este dispositivo a partir de outras fontes, e, em seguida, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="147d6-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="147d6-137">Desa estação de valor para **a versão pacote**.</span><span class="sxs-lookup"><span data-stu-id="147d6-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="147d6-138">Pode escoar alterações nos pacotes existentes e alterar o número da versão para atualizar pacotes previamente aplicados.</span><span class="sxs-lookup"><span data-stu-id="147d6-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="147d6-139">Nos **detalhes de segurança Select para o pacote de provisionamento,** clique em **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="147d6-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="147d6-140">Clique em **seguida** para especificar o local de saída onde deseja que o pacote de provisionamento vá assim que for construído.</span><span class="sxs-lookup"><span data-stu-id="147d6-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="147d6-141">Por predefinição, Windows ICD utiliza a pasta do projeto como localização de saída.</span><span class="sxs-lookup"><span data-stu-id="147d6-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="147d6-142">Opcionalmente, pode clicar em navegar para alterar o local de saída predefinido.</span><span class="sxs-lookup"><span data-stu-id="147d6-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="147d6-143">Clique em **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="147d6-143">Click **Next**.</span></span>
1. <span data-ttu-id="147d6-144">Clique **em Build** para começar a construir o pacote.</span><span class="sxs-lookup"><span data-stu-id="147d6-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="147d6-145">A informação do projeto é exibida na página de construção e a barra de progresso indica o estado de construção.</span><span class="sxs-lookup"><span data-stu-id="147d6-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="147d6-146">Quando a construção estiver concluída, clique em **Terminar**.</span><span class="sxs-lookup"><span data-stu-id="147d6-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="147d6-147">Aplicar o pacote de provisionamento à HoloLens</span><span class="sxs-lookup"><span data-stu-id="147d6-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="147d6-148">Ligação o dispositivo via USB para um PC e inicie o dispositivo, mas não continue além da página **de ajuste** da experiência inicial de configuração (a primeira página com a caixa azul).</span><span class="sxs-lookup"><span data-stu-id="147d6-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="147d6-149">Pressione e solte brevemente os botões **Volume Down** e **Power** simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="147d6-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="147d6-150">HoloLens aparecerão como um dispositivo no Explorador de Ficheiros no PC.</span><span class="sxs-lookup"><span data-stu-id="147d6-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="147d6-151">No File Explorer, arraste e deixe cair o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="147d6-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="147d6-152">Prima e solte brevemente os botões **Volume Down** e **Power** simultaneamente enquanto estiver na página **de ajuste.**</span><span class="sxs-lookup"><span data-stu-id="147d6-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="147d6-153">O dispositivo irá perguntar-lhe se confia no pacote e gostaria de aplicá-lo.</span><span class="sxs-lookup"><span data-stu-id="147d6-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="147d6-154">Confirme que confia no pacote.</span><span class="sxs-lookup"><span data-stu-id="147d6-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="147d6-155">Verá se o pacote foi aplicado com sucesso ou não.</span><span class="sxs-lookup"><span data-stu-id="147d6-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="147d6-156">Se falhar, pode consertar o seu pacote e tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="147d6-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="147d6-157">Se tiver sido bem sucedido, proceda com a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="147d6-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="147d6-158">Se o dispositivo foi adquirido antes de agosto de 2016, terá de iniciar sedutar no dispositivo com uma conta Microsoft, receber a mais recente atualização de SO e, em seguida, redefinir o SISTEMA para aplicar o pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="147d6-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="147d6-159">Verificar encriptação do dispositivo</span><span class="sxs-lookup"><span data-stu-id="147d6-159">Verify device encryption</span></span>

<span data-ttu-id="147d6-160">A encriptação é silenciosa na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="147d6-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="147d6-161">Para verificar o estado de encriptação do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="147d6-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="147d6-162">No HoloLens, vá ao **Definições**  >  **System**  >  **About.**</span><span class="sxs-lookup"><span data-stu-id="147d6-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="147d6-163">**O BitLocker** **está ativado** se o dispositivo estiver encriptado.</span><span class="sxs-lookup"><span data-stu-id="147d6-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Sobre o ecrã mostrando BitLocker ativado](images/about-encryption.png)
