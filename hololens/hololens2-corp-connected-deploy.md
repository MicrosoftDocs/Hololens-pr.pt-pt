---
title: Guia de Implementação - HoloLens conectados corporativos 2 com dinâmica 365 guias - Implementar
description: Saiba como configurar implementações de dispositivos HoloLens 2 sobre uma rede conectada corporativa com Guias Dinâmicos 365.
keywords: HoloLens, gestão, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Device Management
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378543"
---
# <a name="deploy---corporate-connected-guide"></a>Implementar - Guia Conectado Corporativo

Uma parte importante de cada implementação é garantir que a sua implementação está corretamente configurada antes de testá-la por si mesmo para garantir uma experiência suave para o utilizador final.

Como estamos a implementar o certificado de Wi-Fi via MDM, teremos de configurar inicialmente holoLens e inscrever dispositivos numa rede de Wi-Fi aberta, ou numa rede que não exija o certificado. Uma vez que os HoloLens terminaram o OOBE e o Inscrito, o dispositivo receberá o certificado de rede e LOB configurado anteriormente e poderemos validar ambos foram recebidos pelo dispositivo.

Em seguida, poderá confirmar que pode ser autor e operar um Guia de Teste.

## <a name="enrollment-validation"></a>Validação de Inscrição

Agora que tudo está devidamente configurado para a Azure AD e a Inscrição do MDM, o resto deve agora ser um estalo. Você precisará de uma ligação Wi-Fi e o dispositivo HoloLens, e uma das contas de utilizadores AD Azure previamente configuradas.

Se o seu dispositivo não estiver neste momento sentado num estado de definição de fábrica, agora seria uma boa altura para voltar a [desatar o dispositivo](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).

1. Uma vez que o seu dispositivo esteja no OOBE, terá de começar a interagir e a seguir as indicações.

2. Ligue-se a uma rede de Wi-Fi aberta que não requer certificados para aderir ao Wi-Fi. Isto permitirá que o dispositivo descarregue o certificado a utilizar no Wi-Fi da organização após a configuração inicial.

3. A origem crítica será quando lhe perguntarem **quem é o dono deste HoloLens?** Selecione O meu trabalho ou escola é o dono e **insira** as suas credenciais de conta AZure AD.

4. Quando a inscrição for bem sucedida, será solicitado a configurar um PIN. Este PIN é exclusivo deste dispositivo para este utilizador. Também será solicitado para digitalizações de Íris, dados de voz e definições de telemetria e, finalmente, poderá aprender a abrir o menu inicial e completar o OOBE.

5. Assim que aterrar no Mixed Reality Home, abra o menu Iniciar usando o **gesto Iniciar** que acabou de aprender.

6. Selecione a aplicação **Definições** e selecione **Sistema.** A primeira informação que verá é o nome do dispositivo, que para o seu dispositivo HoloLens 2 será &quot; HOLOLENS, &quot; seguido de uma cadeia de seis caracteres.

7. Tome nota deste nome.

    ![Ecrã HoloLens 2 Definições](./images/hololens2-settings-about.jpg)

