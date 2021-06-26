---
title: Como carregar lateralmente e instalar apps através do Instalador de Aplicações HoloLens 2
description: Aprenda a instalar e resolver problemas com o instalador de aplicações e carregar lateralmente e instalar aplicações via UI.
keywords: gestão de aplicativos, app, hololens, instalador de aplicativos
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8be5c2ed7fba38b6710aba9c122557a36073a79
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924133"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="a247f-104">Instalar aplicativos no HoloLens 2 através do Instalador de Aplicações</span><span class="sxs-lookup"><span data-stu-id="a247f-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="a247f-105">Esta funcionalidade foi disponibilizada no [Windows Holographic, versão 20H2 – dezembro 2020 Update](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="a247f-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="a247f-106">Certifique-se de que o seu dispositivo está [atualizado](hololens-update-hololens.md) para utilizar esta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="a247f-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="a247f-107">**Adicionámos uma nova capacidade (App Installer) para permitir a instalação de aplicações de forma mais perfeita** nos seus dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a247f-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="a247f-108">A funcionalidade será **on-by predefinida para dispositivos não geridos**.</span><span class="sxs-lookup"><span data-stu-id="a247f-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="a247f-109">Para evitar perturbações nas empresas, o instalador de aplicações **não estará disponível para dispositivos geridos** neste momento.</span><span class="sxs-lookup"><span data-stu-id="a247f-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="a247f-110">Um dispositivo é considerado "gerido" se **algum** dos seguintes for verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="a247f-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="a247f-111">MDM [Inscrito](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="a247f-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="a247f-112">Configurado com [pacote de provisionamento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="a247f-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="a247f-113">[Identidade](hololens-identity.md) do utilizador é Azure AD</span><span class="sxs-lookup"><span data-stu-id="a247f-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="a247f-114">Agora é possível instalar apps sem necessidade de ativar o Modo de Desenvolvimento ou de utilizar o Portal do Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a247f-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="a247f-115">Descarregue (através de USB ou através do Microsoft Edge) o Pacote Appx para o seu dispositivo e navegue para o Pacote Appx no File Explorer para ser solicitado para iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="a247f-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="a247f-116">Em alternativa, [inicie uma instalação a partir de uma página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="a247f-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="a247f-117">Tal como as aplicações que instala a partir da Microsoft Store ou sideload utilizando a capacidade de implementação da App LOB do MDM, as aplicações precisam de ser assinadas digitalmente com a [Ferramenta de Sinais](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado utilizado para assinar deve ser fidedigno](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo HoloLens antes de a aplicação poder ser implementada.</span><span class="sxs-lookup"><span data-stu-id="a247f-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="a247f-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a247f-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="a247f-119">Para os seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="a247f-119">For your devices:</span></span>

<span data-ttu-id="a247f-120">Esta funcionalidade encontra-se atualmente disponível nas construções Holográficas 20H2 do Windows para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a247f-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="a247f-121">Certifique-se de que todos os dispositivos que utilizam este método são [atualizados](hololens-update-hololens.md).</span><span class="sxs-lookup"><span data-stu-id="a247f-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="a247f-122">Para as suas aplicações:</span><span class="sxs-lookup"><span data-stu-id="a247f-122">For your apps:</span></span>

<span data-ttu-id="a247f-123">A Configuração da Solução da sua aplicação deve ser **Master** ou **Release,** uma vez que o Instalador de Aplicações utilizará dependências da loja.</span><span class="sxs-lookup"><span data-stu-id="a247f-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="a247f-124">Veja mais sobre [a criação de pacotes de aplicações.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="a247f-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="a247f-125">As aplicações instaladas através deste método devem ser assinadas digitalmente.</span><span class="sxs-lookup"><span data-stu-id="a247f-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="a247f-126">Terá de usar um certificado para assinar a aplicação.</span><span class="sxs-lookup"><span data-stu-id="a247f-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="a247f-127">Você pode obter um certificado da [Lista de CA Fidedignas da MS,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)caso em que você não precisará tomar qualquer ação extra.</span><span class="sxs-lookup"><span data-stu-id="a247f-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="a247f-128">Ou pode assinar o seu próprio certificado no entanto esse certificado terá de ser empurrado para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a247f-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="a247f-129">Como assinar aplicativos [utilizando a Ferramenta de Sinal.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="a247f-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="a247f-130">**Opções de certificado:**</span><span class="sxs-lookup"><span data-stu-id="a247f-130">**Certificate options:**</span></span>

- [<span data-ttu-id="a247f-131">Lista CA Fidedigna de MS</span><span class="sxs-lookup"><span data-stu-id="a247f-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="a247f-132">**Escolha um método de implantação de certificados.**</span><span class="sxs-lookup"><span data-stu-id="a247f-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="a247f-133">[Os pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.</span><span class="sxs-lookup"><span data-stu-id="a247f-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="a247f-134">O MDM pode ser utilizado para [aplicar certificados com configurações do dispositivo.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="a247f-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="a247f-135">Utilize o [gestor de certificados no](certificate-manager.md)dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a247f-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="a247f-136">Método de instalação</span><span class="sxs-lookup"><span data-stu-id="a247f-136">Installation method</span></span>

1. <span data-ttu-id="a247f-137">Verifique se o seu dispositivo não é considerado gerido.</span><span class="sxs-lookup"><span data-stu-id="a247f-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="a247f-138">Verifique se o seu dispositivo HoloLens 2 está ligado e está inscrito.</span><span class="sxs-lookup"><span data-stu-id="a247f-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="a247f-139">No seu PC, navegue para a sua aplicação personalizada e copie o seu appapp.appxbundle para o seu devicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="a247f-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="a247f-140">Depois de ter terminado de copiar o seu ficheiro, poderá desligar o seu dispositivo e terminar a instalação mais tarde.</span><span class="sxs-lookup"><span data-stu-id="a247f-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="a247f-141">A partir do seu dispositivo HoloLens 2 Abra o **Menu Iniciar,** selecione **Todas as aplicações** e lance a aplicação **File Explorer.**</span><span class="sxs-lookup"><span data-stu-id="a247f-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="a247f-142">Navegue para a pasta Downloads.</span><span class="sxs-lookup"><span data-stu-id="a247f-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="a247f-143">Pode ser necessário no painel esquerdo da aplicação selecionar este **dispositivo** primeiro e, em seguida, navegar para Downloads.</span><span class="sxs-lookup"><span data-stu-id="a247f-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="a247f-144">Selecione o ficheiro appxbundle do seuapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="a247f-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="a247f-145">O Instalador de Aplicações será lançado.</span><span class="sxs-lookup"><span data-stu-id="a247f-145">The App Installer will launch.</span></span> <span data-ttu-id="a247f-146">Selecione o botão **Instalar** para instalar a sua aplicação.</span><span class="sxs-lookup"><span data-stu-id="a247f-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="a247f-147">A aplicação instalada será lançada automaticamente após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="a247f-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Instalação de exemplos MRTK através do Instalador de Aplicações](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="a247f-149">Instalações de resolução de problemas</span><span class="sxs-lookup"><span data-stu-id="a247f-149">Troubleshooting Installs</span></span>

<span data-ttu-id="a247f-150">Se a sua aplicação não tiver sido instalada, verifique o seguinte para resolver problemas:</span><span class="sxs-lookup"><span data-stu-id="a247f-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="a247f-151">A sua aplicação ou é um Master ou Release build.</span><span class="sxs-lookup"><span data-stu-id="a247f-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="a247f-152">O seu dispositivo é atualizado para uma construção na qual esta funcionalidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="a247f-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="a247f-153">Está [ligado à internet.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="a247f-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="a247f-154">Os seus [pontos finais para a Microsoft Store](hololens-offline.md) estão corretamente configurados.</span><span class="sxs-lookup"><span data-stu-id="a247f-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="a247f-155">Instalador web</span><span class="sxs-lookup"><span data-stu-id="a247f-155">Web Installer</span></span>

<span data-ttu-id="a247f-156">Os utilizadores podem instalar uma aplicação diretamente a partir de um servidor web.</span><span class="sxs-lookup"><span data-stu-id="a247f-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="a247f-157">Este fluxo requer a utilização do Instalador de Aplicações combinado com um método de distribuição fácil de descarregar e instalar.</span><span class="sxs-lookup"><span data-stu-id="a247f-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="a247f-158">Como configurar a instalação web:</span><span class="sxs-lookup"><span data-stu-id="a247f-158">How to set up web install:</span></span>

1. <span data-ttu-id="a247f-159">Certifique-se de que a sua aplicação está corretamente configurada para instalar.</span><span class="sxs-lookup"><span data-stu-id="a247f-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="a247f-160">Siga estes [passos para permitir a instalação a partir de uma página web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="a247f-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="a247f-161">Experiência do utilizador final:</span><span class="sxs-lookup"><span data-stu-id="a247f-161">End user experience:</span></span>

1. <span data-ttu-id="a247f-162">O utilizador recebe e instala o certificado no dispositivo utilizando um método previamente escolhido acima.</span><span class="sxs-lookup"><span data-stu-id="a247f-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="a247f-163">O utilizador visita o URL criado a partir do degrau acima.</span><span class="sxs-lookup"><span data-stu-id="a247f-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="a247f-164">A aplicação irá agora instalar-se no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a247f-164">The app will now install to the device.</span></span> <span data-ttu-id="a247f-165">Para encontrar a aplicação, abra o **menu Iniciar** e selecione o botão **Todas as aplicações** para encontrar a sua aplicação.</span><span class="sxs-lookup"><span data-stu-id="a247f-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="a247f-166">Para obter mais ajuda na resolução de problemas, o método de instalação do instalador de aplicações visite [problemas de instalação de aplicações de resolução de problemas.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="a247f-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="a247f-167">A UI durante o processo de atualização não é suportada.</span><span class="sxs-lookup"><span data-stu-id="a247f-167">UI during the update process is not supported.</span></span> <span data-ttu-id="a247f-168">Assim, a opção ShowPrompt [nesta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e as opções relacionadas não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="a247f-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="a247f-169">Exemplos de Aplicações</span><span class="sxs-lookup"><span data-stu-id="a247f-169">Sample Apps</span></span>

<span data-ttu-id="a247f-170">Experimente o Instalador de Aplicações com uma das nossas aplicações de amostra disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a247f-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="a247f-171">Exemplos de aplicações</span><span class="sxs-lookup"><span data-stu-id="a247f-171">Sample apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/features-and-samples?tabs=unity#sample-apps)
