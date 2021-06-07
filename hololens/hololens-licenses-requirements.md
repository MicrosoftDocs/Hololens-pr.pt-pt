---
title: Requisitos de licença
description: Mantenha-se atualizado com todos os requisitos e diretrizes de licenciamento necessários para a gestão de dispositivos móveis, HoloLens e Remote Assist.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379913"
---
# <a name="license-requirements"></a>Requisitos de licença

## <a name="mobile-device-management-mdm-licenses-guidance"></a>Orientação para as licenças de gestão de dispositivos móveis (MDM)

Se planeia gerir os seus dispositivos HoloLens, precisará do Azure AD e de um MDM. O Ative Diretor (AD) não pode ser utilizado para gerir dispositivos HoloLens.
Se planeia utilizar um MDM diferente do Intune, é necessário um [Diretório Ativo Azure.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
Se planeia usar o Intune como seu MDM, leia a [lista de suites](https://docs.microsoft.com/intune/fundamentals/licenses) que incluem licenças Intune. **Por favor, note que a Azure AD está incluída na maioria destas suites.**

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a>Identifique as licenças necessárias para o seu cenário e produtos

### <a name="hololens-1st-gen-licenses-requirements"></a>Requisitos de licenças hololens (1ª gen)

Poderá ser necessário atualizar o seu dispositivo HoloLens (1º género) para o Windows Holographic for Business. (Consulte [as funcionalidades comerciais da HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) para determinar se precisa de fazer upgrade).

 Em caso afirmativo, terá de fazer o seguinte:

- Adquirir um ficheiro XML de licença da HoloLens Enterprise
- Aplique o ficheiro XML nos HoloLens. Pode fazê-lo através de um [pacote de Provisioning](hololens-provisioning.md) ou através do seu [Gestor de Dispositivos Móveis](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### <a name="remote-assist-license-requirements"></a>Requisitos de licença de assistência remota

Certifique-se de que tem o licenciamento e o dispositivo necessários, que pode consultar a documentação dos [requisitos.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)

1. [Licença de Assistência Remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. Ou tente um [julgamento de Assistência Remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Equipas Freemium/Equipas](https://products.office.com/microsoft-teams/free)
1. [Licença Azure Ative Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Se planeia implementar **[este cenário de inquilinos cruzados,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** poderá necessitar de uma licença de Barreiras de Informação. Consulte [este artigo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se é necessária uma Licença de Barreira de Informação.

### <a name="guides-license-requirements"></a>Requisitos de licença de guias

Confira os [requisitos de licenciamento e dispositivo atualizados.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)

1. [Licença Azure Ative Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
