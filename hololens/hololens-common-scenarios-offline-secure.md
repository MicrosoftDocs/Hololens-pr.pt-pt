---
title: Cenários Comuns - Offline Secure HoloLens 2
description: Saiba como configurar um cenário de implementação e implementação de aplicações de segurança offline com provisão para dispositivos HoloLens.
keywords: HoloLens, gestão, offline, offline seguro
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378487"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="ca774-104">Cenários Comuns - Offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ca774-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="ca774-105">Descrição Geral</span><span class="sxs-lookup"><span data-stu-id="ca774-105">Overview</span></span>

<span data-ttu-id="ca774-106">Este guia fornece orientações para a aplicação de um pacote de provisionamento de amostra que bloqueie um HoloLens 2 para utilização em ambientes seguros com as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="ca774-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="ca774-107">Desativar o Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="ca774-107">Disable WiFi.</span></span>
-   <span data-ttu-id="ca774-108">Desative o BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="ca774-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="ca774-109">Desative os microfones.</span><span class="sxs-lookup"><span data-stu-id="ca774-109">Disable Microphones.</span></span>
-   <span data-ttu-id="ca774-110">Evita a adição ou remoção de pacotes de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="ca774-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="ca774-111">Nenhum utilizador pode ativar qualquer um dos componentes restritos acima referidos.</span><span class="sxs-lookup"><span data-stu-id="ca774-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="ca774-112">[![Cenário de segurança offline ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ca774-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="ca774-113">Preparação</span><span class="sxs-lookup"><span data-stu-id="ca774-113">Prepare</span></span>

<span data-ttu-id="ca774-114">Configuração do PC do Windows 10</span><span class="sxs-lookup"><span data-stu-id="ca774-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="ca774-115">[Descarregue o mais recente ficheiro HoloLens 2 OS](https://aka.ms/hololens2download) diretamente para um PC.</span><span class="sxs-lookup"><span data-stu-id="ca774-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="ca774-116">O suporte para esta configuração está incluído na Build 19041.1117 ou acima.</span><span class="sxs-lookup"><span data-stu-id="ca774-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="ca774-117">Descarregue/Instale a ferramenta Advanced Recovery Companion (ARC) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) para o seu PC</span><span class="sxs-lookup"><span data-stu-id="ca774-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="ca774-118">Descarregue/Instale a mais recente ferramenta [do Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) da Microsoft Store para o seu PC.</span><span class="sxs-lookup"><span data-stu-id="ca774-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="ca774-119">[Descarregue a pasta OfflineSecureHL2_Sample com os ficheiros do projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para construir o PPKG.</span><span class="sxs-lookup"><span data-stu-id="ca774-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="ca774-120">Prepare a sua aplicação offline [Line of Business para a implementação ppkg](app-deploy-provisioning-package.md).</span><span class="sxs-lookup"><span data-stu-id="ca774-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="ca774-121">Configurar</span><span class="sxs-lookup"><span data-stu-id="ca774-121">Configure</span></span>

<span data-ttu-id="ca774-122">Construa um pacote de provisionamento de configuração segura</span><span class="sxs-lookup"><span data-stu-id="ca774-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="ca774-123">Lance a ferramenta WCD no seu PC.</span><span class="sxs-lookup"><span data-stu-id="ca774-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="ca774-124">Selecione **o projeto De arquivo -> Open**.</span><span class="sxs-lookup"><span data-stu-id="ca774-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="ca774-125">Navegue até à localização da pasta OfflineSecureHL2_Sample previamente guardada e selecione: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="ca774-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="ca774-126">O projeto deve abrir e deverá agora ter uma lista de personalizações disponíveis:</span><span class="sxs-lookup"><span data-stu-id="ca774-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ca774-127">![Screenshot do pacote de configuração aberto em WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="ca774-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="ca774-128">Configurações definidas neste pacote de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="ca774-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="ca774-129">Item</span><span class="sxs-lookup"><span data-stu-id="ca774-129">Item</span></span>                                                |     <span data-ttu-id="ca774-130">Definições</span><span class="sxs-lookup"><span data-stu-id="ca774-130">Setting</span></span>                       |     <span data-ttu-id="ca774-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="ca774-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="ca774-132">Contas / Utilizadores</span><span class="sxs-lookup"><span data-stu-id="ca774-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="ca774-133">Nome de utilizador local & palavra-passe</span><span class="sxs-lookup"><span data-stu-id="ca774-133">Local User Name & Password</span></span>    |     <span data-ttu-id="ca774-134">Para estes dispositivos offline, um único nome de utilizador e senha terá de ser definido e partilhado por todos os utilizadores do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ca774-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="ca774-135">Primeira Experiência / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="ca774-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="ca774-136">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="ca774-136">True</span></span>                          |     <span data-ttu-id="ca774-137">Salta a calibração apenas durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="ca774-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="ca774-138">Primeira Experiência / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="ca774-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="ca774-139">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="ca774-139">True</span></span>                          |     <span data-ttu-id="ca774-140">Ignora o treino do dispositivo durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="ca774-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="ca774-141">Primeira Experiência / HoloLens / Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ca774-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="ca774-142">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="ca774-142">True</span></span>                          |     <span data-ttu-id="ca774-143">Salta Wi-Fi config durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="ca774-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="ca774-144">Políticas/Conectividade/Permitir Bluetooth</span><span class="sxs-lookup"><span data-stu-id="ca774-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="ca774-145">No</span><span class="sxs-lookup"><span data-stu-id="ca774-145">No</span></span>                            |     <span data-ttu-id="ca774-146">Desativa Bluetooth</span><span class="sxs-lookup"><span data-stu-id="ca774-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="ca774-147">Políticas/Experiência/Permitir aCortana</span><span class="sxs-lookup"><span data-stu-id="ca774-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="ca774-148">No</span><span class="sxs-lookup"><span data-stu-id="ca774-148">No</span></span>                            |     <span data-ttu-id="ca774-149">Desativa cortana (para eliminar potenciais problemas uma vez que os microfones estão desativados)</span><span class="sxs-lookup"><span data-stu-id="ca774-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="ca774-150">Políticas/Realidade Mista/MicrofoneDisabled</span><span class="sxs-lookup"><span data-stu-id="ca774-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="ca774-151">Yes</span><span class="sxs-lookup"><span data-stu-id="ca774-151">Yes</span></span>                           |     <span data-ttu-id="ca774-152">Desativa o microfone</span><span class="sxs-lookup"><span data-stu-id="ca774-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="ca774-153">Políticas/Privacidade/LetAppsAccessLocalização</span><span class="sxs-lookup"><span data-stu-id="ca774-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="ca774-154">Força negar</span><span class="sxs-lookup"><span data-stu-id="ca774-154">Force deny</span></span>                    |     <span data-ttu-id="ca774-155">Impede que as Aplicações tentem aceder aos dados de localização (para eliminar potenciais problemas uma vez que o rastreio de Localização está desativado)</span><span class="sxs-lookup"><span data-stu-id="ca774-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="ca774-156">Políticas/Privacidade/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="ca774-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="ca774-157">Força negar</span><span class="sxs-lookup"><span data-stu-id="ca774-157">Force deny</span></span>                    |     <span data-ttu-id="ca774-158">Impede que as Apps tentem aceder aos microfones (para eliminar potenciais problemas uma vez que os microfones estão desactivdos)</span><span class="sxs-lookup"><span data-stu-id="ca774-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="ca774-159">Políticas/Segurança/Permitir a Embalagem deProvisão</span><span class="sxs-lookup"><span data-stu-id="ca774-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="ca774-160">No</span><span class="sxs-lookup"><span data-stu-id="ca774-160">No</span></span>                            |     <span data-ttu-id="ca774-161">Impede qualquer pessoa de adicionar pacotes de provisionamento que possam tentar anular políticas bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="ca774-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="ca774-162">Políticas/Segurança/Permitir a Embalagem deProvisão</span><span class="sxs-lookup"><span data-stu-id="ca774-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="ca774-163">No</span><span class="sxs-lookup"><span data-stu-id="ca774-163">No</span></span>                            |     <span data-ttu-id="ca774-164">Impede qualquer pessoa de remover este pacote de provisionamento bloqueado.</span><span class="sxs-lookup"><span data-stu-id="ca774-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="ca774-165">Políticas/Sistema/PermitirLocalização</span><span class="sxs-lookup"><span data-stu-id="ca774-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="ca774-166">No</span><span class="sxs-lookup"><span data-stu-id="ca774-166">No</span></span>                            |     <span data-ttu-id="ca774-167">Impede que o dispositivo tente rastrear os dados de localização.</span><span class="sxs-lookup"><span data-stu-id="ca774-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="ca774-168">Políticas/Wi-Fi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="ca774-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="ca774-169">No</span><span class="sxs-lookup"><span data-stu-id="ca774-169">No</span></span>                            |     <span data-ttu-id="ca774-170">Desativa Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ca774-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="ca774-171">Em Configurações de Tempo de Execução, Selecione **Contas / Utilizadores / Nome do Utilizador: Holo / Password**.</span><span class="sxs-lookup"><span data-stu-id="ca774-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="ca774-172">Observe a palavra-passe e reinicie se desejar.</span><span class="sxs-lookup"><span data-stu-id="ca774-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="ca774-173">Navegue para UniversalAppInstall / UserContextApp e [configuure a aplicação LOB](app-deploy-provisioning-package.md) que irá implementar nestes dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ca774-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ca774-174">![Screenshot de onde adicionar a sua aplicação no WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="ca774-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="ca774-175">Uma vez concluído, selecione o botão "Exportar" e siga todas as instruções até que o seu pacote de provisionamento seja criado.</span><span class="sxs-lookup"><span data-stu-id="ca774-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ca774-176">![Screenshot do botão Exportação para este pacote em WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="ca774-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="ca774-177">Implementar</span><span class="sxs-lookup"><span data-stu-id="ca774-177">Deploy</span></span>

1. <span data-ttu-id="ca774-178">Ligue o HL2 ao seu PC Windows 10 através de cabo USB.</span><span class="sxs-lookup"><span data-stu-id="ca774-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="ca774-179">Lance a ferramenta ARC e **selecione HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="ca774-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 limpa reflash ecrã inicial](images/ARC2.png)

1. <span data-ttu-id="ca774-181">No ecrã seguinte selecione **Manual .**</span><span class="sxs-lookup"><span data-stu-id="ca774-181">On the next screen select **Manual package selection**.</span></span>

   ![Ecrã de informação HoloLens 2 ARC](images/arc_device_info.png)

1. <span data-ttu-id="ca774-183">Navegue para o ficheiro .ffu previamente descarregado e selecione **Open**.</span><span class="sxs-lookup"><span data-stu-id="ca774-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="ca774-184">Na página de Advertência **selecione Continue**.</span><span class="sxs-lookup"><span data-stu-id="ca774-184">At the Warning page select **Continue**.</span></span>

   ![Tela de aviso HoloLens 2 ARC](images/arc_warning.png)

1. <span data-ttu-id="ca774-186">Aguarde que a ferramenta ARC preencha a instalação HoloLens 2 OS.</span><span class="sxs-lookup"><span data-stu-id="ca774-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="ca774-187">Assim que o dispositivo completar a instalação e as botas de volta, do seu PC navegue para o File Explorer e copie o ficheiro PPKG previamente guardado para a pasta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ca774-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ca774-188">![Ficheiro PPKG no PC na janela do Explorador de Ficheiros.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="ca774-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="ca774-189">No HoloLens 2, prima a combinação seguinte do botão para executar o Pacote de Provisionamento: Toque no **volume para baixo** e no **botão de alimentação** ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ca774-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="ca774-190">Será solicitado para aplicar o Pacote de Provisionamento, **selecione Confirmar**</span><span class="sxs-lookup"><span data-stu-id="ca774-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="ca774-191">Uma vez que o pacote de provisionamento complete, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca774-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="ca774-192">Em seguida, deve ser solicitado que assine no dispositivo com a conta local partilhada e a palavra-passe.</span><span class="sxs-lookup"><span data-stu-id="ca774-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="ca774-193">Manter</span><span class="sxs-lookup"><span data-stu-id="ca774-193">Maintain</span></span>

<span data-ttu-id="ca774-194">Com esta configuração, recomenda-se reiniciar o processo acima e relançar o dispositivo com a ferramenta ARC e aplicar um novo PPKG para então fazer quaisquer atualizações ao(s) e/ou aplicações.</span><span class="sxs-lookup"><span data-stu-id="ca774-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
