---
title: HoloLens Resolução de problemas do dispositivo
description: Mantenha-se atualizado sobre as soluções mais comuns para HoloLens problemas com o dispositivo e técnicas de resolução de problemas.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemas, bug, resolução de problemas, correção, ajuda, apoio, HoloLens, emulador
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635454"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="6a5fa-104">Resolução de problemas do dispositivo</span><span class="sxs-lookup"><span data-stu-id="6a5fa-104">Device Troubleshooting</span></span>

<span data-ttu-id="6a5fa-105">Este artigo descreve como resolver várias questões comuns HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="6a5fa-106">Antes de iniciar qualquer procedimento de resolução de problemas, certifique-se de que o seu dispositivo está carregado até **20 a 40%** da capacidade da bateria, se possível.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="6a5fa-107">As [luzes indicadoras](hololens2-setup.md#lights-that-indicate-the-battery-level) da bateria localizadas sob o botão de alimentação são uma forma rápida de verificar a capacidade da bateria sem iniciar sessão no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="6a5fa-108">**Problemas Conhecidos**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-108">**Known Issues**</span></span>
- [<span data-ttu-id="6a5fa-109">Vídeo de Assistência Remota congela após 20 minutos</span><span class="sxs-lookup"><span data-stu-id="6a5fa-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="6a5fa-110">O login automático pede o login</span><span class="sxs-lookup"><span data-stu-id="6a5fa-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="6a5fa-111">Microsoft Edge falha no lançamento</span><span class="sxs-lookup"><span data-stu-id="6a5fa-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="6a5fa-112">O teclado não muda para caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="6a5fa-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="6a5fa-113">Descarregar ficheiros bloqueados não mostra erro</span><span class="sxs-lookup"><span data-stu-id="6a5fa-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="6a5fa-114">Upload/download de tempos de carregamento/descarregamento de ficheiros do Portal do Dispositivo</span><span class="sxs-lookup"><span data-stu-id="6a5fa-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="6a5fa-115">Ecrã azul após desenrolar da pré-visualização insider em um dispositivo piscado com uma construção Insider</span><span class="sxs-lookup"><span data-stu-id="6a5fa-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="6a5fa-116">OneDrive não faz upload automática de imagens</span><span class="sxs-lookup"><span data-stu-id="6a5fa-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="6a5fa-117">**Geral**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-117">**General**</span></span>
- [<span data-ttu-id="6a5fa-118">HoloLens não responde ou não começa</span><span class="sxs-lookup"><span data-stu-id="6a5fa-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="6a5fa-119">Erro do "Espaço baixo do Disco"</span><span class="sxs-lookup"><span data-stu-id="6a5fa-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="6a5fa-120">Falhas de calibração</span><span class="sxs-lookup"><span data-stu-id="6a5fa-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="6a5fa-121">Não posso entrar porque o meu HoloLens foi previamente criado para outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="6a5fa-122">A unidade não está a funcionar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="6a5fa-123">Windows O Portal do Dispositivo não está a funcionar corretamente</span><span class="sxs-lookup"><span data-stu-id="6a5fa-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="6a5fa-124">O HoloLens Emulator não está a funcionar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="6a5fa-125">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-125">**Input**</span></span>
- [<span data-ttu-id="6a5fa-126">Os comandos de voz não estão a funcionar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="6a5fa-127">A entrada da mão não está a funcionar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="6a5fa-128">**Conetividade**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-128">**Connectivity**</span></span>
- [<span data-ttu-id="6a5fa-129">Não se liga a Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6a5fa-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="6a5fa-130">**Dispositivos Externos**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-130">**External Devices**</span></span> 
- [<span data-ttu-id="6a5fa-131">Bluetooth dispositivos não estão a emparelhar</span><span class="sxs-lookup"><span data-stu-id="6a5fa-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="6a5fa-132">O microfone USB-C não está a funcionar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="6a5fa-133">Dispositivos listados como disponíveis em Definições não funcionam</span><span class="sxs-lookup"><span data-stu-id="6a5fa-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="6a5fa-134">Vídeo de Assistência Remota congela após 20 minutos</span><span class="sxs-lookup"><span data-stu-id="6a5fa-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="6a5fa-135">Existe uma versão mais recente do Remote Assist que tem uma correção para este problema.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="6a5fa-136">Por [favor, atualize o Remote Assist](holographic-store-apps.md#update-apps) para a versão mais recente para evitar este problema.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="6a5fa-137">Devido à gravidade desta Edição Conhecida, tínhamos interrompido temporariamente a disponibilidade de Windows Holographic, versão 21H1.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="6a5fa-138">A construção 21H1 está agora novamente disponível, pelo que os dispositivos poderão ser novamente atualizados para a mais recente construção de 21H1.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="6a5fa-139">No mais recente lançamento de [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), alguns utilizadores do Remote Assist experimentaram o congelamento de vídeos durante as chamadas ao longo de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="6a5fa-140">Esta é uma **questão conhecida.**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="6a5fa-141">Soluções</span><span class="sxs-lookup"><span data-stu-id="6a5fa-141">Workarounds</span></span>

<span data-ttu-id="6a5fa-142">Se não conseguir atualizar o Remote Assist para uma construção mais recente, experimente o seguinte trabalho.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="6a5fa-143">Reiniciar entre chamadas</span><span class="sxs-lookup"><span data-stu-id="6a5fa-143">Restart in between calls</span></span>

<span data-ttu-id="6a5fa-144">Se as suas chamadas forem de mais de 20 minutos e estiver a experimentar este problema, tente reiniciar o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="6a5fa-145">Reiniciar o seu dispositivo entre chamadas de Assistência Remota irá refrescar o seu dispositivo e colocá-lo novamente em bom estado.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="6a5fa-146">Para reiniciar rapidamente um dispositivo Windows [Holographic, a versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) abre o menu inicial e selecione o ícone do utilizador e, em seguida, selecione **Restart**.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="6a5fa-147">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="6a5fa-148">O login automático pede o login</span><span class="sxs-lookup"><span data-stu-id="6a5fa-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="6a5fa-149">Um dispositivo HoloLens 2 pode ser configurado para iniciar sessão automaticamente através **de**  ->  **opções** de início de Definições contas  ->   -> e sob a definição **necessária** do valor para **Nunca**.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="6a5fa-150">Alguns utilizadores poderão ser obrigados a fazer login novamente no dispositivo ao atualizarem um dispositivo com uma atualização substancialmente grande, como é o caso de uma atualização de funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="6a5fa-151">Esta é uma **questão conhecida.**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-151">This is a **known issue**.</span></span>

<span data-ttu-id="6a5fa-152">Exemplo de quando isto pode ocorrer:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-152">Example of when this could occur:</span></span>

- <span data-ttu-id="6a5fa-153">Atualização de um dispositivo de Windows Holographic, versão 2004 (Build 19041.xxxx) a Windows Holographic, versão 21H1 (Build 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="6a5fa-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="6a5fa-154">Atualizar um dispositivo para fazer uma grande atualização sobre a mesma grande construção, por exemplo, Windows Holographic, versão 2004 para Windows Holographic, versão 20H2</span><span class="sxs-lookup"><span data-stu-id="6a5fa-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="6a5fa-155">Atualizar um dispositivo de uma imagem de fábrica para a imagem mais recente</span><span class="sxs-lookup"><span data-stu-id="6a5fa-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="6a5fa-156">Isto não deve ocorrer durante:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-156">This should not occur during:</span></span>

- <span data-ttu-id="6a5fa-157">Dispositivos que tomam uma atualização mensal de manutenção</span><span class="sxs-lookup"><span data-stu-id="6a5fa-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="6a5fa-158">Trabalhar em torno de métodos:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-158">Work around methods:</span></span>

- <span data-ttu-id="6a5fa-159">Métodos de entrada como PIN, Password, Íris, Autenticação Web ou teclas FIDO2.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="6a5fa-160">Se o DISPOSITIVO PIN não puder ser lembrado e não estiverem disponíveis outros métodos de autenticação, então um utilizador pode utilizar [o modo de reflashing manual](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="6a5fa-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="6a5fa-161">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="6a5fa-162">Microsoft Edge falha no lançamento</span><span class="sxs-lookup"><span data-stu-id="6a5fa-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="6a5fa-163">Esta questão foi originalmente criada com a versão de envio de Microsoft Edge em mente.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="6a5fa-164">Esta questão pode ser resolvida na [nova Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="6a5fa-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="6a5fa-165">Se não for, por favor, arquive o feedback.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="6a5fa-166">Alguns clientes relataram um problema em que Microsoft Edge não é lançado.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="6a5fa-167">Para estes clientes, o problema persiste através do reboot e não é resolvido com Windows ou atualizações de aplicações.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="6a5fa-168">Se estiver a experimentar este problema e tiver confirmado [Windows está atualizado](hololens-updates.md#manually-check-for-updates), por favor, arquive um bug da [aplicação Feedback Hub](hololens-feedback.md) com a seguinte categoria e subcategoria: Instalar e atualizar > descarregar, instalar e configurar Windows Update.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="6a5fa-169">Não há soluções alternativas conhecidas, pois não conseguimos enraizar a questão até agora.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="6a5fa-170">Arquivar um bug via Feedback Hub ajudará a nossa investigação!</span><span class="sxs-lookup"><span data-stu-id="6a5fa-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="6a5fa-171">Esta é uma **questão conhecida.**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-171">This is a **known issue**.</span></span>

[<span data-ttu-id="6a5fa-172">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="6a5fa-173">O teclado não muda para caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="6a5fa-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="6a5fa-174">Existe um problema durante o OOBE, em que uma vez que o utilizador escolheu uma conta de trabalho ou escola e está a introduzir a sua palavra-passe, tentando mudar para os caracteres especiais no teclado, tocando no botão &123 não se altera para caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="6a5fa-175">Esta é uma **questão conhecida.**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-175">This is a **known issue**.</span></span>

<span data-ttu-id="6a5fa-176">Work-arounds:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-176">Work-arounds:</span></span>
-   <span data-ttu-id="6a5fa-177">Feche o teclado e reabra-o tocando no campo de texto.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="6a5fa-178">Introduza incorretamente a sua palavra-passe.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-178">Incorrectly enter your password.</span></span> <span data-ttu-id="6a5fa-179">Quando o teclado for relançado da próxima vez, funcionará como esperado.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="6a5fa-180">Autenticação web, feche o teclado e selecione **Iniciar sôm nas costas de outro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="6a5fa-181">Se introduzir apenas números, um utilizador pode premir e segurar certas chaves para abrir um menu expandido.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="6a5fa-182">Utilizando um teclado USB.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-182">Using a USB keyboard.</span></span>

<span data-ttu-id="6a5fa-183">Isto não afeta:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-183">This does not affect:</span></span>
- <span data-ttu-id="6a5fa-184">Utilizadores que optem por utilizar uma conta pessoal.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="6a5fa-185">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="6a5fa-186">Descarregar ficheiros bloqueados não é erro</span><span class="sxs-lookup"><span data-stu-id="6a5fa-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="6a5fa-187">Esta é uma **questão conhecida** que é corrigida na Windows build Insider, versão 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="6a5fa-188">Em construções anteriores de Windows Holographic, ao tentar descarregar um ficheiro bloqueado, o resultado seria uma página de erro HTTP.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="6a5fa-189">Na Windows holográfica, a versão 21H1 atualização, tentando descarregar um ficheiro bloqueado resulta em nada visível a acontecer - o ficheiro não descarrega e não há erro.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="6a5fa-190">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="6a5fa-191">Upload/download de tempos de carregamento/descarregamento de ficheiros do Portal do Dispositivo</span><span class="sxs-lookup"><span data-stu-id="6a5fa-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="6a5fa-192">Esta é uma **questão conhecida** que é corrigida na Windows build Insider, versão 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="6a5fa-193">Se desativou previamente a Ligação SSL como parte da solução alternativa, recomendamos vivamente que a reative.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="6a5fa-194">Alguns clientes descobriram que, ao tentar carregar ou descarregar ficheiros, a operação pode parecer pendurar e, em seguida, sair ou nunca completar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="6a5fa-195">Isto é separado da questão conhecida do['ficheiro bloqueado'](#downloading-locked-files-doesnt-error) -- isto afeta Windows construções holográficas, versões 2004, 20H2 e 21H1 no mercado.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="6a5fa-196">O problema tem sido causado por um bug no tratamento do Portal do Dispositivo de determinadas solicitações, e é mais consistentemente atingido quando se utiliza https, que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="6a5fa-197">Solução</span><span class="sxs-lookup"><span data-stu-id="6a5fa-197">Workaround</span></span>

<span data-ttu-id="6a5fa-198">Esta solução, que se aplica igualmente à Wi-Fi e usbNcm, consiste em desativar a opção "necessária" em "Ligação SSL".</span><span class="sxs-lookup"><span data-stu-id="6a5fa-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="6a5fa-199">Para tal, navegue para o Portal do Dispositivo, **Sistema** e selecione a página **Preferências.**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="6a5fa-200">Na secção de Segurança do **Dispositivo,** localizar **a Ligação SSL** e desativar para desativar **a necessária**.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="6a5fa-201">O utilizador deve então ir para http://, não https:// (endereço IP) e funcionalidades como upload de ficheiros e descarregamento funcionarão.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="6a5fa-202">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="6a5fa-203">Ecrã azul após desenrolar da pré-visualização insider em um dispositivo piscado com uma construção Insider</span><span class="sxs-lookup"><span data-stu-id="6a5fa-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="6a5fa-204">Este é um problema que afeta os utilizadores que se encontram numa pré-visualização insider, relançou o seu HoloLens 2 com uma nova construção de pré-visualização insider e, em seguida, não foi inscrito no programa Insider.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="6a5fa-205">Esta é uma **questão conhecida.**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-205">This is a **known issue**.</span></span>

<span data-ttu-id="6a5fa-206">Isto não afeta:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-206">This does not affect:</span></span>
- <span data-ttu-id="6a5fa-207">Utilizadores que não estão inscritos no Windows Insider</span><span class="sxs-lookup"><span data-stu-id="6a5fa-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="6a5fa-208">Insiders:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-208">Insiders:</span></span>
    - <span data-ttu-id="6a5fa-209">Se um dispositivo foi matriculado desde as construções insider foram a versão 18362.x</span><span class="sxs-lookup"><span data-stu-id="6a5fa-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="6a5fa-210">Se eles mostraram um Insider assinado 19041.x construir e ficar inscrito no programa Insider</span><span class="sxs-lookup"><span data-stu-id="6a5fa-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="6a5fa-211">Trabalho:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-211">Work-around:</span></span> 
- <span data-ttu-id="6a5fa-212">Evite a questão</span><span class="sxs-lookup"><span data-stu-id="6a5fa-212">Avoid the issue</span></span> 
    - <span data-ttu-id="6a5fa-213">Flash uma construção não-insider.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-213">Flash a non-insider build.</span></span> <span data-ttu-id="6a5fa-214">Uma das atualizações mensais regulares.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="6a5fa-215">Fique na pré-visualização do Insider</span><span class="sxs-lookup"><span data-stu-id="6a5fa-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="6a5fa-216">Reflash o dispositivo</span><span class="sxs-lookup"><span data-stu-id="6a5fa-216">Reflash the device</span></span>

    1. <span data-ttu-id="6a5fa-217">Coloque o [HoloLens 2 no modo intermitente](hololens-recovery.md) manualmente, ligando completamente sem ligar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="6a5fa-218">Em seguida, enquanto segura o volume, toque no botão De alimentação.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="6a5fa-219">Ligação para o PC e abra o Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="6a5fa-220">Flash o HoloLens 2 para a construção predefinitiva.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="6a5fa-221">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="6a5fa-222">OneDrive não faz upload automática de imagens</span><span class="sxs-lookup"><span data-stu-id="6a5fa-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="6a5fa-223">A aplicação OneDrive para HoloLens não suporta o upload automático de câmaras para trabalho ou contas escolares.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="6a5fa-224">Esta é uma **questão conhecida.**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-224">This is a **known issue**.</span></span>

<span data-ttu-id="6a5fa-225">Soluções alternativas:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-225">Workarounds:</span></span>

- <span data-ttu-id="6a5fa-226">Se for viável para o seu negócio, o upload automático de câmaras é suportado nas contas da Microsoft do consumidor.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="6a5fa-227">Pode iniciar sôms na sua conta Microsoft para além do seu trabalho ou conta escolar (a aplicação OneDrive suporta o duplo s-in).</span><span class="sxs-lookup"><span data-stu-id="6a5fa-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="6a5fa-228">A partir do seu perfil de conta Microsoft dentro de OneDrive pode ativar o upload automático do rolo de câmara de fundo.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="6a5fa-229">Se não conseguir utilizar com segurança uma conta de consumidor da Microsoft para o upload das suas fotos automaticamente, pode enviar manualmente fotografias para o seu trabalho ou conta escolar a partir da aplicação OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="6a5fa-230">Para isso, certifique-se de que está inscrito na sua conta de trabalho ou escola na aplicação OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="6a5fa-231">Selecione o **+** botão e escolha **Upload**.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="6a5fa-232">Encontre as fotos ou vídeos que pretende fazer o upload navegando para **o Pictures > Camera Roll**.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="6a5fa-233">Selecione as fotos ou vídeos que pretende carregar e, em seguida, selecione o botão **Abrir.**</span><span class="sxs-lookup"><span data-stu-id="6a5fa-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="6a5fa-234">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="6a5fa-235">HoloLens não responde ou não começa</span><span class="sxs-lookup"><span data-stu-id="6a5fa-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="6a5fa-236">Se o seu HoloLens não começar:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="6a5fa-237">Se os LEDs ao lado do botão de alimentação não se acenderem ou apenas um LED piscar brevemente, poderá ter de [carregar o seu HoloLens.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="6a5fa-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="6a5fa-238">Se os LEDs acenderem quando premir o botão de alimentação, mas não conseguir ver nada nos visores, [faça um reset duro do dispositivo](hololens-recovery.md#hard-reset-procedure).</span><span class="sxs-lookup"><span data-stu-id="6a5fa-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="6a5fa-239">Se o seu HoloLens ficar congelado ou sem resposta:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="6a5fa-240">Desligue o HoloLens premindo o botão de alimentação até que os cinco LEDs se desliguem, ou durante 15 segundos se os LEDs não responderem.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="6a5fa-241">Para iniciar a HoloLens, prima novamente o botão de alimentação.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="6a5fa-242">Se estes passos não [funcionarem,](hololens-recovery.md) pode tentar recuperar o dispositivo HoloLens 2 ou [HoloLens (1ª geração).](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="6a5fa-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="6a5fa-243">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="6a5fa-244">Erro do "Espaço baixo do Disco"</span><span class="sxs-lookup"><span data-stu-id="6a5fa-244">"Low Disk Space" error</span></span>

<span data-ttu-id="6a5fa-245">Você precisará libertar algum espaço de armazenamento fazendo um ou mais dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="6a5fa-246">Apague alguns espaços não-reutilizados.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-246">Delete some unused spaces.</span></span> <span data-ttu-id="6a5fa-247">Vá a **Definições**  >    >  **System Spaces,** selecione um espaço que já não precisa e, em seguida, selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="6a5fa-248">Retire alguns dos hologramas que colocou.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="6a5fa-249">Elimine algumas fotos e vídeos da aplicação Fotos.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="6a5fa-250">Desinstale algumas aplicações do seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="6a5fa-251">Na lista **de aplicações Desinstalar,** toque e mantenha a aplicação que pretende desinstalar e, em seguida, selecione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="6a5fa-252">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="6a5fa-253">Falha na calibração</span><span class="sxs-lookup"><span data-stu-id="6a5fa-253">Calibration fails</span></span>

<span data-ttu-id="6a5fa-254">A calibração deve funcionar para a maioria das pessoas, mas há casos em que a calibração falha.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="6a5fa-255">Algumas razões potenciais para a falha de calibração incluem:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="6a5fa-256">Distrair-se e não seguir os objetivos de calibração</span><span class="sxs-lookup"><span data-stu-id="6a5fa-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="6a5fa-257">Visor de dispositivo sujo ou riscado não posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="6a5fa-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="6a5fa-258">Óculos sujos ou riscados</span><span class="sxs-lookup"><span data-stu-id="6a5fa-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="6a5fa-259">Certos tipos de lentes de contacto e óculos (lentes de contacto coloridas, algumas lentes de contacto toric, óculos de bloqueio de INFRAVERMELHOS, alguns óculos de prescrição elevada, óculos de sol ou similares)</span><span class="sxs-lookup"><span data-stu-id="6a5fa-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="6a5fa-260">Maquilhagem mais pronunciada e algumas extensões de pestanas</span><span class="sxs-lookup"><span data-stu-id="6a5fa-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="6a5fa-261">Cabelo ou molduras de vidro grosso se estiverem bloqueando o dispositivo de ver os seus olhos</span><span class="sxs-lookup"><span data-stu-id="6a5fa-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="6a5fa-262">Certas fisiologia ocular, condições oculares ou cirurgia ocular, tais como olhos estreitos, pestanas longas, amblyopia, nystagmus, alguns casos de LASIK ou outras cirurgias oculares</span><span class="sxs-lookup"><span data-stu-id="6a5fa-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="6a5fa-263">Se a calibração não for bem sucedida, tente:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="6a5fa-264">Limpeza da viseira do dispositivo</span><span class="sxs-lookup"><span data-stu-id="6a5fa-264">Cleaning your device visor</span></span>
- <span data-ttu-id="6a5fa-265">Limpando os óculos</span><span class="sxs-lookup"><span data-stu-id="6a5fa-265">Cleaning your glasses</span></span>
- <span data-ttu-id="6a5fa-266">Empurrando a viseira do dispositivo o mais próximo possível dos olhos</span><span class="sxs-lookup"><span data-stu-id="6a5fa-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="6a5fa-267">Movendo objetos na sua viseira para fora do caminho (como o cabelo)</span><span class="sxs-lookup"><span data-stu-id="6a5fa-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="6a5fa-268">Acendendo uma luz no seu quarto ou saindo da luz direta do sol</span><span class="sxs-lookup"><span data-stu-id="6a5fa-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="6a5fa-269">Se seguir todas as diretrizes e a calibração continuar a falhar, pode desativar a indicação de calibração Definições.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="6a5fa-270">Informe-nos também ao arquivar feedback no [Feedback Hub.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="6a5fa-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="6a5fa-271">Consulte também informações relacionadas para [a cor da imagem ou resolução de problemas de luminosidade.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="6a5fa-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="6a5fa-272">A definição de IPD não é aplicável para HoloLens 2, uma vez que as posições oculares são calculadas pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="6a5fa-273">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="6a5fa-274">Não posso entrar porque o meu HoloLens foi previamente criado para outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="6a5fa-275">Pode [colocar o dispositivo no **Modo intermitente** e utilizar](hololens-recovery.md#clean-reflash-the-device) o Advanced Recovery Companion para recuperar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="6a5fa-276">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="6a5fa-277">A unidade não está a funcionar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-277">Unity isn't working</span></span>

- <span data-ttu-id="6a5fa-278">Consulte [a instalação das ferramentas](/windows/mixed-reality/install-the-tools) para a versão mais atualizada da Unidade recomendada para HoloLens desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="6a5fa-279">As questões conhecidas com a Pré-Visualização Técnica HoloLens Unidade estão documentadas nos [fóruns da Unidade HoloLens](https://forum.unity3d.com/threads/known-issues.394627/).</span><span class="sxs-lookup"><span data-stu-id="6a5fa-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="6a5fa-280">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="6a5fa-281">Windows O Portal do Dispositivo não está a funcionar corretamente</span><span class="sxs-lookup"><span data-stu-id="6a5fa-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="6a5fa-282">A funcionalidade de visualização ao vivo na captura de Realidade Mista pode apresentar vários segundos de latência.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="6a5fa-283">Na página Entrada Virtual, os controlos Gesture e Scroll na secção Gestos Virtuais não estão funcionais.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="6a5fa-284">Usá-los não terá efeito.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-284">Using them will have no effect.</span></span> <span data-ttu-id="6a5fa-285">O teclado virtual na página de entrada virtual funciona corretamente.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="6a5fa-286">Depois de ativar o Modo de Desenvolvimento em Definições, pode demorar alguns segundos até que o interruptor ligue o Portal do Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="6a5fa-287">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="6a5fa-288">O HoloLens Emulator não está a funcionar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="6a5fa-289">A informação sobre o emulador HoloLens está localizada na nossa documentação do desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="6a5fa-290">Leia mais sobre [a resolução de problemas do emulador HoloLens.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="6a5fa-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="6a5fa-291">Nem todas as aplicações do Microsoft Store são compatíveis com o emulador.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="6a5fa-292">Por exemplo, Young Conker e Fragmentos não são jogáveis no emulador.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="6a5fa-293">Não é possível utilizar a webcam do PC no Emulator.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="6a5fa-294">A funcionalidade de pré-visualização ao vivo do Portal do Dispositivo Windows não funciona com o emulador.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="6a5fa-295">Ainda é possível capturar vídeos e imagens da Realidade Mista.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="6a5fa-296">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="6a5fa-297">Os comandos de voz não estão a funcionar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-297">Voice commands aren't working</span></span>

<span data-ttu-id="6a5fa-298">Se Cortana não responder aos comandos de voz, certifique-se de que Cortana está ligado.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="6a5fa-299">Na lista de aplicações All, selecione **Cortana**  >    >  **Menu Notebook**  >  **Definições** para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="6a5fa-300">Para saber mais sobre o que pode dizer, consulte [Use a sua voz com HoloLens](hololens-cortana.md).</span><span class="sxs-lookup"><span data-stu-id="6a5fa-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="6a5fa-301">Na HoloLens (1ª geração), o reconhecimento da fala incorporada não é configurável.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="6a5fa-302">Está sempre ligado.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-302">It is always turned on.</span></span> <span data-ttu-id="6a5fa-303">No dia 2 HoloLens, pode escolher se liga tanto o reconhecimento da fala como a Cortana durante a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="6a5fa-304">Se o seu HoloLens 2 não estiver a responder à sua voz, certifique-se de que o reconhecimento da fala está ligado.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="6a5fa-305">Vá **começar**  >  **Definições** Discurso  >  **de Privacidade**  >   e ligue o reconhecimento **da fala**.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="6a5fa-306">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="6a5fa-307">A entrada da mão não está a funcionar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-307">Hand input isn't working</span></span>

<span data-ttu-id="6a5fa-308">Para garantir que HoloLens possa ver as suas mãos, é necessário mantê-las na moldura do gesto.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="6a5fa-309">O Mixed Reality Home fornece feedback que lhe permite saber quando as suas mãos são rastreadas.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="6a5fa-310">O feedback é diferente em diferentes versões de HoloLens:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="6a5fa-311">Em HoloLens (1ª gen), o cursor de olhar muda de um ponto para um anel</span><span class="sxs-lookup"><span data-stu-id="6a5fa-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="6a5fa-312">No HoloLens 2, um cursor da ponta do dedo aparece quando a sua mão está perto de uma ardósia, e um raio de mão aparece quando as ardósias estão mais longe</span><span class="sxs-lookup"><span data-stu-id="6a5fa-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="6a5fa-313">Muitas aplicações imersivas seguem padrões de entrada semelhantes ao Mixed Reality Home.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="6a5fa-314">Saiba mais sobre a utilização da entrada manual no [HoloLens (1ª geração)](hololens1-basic-usage.md#use-hololens-with-your-hands) e [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span><span class="sxs-lookup"><span data-stu-id="6a5fa-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="6a5fa-315">Se estiver a usar luvas, note que alguns tipos de luvas não funcionam com o rastreio da mão.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="6a5fa-316">Um exemplo comum são as luvas de borracha pretas, que tendem a absorver a luz infravermelha e não são captadas pela câmara de profundidade.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="6a5fa-317">Se o seu trabalho envolve luvas de borracha, recomendamos experimentar uma cor mais clara, como azul ou cinza.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="6a5fa-318">Outro exemplo são as grandes luvas largas, que tendem a obscurecer a forma da sua mão.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="6a5fa-319">Recomendamos a utilização de luvas que sejam o mais adequadas possível para obter os melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="6a5fa-320">Se a sua viseira tiver impressões digitais ou manchas, utilize o pano de limpeza de microfibras que acompanha a HoloLens para limpar suavemente a viseira.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="6a5fa-321">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="6a5fa-322">Não consigo ligar-se a Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6a5fa-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="6a5fa-323">Aqui estão algumas coisas a experimentar se não consegue ligar o seu HoloLens a uma rede Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="6a5fa-324">Certifique-se de que Wi-Fi está ligado.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="6a5fa-325">Para verificar, use o gesto Iniciar e, em seguida, selecione **Definições** Internet  >  **&amp;**  >  **Wi-Fi da** Rede .</span><span class="sxs-lookup"><span data-stu-id="6a5fa-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="6a5fa-326">Se Wi-Fi estiver ligado, tente desligá-lo e depois ligado novamente.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="6a5fa-327">Aproxime o computador do router ou do ponto de acesso.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="6a5fa-328">Reinicie o router Wi-Fi e [reinicie HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="6a5fa-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="6a5fa-329">Tente ligar de novo.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-329">Try connecting again.</span></span>
- <span data-ttu-id="6a5fa-330">Se nenhuma destas coisas funcionar, verifique se o seu router está a utilizar o firmware mais recente.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="6a5fa-331">Pode encontrar esta informação no site do fabricante.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="6a5fa-332">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="6a5fa-333">Bluetooth dispositivos não estão a emparelhar</span><span class="sxs-lookup"><span data-stu-id="6a5fa-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="6a5fa-334">Se tiver problemas [em emparelhar um dispositivo Bluetooth,](hololens-connect-devices.md)experimente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="6a5fa-335">Vá a  >  **Definições Dispositivos**, e certifique-se de que Bluetooth está ligado.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="6a5fa-336">Se for, desligue e volte a ligá-lo.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="6a5fa-337">Certifique-se de que o seu Bluetooth dispositivo está completamente carregado ou tem pilhas frescas.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="6a5fa-338">Se ainda não conseguir ligar, [reinicie a HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="6a5fa-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="6a5fa-339">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="6a5fa-340">O microfone USB-C não está a funcionar.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="6a5fa-341">Esteja ciente de que alguns microfones USB-C se reportam incorretamente como um microfone *e* um altifalante.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="6a5fa-342">Este é um problema com o microfone e não com HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="6a5fa-343">Ao ligar um destes microfones a HoloLens, o som pode perder-se.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="6a5fa-344">Felizmente, há uma solução simples.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="6a5fa-345">No **Definições**  ->  **System**  ->  **Sound,** coloque explicitamente os altifalantes incorporados **(Controlador de áudio de recurso analógico)** como o **dispositivo Predefinido**.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="6a5fa-346">HoloLens deve lembrar-se desta definição mesmo que o microfone seja removido e reconectado mais tarde.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Resolução de problemas dos microfones USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="6a5fa-348">Dispositivos listados como disponíveis em Definições não funcionam</span><span class="sxs-lookup"><span data-stu-id="6a5fa-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="6a5fa-349">HoloLens (1ª geração) não suporta Bluetooth perfis de áudio.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="6a5fa-350">Bluetooth dispositivos de áudio, como altifalantes e auscultadores, podem aparecer como disponíveis em HoloLens configurações, mas não são suportados.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="6a5fa-351">HoloLens 2 suporta o perfil de áudio A2DP Bluetooth para reprodução estéreo.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="6a5fa-352">O perfil Bluetooth Mãos Livres que permite a captura do microfone a partir de uma Bluetooth periférico não é suportado no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="6a5fa-353">Se tiver problemas em usar um dispositivo Bluetooth, certifique-se de que é um dispositivo suportado.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="6a5fa-354">Os dispositivos suportados incluem:</span><span class="sxs-lookup"><span data-stu-id="6a5fa-354">Supported devices include the following:</span></span>

- <span data-ttu-id="6a5fa-355">QWERTY em inglês Bluetooth teclados (pode usá-los em qualquer lugar que utilize o teclado holográfico).</span><span class="sxs-lookup"><span data-stu-id="6a5fa-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="6a5fa-356">Bluetooth ratos.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-356">Bluetooth mice.</span></span>
- <span data-ttu-id="6a5fa-357">O [HoloLens clicker](hololens1-clicker.md).</span><span class="sxs-lookup"><span data-stu-id="6a5fa-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="6a5fa-358">Pode emparelhar outros dispositivos HID e GATT Bluetooth juntamente com o seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="6a5fa-359">No entanto, poderá ter de instalar aplicações de acompanhantes correspondentes a partir de Microsoft Store para utilizar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6a5fa-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="6a5fa-360">De volta à lista</span><span class="sxs-lookup"><span data-stu-id="6a5fa-360">Back to list</span></span>](#list)
