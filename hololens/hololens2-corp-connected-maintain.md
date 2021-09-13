---
title: Guia de Implementação - Corporate connected HoloLens 2 com Dynamics 365 Guides - Manter
description: Saiba como manter HoloLens 2 dispositivos sobre uma rede corporativa Conectada com Guias Dinâmicos 365.
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033431"
---
# <a name="maintain---corporate-connected-guide"></a>Manter - Guia Conectado Corporativo

## <a name="update-hololens"></a>Atualizar HoloLens

A Microsoft desenhou Windows Update for Business para fornecer aos administradores de TI capacidades adicionais de gestão centradas na Windows atualização, tais como a capacidade de implementar atualizações em grupos de dispositivos e definir janelas de manutenção para instalar atualizações.

Um método popular de gestão de atualizações é fazer um adiamento de funcionalidades de 30 dias. Isto permite que os Admins atualizem e pré-visualizam novas funcionalidades, obtendo conhecimento em primeira mão e informando o seu suporte de quaisquer novas alterações.

Saiba como gerir HoloLens atualizações , incluindo dias [programados,](/hololens/hololens-updates)hora marcada e definição de horas ativas no dispositivo, para que seja atualizado fora do horário de trabalho.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Como atualizar Os Guias Dinâmicos 365 (e outras aplicações da loja)

Dynamics 365 Guides é uma aplicação In-Box, e pode ser atualizada através da aplicação Microsoft Store. Para todas as aplicações que são descarregadas através do Microsoft Store, estas podem ser [atualizadas através da própria](/hololens/holographic-store-apps#update-apps) aplicação Microsoft Store manualmente.

## <a name="how-to-update-lob-apps"></a>Como atualizar aplicações LOB

As aplicações LOB podem ser atualizadas da mesma forma que foram adicionadas ao Intune. As aplicações podem ser atualizadas no Intune carregando a nova aplicação com um número de versão mais elevado para a configuração de App existente. Quando o dispositivo sincronizar com o Intune, irá observar que existe uma versão mais recente da aplicação e a aplicação mais recente será descarregada e substituirá a antiga app.

1. Para fazer o upload da aplicação mais recente, navegue para o [portal MEM](https://endpoint.microsoft.com/#home)  ->  **Apps** -> Todas as **aplicações**  ->  *TheNameOfYourApp*  ->  **Properties.**
2. Ao lado das informações da App, **selecione Editar.**
3. Para obter o valor do &quot; ficheiro Select para &quot; atualizar, selecione o seu ficheiro.
4. A partir daqui, use o menu de contexto para abrir o seu explorador de ficheiros e fazer o upload da versão mais recente da aplicação LOB. Certifique-se de incluir as dependências conforme necessário.

Veja mais: [Implementação de aplicativos Intune para HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Plano de Desenvolvimento

Com o seu dispositivo matriculado com sucesso, está agora preparado para implementar mais aplicações LOB para os seus dispositivos. Durante a duração deste Guia, estamos a usar uma aplicação de amostra, mas é mais provável que queira utilizar aplicações personalizadas construídas para as necessidades da sua organização.

Se já tem uma aplicação LOB, então está pronto para implementar a [sua aplicação através do MDM.](/hololens/app-deploy-intune) Se preferir um método diferente, reveja a visão geral da implementação da [aplicação para HoloLens 2](/hololens/app-deploy-overview) para aprender mais métodos de implantação da sua app LOB nos seus dispositivos.

Se ainda tem de criar a sua própria app LOB ou ainda está em processo de criação, então reveja os nossos docs de desenvolvimento de realidade mista para [começar a desenhar e prototipar](/windows/mixed-reality/design/design) ou aprender os conceitos fundamentais para começar com o desenvolvimento da realidade [mista.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Plano de Suporte

Um plano de apoio é uma coisa excelente para se ter em prática. Ter alguém, ou um grupo, treinado para resolver problemas no processo de inscrição em dispositivos HoloLens e também uso geral do dispositivo HoloLens dentro da sua organização é útil. De forma a permitir que os seus utilizadores tenham uma resolução mais rápida dos seus problemas, sugerimos que o seu processo de escalada seja tratado de forma semelhante a esta ordem:

1. Sua mesa de apoio.
2. A sua equipa de peritos em HoloLens
3. [HoloLens Docs](/hololens/)  /  [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)
4. [Suporte de contato](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Gestão de Dispositivos

Este guia falou sobre a criação de Mobile Device Management (MDM) e utilizou-o para configurar algumas configurações do dispositivo e aplicar definições para permitir o acesso em termos de certificados de Wi-Fi e procuração. No entanto, o MDM também pode ser usado para aplicar restrições de dispositivos através de CSPs e Políticas.

Em muitos casos, os dispositivos podem ter restrições de conectividade, tais como Bluetooth, VPN, USB ou até mesmo desligar o acesso à câmara ou microfone. Se algum destes interesses lhe interessa, então encorajamo-lo a ler a nossa página comum de restrições de [dispositivos.](/hololens/hololens-common-device-restrictions)

Existem outras restrições mais complexas do dispositivo que pode utilizar. Como:

- Limitar as páginas que podem ser visualizadas na aplicação Definições utilizando [a DefiniçõesPageVisibilidade](/hololens/settings-uri-list), permitindo aos utilizadores acederem apenas às definições de que precisam de ajustar, como alterar a sua ligação Wi-Fi.
- Utilize [o modo Quiosque](/hololens/hololens-kiosk) para limitar a UI apresentada aos utilizadores num dispositivo. Pode definir Quiosques para mostrar uma única aplicação, ou várias aplicações com uma página de início personalizada. Os quiosques também podem apresentar diferentes experiências a diferentes utilizadores.
- [Windows Application Control (WDAC)](/hololens/windows-defender-application-control-wdac) para impedir que aplicações ou processos específicos se desempam totalmente.

Se quiser aprender sobre métodos adicionais de gestão de dispositivos ou restrições de dispositivos, então dê o próximo passo e leia a nossa [Visão Geral de Gestão de Dispositivos](/hololens/hololens-csp-policy-overview).





