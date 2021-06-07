---
title: Encriptação HoloLens BitLocker
description: Saiba como ativar a encriptação do dispositivo BitLocker para proteger ficheiros armazenados nos seus dispositivos de realidade mista HoloLens.
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
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378474"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="2eb21-103">Encriptação Do HoloLens (1ª Gen) BitLocker</span><span class="sxs-lookup"><span data-stu-id="2eb21-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="2eb21-104">HoloLens (1º gênero) e HoloLens 2 ambos suportam encriptação do dispositivo usando BitLocker, no entanto, BitLocker está sempre ativado em HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2eb21-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="2eb21-105">Este artigo irá ajudá-lo a ativar e gerir o BitLocker no HoloLens (1º género).</span><span class="sxs-lookup"><span data-stu-id="2eb21-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="2eb21-106">No HoloLens (1º gênero) pode ativar a encriptação do dispositivo BitLocker manualmente ou utilizar a gestão de dispositivos móveis (MDM).</span><span class="sxs-lookup"><span data-stu-id="2eb21-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="2eb21-107">Siga estas instruções para permitir a [encriptação do dispositivo BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) para proteger ficheiros e informações armazenados nos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2eb21-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="2eb21-108">A encriptação do dispositivo ajuda a proteger os seus dados utilizando o método de encriptação AES-CBC 128, que é equivalente ao [método 3 do Método EncryptionMethodByDriveType](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) no fornecedor de serviços de configuração BitLocker (CSP).</span><span class="sxs-lookup"><span data-stu-id="2eb21-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="2eb21-109">O pessoal que tiver a chave de encriptação correta (como uma palavra-passe) pode desencriptar ou efetuar uma recuperação de dados.</span><span class="sxs-lookup"><span data-stu-id="2eb21-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="2eb21-110">Ativar a encriptação do dispositivo usando o MDM</span><span class="sxs-lookup"><span data-stu-id="2eb21-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="2eb21-111">Pode utilizar o seu fornecedor de Gestão de Dispositivos Móveis (MDM) para aplicar uma política que exija encriptação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2eb21-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="2eb21-112">A política a utilizar é a [definição de Segurança/RequerDeviceEncrição](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) na Política CSP.</span><span class="sxs-lookup"><span data-stu-id="2eb21-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="2eb21-113">Consulte as instruções para ativar a encriptação do dispositivo utilizando o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="2eb21-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="2eb21-114">Para outras ferramentas DEDM, consulte a documentação do seu fornecedor de MDM para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="2eb21-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="2eb21-115">Se o seu fornecedor DEMS necessitar de URI personalizado para encriptação do dispositivo, utilize a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="2eb21-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="2eb21-116">**Nome**: um nome à sua escolha</span><span class="sxs-lookup"><span data-stu-id="2eb21-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="2eb21-117">**Descrição**: opcional</span><span class="sxs-lookup"><span data-stu-id="2eb21-117">**Description**: optional</span></span>
- <span data-ttu-id="2eb21-118">**OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="2eb21-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="2eb21-119">Tipo de **dados**: inteiro</span><span class="sxs-lookup"><span data-stu-id="2eb21-119">**Data type**: integer</span></span>
- <span data-ttu-id="2eb21-120">**Valor:**`1`</span><span class="sxs-lookup"><span data-stu-id="2eb21-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="2eb21-121">Ativar a encriptação do dispositivo utilizando um pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="2eb21-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="2eb21-122">Os pacotes de provisionamento são ficheiros criados pela ferramenta Design de Configuração do Windows que aplicam uma configuração especificada a um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2eb21-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="2eb21-123">Crie um pacote de provisionamento que atualize a edição holográfica do Windows e permita encriptação</span><span class="sxs-lookup"><span data-stu-id="2eb21-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="2eb21-124">Crie um pacote de provisões para hololens.</span><span class="sxs-lookup"><span data-stu-id="2eb21-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="2eb21-125">Vá para **configurações de tempo de**  >    >  **execução Segurança** políticas e selecione **RequireDeviceEncryption**.</span><span class="sxs-lookup"><span data-stu-id="2eb21-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Requerer a configuração de encriptação do dispositivo configurado para sim](images/device-encryption.png)

