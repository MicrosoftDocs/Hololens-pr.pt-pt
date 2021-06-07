---
title: Inscrição empresarial de dispositivos HoloLens em endereço MAC restrito Wi-Fi Ambiente
description: Como endereçar MAC para rede em dispositivos HoloLens 2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379867"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="bd6c0-103">Inscrição empresarial de dispositivos HoloLens em endereço MAC restrito Wi-Fi Ambiente</span><span class="sxs-lookup"><span data-stu-id="bd6c0-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="bd6c0-104">Este documento descreverá um cenário comum que identificamos em ambientes de clientes onde o Wi-Fi é restrito por endereços MAC, ou os certificados são obrigados a aderir a redes sem fios.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="bd6c0-105">Cenário de Exemplo</span><span class="sxs-lookup"><span data-stu-id="bd6c0-105">Example Scenario</span></span>

<span data-ttu-id="bd6c0-106">Muitos clientes em ambientes seguros têm restrições nas suas redes sem fios ou com fios que apenas permitirão que dispositivos aprovados (baseados em endereços MAC) se conectem com sucesso.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="bd6c0-107">Isto pode ser aplicado através da filtragem do Endereço MAC num Ponto de Acesso Sem Fios ou através de um servidor DHCP.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="bd6c0-108">Além disso, algumas redes sem fios podem ser protegidas com PEAP, o que requer que um certificado seja aplicado ao dispositivo antes de autenticar na rede Sem Fios.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="bd6c0-109">Neste cenário, dois requisitos-chave podem introduzir atrasos ou exigir uma intervenção manual ao juntar dispositivos HoloLens à rede:</span><span class="sxs-lookup"><span data-stu-id="bd6c0-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="bd6c0-110">O certificado PEAP sem fios deve ser aplicado ao dispositivo antes de o dispositivo se juntar com sucesso à rede sem fios.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="bd6c0-111">O endereço MAC do adaptador Wi-Fi HoloLens deve estar registado.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="bd6c0-112">Os principais desafios com os requisitos acima referidos são:</span><span class="sxs-lookup"><span data-stu-id="bd6c0-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="bd6c0-113">O Endereço MAC só pode ser identificado a partir da aplicação Definições no dispositivo ou do Intune após uma inscrição bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="bd6c0-114">Sem o endereço MAC, o dispositivo não pode aderir à Rede Wi-Fi para iniciar a inscrição.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="bd6c0-115">As soluções manuais para estes desafios requerem que um técnico interaja com o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="bd6c0-116">Soluções</span><span class="sxs-lookup"><span data-stu-id="bd6c0-116">Solutions</span></span>

<span data-ttu-id="bd6c0-117">Existem muitas formas de melhorar esta situação, dependendo das infraestruturas disponíveis no ambiente.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="bd6c0-118">Solução</span><span class="sxs-lookup"><span data-stu-id="bd6c0-118">Solution</span></span> | <span data-ttu-id="bd6c0-119">Benefícios</span><span class="sxs-lookup"><span data-stu-id="bd6c0-119">Benefits</span></span> | <span data-ttu-id="bd6c0-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd6c0-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="bd6c0-121">Pacote de Provisionamento com Adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="bd6c0-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="bd6c0-122">Melhora a experiência da OOBE e permite uma experiência técnica mais rápida.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="bd6c0-123">HoloLens compatível com o adaptador USB-C Hub + Ethernet, e o técnico ainda terá de interagir com o dispositivo para captura MAC e finalização OOBE</span><span class="sxs-lookup"><span data-stu-id="bd6c0-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="bd6c0-124">Piloto automático com registo intune sobre ethernet</span><span class="sxs-lookup"><span data-stu-id="bd6c0-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="bd6c0-125">Trata-se de uma ligação e registo único do dispositivo ao ambiente do cliente.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="bd6c0-126">A captura mac pode ser concluída sem necessidade de interagir com o dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd6c0-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="bd6c0-127">Intune habilitado para o cliente inquilino AAD e um adaptador Ethernet USB-C compatível com HoloLens</span><span class="sxs-lookup"><span data-stu-id="bd6c0-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="bd6c0-128">Relatório automatizado de endereços MAC</span><span class="sxs-lookup"><span data-stu-id="bd6c0-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="bd6c0-129">Quando os dispositivos são registados no inquilino Intune, um script pode reportar o endereço MAC ao técnico.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="bd6c0-130">Cmdlets Intune PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd6c0-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="bd6c0-131">Pacote de Provisionamento com Adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="bd6c0-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="bd6c0-132">Se a rede com fios também estiver sujeita a restrições MAC, então o endereço MAC do adaptador USB-C Hub + Ethernet também terá de ser pré-aprovado.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="bd6c0-133">Deve ter-se cuidado com este adaptador, pois permitirá o acesso à rede a partir de outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="bd6c0-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd6c0-134">Requirements</span></span>

