---
title: Página Definições Visibilidade
description: Mantenha-se atualizado com a nossa lista de URIs suportados para PageVisibilityList e Guia em HoloLens dispositivos de realidade mista.
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
ms.openlocfilehash: 5ac3ff27085fd2f7c5bc1de0e461079a673bbb23
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637171"
---
# <a name="page-settings-visibility"></a>Página Definições Visibilidade

Uma das funcionalidades geríveis para dispositivos HoloLens é utilizar a [política Definições/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas dentro da aplicação Definições. PageVisibilityList é uma política que permite que os administradores de TI impeçam que páginas específicas no Sistema Definições aplicação sejam visíveis ou acessíveis, ou que o façam para todas as páginas, exceto as especificadas.

> [!NOTE]
> Esta funcionalidade é apenas avaliável em [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou superior para HoloLens 2 dispositivos. Certifique-se de que os dispositivos para os seguintes são atualizados.


## <a name="examples"></a>Exemplos
As páginas são identificadas por uma versão abreviada dos URIs publicados, que é o URI menos o prefixo "ms-settings:".

O exemplo a seguir ilustra uma política que permitiria o acesso apenas às páginas sobre e bluetooth, que têm URI "network-wifi" e "bluetooth" respectivamente:
- `showonly:network-wifi;network-proxy;bluetooth`

O exemplo a seguir ilustra uma política que esconderia a página de Reset do SISTEMA:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Implementação desta política via Intune

Estes são os valores de configuração que serão fornecidos ao Intune:

- **Nome:** Um nome de exibição preferido para o perfil.
- **OMA-URI:** O URI totalmente qualificado da página de definição, incluindo o seu [âmbito](/windows/client-management/mdm/policy-configuration-service-provider). Estes exemplos nesta página estão a usar o `./Device` âmbito.
- **Valor:** Um valor de cadeia que indica se deve ocultar ou mostrar *apenas* as páginas especificadas. Os valores possíveis são `hide:<pagename>` `showonly:<pagename>` e. 
 
Várias páginas podem ser especificadas separando-as com um ponto e vírgula, e uma lista de páginas comuns pode ser encontrada abaixo.

1. Crie uma **política personalizada.**
1. Ao definir o **OMA-URI** introduza o URI totalmente ateado. Por exemplo: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Ao selecionar a escolha de dados escolha: **String**
1. Ao especificar **Valor,** utilize a orientação acima. Por exemplo: **`showonly:network-wifi;network-proxy;bluetooth`** ou **`hide:reset`** 
> [!IMPORTANT]
> Certifique-se de atribuir a configuração do dispositivo personalizado a um grupo em que o dispositivo se destina a estar. Se este passo não for dado, a apólice será empurrada, mas não será aplicada.

Consulte [HoloLens configuração do MDM](hololens-mdm-configure.md) para obter mais informações sobre grupos Intune e configurações do dispositivo.


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Implementação desta política através de um pacote de provisionamento

Estes são os valores de configuração que serão especificados no Windows Designer de Configuração:

**Valor:** Um valor de cadeia que indica se deve ocultar ou mostrar *apenas* as páginas especificadas. Os valores possíveis são `hide:<pagename>` `showonly:<pagename>` e. Várias páginas podem ser especificadas separando-as com um ponto e vírgula, e uma lista de páginas comuns pode ser encontrada abaixo.


1. Ao criar o seu pacote em Windows Designer de Configuração navegue para **políticas > Definições > PageVisibilityList**
1. Insira a corda: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exporte o seu Pacote de Provisionamento.
1. Aplique a embalagem no seu dispositivo.
Para obter informações completas sobre como criar e aplicar um pacote de provisionamento visite [a página de a provisionamento HoloLens](hololens-provisioning.md).


Independentemente do método escolhido, o seu dispositivo deverá agora receber as alterações e os utilizadores serão apresentados com a seguinte App Definições.

![Screenshot de horas ativas a ser modificada na app Definições](images/hololens-page-visibility-list.jpg)

Para configurar as páginas de aplicações Definições para mostrar ou ocultar a sua própria seleção de páginas, dê uma olhada nas URIs Definições disponíveis no HoloLens.

## <a name="settings-uris"></a>Definições URIs

HoloLens dispositivos e dispositivos Windows 10 têm uma seleção diferente de páginas dentro da aplicação Definições. Nesta página, encontrará apenas as definições que existem no HoloLens.

### <a name="accounts"></a>Contas
| Página de definições           | URI                                            |
|-------------------------|------------------------------------------------|
| Acesso escolar ou profissional | `workplace`                         |
| Inscrição da Íris       | `signinoptions-launchirisenrollment` |
| Assinar opções         | ` signinoptions `                   |

### <a name="apps"></a>Aplicações
| Página de definições | URI                          |
|---------------|------------------------------|
| Apps & apresenta <sup>2</sup>     | `appsfeatures` <br> |
| Apps & funcionalidades > Opções Avançadas <sup>2</sup>     | `appsfeatures-app` <br> |
| Apps & funcionalidades > Offline Mapas <sup>2</sup>     | `maps-maps` <br> |
| Apps & funcionalidades > Offline Mapas > Baixar mapas <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Dispositivos
| Página de definições | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Rato <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Privacidade
| Página de definições            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informação da Conta             | `privacy-accountinfo`              |
| Diagnóstico de Aplicativos        | `privacy-appdiagnostics`              |
| Aplicativos de fundo        | `privacy-backgroundapps`              |
| Calendário                 | `privacy-calendar`                    |
| Chamada História             | `privacy-callhistory`                 |
| Câmara                   | `privacy-webcam`                      |
| Contactos                 | `privacy-contacts`                    |
| Feedback & de Diagnóstico | `privacy-feedback`                    |
| Documentos                | `privacy-documents`                   |
| E-mail                    | `privacy-email`                       |
| Sistema de ficheiros              | `privacy-broadfilesystemaccess`       |
| General <sup>2</sup>             | `privacy-general`       |
| A & de tinta datilografar personalização <sup>2</sup>             | `privacy-speechtyping`       |
| Localização                 | `privacy-location`                    |
| Mensagens                | `privacy-messaging`                   |
| Microfone               | `privacy-microphone`                  |
| Moção <sup>2</sup>               | `privacy-motion`                  |
| Notificações            | `privacy-notifications`               |
| Outros dispositivos            | `privacy-customdevices`               |
| Imagens                 | `privacy-pictures`                    |
| Rádios                   | `privacy-radios`                      |
| Bordas <sup>screenshot 2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Screenshots e aplicativos <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Voz                   | `privacy-speech`                      |
| Tarefas                    | `privacy-tasks`                       |
| Movimentos dos utilizadores           | `privacy-backgroundspatialperception` |
| Vídeos                   | `privacy-videos`                      |
| Ativação de voz       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Rede e Internet
| Página de definições | URI                              |
|---------------|----------------------------------|
| Modo avião <sup>2</sup> | `network-airplanemode`        |
| Proxy | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>Sistema
| Página de definições      | URI                                |
|--------------------|------------------------------------|
| Bateria <sup>2</sup>           | `batterysaver`<br>|
| Bateria <sup>2</sup>           | `batterysaver-settings`<br>|
| Cores             | `colors`<br>`personalization-colors` |
| Hologramas <sup>2</sup>  |  `holograms`  |
| Calibração <sup>2</sup> |  `calibration` |
| Notificações & ações  | `notifications`          |
| Experiências partilhadas | `crossdevice` 
| Som <sup>2</sup>           | `sound`<br>|
| Volume > de aplicações de som e preferência do dispositivo <sup>2</sup>           | `apps-volume`<br>|
| Sound > Gerir dispositivos de som <sup>2</sup>           | `sound-devices`<br>|
| Armazenamento            | `storagesense`           |
| Armazenamento > Configurar Armazenamento Sense <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Linguagem & tempo
| Página de definições | URI                                           |
|---------------|-----------------------------------------------|
| Data & hora <sup>2</sup> | `dateandtime`                  |
| Teclado <sup>2</sup> | `keyboard`                  |
| Língua <sup>2</sup> | `language`                  |
| Língua <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Linguagem      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Region        | `regionformatting`                  |

### <a name="update--security"></a>Atualizar segurança &
| Página de definições                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Opções Avançadas                    | `windowsupdate-options`         |
| Recuperação & reinicialização <sup>2</sup>      | `reset`         |
| Programa Windows Insider               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Atualização - Verificações de atualizações | `windowsupdate-action`          |


- <sup>1</sup> - Para versões anteriores à Windows Holográfica, versão 21H1, os dois URIs seguintes não o levam realmente às **páginas de opções avançadas** ou **opções;** apenas bloquearão ou mostrarão a página principal de Atualização Windows.
  -  windowsupdate opções
  -  windowsupdate-restartoptions

- <sup>2</sup> - Disponível em Windows Holographic 21H1 ou superior.


Para obter uma lista completa de WINDOWS 10 DEFINIÇÕES URIs, visite a documentação de [definições de lançamento.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
