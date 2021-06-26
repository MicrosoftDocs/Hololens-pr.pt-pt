---
title: Implementação hololens 2 e resolução de problemas geridos do dispositivo
description: Resolução de problemas HoloLens 2 dispositivos em um ambiente enterprise
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: resolução de problemas
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961641"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="5a7ca-104">Implementação de resolução de problemas e dispositivos geridos</span><span class="sxs-lookup"><span data-stu-id="5a7ca-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="5a7ca-105">Este artigo descreve como resolver várias questões ou responder a questões relativas à implementação e gestão do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="5a7ca-106">Antes de iniciar qualquer procedimento de resolução de problemas, certifique-se de que o seu dispositivo está carregado até **20 a 40%** da capacidade da bateria, se possível.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="5a7ca-107">As [luzes indicadoras](hololens2-setup.md#lights-that-indicate-the-battery-level) da bateria localizadas sob o botão de alimentação são uma forma rápida de verificar a capacidade da bateria sem iniciar sessão no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="5a7ca-108">Resolução de problemas da EAP</span><span class="sxs-lookup"><span data-stu-id="5a7ca-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="5a7ca-109">Resolução de problemas wi-fi</span><span class="sxs-lookup"><span data-stu-id="5a7ca-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="5a7ca-110">Resolução de problemas de rede</span><span class="sxs-lookup"><span data-stu-id="5a7ca-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="5a7ca-111">Não pode entrar num dispositivo HoloLens previamente configurado</span><span class="sxs-lookup"><span data-stu-id="5a7ca-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="5a7ca-112">Não pode iniciar sessão depois de atualizar para o Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="5a7ca-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="5a7ca-113">Resolução de problemas do piloto automático</span><span class="sxs-lookup"><span data-stu-id="5a7ca-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="5a7ca-114">FaQs de dispositivos HoloLens geridos</span><span class="sxs-lookup"><span data-stu-id="5a7ca-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="5a7ca-115">Resolução de problemas da EAP</span><span class="sxs-lookup"><span data-stu-id="5a7ca-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="5a7ca-116">Verifique duas vezes Wi-Fi perfil tem as definições certas:</span><span class="sxs-lookup"><span data-stu-id="5a7ca-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="5a7ca-117">O tipo EAP é configurado corretamente, tipos comuns de EAP: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="5a7ca-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="5a7ca-118">Wi-Fi nome SSID é certo e coincide com a cadeia HEX.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="5a7ca-119">Para o EAP-TLS, o TrustedRootCA contém o hash SHA-1 do certificado de CA de raiz fidedigna do servidor.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="5a7ca-120">No comando "certutil.exe-dump cert_file_name" do Windows PC, o comando mostrará a cadeia de haxixe SHA-1 de um certificado.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="5a7ca-121">Colete a captura de pacotes de rede nos registos do Access Point ou do Controlador ou do servidor AAA para saber onde a sessão EAP falha.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="5a7ca-122">Se a identidade EAP fornecida pela HoloLens não for esperada, verifique se a identidade foi corretamente fornecida através de Wi-Fi perfil ou certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="5a7ca-123">Se o servidor rejeitar o certificado de cliente HoloLens, verifique se o certificado de cliente exigido foi a provisionado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="5a7ca-124">Se o HoloLens rejeitar o certificado do servidor, verifique se o certificado de CA raiz do servidor foi a provisionado no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="5a7ca-125">Se o perfil da empresa for a provisionado através de Wi-Fi pacote de provisionamento, considere aplicar o pacote de provisionamento num PC windows 10.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="5a7ca-126">Se também falhar no PC do Windows 10, siga o guia de resolução de problemas de autenticação do cliente Windows 802.1X.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="5a7ca-127">Envie-nos feedback através do Feedback Hub.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="5a7ca-128">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="5a7ca-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="5a7ca-129">Resolução de problemas Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="5a7ca-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="5a7ca-130">Aqui estão algumas coisas a experimentar se não consegue ligar os hololens a uma rede Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="5a7ca-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="5a7ca-131">Certifique-se de que Wi-Fi está ligado.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="5a7ca-132">Para verificar, utilize o gesto Iniciar e, em seguida, selecione Definições > Rede & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="5a7ca-133">Se Wi-Fi estiver ligado, tente desligá-lo e depois ligado novamente.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="5a7ca-134">Aproxime o computador do router ou do ponto de acesso.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="5a7ca-135">Reinicie o router Wi-Fi e reinicie os HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="5a7ca-136">Tente ligar de novo.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-136">Try connecting again.</span></span>
4. <span data-ttu-id="5a7ca-137">Se nenhuma destas coisas funcionar, verifique se o seu router está a utilizar o firmware mais recente.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="5a7ca-138">Pode encontrar esta informação no site do fabricante.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="5a7ca-139">Quando você assina uma conta empresarial ou organizacional no dispositivo, também pode aplicar a política de Gestão de Dispositivos Móveis (MDM), se a política for configurada pelo seu administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="5a7ca-140">Resolução de problemas de rede</span><span class="sxs-lookup"><span data-stu-id="5a7ca-140">Network Troubleshooting</span></span>
<span data-ttu-id="5a7ca-141">Se os problemas de rede são um obstáculo à implementação e utilização com sucesso do HoloLens 2 na sua organização, saiba como duas ferramentas de diagnóstico de rede bem conhecidas, Fiddler e Wireshark podem ajudá-lo a digitalizar, diagnosticar e identificar problemas.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="5a7ca-142">Confira este [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="5a7ca-143">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="5a7ca-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="5a7ca-144">Não pode entrar num dispositivo HoloLens previamente configurado</span><span class="sxs-lookup"><span data-stu-id="5a7ca-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="5a7ca-145">Se o seu dispositivo foi previamente configurado para outra pessoa, seja para um cliente ou para um ex-funcionário, e não tiver a sua palavra-passe para desbloquear o dispositivo, pode usar o Intune para [limpar](https://docs.microsoft.com/intune/remote-actions/devices-wipe) remotamente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="5a7ca-146">Em seguida, o aparelho volta a piscar sozinho.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="5a7ca-147">Quando limpar o dispositivo, certifique-se de deixar o **estado de inscrição e a conta do utilizador** sem controlo.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="5a7ca-148">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="5a7ca-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="5a7ca-149">Não pode iniciar sessão depois de atualizar para o Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="5a7ca-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="5a7ca-150">Sintomas</span><span class="sxs-lookup"><span data-stu-id="5a7ca-150">Symptoms</span></span>
- <span data-ttu-id="5a7ca-151">A utilização de PIN para logon falhará após a entrada no PIN correto.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="5a7ca-152">A utilização do método de início de sessão da Web falhará após a sua assinatura na página web.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="5a7ca-153">O dispositivo não está listado como "Azure AD aderido" no [portal Azure](https://portal.azure.com/) -> Azure Ative Directory -> Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="5a7ca-154">Causa</span><span class="sxs-lookup"><span data-stu-id="5a7ca-154">Cause</span></span>
<span data-ttu-id="5a7ca-155">O dispositivo impactado pode ter sido apagado do inquilino AZure AD.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="5a7ca-156">Por exemplo, isto pode acontecer porque:</span><span class="sxs-lookup"><span data-stu-id="5a7ca-156">For example, this may happen because:</span></span>

- <span data-ttu-id="5a7ca-157">Um administrador ou utilizador eliminou o dispositivo no portal Azure ou na utilização do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="5a7ca-158">O dispositivo foi removido do inquilino da AD Azure devido à inatividade.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="5a7ca-159">Para um ambiente eficientemente gerido, recomendamos normalmente que os administradores de TI [removam dispositivos inativos e velhos do seu inquilino AD Azure.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="5a7ca-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="5a7ca-160">Quando um dispositivo impactado tentar contactar novamente o inquilino Azure AD depois de ter sido eliminado, deixará de autenticar com a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="5a7ca-161">Este efeito é muitas vezes invisível para o utilizador do dispositivo, uma vez que a logon em cache via PIN continuará a permitir que o utilizador se insi.ndo.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="5a7ca-162">Mitigação</span><span class="sxs-lookup"><span data-stu-id="5a7ca-162">Mitigation</span></span>
<span data-ttu-id="5a7ca-163">Não existe atualmente forma de adicionar um dispositivo HoloLens eliminado de volta ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="5a7ca-164">Os dispositivos afetados terão de ser reassusados seguindo as instruções de [reflashing](hololens-recovery.md#clean-reflash-the-device)do seu dispositivo .</span><span class="sxs-lookup"><span data-stu-id="5a7ca-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="5a7ca-165">Resolução de problemas do piloto automático</span><span class="sxs-lookup"><span data-stu-id="5a7ca-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="5a7ca-166">Os seguintes artigos podem ser um recurso útil para você aprender mais informações e resolver problemas de piloto automático Problemas, no entanto, esteja ciente de que estes artigos são baseados no Windows 10 Desktop e nem todas as informações podem aplicar-se a HoloLens:</span><span class="sxs-lookup"><span data-stu-id="5a7ca-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="5a7ca-167">Windows Autopilot - problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="5a7ca-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="5a7ca-168">Problemas de inscrição de dispositivos Windows na Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5a7ca-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="5a7ca-169">Windows Autopilot - Conflitos Políticos</span><span class="sxs-lookup"><span data-stu-id="5a7ca-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="5a7ca-170">FaQs de dispositivos HoloLens geridos</span><span class="sxs-lookup"><span data-stu-id="5a7ca-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="5a7ca-171">Posso utilizar o Gestor de Configuração do Centro de Sistema (SCCM) para gerir dispositivos HoloLens?</span><span class="sxs-lookup"><span data-stu-id="5a7ca-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="5a7ca-172">N.º</span><span class="sxs-lookup"><span data-stu-id="5a7ca-172">No.</span></span> <span data-ttu-id="5a7ca-173">Tens de usar um sistema MDM para gerir dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="5a7ca-174">Posso utilizar os Serviços de Domínio do Diretório Ativo (DS AD) para gerir as contas de utilizadores do HoloLens?</span><span class="sxs-lookup"><span data-stu-id="5a7ca-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="5a7ca-175">N.º</span><span class="sxs-lookup"><span data-stu-id="5a7ca-175">No.</span></span> <span data-ttu-id="5a7ca-176">Tem de utilizar o Azure Ative Directory (Azure AD) para gerir as contas dos utilizadores dos dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="5a7ca-177">Os HoloLens são capazes de matricular automaticamente os Sistemas automatizados de captura de dados (ADCS).</span><span class="sxs-lookup"><span data-stu-id="5a7ca-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="5a7ca-178">N.º</span><span class="sxs-lookup"><span data-stu-id="5a7ca-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="5a7ca-179">Os HoloLens podem participar na Autenticação Integrada do Windows?</span><span class="sxs-lookup"><span data-stu-id="5a7ca-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="5a7ca-180">N.º</span><span class="sxs-lookup"><span data-stu-id="5a7ca-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="5a7ca-181">A HoloLens suporta a marca?</span><span class="sxs-lookup"><span data-stu-id="5a7ca-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="5a7ca-182">N.º</span><span class="sxs-lookup"><span data-stu-id="5a7ca-182">No.</span></span> <span data-ttu-id="5a7ca-183">No entanto, pode contornar esta questão utilizando uma das seguintes abordagens:</span><span class="sxs-lookup"><span data-stu-id="5a7ca-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="5a7ca-184">Crie uma aplicação personalizada e, em seguida, ative o [modo Quiosque](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="5a7ca-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="5a7ca-185">A aplicação personalizada pode ter marca, e pode lançar outras aplicações (como o Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="5a7ca-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="5a7ca-186">Altere todas as fotos do perfil do utilizador no Azure AD para o logótipo da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="5a7ca-187">No entanto, isto pode não ser desejável para todos os cenários.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="5a7ca-188">Que capacidades de registo os HoloLens 2 oferecem?</span><span class="sxs-lookup"><span data-stu-id="5a7ca-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="5a7ca-189">O registo está limitado a vestígios que podem ser capturados em cenários de desenvolvimento ou resolução de problemas, ou telemetria que os dispositivos enviam para servidores da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="5a7ca-190">Perguntas sobre a segurança de dispositivos HoloLens</span><span class="sxs-lookup"><span data-stu-id="5a7ca-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="5a7ca-191">Consulte as [nossas informações de segurança HoloLens 2](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5a7ca-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="5a7ca-192">Para dispositivos HoloLens 1st Gen, por favor [reveja este FAQ](hololens1-faq-security.md).</span><span class="sxs-lookup"><span data-stu-id="5a7ca-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="5a7ca-193">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="5a7ca-193">Back to list</span></span>](#list)
