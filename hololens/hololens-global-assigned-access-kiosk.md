---
title: Acesso Global Atribuído
description: Começa com o nosso guia para usar o OMA-URI para quiosques de acesso atribuído global com intune e designer de configuração de janelas.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, acesso atribuído, quiosque
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640428"
---
# <a name="global-assigned-access--kiosk"></a>Acesso Global Atribuído - Quiosque

Esta funcionalidade configura HoloLens dispositivo 2 para vários quiosques de aplicações, que é aplicável a nível do sistema, não possui qualquer afinidade com qualquer identidade no sistema e aplica-se a todos os que assinam no dispositivo.

> [!NOTE]
> Atualmente, esta funcionalidade apenas se encontra disponível em Windows o Insider. Se quiser experimentar esta funcionalidade antes de estar disponível em HoloLens lançamentos, leia mais sobre [Windows builds insider.](hololens-insider.md)

## <a name="how-to-use-global-assigned-access-in-intune"></a>Como utilizar o Acesso Global Atribuído em Intune?

> [!NOTE]
> Por favor, esteja atento às áreas marcadas com "<!-". Estas áreas exigirão que faça modificações com base nas suas preferências.

1. Crie um perfil de configuração de dispositivo OMA URI personalizado da seguinte forma e aplique-o no grupo de dispositivos HoloLens:

    Valor URI: ./Dispositivo/Fornecedor/MSFT/AtribuiçãoAccess/Configuração

    > [!div class="mx-imgBorder"]
    > ![Acesso Global Atribuído OMA-URI em Intune](images/global-assigned-access-omauri.png)

2. Para valor, atualização e pasta de conteúdo:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Como utilizar o Global Assigned Access em Windows Designer de Configuração?

1. Atualize e guarde a bolha XML acima mencionada como ficheiro XML. 

2. Siga os passos na [Utilização de um pacote de provisionamento para configurar um quiosque de aplicações únicas ou multi-aplicações](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), especificamente a secção "Prov. pacote, passo 2 - Adicione o ficheiro XML de configuração de quiosque a um pacote de provisionamento" e consulte o ficheiro XML que foi guardado no passo anterior.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Posso criar uma configuração em que o global se aplica a todos e a configuração separada se aplica a 1 conta AD Azure ou grupo AD Azure? 

Sim, consulte o exemplo de bolha XML abaixo. O perfil de Acesso Atribuído Global é aplicado no HoloLens quando não é encontrado um específico para o utilizador assinado no utilizador, pelo que se trata de uma configuração de modo de quiosque predefinido para o utilizador inscrito.
Aqui está um exemplo de bolha XML a ser usado:

> [!NOTE]
> Por favor, esteja atento às áreas destacadas com `<!-` . Estas áreas exigirão que faça modificações com base nas suas preferências.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Excluindo os DeviceOwners do Perfil de Acesso Global Atribuído

Esta funcionalidade permite que um utilizador considerado "[Proprietário do Dispositivo](security-adminless-os.md)" no HoloLens seja excluído do Global Assigned Access. Para tirar partido desta funcionalidade, na bolha XML para configuração de quiosque de várias aplicações, certifique-se de que são adicionadas linhas destacadas:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Exemplos adicionais de acesso atribuídos globalmente

Este é um exemplo do quiosque global de acesso atribuído que quando qualquer utilizador assina, terá um quiosque multi-aplicações com a app Definições, Feedback Hub e Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Este exemplo é um quiosque de Acesso Atribuído Global que exclui o proprietário do dispositivo, quando qualquer outro utilizador AZure AD assina em que terá um quiosque multi-aplicações com a app Definições, Feedback Hub e Microsoft Edge. Este quiosque também inclui uma configuração de quiosque secundário para uma conta do Visitante, que pode ser assinada por qualquer pessoa no ecrã de bloqueio. Quando um utilizador assina na conta do Visitante, terá um quiosque multi-aplicações que só tem a aplicação Feedback Hub.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
