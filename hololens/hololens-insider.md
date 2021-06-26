---
title: Pré-visualização insider para Microsoft HoloLens
description: Saiba como começar com as construções insider e forneça feedback valioso para a nossa próxima grande atualização do sistema operativo para HoloLens.
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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924371"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="4ad3a-103">Pré-visualização insider para Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="4ad3a-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="4ad3a-104">Bem-vindos às mais recentes construções insider preview para HoloLens!</span><span class="sxs-lookup"><span data-stu-id="4ad3a-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="4ad3a-105">É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer feedback valioso para a nossa próxima grande atualização do sistema operativo para holoLens.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="4ad3a-106">Notas de lançamento do Windows Insider</span><span class="sxs-lookup"><span data-stu-id="4ad3a-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="4ad3a-107">Estamos entusiasmados por voltar a voar novas funcionalidades para o Windows Insiders.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="4ad3a-108">Novas construções serão voadas para os Canais Dev e Beta para as últimas atualizações.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="4ad3a-109">Continuaremos a atualizar esta página à medida que adicionamos mais funcionalidades e atualizações às nossas construções do Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="4ad3a-110">Fique animado e pronto para misturar estas atualizações na sua realidade.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-110">Get excited and ready to mix these updates into your reality.</span></span> 

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="4ad3a-111">Alterações no CSP nos HoloLens</span><span class="sxs-lookup"><span data-stu-id="4ad3a-111">CSP changes on HoloLens</span></span>
 
- <span data-ttu-id="4ad3a-112">Introduzido na construção do Windows Insider, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="4ad3a-112">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="4ad3a-113">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="4ad3a-113">DevDetail CSP</span></span>

<span data-ttu-id="4ad3a-114">O DevDetail CSP também reporta espaço de armazenamento gratuito no dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-114">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="4ad3a-115">Isto deve corresponder aproximadamente ao valor mostrado na página de Armazenamento da App de Definições.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-115">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="4ad3a-116">Segue-se o nó específico que contém esta informação.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-116">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="4ad3a-117">./DevDetail/Ext/Microsoft/FreeStorage (apenas operação GET)</span><span class="sxs-lookup"><span data-stu-id="4ad3a-117">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="4ad3a-118">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="4ad3a-118">DeviceStatus CSP</span></span>

<span data-ttu-id="4ad3a-119">DeviceStatus CSP agora também reporta SSID e BSSID da rede Wifi com a qual holoLens está ativamente conectado.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-119">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="4ad3a-120">Seguem-se os nós específicos que contêm esta informação.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-120">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="4ad3a-121">./Fornecedor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address do adaptador de Wi-Fi*/SSID</span><span class="sxs-lookup"><span data-stu-id="4ad3a-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="4ad3a-122">./Fornecedor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address do adaptador Wi-Fi*/BSSID</span><span class="sxs-lookup"><span data-stu-id="4ad3a-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="4ad3a-123">Blob de sincronização de exemplo (para fornecedores de MDM) para consulta para NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="4ad3a-123">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

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

### <a name="fixes-and-improvements"></a><span data-ttu-id="4ad3a-124">Correções e melhorias:</span><span class="sxs-lookup"><span data-stu-id="4ad3a-124">Fixes and improvements:</span></span>

