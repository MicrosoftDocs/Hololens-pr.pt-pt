---
title: Configura o seu HoloLens 2
description: Aprenda a configurar o seu HoloLens 2 pela primeira vez em Wi-Fi rede com uma conta Microsoft (MSA) ou Azure Ative Directory (AAD).
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
ms.openlocfilehash: a5c0e28eff9bb71135309ec5e484fc5b88f02d08
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636680"
---
# <a name="set-up-your-hololens-2"></a>Configura o seu HoloLens 2

A primeira vez que ligar o seu HoloLens, será guiado através da configuração do seu dispositivo, da sessão com uma conta de utilizador e da calibração da HoloLens para os olhos.  Esta secção percorre a experiência inicial de configuração HoloLens 2.

Na próxima secção, aprenderás a trabalhar com HoloLens e a interagir com hologramas. Para antecipar o artigo, consulte ["Obter HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Antes de começar

Antes de começar, certifique-se de ter o seguinte disponível:

**Uma ligação de rede**. Terá de ligar o seu HoloLens a uma rede para o configurar. Com HoloLens 2, pode ligar-se com Wi-Fi ou utilizando o ethernet (precisará de um adaptador USB-C-para-Ethernet). A primeira vez que se conectar, precisará de uma rede aberta ou protegida por palavra-passe que não exija navegar para um website ou usar certificados para se conectar. [Saiba mais sobre os websites que HoloLens utiliza.](hololens-offline.md)

**Uma conta Microsoft.** Também terá de iniciar scontabilidade para HoloLens com uma conta Microsoft (ou com a sua conta de trabalho, se a sua organização possuir o dispositivo). Se não tiver uma conta Microsoft, vá a [account.microsoft.com](https://account.microsoft.com) e crie uma de graça.

**Um espaço seguro e bem iluminado sem perigos de tropeçar.** [Informações de saúde e segurança.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Os acessórios de conforto opcionais** que acompanham o seu HoloLens, para ajudá-lo a obter o ajuste mais confortável. [Mais sobre o ajuste e o conforto.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Configurar o Windows

A primeira vez que começas o teu HoloLens 2, a tua primeira tarefa é configurar Windows Holographic.  Quando iniciar a sua HoloLens, ouvirá música e verá um logotipo Windows.

![Primeiro ecrã durante a primeira bota](images/01-magic-moment.png)

Verá um beija-flor voando por aí.

![Beija-flor voando](images/hummingbird-1.png)

Siga com a mão.

![Beija-flor voando de perto](images/hummingbird-2.png)

HoloLens 2 irá acompanhá-lo através dos seguintes passos:

1. Selecione o seu idioma.

    ![Selecionar idioma](images/04-language.png)

1. Selecione a sua região.

    ![Selecione região](images/05-region.png)

1. Calibra HoloLens aos olhos.  Se optar por saltar a calibração, será solicitado da próxima vez que iniciar sessão. 

    1. Primeiro, vai ajustar a sua viseira.
    
        ![Tela de seleção de calibração](images/06-et-corners.png)

    2. Para calibrar, você vai olhar para um conjunto de alvos (referidos como pedras preciosas). Tudo bem se piscar ou fechar os olhos durante a calibração, mas tente não olhar para outros objetos na sala ou no espaço físico. HoloLens usa este processo para aprender sobre a sua posição ocular para que possa tornar melhor o seu mundo holográfico. 

        ![Ajuste-se para os seus olhos](images/07-adjust-eyes.png)

        Após a calibração, os hologramas aparecerão corretamente, mesmo quando a viseira se desloca na sua cabeça. As informações de calibração são armazenadas localmente no dispositivo e não estão associadas a nenhuma informação da conta. Para obter mais informações, consulte [os dados de calibração e segurança.](hololens-calibration.md#calibration-data-and-security)

        ![A calibração está completa](images/calibration-complete.png)

1. Ligação à internet (selecione Wi-Fi ou a sua ligação ethernet).

     HoloLens define automaticamente o seu fuso horário com base em informações obtidas a partir da rede Wi-Fi. Após o acabamento da configuração, pode alterar o fuso horário utilizando a aplicação Definições.

    ![Ligar a uma rede Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Se progredir para além do passo Wi-Fi e mais tarde precisar de mudar para uma rede diferente enquanto ainda estiver configurado, pode premir simultaneamente os botões **Volume Down** e **Power** para voltar a este passo se estiver a executar uma versão SO a partir de outubro de 2019 ou mais tarde. Para versões anteriores, poderá ser necessário [reiniciar o dispositivo](hololens-recovery.md) ou reiniciá-lo num local onde a rede Wi-Fi não esteja disponível para evitar a sua ligação automática.
    > 
    > Note também que durante HoloLens Configuração, há um tempo de credencial de dois minutos. O nome de utilizador/palavra-passe tem de ser introduzido dentro de dois minutos, caso contrário o campo do nome de utilizador será automaticamente limpo.

1. HoloLens 2 procurará e aplicará um perfil de piloto automático se existir. Não é necessária nenhuma ação neste ecrã.
 
    ![Pesquisa de perfil de piloto automático](images/autopilot-profile-search.png) 

1. Clique em **Aceitar** no ecrã de licenciamento.

    ![Windows contrato de licença](images/windows-license-agreement.png)

1. Inscreva-se na sua conta de utilizador. Vais escolher entre **o meu trabalho ou a minha escola** e eu sou o **dono.**

    ![Definir utilizador](images/13-device-owner.png)
    - Quando escolher **O meu trabalho ou escola é dono dele,** inscreva-se com uma conta AZure AD. Se a sua organização utilizar Azure AD Premium e tiver configurado a inscrição automática de MDM, HoloLens matricula-se automaticamente no MDM. Se a sua organização não utilizar Azure AD Premium, a inscrição automática de MDM não está disponível. Nesse caso, é necessário [inscrever manualmente HoloLens na gestão do dispositivo.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Insira as informações da sua conta organizacional.
        1. Aceite a declaração de privacidade e o contrato de licença do utilizador final.
        1. Inscreva-se utilizando as suas credenciais Azure AD. Isto pode redirecionar para a página de início de sção da sua organização.
        1. Continue a configurar o dispositivo.

    - Quando **escolheres o dono,** inscreves-te com uma conta Microsoft. Após a conclusão da configuração, pode [inscrever-se manualmente HoloLens na gestão do dispositivo](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Introduza as informações da sua conta microsoft.
        2. Introduza a palavra-passe. Se a sua conta Microsoft necessitar [de verificação em duas etapas (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)complete o processo de verificação.

        
1. Configurar o sinal de iris selecionando em **seguida**. Você vai passar por uma experiência semelhante à calibração dos olhos. Selecione **Feito** quando a varredura estiver completa. Também pode selecionar **Skip** para contornar este passo.
    
    ![Conclusão da ](images/setup-iris.png) ![ configuração da Íris Iris](images/iris-setup-complete.png) 
     
  
1. Irá configurar um PIN para iniciar sessão no dispositivo. Este PIN é específico do dispositivo. 

    ![Windows Hello de configuração](images/setup-windows-hello.png)

    ![Configuração Windows Hello PIN](images/windows-hello-pin.png)

    ![Windows Hello Configuração bem sucedida](images/windows-hello-successful.png) 
    
1. Selecione se ativar a fala no HoloLens 2.

    ![Ativar Cortana](images/22-do-more-with-voice.png)

1. Selecione se ativa a localização no HoloLens 2.
    
    ![Ativar serviços de localização](images/setup-location-services.png)

1. Selecione o seu nível de telemetria. Se puder, por favor, ative a telemetria opcional. Esta informação realmente ajuda a HoloLens equipa de engenharia.

     ![Nível de telemetria](images/24-telemetry.png)

1. Aprenda a usar o gesto inicial no HoloLens 2.

     ![Aprenda a usar o gesto inicial, imagem 1](images/26-01-startmenu-learning.png)

     ![Aprenda a usar o gesto inicial, imagem 2](images/26-02-startmenu-learning.png)

Parabéns!  A configuração está completa e está pronto a usar HoloLens!

## <a name="next-steps"></a>Passos seguintes

1. Comece logo a interagir com a Realidade Mista e navegue Windows 10 no seu HoloLens - confira a app **Sugestões** para tutoriais práticos para interações com as mãos. Use o gesto inicial para ir para Iniciar ou dizer "Vá para começar" e selecione Sugestões.

1. Clique abaixo para continuar a ler sobre como contornar HoloLens 2.

> [!div class="nextstepaction"]
> [Introdução ao HoloLens 2](hololens2-basic-usage.md)