- <span data-ttu-id="bd6c0-135">Porta de rede com fios com acesso à rede de clientes</span><span class="sxs-lookup"><span data-stu-id="bd6c0-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="bd6c0-136">HoloLens Compatível COM O Hub USB-C com o adaptador Ethernet — Qualquer adaptador que não exija controladores adicionais ou instalações de aplicações deve ser adequado.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="bd6c0-137">Pacote de provisionamento que contenha:</span><span class="sxs-lookup"><span data-stu-id="bd6c0-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="bd6c0-138">Contendo informações e certificados de rede sem fios</span><span class="sxs-lookup"><span data-stu-id="bd6c0-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="bd6c0-139">Opcionalmente contendo informações de inscrição para o Azure AD da Organização</span><span class="sxs-lookup"><span data-stu-id="bd6c0-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="bd6c0-140">Contendo quaisquer outras definições de provisionamento necessárias</span><span class="sxs-lookup"><span data-stu-id="bd6c0-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="bd6c0-141">Processo</span><span class="sxs-lookup"><span data-stu-id="bd6c0-141">Process</span></span>

<span data-ttu-id="bd6c0-142">O Processo pode variar dependendo do nível de software do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="bd6c0-143">Se o dispositivo tiver a [atualização de maio de 2004,](hololens-release-notes.md#windows-holographic-version-2004)siga os passos abaixo.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="bd6c0-144">Coloque o pacote de provisionamento na raiz de uma pen USB e ligue-o ao Hub.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="bd6c0-145">Ligue o cabo Ethernet ao adaptador Hub + Ethernet.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="bd6c0-146">Ligue o hub USB-C ao dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="bd6c0-147">Ligue os HoloLens e coloque o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="bd6c0-148">Pressione o **botão Volume Down e Power** para aplicar o pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="bd6c0-149">O técnico pode agora seguir o OOBE e, quando estiver concluído, abrir a App Definições para recuperar o Endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="bd6c0-150">Se o dispositivo tiver um sistema operativo antes da [atualização de maio de 2004,](hololens-release-notes.md#windows-holographic-version-2004)siga os passos abaixo.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="bd6c0-151">Ligue os HoloLens e ligue o dispositivo a um PC.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="bd6c0-152">O dispositivo deve aparecer no PC como um dispositivo de armazenamento de ficheiros.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="bd6c0-153">Copiar o pacote de provisionamento para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd6c0-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="bd6c0-154">Ligue o cabo Ethernet ao centro.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="bd6c0-155">Ligue o hub USB-C ao dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="bd6c0-156">Coloque os HoloLens</span><span class="sxs-lookup"><span data-stu-id="bd6c0-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="bd6c0-157">Pressione o botão **Volume Down e Power** para aplicar o pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="bd6c0-158">O técnico pode agora seguir o OOBE e, quando estiver concluído, abrir a App Definições para recuperar o Endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="bd6c0-159">Benefícios</span><span class="sxs-lookup"><span data-stu-id="bd6c0-159">Benefits</span></span>

<span data-ttu-id="bd6c0-160">Isto permitirá que um "único toque" do dispositivo, aplique o pacote de provisionamento correto e recolha o endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="bd6c0-161">Os pacotes de provisionamento podem ser criados seguindo as orientações aqui.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="bd6c0-162">Piloto automático com inscrição intune</span><span class="sxs-lookup"><span data-stu-id="bd6c0-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="bd6c0-163">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd6c0-163">Requirements</span></span>

- <span data-ttu-id="bd6c0-164">Porta de rede com fios com acesso à rede de clientes</span><span class="sxs-lookup"><span data-stu-id="bd6c0-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="bd6c0-165">Dispositivos HoloLens em execução Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="bd6c0-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="bd6c0-166">Adaptador ethernet USB-C compatível com HoloLens</span><span class="sxs-lookup"><span data-stu-id="bd6c0-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="bd6c0-167">Intune configurado e habilitado para o cliente Inquilino</span><span class="sxs-lookup"><span data-stu-id="bd6c0-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="bd6c0-168">Dispositivo registado para Piloto Automático e importado para o Cliente Inquilino</span><span class="sxs-lookup"><span data-stu-id="bd6c0-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="bd6c0-169">Políticas intune definidas para o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="bd6c0-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="bd6c0-170">Contendo informações e certificados de rede sem fios</span><span class="sxs-lookup"><span data-stu-id="bd6c0-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="bd6c0-171">Contendo quaisquer outras definições de provisionamento necessárias</span><span class="sxs-lookup"><span data-stu-id="bd6c0-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="bd6c0-172">Isto permitirá a um cliente com requisitos avançados de networking inscrever os dispositivos numa abordagem prática e escalável</span><span class="sxs-lookup"><span data-stu-id="bd6c0-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="bd6c0-173">Serão necessários pré-requisitos adicionais, como abaixo:</span><span class="sxs-lookup"><span data-stu-id="bd6c0-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="bd6c0-174">[Ativar o Inquilino para a pré-visualização do Piloto Automático](https://docs.microsoft.com/hololens/hololens2-autopilot).</span><span class="sxs-lookup"><span data-stu-id="bd6c0-174">[Enable the Tenant for the Autopilot preview](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
1. <span data-ttu-id="bd6c0-175">Crie as políticas HoloLens para substituir o Pacote de Provisionamento dentro do Intune.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="bd6c0-176">Crie as Políticas Intune HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="bd6c0-177">Atribua os dispositivos ao grupo correto.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="bd6c0-178">Processo</span><span class="sxs-lookup"><span data-stu-id="bd6c0-178">Process</span></span>

1. <span data-ttu-id="bd6c0-179">Ligue o cabo ethernet ao adaptador e ligue o adaptador à porta USB-C do dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="bd6c0-180">Liga os HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="bd6c0-181">O dispositivo deve ligar-se automaticamente à internet durante o OOBE através do adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="bd6c0-182">Deve detetar a configuração do Piloto Automático e registar-se automaticamente com Azure AD e Intune.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="bd6c0-183">O Dispositivo aplicará os certificados de Wi-Fi necessários e outras configurações, conforme necessário através do Intune.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="bd6c0-184">Quando estiver concluído, o técnico pode carregar o Portal Intune (Endpoint Manager) e perfurar a página de propriedades do dispositivo no **Home -> Devices -> DeviceName -> Hardware**.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="bd6c0-185">O endereço MAC Wi-Fi será visível dentro do Portal Intune.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![Endereço MAC via Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="bd6c0-187">O técnico adicionará este endereço MAC como um dispositivo permitido.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="bd6c0-188">Benefícios</span><span class="sxs-lookup"><span data-stu-id="bd6c0-188">Benefits</span></span>

<span data-ttu-id="bd6c0-189">Isto permitirá uma experiência de implantação "Heads off" para o Técnico, com o dispositivo a poder ir da caixa para se matricular em AZure AD e Intune sem que o técnico tenha de usar o dispositivo ou interagir manualmente com o ambiente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="bd6c0-190">Comunicação de endereços MAC ao Técnico</span><span class="sxs-lookup"><span data-stu-id="bd6c0-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="bd6c0-191">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd6c0-191">Requirements</span></span>

- <span data-ttu-id="bd6c0-192">Autorização do "Intune Graph PowerShell" contra o cliente Inquilino</span><span class="sxs-lookup"><span data-stu-id="bd6c0-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="bd6c0-193">Instalação do Intune Graph PowerShell na máquina de técnicos.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="bd6c0-194">Leia o acesso aos elementos "Dispositivos Geridos" do Intune.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="bd6c0-195">(Operador de mesa de ajuda ou superior, ou um papel personalizado)</span><span class="sxs-lookup"><span data-stu-id="bd6c0-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="bd6c0-196">Atualmente, não existe uma forma "simples" de desencadear um comando de automação baseado na inscrição de um novo dispositivo dentro do Intune.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="bd6c0-197">Portanto, este comando fornecerá ao técnico uma forma simples de recuperar o endereço MAC sem precisar de entrar no portal e recuperá-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="bd6c0-198">Isto irá devolver o nome e o endereço MAC de quaisquer dispositivos HoloLens que tenham sido matriculados nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![Endereço MAC via PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="bd6c0-200">Processo</span><span class="sxs-lookup"><span data-stu-id="bd6c0-200">Process</span></span>

<span data-ttu-id="bd6c0-201">Após a inscrição intune concluída, o Técnico executaria o script acima para recuperar o endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="bd6c0-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
