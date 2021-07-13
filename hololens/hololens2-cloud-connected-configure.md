---
title: Guia de implementação - Implementação HoloLens 2 ligada à nuvem em escala com Assistência Remota - Configuração
description: Saiba como configurar configurações para inscrever HoloLens dispositivos sobre uma rede Cloud Connected em escala com Remote Assist.
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635148"
---
# <a name="configure---cloud-connected-guide"></a>Configuração - Guia ligado à nuvem

Nesta secção do guia,&#39;vamos analisar como configurar a Inscrição Automática para o seu inquilino, e como aplicar licenças tanto para o Intune como para a Assistência Remota.

## <a name="azure-users-and-groups"></a>Utilizadores e Grupos Azure

Azure, e Intune por essa extensão, usa utilizadores e grupos para ajudar a atribuir configurações e licenças. Para validar este fluxo de implementação e ser capaz de fazer uma chamada de Assistência Remota de um utilizador para outro,&#39;vai precisar de duas contas de utilizador.

Podemos fazer um único grupo de utilizadores com o propósito de atribuir licenças. Podemos juntar ambos os utilizadores ao mesmo grupo e aplicar uma licença para Intune e Remote Assist a esse grupo.

Se não&#39;já não tem acesso a duas contas AD Azure num grupo de utilizadores que pode utilizar; aqui estão os guias de arranque rápido para:

- [Como criar um utilizador](/mem/intune/fundamentals/quickstart-create-user)
- [Como criar um grupo](/mem/intune/fundamentals/quickstart-create-group)
- [Adicionar utilizadores a um grupo](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Adicionar utilizadores criados para criar grupo
- [Configure Ad AD para permitir que um Grupo de Utilizadores se junte a dispositivos](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Certifique-se de que o novo grupo de utilizadores tem permissão para inscrever dispositivos no Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Inscrição automática no HoloLens 2

Para ter uma experiência suave e sem emenda, a criação de Azure Ative Directory Join (AADJ) e a Inscrição Automática para a Intune para HoloLens 2 dispositivos é o caminho a seguir. Isto permitirá que os utilizadores insiram as suas credenciais de login da organização durante o OOBE e se registem automaticamente com a Azure AD e inscrevam o dispositivo no MDM.

Ao utilizar [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/#home)podemos selecionar serviços e navegar algumas páginas até podermos selecionar Obter um Premium teste. Pode notar que há Azure Ative Directory Premium 1 e 2, pois a Inscrição Automática P1 é suficiente. Podemos selecionar Intune e selecionar o âmbito do utilizador para a inscrição automática e selecionar o grupo que foi previamente criado.

Para mais detalhes e passos, leia o guia sobre [como permitir a inscrição automática para o Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Licenças de Inscrição

Uma licença de aplicação permite a um utilizador instalar apps adquiridas pela empresa ou atualizar de um teste gratuito para a versão completa de uma aplicação. As licenças de aplicação podem ser aplicadas a utilizadores, grupos de utilizadores ou grupos de dispositivos. &#39;vai precisar de licenças de Assistência Remota para os utilizadores da sua organização utilizarem o Remote Assist. Para efeitos deste guia, atribuiremos licenças de Assistência Remota ao grupo de utilizadores que criámos acima em [Utilizadores e Grupos Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Os requisitos para licenças podem ser diferentes dependendo se o utilizador irá fazer a chamada de Assistência Remota a partir de um dispositivo ou será um colaborador remoto de Microsoft Teams. Por predefinição, as caixas de assistência remota e Teams estão marcadas. Para efeitos deste guia, sugerimos deixar as caixas predefinidas verificadas.

1. Saiba mais sobre os [diferentes requisitos de licenciamento e produto por função.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Existem alguns tipos diferentes de licenças de Assistência Remota, por isso certifique-se de obter as corretas para as suas necessidades.
2. Terá&#39;de adquirir a [licença.](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Aplique as suas licenças](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) no grupo.

## <a name="next-step"></a>Passo seguinte

> [!div class="nextstepaction"]
> [Implementação ligada à nuvem - Implementar](hololens2-cloud-connected-deploy.md)