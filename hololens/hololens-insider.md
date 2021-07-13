---
title: Pré-visualização de insider para Microsoft HoloLens
description: Saiba como começar com as construções do Insider e forneça feedback valioso para a nossa próxima grande atualização do sistema operativo para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636098"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="4c8bf-103">Pré-visualização de insider para Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="4c8bf-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="4c8bf-104">Bem-vindos às mais recentes construções de Insider Preview para HoloLens!</span><span class="sxs-lookup"><span data-stu-id="4c8bf-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="4c8bf-105">É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer feedback valioso para a nossa próxima grande atualização do sistema operativo para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="4c8bf-106">Windows Notas de lançamento de insider</span><span class="sxs-lookup"><span data-stu-id="4c8bf-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="4c8bf-107">Estamos entusiasmados por começar a voar novas funcionalidades para Windows Insiders novamente.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="4c8bf-108">Novas construções serão voadas para os Canais Dev e Beta para as últimas atualizações.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="4c8bf-109">Continuaremos a atualizar esta página à medida que adicionamos mais funcionalidades e atualizações ao nosso Windows o Insider constrói.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="4c8bf-110">Fique animado e pronto para misturar estas atualizações na sua realidade.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="4c8bf-111">Funcionalidade</span><span class="sxs-lookup"><span data-stu-id="4c8bf-111">Feature</span></span>                 | <span data-ttu-id="4c8bf-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="4c8bf-112">Description</span></span>                | <span data-ttu-id="4c8bf-113">Utilizador ou Cenário</span><span class="sxs-lookup"><span data-stu-id="4c8bf-113">User or Scenario</span></span> | <span data-ttu-id="4c8bf-114">Construção introduzida</span><span class="sxs-lookup"><span data-stu-id="4c8bf-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="4c8bf-115">Alterações do CSP para reportar detalhes HoloLens</span><span class="sxs-lookup"><span data-stu-id="4c8bf-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="4c8bf-116">Novos CSPs para consulta de dados</span><span class="sxs-lookup"><span data-stu-id="4c8bf-116">New CSPs for to query data</span></span> | <span data-ttu-id="4c8bf-117">Administradores de TI</span><span class="sxs-lookup"><span data-stu-id="4c8bf-117">IT Admins</span></span>    | <span data-ttu-id="4c8bf-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="4c8bf-118">20348.1403</span></span>                 |
| [<span data-ttu-id="4c8bf-119">Política de login automático controlada pela CSP</span><span class="sxs-lookup"><span data-stu-id="4c8bf-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="4c8bf-120">Usado para iniciar sessão numa conta automaticamente</span><span class="sxs-lookup"><span data-stu-id="4c8bf-120">Used to log in an account automatically</span></span> | <span data-ttu-id="4c8bf-121">Administradores de TI</span><span class="sxs-lookup"><span data-stu-id="4c8bf-121">IT Admins</span></span> | <span data-ttu-id="4c8bf-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="4c8bf-122">20348.1405</span></span> |
| [<span data-ttu-id="4c8bf-123">Suporte de ficheiro PFX para Gestor de Certificados</span><span class="sxs-lookup"><span data-stu-id="4c8bf-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="4c8bf-124">Adicione pfx certs via Definições UI</span><span class="sxs-lookup"><span data-stu-id="4c8bf-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="4c8bf-125">Utilizador Final</span><span class="sxs-lookup"><span data-stu-id="4c8bf-125">End User</span></span> | <span data-ttu-id="4c8bf-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="4c8bf-126">20348.1405</span></span> |
| [<span data-ttu-id="4c8bf-127">Ver relatório de diagnóstico avançado em Definições sobre HoloLens</span><span class="sxs-lookup"><span data-stu-id="4c8bf-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="4c8bf-128">Ver registos de diagnóstico do MDM no dispositivo</span><span class="sxs-lookup"><span data-stu-id="4c8bf-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="4c8bf-129">Resolução de problemas</span><span class="sxs-lookup"><span data-stu-id="4c8bf-129">Troubleshooting</span></span> | <span data-ttu-id="4c8bf-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="4c8bf-130">20348.1405</span></span> |
| [<span data-ttu-id="4c8bf-131">Notificações de Diagnóstico Offline</span><span class="sxs-lookup"><span data-stu-id="4c8bf-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="4c8bf-132">Feedback audiovisual para coleção de registos</span><span class="sxs-lookup"><span data-stu-id="4c8bf-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="4c8bf-133">Resolução de problemas</span><span class="sxs-lookup"><span data-stu-id="4c8bf-133">Troubleshooting</span></span> | <span data-ttu-id="4c8bf-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="4c8bf-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="4c8bf-135">Alterações do CSP para reportar detalhes HoloLens</span><span class="sxs-lookup"><span data-stu-id="4c8bf-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="4c8bf-136">Introduzido em Windows insider build, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="4c8bf-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="4c8bf-137">Os seguintes CSPs foram atualizados com novas formas de reportar informações dos seus dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="4c8bf-138">DevDetail CSP - Armazenamento grátis</span><span class="sxs-lookup"><span data-stu-id="4c8bf-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="4c8bf-139">O DevDetail CSP também informa agora espaço de armazenamento gratuito no HoloLens dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="4c8bf-140">Isto deve corresponder aproximadamente ao valor mostrado na página de Armazenamento da app Definições.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="4c8bf-141">Segue-se o nó específico que contém esta informação.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="4c8bf-142">./DevDetail/Ext/Microsoft/FreeStorage (apenas operação GET)</span><span class="sxs-lookup"><span data-stu-id="4c8bf-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="4c8bf-143">DeviceStatus CSP - SSID e BSSID</span><span class="sxs-lookup"><span data-stu-id="4c8bf-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="4c8bf-144">O DeviceStatus CSP informa agora também o SSID e o BSSID de Wi-Fi rede com a qual HoloLens está ativamente ligado.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="4c8bf-145">Seguem-se os nós específicos que contêm esta informação.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="4c8bf-146">./Fornecedor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address do adaptador de Wi-Fi*/SSID</span><span class="sxs-lookup"><span data-stu-id="4c8bf-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="4c8bf-147">./Fornecedor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address do adaptador Wi-Fi*/BSSID</span><span class="sxs-lookup"><span data-stu-id="4c8bf-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="4c8bf-148">Blob de sincronização de exemplo (para fornecedores de MDM) para consulta para NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="4c8bf-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="4c8bf-149">Política de login automático controlada pela CSP</span><span class="sxs-lookup"><span data-stu-id="4c8bf-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="4c8bf-150">Esta nova política DomLogonUser controla se um utilizador será automaticamente iniciado.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="4c8bf-151">Alguns clientes querem configurar dispositivos que estejam ligados a uma identidade, mas não querem qualquer experiência de inscrição.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="4c8bf-152">Imagine pegar num dispositivo e utilizar imediatamente assistência remota.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="4c8bf-153">Ou ter o benefício de poder distribuir rapidamente HoloLens dispositivos e permitir que os seus utilizadores finais acelerem o login.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="4c8bf-154">Quando a apólice é definida como um valor não vazio, especifica o endereço de e-mail do utilizador de início de sím em si.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="4c8bf-155">O utilizador especificado deve apresentar-se ao dispositivo pelo menos uma vez para ativar o início de sísmis automático.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="4c8bf-156">O OMA-URI do novo valor de cadeia de políticas `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`</span><span class="sxs-lookup"><span data-stu-id="4c8bf-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="4c8bf-157">O utilizador com o mesmo endereço de e-mail terá o início de são automático ativado.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="4c8bf-158">Num dispositivo em que esta política está configurada, o utilizador especificado na política terá de se apresentar pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="4c8bf-159">As reinicializações subsequentes do dispositivo após o primeiro início de sessão terão o utilizador especificado automaticamente ligado.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="4c8bf-160">Apenas um único utilizador de início de sítido automático é suportado.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="4c8bf-161">Uma vez ativado, o utilizador registado automaticamente não poderá iniciar sessão manualmente.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="4c8bf-162">Para se apresentar como um utilizador diferente, a política deve primeiro ser desativada.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="4c8bf-163">Alguns eventos, como as principais atualizações do SO, podem exigir que o utilizador especificado volte a apresentar-se ao dispositivo para retomar o comportamento do início de sé.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="4c8bf-164">O logotipo automático só é suportado para utilizadores de MSA e AAD.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="4c8bf-165">Suporte de ficheiro PFX para Gestor de Certificados</span><span class="sxs-lookup"><span data-stu-id="4c8bf-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="4c8bf-166">Introduzido em Windows insider build 20348.1405.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="4c8bf-167">Adicionámos apoio ao [Gestor de Certificados](certificate-manager.md) para agora usar certificados .pfx.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="4c8bf-168">Quando os utilizadores navegam para **Definições**  >  **Atualizar &**  >  **Certificados de** Segurança , e selecione **Instalar um certificado,** o UI agora suporta o ficheiro de certificado .pfx.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="4c8bf-169">Os utilizadores podem importar certificado .pfx, com chave privada, para a loja de utilizadores ou loja de máquinas.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="4c8bf-170">Ver relatório de diagnóstico avançado em Definições sobre HoloLens</span><span class="sxs-lookup"><span data-stu-id="4c8bf-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="4c8bf-171">Para dispositivos geridos quando o comportamento de resolução de problemas, confirmar que uma configuração de política esperada é aplicada é um passo importante.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="4c8bf-172">Anteriormente a esta nova funcionalidade, esta tinha de ser feita fora do dispositivo via MDM ou perto do dispositivo depois de exportar registos de diagnóstico do MDM recolhidos através **do Definições**  ->  **Contas** Access  >  **ou escola**, e selecione **Exporte os seus registos de gestão** e seja visualizado num PC próximo.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="4c8bf-173">Agora o DIAGNÓSTICO MDM pode ser visto no dispositivo usando o navegador Edge.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="4c8bf-174">Para ver mais facilmente o relatório de diagnóstico do MDM, navegue para a página de Access work ou school, e **selecione Ver relatório de diagnóstico avançado**.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="4c8bf-175">Isto gerará e abrirá o relatório numa nova janela Edge.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-175">This will generate and open the report in a new Edge window.</span></span>

![Consulte o relatório de diagnóstico avançado na aplicação Definições.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="4c8bf-177">Notificações de Diagnóstico Offline</span><span class="sxs-lookup"><span data-stu-id="4c8bf-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="4c8bf-178">Esta é uma atualização para uma funcionalidade existente chamada [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span><span class="sxs-lookup"><span data-stu-id="4c8bf-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="4c8bf-179">Anteriormente, não havia um indicador claro para os utilizadores de que tinham desencadeado a recolha de diagnóstico ou que tinham concluído.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="4c8bf-180">Agora adicionado no Windows builds Insider, existem duas formas de feedback audiovisual para diagnóstico offline.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="4c8bf-181">A primeira a ser torras notificações exibidas para ambos quando a recolha começa e completa.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="4c8bf-182">Estes serão apresentados quando o utilizador iniciar sessão e tiver visuais.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-182">These will be displayed when the user is logged in and has visuals.</span></span>

![Torrada para recolher troncos.](./images/logcollection1.jpg)

![Torradas quando a recolha de registos estiver completa.](./images/logcollection2.jpg)
 
<span data-ttu-id="4c8bf-185">Como os utilizadores usam frequentemente o Offline Diagnostics como um mecanismo de recolha de registos de recuo para quando não têm acesso a um ecrã, não podem fazer login ou ainda estão no OOBE, haverá também uma sugestão de áudio reproduzida quando os registos são recolhidos.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="4c8bf-186">Este som será reproduzido para além da notificação de torradas.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="4c8bf-187">Esta nova funcionalidade será ativada quando o dispositivo atualizar, e não necessita de ser ativada ou gerida.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="4c8bf-188">Em qualquer caso que este novo feedback não possa ser exibido ou ouvido, o Offline Diagnostics continuará a ser gerado.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="4c8bf-189">Esperamos que com esta mais recente adição de feedback audiovisual seja mais fácil recolher dados de diagnóstico e, mais rapidamente, ser capaz de resolver os seus problemas.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="4c8bf-190">Correções e melhorias:</span><span class="sxs-lookup"><span data-stu-id="4c8bf-190">Fixes and improvements:</span></span>

- <span data-ttu-id="4c8bf-191">Corrigiu um [problema conhecido para o Portal do Dispositivo onde não havia qualquer solicitação de descarregamento de ficheiros bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="4c8bf-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="4c8bf-192">Corrigi um [problema conhecido para o Portal do Dispositivo com upload de ficheiros e descarregamento de tempo.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="4c8bf-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="4c8bf-193">Comece a receber construções insider</span><span class="sxs-lookup"><span data-stu-id="4c8bf-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="4c8bf-194">Se ainda não foi atualizado recentemente, por favor reinicie o seu dispositivo para atualizar o estado e obter a mais recente construção.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="4c8bf-195">O comando de voz "Reboot device" funciona bem.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="4c8bf-196">Também pode escolher o botão de reinício no programa insider Definições/Windows.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="4c8bf-197">Tivemos uma escuta na parte de trás que podes ter encontrado e isto vai pôr-te de volta aos trilhos.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="4c8bf-198">Num dispositivo HoloLens 2, vá para **Definições**  >  **Update & Security** Windows Insider  >  **Program** e **selecione Get start**.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="4c8bf-199">Ligue a conta que usou para se registar como Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="4c8bf-200">Windows infiltrado está agora a mudar-se para os Canais.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="4c8bf-201">O anel **Rápido** tornar-se-á o **Canal Dev**, o anel **Lento** passará a ser o **Canal Beta**, e o anel **de pré-visualização** de lançamento tornar-se-á o **Canal de Pré-visualização de Lançamento**.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="4c8bf-202">Aqui está o que o mapeamento parece:</span><span class="sxs-lookup"><span data-stu-id="4c8bf-202">Here is what that mapping looks like:</span></span>

![Windows Explicação dos Canais Internos](images/WindowsInsiderChannels.png)

<span data-ttu-id="4c8bf-204">Para mais informações, consulte [a introdução Windows canais Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nos blogs Windows.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="4c8bf-205">Em seguida, selecione **Ative development of Windows**, escolha se gostaria de receber construções de **Dev Channel** ou Beta **Channel** e reveja os termos do programa.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="4c8bf-206">**Selecione Confirm > Reinicie agora** para terminar.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="4c8bf-207">Depois de o seu dispositivo ter sido reiniciado, vá a **Definições > Update & Security > Verifique se há novidades** para obter a mais recente construção.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="4c8bf-208">Atualizar erro 0x80070490 trabalho</span><span class="sxs-lookup"><span data-stu-id="4c8bf-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="4c8bf-209">Se encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, experimente o seguinte trabalho de curto prazo.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="4c8bf-210">Envolve mover o seu canal de insider, pegar na atualização e, em seguida, mover o seu canal Insider de volta.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="4c8bf-211">Fase um - Visualização de lançamento</span><span class="sxs-lookup"><span data-stu-id="4c8bf-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="4c8bf-212">Definições, Update & Security, Windows Insider Program, selecione **Release Preview Channel**.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="4c8bf-213">Definições, Atualizar segurança &, Windows Update, **verificar as atualizações**.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="4c8bf-214">Depois da atualização, continue para a fase dois.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="4c8bf-215">Fase dois - Canal Dev</span><span class="sxs-lookup"><span data-stu-id="4c8bf-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="4c8bf-216">Definições, Update & Security, Windows Insider Program, selecione **Dev Channel**.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="4c8bf-217">Definições, Atualizar segurança &, Windows Update, **verificar as atualizações**.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="4c8bf-218">Direções de descarregamento e flash da FFU</span><span class="sxs-lookup"><span data-stu-id="4c8bf-218">FFU download and flash directions</span></span>

<span data-ttu-id="4c8bf-219">Para testar com um voo assinado ffu, primeiro tem de voar desbloqueando o seu dispositivo antes de piscar o voo assinado ffu.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="4c8bf-220">No PC:</span><span class="sxs-lookup"><span data-stu-id="4c8bf-220">On PC:</span></span>
    1. <span data-ttu-id="4c8bf-221">Faça o download para o seu PC a partir de [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="4c8bf-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="4c8bf-222">Instalar o ARC (Advanced Recovery Companion) a partir do Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="4c8bf-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="4c8bf-223">No HoloLens - Desbloqueio de voo: Abrir **Definições**  >  **atualizar & segurança** Windows Insider  >  **Program** e depois inscrever-se, reiniciar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="4c8bf-224">Flash FFU - Agora pode piscar o voo assinado FFU usando ARC.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="4c8bf-225">Fornecer problemas de feedback e relatório</span><span class="sxs-lookup"><span data-stu-id="4c8bf-225">Provide feedback and report issues</span></span>

<span data-ttu-id="4c8bf-226">Por favor, use [a aplicação Feedback Hub](hololens-feedback.md) no seu HoloLens para fornecer problemas de feedback e relatório.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="4c8bf-227">A utilização do Feedback Hub garante que todas as informações necessárias de diagnóstico estão incluídas para ajudar os nossos engenheiros a depurar e resolver rapidamente o problema.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="4c8bf-228">Os problemas com a versão chinesa e japonesa de HoloLens devem ser reportados da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="4c8bf-229">Não se esqueça de aceitar a solicitação que pergunta se pretende que o Feedback Hub aceda à pasta Documentos (selecione **Sim** quando solicitado).</span><span class="sxs-lookup"><span data-stu-id="4c8bf-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="4c8bf-230">Nota para desenvolvedores</span><span class="sxs-lookup"><span data-stu-id="4c8bf-230">Note for developers</span></span>

<span data-ttu-id="4c8bf-231">É bem-vindo e encorajado a tentar desenvolver as suas aplicações usando as construções insider de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="4c8bf-232">Confira a [documentação do programador HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="4c8bf-233">As mesmas instruções funcionam com as construções de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="4c8bf-234">Pode usar as mesmas construções de Unidade e Visual Studio que já está a usar para HoloLens desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="4c8bf-235">Pare de receber builds Insider</span><span class="sxs-lookup"><span data-stu-id="4c8bf-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="4c8bf-236">Se já não quiser receber as construções insider de Windows Holographic, pode optar por sair quando o seu HoloLens estiver a executar uma construção de produção, ou pode recuperar o [seu dispositivo](hololens-recovery.md) utilizando o Advanced Recovery Companion para recuperar o seu dispositivo para uma versão não-Insider de Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="4c8bf-237">Existe um problema conhecido em que os utilizadores que não se matriculam no Insider Preview constroem depois de reinstalarem manualmente uma nova construção de pré-visualização experimentariam um ecrã azul.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="4c8bf-238">Depois, devem recuperar manualmente o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="4c8bf-239">Para mais detalhes sobre se você seria impactado ou não, por favor, veja mais sobre esta [Edição Conhecida.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="4c8bf-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="4c8bf-240">Para verificar se o seu HoloLens está a executar uma construção de produção:</span><span class="sxs-lookup"><span data-stu-id="4c8bf-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="4c8bf-241">Vá ao **Definições > System > About**, e encontre o número de construção.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="4c8bf-242">[Consulte as notas de lançamento para os números de construção de produção](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="4c8bf-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="4c8bf-243">Para excluir as construções insider:</span><span class="sxs-lookup"><span data-stu-id="4c8bf-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="4c8bf-244">Numa HoloLens executar uma construção de produção, vá a **Definições > Update & Security > Windows Insider Program**, e selecione **Builds Stop Insider**.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="4c8bf-245">Siga as instruções para desativar o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c8bf-245">Follow the instructions to opt out your device.</span></span>