8. Verifique se o seu dispositivo está aderido com sucesso ao Azure AD. Há duas maneiras;

    1.  A aplicação Definições. A partir **de Definições** selecionam   ->  **Contas Acesso trabalho ou escola**. A partir deste ecrã, pode verificar que está matriculado com sucesso ao ver &quot; Connected to nameofAAD&#39;s Azure AD. Ligado por *yourusername@nameofAAD.onmicrosoft.com* . Isto verificará se o seu dispositivo se juntou à sua organização&#39;Azure AD.

    1. O [portal Azure.](https://portal.azure.com/#home) Aceda a Dispositivos **de Diretório Ativo Azure**  ->    ->  **Todos os dispositivos** e procure o nome do dispositivo. No Tipo DeDerro, será apresentado como sendo 'Azure AD Joined'.
        ![Verifique o tipo de junção em Azure AD](./images/hololens2-devices-all-devices.png)

9. Verifique se o seu dispositivo está matriculado com MDM. Há duas maneiras;

    1. A partir **de Definições**, selecione **Contas**  ->  **Access trabalho ou escola**. A partir deste ecrã, pode verificar que está matriculado com sucesso ao ver &quot; Connected to nameofAAD&#39;s Azure AD. Ligado por *yourusername@nameofAAD.onmicrosoft.com* . A partir deste trabalho de Acesso ou conta escolar selecionando &quot; Connected to nameofAAD&#39;s Azure AD. Ligado yourusername@nameofAAD.onmicrosoft.com &quot; e selecione o botão **Informação.**

    1. [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home). Faça login e selecione  **Dispositivos**  e, em seguida,  **Todos os dispositivos**. A partir daqui, pode pesquisar o seu dispositivo HoloLens&#39;nome. Deves poder ver os teus HoloLens listados no Intune.

        ![Verifique gerido pela Intune em Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>validação do certificado Wi-Fi

Por esta altura, o dispositivo já devia ter recebido o certificado de Wi-Fi. A validação mais simples que pode fazer é tentar ligar-se à ligação Wi-Fi para a qual&#39;recebeu o certificado. Abra a aplicação **Definições** e navegue para o Wi-Fi **da &amp; Internet da Rede** e  ->   selecione a ligação Wi-fi. Uma vez conectado, abra a aplicação Microsoft Edge e confirme que pode navegar para um website.

Para confirmar que recebeu o certificado no dispositivo, pode utilizar o [Gestor de Certificados.](https://docs.microsoft.com/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>Validar a instalação de aplicativo LOB

Para ver o progresso da instalação de uma aplicação gerida, ou vê se a aplicação está instalada ou verifica Definições. Ao configurar uma aplicação LOB como uma instalação necessária para o nosso grupo, depois de inscrever os HoloLens com um utilizador no grupo designado, a aplicação será automaticamente transferida para os HoloLens.

Abra o menu Iniciar e selecione **Todas as aplicações**. Dependendo do número de aplicações que tem, poderá ter de utilizar os botões **de página para cima** ou para **baixo.**

Para validar a instalação da aplicação no dispositivo, pode fazê-lo através de **Definições**  ->  **Contas**  ->  **Aceder ao trabalho ou escola**; selecione a conta em seguida o botão **Info,** e desloque-se para baixo para ver diferentes configurações e aplicações aplicadas ao dispositivo a partir de MDM.

Para validar a instalação do Intune, navegue para o [portal MEM](https://endpoint.microsoft.com/#home)  ->  **Apps** -> Todas as **aplicações**  -> *TheNameOfYourApp* Device instalar a página de  ->  **estado.**

Ver mais: [Implementação de aplicativos Intune para HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Validar Dinâmica 365 Guias

Existem modos para a aplicação Guides em HoloLens, autoria e funcionamento. Terá de terminar a autoria de um guia antes de o operar.

### <a name="authoring-the-guide"></a>Autoria do Guia

Não precisamos de fazer muito por esta validação rápida. Basta selecionar o guia que preparou no seu PC. Você precisará [ancorar o guia,](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)para uma validação rápida você pode usar uma âncora holográfica. Depois, deve [colocar os seus passos e modelos.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> Você precisará do papel **de Autoring** para iniciar sessão no PC e autor nos HoloLens. A função do Operador é apenas de leitura e não tem acesso à aplicação para PC.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Funcionamento do Guia

Uma vez que os hologramas estejam no lugar, pode testar o funcionamento do seu guia. 
- Selecione **o modo de operador**
- Clique nos passos do seu guia.

Para obter uma orientação mais aprofundada sobre como operar um guia, confira estes recursos:

[Visão geral da exploração de um guia em Dinâmica 365 Guias](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Oriente-se com o cartão Step como operador em Guias Dinâmicos 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Passo seguinte 
> [!div class="nextstepaction"]
> [Implementação conectada corporativa - Manter](hololens2-corp-connected-maintain.md)
