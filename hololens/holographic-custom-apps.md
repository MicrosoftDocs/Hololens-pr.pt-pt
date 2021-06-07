---
title: Gerir aplicativos personalizados para HoloLens (1ª gen)
description: Aprenda a instalar, desinstalar e carregar as aplicações holográficas personalizadas em dispositivos HoloLens utilizando o Portal do Dispositivo e o Estúdio Visual.
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378535"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Gerir aplicativos personalizados para HoloLens (1ª gen)

O HoloLens suporta muitas aplicações existentes a partir da Microsoft Store, bem como novas aplicações construídas especificamente para HoloLens. Este artigo centra-se em aplicações holográficas personalizadas.  

Para obter mais informações sobre aplicações da loja, consulte [Gerir aplicações com a loja.](holographic-store-apps.md)

> [!IMPORTANT]
> A seguinte informação foi criada para os HoloLens (1º género), também chamada de HoloLens Developer Edition na época. Como tal, as aplicações de sideloading através do portal do dispositivo e a instalação de apps via Visual Studio eram comuns na altura. Para implementações empresariais não recomendamos o modo de desenvolvimento, que ambos os métodos utilizam. Se estiver interessado num método de implementação de aplicações seguras, por favor reveja a nossa [App Management: Overview](app-deploy-overview.md).
>
> Se estiver à procura de um dos métodos de instalação de aplicações para dispositivos HoloLens 2, consulte:
> - [Portal do Dispositivo: Instalar uma App](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Utilização do Estúdio Visual para implementar e depurar apps](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Instalar aplicações personalizadas

Pode instalar as suas próprias aplicações no HoloLens, quer utilizando o Portal do Dispositivo, quer implantando as aplicações a partir do Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Instalar um pacote de aplicações com o Portal do Dispositivo

1. Estabeleça uma ligação do Portal do [Dispositivo](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) ao HoloLens alvo.

1. Na navegação à esquerda, navegue para a página **Apps.**

1. No **Âmbito do Pacote de Aplicações,** consulte o ficheiro .appx que está associado à sua aplicação.

   > [!IMPORTANT]
   > Certifique-se de que faz referência a quaisquer ficheiros de dependência e certificados associados.

1. Selecione **Go**.

   > [!div class="mx-imgBorder"]
   > ![Instale o formulário de aplicação no Portal do Dispositivo Windows no Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Implementação do Microsoft Visual Studio 2015

1. Abra a solução visual studio da sua aplicação (.sln ficheiro).

1. Abra as **Propriedades** do projeto.

1. Selecione a seguinte configuração de construção: **Master/x86/Remote Machine**.

1. Quando seleciona **máquina remota:**
   - Certifique-se de que o endereço aponta para o endereço IP Wi-Fi dos seus HoloLens.
   - Definir a autenticação para a Universal (Protocolo Não **Encriptado)**.
   
1. Construa a sua solução.

1. Para implementar a aplicação do seu PC de desenvolvimento para os hololens, selecione **Remote Machine**. Se já tem uma construção existente nos HoloLens, selecione **Sim** para instalar esta versão mais recente.  

   ![Implementação de máquina remota para apps para Microsoft HoloLens em Estúdio Visual](images/vs2015-remotedeployment.jpg)  
   
1. A aplicação instalará e lançará automaticamente nos seus HoloLens.

Depois de instalar uma aplicação, vai encontrá-la na lista **de aplicações All** **(Start**  >  **All apps).**
