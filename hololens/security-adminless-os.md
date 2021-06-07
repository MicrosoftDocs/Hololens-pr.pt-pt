---
title: Segurança do sistema operativo sem administração
description: Saiba mais sobre sistemas operativos sem administração, proprietários de dispositivos e segurança em dispositivos de realidade mista HoloLens.
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
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379877"
---
# <a name="admin-less-operating-system"></a>Sistema operativo sem administração

O HoloLens 2 minimiza a área de superfície para a escalada de privilégios, desativando o suporte ao grupo de Administradores e limitando todo o código de aplicação UWP de terceiros para executar apenas como utilizadores padrão dentro da caixa de areia AppContainer. Este código só tem acesso aos recursos protegidos por capacidades expressamente manifestadas na aplicação de um utilizador não levítico, para além dos recursos acessíveis a todos os AppContainers.
Estas capacidades de aplicação continuam a ter o modelo de classificação de três níveis:
  * Geral
  * Restrito
  * Windows

Os componentes do Windows também podem alavancar a caixa de areia AppContainer através de UWPs do sistema. Para saber mais sobre a Universal Windows Platform (UWP), consulte [a documentação do UWP](https://docs.microsoft.com/windows/uwp/). Além disso, os componentes windows com maior necessidade de redução de privilégios (como páginas de conteúdos de navegador ou parsers) utilizam a caixa de areia Menos Privilegiada appContainer (LPAC), que corta o acesso ao conjunto de recursos acessíveis a todos os AppContainers.

## <a name="device-owner"></a>Proprietário do dispositivo

Por último, a execução de operações específicas a nível do dispositivo, como a junção do dispositivo a um inquilino ou à gestão do utilizador, só é permitida para "proprietários de dispositivos". Este grupo é preenchido por utilizadores no dispositivo através de um dos seguintes passos:
  * O primeiro utilizador do dispositivo é sempre designado como Proprietário. 
> [!IMPORTANT]
>Para os utilizadores AD Azure, a exceção a esta regra é que se o dispositivo for Azure AD aderido através de inscrição em AD Azure ou a granel, que utiliza um utilizador não real. Neste caso, o primeiro utilizador AAD a assinar no dispositivo não pode ser feito automaticamente pelo proprietário do dispositivo, a menos que esse utilizador tenha a função de "administrador global" ou "administrador de dispositivos" atribuída no portal Azure. Para mais informações, consulte a nota abaixo.  

  * Quando um utilizador é promovido a proprietário do UX de definições por outro Proprietário no dispositivo.
  * Se o proprietário do dispositivo já não estiver disponível (sai da empresa) e o dispositivo for a aderido ao Azure AD, o Administrador Inquilino pode mudar o proprietário do dispositivo para um novo utilizador no portal Azure. Os Administradores Globais e Administradores de Dispositivos de um inquilino AZURE AD são implicitamente inscritos como Proprietários no dispositivo sem exigir qualquer um dos passos anteriores.  

 Os administradores de TI podem gerir o que as aplicações podem aceder através das políticas [de Privacidade.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) 

> [!NOTE]
> Para saber mais sobre quem é o proprietário de um dispositivo de ação AD Azure, consulte [a documentação "Atribuir a Administração Local"](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (mas leia "administrador local" como "proprietário de dispositivos" uma vez que a administração não existe no HoloLens).