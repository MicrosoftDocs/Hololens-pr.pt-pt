---
title: Pacote de Provisionamento
description: Saiba mais sobre a embalagem de aplicações, fornecimento, implementação e implementação de aplicações empresariais para dispositivos HoloLens.
keywords: aplicação, implementação de aplicativos, implementação de aplicativos empresariais, provisionamento
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2cb497d850ff7ba2de66f69e8ec53e6dd36b773cc13d01b038def8d539e3b0c1
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665221"
---
# <a name="provisioning-package"></a>Pacote de Provisionamento

Os pacotes de provisionamento podem ser utilizados para preparar e configurar dispositivos num ambiente sem acesso à gestão de pontos finais. Podem também ser implantados num dispositivo independentemente da identidade do utilizador, do estado de inscrição, durante a Experiência out of Box (OOBE), ou através da [aplicação de um pacote de provisionamento durante a configuração](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## <a name="provisioning-packages-considerations"></a>Considerações relativas aos pacotes de provisionamento:

* Aplicativos não públicos
* Carga lateral USB apenas
* Nenhuma atualização automática (requer atualizações manuais via PPKGs)

As aplicações instaladas através de um pacote de provisionamento devem ser assinadas por um certificado na loja de máquinas local. O fornecimento de pacotes só pode instalar certificados na loja do dispositivo (máquina local), pelo que uma aplicação e certificado podem ser instalados através do mesmo pacote de provisionamento. Se estiver a implementar o seu certificado a partir do MDM ou a instalar através do [Gestor de Certificados,](certificate-manager.md)certifique-se de que implementa o certificado na loja de máquinas local para assinar as aplicações instaladas desta forma.

Para conhecer os fundamentos da criação de um Pacote de Provisionamento para dispositivos HoloLens, visite [HoloLens Provisioning](/hololens/hololens-provisioning). Para implementar uma aplicação, tem de começar com o provisionamento avançado.

> [!NOTE]
> HoloLens (1ª geração) tem aplicações de instalação de suporte limitado **(UniversalAppInstall**) utilizando um pacote de provisionamento. HoloLens dispositivos (1ª geração) só suportam a instalação de uma aplicação via PPKG apenas durante o OOBE e apenas com instalações de contexto do utilizador.

## <a name="setup"></a>Configuração

Dentro [de Windows Designer de Configuração](https://www.microsoft.com/store/productId/9NBLGGH4TX22) dê quatro passos.

1. Definir ApplicationManagement/AllowAllTrustedApps para "Sim". Ver: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Navegue para **UniversalAppInstall**  >  **UserContextAppLicense** insira o **PackageFamilyName**. Consulte [a UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall). Ver também: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Pode utilizar o Portal do Dispositivo num dispositivo ao que já instalou a sua aplicação. Visite a página apps, e olhe para a linha PackageRelativeID, todas as informações antes do "!" É o seu **Nome De Família Pacote.**

3. Em seguida, verá que tem uma nova secção, **ApplicationFile**. Use esta área para carregar o seu pacote de aplicações.

4. Dependendo se adquiriu a sua aplicação ou construiu a sua própria aplicação LOB, terá de carregar o ficheiro de licença ou certificado de segurança.

    - Para o ficheiro de licença: navegue para **UniversalAppInstall**  >  **UserContextAppLicence** e navegue até à localização da sua licença e faça o upload.
    - Para o ficheiro de segurança, navegue em **Certificados** e selecione o seu certificado para instalar ao lado do seu pacote .appx.

Certifique-se de guardar o seu projeto para um local seguro. Em **seguida,** exporte-o como um **pacote de provisionamento.**  

Consulte também: [Aplique o seu pacote de provisionamento à HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
