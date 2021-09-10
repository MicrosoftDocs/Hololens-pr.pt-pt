---
title: Apresentamos a nova app Definições
description: Conheça a nova app Definições
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, configurações, picker de aplicativos, volume
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bcde697b5887573826a3a1a61e8c3707b4d0337a
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427576"
---
# <a name="new-settings-app"></a>App New Definições

Com [Windows Holographic, versão 21H1, estamos](hololens-release-notes.md#windows-holographic-version-21h1)a introduzir uma nova versão da aplicação Definições. A nova aplicação Definições inclui novas funcionalidades e configurações expandidas para HoloLens 2 nas seguintes áreas: Som, Energia & sono, Rede & Internet, Apps, Contas, Facilidade de Acesso e muito mais.

> [!NOTE]
> Uma vez que a nova aplicação Definições é distinta da aplicação legacy Definições, qualquer Definições janelas que tenha colocado anteriormente em torno do seu ambiente será removida após a atualização.

![Página inicial da aplicação new Definições.](images/new-settings-app.png)

**Novas funcionalidades e configurações**
- Definições pesquisa: procure configurações a partir da página inicial Definições usando palavras-chave ou o nome da definição.
- Calibração de [cor](hololens2-display.md#how-to-use-display-color-calibration) > sistema
    - Selecione um perfil de cores alternativo para o seu ecrã HoloLens 2.
- Som > do sistema:
  - Dispositivos de áudio de entrada e saída: escolha independentemente os seus dispositivos de áudio de entrada e saída (por exemplo, ouça áudio através de auscultadores Bluetooth ou utilize um microfone USB-C para entrada de áudio).
    > [!NOTE]
    > Bluetooth microfones não são suportados por HoloLens 2.
  - Volume de aplicação: ajuste de forma independente o volume de cada aplicação. Consulte [por controlo de volume de aplicação](holographic-home.md#per-app-volume-control).
- Sistema > O & o sono: escolha quando o dispositivo deve ir dormir após um período de inatividade.
- Sistema > Bateria: ativar manualmente o modo de poupança de bateria ou definir um limiar de bateria em que o modo de poupança de bateria se liga automaticamente.
- Dispositivos > USB: pode desativar as ligações USB por defeito.
- Rede & Internet:
  - Os adaptadores USB-C Ethernet vão agora aparecer na Rede & Internet.
  - As definições do adaptador USB-C Ethernet já estão disponíveis, incluindo o seu endereço IP.
  - Agora pode ativar o modo avião no HoloLens 2.
- Aplicações: pode redefinir as aplicações predefinidos utilizadas para tipos de ficheiros e ligações. Para obter mais informações consulte [o selecionador de aplicações Predefinido.](holographic-home.md#default-app-picker)
- Contas > Outros utilizadores: os proprietários de dispositivos podem adicionar utilizadores, atualizar os utilizadores padrão aos proprietários dos dispositivos, reduzir os proprietários de dispositivos para utilizadores padrão e remover os utilizadores.
- Facilidade de acesso: alterar o tamanho do texto e alguns efeitos visuais.

**Problemas conhecidos**
- As janelas Definições previamente colocadas serão removidas (ver nota acima).
- Já não é possível mudar o nome do seu dispositivo com a aplicação Definições. Os administradores de TI podem renomear os dispositivos utilizando o Windows Autopilot para HoloLens modelo de nome do dispositivo [2](hololens2-autopilot.md) ou o nó [DEDSP CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName DOM.
- A página Ethernet mostra sempre um dispositivo Ethernet virtual ("UsbNcm") em todos os momentos.
- O uso da bateria para o novo Microsoft Edge pode não ser exato, devido à sua natureza como uma aplicação de ambiente de trabalho Win32 suportada por uma camada de adaptador UWP (nenhuma correção antecipada em breve).

