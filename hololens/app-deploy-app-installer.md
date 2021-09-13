---
title: Como carregar lateralmente e instalar apps através de HoloLens 2 App Installer
description: Aprenda a instalar e resolver problemas com o instalador de aplicações e carregar lateralmente e instalar aplicações via UI.
keywords: gestão de aplicativos, app, hololens, instalador de aplicativos
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 071dfb3b211928c561fc84754dd7ed4d64886f61
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033072"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Instale apps no HoloLens 2 através do Instalador de Aplicações

> [!NOTE]
> Esta funcionalidade foi disponibilizada em [Windows Holographic, versão 20H2 – dezembro 2020 Update](hololens-release-notes.md). Certifique-se de que o seu dispositivo está [atualizado](hololens-update-hololens.md) para utilizar esta funcionalidade.

**Adicionámos uma nova capacidade (App Installer) para permitir a instalação de aplicações de forma mais perfeita** nos seus HoloLens 2 dispositivos. A funcionalidade será **on-by predefinida para dispositivos não geridos**. Para evitar perturbações nas empresas, o instalador de aplicações **não estará disponível para dispositivos geridos** neste momento.  

Um dispositivo é considerado "gerido" se **algum** dos seguintes for verdadeiro:

- MDM [Inscrito](hololens-enroll-mdm.md)
- Configurado com [pacote de provisionamento](hololens-provisioning.md)
- [Identidade](hololens-identity.md) do utilizador é Azure AD

Agora é possível instalar apps sem necessidade de ativar o Modo de Desenvolvimento ou de utilizar o Portal do Dispositivo.  Descarregue (através de USB ou através de Microsoft Edge) o Pacote Appx para o seu dispositivo e navegue para o Pacote Appx no Explorador de Ficheiros para ser solicitado para iniciar a instalação.  Em alternativa, [inicie uma instalação a partir de uma página web](/windows/msix/app-installer/installing-windows10-apps-web). Tal como as aplicações que instala a partir do Microsoft Store ou sideload utilizando a capacidade de implementação da App LOB do MDM, as aplicações precisam de ser assinadas digitalmente com a [Ferramenta de Sinais](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado utilizado para assinar deve ser confiável](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo HoloLens antes de a aplicação poder ser implementada.

## <a name="requirements"></a>Requisitos

### <a name="for-your-devices"></a>Para os seus dispositivos:

Esta funcionalidade encontra-se atualmente disponível em Windows 20H2 holográficos para HoloLens 2 dispositivos. Certifique-se de que todos os dispositivos que utilizam este método são [atualizados](hololens-update-hololens.md).

### <a name="for-your-apps"></a>Para as suas aplicações:

A Configuração da Solução da sua aplicação deve ser **Master** ou **Release,** uma vez que o Instalador de Aplicações utilizará dependências da loja. Veja mais sobre [a criação de pacotes de aplicações.](/windows/msix/app-installer/create-appinstallerfile-vs)

As aplicações instaladas através deste método devem ser assinadas digitalmente. Terá de usar um certificado para assinar a aplicação. Você pode obter um certificado da [Lista de CA Fidedignas da MS,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)caso em que você não precisará tomar qualquer ação extra. Ou pode assinar o seu próprio certificado no entanto esse certificado terá de ser empurrado para o dispositivo.

- Como assinar aplicativos [utilizando a Ferramenta de Sinal.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opções de certificado:**

- [Lista CA Fidedigna de MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Escolha um método de implantação de certificados.**

- [Os pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.
- O MDM pode ser utilizado para [aplicar certificados com configurações do dispositivo.](/mem/intune/protect/certificates-configure)
- Utilize o [gestor de certificados no](certificate-manager.md)dispositivo.

## <a name="installation-method"></a>Método de instalação

1. Verifique se o seu dispositivo não é considerado gerido.
1. Verifique se o seu dispositivo HoloLens 2 está ligado e está inscrito.
1. No seu PC, navegue para a sua aplicação personalizada e copie o seu appapp.appxbundle para o seu nome dedevicename\Internal Armazenamento\Downloads.
    Depois de ter terminado de copiar o seu ficheiro, poderá desligar o seu dispositivo e terminar a instalação mais tarde.
1. A partir do seu HoloLens 2 dispositivo Abra o **Menu Iniciar,** selecione **Todas as aplicações** e lance a aplicação **File Explorer.**
1. Navegue para a pasta Downloads. Pode ser necessário no painel esquerdo da aplicação selecionar este **dispositivo** primeiro e, em seguida, navegar para Downloads.
1. Selecione o ficheiro appxbundle do seuapp.appxbundle.
1. O Instalador de Aplicações será lançado. Selecione o botão **Instalar** para instalar a sua aplicação.

A aplicação instalada será lançada automaticamente após a conclusão da instalação.

![Instalação de exemplos MRTK através do Instalador de Aplicações.](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Instalações de resolução de problemas

Se a sua aplicação não tiver sido instalada, verifique o seguinte para resolver problemas:

- A sua aplicação ou é um Master ou Release build.
- O seu dispositivo é atualizado para uma construção na qual esta funcionalidade está disponível.
- Está [ligado à internet.](hololens-network.md)
- Os seus [pontos finais para a Microsoft Store](hololens-offline.md) estão corretamente configurados.  

## <a name="web-installer"></a>Instalador web

Os utilizadores podem instalar uma aplicação diretamente a partir de um servidor web. Este fluxo requer a utilização do Instalador de Aplicações combinado com um método de distribuição fácil de descarregar e instalar.

### <a name="how-to-set-up-web-install"></a>Como configurar a instalação web:

1. Certifique-se de que a sua aplicação está corretamente configurada para instalar.
1. Siga estes [passos para permitir a instalação a partir de uma página web.](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### <a name="end-user-experience"></a>Experiência do utilizador final:

1. O utilizador recebe e instala o certificado no dispositivo utilizando um método previamente escolhido acima.
1. O utilizador visita o URL criado a partir do degrau acima.

A aplicação irá agora instalar-se no dispositivo. Para encontrar a aplicação, abra o **menu Iniciar** e selecione o botão **Todas as aplicações** para encontrar a sua aplicação.

- Para obter mais ajuda na resolução de problemas, o método de instalação do instalador de aplicações visite [problemas de instalação de aplicações de resolução de problemas.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> A UI durante o processo de atualização não é suportada. Assim, a opção ShowPrompt [nesta página](/windows/msix/app-installer/update-settings) e as opções relacionadas não são suportadas.

## <a name="sample-apps"></a>Exemplos de Aplicações

Experimente o Instalador de Aplicações com uma das nossas aplicações de amostra disponíveis. 
> [!div class="nextstepaction"]
> [Exemplos de aplicações](/windows/mixed-reality/develop/features-and-samples)
