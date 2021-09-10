---
title: Guia de implementação - Implementação HoloLens 2 ligada à nuvem em escala com assistência remota - Implementar
description: Saiba como validar a inscrição e o Remote Assist para HoloLens dispositivos numa rede Cloud Connected.
keywords: HoloLens, gestão, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Device Management
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 519770badab9f260316fe4cfff4bf453a7c971a7
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428752"
---
# <a name="deploy---cloud-connected-guide"></a>Implementar - Guia ligado à nuvem

Agora que tem tudo configurado, deve estar pronto para distribuir dispositivos. No entanto, agora é quando deve validar a sua configuração pela primeira vez. Em primeiro lugar, o processo de inscrição Azure AD e MDM deve ser validado, seguindo-se a verificação de que uma chamada de Assistência Remota pode ser colocada.

## <a name="enrollment-validation"></a>Validação de Inscrição

Agora que tudo está devidamente configurado para a Azure AD e a Inscrição do MDM, o resto deve agora ser um estalo. &#39;necessitará de uma ligação Wi-Fi e do dispositivo HoloLens, bem como uma das contas de utilizador AAD previamente configuradas.

Se o seu dispositivo não estiver&#39;atualmente em estado de definição de fábrica, agora seria uma boa altura para [relançar o dispositivo](/hololens/hololens-recovery#clean-reflash-the-device).

1. Uma vez que o seu dispositivo esteja no OOBE,&#39;terá de começar a interagir e a seguir as indicações. 
1. A origem crítica será quando lhe perguntarem **Quem é dono deste HoloLens?** Selecione O meu trabalho ou escola é o dono e **insira** as suas credenciais de conta AZure AD.
1. Quando a inscrição for bem sucedida,&#39;será solicitado para configurar um PIN. Este PIN é exclusivo deste dispositivo para este utilizador. Também será solicitado para digitalizações de Íris, dados de voz e definições de telemetria e, finalmente,&#39;poderá aprender a abrir o menu inicial e completar o OOBE.
1. Assim que aterrares no Mixed Reality Home abre o menu Iniciar usando o **gesto Iniciar** que acabaste de aprender.
1. Selecione a aplicação **Definições** e selecione **Sistema.** A primeira informação que&#39;verá é o nome do dispositivo, que para o seu dispositivo HoloLens 2 será &quot; HOLOLENS, &quot; seguido de uma cadeia de seis caracteres.
1. Tome nota deste nome.

![HoloLens 2 Definições.](./images/hololens2-settings-about.jpg)

7. Pode verificar se o seu dispositivo está matriculado com sucesso no AD Azure dentro da aplicação Definições. A partir **de Definições** selecione **Contas** Acesso trabalho  ->  **ou escola.** A partir deste ecrã pode verificar que está matriculado com sucesso ao ver &quot; Connected to _nameofAAD_&#39;s Azure AD. Ligado pelo seu nome _de nome_ de nome de @ _ação (onmicrosoft.com)._ &quot;


Para validar o dispositivo tem Azure AD Unidos podemos verificar o Azure Ative Directory a partir do [portal Azure](https://portal.azure.com/#home)  ->  **Azure Ative Directory**  ->  **Dispositivos** Todos  ->  **os dispositivos**, e pesquisar o nome do dispositivo. &#39;poderá ver que o dispositivo faz parte do Azure Ative Directory.


![Azure Ative Directory.](./images/aad-enrollment.png)

Em seguida,&#39;terá de entrar no [centro de administração Microsoft Endpoint Manager.](https://endpoint.microsoft.com/#home) Faça login e selecione **Dispositivos** e, em seguida, **Todos os dispositivos**. A partir daqui pode pesquisar o seu HoloLens dispositivo&#39;nome. Deve poder ver o seu HoloLens listado no Intune.

![Intune - Dispositivo.](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Validação de chamada de assistência remota

Uma vez que&#39;verificado que o seu dispositivo está matriculado tanto no seu AAD como no MDM,&#39;tempo de esporar uma chamada de Assistência Remota de teste. Para esta validação&#39;terá de ter o dispositivo HoloLens e um PC Windows 10, bem como uma segunda conta de utilizador AD Azure para o PC.

Esta etapa de validação pressupõe que já completou o último passo de validação e que o seu dispositivo está matriculado e o seu utilizador AZure AD está no dispositivo.


1. Se ainda não tiver Microsoft Teams instalado no seu PC, pode [baixar Teams aqui.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Inscreva-se em Teams utilizando a segunda conta de utilizador Azure AD do que a que está atualmente assinada no seu HoloLens. Uma vez assinado no seu PC, estará pronto para receber a chamada.
3. Desbloqueie o HoloLens e inscreva-se.
4. Para lançar a aplicação Remote Assist abra o **Menu Iniciar** e selecione **Remote Assist**. O Remote Assist não é apenas agregado como uma aplicação de caixa de entrada, mas fixado no menu inicial de HoloLens 2&#39;. Num caso em que não&#39;vê-lo preso à menu Iniciar, depois abra a lista **de aplicações all** para o procurar.
5. Assim que o Remote Assist iniciar, deverá identificar o utilizador do dispositivo através [do SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) e entrar na aplicação.
6. A partir da aplicação, selecione **Procurar** e procurar o segundo utilizador no PC. Selecione o utilizador para iniciar a chamada.
7. Do seu pc, responda à chamada.

Parabéns,&#39;ligado com sucesso e está na sua chamada de assistência remota. Certifique-se de experimentar funcionalidades específicas de assistência remota, tais como a utilização:

- [Anotações de tinta](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Partilhe um arquivo e veja na realidade mista](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obtenha ajuda em outra aplicação HoloLens](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Passo seguinte

> [!div class="nextstepaction"]
> [Implementação ligada à nuvem - Manter](hololens2-cloud-connected-maintain.md)