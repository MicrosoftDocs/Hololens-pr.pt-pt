---
title: Visibilidade de Definições de Página
description: Mantenha-se atualizado com a nossa lista de URIs suportados para PageVisibilityList e Guide em holoLens dispositivos de realidade mista.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, acesso atribuído, quiosque, página de definições
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5779ffa1de1700b4fcd17fc17b8ae3a82a45c22
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379893"
---
# <a name="page-settings-visibility"></a>Visibilidade de Definições de Página

Uma das funcionalidades geríveis para dispositivos HoloLens é a utilização da [política Definições/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas dentro da aplicação Definições. PageVisibilityList é uma política que permite que os administradores de TI impeçam que páginas específicas na aplicação Definições do Sistema sejam visíveis ou acessíveis, ou que o façam para todas as páginas, exceto as especificadas.

> [!NOTE]
> Esta funcionalidade é apenas avaliável no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou superior para dispositivos HoloLens 2. Certifique-se de que os dispositivos para os seguintes são atualizados.

O exemplo a seguir ilustra uma política que permitiria o acesso apenas às páginas sobre e bluetooth, que têm URI "ms-settings:network-wifi" e "ms-settings:bluetooth" respectivamente:
- `showonly:network-wifi;network-proxy;bluetooth`

Para definir isto através de um Pacote de Provisionamento:

1. Ao criar o seu pacote no Windows Configuration Designer navegue para **políticas > definições > PageVisibilityList**
1. Insira a corda: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exporte o seu Pacote de Provisionamento.
1. Aplique a embalagem no seu dispositivo.
Para obter todos os detalhes sobre como criar e aplicar um pacote de provisionamento visite [esta página](hololens-provisioning.md).

Isto pode ser feito via Intune usando OMA-URI:

1. Crie uma **política personalizada.**
1. Ao configurar o OMA-URI utilize a cadeia: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Ao selecionar a escolha de dados escolha: **String**
1. Ao escrever o valor: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Certifique-se de atribuir a configuração do dispositivo personalizado a um grupo em que o dispositivo se destina a estar.

Consulte a [configuração do MDM holoLens](hololens-mdm-configure.md) para obter mais informações sobre grupos Intune e configurações de dispositivos.

Independentemente do método escolhido, o seu dispositivo deverá agora receber as alterações e os utilizadores serão apresentados com a seguinte App de Definições.

![Screenshot de horas ativas a ser modificada na aplicação Definições](images/hololens-page-visibility-list.jpg)

Para configurar as páginas de aplicações Definições para mostrar ou ocultar a sua própria seleção de páginas, dê uma olhada nas Definições URIs disponíveis nos HoloLens.

## <a name="settings-uris"></a>IURS de Definições

Os dispositivos HoloLens e dispositivos Windows 10 têm uma seleção diferente de páginas dentro da aplicação Definições. Nesta página, encontrará apenas as definições que existem no HoloLens.

### <a name="accounts"></a>Contas
| Página de definições           | URI                                            |
|-------------------------|------------------------------------------------|
| Acesso escolar ou profissional | `ms-settings:workplace`                         |
| Inscrição da Íris       | `ms-settings:signinoptions-launchirisenrollment` |
| Assinar opções         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>Aplicações
| Página de definições | URI                          |
|---------------|------------------------------|
| Apps & apresenta<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| Apps & funcionalidades > Opções Avançadas <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| Apps & funcionalidades > Offline Maps <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| Apps & funcionalidades > Offline Maps > Baixar mapas <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Dispositivos
| Página de definições | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| Rato <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Privacidade
| Página de definições            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informação da Conta             | `ms-settings:privacy-accountinfo`              |
| Diagnóstico de Aplicativos        | `ms-settings:privacy-appdiagnostics`              |
| Aplicativos de fundo        | `ms-settings:privacy-backgroundapps`              |
| Calendário                 | `ms-settings:privacy-calendar`                    |
| Chamada História             | `ms-settings:privacy-callhistory`                 |
| Câmara                   | `ms-settings:privacy-webcam`                      |
| Contactos                 | `ms-settings:privacy-contacts`                    |
| Feedback & de Diagnóstico | `ms-settings:privacy-feedback`                    |
| Documentos                | `ms-settings:privacy-documents`                   |
| E-mail                    | `ms-settings:privacy-email`                       |
| Sistema de ficheiros              | `ms-settings:privacy-broadfilesystemaccess`       |
| General <sup>2</sup>             | `ms-settings:privacy-general`       |
| A & de tinta datilografar personalização <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Localização                 | `ms-settings:privacy-location`                    |
| Mensagens                | `ms-settings:privacy-messaging`                   |
| Microfone               | `ms-settings:privacy-microphone`                  |
| Moção <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| Notificações            | `ms-settings:privacy-notifications`               |
| Outros dispositivos            | `ms-settings:privacy-customdevices`               |
| Imagens                 | `ms-settings:privacy-pictures`                    |
| Rádios                   | `ms-settings:privacy-radios`                      |
| Bordas <sup>screenshot 2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Screenshots e aplicativos <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Voz                   | `ms-settings:privacy-speech`                      |
| Tarefas                    | `ms-settings:privacy-tasks`                       |
| Movimentos dos utilizadores           | `ms-settings:privacy-backgroundspatialperception` |
| Vídeos                   | `ms-settings:privacy-videos`                      |
| Ativação de voz       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Rede e Internet
| Página de definições | URI                              |
|---------------|----------------------------------|
| Modo avião <sup>2</sup> | `ms-settings:network-airplanemode`        |
| Proxy | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>Sistema
| Página de definições      | URI                                |
|--------------------|------------------------------------|
| Bateria <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| Bateria <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| Cores             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Hologramas <sup>2</sup>  |  `ms-settings:holograms`  |
| Calibração <sup>2</sup> |  `ms-settings:calibration` |
| Notificações & ações  | `ms-settings:notifications`          |
| Experiências partilhadas | `ms-settings:crossdevice` 
| Som <sup>2</sup>           | `ms-settings:sound`<br>|
| Volume > de aplicações de som e preferência do dispositivo <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Sound > Gerir dispositivos de som <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Armazenamento            | `ms-settings:storagesense`           |
| Armazenamento > Configue Storage Sense <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Linguagem & tempo
| Página de definições | URI                                           |
|---------------|-----------------------------------------------|
| Data & hora <sup>2</sup> | `ms-settings:dateandtime`                  |
| Teclado <sup>2</sup> | `ms-settings:keyboard`                  |
| Língua <sup>2</sup> | `ms-settings:language`                  |
| Língua <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Linguagem      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Region        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Atualizar segurança &
| Página de definições                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Opções Avançadas                    | `ms-settings:windowsupdate-options`         |
| Recuperação & reinicialização <sup>2</sup>      | `ms-settings:reset`         |
| Programa Windows Insider               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Atualização do Windows - Verifica as atualizações | `ms-settings:windowsupdate-action`          |


>  <sup>1</sup> Para versões anteriores ao Windows Holographic, versão 21H1, os dois URIs seguintes não o levam realmente às **opções avançadas** ou páginas **opções;** apenas bloquearão ou mostrarão a página principal do Windows Update.
> - ms-settings:windowsupdate-opções
> - ms-settings:windowsupdate-restartoptions
 
> <sup>2</sup> - Disponível no Windows Holographic 21H1 ou superior.


Para obter uma lista completa dos URIs de Definições do Windows 10, visite a documentação das [definições de lançamento.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
