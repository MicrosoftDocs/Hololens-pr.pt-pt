---
title: Introduzindo a nova app Definições
description: Conheça a nova aplicação Definições
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, configurações, picker de aplicativos, volume
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379978"
---
# <a name="new-settings-app"></a>App Novas Definições

Com [o Windows Holographic, versão 21H1, estamos](hololens-release-notes.md#windows-holographic-version-21h1)a introduzir uma nova versão da aplicação Definições. A nova aplicação Definições inclui novas funcionalidades e definições expandidas para HoloLens 2 nas seguintes áreas: Som, Energia & sono, Rede & Internet, Apps, Contas, Facilidade de Acesso e muito mais.

> [!NOTE]
> Uma vez que a nova aplicação Definições é distinta da aplicação Definições antigas, quaisquer janelas de Definições que tenha colocado anteriormente em torno do seu ambiente serão removidas após a atualização.

![Página inicial da aplicação De Novas Definições](images/new-settings-app.png)

**Novas funcionalidades e configurações**
- Pesquisa de definições: procure definições a partir da página inicial de Definições utilizando palavras-chave ou o nome da definição.
- Calibração de [cor](hololens2-display.md#how-to-use-display-color-calibration) > sistema
    - Selecione um perfil de cores alternativo para o seu ecrã HoloLens 2.
- Som > do sistema:
  - Dispositivos de áudio de entrada e saída: escolha independentemente os seus dispositivos de áudio de entrada e saída (por exemplo, ouça áudio através de auscultadores Bluetooth ou utilize um microfone USB-C para entrada de áudio).
    > [!NOTE]
    > Os microfones Bluetooth não são suportados pelos HoloLens 2.
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
- As janelas de definições previamente colocadas serão removidas (ver nota acima).
- Já não é possível mudar o nome do seu dispositivo com a aplicação Definições. Os administradores de TI podem renomear os dispositivos utilizando o modelo de nome do dispositivo [Windows Autopilot para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) ou o nó MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- A página Ethernet mostra sempre um dispositivo Ethernet virtual ("UsbNcm") em todos os momentos.
- A utilização da bateria para o novo Microsoft Edge pode não ser exata, devido à sua natureza como uma aplicação de ambiente de trabalho Win32 suportada por uma camada de adaptador UWP (nenhuma correção prevista para breve).