1. <span data-ttu-id="2eb21-127">Encontre o ficheiro de licença XML que foi fornecido quando adquiriu a Suite Comercial.</span><span class="sxs-lookup"><span data-stu-id="2eb21-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="2eb21-128">Navegue e selecione o ficheiro de licença XML que foi fornecido quando adquiriu a Suite Comercial.</span><span class="sxs-lookup"><span data-stu-id="2eb21-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="2eb21-129">Pode configurar [definições adicionais no pacote de provisionamento](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="2eb21-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="2eb21-130">No menu **Ficheiro**, clique em **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2eb21-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="2eb21-131">Leia o aviso explicando que os ficheiros do projeto podem conter informações sensíveis e clicar **em OK**.</span><span class="sxs-lookup"><span data-stu-id="2eb21-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2eb21-132">Ao construir um pacote de provisionamento, poderá incluir informações sensíveis nos ficheiros do projeto e no ficheiro do pacote de provisionamento (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="2eb21-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="2eb21-133">Embora tenha a opção de encriptar o ficheiro .ppkg, os ficheiros do projeto não estão encriptados.</span><span class="sxs-lookup"><span data-stu-id="2eb21-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="2eb21-134">Deve armazenar os ficheiros do projeto num local seguro e eliminar os ficheiros do projeto quando já não for necessário.</span><span class="sxs-lookup"><span data-stu-id="2eb21-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="2eb21-135">No menu **Exportação,** clique no **pacote De provisionamento.**</span><span class="sxs-lookup"><span data-stu-id="2eb21-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="2eb21-136">Alterar **Proprietário** para **IT Admin,** que definirá a precedência deste pacote de provisionamento superior ao que os pacotes de provisionamento aplicados a este dispositivo a partir de outras fontes, e, em seguida, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="2eb21-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="2eb21-137">Desa estação de valor para **a versão pacote**.</span><span class="sxs-lookup"><span data-stu-id="2eb21-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="2eb21-138">Pode escoar alterações nos pacotes existentes e alterar o número da versão para atualizar pacotes previamente aplicados.</span><span class="sxs-lookup"><span data-stu-id="2eb21-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="2eb21-139">Nos **detalhes de segurança Select para o pacote de provisionamento,** clique em **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="2eb21-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="2eb21-140">Clique em **seguida** para especificar o local de saída onde deseja que o pacote de provisionamento vá assim que for construído.</span><span class="sxs-lookup"><span data-stu-id="2eb21-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="2eb21-141">Por predefinição, o Windows ICD utiliza a pasta do projeto como localização de saída.</span><span class="sxs-lookup"><span data-stu-id="2eb21-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="2eb21-142">Opcionalmente, pode clicar em navegar para alterar o local de saída predefinido.</span><span class="sxs-lookup"><span data-stu-id="2eb21-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="2eb21-143">Clique em **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="2eb21-143">Click **Next**.</span></span>
1. <span data-ttu-id="2eb21-144">Clique **em Build** para começar a construir o pacote.</span><span class="sxs-lookup"><span data-stu-id="2eb21-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="2eb21-145">A informação do projeto é exibida na página de construção e a barra de progresso indica o estado de construção.</span><span class="sxs-lookup"><span data-stu-id="2eb21-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="2eb21-146">Quando a construção estiver concluída, clique em **Terminar**.</span><span class="sxs-lookup"><span data-stu-id="2eb21-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="2eb21-147">Aplicar o pacote de provisionamento aos HoloLens</span><span class="sxs-lookup"><span data-stu-id="2eb21-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="2eb21-148">Ligue o dispositivo via USB a um PC e inicie o dispositivo, mas não continue além da página **de ajuste** da experiência inicial de configuração (a primeira página com a caixa azul).</span><span class="sxs-lookup"><span data-stu-id="2eb21-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="2eb21-149">Pressione e solte brevemente os botões **Volume Down** e **Power** simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="2eb21-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="2eb21-150">Os HoloLens aparecerão como um dispositivo no File Explorer no PC.</span><span class="sxs-lookup"><span data-stu-id="2eb21-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="2eb21-151">No File Explorer, arraste e deixe cair o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2eb21-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="2eb21-152">Prima e solte brevemente os botões **Volume Down** e **Power** simultaneamente enquanto estiver na página **de ajuste.**</span><span class="sxs-lookup"><span data-stu-id="2eb21-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="2eb21-153">O dispositivo irá perguntar-lhe se confia no pacote e gostaria de aplicá-lo.</span><span class="sxs-lookup"><span data-stu-id="2eb21-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="2eb21-154">Confirme que confia no pacote.</span><span class="sxs-lookup"><span data-stu-id="2eb21-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="2eb21-155">Verá se o pacote foi aplicado com sucesso ou não.</span><span class="sxs-lookup"><span data-stu-id="2eb21-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="2eb21-156">Se falhar, pode consertar o seu pacote e tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="2eb21-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="2eb21-157">Se tiver sido bem sucedido, proceda com a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2eb21-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="2eb21-158">Se o dispositivo foi adquirido antes de agosto de 2016, terá de iniciar sedutar no dispositivo com uma conta Microsoft, receber a mais recente atualização de SO e, em seguida, redefinir o SISTEMA para aplicar o pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="2eb21-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="2eb21-159">Verificar encriptação do dispositivo</span><span class="sxs-lookup"><span data-stu-id="2eb21-159">Verify device encryption</span></span>

<span data-ttu-id="2eb21-160">A encriptação é silenciosa nos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2eb21-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="2eb21-161">Para verificar o estado de encriptação do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="2eb21-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="2eb21-162">No HoloLens, vá ao **Sistema de Definições**  >    >  **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="2eb21-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="2eb21-163">**O BitLocker** **está ativado** se o dispositivo estiver encriptado.</span><span class="sxs-lookup"><span data-stu-id="2eb21-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Sobre o ecrã mostrando BitLocker ativado](images/about-encryption.png)
