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
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428020"
---
# <a name="license-requirements"></a>Requisitos de licença

## <a name="overview"></a>Descrição Geral
Esta página fornece uma visão geral de alto nível das licenças e contas necessárias para implementar dispositivos de HoloLens 2 geridos e não geridos na sua organização. Inclui também informações para licenciamento de Dinâmicos 365 [Remote Assist](#dynamics-365-remote-assist) e [Guides](#dynamics-365-guides).

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 requisitos de licença e conta

 
|       &nbsp;      | HoloLens geridos | HoloLens não geridos |
|-------------------|-----------------|---------------------|
| **Caso de uso de negócios** | | |
| [Implementar para dispositivos ligados à nuvem - prova de implementação de conceito/piloto](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Implementar dentro da rede da sua organização - implantação em escala](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Implementar em ambiente offline seguro](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Licenças** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> ou <sup>2)</sup> | ✔️  | |
| **Contas** |  | |
| Conta Azure AD Ad | ✔️ |  |
| Conta de Utilizador do Azure AD | ✔️ | |
| [Conta Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Conta Local](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> [Inscrição automática](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) durante a configuração inicial do dispositivo, que regista e junta Azure Ative Directory e permite que o dispositivo seja gerido com o Intune.
- <sup>2</sup> [Windows Autopilot para HoloLens 2](hololens2-autopilot.md) simplifica a experiência de provisionamento tanto para administradores de TI como para utilizadores finais. Os administradores de TI podem pré-configurar HoloLens 2 políticas, e após o primeiro arranque, os dispositivos serão implantados em estado de preparação para o negócio com zero interação do utilizador final.
- <sup>3</sup> Esta conta deve ser [disponibilizada](hololens-provisioning.md#provisioning-package-hololens-wizard) com antecedência com Windows Designer de Configuração (WCD).

> [!IMPORTANT]
> O Ative Directory (AD) não pode ser utilizado para gerir HoloLens dispositivos.
 
> [!WARNING]
> Vários utilizadores não são suportados para um dispositivo que utilize uma conta MSA ou local.

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

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free)

- Conectividade de rede

Se planeia implementar este [cenário de inquilinos cruzados,](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)poderá necessitar de uma licença de Barreiras de Informação. Consulte [este artigo](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se é necessária uma Licença de Barreira de Informação.

### <a name="dynamics-365-guides"></a>Dinâmica 365 Guias 

#### <a name="admin"></a>Admin

1. Conta AZURE AD (necessária para a aquisição da subscrição e atribuição de licenças)
2. Subscrição de [Guias Dinâmicos](/dynamics365/mixed-reality/guides/setup-step-one) 365 ou teste gratuito

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
