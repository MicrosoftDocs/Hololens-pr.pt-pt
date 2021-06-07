---
title: Preparar certificados e perfis de rede para HoloLens 2
description: Saiba como configurar, utilizar, implementar e resolver problemas certificados para rede em dispositivos de realidade mista HoloLens 2.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: eedb451847757eba02465d7ded4494b9712497ff
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379838"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Preparar certificados e perfis de rede para HoloLens 2

A autenticação baseada em certificados é um requisito comum para os clientes que usam HoloLens 2. Você pode precisar de certificados para aceder wi-fi, para conectar-se a soluções VPN, ou para aceder a recursos internos na sua organização.

Uma vez que os dispositivos HoloLens 2 são normalmente associados ao Azure Ative Directory (Azure AD) e geridos pela Intune ou outro fornecedor de MDM, terá de implementar esses certificados utilizando uma infraestrutura de certificados Simple Certificate (SCEP) ou Desobstrução de Chaves Públicas (PKCS) que esteja integrada com a sua solução MDM. 

>[!NOTE]
> Se não tiver um fornecedor de MDM, ainda pode implementar certificados através de um [pacote de provisionamento](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages) no [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) ou através do Certificate [Manager,](https://docs.microsoft.com/hololens/certificate-manager) indo para **Definições > Atualização & Gestor de Certificados de Segurança >** de Segurança .

## <a name="certificate-requirements"></a>Requisitos de certificados
Os certificados de raiz são necessários para a implantação de certificados através de uma infraestrutura SCEP ou PKCS. Outras aplicações e serviços na sua organização podem exigir que os certificados de raiz sejam também implantados nos seus dispositivos HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi requisitos de conectividade
Para permitir que um dispositivo seja automaticamente fornecido com a configuração Wi-Fi necessária para a sua rede empresarial, necessitará de um perfil de configuração Wi-Fi. Pode configurar o Intune ou outro fornecedor de MDM para implementar estes perfis nos seus dispositivos. Se a segurança da sua rede exigir que os dispositivos façam parte do domínio local, também poderá ter de avaliar a sua Wi-Fi infraestrutura de rede para se certificar de que é compatível com dispositivos HoloLens 2 (os dispositivos HoloLens 2 são apenas unidos a Ad Azure).

## <a name="deploy-certificate-infrastructure"></a>Implantar infraestrutura de certificados
Se já não existir nenhuma infraestrutura SCEP ou PKCS, terá de preparar uma. Para apoiar a utilização de certificados SCEP ou PKCS para autenticação, a Intune requer a utilização de um [conector](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)de certificado .

> [!NOTE]
> Quando utilizar o SCEP com um Microsoft CA, também deve configurar o Serviço de [Inscrição de Dispositivos de Rede (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Para obter mais informações, consulte [configurar um perfil de certificado para os seus dispositivos no Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implementar certificados e perfil Wi-Fi/VPN
Para implementar certificados e perfis, siga estes passos:
1.  Crie um perfil para cada um dos certificados Raiz e Intermediário (ver [Criar perfis de certificados fidedignos](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Cada um destes perfis deve ter uma descrição que inclua uma data de validade no formato DD/MM/YYYY. **Os perfis de certificado sem data de validade não serão implantados.**
1.  Criar um perfil para cada certificado SCEP ou PKCS (ver [Criar um perfil de certificado SCEP ou criar um perfil de certificado PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Cada um destes perfis deve ter uma descrição que inclua uma data de validade no formato DD/MM/YYYY. **Os perfis de certificado sem data de validade não serão implantados.**

    > [!NOTE]
    > Como o HoloLens 2 é considerado para muitos como um dispositivo partilhado, vários utilizadores por dispositivo, é recomendado para implementar certificados de Dispositivo em vez de certificados de utilizador para Wi-Fi autenticação sempre que possível

3.  Crie um perfil para cada rede de Wi-Fi corporativa (ver [definições wi-fi para dispositivos Windows 10 e posteriores](https://docs.microsoft.com/intune/wi-fi-settings-windows)). 
    > [!NOTE]
    > Recomenda-se que o perfil Wi-Fi seja [atribuído](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) aos grupos de Dispositivos e não aos grupos do Utilizador, sempre que possível. 

    > [!TIP]
    > Também pode exportar um perfil de Wi-Fi de trabalho a partir de um PC Windows 10 na sua rede corporativa. Esta exportação cria um ficheiro XML com todas as definições atuais. Em seguida, importe este ficheiro para o Intune e use-o como Wi-Fi perfil para os seus dispositivos HoloLens 2. Consulte [as definições de exportação e importação Wi-Fi para dispositivos Windows.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Crie um perfil para cada VPN corporativo (ver [definições de dispositivos Holográficos Windows 10 e Windows para adicionar ligações VPN utilizando o Intune).](https://docs.microsoft.com/intune/vpn-settings-windows-10)

## <a name="troubleshooting-certificates"></a>Certificados de resolução de problemas

No caso de necessitar de validar corretamente um certificado, utilize o [Gestor de Certificados](certificate-manager.md) no dispositivo para verificar se o seu certificado está presente.  

>[!WARNING]
> Embora possa ver certificados implantados pelo MDM no Certificate Manager, não pode desinstalá-los no Certificate Manager. Deve desinstalá-los através do MDM.


