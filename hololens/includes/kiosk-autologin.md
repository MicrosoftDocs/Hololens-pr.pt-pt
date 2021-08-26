---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859409"
---
# <a name="non-aad-configuration"></a>[Configuração não-AAD](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>Configuração não-AAD

1. Criar um pacote de provisionamento que:
    1. Configurações de tempo de execução/Atribuição De Acesso para permitir contas do Visitante.
    1. Inativamente inscreve o dispositivo em MDM (definições de tempo de execução/Local de Trabalho/Inscrições) para que possa ser gerido mais tarde.
    1. Não crie uma conta local
2. [Aplicar o pacote de provisionamento.](../hololens-provisioning.md)

# <a name="aad-configuration"></a>[Configuração AAD](#tab/aadlogon)

#### <a name="aad-configuration"></a>Configuração AAD

Os dispositivos de aad configurados para o modo quiosque podem iniciar sação numa conta do Visitante com um único toque de botão a partir do ecrã de inscrição. Uma vez iniciado na conta do visitante, o dispositivo não solicitará novamente a inscrição até que o Visitante seja explicitamente assinado a partir do menu inicial ou o dispositivo seja reiniciado.

O início de sísmis do Visitor Auto pode ser gerido através da [política personalizada OMA-URI](/mem/intune/configuration/custom-settings-windows-10):

- Valor URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Política | Description | Configurações |
| --------------------------- | ------------- | -------------------- |
| Realidade Mista/VisitanteAutoLogon | Permite um visitante a apresentar um início de saúde a um quiosque. | 1 (Sim), 0 (Não, padrão.) |