- <span data-ttu-id="4ad3a-125">Corrigiu um [problema conhecido para o Portal do Dispositivo onde não havia qualquer solicitação de descarregamento de ficheiros bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="4ad3a-125">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="4ad3a-126">Corrigi um [problema conhecido para o Portal do Dispositivo com upload de ficheiros e descarregamento de tempo.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="4ad3a-126">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="4ad3a-127">Comece a receber construções insider</span><span class="sxs-lookup"><span data-stu-id="4ad3a-127">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="4ad3a-128">Se ainda não foi atualizado recentemente, por favor reinicie o seu dispositivo para atualizar o estado e obter a mais recente construção.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-128">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="4ad3a-129">O comando de voz "Reboot device" funciona bem.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-129">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="4ad3a-130">Também pode escolher o botão de reinício em Definições/Programa Insider do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-130">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="4ad3a-131">Tivemos uma escuta na parte de trás que podes ter encontrado e isto vai pôr-te de volta aos trilhos.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-131">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="4ad3a-132">Num dispositivo HoloLens 2 aceda a **Definições**  >  **Atualizar & Programa de Segurança** Do Windows  >  **Insider** e **selecione Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-132">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="4ad3a-133">Ligue a conta que usou para registar como Um Insider do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-133">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="4ad3a-134">O insider do Windows está agora a mudar-se para os Canais.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-134">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="4ad3a-135">O anel **Rápido** tornar-se-á o **Canal Dev**, o anel **Lento** passará a ser o **Canal Beta**, e o anel **de pré-visualização** de lançamento tornar-se-á o **Canal de Pré-visualização de Lançamento**.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-135">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="4ad3a-136">Eis o que esse mapeamento parece: ![ explicação dos canais Insider do Windows ](images/WindowsInsiderChannels.png) Para obter mais informações, consulte [a introdução dos canais Insider do Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nos blogs do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-136">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="4ad3a-137">Em seguida, selecione **Ative development of Windows**, escolha se gostaria de receber construções de **Dev Channel** ou Beta **Channel** e reveja os termos do programa.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-137">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="4ad3a-138">**Selecione Confirm > Reinicie agora** para terminar.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-138">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="4ad3a-139">Depois de o seu dispositivo ter sido reiniciado, vá a **Definições > Atualizar & Segurança > Verifique se há atualizações** para obter a mais recente construção.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-139">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="4ad3a-140">Atualizar erro 0x80070490 trabalho</span><span class="sxs-lookup"><span data-stu-id="4ad3a-140">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="4ad3a-141">Se encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, experimente o seguinte trabalho de curto prazo.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-141">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="4ad3a-142">Envolve mover o seu canal de insider, pegar na atualização e, em seguida, mover o seu canal Insider de volta.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-142">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="4ad3a-143">Fase um - Visualização de lançamento</span><span class="sxs-lookup"><span data-stu-id="4ad3a-143">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="4ad3a-144">Definições, Atualizar & Segurança, Programa De Insider do Windows, selecione **Release Preview Channel**.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-144">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="4ad3a-145">Definições, Atualizar & Segurança, Atualização do Windows, **Verificar atualizações**.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-145">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="4ad3a-146">Depois da atualização, continue para a fase dois.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-146">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="4ad3a-147">Fase dois - Canal Dev</span><span class="sxs-lookup"><span data-stu-id="4ad3a-147">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="4ad3a-148">Definições, Atualizar & Segurança, Programa De Insider do Windows, selecione **Dev Channel**.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-148">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="4ad3a-149">Definições, Atualizar & Segurança, Atualização do Windows, **Verificar atualizações**.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-149">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="4ad3a-150">Direções de descarregamento e flash da FFU</span><span class="sxs-lookup"><span data-stu-id="4ad3a-150">FFU download and flash directions</span></span>
<span data-ttu-id="4ad3a-151">Para testar com um voo assinado ffu, primeiro tem de voar desbloqueando o seu dispositivo antes de piscar o voo assinado ffu.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-151">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="4ad3a-152">No PC:</span><span class="sxs-lookup"><span data-stu-id="4ad3a-152">On PC:</span></span>
    1. <span data-ttu-id="4ad3a-153">Faça o download para o seu PC a partir de [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="4ad3a-153">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="4ad3a-154">Instale o ARC (Advanced Recovery Companion) a partir da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="4ad3a-154">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="4ad3a-155">No HoloLens - Desbloqueio de voo: Atualização de **definições abertas**  >  **& Programa de Segurança** Do Windows  >  **Insider,** em seguida, inscreva-se, reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-155">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="4ad3a-156">Flash FFU - Agora pode piscar o voo assinado FFU usando ARC.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-156">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="4ad3a-157">Fornecer problemas de feedback e relatório</span><span class="sxs-lookup"><span data-stu-id="4ad3a-157">Provide feedback and report issues</span></span>
<span data-ttu-id="4ad3a-158">Por favor, use [a aplicação Feedback Hub](hololens-feedback.md) nos seus HoloLens para fornecer problemas de feedback e relatório.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-158">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="4ad3a-159">A utilização do Feedback Hub garante que todas as informações necessárias de diagnóstico estão incluídas para ajudar os nossos engenheiros a depurar e resolver rapidamente o problema.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-159">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="4ad3a-160">Os problemas com a versão chinesa e japonesa dos HoloLens devem ser relatados da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-160">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="4ad3a-161">Não se esqueça de aceitar a solicitação que pergunta se pretende que o Feedback Hub aceda à pasta Documentos (selecione **Sim** quando solicitado).</span><span class="sxs-lookup"><span data-stu-id="4ad3a-161">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="4ad3a-162">Nota para desenvolvedores</span><span class="sxs-lookup"><span data-stu-id="4ad3a-162">Note for developers</span></span>
<span data-ttu-id="4ad3a-163">É bem-vindo e encorajado a tentar desenvolver as suas aplicações usando as construções Insider da HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-163">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="4ad3a-164">Consulte a [Documentação do Desenvolvedor holoLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-164">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="4ad3a-165">As mesmas instruções funcionam com as construções insider dos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-165">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="4ad3a-166">Pode utilizar as mesmas construções de Unidade e Estúdio Visual que já está a usar para o desenvolvimento do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-166">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="4ad3a-167">Pare de receber builds Insider</span><span class="sxs-lookup"><span data-stu-id="4ad3a-167">Stop receiving Insider builds</span></span>
<span data-ttu-id="4ad3a-168">Se já não pretender receber as construções insider do Windows Holographic, pode optar por sair quando os hololes estiverem a executar uma produção, ou pode recuperar o [seu dispositivo](hololens-recovery.md) utilizando o Advanced Recovery Companion para recuperar o seu dispositivo para uma versão não-Insider do Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-168">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="4ad3a-169">Existe um problema conhecido em que os utilizadores que não se matriculam no Insider Preview constroem depois de reinstalarem manualmente uma nova construção de pré-visualização experimentariam um ecrã azul.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-169">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="4ad3a-170">Depois, devem recuperar manualmente o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-170">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="4ad3a-171">Para mais detalhes sobre se você seria impactado ou não, por favor, veja mais sobre esta [Edição Conhecida.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="4ad3a-171">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="4ad3a-172">Para verificar se os seus HoloLens estão a executar uma construção de produção:</span><span class="sxs-lookup"><span data-stu-id="4ad3a-172">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="4ad3a-173">Vá a **Definições > System > Sobre**, e encontre o número de construção.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-173">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="4ad3a-174">[Consulte as notas de lançamento para os números de construção de produção](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="4ad3a-174">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="4ad3a-175">Para excluir as construções insider:</span><span class="sxs-lookup"><span data-stu-id="4ad3a-175">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="4ad3a-176">Num HoloLens que executa uma construção de produção, vá a **Definições > Atualização & Security > Programa Do Windows Insider**, e selecione **builds Stop Insider**.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-176">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="4ad3a-177">Siga as instruções para desativar o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ad3a-177">Follow the instructions to opt out your device.</span></span>
