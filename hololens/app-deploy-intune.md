---
title: Portal intune e da empresa
description: Aprenda a configurar, atribuir e criar uma experiência de utilizador confortável com a Intune, a gestão de dispositivos móveis e o portal da empresa.
keywords: intune, gestão de aplicativos, app, portal da empresa, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378631"
---
# <a name="intune--company-portal"></a>Portal da Empresa Intune &

Com a Mobile Device Management (MDM), pode utilizar as suas próprias aplicações personalizadas através [do Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para a implementar diretamente nos seus dispositivos HoloLens. O Microsoft Intune é um serviço baseado na nuvem que se foca na gestão de dispositivos móveis (MDM) e na gestão de aplicações móveis (MAM). O Intune está incluído na [suite Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)da Microsoft, e permite que os utilizadores sejam produtivos, mantendo os dados da sua organização protegidos. Para saber mais sobre Intune, leia [O Que é Intune.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Configuração

1. Faça upload de uma aplicação para uma Linha de Negócios ou faça upload de uma aplicação personalizada para o seu inquilino Intune. Ver também: [Gestão de aplicações da Enterprise](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Atribua a sua aplicação a um grupo.](https://docs.microsoft.com/mem/intune/apps/apps-deploy) Com base no tipo de atribuição que escolher, a aplicação pode ser entregue automaticamente ou disponível para ser prontamente puxada para baixo se tiver uma seleção de aplicações.

> [!NOTE]
> Ao construir o seu pacote appx, certifique-se de que inclui a arquitetura para os dispositivos para os dispositivos a que está a implementar. HoloLens 2 é ARM64, e HoloLens (1ª Gen) é x86. Pode incluir ambos num único pacote de aplicações se pretender ter um ambiente de dispositivos mistos.

## <a name="assignment-types"></a>Tipos de atribuição

Para que a sua aplicação seja automaticamente instalada no dispositivo após a inscrição, deverá selecionar **o Requerido** para esse grupo.
Para disponibilizar a sua aplicação para download para dispositivos matriculados através do portal da empresa, selecione **Disponível para dispositivos inscritos.**

## <a name="end-user-experience"></a>experiência End-User

Depois de configurar a configuração no Intune, está pronto para que os utilizadores finais recebam as suas aplicações selecionadas.

Siga estes passos para obter automaticamente a sua(s) aplicação):

1. Inscreva o seu dispositivo com o seu inquilino.
2. Uma vez concluída a inscrição do seu dispositivo, deverá receber a aplicação no seu dispositivo.
3. Se não estiver a vê-lo imediatamente, vá a **Definições**  >  **Contas**  >  **Trabalhar ou Escola a** sua  >  *conta* Informação, e desloque-se para ver informações sobre o estado da aplicação instalada.

Como chegar a apps através do Portal da Empresa:

1. Abra o **Menu Iniciar** e selecione **Microsoft Store**.
2. Procure no **Portal da Empresa** e descarregue a aplicação.
3. Inscreva-se na sua conta.
4. Selecione a aplicação que deseja receber e descarregue-a.

> [!Tip]
> Saiba mais sobre [a instalação automática do Portal da Empresa](https://docs.microsoft.com/mem/intune/apps/company-portal-app) e a [implementação e gestão de aplicações no Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
