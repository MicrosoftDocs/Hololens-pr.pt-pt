---
title: Página Definições Visibilidade
description: Mantenha-se atualizado com a nossa lista de URIs suportados para PageVisibilityList e Guia em HoloLens dispositivos de realidade mista.
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
ms.openlocfilehash: 5ac3ff27085fd2f7c5bc1de0e461079a673bbb23
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637171"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="000f5-104">Página Definições Visibilidade</span><span class="sxs-lookup"><span data-stu-id="000f5-104">Page Settings Visibility</span></span>

<span data-ttu-id="000f5-105">Uma das funcionalidades geríveis para dispositivos HoloLens é utilizar a [política Definições/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas dentro da aplicação Definições.</span><span class="sxs-lookup"><span data-stu-id="000f5-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="000f5-106">PageVisibilityList é uma política que permite que os administradores de TI impeçam que páginas específicas no Sistema Definições aplicação sejam visíveis ou acessíveis, ou que o façam para todas as páginas, exceto as especificadas.</span><span class="sxs-lookup"><span data-stu-id="000f5-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="000f5-107">Esta funcionalidade é apenas avaliável em [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou superior para HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="000f5-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="000f5-108">Certifique-se de que os dispositivos para os seguintes são atualizados.</span><span class="sxs-lookup"><span data-stu-id="000f5-108">Please ensure devices you intend to use this for are updated.</span></span>


## <a name="examples"></a><span data-ttu-id="000f5-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="000f5-109">Examples</span></span>
<span data-ttu-id="000f5-110">As páginas são identificadas por uma versão abreviada dos URIs publicados, que é o URI menos o prefixo "ms-settings:".</span><span class="sxs-lookup"><span data-stu-id="000f5-110">Pages are identified by a shortened version of the published URIs, which is the URI minus the "ms-settings:" prefix.</span></span>

<span data-ttu-id="000f5-111">O exemplo a seguir ilustra uma política que permitiria o acesso apenas às páginas sobre e bluetooth, que têm URI "network-wifi" e "bluetooth" respectivamente:</span><span class="sxs-lookup"><span data-stu-id="000f5-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "network-wifi" and "bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="000f5-112">O exemplo a seguir ilustra uma política que esconderia a página de Reset do SISTEMA:</span><span class="sxs-lookup"><span data-stu-id="000f5-112">The following example illustrates a policy that would hide the OS Reset page:</span></span>
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a><span data-ttu-id="000f5-113">Implementação desta política via Intune</span><span class="sxs-lookup"><span data-stu-id="000f5-113">Deploying this policy via Intune</span></span>

<span data-ttu-id="000f5-114">Estes são os valores de configuração que serão fornecidos ao Intune:</span><span class="sxs-lookup"><span data-stu-id="000f5-114">These are the configuration values that will be supplied to Intune:</span></span>

- <span data-ttu-id="000f5-115">**Nome:** Um nome de exibição preferido para o perfil.</span><span class="sxs-lookup"><span data-stu-id="000f5-115">**Name:** An admin preferred display name for the profile.</span></span>
- <span data-ttu-id="000f5-116">**OMA-URI:** O URI totalmente qualificado da página de definição, incluindo o seu [âmbito](/windows/client-management/mdm/policy-configuration-service-provider).</span><span class="sxs-lookup"><span data-stu-id="000f5-116">**OMA-URI:** The fully qualified URI of the setting page including its [scope](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="000f5-117">Estes exemplos nesta página estão a usar o `./Device` âmbito.</span><span class="sxs-lookup"><span data-stu-id="000f5-117">This examples on this page are using the `./Device` scope.</span></span>
- <span data-ttu-id="000f5-118">**Valor:** Um valor de cadeia que indica se deve ocultar ou mostrar *apenas* as páginas especificadas.</span><span class="sxs-lookup"><span data-stu-id="000f5-118">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="000f5-119">Os valores possíveis são `hide:<pagename>` `showonly:<pagename>` e.</span><span class="sxs-lookup"><span data-stu-id="000f5-119">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> 
 
<span data-ttu-id="000f5-120">Várias páginas podem ser especificadas separando-as com um ponto e vírgula, e uma lista de páginas comuns pode ser encontrada abaixo.</span><span class="sxs-lookup"><span data-stu-id="000f5-120">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>

1. <span data-ttu-id="000f5-121">Crie uma **política personalizada.**</span><span class="sxs-lookup"><span data-stu-id="000f5-121">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="000f5-122">Ao definir o **OMA-URI** introduza o URI totalmente ateado.</span><span class="sxs-lookup"><span data-stu-id="000f5-122">When setting the **OMA-URI** enter the fully scoped URI.</span></span> <span data-ttu-id="000f5-123">Por exemplo: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="000f5-123">For example: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="000f5-124">Ao selecionar a escolha de dados escolha: **String**</span><span class="sxs-lookup"><span data-stu-id="000f5-124">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="000f5-125">Ao especificar **Valor,** utilize a orientação acima.</span><span class="sxs-lookup"><span data-stu-id="000f5-125">When specifying **Value** use the guidance above.</span></span> <span data-ttu-id="000f5-126">Por exemplo: **`showonly:network-wifi;network-proxy;bluetooth`** ou **`hide:reset`**</span><span class="sxs-lookup"><span data-stu-id="000f5-126">For example: **`showonly:network-wifi;network-proxy;bluetooth`** or **`hide:reset`**</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="000f5-127">Certifique-se de atribuir a configuração do dispositivo personalizado a um grupo em que o dispositivo se destina a estar.</span><span class="sxs-lookup"><span data-stu-id="000f5-127">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span> <span data-ttu-id="000f5-128">Se este passo não for dado, a apólice será empurrada, mas não será aplicada.</span><span class="sxs-lookup"><span data-stu-id="000f5-128">If this step is not performed, the policy will be pushed but won't be applied.</span></span>

<span data-ttu-id="000f5-129">Consulte [HoloLens configuração do MDM](hololens-mdm-configure.md) para obter mais informações sobre grupos Intune e configurações do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="000f5-129">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>


## <a name="deploying-this-policy-via-a-provisioning-package"></a><span data-ttu-id="000f5-130">Implementação desta política através de um pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="000f5-130">Deploying this policy via a Provisioning Package</span></span>

<span data-ttu-id="000f5-131">Estes são os valores de configuração que serão especificados no Windows Designer de Configuração:</span><span class="sxs-lookup"><span data-stu-id="000f5-131">These are the configuration values that will be specified in Windows Configuration Designer:</span></span>

<span data-ttu-id="000f5-132">**Valor:** Um valor de cadeia que indica se deve ocultar ou mostrar *apenas* as páginas especificadas.</span><span class="sxs-lookup"><span data-stu-id="000f5-132">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="000f5-133">Os valores possíveis são `hide:<pagename>` `showonly:<pagename>` e.</span><span class="sxs-lookup"><span data-stu-id="000f5-133">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> <span data-ttu-id="000f5-134">Várias páginas podem ser especificadas separando-as com um ponto e vírgula, e uma lista de páginas comuns pode ser encontrada abaixo.</span><span class="sxs-lookup"><span data-stu-id="000f5-134">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>


1. <span data-ttu-id="000f5-135">Ao criar o seu pacote em Windows Designer de Configuração navegue para **políticas > Definições > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="000f5-135">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="000f5-136">Insira a corda: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="000f5-136">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="000f5-137">Exporte o seu Pacote de Provisionamento.</span><span class="sxs-lookup"><span data-stu-id="000f5-137">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="000f5-138">Aplique a embalagem no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="000f5-138">Apply the package to your device.</span></span>
<span data-ttu-id="000f5-139">Para obter informações completas sobre como criar e aplicar um pacote de provisionamento visite [a página de a provisionamento HoloLens](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="000f5-139">For full details on how to create and apply a provisioning package visit [the HoloLens provisioning page](hololens-provisioning.md).</span></span>


<span data-ttu-id="000f5-140">Independentemente do método escolhido, o seu dispositivo deverá agora receber as alterações e os utilizadores serão apresentados com a seguinte App Definições.</span><span class="sxs-lookup"><span data-stu-id="000f5-140">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Screenshot de horas ativas a ser modificada na app Definições](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="000f5-142">Para configurar as páginas de aplicações Definições para mostrar ou ocultar a sua própria seleção de páginas, dê uma olhada nas URIs Definições disponíveis no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="000f5-142">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="000f5-143">Definições URIs</span><span class="sxs-lookup"><span data-stu-id="000f5-143">Settings URIs</span></span>

<span data-ttu-id="000f5-144">HoloLens dispositivos e dispositivos Windows 10 têm uma seleção diferente de páginas dentro da aplicação Definições.</span><span class="sxs-lookup"><span data-stu-id="000f5-144">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="000f5-145">Nesta página, encontrará apenas as definições que existem no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="000f5-145">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="000f5-146">Contas</span><span class="sxs-lookup"><span data-stu-id="000f5-146">Accounts</span></span>
| <span data-ttu-id="000f5-147">Página de definições</span><span class="sxs-lookup"><span data-stu-id="000f5-147">Settings page</span></span>           | <span data-ttu-id="000f5-148">URI</span><span class="sxs-lookup"><span data-stu-id="000f5-148">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="000f5-149">Acesso escolar ou profissional</span><span class="sxs-lookup"><span data-stu-id="000f5-149">Access work or school</span></span> | `workplace`                         |
| <span data-ttu-id="000f5-150">Inscrição da Íris</span><span class="sxs-lookup"><span data-stu-id="000f5-150">Iris Enrollment</span></span>       | `signinoptions-launchirisenrollment` |
| <span data-ttu-id="000f5-151">Assinar opções</span><span class="sxs-lookup"><span data-stu-id="000f5-151">Sign In Options</span></span>         | ` signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="000f5-152">Aplicações</span><span class="sxs-lookup"><span data-stu-id="000f5-152">Apps</span></span>
| <span data-ttu-id="000f5-153">Página de definições</span><span class="sxs-lookup"><span data-stu-id="000f5-153">Settings page</span></span> | <span data-ttu-id="000f5-154">URI</span><span class="sxs-lookup"><span data-stu-id="000f5-154">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="000f5-155">Apps & apresenta <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-155">Apps & features <sup>2</sup></span></span>     | `appsfeatures` <br> |
| <span data-ttu-id="000f5-156">Apps & funcionalidades > Opções Avançadas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-156">Apps & features > Advanced Options <sup>2</sup></span></span>     | `appsfeatures-app` <br> |
| <span data-ttu-id="000f5-157">Apps & funcionalidades > Offline Mapas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-157">Apps & features > Offline Maps <sup>2</sup></span></span>     | `maps-maps` <br> |
| <span data-ttu-id="000f5-158">Apps & funcionalidades > Offline Mapas > Baixar mapas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-158">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="000f5-159">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="000f5-159">Devices</span></span>
| <span data-ttu-id="000f5-160">Página de definições</span><span class="sxs-lookup"><span data-stu-id="000f5-160">Settings page</span></span> | <span data-ttu-id="000f5-161">URI</span><span class="sxs-lookup"><span data-stu-id="000f5-161">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="000f5-162">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="000f5-162">Bluetooth</span></span>     | `bluetooth` <br> `connecteddevices` |
| <span data-ttu-id="000f5-163">Rato <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-163">Mouse <sup>2</sup></span></span>      | `mouse` <br>  |
| <span data-ttu-id="000f5-164">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-164">USB <sup>2</sup></span></span>      | `usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="000f5-165">Privacidade</span><span class="sxs-lookup"><span data-stu-id="000f5-165">Privacy</span></span>
| <span data-ttu-id="000f5-166">Página de definições</span><span class="sxs-lookup"><span data-stu-id="000f5-166">Settings page</span></span>            | <span data-ttu-id="000f5-167">URI</span><span class="sxs-lookup"><span data-stu-id="000f5-167">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="000f5-168">Informação da Conta</span><span class="sxs-lookup"><span data-stu-id="000f5-168">Account Info</span></span>             | `privacy-accountinfo`              |
| <span data-ttu-id="000f5-169">Diagnóstico de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="000f5-169">App Diagnostics</span></span>        | `privacy-appdiagnostics`              |
| <span data-ttu-id="000f5-170">Aplicativos de fundo</span><span class="sxs-lookup"><span data-stu-id="000f5-170">Background Apps</span></span>        | `privacy-backgroundapps`              |
| <span data-ttu-id="000f5-171">Calendário</span><span class="sxs-lookup"><span data-stu-id="000f5-171">Calendar</span></span>                 | `privacy-calendar`                    |
| <span data-ttu-id="000f5-172">Chamada História</span><span class="sxs-lookup"><span data-stu-id="000f5-172">Call History</span></span>             | `privacy-callhistory`                 |
| <span data-ttu-id="000f5-173">Câmara</span><span class="sxs-lookup"><span data-stu-id="000f5-173">Camera</span></span>                   | `privacy-webcam`                      |
| <span data-ttu-id="000f5-174">Contactos</span><span class="sxs-lookup"><span data-stu-id="000f5-174">Contacts</span></span>                 | `privacy-contacts`                    |
| <span data-ttu-id="000f5-175">Feedback & de Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="000f5-175">Diagnostics & Feedback</span></span> | `privacy-feedback`                    |
| <span data-ttu-id="000f5-176">Documentos</span><span class="sxs-lookup"><span data-stu-id="000f5-176">Documents</span></span>                | `privacy-documents`                   |
| <span data-ttu-id="000f5-177">E-mail</span><span class="sxs-lookup"><span data-stu-id="000f5-177">Email</span></span>                    | `privacy-email`                       |
| <span data-ttu-id="000f5-178">Sistema de ficheiros</span><span class="sxs-lookup"><span data-stu-id="000f5-178">File system</span></span>              | `privacy-broadfilesystemaccess`       |
| <span data-ttu-id="000f5-179">General <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-179">General <sup>2</sup></span></span>             | `privacy-general`       |
| <span data-ttu-id="000f5-180">A & de tinta datilografar personalização <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-180">Ink & typing personalization <sup>2</sup></span></span>             | `privacy-speechtyping`       |
| <span data-ttu-id="000f5-181">Localização</span><span class="sxs-lookup"><span data-stu-id="000f5-181">Location</span></span>                 | `privacy-location`                    |
| <span data-ttu-id="000f5-182">Mensagens</span><span class="sxs-lookup"><span data-stu-id="000f5-182">Messaging</span></span>                | `privacy-messaging`                   |
| <span data-ttu-id="000f5-183">Microfone</span><span class="sxs-lookup"><span data-stu-id="000f5-183">Microphone</span></span>               | `privacy-microphone`                  |
| <span data-ttu-id="000f5-184">Moção <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-184">Motion <sup>2</sup></span></span>               | `privacy-motion`                  |
| <span data-ttu-id="000f5-185">Notificações</span><span class="sxs-lookup"><span data-stu-id="000f5-185">Notifications</span></span>            | `privacy-notifications`               |
| <span data-ttu-id="000f5-186">Outros dispositivos</span><span class="sxs-lookup"><span data-stu-id="000f5-186">Other devices</span></span>            | `privacy-customdevices`               |
| <span data-ttu-id="000f5-187">Imagens</span><span class="sxs-lookup"><span data-stu-id="000f5-187">Pictures</span></span>                 | `privacy-pictures`                    |
| <span data-ttu-id="000f5-188">Rádios</span><span class="sxs-lookup"><span data-stu-id="000f5-188">Radios</span></span>                   | `privacy-radios`                      |
| <span data-ttu-id="000f5-189">Bordas <sup>screenshot 2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-189">Screenshot borders <sup>2</sup></span></span>             | `privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="000f5-190">Screenshots e aplicativos <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-190">Screenshots and apps <sup>2</sup></span></span>             | `privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="000f5-191">Voz</span><span class="sxs-lookup"><span data-stu-id="000f5-191">Speech</span></span>                   | `privacy-speech`                      |
| <span data-ttu-id="000f5-192">Tarefas</span><span class="sxs-lookup"><span data-stu-id="000f5-192">Tasks</span></span>                    | `privacy-tasks`                       |
| <span data-ttu-id="000f5-193">Movimentos dos utilizadores</span><span class="sxs-lookup"><span data-stu-id="000f5-193">User movements</span></span>           | `privacy-backgroundspatialperception` |
| <span data-ttu-id="000f5-194">Vídeos</span><span class="sxs-lookup"><span data-stu-id="000f5-194">Videos</span></span>                   | `privacy-videos`                      |
| <span data-ttu-id="000f5-195">Ativação de voz</span><span class="sxs-lookup"><span data-stu-id="000f5-195">Voice Activation</span></span>       | `privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="000f5-196">Rede e Internet</span><span class="sxs-lookup"><span data-stu-id="000f5-196">Network & Internet</span></span>
| <span data-ttu-id="000f5-197">Página de definições</span><span class="sxs-lookup"><span data-stu-id="000f5-197">Settings page</span></span> | <span data-ttu-id="000f5-198">URI</span><span class="sxs-lookup"><span data-stu-id="000f5-198">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="000f5-199">Modo avião <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-199">Airplane Mode <sup>2</sup></span></span> | `network-airplanemode`        |
| <span data-ttu-id="000f5-200">Proxy</span><span class="sxs-lookup"><span data-stu-id="000f5-200">Proxy</span></span> | `network-proxy`        |
| <span data-ttu-id="000f5-201">VPN</span><span class="sxs-lookup"><span data-stu-id="000f5-201">VPN</span></span>   | `network-vpn`          |
| <span data-ttu-id="000f5-202">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="000f5-202">Wi-Fi</span></span>  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="000f5-203">Sistema</span><span class="sxs-lookup"><span data-stu-id="000f5-203">System</span></span>
| <span data-ttu-id="000f5-204">Página de definições</span><span class="sxs-lookup"><span data-stu-id="000f5-204">Settings page</span></span>      | <span data-ttu-id="000f5-205">URI</span><span class="sxs-lookup"><span data-stu-id="000f5-205">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="000f5-206">Bateria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-206">Battery <sup>2</sup></span></span>           | `batterysaver`<br>|
| <span data-ttu-id="000f5-207">Bateria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-207">Battery <sup>2</sup></span></span>           | `batterysaver-settings`<br>|
| <span data-ttu-id="000f5-208">Cores</span><span class="sxs-lookup"><span data-stu-id="000f5-208">Colors</span></span>             | `colors`<br>`personalization-colors` |
| <span data-ttu-id="000f5-209">Hologramas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-209">Holograms <sup>2</sup></span></span>  |  `holograms`  |
| <span data-ttu-id="000f5-210">Calibração <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-210">Calibration <sup>2</sup></span></span> |  `calibration` |
| <span data-ttu-id="000f5-211">Notificações & ações</span><span class="sxs-lookup"><span data-stu-id="000f5-211">Notifications & actions</span></span>  | `notifications`          |
| <span data-ttu-id="000f5-212">Experiências partilhadas</span><span class="sxs-lookup"><span data-stu-id="000f5-212">Shared Experiences</span></span> | `crossdevice` 
| <span data-ttu-id="000f5-213">Som <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-213">Sound <sup>2</sup></span></span>           | `sound`<br>|
| <span data-ttu-id="000f5-214">Volume > de aplicações de som e preferência do dispositivo <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-214">Sound > App volume and device preference <sup>2</sup></span></span>           | `apps-volume`<br>|
| <span data-ttu-id="000f5-215">Sound > Gerir dispositivos de som <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-215">Sound > Manage sound devices <sup>2</sup></span></span>           | `sound-devices`<br>|
| <span data-ttu-id="000f5-216">Armazenamento</span><span class="sxs-lookup"><span data-stu-id="000f5-216">Storage</span></span>            | `storagesense`           |
| <span data-ttu-id="000f5-217">Armazenamento > Configurar Armazenamento Sense <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-217">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="000f5-218">Linguagem & tempo</span><span class="sxs-lookup"><span data-stu-id="000f5-218">Time & Language</span></span>
| <span data-ttu-id="000f5-219">Página de definições</span><span class="sxs-lookup"><span data-stu-id="000f5-219">Settings page</span></span> | <span data-ttu-id="000f5-220">URI</span><span class="sxs-lookup"><span data-stu-id="000f5-220">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="000f5-221">Data & hora <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-221">Date & time <sup>2</sup></span></span> | `dateandtime`                  |
| <span data-ttu-id="000f5-222">Teclado <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-222">Keyboard <sup>2</sup></span></span> | `keyboard`                  |
| <span data-ttu-id="000f5-223">Língua <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-223">Language <sup>2</sup></span></span> | `language`                  |
| <span data-ttu-id="000f5-224">Língua <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-224">Language <sup>2</sup></span></span> | `regionlanguage-languageoptions`                  |
| <span data-ttu-id="000f5-225">Linguagem</span><span class="sxs-lookup"><span data-stu-id="000f5-225">Language</span></span>      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="000f5-226">Region</span><span class="sxs-lookup"><span data-stu-id="000f5-226">Region</span></span>        | `regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="000f5-227">Atualizar segurança &</span><span class="sxs-lookup"><span data-stu-id="000f5-227">Update & Security</span></span>
| <span data-ttu-id="000f5-228">Página de definições</span><span class="sxs-lookup"><span data-stu-id="000f5-228">Settings page</span></span>                         | <span data-ttu-id="000f5-229">URI</span><span class="sxs-lookup"><span data-stu-id="000f5-229">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="000f5-230">Opções Avançadas</span><span class="sxs-lookup"><span data-stu-id="000f5-230">Advanced Options</span></span>                    | `windowsupdate-options`         |
| <span data-ttu-id="000f5-231">Recuperação & reinicialização <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="000f5-231">Reset & Recovery <sup>2</sup></span></span>      | `reset`         |
| <span data-ttu-id="000f5-232">Programa Windows Insider</span><span class="sxs-lookup"><span data-stu-id="000f5-232">Windows Insider Program</span></span>               | `windowsinsider` <br>`windowsinsider-optin`          |
| <span data-ttu-id="000f5-233">Windows Update</span><span class="sxs-lookup"><span data-stu-id="000f5-233">Windows Update</span></span>                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><span data-ttu-id="000f5-234"><sup>1</sup>`windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="000f5-234"><sup>1</sup>`windowsupdate-options`</span></span><br><span data-ttu-id="000f5-235"><sup>1</sup>`windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="000f5-235"><sup>1</sup>`windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="000f5-236">Windows Atualização - Verificações de atualizações</span><span class="sxs-lookup"><span data-stu-id="000f5-236">Windows Update - Checks for updates</span></span> | `windowsupdate-action`          |


- <span data-ttu-id="000f5-237"><sup>1</sup> - Para versões anteriores à Windows Holográfica, versão 21H1, os dois URIs seguintes não o levam realmente às **páginas de opções avançadas** ou **opções;** apenas bloquearão ou mostrarão a página principal de Atualização Windows.</span><span class="sxs-lookup"><span data-stu-id="000f5-237"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="000f5-238">windowsupdate opções</span><span class="sxs-lookup"><span data-stu-id="000f5-238">windowsupdate-options</span></span>
  -  <span data-ttu-id="000f5-239">windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="000f5-239">windowsupdate-restartoptions</span></span>

- <span data-ttu-id="000f5-240"><sup>2</sup> - Disponível em Windows Holographic 21H1 ou superior.</span><span class="sxs-lookup"><span data-stu-id="000f5-240"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="000f5-241">Para obter uma lista completa de WINDOWS 10 DEFINIÇÕES URIs, visite a documentação de [definições de lançamento.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="000f5-241">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
