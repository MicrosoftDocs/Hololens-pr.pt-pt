---
title: Configurar os seus HoloLens 2
description: Saiba como configurar o seu HoloLens 2 pela primeira vez em Wi-Fi rede com uma conta Microsoft (MSA) ou Azure Ative Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923787"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="71640-104">Configurar os seus HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="71640-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="71640-105">A primeira vez que ligar os HoloLens, será guiado através da configuração do seu dispositivo, da sessão com uma conta de utilizador e da calibração dos HoloLens para os seus olhos.</span><span class="sxs-lookup"><span data-stu-id="71640-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="71640-106">Esta secção percorre a experiência inicial de configuração hololens 2.</span><span class="sxs-lookup"><span data-stu-id="71640-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="71640-107">Na próxima secção, aprenderás a trabalhar com hololens e a interagir com hologramas.</span><span class="sxs-lookup"><span data-stu-id="71640-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="71640-108">Para antecipar o artigo, consulte [Getting around HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="71640-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="71640-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="71640-109">Before you start</span></span>

<span data-ttu-id="71640-110">Antes de começar, certifique-se de ter o seguinte disponível:</span><span class="sxs-lookup"><span data-stu-id="71640-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="71640-111">**Uma ligação de rede**.</span><span class="sxs-lookup"><span data-stu-id="71640-111">**A network connection**.</span></span> <span data-ttu-id="71640-112">Terá de ligar os HoloLens a uma rede para o configurar.</span><span class="sxs-lookup"><span data-stu-id="71640-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="71640-113">Com hololens 2, pode conectar-se com Wi-Fi ou utilizando ethernet (precisará de um adaptador USB-C-para-Ethernet).</span><span class="sxs-lookup"><span data-stu-id="71640-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="71640-114">A primeira vez que se conectar, precisará de uma rede aberta ou protegida por palavra-passe que não exija navegar para um website ou usar certificados para se conectar.</span><span class="sxs-lookup"><span data-stu-id="71640-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="71640-115">[Saiba mais sobre os websites que o HoloLens utiliza.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="71640-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="71640-116">**Uma conta Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="71640-116">**A Microsoft account**.</span></span> <span data-ttu-id="71640-117">Também terá de iniciar scontabilidade no HoloLens com uma conta Microsoft (ou com a sua conta de trabalho, se a sua organização possuir o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="71640-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="71640-118">Se não tiver uma conta Microsoft, vá a [account.microsoft.com](https://account.microsoft.com) e crie uma de graça.</span><span class="sxs-lookup"><span data-stu-id="71640-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="71640-119">**Um espaço seguro e bem iluminado sem perigos de tropeçar.**</span><span class="sxs-lookup"><span data-stu-id="71640-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="71640-120">[Informações de saúde e segurança.](https://go.microsoft.com/fwlink/p/?LinkId=746661)</span><span class="sxs-lookup"><span data-stu-id="71640-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="71640-121">**Os acessórios de conforto opcionais** que vieram com os seus HoloLens, para ajudá-lo a obter o ajuste mais confortável.</span><span class="sxs-lookup"><span data-stu-id="71640-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="71640-122">[Mais sobre o ajuste e o conforto.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="71640-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="71640-123">Configurar o Windows</span><span class="sxs-lookup"><span data-stu-id="71640-123">Set up Windows</span></span>

<span data-ttu-id="71640-124">A primeira vez que inicia os HoloLens 2, a sua primeira tarefa é configurar o Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="71640-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="71640-125">Quando iniciar os HoloLens, ouvirá música e verá um logótipo do Windows.</span><span class="sxs-lookup"><span data-stu-id="71640-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Primeiro ecrã durante a primeira bota](images/01-magic-moment.png)

<span data-ttu-id="71640-127">HoloLens 2 irá acompanhá-lo através dos seguintes passos:</span><span class="sxs-lookup"><span data-stu-id="71640-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="71640-128">Selecione o seu idioma.</span><span class="sxs-lookup"><span data-stu-id="71640-128">Select your language.</span></span>

    ![Selecionar idioma](images/04-language.png)

1. <span data-ttu-id="71640-130">Selecione a sua região.</span><span class="sxs-lookup"><span data-stu-id="71640-130">Select your region.</span></span>

    ![Selecione região](images/05-region.png)

1. <span data-ttu-id="71640-132">Calibra holoLens aos teus olhos.</span><span class="sxs-lookup"><span data-stu-id="71640-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="71640-133">Se optar por saltar a calibração, será solicitado da próxima vez que iniciar sessão.</span><span class="sxs-lookup"><span data-stu-id="71640-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="71640-134">Primeiro, vai ajustar a sua viseira.</span><span class="sxs-lookup"><span data-stu-id="71640-134">First, you'll adjust your visor.</span></span>
    
        ![Tela de seleção de calibração](images/06-et-corners.png)

    2. <span data-ttu-id="71640-136">Para calibrar, você vai olhar para um conjunto de alvos (referidos como pedras preciosas).</span><span class="sxs-lookup"><span data-stu-id="71640-136">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="71640-137">Tudo bem se piscar ou fechar os olhos durante a calibração, mas tente não olhar para outros objetos na sala ou no espaço físico.</span><span class="sxs-lookup"><span data-stu-id="71640-137">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="71640-138">HoloLens usa este processo para aprender sobre a sua posição ocular para que possa tornar melhor o seu mundo holográfico.</span><span class="sxs-lookup"><span data-stu-id="71640-138">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Ajuste-se para os seus olhos](images/07-adjust-eyes.png)

        <span data-ttu-id="71640-140">Após a calibração, os hologramas aparecerão corretamente, mesmo quando a viseira se desloca na sua cabeça.</span><span class="sxs-lookup"><span data-stu-id="71640-140">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="71640-141">As informações de calibração são armazenadas localmente no dispositivo e não estão associadas a nenhuma informação da conta.</span><span class="sxs-lookup"><span data-stu-id="71640-141">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="71640-142">Para obter mais informações, consulte [os dados de calibração e segurança.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="71640-142">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![A calibração está completa](images/calibration-complete.png)

1. <span data-ttu-id="71640-144">Ligue-se à internet (selecione Wi-Fi ou a sua ligação ethernet).</span><span class="sxs-lookup"><span data-stu-id="71640-144">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="71640-145">O HoloLens define o seu fuso horário automaticamente com base em informações obtidas a partir da rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="71640-145">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="71640-146">Após o acabamento da configuração, pode alterar o fuso horário utilizando a aplicação Definições.</span><span class="sxs-lookup"><span data-stu-id="71640-146">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Ligar a uma rede Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="71640-148">Se progredir para além do passo Wi-Fi e mais tarde precisar de mudar para uma rede diferente enquanto ainda estiver configurado, pode premir simultaneamente os botões **Volume Down** e **Power** para voltar a este passo se estiver a executar uma versão SO a partir de outubro de 2019 ou mais tarde.</span><span class="sxs-lookup"><span data-stu-id="71640-148">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="71640-149">Para versões anteriores, poderá ser necessário [reiniciar o dispositivo](hololens-recovery.md) ou reiniciá-lo num local onde a rede Wi-Fi não esteja disponível para evitar a sua ligação automática.</span><span class="sxs-lookup"><span data-stu-id="71640-149">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="71640-150">Note também que durante a configuração hololes, há uma pausa de credencial de dois minutos.</span><span class="sxs-lookup"><span data-stu-id="71640-150">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="71640-151">O nome de utilizador/palavra-passe tem de ser introduzido dentro de dois minutos, caso contrário o campo do nome de utilizador será automaticamente limpo.</span><span class="sxs-lookup"><span data-stu-id="71640-151">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="71640-152">HoloLens 2 procurará e aplicará um perfil autopiloto se existir.</span><span class="sxs-lookup"><span data-stu-id="71640-152">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="71640-153">Não é necessária nenhuma ação neste ecrã.</span><span class="sxs-lookup"><span data-stu-id="71640-153">No action is needed on this screen.</span></span>
 
    ![Pesquisa de perfil de piloto automático](images/autopilot-profile-search.png) 

1. <span data-ttu-id="71640-155">Clique em **Aceitar** no ecrã de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="71640-155">Click **Accept** on the licensing screen.</span></span>

    ![Contrato de licença do Windows](images/windows-license-agreement.png)

1. <span data-ttu-id="71640-157">Inscreva-se na sua conta de utilizador.</span><span class="sxs-lookup"><span data-stu-id="71640-157">Sign in to your user account.</span></span> <span data-ttu-id="71640-158">Vais escolher entre **o meu trabalho ou a minha escola** e eu sou o **dono.**</span><span class="sxs-lookup"><span data-stu-id="71640-158">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="71640-159">Quando escolher **O meu trabalho ou escola é dono dele,** inscreva-se com uma conta AZure AD.</span><span class="sxs-lookup"><span data-stu-id="71640-159">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="71640-160">Se a sua organização utilizar o Azure AD Premium e tiver configurado a inscrição automática de MDM, a HoloLens matricula-se automaticamente no MDM.</span><span class="sxs-lookup"><span data-stu-id="71640-160">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="71640-161">Se a sua organização não utilizar o Azure AD Premium, a inscrição automática de MDM não está disponível.</span><span class="sxs-lookup"><span data-stu-id="71640-161">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="71640-162">Nesse caso, é necessário [inscrever manualmente holoLens na gestão do dispositivo.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="71640-162">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="71640-163">Insira as informações da sua conta organizacional.</span><span class="sxs-lookup"><span data-stu-id="71640-163">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="71640-164">Aceite a declaração de privacidade e o contrato de licença do utilizador final.</span><span class="sxs-lookup"><span data-stu-id="71640-164">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="71640-165">Inscreva-se utilizando as suas credenciais Azure AD.</span><span class="sxs-lookup"><span data-stu-id="71640-165">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="71640-166">Isto pode redirecionar para a página de início de sção da sua organização.</span><span class="sxs-lookup"><span data-stu-id="71640-166">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="71640-167">Continue a configurar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="71640-167">Continue setting up the device.</span></span>

    - <span data-ttu-id="71640-168">Quando **escolheres o dono,** inscreves-te com uma conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71640-168">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="71640-169">Após a configuração estar concluída, pode [inscrever os HoloLens manualmente na gestão do dispositivo.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="71640-169">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="71640-170">Introduza as informações da sua conta microsoft.</span><span class="sxs-lookup"><span data-stu-id="71640-170">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="71640-171">Introduza a palavra-passe.</span><span class="sxs-lookup"><span data-stu-id="71640-171">Enter your password.</span></span> <span data-ttu-id="71640-172">Se a sua conta Microsoft necessitar [de verificação em duas etapas (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)complete o processo de verificação.</span><span class="sxs-lookup"><span data-stu-id="71640-172">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Definir utilizador](images/13-device-owner.png)

1. <span data-ttu-id="71640-174">Configurar o sinal de iris selecionando em **seguida**.</span><span class="sxs-lookup"><span data-stu-id="71640-174">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="71640-175">Você vai passar por uma experiência semelhante à calibração dos olhos.</span><span class="sxs-lookup"><span data-stu-id="71640-175">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="71640-176">Selecione **Feito** quando a varredura estiver completa.</span><span class="sxs-lookup"><span data-stu-id="71640-176">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="71640-177">Também pode selecionar **Skip** para contornar este passo.</span><span class="sxs-lookup"><span data-stu-id="71640-177">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="71640-178">![Conclusão da ](images/setup-iris.png) ![ configuração da Íris Iris](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="71640-178">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="71640-179">Irá configurar um PIN para iniciar sessão no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="71640-179">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="71640-180">Este PIN é específico do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="71640-180">This PIN is device specific.</span></span> 

    ![Configuração Windows Olá](images/setup-windows-hello.png)

    ![Configuração Windows Hello PIN](images/windows-hello-pin.png)

    ![Windows Hello Setup bem sucedido](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="71640-184">Selecione se ativar a fala no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="71640-184">Select whether to enable speech on HoloLens 2.</span></span>

    ![Ativar cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="71640-186">Selecione se ativa a localização no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="71640-186">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Ativar serviços de localização](images/setup-location-services.png)

1. <span data-ttu-id="71640-188">Selecione o seu nível de telemetria.</span><span class="sxs-lookup"><span data-stu-id="71640-188">Select your telemetry level.</span></span> <span data-ttu-id="71640-189">Se puder, por favor, ative a telemetria opcional.</span><span class="sxs-lookup"><span data-stu-id="71640-189">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="71640-190">Esta informação realmente ajuda a equipa de engenharia hololens.</span><span class="sxs-lookup"><span data-stu-id="71640-190">This information really helps the HoloLens engineering team.</span></span>

     ![Nível de telemetria](images/24-telemetry.png)

1. <span data-ttu-id="71640-192">Aprenda a usar o gesto inicial no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="71640-192">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Aprenda a usar o gesto inicial, imagem 1](images/26-01-startmenu-learning.png)

     ![Aprenda a usar o gesto inicial, imagem 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="71640-195">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="71640-195">Congratulations!</span></span>  <span data-ttu-id="71640-196">A configuração está completa e está pronto para usar HoloLens!</span><span class="sxs-lookup"><span data-stu-id="71640-196">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="71640-197">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="71640-197">Next steps</span></span>

1. <span data-ttu-id="71640-198">Comece a interagir imediatamente com a Realidade Mista e navegue no Windows 10 nos seus HoloLens - consulte a aplicação **Tips** para tutoriais práticos para interações com as mãos.</span><span class="sxs-lookup"><span data-stu-id="71640-198">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="71640-199">Use o gesto inicial para ir para Iniciar ou dizer "Vá para começar" e selecione Dicas.</span><span class="sxs-lookup"><span data-stu-id="71640-199">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="71640-200">Clique abaixo para continuar a ler sobre como contornar HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="71640-200">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="71640-201">Introdução ao HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="71640-201">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
