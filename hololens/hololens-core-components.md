---
title: Planeamento holoLens 2 implantação em ambiente comercial
description: Conheça as principais necessidades de implantação e gestão de HoloLens em ambientes empresariais, incluindo infraestruturas, diretório ativo azul e gestão de dispositivos móveis.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961481"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Planeamento holoLens 2 implantação em ambiente comercial

## <a name="overview"></a>Descrição Geral
> [!NOTE]
> Esta visão geral destina-se a ajudar os profissionais de TI a compreender considerações para implementar e gerir dispositivos Microsoft HoloLens 2 dentro de uma organização. Para os utilizadores finais do dispositivo, consulte [o Basics](hololens2-setup.md) para começar.

O HoloLens 2 funciona no Windows 10 Holographic que fornece às organizações tecnologias robustas, flexíveis, incorporadas para dispositivos móveis e gestão de aplicações. O Windows 10 Holographic suporta a gestão do ciclo de vida do dispositivo de ponta a ponta para dar às empresas o controlo sobre os seus dispositivos, dados e apps. O HoloLens 2 pode ser facilmente incorporado em práticas padrão de ciclo de vida, desde a inscrição, configuração e gestão de aplicações do dispositivo até à manutenção e reforma usando uma solução abrangente de gestão de dispositivos móveis.

Os seguintes passos podem ajudá-lo a guiá-lo através do processo de adoção hololes 2 dentro da sua organização.

| | |
|--|--|
| ![Passo 1](images/1green.png)| <br/> **[Cenários de implantação comuns](hololens-requirements.md)**: Compreenda os cenários de implantação e explore os componentes centrais necessários para implantar dispositivos HoloLens 2. |
| ![Passo 2](images/2green.png)| <br/> **[Preparar](#prepare)**: Familiarize-se com os elementos essenciais da infraestrutura necessários para hololens 2. |
| ![Passo 3](images/3green.png) | <br/> **[Configurar](#configure)**: Aprenda a configurar os seus componentes essenciais para uma implantação baseada na nuvem. |
| ![Passo 4](images/4green.png) | <br/> **[Implementar](#deploy)**: Descubra como implantar os seus dispositivos e distribuir as suas aplicações de forma segura e eficiente. |
| ![Passo 5](images/5green.png) | <br/> **[Manter](#maintain)**: Descubra o que é necessário para manter corretamente o estado dos seus dispositivos HoloLens 2 e garantir o cumprimento da política corporativa. |

## <a name="prepare"></a>Preparação

Conheça os serviços essenciais de infraestrutura necessários para suportar todo o conjunto de capacidades HoloLens 2. 

| Componente | Descrição |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Fornece gestão de identidade e acesso para os HoloLens 2  |
| [Mobile Device Management](hololens-mdm-configure.md)| Gere os dispositivos HoloLens 2 ligados ao seu inquilino  |
| [Rede Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi está disponível e os dispositivos podem ser ligados à Internet  |

## <a name="configure"></a>Configurar

Utilize o Intune e o Autopilot como soluções de baixo toque para inscrever e configurar holoLens 2 para o inquilino AZure AD da sua organização e MDM.

| Componente | Descrição |
|-----------|------------|
| [Inscrição automática](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Após o início de sessão, os dispositivos registam-se automaticamente com a Azure AD e inscrevem-se no MDM  |
| [Licenças de Inscrição](hololens2-cloud-connected-configure.md#application-licenses)| Pode ser aplicado a utilizadores, grupos de utilizadores ou grupos de dispositivos  |
| [Utilizadores e Grupos Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Ajuda a atribuir configurações e licenças para os HoloLens 2  |

## <a name="deploy"></a>Implementar

Distribua os seus dispositivos HoloLens 2 e valide a sua configuração. 

| Componente | Descrição |
|-----------|------------|
| [Validação de Inscrição](hololens2-corp-connected-deploy.md#enrollment-validation) | Validar o dispositivo tem AZure AD Unidos a partir de Definições ou do Portal Azure |
| [Validação de Certificados](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Verifique as definições e valide-as foram distribuídas corretamente |
| [Validar instalações de aplicações](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Confirme que a aplicação está presente e que está a trabalhar no seu HoloLens 2 |

## <a name="maintain"></a>Manter

Utilize o Windows Update for Business juntamente com o seu sistema MDM ou a Microsoft Store para manter a sua frota de HoloLens 2 e aplicações atualizadas.

| Componente | Descrição |
|-----------|------------|
| [Atualizar HoloLens 2](hololens-updates.md) | Configurar atualizações conforme necessário através de Atualizações do Windows para Negócios |
| [Atualizar aplicações](app-deploy-overview.md) | Configure através do seu sistema MDM ou da Microsoft Store
