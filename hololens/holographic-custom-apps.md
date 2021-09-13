---
title: Gerir aplicativos personalizados para HoloLens (1ª gen)
description: Aprenda a instalar, desinstalar e carregar as aplicações holográficas personalizadas em dispositivos HoloLens utilizando o Portal do Dispositivo e Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033104"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Gerir aplicativos personalizados para HoloLens (1ª gen)

HoloLens suporta muitas aplicações existentes a partir do Microsoft Store, bem como novas aplicações construídas especificamente para HoloLens. Este artigo centra-se em aplicações holográficas personalizadas.  

Para obter mais informações sobre aplicações da loja, consulte [Gerir aplicações com a loja.](holographic-store-apps.md)

> [!IMPORTANT]
> Foram criadas as seguintes informações para o HoloLens (1º género), também chamada de HoloLens Developer Edition na época. Como tal, as aplicações de sideloading através do portal do dispositivo e a instalação de apps através de Visual Studio eram comuns na altura. Para implementações empresariais não recomendamos o modo de desenvolvimento, que ambos os métodos utilizam. Se estiver interessado num método de implementação de aplicações seguras, por favor reveja a nossa [App Management: Overview](app-deploy-overview.md).
>
> Se estiver à procura de um dos métodos de instalação de aplicações para HoloLens 2 dispositivos, consulte:
>
> - [Portal do Dispositivo: Instalar uma App](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Utilizar Visual Studio para implementar e depurar apps](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Instalar aplicações personalizadas

Pode instalar as suas próprias aplicações no HoloLens, quer através do Portal do Dispositivo, quer através da implementação das aplicações a partir de Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Instalar um pacote de aplicações com o Portal do Dispositivo

1. Estabeleça uma ligação do Portal do [Dispositivo](/windows/mixed-reality/using-the-windows-device-portal) ao HoloLens-alvo.

1. Na navegação à esquerda, navegue para a página **Apps.**

1. No **Âmbito do Pacote de Aplicações,** consulte o ficheiro .appx que está associado à sua aplicação.

   > [!IMPORTANT]
   > Certifique-se de que faz referência a quaisquer ficheiros de dependência e certificados associados.

1. Selecione **Go**.

   > [!div class="mx-imgBorder"]
   > ![Instale o formulário de aplicação no portal Windows do dispositivo no Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Implementação a partir de Microsoft Visual Studio 2015

1. Abra a solução de Visual Studio da sua aplicação (.sln ficheiro).

1. Abra as **Propriedades** do projeto.

1. Selecione a seguinte configuração de construção: **Master/x86/Remote Machine**.

1. Quando seleciona **máquina remota:**
   - Certifique-se de que o endereço aponta para o endereço IP Wi-Fi do seu HoloLens.
   - Definir a autenticação para a Universal (Protocolo Não **Encriptado)**.
   
1. Construa a sua solução.

1. Para implementar a aplicação do seu PC de desenvolvimento para o seu HoloLens, selecione **Remote Machine**. Se já tiver uma construção existente sobre o HoloLens, selecione **Sim** para instalar esta versão mais recente.  

   ![Implementação de Máquinas Remotas para aplicações para Microsoft HoloLens em Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. A aplicação instalará e lançará automaticamente no seu HoloLens.

Depois de instalar uma aplicação, vai encontrá-la na lista **de aplicações All** **(Start**  >  **All apps).**
