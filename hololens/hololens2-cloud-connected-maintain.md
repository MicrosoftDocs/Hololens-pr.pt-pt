---
title: Guia de implementação - Implementação HoloLens 2 ligada à nuvem em escala com assistência remota - Manter
description: Mantenha-se atualizado com as nossas dicas para manter e suportar HoloLens dispositivos numa rede Cloud Connected.
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033530"
---
# <a name="maintain---cloud-connected-guide"></a>Manter - Guia ligado à nuvem

## <a name="updates"></a>Atualizações

A Microsoft desenhou Windows Update for Business para fornecer aos administradores de TI capacidades adicionais de gestão centradas na Windows atualização, tais como a capacidade de implementar atualizações em grupos de dispositivos e definir janelas de manutenção para instalar atualizações.

Saiba como [gerir HoloLens atualizações,](/hololens/hololens-updates) incluindo dias programados, hora programada e definição de horas ativas no dispositivo para que seja atualizado fora do horário de trabalho.

O Remote Assist é uma aplicação In-Box e pode ser atualizado através da aplicação Microsoft Store. Para todas as aplicações que são descarregadas através do Microsoft Store podem ser [atualizadas através da própria](/hololens/holographic-store-apps#update-apps) aplicação Microsoft Store manualmente.

## <a name="support-plan"></a>Plano de Suporte

Um plano de apoio é uma coisa excelente para se ter em prática. Ter alguém, ou um grupo treinado para resolver problemas no processo de inscrição em dispositivos HoloLens e também uso geral do dispositivo de HoloLens dentro da sua organização é útil. De forma a permitir que os seus utilizadores tenham uma resolução mais rápida dos seus problemas, sugerimos que o seu processo de escalada seja tratado de forma semelhante a esta ordem:

1. Sua mesa de apoio.
2. A sua equipa de peritos em HoloLens
3. [HoloLens Docs](/hololens/)  /  [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)
4. [Suporte de contato](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Plano de Desenvolvimento

Com o seu dispositivo matriculado com sucesso, está agora preparado para implementar aplicações da Linha de Negócios (apps LOB) para os seus dispositivos. Estes são aplicativos personalizados construídos para a sua organização&#39;necessidades.

Se já tem uma linha de aplicação de negócios, então&#39;pronto para implementar a [sua aplicação através do MDM.](/hololens/app-deploy-intune) Se&#39;prefere um método diferente, em seguida, reveja a visão geral da implementação da [aplicação para HoloLens 2](/hololens/app-deploy-overview) para aprender mais métodos de implementação da sua app LOB nos seus dispositivos.

Se ainda&#39;ter criado a sua própria app LOB ou ainda estiver em processo de criação, então reveja os nossos docs de desenvolvimento de realidade mista para [começar a desenhar e prototipar](/windows/mixed-reality/design/design) ou aprender os conceitos fundamentais para começar com o desenvolvimento da realidade [mista.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Gestão de Dispositivos 

Embora este guia falasse sobre a criação de Mobile Device Management (MDM) não foi utilizado para aplicar restrições de dispositivos ou políticas aplicadas aos dispositivos. A gestão do dispositivo pode ser usada para permitir o acesso, empurrando certificados ou restringindo o acesso com uma variedade de restrições ao dispositivo. 

Em muitos casos, os dispositivos podem ter restrições de conectividade como Bluetooth, VPN, USB ou até mesmo desligar o acesso à câmara ou microfone. Se algum destes interesses o encorajar então a ler a nossa [página comum de restrições](hololens-common-device-restrictions.md)de dispositivos .

Existem outras restrições mais complexas do dispositivo que pode utilizar. Como:

- Limitar as páginas que podem ser visualizadas na aplicação Definições utilizando [a DefiniçõesPageVisibilidade](settings-uri-list.md), permitindo aos utilizadores acederem apenas às definições de que necessitam para se ajustarem, tais como alterar a sua ligação Wi-Fi.
- Utilize [o modo Quiosque](hololens-kiosk.md) para limitar a UI apresentada aos utilizadores num dispositivo. Pode definir Quiosques para mostrar uma única aplicação, ou várias aplicações com uma página de início personalizada. Os quiosques também podem apresentar diferentes experiências a diferentes utilizadores.  
- [Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) para impedir que aplicações ou processos específicos se desempam totalmente.

Se quiser aprender sobre métodos mais diferentes de gestão de dispositivos ou restrições de dispositivos, então dê o próximo passo e leia a nossa Visão Geral de Gestão de Dispositivos.

## <a name="next-step"></a>Passo seguinte

> [!div class="nextstepaction"]
> [Leia a visão geral dos CSPs e da Gestão de Dispositivos](hololens-csp-policy-overview.md)