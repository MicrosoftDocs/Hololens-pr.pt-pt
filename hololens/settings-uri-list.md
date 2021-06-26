---
title: Visibilidade de Definições de Página
description: Mantenha-se atualizado com a nossa lista de URIs suportados para PageVisibilityList e Guide em holoLens dispositivos de realidade mista.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, acesso atribuído, quiosque, página de definições
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924337"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="50f41-104">Visibilidade de Definições de Página</span><span class="sxs-lookup"><span data-stu-id="50f41-104">Page Settings Visibility</span></span>

<span data-ttu-id="50f41-105">Uma das funcionalidades geríveis para dispositivos HoloLens é a utilização da [política Definições/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas dentro da aplicação Definições.</span><span class="sxs-lookup"><span data-stu-id="50f41-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="50f41-106">PageVisibilityList é uma política que permite que os administradores de TI impeçam que páginas específicas na aplicação Definições do Sistema sejam visíveis ou acessíveis, ou que o façam para todas as páginas, exceto as especificadas.</span><span class="sxs-lookup"><span data-stu-id="50f41-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="50f41-107">Esta funcionalidade é apenas avaliável no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou superior para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="50f41-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="50f41-108">Certifique-se de que os dispositivos para os seguintes são atualizados.</span><span class="sxs-lookup"><span data-stu-id="50f41-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="50f41-109">O exemplo a seguir ilustra uma política que permitiria o acesso apenas às páginas sobre e bluetooth, que têm URI "ms-settings:network-wifi" e "ms-settings:bluetooth" respectivamente:</span><span class="sxs-lookup"><span data-stu-id="50f41-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="50f41-110">Para definir isto através de um Pacote de Provisionamento:</span><span class="sxs-lookup"><span data-stu-id="50f41-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="50f41-111">Ao criar o seu pacote no Windows Configuration Designer navegue para **políticas > definições > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="50f41-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="50f41-112">Insira a corda: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="50f41-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="50f41-113">Exporte o seu Pacote de Provisionamento.</span><span class="sxs-lookup"><span data-stu-id="50f41-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="50f41-114">Aplique a embalagem no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="50f41-114">Apply the package to your device.</span></span>
<span data-ttu-id="50f41-115">Para obter todos os detalhes sobre como criar e aplicar um pacote de provisionamento visite [esta página](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="50f41-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="50f41-116">Isto pode ser feito via Intune usando OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="50f41-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="50f41-117">Crie uma **política personalizada.**</span><span class="sxs-lookup"><span data-stu-id="50f41-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="50f41-118">Ao configurar o OMA-URI utilize a cadeia: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="50f41-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="50f41-119">Ao selecionar a escolha de dados escolha: **String**</span><span class="sxs-lookup"><span data-stu-id="50f41-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="50f41-120">Ao escrever o valor: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="50f41-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="50f41-121">Certifique-se de atribuir a configuração do dispositivo personalizado a um grupo em que o dispositivo se destina a estar.</span><span class="sxs-lookup"><span data-stu-id="50f41-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="50f41-122">Consulte a [configuração do MDM holoLens](hololens-mdm-configure.md) para obter mais informações sobre grupos Intune e configurações de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="50f41-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="50f41-123">Independentemente do método escolhido, o seu dispositivo deverá agora receber as alterações e os utilizadores serão apresentados com a seguinte App de Definições.</span><span class="sxs-lookup"><span data-stu-id="50f41-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Screenshot de horas ativas a ser modificada na aplicação Definições](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="50f41-125">Para configurar as páginas de aplicações Definições para mostrar ou ocultar a sua própria seleção de páginas, dê uma olhada nas Definições URIs disponíveis nos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="50f41-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="50f41-126">IURS de Definições</span><span class="sxs-lookup"><span data-stu-id="50f41-126">Settings URIs</span></span>

<span data-ttu-id="50f41-127">Os dispositivos HoloLens e dispositivos Windows 10 têm uma seleção diferente de páginas dentro da aplicação Definições.</span><span class="sxs-lookup"><span data-stu-id="50f41-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="50f41-128">Nesta página, encontrará apenas as definições que existem no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="50f41-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="50f41-129">Contas</span><span class="sxs-lookup"><span data-stu-id="50f41-129">Accounts</span></span>
| <span data-ttu-id="50f41-130">Página de definições</span><span class="sxs-lookup"><span data-stu-id="50f41-130">Settings page</span></span>           | <span data-ttu-id="50f41-131">URI</span><span class="sxs-lookup"><span data-stu-id="50f41-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="50f41-132">Acesso escolar ou profissional</span><span class="sxs-lookup"><span data-stu-id="50f41-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="50f41-133">Inscrição da Íris</span><span class="sxs-lookup"><span data-stu-id="50f41-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="50f41-134">Assinar opções</span><span class="sxs-lookup"><span data-stu-id="50f41-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="50f41-135">Aplicações</span><span class="sxs-lookup"><span data-stu-id="50f41-135">Apps</span></span>
| <span data-ttu-id="50f41-136">Página de definições</span><span class="sxs-lookup"><span data-stu-id="50f41-136">Settings page</span></span> | <span data-ttu-id="50f41-137">URI</span><span class="sxs-lookup"><span data-stu-id="50f41-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="50f41-138">Apps & apresenta<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="50f41-139">Apps & funcionalidades > Opções Avançadas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="50f41-140">Apps & funcionalidades > Offline Maps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="50f41-141">Apps & funcionalidades > Offline Maps > Baixar mapas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="50f41-142">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="50f41-142">Devices</span></span>
| <span data-ttu-id="50f41-143">Página de definições</span><span class="sxs-lookup"><span data-stu-id="50f41-143">Settings page</span></span> | <span data-ttu-id="50f41-144">URI</span><span class="sxs-lookup"><span data-stu-id="50f41-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="50f41-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="50f41-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="50f41-146">Rato <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="50f41-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="50f41-148">Privacidade</span><span class="sxs-lookup"><span data-stu-id="50f41-148">Privacy</span></span>
| <span data-ttu-id="50f41-149">Página de definições</span><span class="sxs-lookup"><span data-stu-id="50f41-149">Settings page</span></span>            | <span data-ttu-id="50f41-150">URI</span><span class="sxs-lookup"><span data-stu-id="50f41-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="50f41-151">Informação da Conta</span><span class="sxs-lookup"><span data-stu-id="50f41-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="50f41-152">Diagnóstico de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="50f41-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="50f41-153">Aplicativos de fundo</span><span class="sxs-lookup"><span data-stu-id="50f41-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="50f41-154">Calendário</span><span class="sxs-lookup"><span data-stu-id="50f41-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="50f41-155">Chamada História</span><span class="sxs-lookup"><span data-stu-id="50f41-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="50f41-156">Câmara</span><span class="sxs-lookup"><span data-stu-id="50f41-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="50f41-157">Contactos</span><span class="sxs-lookup"><span data-stu-id="50f41-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="50f41-158">Feedback & de Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="50f41-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="50f41-159">Documentos</span><span class="sxs-lookup"><span data-stu-id="50f41-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="50f41-160">E-mail</span><span class="sxs-lookup"><span data-stu-id="50f41-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="50f41-161">Sistema de ficheiros</span><span class="sxs-lookup"><span data-stu-id="50f41-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="50f41-162">General <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="50f41-163">A & de tinta datilografar personalização <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="50f41-164">Localização</span><span class="sxs-lookup"><span data-stu-id="50f41-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="50f41-165">Mensagens</span><span class="sxs-lookup"><span data-stu-id="50f41-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="50f41-166">Microfone</span><span class="sxs-lookup"><span data-stu-id="50f41-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="50f41-167">Moção <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="50f41-168">Notificações</span><span class="sxs-lookup"><span data-stu-id="50f41-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="50f41-169">Outros dispositivos</span><span class="sxs-lookup"><span data-stu-id="50f41-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="50f41-170">Imagens</span><span class="sxs-lookup"><span data-stu-id="50f41-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="50f41-171">Rádios</span><span class="sxs-lookup"><span data-stu-id="50f41-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="50f41-172">Bordas <sup>screenshot 2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="50f41-173">Screenshots e aplicativos <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="50f41-174">Voz</span><span class="sxs-lookup"><span data-stu-id="50f41-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="50f41-175">Tarefas</span><span class="sxs-lookup"><span data-stu-id="50f41-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="50f41-176">Movimentos dos utilizadores</span><span class="sxs-lookup"><span data-stu-id="50f41-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="50f41-177">Vídeos</span><span class="sxs-lookup"><span data-stu-id="50f41-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="50f41-178">Ativação de voz</span><span class="sxs-lookup"><span data-stu-id="50f41-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="50f41-179">Rede e Internet</span><span class="sxs-lookup"><span data-stu-id="50f41-179">Network & Internet</span></span>
| <span data-ttu-id="50f41-180">Página de definições</span><span class="sxs-lookup"><span data-stu-id="50f41-180">Settings page</span></span> | <span data-ttu-id="50f41-181">URI</span><span class="sxs-lookup"><span data-stu-id="50f41-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="50f41-182">Modo avião <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="50f41-183">Proxy</span><span class="sxs-lookup"><span data-stu-id="50f41-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="50f41-184">VPN</span><span class="sxs-lookup"><span data-stu-id="50f41-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="50f41-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="50f41-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="50f41-186">Sistema</span><span class="sxs-lookup"><span data-stu-id="50f41-186">System</span></span>
| <span data-ttu-id="50f41-187">Página de definições</span><span class="sxs-lookup"><span data-stu-id="50f41-187">Settings page</span></span>      | <span data-ttu-id="50f41-188">URI</span><span class="sxs-lookup"><span data-stu-id="50f41-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="50f41-189">Bateria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="50f41-190">Bateria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="50f41-191">Cores</span><span class="sxs-lookup"><span data-stu-id="50f41-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="50f41-192">Hologramas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="50f41-193">Calibração <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="50f41-194">Notificações & ações</span><span class="sxs-lookup"><span data-stu-id="50f41-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="50f41-195">Experiências partilhadas</span><span class="sxs-lookup"><span data-stu-id="50f41-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="50f41-196">Som <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="50f41-197">Volume > de aplicações de som e preferência do dispositivo <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="50f41-198">Sound > Gerir dispositivos de som <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="50f41-199">Armazenamento</span><span class="sxs-lookup"><span data-stu-id="50f41-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="50f41-200">Armazenamento > Configure Armazenamento Sense <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-200">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="50f41-201">Linguagem & tempo</span><span class="sxs-lookup"><span data-stu-id="50f41-201">Time & Language</span></span>
| <span data-ttu-id="50f41-202">Página de definições</span><span class="sxs-lookup"><span data-stu-id="50f41-202">Settings page</span></span> | <span data-ttu-id="50f41-203">URI</span><span class="sxs-lookup"><span data-stu-id="50f41-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="50f41-204">Data & hora <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="50f41-205">Teclado <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="50f41-206">Língua <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="50f41-207">Língua <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="50f41-208">Linguagem</span><span class="sxs-lookup"><span data-stu-id="50f41-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="50f41-209">Region</span><span class="sxs-lookup"><span data-stu-id="50f41-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="50f41-210">Atualizar segurança &</span><span class="sxs-lookup"><span data-stu-id="50f41-210">Update & Security</span></span>
| <span data-ttu-id="50f41-211">Página de definições</span><span class="sxs-lookup"><span data-stu-id="50f41-211">Settings page</span></span>                         | <span data-ttu-id="50f41-212">URI</span><span class="sxs-lookup"><span data-stu-id="50f41-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="50f41-213">Opções Avançadas</span><span class="sxs-lookup"><span data-stu-id="50f41-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="50f41-214">Recuperação & reinicialização <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f41-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="50f41-215">Programa Windows Insider</span><span class="sxs-lookup"><span data-stu-id="50f41-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="50f41-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="50f41-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="50f41-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="50f41-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="50f41-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="50f41-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="50f41-219">Atualização do Windows - Verifica as atualizações</span><span class="sxs-lookup"><span data-stu-id="50f41-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


- <span data-ttu-id="50f41-220"><sup>1</sup> - Para versões anteriores ao Windows Holographic, versão 21H1, os dois URIs seguintes não o levam realmente às **opções avançadas** ou páginas **opções;** apenas bloquearão ou mostrarão a página principal do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="50f41-220"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="50f41-221">ms-settings:windowsupdate-opções</span><span class="sxs-lookup"><span data-stu-id="50f41-221">ms-settings:windowsupdate-options</span></span>
  -  <span data-ttu-id="50f41-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="50f41-222">ms-settings:windowsupdate-restartoptions</span></span>

- <span data-ttu-id="50f41-223"><sup>2</sup> - Disponível no Windows Holographic 21H1 ou superior.</span><span class="sxs-lookup"><span data-stu-id="50f41-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="50f41-224">Para obter uma lista completa dos URIs de Definições do Windows 10, visite a documentação das [definições de lançamento.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="50f41-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
