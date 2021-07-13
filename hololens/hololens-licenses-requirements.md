---
title: Requisitos de licença
description: Mantenha-se atualizado com todos os requisitos e diretrizes de licenciamento necessários para a gestão de dispositivos móveis, HoloLens e Assistência Remota.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640288"
---
# <a name="license-requirements"></a>Requisitos de licença

## <a name="hololens-2-device-managed"></a>HoloLens 2 Dispositivo (gerido)

[Conta Azure AD](/azure/active-directory/)

> [!IMPORTANT]
> O Ative Directory (AD) não pode ser utilizado para gerir HoloLens dispositivos.

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) ou outro MDM.
- [Windows Autopilot para HoloLens 2](hololens2-autopilot.md)- simplifica a experiência de fornecimento tanto para administradores de TI como para utilizadores finais. Os administradores de TI podem pré-configurar HoloLens 2 políticas, e após o primeiro arranque, os dispositivos serão implantados em estado de preparação para o negócio com zero interação do utilizador final. 

  > [!NOTE]
  > Windows O piloto automático requer que [o Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) e a [inscrição automática](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) sejam configurados primeiro para o fluxo de piloto automático de baixo toque e para a implementação do dispositivo. 

### <a name="business-use-case"></a>Caso de utilização de negócios: 

- [Cenário de implantação A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - prova de conceito ou implantação de pilotos.

- [Cenário de implantação B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - implantação à escala.

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2 Apenas dispositivo (não gerido)

Ao utilizar uma conta Microsoft (MSA) ou uma conta local não são necessárias licenças adicionais para estas contas.

[Conta Local](/windows/security/identity-protection/access-control/local-accounts)

- Esta conta deve ser [disponibilizada](hololens-provisioning.md#provisioning-package-hololens-wizard) com antecedência com Windows Designer de Configuração (WCD).

[Conta Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> Vários utilizadores não são suportados por um dispositivo que utilize qualquer uma destas contas.

### <a name="business-use-case"></a>Caso de utilização de negócios: 

- [Cenário de implantação C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - implantação offline ou segura.
 
## <a name="dynamics-365-licensing-and-requirements"></a>Dinâmica 365 Licenciamento e Requisitos

### <a name="dynamics-365-remote-assist"></a>Dinâmico 365 Assistência Remota 

#### <a name="admin"></a>Admin

- Conta AZURE AD (necessária para a aquisição da subscrição e atribuição de licenças)
- [Subscrição de Assistência Remota](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [Ensaio de Assistência Remota)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist utilizador

- Conta do Azure AD

- Licença de Assistência Remota 

  > [!NOTE]
  > Microsoft Teams está agregado com assistência remota

- Conectividade da rede

#### <a name="microsoft-teams-user"></a>Microsoft Teams utilizador

- Conta do Azure AD

- Microsoft Teams ou [Teams Freemium.](https://products.office.com/microsoft-teams/free)

- Conectividade de rede

Se planeia implementar este [cenário de inquilinos cruzados,](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)poderá necessitar de uma licença de Barreiras de Informação. Consulte [este artigo](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se é necessária uma Licença de Barreira de Informação.

### <a name="dynamics-365-guides"></a>Dinâmica 365 Guias 

#### <a name="admin"></a>Admin

- Conta AZURE AD (necessária para a aquisição da subscrição e atribuição de licenças)
- Subscrição de [Guias Dinâmicos](/dynamics365/mixed-reality/guides/setup-step-one) 365 ou teste gratuito

#### <a name="guides-author"></a>Autor de Guias

1. Conta do Azure AD
1. [Licença de Guias Dinâmicos 365](/dynamics365/mixed-reality/guides/requirements)
1. Aplicação Dinâmica 365 Guias instalada num PC ou HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (usado para ver o painel de instrumentos Analytics)
1. Papel de autor (para criar guias)
1. Conectividade da rede

#### <a name="guides-user"></a>Guias Utilizador

1. Conta do Azure AD
1. [Licença de Guias Dinâmicos 365](/dynamics365/mixed-reality/guides/requirements)
1. Aplicação Dynamics 365 Guides instalada num HoloLens
1. Função do operador (para testar ou utilizar guias)
1. Conectividade da rede
