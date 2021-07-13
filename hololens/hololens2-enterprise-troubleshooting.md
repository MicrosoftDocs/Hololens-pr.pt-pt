---
title: HoloLens implementação 2 e conseguiu resolver problemas com dispositivos
description: Resolução de problemas HoloLens 2 dispositivos em ambiente empresarial
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
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636882"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="92c35-104">Implementação de resolução de problemas e dispositivos geridos</span><span class="sxs-lookup"><span data-stu-id="92c35-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="92c35-105">Este artigo descreve como resolver várias questões ou responder a questões relativas à implementação e gestão de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="92c35-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="92c35-106">Antes de iniciar qualquer procedimento de resolução de problemas, certifique-se de que o seu dispositivo está carregado até **20 a 40%** da capacidade da bateria, se possível.</span><span class="sxs-lookup"><span data-stu-id="92c35-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="92c35-107">As [luzes indicadoras](hololens2-setup.md#lights-that-indicate-the-battery-level) da bateria localizadas sob o botão de alimentação são uma forma rápida de verificar a capacidade da bateria sem iniciar sessão no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92c35-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="92c35-108">Resolução de problemas da EAP</span><span class="sxs-lookup"><span data-stu-id="92c35-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="92c35-109">Resolução de problemas wi-fi</span><span class="sxs-lookup"><span data-stu-id="92c35-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="92c35-110">Resolução de problemas de rede</span><span class="sxs-lookup"><span data-stu-id="92c35-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="92c35-111">Não pode entrar num dispositivo de HoloLens previamente configurado</span><span class="sxs-lookup"><span data-stu-id="92c35-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="92c35-112">Não pode iniciar sessão depois de atualizar para Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="92c35-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="92c35-113">Resolução de problemas do piloto automático</span><span class="sxs-lookup"><span data-stu-id="92c35-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="92c35-114">Perguntas frequentes de dispositivos de HoloLens geridos</span><span class="sxs-lookup"><span data-stu-id="92c35-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="92c35-115">Resolução de problemas da EAP</span><span class="sxs-lookup"><span data-stu-id="92c35-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="92c35-116">Verifique duas vezes Wi-Fi perfil tem as definições certas:</span><span class="sxs-lookup"><span data-stu-id="92c35-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="92c35-117">O tipo EAP é configurado corretamente, tipos comuns de EAP: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="92c35-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="92c35-118">Wi-Fi nome SSID é certo e coincide com a cadeia HEX.</span><span class="sxs-lookup"><span data-stu-id="92c35-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="92c35-119">Para o EAP-TLS, o TrustedRootCA contém o hash SHA-1 do certificado de CA de raiz fidedigna do servidor.</span><span class="sxs-lookup"><span data-stu-id="92c35-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="92c35-120">No Windows comando "certutil.exe-dump cert_file_name" do PC mostrará a cadeia de haxixe SHA-1 de um certificado.</span><span class="sxs-lookup"><span data-stu-id="92c35-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="92c35-121">Colete a captura de pacotes de rede nos registos do Access Point ou do Controlador ou do servidor AAA para saber onde a sessão EAP falha.</span><span class="sxs-lookup"><span data-stu-id="92c35-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="92c35-122">Se a identidade EAP fornecida por HoloLens não for esperada, verifique se a identidade foi corretamente fornecida através de Wi-Fi perfil ou certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="92c35-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="92c35-123">Se o servidor rejeitar HoloLens certificado de cliente, verifique se o certificado de cliente exigido foi a provisionado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92c35-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="92c35-124">Se HoloLens rejeitar o certificado do servidor, verifique se o certificado de CA raiz do servidor foi a provisionado no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="92c35-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="92c35-125">Se o perfil da empresa for previsto através de Wi-Fi pacote de provisionamento, considere a aplicação do pacote de provisionamento num pc Windows 10.</span><span class="sxs-lookup"><span data-stu-id="92c35-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="92c35-126">Se também falhar Windows 10 PC, siga o guia de resolução de problemas de autenticação do cliente Windows 802.1X.</span><span class="sxs-lookup"><span data-stu-id="92c35-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="92c35-127">Envie-nos feedback através do Feedback Hub.</span><span class="sxs-lookup"><span data-stu-id="92c35-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="92c35-128">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="92c35-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="92c35-129">Resolução de problemas Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="92c35-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="92c35-130">Aqui estão algumas coisas a experimentar se não consegue ligar o seu HoloLens a uma rede Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="92c35-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="92c35-131">Certifique-se de que Wi-Fi está ligado.</span><span class="sxs-lookup"><span data-stu-id="92c35-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="92c35-132">Para verificar, utilize o gesto Iniciar e, em seguida, selecione Definições > Rede & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="92c35-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="92c35-133">Se Wi-Fi estiver ligado, tente desligá-lo e depois ligado novamente.</span><span class="sxs-lookup"><span data-stu-id="92c35-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="92c35-134">Aproxime o computador do router ou do ponto de acesso.</span><span class="sxs-lookup"><span data-stu-id="92c35-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="92c35-135">Reinicie o router Wi-Fi e reinicie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="92c35-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="92c35-136">Tente ligar de novo.</span><span class="sxs-lookup"><span data-stu-id="92c35-136">Try connecting again.</span></span>
4. <span data-ttu-id="92c35-137">Se nenhuma destas coisas funcionar, verifique se o seu router está a utilizar o firmware mais recente.</span><span class="sxs-lookup"><span data-stu-id="92c35-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="92c35-138">Pode encontrar esta informação no site do fabricante.</span><span class="sxs-lookup"><span data-stu-id="92c35-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="92c35-139">Quando você assina uma conta empresarial ou organizacional no dispositivo, também pode aplicar a política de Gestão de Dispositivos Móveis (MDM), se a política for configurada pelo seu administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="92c35-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

[<span data-ttu-id="92c35-140">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="92c35-140">Back to list</span></span>](#list)

## <a name="network-troubleshooting"></a><span data-ttu-id="92c35-141">Resolução de problemas de rede</span><span class="sxs-lookup"><span data-stu-id="92c35-141">Network Troubleshooting</span></span>
<span data-ttu-id="92c35-142">Se os problemas de rede forem um obstáculo à implementação e utilização com sucesso HoloLens 2 na sua organização, configurar o Fiddler e/ou o Wireshark para capturar e analisar o tráfego HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="92c35-142">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, configure Fiddler and/or Wireshark to capture and analyze HTTP/HTTPS traffic.</span></span> 

### <a name="configure-fiddler-to-capture-http-traffic"></a><span data-ttu-id="92c35-143">Configure o violinista para capturar o tráfego HTTP</span><span class="sxs-lookup"><span data-stu-id="92c35-143">Configure Fiddler to capture HTTP traffic</span></span>
<span data-ttu-id="92c35-144">O Fiddler é um proxy de depuração web e é usado para resolver problemas http(s).</span><span class="sxs-lookup"><span data-stu-id="92c35-144">Fiddler is a web debugging proxy and is used to troubleshoot HTTP(S) issues.</span></span> <span data-ttu-id="92c35-145">Captura todos os pedidos HTTP que o computador faz e regista tudo o que lhe está associado.</span><span class="sxs-lookup"><span data-stu-id="92c35-145">It captures every HTTP request the computer makes and records everything associated with it.</span></span> <span data-ttu-id="92c35-146">Descobrir problemas de autenticação de utilizador final para as suas aplicações HTTPS impulsiona uma melhor produtividade e eficiência para os seus casos de utilização HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="92c35-146">Uncovering end-user authentication issues for your HTTPS apps drives better productivity and efficiency for your target HoloLens 2 use cases.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="92c35-147">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="92c35-147">Prerequisites</span></span>
 
- <span data-ttu-id="92c35-148">HoloLens 2 dispositivos e o seu PC devem estar na mesma rede</span><span class="sxs-lookup"><span data-stu-id="92c35-148">HoloLens 2 devices and your PC must be on the same network</span></span>
- <span data-ttu-id="92c35-149">Note o endereço IP do seu PC</span><span class="sxs-lookup"><span data-stu-id="92c35-149">Note the IP address of your PC</span></span>

#### <a name="install-and-configure-fiddler"></a><span data-ttu-id="92c35-150">Instalar e Configurar Violinista</span><span class="sxs-lookup"><span data-stu-id="92c35-150">Install and Configure Fiddler</span></span>

1. <span data-ttu-id="92c35-151">No seu PC - [instale](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) e inicie o Fiddler.</span><span class="sxs-lookup"><span data-stu-id="92c35-151">On your PC - [install](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) and start Fiddler.</span></span>  
1. <span data-ttu-id="92c35-152">No seu PC - configure o Fiddler para permitir a ligação de computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="92c35-152">On your PC - configure Fiddler to allow remote computers to connect.</span></span>
    1. <span data-ttu-id="92c35-153">Ir a Fiddler Definições -> Conexões</span><span class="sxs-lookup"><span data-stu-id="92c35-153">Go to Fiddler Settings -> Connections</span></span>
    1. <span data-ttu-id="92c35-154">Note a porta de audição para Violinista (por defeito é 8866)</span><span class="sxs-lookup"><span data-stu-id="92c35-154">Note the listening port for Fiddler (default is 8866)</span></span>
    1. <span data-ttu-id="92c35-155">Verifique permitir a ligação de computadores remotos</span><span class="sxs-lookup"><span data-stu-id="92c35-155">Check Allow remote computers to connect</span></span>
    1. <span data-ttu-id="92c35-156">Clicar em Guardar</span><span class="sxs-lookup"><span data-stu-id="92c35-156">Click Save</span></span>
3. <span data-ttu-id="92c35-157">No seu HoloLens 2 – configurar o Violinista como o servidor proxy<sup>1</sup>:</span><span class="sxs-lookup"><span data-stu-id="92c35-157">On your HoloLens 2 – configure Fiddler as the proxy server<sup>1</sup>:</span></span>
    1. <span data-ttu-id="92c35-158">Abra a menu Iniciar e selecione Definições</span><span class="sxs-lookup"><span data-stu-id="92c35-158">Open the Start menu and select Settings</span></span>
    1. <span data-ttu-id="92c35-159">Selecione Rede & Internet e, em seguida, Proxy no menu esquerdo</span><span class="sxs-lookup"><span data-stu-id="92c35-159">Select Network & Internet and then Proxy on the left menu</span></span>
    1. <span data-ttu-id="92c35-160">Desloque-se para baixo para configuração de procuração manual e alterne Use um servidor proxy para On</span><span class="sxs-lookup"><span data-stu-id="92c35-160">Scroll down to Manual proxy setup and toggle Use a proxy server to On</span></span>
    1. <span data-ttu-id="92c35-161">Insira o endereço IP do PC onde o Fiddler está instalado</span><span class="sxs-lookup"><span data-stu-id="92c35-161">Enter the IP address of the PC where Fiddler is installed</span></span>
    1. <span data-ttu-id="92c35-162">Introduza o número de porta acima indicado (o padrão é 8866)</span><span class="sxs-lookup"><span data-stu-id="92c35-162">Enter the port number noted above (default is 8866)</span></span>
    1. <span data-ttu-id="92c35-163">Clicar em Guardar</span><span class="sxs-lookup"><span data-stu-id="92c35-163">Click Save</span></span>

<span data-ttu-id="92c35-164"><sup>1</sup> Para as construções 20279.1006+ (Insiders e o próximo lançamento), utilize os seguintes passos para configurar o proxy:</span><span class="sxs-lookup"><span data-stu-id="92c35-164"><sup>1</sup> For builds 20279.1006+ (Insiders and the upcoming release), use the following steps to configure proxy:</span></span>
1. <span data-ttu-id="92c35-165">Abra a menu Iniciar e vá para a página propriedades da sua rede de Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="92c35-165">Open the Start menu and go to your Wi-Fi Network’s Properties page</span></span> 
1. <span data-ttu-id="92c35-166">Desça até Proxy</span><span class="sxs-lookup"><span data-stu-id="92c35-166">Scroll down to Proxy</span></span>
1. <span data-ttu-id="92c35-167">Alteração para Configuração Manual</span><span class="sxs-lookup"><span data-stu-id="92c35-167">Change to Manual Setup</span></span>
1. <span data-ttu-id="92c35-168">Insira o endereço IP do PC onde o Fiddler está instalado</span><span class="sxs-lookup"><span data-stu-id="92c35-168">Enter the IP address of the PC where Fiddler is installed</span></span>
1. <span data-ttu-id="92c35-169">Introduza o número da porta acima indicado.</span><span class="sxs-lookup"><span data-stu-id="92c35-169">Enter the port number noted above.</span></span> <span data-ttu-id="92c35-170">(o padrão é 8866)</span><span class="sxs-lookup"><span data-stu-id="92c35-170">(default is 8866)</span></span>
1. <span data-ttu-id="92c35-171">Clique em Aplicar</span><span class="sxs-lookup"><span data-stu-id="92c35-171">Click Apply</span></span>
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a><span data-ttu-id="92c35-172">Desencriptar tráfego HTTPS de HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="92c35-172">Decrypt HTTPS traffic from HoloLens 2</span></span>

1. <span data-ttu-id="92c35-173">No seu PC – exporte o certificado Fiddler.</span><span class="sxs-lookup"><span data-stu-id="92c35-173">On your PC – export the Fiddler certificate.</span></span>
    1. <span data-ttu-id="92c35-174">Vá ao Fiddler Definições -> HTTPS e expanda a Definições Avançada</span><span class="sxs-lookup"><span data-stu-id="92c35-174">Go to Fiddler Settings -> HTTPS and expand Advanced Settings</span></span>
    2. <span data-ttu-id="92c35-175">Clique no certificado de Violino de Exportação.</span><span class="sxs-lookup"><span data-stu-id="92c35-175">Click Export Fiddler certificate.</span></span> <span data-ttu-id="92c35-176">Poupará para o seu ambiente de trabalho</span><span class="sxs-lookup"><span data-stu-id="92c35-176">It will save to your desktop</span></span>
    3. <span data-ttu-id="92c35-177">Mova o certificado para a pasta Downloads no seu HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="92c35-177">Move the certificate over to the Downloads folder on your HoloLens 2</span></span>

2.  <span data-ttu-id="92c35-178">No seu HoloLens 2 - importe o certificado Fiddler.</span><span class="sxs-lookup"><span data-stu-id="92c35-178">On your HoloLens 2 - import the Fiddler certificate.</span></span>
    1. <span data-ttu-id="92c35-179">Ir para Definições -> atualização e segurança -> certificados</span><span class="sxs-lookup"><span data-stu-id="92c35-179">Go to Settings -> Update and Security -> Certificates</span></span>
    2. <span data-ttu-id="92c35-180">Clique em Instalar Certificado, navegue na pasta Downloads e selecione o certificado Fiddler</span><span class="sxs-lookup"><span data-stu-id="92c35-180">Click Install Certificate, browse to the Downloads folder and select the Fiddler certificate</span></span>
    3. <span data-ttu-id="92c35-181">Alterar a localização da loja para máquina local</span><span class="sxs-lookup"><span data-stu-id="92c35-181">Change Store Location to Local Machine</span></span>
    4. <span data-ttu-id="92c35-182">Alterar Loja de Certificados para raiz</span><span class="sxs-lookup"><span data-stu-id="92c35-182">Change Certificate Store to root</span></span>
    5. <span data-ttu-id="92c35-183">Selecione instalar</span><span class="sxs-lookup"><span data-stu-id="92c35-183">Select Install</span></span>
    6. <span data-ttu-id="92c35-184">Confirme que o certificado está na lista de certificados.</span><span class="sxs-lookup"><span data-stu-id="92c35-184">Confirm the certificate is showing in the list of certificates.</span></span> <span data-ttu-id="92c35-185">Caso contrário, repita os passos acima</span><span class="sxs-lookup"><span data-stu-id="92c35-185">If not, repeat the above steps</span></span>

#### <a name="inspect-https-sessions"></a><span data-ttu-id="92c35-186">Inspecionar sessões HTTP(S)</span><span class="sxs-lookup"><span data-stu-id="92c35-186">Inspect HTTP(S) sessions</span></span>

<span data-ttu-id="92c35-187">No seu PC, o Fiddler apresentará as sessões HTTP(S) ao vivo do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="92c35-187">On your PC, Fiddler will show the HoloLens 2’s live HTTP(S) sessions.</span></span> <span data-ttu-id="92c35-188">O painel de inspetores em Violino pode mostrar http(S) pedido/resposta em diferentes pontos de vista - por exemplo, a visão "Raw" mostra o pedido bruto ou a resposta em texto simples.</span><span class="sxs-lookup"><span data-stu-id="92c35-188">The Inspectors panel in Fiddler can show HTTP(S) request/response in different views - for example, the “Raw” view shows the raw request or response in plain text.</span></span> 

### <a name="configure-wireshark-to-capture-network-traffic"></a><span data-ttu-id="92c35-189">Configure o Wireshark para capturar o tráfego da rede</span><span class="sxs-lookup"><span data-stu-id="92c35-189">Configure Wireshark to capture network traffic</span></span>
<span data-ttu-id="92c35-190">O Wireshark é um analisador de protocolo de rede e é utilizado para inspecionar o tráfego TCP/UDP de e para os seus HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="92c35-190">Wireshark is a network protocol analyzer and is used to inspect TCP/UDP traffic from and to your HoloLens 2 devices.</span></span> <span data-ttu-id="92c35-191">Isto torna fácil identificar que tráfego está atravessando a sua rede para o seu HoloLens 2, quanto dela, com que frequência, quanta latência existe entre certos lúpulos, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="92c35-191">This makes it easy to identify what traffic is crossing your network to your HoloLens 2, how much of it, how frequently, how much latency there is between certain hops, and so forth.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="92c35-192">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="92c35-192">Prerequisites:</span></span>
- <span data-ttu-id="92c35-193">O PC deve ter acesso à Internet e apoiar a partilha de Internet ao longo de Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="92c35-193">PC must have internet access and support Internet sharing over Wi-Fi</span></span>

#### <a name="install-and-configure-wireshark"></a><span data-ttu-id="92c35-194">Instalar e Configurar o Arame</span><span class="sxs-lookup"><span data-stu-id="92c35-194">Install and Configure Wireshark</span></span>
1. <span data-ttu-id="92c35-195">No seu PC - instale [o Wireshark](https://www.wireshark.org/#download)</span><span class="sxs-lookup"><span data-stu-id="92c35-195">On your PC - install [Wireshark](https://www.wireshark.org/#download)</span></span> 
1. <span data-ttu-id="92c35-196">No seu PC - permita ao Hotspot Mobile partilhar a sua ligação à Internet a partir de Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="92c35-196">On your PC - enable Mobile hotspot to share your Internet connection from Wi-Fi.</span></span>
1. <span data-ttu-id="92c35-197">No seu PC - inicie o Wireshark e capture o tráfego a partir da interface de hotspot Mobile.</span><span class="sxs-lookup"><span data-stu-id="92c35-197">On your PC - start Wireshark and capture traffic from the Mobile hotspot interface.</span></span> 
1. <span data-ttu-id="92c35-198">No seu HoloLens 2 – altere a sua rede de Wi-Fi para o hotspot Mobile do PC.</span><span class="sxs-lookup"><span data-stu-id="92c35-198">On your HoloLens 2 – change its Wi-Fi network to the PC’s Mobile hotspot.</span></span> <span data-ttu-id="92c35-199">HoloLens tráfego IP 2 aparecerão em Wireshark.</span><span class="sxs-lookup"><span data-stu-id="92c35-199">HoloLens 2 IP traffic will show up in Wireshark.</span></span>

#### <a name="analyze-wireshark-logs"></a><span data-ttu-id="92c35-200">Analisar troncos de arame</span><span class="sxs-lookup"><span data-stu-id="92c35-200">Analyze Wireshark logs</span></span>
<span data-ttu-id="92c35-201">Os filtros de arame podem ajudar a filtrar os pacotes de interesses.</span><span class="sxs-lookup"><span data-stu-id="92c35-201">Wireshark filters can help filtering out the packets of interests.</span></span> 

<span data-ttu-id="92c35-202">Confira o [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)original.</span><span class="sxs-lookup"><span data-stu-id="92c35-202">Check out the original [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span></span>

[<span data-ttu-id="92c35-203">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="92c35-203">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="92c35-204">Não pode entrar num dispositivo de HoloLens previamente configurado</span><span class="sxs-lookup"><span data-stu-id="92c35-204">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="92c35-205">Se o seu dispositivo foi previamente configurado para outra pessoa, seja para um cliente ou para um ex-funcionário, e não tiver a sua palavra-passe para desbloquear o dispositivo, pode usar o Intune para [limpar](/intune/remote-actions/devices-wipe) remotamente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92c35-205">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="92c35-206">Em seguida, o aparelho volta a piscar sozinho.</span><span class="sxs-lookup"><span data-stu-id="92c35-206">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="92c35-207">Quando limpar o dispositivo, certifique-se de deixar o **estado de inscrição e a conta do utilizador** sem controlo.</span><span class="sxs-lookup"><span data-stu-id="92c35-207">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>

[<span data-ttu-id="92c35-208">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="92c35-208">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="92c35-209">Não pode iniciar sessão depois de atualizar para Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="92c35-209">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="92c35-210">Sintomas</span><span class="sxs-lookup"><span data-stu-id="92c35-210">Symptoms</span></span>
- <span data-ttu-id="92c35-211">A utilização de PIN para logon falhará após a entrada no PIN correto.</span><span class="sxs-lookup"><span data-stu-id="92c35-211">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="92c35-212">A utilização do método de início de sessão da Web falhará após a sua assinatura na página web.</span><span class="sxs-lookup"><span data-stu-id="92c35-212">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="92c35-213">O dispositivo não está listado como "Azure AD unidos" em dispositivos de > [portal Azure](https://portal.azure.com/) -> Azure Ative Directory..</span><span class="sxs-lookup"><span data-stu-id="92c35-213">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="92c35-214">Causa</span><span class="sxs-lookup"><span data-stu-id="92c35-214">Cause</span></span>
<span data-ttu-id="92c35-215">O dispositivo impactado pode ter sido apagado do inquilino AZure AD.</span><span class="sxs-lookup"><span data-stu-id="92c35-215">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="92c35-216">Por exemplo, isto pode acontecer porque:</span><span class="sxs-lookup"><span data-stu-id="92c35-216">For example, this may happen because:</span></span>

- <span data-ttu-id="92c35-217">Um administrador ou utilizador eliminou o dispositivo no portal Azure ou na utilização do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92c35-217">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="92c35-218">O dispositivo foi removido do inquilino da AD Azure devido à inatividade.</span><span class="sxs-lookup"><span data-stu-id="92c35-218">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="92c35-219">Para um ambiente eficientemente gerido, recomendamos normalmente que os administradores de TI [removam dispositivos inativos e velhos do seu inquilino AD Azure.](/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="92c35-219">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="92c35-220">Quando um dispositivo impactado tentar contactar novamente o inquilino Azure AD depois de ter sido eliminado, deixará de autenticar com a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="92c35-220">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="92c35-221">Este efeito é muitas vezes invisível para o utilizador do dispositivo, uma vez que a logon em cache via PIN continuará a permitir que o utilizador se insi.ndo.</span><span class="sxs-lookup"><span data-stu-id="92c35-221">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="92c35-222">Mitigação</span><span class="sxs-lookup"><span data-stu-id="92c35-222">Mitigation</span></span>
<span data-ttu-id="92c35-223">Não existe atualmente forma de adicionar um dispositivo de HoloLens eliminado de volta ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="92c35-223">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="92c35-224">Os dispositivos afetados terão de ser reassusados seguindo as instruções de [reflashing](hololens-recovery.md#clean-reflash-the-device)do seu dispositivo .</span><span class="sxs-lookup"><span data-stu-id="92c35-224">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

[<span data-ttu-id="92c35-225">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="92c35-225">Back to list</span></span>](#list)

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="92c35-226">Resolução de problemas do piloto automático</span><span class="sxs-lookup"><span data-stu-id="92c35-226">Autopilot Troubleshooting</span></span>

<span data-ttu-id="92c35-227">Os seguintes artigos podem ser um recurso útil para você aprender mais informações e resolver problemas de piloto automático Problemas, no entanto, esteja ciente de que estes artigos são baseados em Windows 10 Desktop e nem todas as informações podem ser aplicadas a HoloLens:</span><span class="sxs-lookup"><span data-stu-id="92c35-227">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="92c35-228">Windows Autopilot - questões conhecidas</span><span class="sxs-lookup"><span data-stu-id="92c35-228">Windows Autopilot - known issues</span></span>](/mem/autopilot/known-issues)
- [<span data-ttu-id="92c35-229">Resolução de problemas Windows problemas de inscrição de dispositivos em Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="92c35-229">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="92c35-230">Windows Autopilot - Conflitos Políticos</span><span class="sxs-lookup"><span data-stu-id="92c35-230">Windows Autopilot - Policy Conflicts</span></span>](/mem/autopilot/policy-conflicts)

[<span data-ttu-id="92c35-231">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="92c35-231">Back to list</span></span>](#list)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="92c35-232">Perguntas frequentes de dispositivos de HoloLens geridos</span><span class="sxs-lookup"><span data-stu-id="92c35-232">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="92c35-233">Posso utilizar System Center Configuration Manager (SCCM) para gerir dispositivos HoloLens?</span><span class="sxs-lookup"><span data-stu-id="92c35-233">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="92c35-234">N.º</span><span class="sxs-lookup"><span data-stu-id="92c35-234">No.</span></span> <span data-ttu-id="92c35-235">Tem de usar um sistema MDM para gerir HoloLens dispositivos.</span><span class="sxs-lookup"><span data-stu-id="92c35-235">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="92c35-236">Posso utilizar os Serviços de Domínio do Diretório Ativo (DS AD) para gerir HoloLens contas de utilizador?</span><span class="sxs-lookup"><span data-stu-id="92c35-236">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="92c35-237">N.º</span><span class="sxs-lookup"><span data-stu-id="92c35-237">No.</span></span> <span data-ttu-id="92c35-238">Tem de utilizar Azure Ative Directory (Azure AD) para gerir as contas dos utilizadores para HoloLens dispositivos.</span><span class="sxs-lookup"><span data-stu-id="92c35-238">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="92c35-239">A HoloLens é capaz de matricular automaticamente os Sistemas automatizados de captura de dados (ADCS).</span><span class="sxs-lookup"><span data-stu-id="92c35-239">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="92c35-240">N.º</span><span class="sxs-lookup"><span data-stu-id="92c35-240">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="92c35-241">Pode HoloLens participar na Autenticação integrada Windows?</span><span class="sxs-lookup"><span data-stu-id="92c35-241">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="92c35-242">N.º</span><span class="sxs-lookup"><span data-stu-id="92c35-242">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="92c35-243">A HoloLens suporta a marca?</span><span class="sxs-lookup"><span data-stu-id="92c35-243">Does HoloLens support branding?</span></span>

<span data-ttu-id="92c35-244">N.º</span><span class="sxs-lookup"><span data-stu-id="92c35-244">No.</span></span> <span data-ttu-id="92c35-245">No entanto, pode contornar esta questão utilizando uma das seguintes abordagens:</span><span class="sxs-lookup"><span data-stu-id="92c35-245">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="92c35-246">Crie uma aplicação personalizada e, em seguida, ative o [modo Quiosque](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="92c35-246">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="92c35-247">A aplicação personalizada pode ter marca, e pode lançar outras aplicações (como o Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="92c35-247">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="92c35-248">Altere todas as fotos do perfil do utilizador no Azure AD para o logótipo da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="92c35-248">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="92c35-249">No entanto, isto pode não ser desejável para todos os cenários.</span><span class="sxs-lookup"><span data-stu-id="92c35-249">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="92c35-250">Que capacidades de registo HoloLens 2 oferecem?</span><span class="sxs-lookup"><span data-stu-id="92c35-250">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="92c35-251">O registo está limitado a vestígios que podem ser capturados em cenários de desenvolvimento ou resolução de problemas, ou telemetria que os dispositivos enviam para servidores da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92c35-251">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="92c35-252">Perguntas sobre a segurança de dispositivos de HoloLens</span><span class="sxs-lookup"><span data-stu-id="92c35-252">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="92c35-253">Consulte as [nossas informações de segurança HoloLens 2.](security-overview.md)</span><span class="sxs-lookup"><span data-stu-id="92c35-253">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="92c35-254">Para HoloLens dispositivos da 1ª Gen, por favor [reveja este FAQ](hololens1-faq-security.yml).</span><span class="sxs-lookup"><span data-stu-id="92c35-254">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.yml).</span></span>

[<span data-ttu-id="92c35-255">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="92c35-255">Back to list</span></span>](#list)
