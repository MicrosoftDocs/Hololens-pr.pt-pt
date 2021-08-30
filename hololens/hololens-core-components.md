---
title: Planeamento HoloLens 2 implantação em ambiente comercial
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
ms.openlocfilehash: 8605d1a889fb9facdab0e9585a43a61880155952
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188904"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Planeamento HoloLens 2 implantação em ambiente comercial

## <a name="overview"></a>Descrição Geral

> [!NOTE]
> Esta visão geral destina-se a ajudar os profissionais de TI a compreender considerações para implementar e gerir Microsoft HoloLens 2 dispositivos dentro de uma organização. Para os utilizadores finais do dispositivo, consulte [obter o seu HoloLens 2 pronto a usar para](hololens2-setup.md) começar.

HoloLens 2 funciona em Windows 10 Holographic que fornece às organizações tecnologias robustas, flexíveis, incorporadas para dispositivos móveis e gestão de aplicações. Windows 10 Holographic suporta a gestão do ciclo de vida do dispositivo de ponta a ponta para dar às empresas o controlo sobre os seus dispositivos, dados e apps. O HoloLens 2 pode ser facilmente incorporado em práticas padrão de ciclo de vida, desde a inscrição, configuração e gestão de aplicações do dispositivo até à manutenção e reforma utilizando uma solução abrangente de gestão de dispositivos móveis.

Os seguintes passos e vídeo podem ajudá-lo a guiá-lo através do processo de adoção de HoloLens 2 dentro da sua organização.

| &nbsp; | &nbsp; |
|--|--|
| ![Passo 1.](images/1green.png)| <br/> **[Cenários de implantação comuns](hololens-requirements.md)**: Compreenda os cenários de implantação e explore os componentes centrais necessários para implantar HoloLens 2 dispositivos. |
| ![Passo 2.](images/2green.png)| <br/> **[Preparar](#prepare)**: Familiarize-se com os elementos essenciais da infraestrutura necessários para HoloLens 2. |
| ![Passo 3.](images/3green.png) | <br/> **[Configurar](#configure)**: Aprenda a configurar os seus componentes essenciais para uma implantação baseada na nuvem. |
| ![Passo 4:](images/4green.png) | <br/> **[Implementar](#deploy)**: Descubra como implantar os seus dispositivos e distribuir as suas aplicações de forma segura e eficiente. |
| ![Passo 5.](images/5green.png) | <br/> **[Manter](#maintain)**: Descubra o que é necessário para manter corretamente o estado dos seus HoloLens 2 dispositivos e garantir o cumprimento da política corporativa. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Preparação

Conheça os serviços essenciais de infraestrutura necessários para suportar todo o conjunto de capacidades HoloLens 2.

| Componente | Descrição |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Fornece gestão de identidade e acesso para o HoloLens 2  |
| [Mobile Device Management](hololens-mdm-configure.md)| Gere HoloLens 2 dispositivos ligados ao seu inquilino  |
| [Rede Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi está disponível e os dispositivos podem ser ligados à Internet  |

## <a name="configure"></a>Configurar

Utilize o Intune e o Autopilot como soluções de baixo toque para inscrever e configurar HoloLens 2 para o inquilino AZure AD da sua organização e MDM.

| Componente | Descrição |
|-----------|------------|
| [Inscrição automática](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Após o início de sessão, os dispositivos registam-se automaticamente com a Azure AD e inscrevem-se no MDM  |
| [Licenças de Inscrição](hololens2-cloud-connected-configure.md#application-licenses)| Pode ser aplicado a utilizadores, grupos de utilizadores ou grupos de dispositivos  |
| [Utilizadores e Grupos Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Ajuda a atribuir configurações e licenças para o HoloLens 2  |

## <a name="deploy"></a>Implementar

Distribua os seus HoloLens 2 dispositivos e valide a sua configuração. 

| Componente | Descrição |
|-----------|------------|
| [Validação de Inscrição](hololens2-corp-connected-deploy.md#enrollment-validation) | Validar o dispositivo tem AZure AD Unidos a partir de Definições ou do Portal Azure |
| [Validação de Certificados](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Verifique as definições e valide-as foram distribuídas corretamente |
| [Validar instalações de aplicações](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Confirme que a aplicação está presente e que está a trabalhar no seu HoloLens 2 |

## <a name="maintain"></a>Manter

Utilize Windows Update for Business juntamente com o seu sistema MDM ou o Microsoft Store para manter a sua frota de HoloLens 2 e aplicações atualizadas.

| Componente | Descrição |
|-----------|------------|
| [Atualização HoloLens 2](hololens-updates.md) | Configurar atualizações conforme necessário através de Windows Atualizações para Negócios |
| [Atualizar aplicações](app-deploy-overview.md) | Configure através do seu sistema MDM ou do Microsoft Store
