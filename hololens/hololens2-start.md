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
# <a name="set-up-your-hololens-2"></a>Configurar os seus HoloLens 2

A primeira vez que ligar os HoloLens, será guiado através da configuração do seu dispositivo, da sessão com uma conta de utilizador e da calibração dos HoloLens para os seus olhos.  Esta secção percorre a experiência inicial de configuração hololens 2.

Na próxima secção, aprenderás a trabalhar com hololens e a interagir com hologramas. Para antecipar o artigo, consulte [Getting around HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Antes de começar

Antes de começar, certifique-se de ter o seguinte disponível:

**Uma ligação de rede**. Terá de ligar os HoloLens a uma rede para o configurar. Com hololens 2, pode conectar-se com Wi-Fi ou utilizando ethernet (precisará de um adaptador USB-C-para-Ethernet). A primeira vez que se conectar, precisará de uma rede aberta ou protegida por palavra-passe que não exija navegar para um website ou usar certificados para se conectar. [Saiba mais sobre os websites que o HoloLens utiliza.](hololens-offline.md)

**Uma conta Microsoft.** Também terá de iniciar scontabilidade no HoloLens com uma conta Microsoft (ou com a sua conta de trabalho, se a sua organização possuir o dispositivo). Se não tiver uma conta Microsoft, vá a [account.microsoft.com](https://account.microsoft.com) e crie uma de graça.

**Um espaço seguro e bem iluminado sem perigos de tropeçar.** [Informações de saúde e segurança.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Os acessórios de conforto opcionais** que vieram com os seus HoloLens, para ajudá-lo a obter o ajuste mais confortável. [Mais sobre o ajuste e o conforto.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Configurar o Windows

A primeira vez que inicia os HoloLens 2, a sua primeira tarefa é configurar o Windows Holographic.  Quando iniciar os HoloLens, ouvirá música e verá um logótipo do Windows.

![Primeiro ecrã durante a primeira bota](images/01-magic-moment.png)

HoloLens 2 irá acompanhá-lo através dos seguintes passos:

1. Selecione o seu idioma.

    ![Selecionar idioma](images/04-language.png)

1. Selecione a sua região.

    ![Selecione região](images/05-region.png)

1. Calibra holoLens aos teus olhos.  Se optar por saltar a calibração, será solicitado da próxima vez que iniciar sessão. 

    1. Primeiro, vai ajustar a sua viseira.
    
        ![Tela de seleção de calibração](images/06-et-corners.png)

    2. Para calibrar, você vai olhar para um conjunto de alvos (referidos como pedras preciosas). Tudo bem se piscar ou fechar os olhos durante a calibração, mas tente não olhar para outros objetos na sala ou no espaço físico. HoloLens usa este processo para aprender sobre a sua posição ocular para que possa tornar melhor o seu mundo holográfico. 

        ![Ajuste-se para os seus olhos](images/07-adjust-eyes.png)

        Após a calibração, os hologramas aparecerão corretamente, mesmo quando a viseira se desloca na sua cabeça. As informações de calibração são armazenadas localmente no dispositivo e não estão associadas a nenhuma informação da conta. Para obter mais informações, consulte [os dados de calibração e segurança.](hololens-calibration.md#calibration-data-and-security)

        ![A calibração está completa](images/calibration-complete.png)

1. Ligue-se à internet (selecione Wi-Fi ou a sua ligação ethernet).

     O HoloLens define o seu fuso horário automaticamente com base em informações obtidas a partir da rede Wi-Fi. Após o acabamento da configuração, pode alterar o fuso horário utilizando a aplicação Definições.

    ![Ligar a uma rede Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Se progredir para além do passo Wi-Fi e mais tarde precisar de mudar para uma rede diferente enquanto ainda estiver configurado, pode premir simultaneamente os botões **Volume Down** e **Power** para voltar a este passo se estiver a executar uma versão SO a partir de outubro de 2019 ou mais tarde. Para versões anteriores, poderá ser necessário [reiniciar o dispositivo](hololens-recovery.md) ou reiniciá-lo num local onde a rede Wi-Fi não esteja disponível para evitar a sua ligação automática.
    > 
    > Note também que durante a configuração hololes, há uma pausa de credencial de dois minutos. O nome de utilizador/palavra-passe tem de ser introduzido dentro de dois minutos, caso contrário o campo do nome de utilizador será automaticamente limpo.

1. HoloLens 2 procurará e aplicará um perfil autopiloto se existir. Não é necessária nenhuma ação neste ecrã.
 
    ![Pesquisa de perfil de piloto automático](images/autopilot-profile-search.png) 

1. Clique em **Aceitar** no ecrã de licenciamento.

    ![Contrato de licença do Windows](images/windows-license-agreement.png)

1. Inscreva-se na sua conta de utilizador. Vais escolher entre **o meu trabalho ou a minha escola** e eu sou o **dono.**

    - Quando escolher **O meu trabalho ou escola é dono dele,** inscreva-se com uma conta AZure AD. Se a sua organização utilizar o Azure AD Premium e tiver configurado a inscrição automática de MDM, a HoloLens matricula-se automaticamente no MDM. Se a sua organização não utilizar o Azure AD Premium, a inscrição automática de MDM não está disponível. Nesse caso, é necessário [inscrever manualmente holoLens na gestão do dispositivo.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Insira as informações da sua conta organizacional.
        1. Aceite a declaração de privacidade e o contrato de licença do utilizador final.
        1. Inscreva-se utilizando as suas credenciais Azure AD. Isto pode redirecionar para a página de início de sção da sua organização.
        1. Continue a configurar o dispositivo.

    - Quando **escolheres o dono,** inscreves-te com uma conta Microsoft. Após a configuração estar concluída, pode [inscrever os HoloLens manualmente na gestão do dispositivo.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Introduza as informações da sua conta microsoft.
        2. Introduza a palavra-passe. Se a sua conta Microsoft necessitar [de verificação em duas etapas (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)complete o processo de verificação.

    ![Definir utilizador](images/13-device-owner.png)

1. Configurar o sinal de iris selecionando em **seguida**. Você vai passar por uma experiência semelhante à calibração dos olhos. Selecione **Feito** quando a varredura estiver completa. Também pode selecionar **Skip** para contornar este passo.
    
    ![Conclusão da ](images/setup-iris.png) ![ configuração da Íris Iris](images/iris-setup-complete.png) 
     
  
1. Irá configurar um PIN para iniciar sessão no dispositivo. Este PIN é específico do dispositivo. 

    ![Configuração Windows Olá](images/setup-windows-hello.png)

    ![Configuração Windows Hello PIN](images/windows-hello-pin.png)

    ![Windows Hello Setup bem sucedido](images/windows-hello-successful.png) 
    
1. Selecione se ativar a fala no HoloLens 2.

    ![Ativar cortana](images/22-do-more-with-voice.png)

1. Selecione se ativa a localização no HoloLens 2.
    
    ![Ativar serviços de localização](images/setup-location-services.png)

1. Selecione o seu nível de telemetria. Se puder, por favor, ative a telemetria opcional. Esta informação realmente ajuda a equipa de engenharia hololens.

     ![Nível de telemetria](images/24-telemetry.png)

1. Aprenda a usar o gesto inicial no HoloLens 2.

     ![Aprenda a usar o gesto inicial, imagem 1](images/26-01-startmenu-learning.png)

     ![Aprenda a usar o gesto inicial, imagem 2](images/26-02-startmenu-learning.png)

Parabéns!  A configuração está completa e está pronto para usar HoloLens!

## <a name="next-steps"></a>Passos seguintes

1. Comece a interagir imediatamente com a Realidade Mista e navegue no Windows 10 nos seus HoloLens - consulte a aplicação **Tips** para tutoriais práticos para interações com as mãos. Use o gesto inicial para ir para Iniciar ou dizer "Vá para começar" e selecione Dicas.

1. Clique abaixo para continuar a ler sobre como contornar HoloLens 2.

> [!div class="nextstepaction"]
> [Introdução ao HoloLens 2](hololens2-basic-usage.md)
