---
title: Segurança do sistema operativo sem administração
description: Conheça os sistemas operativos sem administração, os proprietários de dispositivos e a segurança em HoloLens dispositivos de realidade mista.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, administradores, sem administração, sistema operativo, sistema operativo sem administração, administrador-os, administração-sem-os, hololens 2, hololens2 segurança,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036609"
---
# <a name="admin-less-operating-system"></a>Sistema operativo sem administração

HoloLens 2 minimiza a área de superfície para a escalada de privilégios, desativando o suporte ao grupo de Administradores e limitando todo o código de aplicação UWP de terceiros para executar apenas como utilizadores padrão dentro da caixa de areia AppContainer. Este código só tem acesso aos recursos protegidos por capacidades expressamente manifestadas na aplicação de um utilizador não levítico, para além dos recursos acessíveis a todos os AppContainers.
Estas capacidades de aplicação continuam a ter o modelo de classificação de três níveis:
  * Geral
  * Restrito
  * Windows

Windows componentes também podem alavancar a caixa de areia AppContainer através de UWPs do sistema. Para saber mais sobre a Plataforma de Windows Universal (UWP), consulte [a documentação da UWP](/windows/uwp/). Além disso, Windows componentes com maior necessidade de redução de privilégios (como páginas de conteúdos de navegador ou parsers) usam a caixa de areia Despretenser appContainer (LPAC) menos privilegiada, que corta o acesso ao conjunto de recursos acessíveis a todos os AppContainers.

## <a name="device-owner"></a>Proprietário do dispositivo

Por último, a execução de operações específicas a nível do dispositivo, como a junção do dispositivo a um inquilino ou à gestão do utilizador, só é permitida para "proprietários de dispositivos". Este grupo é preenchido por utilizadores no dispositivo através de um dos seguintes passos:
  * O primeiro utilizador do dispositivo é sempre designado como Proprietário. 
> [!IMPORTANT]
>Para os utilizadores AD Azure, a exceção a esta regra é que se o dispositivo for Azure AD aderido através de inscrição em AD Azure ou a granel, que utiliza um utilizador não real. Neste caso, o primeiro utilizador AAD a assinar no dispositivo não pode ser feito automaticamente pelo proprietário do dispositivo, a menos que esse utilizador tenha a função de "administrador global" ou "administrador de dispositivos" atribuída no portal Azure. Para mais informações, consulte a nota abaixo.  

  * Quando um utilizador é promovido a proprietário do Definições UX por outro Proprietário no dispositivo.
  * Se o proprietário do dispositivo já não estiver disponível (sai da empresa) e o dispositivo for a aderido ao Azure AD, o Administrador Inquilino pode mudar o proprietário do dispositivo para um novo utilizador no portal Azure. Os Administradores Globais e Administradores de Dispositivos de um inquilino AZURE AD são implicitamente inscritos como Proprietários no dispositivo sem exigir qualquer um dos passos anteriores.  

 Os administradores de TI podem gerir o que as aplicações podem aceder através das políticas [de Privacidade.](/windows/client-management/mdm/policy-csp-privacy) 

> [!NOTE]
> Para saber mais sobre quem é o proprietário de um dispositivo de ação AD Azure, consulte [a documentação "Atribuir a Administração Local"](/azure/active-directory/devices/assign-local-admin) (mas leia "administrador local" como "proprietário do dispositivo" uma vez que a administração não existe no HoloLens).