---
title: Configurar HoloLens (1ª geração)
description: Aprenda a configurar o seu HoloLens (1º género) pela primeira vez em Wi-Fi rede com uma conta Microsoft (MSA) ou Azure Ative Directory (AAD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428562"
---
# <a name="set-up-your-hololens-1st-gen"></a>Configurar o seu HoloLens (1ª geração)

A primeira vez que ligar o seu HoloLens, será guiado através da calibração do seu dispositivo, da configuração do seu dispositivo e da sua inscrição.  Este artigo percorre a experiência de início e configuração da HoloLens (1ª geração).

Na próxima secção, aprenderás a trabalhar com HoloLens e a interagir com hologramas. Para antecipar este artigo, consulte [Começar com HoloLens (1ª geração)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Antes de começar

Antes de começar, certifique-se de ter o seguinte disponível:

**Uma ligação Wi-Fi.** Terá de ligar o seu HoloLens a uma rede Wi-Fi para o configurar. A primeira vez que se conectar, precisará de uma rede aberta ou protegida por palavra-passe que não exija navegar para um website ou usar certificados para se conectar. [Saiba mais sobre os websites que HoloLens utiliza.](hololens-offline.md)

**Uma conta Microsoft ou uma conta de trabalho.** Também terá de utilizar uma conta Microsoft (ou uma conta de trabalho, se a sua organização é proprietária do dispositivo) para iniciar scontabilidade para HoloLens. Se não tiver uma conta Microsoft, vá a [account.microsoft.com](https://account.microsoft.com) e crie uma de graça.

**Um espaço seguro e bem iluminado sem perigos de tropeçar.** [Informações de saúde e segurança.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Os acessórios de conforto opcionais** que acompanham o seu HoloLens, para ajudá-lo a obter o ajuste mais confortável. [Mais sobre o ajuste e o conforto.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - A primeira vez que usa o seu HoloLens, [Cortana](hololens-cortana.md) já está ligado e pronto para guiá-lo (embora ela não possa responder às suas perguntas até depois de configurar o seu dispositivo). Pode desligá Cortana a qualquer momento nas definições de Cortana.
> - Para mudar para a versão chinesa ou japonesa de HoloLens, terá de descarregar a construção para o idioma num PC e depois instalá-la no seu HoloLens. Para obter mais informações, consulte [instalar versões localizadas de HoloLens (1ª geração)](hololens1-install-localized.md).

## <a name="start-your-hololens-and-set-up-windows"></a>Iniciem os hololens e criem Windows

A primeira vez que iniciar o seu HoloLens, a sua primeira tarefa é configurar Windows Holographic no seu dispositivo.

1. Ligação à internet (HoloLens o guia para selecionar Wi-Fi rede).

1. Inscreva-se na sua conta de utilizador. Escolha entre **o meu trabalho ou a minha escola é o dono** e eu sou o **dono.**
    - Quando escolher **O meu trabalho ou escola é o dono, inscreva-se** utilizando uma conta AZure AD. Se a sua organização utilizar Azure AD Premium e tiver configurado a inscrição automática de MDM, HoloLens matricula-se automaticamente no MDM. Se a sua organização não utilizar Azure AD Premium, a inscrição automática de MDM não está disponível, pelo que terá de [inscrever manualmente HoloLens na gestão do dispositivo.](hololens-enroll-mdm.md#different-ways-to-enroll) Para iniciar sôms no seu dispositivo pela primeira vez utilizando uma conta de trabalho ou escola, siga estes passos:
        1. Insira as informações da sua conta organizacional.
        1. Aceite a declaração de privacidade.
        1. Inscreva-se utilizando as suas credenciais Azure AD. Isto pode redirecionar para a página de início de sção da sua organização.
        1. Continue a configurar o dispositivo.
    - Quando **escolheres eu, inscreves-te** utilizando uma conta Microsoft. Após a conclusão da configuração, pode [inscrever-se manualmente HoloLens na gestão do dispositivo](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Introduza as informações da sua conta microsoft.
        1. Introduza a palavra-passe. Se a sua conta Microsoft necessitar [de verificação em duas etapas (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)complete o processo de verificação.

1. O dispositivo define o seu fuso horário com base nas informações que obtém da rede Wi-Fi.

## <a name="calibration"></a>Calibração

Depois de Cortana se apresentar, o próximo passo de configuração é a calibração. Para obter a melhor experiência HoloLens, deverá concluir o processo de calibração durante a configuração.

HoloLens (1º gênero) usa a distância entre as suas pupilas (DISTÂNCIA IPD ou [distância interpupilar)](https://en.wikipedia.org/wiki/Interpupillary_distance)para tornar os hologramas claros e fáceis de interagir. Se o IPD não estiver correto, os hologramas podem parecer instáveis ou a uma distância incorreta.

Durante a calibração, HoloLens pede-lhe para alinhar o dedo com uma série de seis alvos por olho. HoloLens utiliza este processo para definir o IPD correto para os seus olhos. Se a calibração precisar de ser atualizada ou ajustada para um novo utilizador, o novo utilizador pode executar a aplicação calibração fora da configuração.

![Ecrã de alinhamento de dedos IPD no segundo passo.](./images/ipd-finger-alignment-300px.jpg)

*Tela de alinhamento de dedos IPD no segundo passo*

Parabéns! A configuração está completa e pode começar a utilizar HoloLens.

## <a name="next-steps"></a>Passos seguintes

> [!div class="nextstepaction"]
> [Começar com HoloLens (1ª geração)](hololens1-basic-usage.md)
