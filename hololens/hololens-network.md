---
title: Ligue hololens a uma rede
description: Saiba como configurar e conectar-se à internet com holoLens e como identificar o endereço IP do dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, wireless, internet, ip, endereço ip
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: d68c75dcb2249a67f2e07c77cb1b69997eb0ae72
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379908"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="44ff4-104">Ligue hololens a uma rede</span><span class="sxs-lookup"><span data-stu-id="44ff4-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="44ff4-105">Para fazer a maioria das coisas nos hololens, tem que estar ligado a uma rede.</span><span class="sxs-lookup"><span data-stu-id="44ff4-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="44ff4-106">O HoloLens contém um rádio 802.11ac, 2x2 Wi-Fi e ligá-lo a uma rede é semelhante a ligar um dispositivo Windows 10 Desktop ou Mobile a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="44ff4-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="44ff4-107">Este guia irá ajudá-lo:</span><span class="sxs-lookup"><span data-stu-id="44ff4-107">This guide will help you:</span></span>

- <span data-ttu-id="44ff4-108">Ligue-se a uma rede que utilize Wi-Fi, ou apenas para HoloLens 2, Wi-Fi Direct ou Ethernet sobre USB-C</span><span class="sxs-lookup"><span data-stu-id="44ff4-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="44ff4-109">Desativar e reativar Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="44ff4-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="44ff4-110">Leia mais sobre [a utilização de HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="44ff4-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="44ff4-111">Ligação pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="44ff4-111">Connecting for the first time</span></span>

<span data-ttu-id="44ff4-112">A primeira vez que usar os HoloLens, será guiado através da ligação a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="44ff4-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="44ff4-113">Se tiver problemas em ligar-se a Wi-Fi durante a configuração, certifique-se de que a sua rede é uma rede aberta, protegida por palavras-passe ou uma rede de portal cativo.</span><span class="sxs-lookup"><span data-stu-id="44ff4-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="44ff4-114">Além disso, confirme que a rede não requer que utilize um certificado para se ligar.</span><span class="sxs-lookup"><span data-stu-id="44ff4-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="44ff4-115">Após a configuração, pode ligar-se a outros tipos de redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="44ff4-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="44ff4-116">Nos dispositivos HoloLens 2, um utilizador também pode [utilizar um adaptador USB-C para Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para ligar diretamente a Wi-Fi para ajudar a configurar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44ff4-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="44ff4-117">Uma vez configurado o dispositivo, um utilizador pode continuar a utilizar o adaptador ou pode desligar o dispositivo do adaptador e [ligar-se ao wi-fi após a instalação](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="44ff4-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="44ff4-118">Ligação a Wi-Fi após a configuração</span><span class="sxs-lookup"><span data-stu-id="44ff4-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="44ff4-119">Pré-forma o **gesto Iniciar** e selecione **Definições**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="44ff4-120">A aplicação Definições será colocada automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="44ff4-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="44ff4-121">Selecione **Rede &**  >  **Wi-Fi de** Internet.</span><span class="sxs-lookup"><span data-stu-id="44ff4-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="44ff4-122">Certifique-se de que o Wi-Fi está ativado.</span><span class="sxs-lookup"><span data-stu-id="44ff4-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="44ff4-123">Se não vires a tua rede, percorra a lista.</span><span class="sxs-lookup"><span data-stu-id="44ff4-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="44ff4-124">Selecione uma rede e, em seguida, selecione **Connect**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="44ff4-125">Se for solicitado para uma palavra-passe de rede escreva-a e, em seguida, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi configurações](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="44ff4-127">Para confirmar que está ligado a uma rede Wi-Fi, verifique o estado Wi-Fi no menu **Iniciar:**</span><span class="sxs-lookup"><span data-stu-id="44ff4-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="44ff4-128">Abra o menu **Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="44ff4-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="44ff4-129">Olhe para o lado superior esquerdo do menu **Iniciar** para Wi-Fi estado.</span><span class="sxs-lookup"><span data-stu-id="44ff4-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="44ff4-130">O estado de Wi-Fi e o SSID da rede conectada serão mostrados.</span><span class="sxs-lookup"><span data-stu-id="44ff4-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="44ff4-131">Se Wi-Fi não estiver disponível, também pode [ligar-se às redes Cellular e 5G.](https://docs.microsoft.com/hololens/hololens-cellular)</span><span class="sxs-lookup"><span data-stu-id="44ff4-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](https://docs.microsoft.com/hololens/hololens-cellular).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44ff4-132">Por design, os utilizadores não podem afinar o comportamento de roaming Wi-Fi dos HoloLens 2 - **a única maneira de refrescar a lista de Wi-Fi é alternar o Wi-Fi Off and On**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="44ff4-133">Isto evita muitos problemas, como quando um dispositivo pode permanecer "preso" a um AP uma vez que está fora de alcance.</span><span class="sxs-lookup"><span data-stu-id="44ff4-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="troubleshooting-your-connection-to-wi-fi"></a><span data-ttu-id="44ff4-134">Resolução de problemas da sua ligação com Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="44ff4-134">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="44ff4-135">Se tiver problemas de ligação ao Wi-Fi, veja [se não consigo ligar-me ao Wi-Fi.](./hololens-faq.md#i-cant-connect-to-wi-fi)</span><span class="sxs-lookup"><span data-stu-id="44ff4-135">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="44ff4-136">Quando você assina uma conta empresarial ou organizacional no dispositivo, também pode aplicar a política de Gestão de Dispositivos Móveis (MDM), se a política for configurada pelo seu administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="44ff4-136">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="44ff4-137">Ligue hololens à Enterprise Wi-Fi Network</span><span class="sxs-lookup"><span data-stu-id="44ff4-137">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="44ff4-138">Os perfis Wi-Fi empresa utilizam o Protocolo de Autenticação Extensível (EAP) para autenticar ligações Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="44ff4-138">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="44ff4-139">HoloLens Enterprise Wi-Fi perfil pode ser configurado através de MDM ou pacote de provisionamento criado pelo [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="44ff4-139">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="44ff4-140">Para o dispositivo gerido microsoft Intune, consulte [o Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para obter instruções de configuração.</span><span class="sxs-lookup"><span data-stu-id="44ff4-140">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="44ff4-141">Para criar um pacote de provisionamento Wi-Fi em WCD, é necessário um perfil de Wi-Fi pré-configurado .xml ficheiro.</span><span class="sxs-lookup"><span data-stu-id="44ff4-141">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="44ff4-142">Aqui está uma amostra Wi-Fi perfil para WPA2-Enterprise com autenticação EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="44ff4-142">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="44ff4-143">O certificado de CA raiz do servidor e o certificado de cliente podem ter de ser a provisionados no dispositivo, dependendo do tipo EAP.</span><span class="sxs-lookup"><span data-stu-id="44ff4-143">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="44ff4-144">Recursos adicionais:</span><span class="sxs-lookup"><span data-stu-id="44ff4-144">Additional resources:</span></span>

- <span data-ttu-id="44ff4-145">WLANv1Profile Schema: [[MS-GPWL]: Perfil de LAN sem fios v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="44ff4-145">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="44ff4-146">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="44ff4-146">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

## <a name="eap-troubleshooting"></a><span data-ttu-id="44ff4-147">Resolução de problemas da EAP</span><span class="sxs-lookup"><span data-stu-id="44ff4-147">EAP Troubleshooting</span></span>
> [!TIP]
> <span data-ttu-id="44ff4-148">A maioria dos problemas de rede são o resultado de uma das 3 definições abaixo do 3 estar incorreta no perfil Wi-FI.</span><span class="sxs-lookup"><span data-stu-id="44ff4-148">A majority of network issues are the result of one of the below 3 settings being incorrect in the Wi-FI profile.</span></span> 
1. <span data-ttu-id="44ff4-149">Verifique duas vezes Wi-Fi perfil tem as definições certas:</span><span class="sxs-lookup"><span data-stu-id="44ff4-149">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="44ff4-150">O tipo EAP é configurado corretamente, tipos comuns de EAP: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="44ff4-150">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="44ff4-151">Wi-Fi nome SSID é certo e coincide com a cadeia HEX.</span><span class="sxs-lookup"><span data-stu-id="44ff4-151">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="44ff4-152">Para o EAP-TLS, o TrustedRootCA contém o hash SHA-1 do servidor&#39;certificado de CA de raiz fidedigna.</span><span class="sxs-lookup"><span data-stu-id="44ff4-152">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="44ff4-153">No Windows &quot; PC,certutil.exe comando de nome de ficheiro cert de despejo \_ \_ &quot; mostrará um certificado&#39;cadeia de hash SHA-1 do Windows PC.</span><span class="sxs-lookup"><span data-stu-id="44ff4-153">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>

2. <span data-ttu-id="44ff4-154">Colete a captura de pacotes de rede nos registos do Access Point ou do Controlador ou do servidor AAA para saber onde a sessão EAP falha.</span><span class="sxs-lookup"><span data-stu-id="44ff4-154">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="44ff4-155">Se a identidade EAP fornecida pela HoloLens não for esperada, verifique se a identidade foi corretamente fornecida através de Wi-Fi perfil ou certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="44ff4-155">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="44ff4-156">Se o servidor rejeitar o certificado de cliente HoloLens, verifique se o certificado de cliente exigido foi a provisionado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44ff4-156">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="44ff4-157">Se o HoloLens rejeitar o certificado do servidor, verifique se o certificado de CA raiz do servidor foi a provisionado no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="44ff4-157">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="44ff4-158">Se o perfil da empresa for a provisionado através de Wi-Fi pacote de provisionamento, considere aplicar o pacote de provisionamento num PC windows 10.</span><span class="sxs-lookup"><span data-stu-id="44ff4-158">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="44ff4-159">Se também falhar no PC do Windows 10, siga o [guia de resolução de problemas de autenticação do cliente Windows 802.1X](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span><span class="sxs-lookup"><span data-stu-id="44ff4-159">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="44ff4-160">Desaponte a sua telemetria para Full ou Optional (dependendo da sua construção) e, em seguida, envie-nos feedback através [do Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span><span class="sxs-lookup"><span data-stu-id="44ff4-160">Set your telemetry to Full or Optional (depending on your build) and then send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="44ff4-161">Recursos adicionais:</span><span class="sxs-lookup"><span data-stu-id="44ff4-161">Additional resources:</span></span>
- [<span data-ttu-id="44ff4-162">Exportar definições de Wi-Fi a partir de um dispositivo Windows</span><span class="sxs-lookup"><span data-stu-id="44ff4-162">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="configure-network-proxy"></a><span data-ttu-id="44ff4-163">Configure Rede Proxy</span><span class="sxs-lookup"><span data-stu-id="44ff4-163">Configure Network Proxy</span></span>

<span data-ttu-id="44ff4-164">Esta secção abrange o proxy de rede para aplicações HoloLens OS e Universal Windows Platform (UWP) utilizando a pilha HTTP do Windows.</span><span class="sxs-lookup"><span data-stu-id="44ff4-164">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="44ff4-165">As aplicações que utilizam a pilha HTTP não-Windows podem ter a sua própria configuração e manuseamento de procuração.</span><span class="sxs-lookup"><span data-stu-id="44ff4-165">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="44ff4-166">Configurações proxy</span><span class="sxs-lookup"><span data-stu-id="44ff4-166">Proxy Configurations</span></span> 

- <span data-ttu-id="44ff4-167">Script Proxy Auto-Config (PAC): um [ficheiro PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (abre um site não Microsoft) contém uma função JavaScript FindProxyForURL (url, anfitrião).</span><span class="sxs-lookup"><span data-stu-id="44ff4-167">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="44ff4-168">Procuração Estática: na forma de Servidor:Porta.</span><span class="sxs-lookup"><span data-stu-id="44ff4-168">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="44ff4-169">Web Proxy Auto-Discovery Protocol (WPAD): fornecer URL de ficheiro de configuração de procuração através de DHCP ou DNS.</span><span class="sxs-lookup"><span data-stu-id="44ff4-169">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="44ff4-170">Métodos de provisionamento por procuração</span><span class="sxs-lookup"><span data-stu-id="44ff4-170">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="44ff4-171">Há três formas de providenciar proxies:</span><span class="sxs-lookup"><span data-stu-id="44ff4-171">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="44ff4-172">**Definições UI:**</span><span class="sxs-lookup"><span data-stu-id="44ff4-172">**Settings UI:**</span></span> 
    1. <span data-ttu-id="44ff4-173">Procuração por utilizador (20H2 ou mais cedo):</span><span class="sxs-lookup"><span data-stu-id="44ff4-173">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="44ff4-174">Abra o menu Iniciar e selecione Definições.</span><span class="sxs-lookup"><span data-stu-id="44ff4-174">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="44ff4-175">Selecione Network & Internet e, em seguida, Proxy no menu esquerdo.</span><span class="sxs-lookup"><span data-stu-id="44ff4-175">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="44ff4-176">Desloque-se para a configuração de procuração manual e altere Use um servidor proxy para On.</span><span class="sxs-lookup"><span data-stu-id="44ff4-176">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="44ff4-177">Insira o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="44ff4-177">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="44ff4-178">Introduza o número da porta.</span><span class="sxs-lookup"><span data-stu-id="44ff4-178">Enter the port number.</span></span>
        6. <span data-ttu-id="44ff4-179">Clique em Guardar.</span><span class="sxs-lookup"><span data-stu-id="44ff4-179">Click Save.</span></span>
      1. <span data-ttu-id="44ff4-180">Procuração WiFi (21H1 ou superior):</span><span class="sxs-lookup"><span data-stu-id="44ff4-180">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="44ff4-181">Abra o menu Iniciar e vá para a página Wi-Fi 'Propriedades' da Rede.</span><span class="sxs-lookup"><span data-stu-id="44ff4-181">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="44ff4-182">Desça até Proxy</span><span class="sxs-lookup"><span data-stu-id="44ff4-182">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="44ff4-183">Alteração para Configuração Manual</span><span class="sxs-lookup"><span data-stu-id="44ff4-183">Change to Manual Setup</span></span>
          1. <span data-ttu-id="44ff4-184">Insira o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="44ff4-184">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="44ff4-185">Introduza o número da porta.</span><span class="sxs-lookup"><span data-stu-id="44ff4-185">Enter the port number.</span></span>
          1. <span data-ttu-id="44ff4-186">Clique em Aplicar.</span><span class="sxs-lookup"><span data-stu-id="44ff4-186">Click Apply.</span></span>
        
 2. <span data-ttu-id="44ff4-187">**MDM**</span><span class="sxs-lookup"><span data-stu-id="44ff4-187">**MDM**</span></span> 
     1. <span data-ttu-id="44ff4-188">Intune - Use estes [passos](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para configurar o proxy em Intune.</span><span class="sxs-lookup"><span data-stu-id="44ff4-188">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="44ff4-189">Terá de deslocar-se para o fundo da secção.</span><span class="sxs-lookup"><span data-stu-id="44ff4-189">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="44ff4-190">Outras soluções DE MDM de terceiros - Use um [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span><span class="sxs-lookup"><span data-stu-id="44ff4-190">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="44ff4-191">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="44ff4-191">**PPKG**</span></span> 
    1. <span data-ttu-id="44ff4-192">Open Windows Configuration Designer</span><span class="sxs-lookup"><span data-stu-id="44ff4-192">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="44ff4-193">Clique em Provisionamento Avançado, insira o nome para o seu novo Projeto e clique em Seguinte.</span><span class="sxs-lookup"><span data-stu-id="44ff4-193">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="44ff4-194">Selecione o Windows Holographic (HoloLens 2) e clique em Seguinte.</span><span class="sxs-lookup"><span data-stu-id="44ff4-194">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="44ff4-195">Importe o seu PPKG (opcional) e clique em Terminar.</span><span class="sxs-lookup"><span data-stu-id="44ff4-195">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="44ff4-196">Expandir configurações de tempo de execução -> Perfis de conectividade -> WLAN -> WLAN Proxy.</span><span class="sxs-lookup"><span data-stu-id="44ff4-196">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="44ff4-197">Introduza o SSID da sua rede de Wi-Fi e clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="44ff4-197">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="44ff4-198">Selecione a sua rede Wi-Fi na janela esquerda e introduza as personalizações desejadas.</span><span class="sxs-lookup"><span data-stu-id="44ff4-198">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="44ff4-199">As personalizações ativadas aparecerão em negrito no menu esquerdo.</span><span class="sxs-lookup"><span data-stu-id="44ff4-199">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="44ff4-200">Clique em Guardar e Sair.</span><span class="sxs-lookup"><span data-stu-id="44ff4-200">Click Save and Exit.</span></span>
    1. <span data-ttu-id="44ff4-201">[Aplique](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) o pacote de provisionamento aos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="44ff4-201">[Apply](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="44ff4-202">[Os CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) estão por detrás de muitas das tarefas e políticas de gestão do Windows 10, tanto no Microsoft Intune como em prestadores de serviços não-Microsoft MDM.</span><span class="sxs-lookup"><span data-stu-id="44ff4-202">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="44ff4-203">Também pode utilizar [o Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) para criar um pacote de [provisionamento](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) e aplicá-lo no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="44ff4-203">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="44ff4-204">Os CSPs mais prováveis que serão aplicados aos seus HoloLens 2 são:</span><span class="sxs-lookup"><span data-stu-id="44ff4-204">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="44ff4-205">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): procuração por perfil Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="44ff4-205">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="44ff4-206">Outros CSPs suportados em dispositivos HoloLens</span><span class="sxs-lookup"><span data-stu-id="44ff4-206">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="44ff4-207">VPN</span><span class="sxs-lookup"><span data-stu-id="44ff4-207">VPN</span></span>
<span data-ttu-id="44ff4-208">Uma ligação VPN pode ajudar a fornecer uma ligação mais segura e acesso à rede da sua empresa e à Internet.</span><span class="sxs-lookup"><span data-stu-id="44ff4-208">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="44ff4-209">HoloLens 2 suporta o cliente VPN incorporado e o plug-in VPN da Plataforma Universal windows (UWP).</span><span class="sxs-lookup"><span data-stu-id="44ff4-209">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="44ff4-210">Protocolos VPN incorporados suportados:</span><span class="sxs-lookup"><span data-stu-id="44ff4-210">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="44ff4-211">IKEv2</span><span class="sxs-lookup"><span data-stu-id="44ff4-211">IKEv2</span></span>
- <span data-ttu-id="44ff4-212">L2TP</span><span class="sxs-lookup"><span data-stu-id="44ff4-212">L2TP</span></span>
- <span data-ttu-id="44ff4-213">PPTP</span><span class="sxs-lookup"><span data-stu-id="44ff4-213">PPTP</span></span>

<span data-ttu-id="44ff4-214">Se o certificado for utilizado para a autenticação para o cliente VPN incorporado, o certificado de cliente necessário deve ser adicionado à loja de certificados do utilizador.</span><span class="sxs-lookup"><span data-stu-id="44ff4-214">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="44ff4-215">Para saber se um plug-in VPN de 3ª parte suporta HoloLens 2, vá à Loja para localizar a aplicação VPN e verificar se o HoloLens está listado como um dispositivo suportado e na página System Requirement a app suporta a arquitetura ARM ou ARM64.</span><span class="sxs-lookup"><span data-stu-id="44ff4-215">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="44ff4-216">O HoloLens só suporta aplicações da Plataforma Universal windows para VPN de terceiros.</span><span class="sxs-lookup"><span data-stu-id="44ff4-216">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="44ff4-217">A VPN pode ser gerida pelo MDM através [de Definições/AllowVPN,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)e definida através da  [política VPNv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="44ff4-217">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="44ff4-218">Saiba mais sobre [como configurar a VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) com [estes guias.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="44ff4-218">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="44ff4-219">VPN via UI</span><span class="sxs-lookup"><span data-stu-id="44ff4-219">VPN via UI</span></span>

<span data-ttu-id="44ff4-220">A VPN não é ativada por padrão, mas pode ser ativada manualmente abrindo a aplicação **Definições** e navegando para  **a Rede & Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-220">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="44ff4-221">Selecione um fornecedor VPN.</span><span class="sxs-lookup"><span data-stu-id="44ff4-221">Select a VPN provider.</span></span>
1. <span data-ttu-id="44ff4-222">Crie um nome de ligação.</span><span class="sxs-lookup"><span data-stu-id="44ff4-222">Create a connection name.</span></span> 
1. <span data-ttu-id="44ff4-223">Insira o nome ou endereço do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="44ff4-223">Enter your server name or address.</span></span>
1. <span data-ttu-id="44ff4-224">Selecione o tipo VPN.</span><span class="sxs-lookup"><span data-stu-id="44ff4-224">Select the VPN type.</span></span>
1. <span data-ttu-id="44ff4-225">Selecione o tipo de informação de login.</span><span class="sxs-lookup"><span data-stu-id="44ff4-225">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="44ff4-226">Opcionalmente adicione o nome de utilizador e a palavra-passe.</span><span class="sxs-lookup"><span data-stu-id="44ff4-226">Optionally add user name and password.</span></span>
1. <span data-ttu-id="44ff4-227">Aplique as definições VPN.</span><span class="sxs-lookup"><span data-stu-id="44ff4-227">Apply the VPN settings.</span></span> 

![Configurações hololens VPN](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="44ff4-229">VPN definido através do pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="44ff4-229">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="44ff4-230">No nosso Windows Holographic, versão 20H2, corrigimos um problema de configuração proxy para a ligação VPN.</span><span class="sxs-lookup"><span data-stu-id="44ff4-230">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="44ff4-231">Por favor, considere atualizar dispositivos para esta construção se pretender utilizar este fluxo.</span><span class="sxs-lookup"><span data-stu-id="44ff4-231">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="44ff4-232">Lançar Designer de Configuração do Windows.</span><span class="sxs-lookup"><span data-stu-id="44ff4-232">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="44ff4-233">Clique em **dispositivos Provision HoloLens,** em seguida, selecione o dispositivo-alvo e **next**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-233">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="44ff4-234">Insira o nome e o caminho do pacote.</span><span class="sxs-lookup"><span data-stu-id="44ff4-234">Enter package name and path.</span></span>
1. <span data-ttu-id="44ff4-235">Clique **em Switch para editor avançado.**</span><span class="sxs-lookup"><span data-stu-id="44ff4-235">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="44ff4-236">Configurações de **tempo de execução abertas**  ->  **ConectividadeProfiles**  ->  **VPN**  ->  **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-236">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="44ff4-237">Configure VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="44ff4-237">Configure VPNProfileName</span></span>
1. <span data-ttu-id="44ff4-238">Selecione ProfileType: **Native** or **Third Part**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-238">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="44ff4-239">Para o perfil nativo, selecione **NativeProtocolType**, em seguida, configurar servidor, política de encaminhamento, tipo de autenticação e outras definições.</span><span class="sxs-lookup"><span data-stu-id="44ff4-239">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="44ff4-240">Para o perfil de "Terceiros", configurar o URL do servidor, o nome da família do pacote plug-in VPN (apenas 3 configurações predefinidas) e personalizadas.</span><span class="sxs-lookup"><span data-stu-id="44ff4-240">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="44ff4-241">Exporte o seu pacote.</span><span class="sxs-lookup"><span data-stu-id="44ff4-241">Export your package.</span></span>
1. <span data-ttu-id="44ff4-242">Ligue os HoloLens e copie o ficheiro .ppkg ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44ff4-242">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="44ff4-243">No HoloLens, aplique o VPN .ppkg abrindo o menu Iniciar e selecionando **Definições** De Acesso à  ->  **Conta**  ->  **ou escola**  ->  **Adicionar ou remover pacote de provisionamento** -> Selecione o seu pacote VPN.</span><span class="sxs-lookup"><span data-stu-id="44ff4-243">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="44ff4-244">Criação de VPN via Intune</span><span class="sxs-lookup"><span data-stu-id="44ff4-244">Setting up VPN via Intune</span></span>
<span data-ttu-id="44ff4-245">Basta seguir os documentos do Intune para começar.</span><span class="sxs-lookup"><span data-stu-id="44ff4-245">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="44ff4-246">Ao seguir estes passos, tenha em mente os protocolos VPN incorporados que os dispositivos HoloLens suportam.</span><span class="sxs-lookup"><span data-stu-id="44ff4-246">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="44ff4-247">[Crie perfis VPN para ligar aos servidores VPN no Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="44ff4-247">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="44ff4-248">[Windows 10 e Windows Holographic device configurações para adicionar ligações VPN usando Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="44ff4-248">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="44ff4-249">Quando terminar, lembre-se de [atribuir o perfil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="44ff4-249">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="44ff4-250">VPN através de soluções MDM de 3º partido</span><span class="sxs-lookup"><span data-stu-id="44ff4-250">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="44ff4-251">Exemplo de ligação VPN de 3ª parte:</span><span class="sxs-lookup"><span data-stu-id="44ff4-251">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="44ff4-252">Exemplo nativo do IKEv2 VPN:</span><span class="sxs-lookup"><span data-stu-id="44ff4-252">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="44ff4-253">Desativação Wi-Fi em HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="44ff4-253">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="44ff4-254">Utilização da aplicação Definições em HoloLens</span><span class="sxs-lookup"><span data-stu-id="44ff4-254">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="44ff4-255">Abra o menu **Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="44ff4-255">Open the **Start** menu.</span></span>
1. <span data-ttu-id="44ff4-256">Selecione a aplicação **Definições** a partir do **Início** ou da lista **de Todas as Aplicações** no menu **'Início'** à direita.</span><span class="sxs-lookup"><span data-stu-id="44ff4-256">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="44ff4-257">A aplicação **Definições** será colocada automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="44ff4-257">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="44ff4-258">Selecione **Rede & Internet**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-258">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="44ff4-259">Selecione o interruptor de slider Wi-Fi para movê-lo para a posição **Off.**</span><span class="sxs-lookup"><span data-stu-id="44ff4-259">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="44ff4-260">Isto irá desligar os componentes RF do rádio Wi-Fi e desativar todas as funcionalidades Wi-Fi em HoloLens.</span><span class="sxs-lookup"><span data-stu-id="44ff4-260">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="44ff4-261">Quando o rádio Wi-Fi estiver desativado, os HoloLens não poderão carregar automaticamente os seus [espaços](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="44ff4-261">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="44ff4-262">Mova o interruptor de slider para a posição **On** para ligar o rádio Wi-Fi e restaurar a funcionalidade Wi-Fi no Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="44ff4-262">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="44ff4-263">O estado de rádio Wi-Fi selecionado **(Ligado** ou **Desligado)** persistirá através de reboots.</span><span class="sxs-lookup"><span data-stu-id="44ff4-263">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="44ff4-264">Identificação do endereço IP dos seus HoloLens na rede Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="44ff4-264">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="44ff4-265">Utilizando a aplicação Definições</span><span class="sxs-lookup"><span data-stu-id="44ff4-265">By using the Settings app</span></span>

1. <span data-ttu-id="44ff4-266">Abra o menu **Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="44ff4-266">Open the **Start** menu.</span></span>
1. <span data-ttu-id="44ff4-267">Selecione a aplicação **Definições** a partir do **Início** ou da lista **de Todas as Aplicações** no menu **'Início'** à direita.</span><span class="sxs-lookup"><span data-stu-id="44ff4-267">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="44ff4-268">A aplicação **Definições** será colocada automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="44ff4-268">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="44ff4-269">Selecione **Rede & Internet**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-269">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="44ff4-270">Desloque-se para baixo para baixo da lista de redes Wi-Fi disponíveis e selecione **propriedades de Hardware**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-270">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propriedades de hardware em configurações Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="44ff4-272">O endereço IP aparece ao lado **do endereço IPv4**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-272">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="44ff4-273">Usando comandos de voz</span><span class="sxs-lookup"><span data-stu-id="44ff4-273">By using voice commands</span></span>

<span data-ttu-id="44ff4-274">Dependendo da construção dos seus dispositivos, pode utilizar comandos de voz incorporados ou cortana para exibir o seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="44ff4-274">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="44ff4-275">Sobre as construções depois de [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) falar "Qual é o meu endereço IP?"</span><span class="sxs-lookup"><span data-stu-id="44ff4-275">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="44ff4-276">e será exibido.</span><span class="sxs-lookup"><span data-stu-id="44ff4-276">and it will be displayed.</span></span> <span data-ttu-id="44ff4-277">Para construções anteriores ou HoloLens (1ª gen) dizer "Hey Cortana, Qual é o meu endereço IP?"</span><span class="sxs-lookup"><span data-stu-id="44ff4-277">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="44ff4-278">e cortana mostrará e lerá o seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="44ff4-278">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="44ff4-279">Utilizando o Portal do Dispositivo Windows</span><span class="sxs-lookup"><span data-stu-id="44ff4-279">By using Windows Device Portal</span></span>

1. <span data-ttu-id="44ff4-280">Num navegador web no seu PC, abra o portal do [dispositivo](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="44ff4-280">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="44ff4-281">Navegue para a secção **de Networking.**</span><span class="sxs-lookup"><span data-stu-id="44ff4-281">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="44ff4-282">Esta secção apresenta o seu endereço IP e outras informações de rede.</span><span class="sxs-lookup"><span data-stu-id="44ff4-282">This section displays your IP address and other network information.</span></span> <span data-ttu-id="44ff4-283">Ao utilizar este método, pode copiar e colar o endereço IP no seu PC de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="44ff4-283">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="44ff4-284">Alterar endereço IP para endereço estático</span><span class="sxs-lookup"><span data-stu-id="44ff4-284">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="44ff4-285">Utilizando Definições</span><span class="sxs-lookup"><span data-stu-id="44ff4-285">By using Settings</span></span>
 
1. <span data-ttu-id="44ff4-286">Abra o menu **Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="44ff4-286">Open the **Start** menu.</span></span>
1. <span data-ttu-id="44ff4-287">Selecione a aplicação **Definições** a partir do **Início** ou da lista **de Todas as Aplicações** no menu **'Início'** à direita.</span><span class="sxs-lookup"><span data-stu-id="44ff4-287">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="44ff4-288">A aplicação **Definições** será colocada automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="44ff4-288">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="44ff4-289">Selecione **Rede & Internet**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-289">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="44ff4-290">Desloque-se para baixo para baixo da lista de redes Wi-Fi disponíveis e selecione **propriedades de Hardware**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-290">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="44ff4-291">Na janela de **definições IP de edição,** altere o primeiro campo para **Manual**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-291">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="44ff4-292">Insira a configuração IP desejada nos campos restantes e, em seguida, clique em **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-292">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="44ff4-293">Utilizando o Portal do Dispositivo Windows</span><span class="sxs-lookup"><span data-stu-id="44ff4-293">By using Windows Device Portal</span></span>

1. <span data-ttu-id="44ff4-294">Num navegador web no seu PC, abra o portal do [dispositivo](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="44ff4-294">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="44ff4-295">Navegue para a secção **de Networking.**</span><span class="sxs-lookup"><span data-stu-id="44ff4-295">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="44ff4-296">Selecione o botão **de configuração IPv4.**</span><span class="sxs-lookup"><span data-stu-id="44ff4-296">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="44ff4-297">Selecione **Utilize o seguinte endereço IP** e insira a configuração TCP/IP desejada.</span><span class="sxs-lookup"><span data-stu-id="44ff4-297">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="44ff4-298">Selecione **Utilize os seguintes endereços de servidor DNS** e introduza os endereços de servidor DNS preferidos e alternativos, se necessário.</span><span class="sxs-lookup"><span data-stu-id="44ff4-298">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="44ff4-299">Clique em **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="44ff4-299">Click **Save**.</span></span> 