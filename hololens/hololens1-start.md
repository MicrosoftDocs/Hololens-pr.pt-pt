---
title: Configurar HoloLens (1º género)
description: Saiba como configurar o seu HoloLens (1º género) pela primeira vez em Wi-Fi rede com uma conta Microsoft (MSA) ou Azure Ative Directory (AAD).
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
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378549"
---
# <a name="set-up-your-hololens-1st-gen"></a>Configurar os seus HoloLens (1º género)

A primeira vez que ligar os HoloLens, será guiado através da calibração do seu dispositivo, da configuração do seu dispositivo e da sua inscrição.  Este artigo percorre a experiência de início e configuração do HoloLens (1ª gen).

Na próxima secção, aprenderás a trabalhar com hololens e a interagir com hologramas. Para antecipar este artigo, consulte [Começar com HoloLens (1ª geração)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Antes de começar

Antes de começar, certifique-se de ter o seguinte disponível:

**Uma ligação Wi-Fi.** Terá de ligar os HoloLens a uma rede Wi-Fi para o configurar. A primeira vez que se conectar, precisará de uma rede aberta ou protegida por palavra-passe que não exija navegar para um website ou usar certificados para se conectar. [Saiba mais sobre os websites que o HoloLens utiliza.](hololens-offline.md)

**Uma conta Microsoft ou uma conta de trabalho.** Também terá de utilizar uma conta Microsoft (ou uma conta de trabalho, se a sua organização é proprietária do dispositivo) para iniciar scontabilidade no HoloLens. Se não tiver uma conta Microsoft, vá a [account.microsoft.com](https://account.microsoft.com) e crie uma de graça.

**Um espaço seguro e bem iluminado sem perigos de tropeçar.** [Informações de saúde e segurança.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Os acessórios de conforto opcionais** que vieram com os seus HoloLens, para ajudá-lo a obter o ajuste mais confortável. [Mais sobre o ajuste e o conforto.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - A primeira vez que usa os hololes, [cortana](hololens-cortana.md) já está pronta para guiá-lo (embora ela não possa responder às suas perguntas até depois de configurar o seu dispositivo). Pode desligar cortana a qualquer momento nas definições de Cortana.
> - Para mudar para a versão chinesa ou japonesa dos HoloLens, terá de descarregar a construção para o idioma num PC e depois instalá-la nos seus HoloLens. Para obter mais informações, consulte [instalar versões localizadas de HoloLens (1ª geração)](hololens1-install-localized.md).

## <a name="start-your-hololens-and-set-up-windows"></a>Inicie os hololens e instale o Windows

A primeira vez que inicia os HoloLens, a sua primeira tarefa é configurar o Windows Holographic no seu dispositivo.

1. Ligue-se à internet (HoloLens guia-o para selecionar Wi-Fi rede).

1. Inscreva-se na sua conta de utilizador. Escolha entre **o meu trabalho ou a minha escola é o dono** e eu sou o **dono.**
    - Quando escolher **O meu trabalho ou escola é o dono, inscreva-se** utilizando uma conta AZure AD. Se a sua organização utilizar o Azure AD Premium e tiver configurado a inscrição automática de MDM, a HoloLens matricula-se automaticamente no MDM. Se a sua organização não utilizar o Azure AD Premium, a inscrição automática de MDM não está disponível, pelo que terá de [inscrever manualmente holoLens na gestão de dispositivos.](hololens-enroll-mdm.md#different-ways-to-enroll) Para iniciar sôms no seu dispositivo pela primeira vez utilizando uma conta de trabalho ou escola, siga estes passos:
        1. Insira as informações da sua conta organizacional.
        1. Aceite a declaração de privacidade.
        1. Inscreva-se utilizando as suas credenciais Azure AD. Isto pode redirecionar para a página de início de sção da sua organização.
        1. Continue a configurar o dispositivo.
    - Quando **escolheres eu, inscreves-te** utilizando uma conta Microsoft. Após a configuração estar concluída, pode [inscrever os HoloLens manualmente na gestão do dispositivo.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Introduza as informações da sua conta microsoft.
        1. Introduza a palavra-passe. Se a sua conta Microsoft necessitar [de verificação em duas etapas (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)complete o processo de verificação.

1. O dispositivo define o seu fuso horário com base nas informações que obtém da rede Wi-Fi.

## <a name="calibration"></a>Calibração

Depois de Cortana se apresentar, o próximo passo de configuração é a calibração. Para obter a melhor experiência hololens, deverá completar o processo de calibração durante a configuração.

HoloLens (1º gêger) usa a distância entre as suas pupilas (IPD ou [distância interpupilífera](https://en.wikipedia.org/wiki/Interpupillary_distance)) para tornar os hologramas claros e fáceis de interagir. Se o IPD não estiver correto, os hologramas podem parecer instáveis ou a uma distância incorreta.

Durante a calibração, holoLens pede-lhe para alinhar o dedo com uma série de seis alvos por olho. HoloLens usa este processo para definir o IPD correto para os seus olhos. Se a calibração precisar de ser atualizada ou ajustada para um novo utilizador, o novo utilizador pode executar a aplicação calibração fora da configuração.

![Tela de alinhamento de dedos IPD no segundo passo](./images/ipd-finger-alignment-300px.jpg)

*Tela de alinhamento de dedos IPD no segundo passo*

Parabéns! A configuração está completa e pode começar a usar HoloLens.

## <a name="next-steps"></a>Passos seguintes

> [!div class="nextstepaction"]
> [Começa com holoLens (1ª geração)](hololens1-basic-usage.md)
