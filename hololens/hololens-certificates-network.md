---
title: Preparar certificados e perfis de rede para HoloLens 2
description: Saiba como configurar, utilizar, implementar e resolver problemas de certificados para rede em HoloLens 2 dispositivos de realidade mista.
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
ms.openlocfilehash: d9b752c820af8dbceb2b6b9f3c7a7be4df910805b5a5014bb3e3650551392ce8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664311"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Preparar certificados e perfis de rede para HoloLens 2

A autenticação baseada em certificados é um requisito comum para os clientes que usam HoloLens 2. Você pode precisar de certificados para aceder wi-fi, para conectar-se a soluções VPN, ou para aceder a recursos internos na sua organização.

Uma vez que HoloLens 2 dispositivos são normalmente associados a Azure Ative Directory (Azure AD) e geridos pela Intune ou outro fornecedor de MDM, você precisará de implementar esses certificados utilizando um Protocolo de Inscrição de Certificado Simples (SCEP) ou infraestrutura de certificados de criptografia de chave pública (PKCS) que está integrado com a sua solução MDM. 

>[!NOTE]
> Se não tiver um fornecedor de MDM, ainda pode utilizar certificados através de um [pacote de provisionamento](hololens-provisioning.md#steps-for-creating-provisioning-packages) no [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) ou através do Certificate [Manager,](certificate-manager.md) indo para **Definições > Update & Security > Certificate Manager**.

## <a name="certificate-requirements"></a>Requisitos de certificados
Os certificados de raiz são necessários para a implantação de certificados através de uma infraestrutura SCEP ou PKCS. Outras aplicações e serviços na sua organização podem exigir que os certificados de raiz sejam implantados no seu HoloLens 2 dispositivos também. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi requisitos de conectividade
Para permitir que um dispositivo seja automaticamente fornecido com a configuração Wi-Fi necessária para a sua rede empresarial, necessitará de um perfil de configuração Wi-Fi. Pode configurar o Intune ou outro fornecedor de MDM para implementar estes perfis nos seus dispositivos. Se a segurança da sua rede exigir que os dispositivos façam parte do domínio local, também poderá ter de avaliar a sua Wi-Fi infraestrutura de rede para se certificar de que é compatível com HoloLens 2 dispositivos (HoloLens 2 dispositivos são apenas unidos a Ad Azure).

## <a name="deploy-certificate-infrastructure"></a>Implantar infraestrutura de certificados
Se já não existir nenhuma infraestrutura SCEP ou PKCS, terá de preparar uma. Para apoiar a utilização de certificados SCEP ou PKCS para autenticação, a Intune requer a utilização de um [conector](/mem/intune/protect/certificate-connectors)de certificado .

> [!NOTE]
> Quando utilizar o SCEP com um Microsoft CA, também deve configurar o Serviço de [Inscrição de Dispositivos de Rede (NDES)](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Para obter mais informações, consulte [configurar um perfil de certificado para os seus dispositivos em Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implementar certificados e perfil Wi-Fi/VPN
Para implementar certificados e perfis, siga estes passos:
1.  Crie um perfil para cada um dos certificados Raiz e Intermediário (ver [Criar perfis de certificados fidedignos](/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Cada um destes perfis deve ter uma descrição que inclua uma data de validade no formato DD/MM/YYYY. **Os perfis de certificado sem data de validade não serão implantados.**
1.  Criar um perfil para cada certificado SCEP ou PKCS (ver [Criar um perfil de certificado SCEP ou criar um perfil de certificado PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Cada um destes perfis deve ter uma descrição que inclua uma data de validade no formato DD/MM/YYYY. **Os perfis de certificado sem data de validade não serão implantados.**

    > [!NOTE]
    > Como o HoloLens 2 é considerado para muitos como um dispositivo partilhado, vários utilizadores por dispositivo, recomenda-se a implementação de certificados de Dispositivo em vez de certificados de Utilizador para Wi-Fi autenticação sempre que possível

3.  Crie um perfil para cada rede de Wi-Fi corporativa (ver [definições wi-fi para Windows 10 e dispositivos posteriores).](/intune/wi-fi-settings-windows) 
    > [!NOTE]
    > Recomenda-se que o perfil Wi-Fi seja [atribuído](/mem/intune/configuration/device-profile-assign) aos grupos de Dispositivos e não aos grupos do Utilizador, sempre que possível. 

    > [!TIP]
    > Também pode exportar um perfil de Wi-Fi de trabalho a partir de um pc Windows 10 na sua rede corporativa. Esta exportação cria um ficheiro XML com todas as definições atuais. Em seguida, importe este ficheiro para o Intune e use-o como o perfil Wi-Fi para os seus HoloLens 2 dispositivos. Consulte [as definições de exportação e importação Wi-Fi para dispositivos Windows.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Crie um perfil para cada VPN corporativo (ver [Windows 10 e Windows configurações de dispositivo holográfico para adicionar ligações VPN utilizando o Intune).](/intune/vpn-settings-windows-10)

## <a name="troubleshooting-certificates"></a>Certificados de resolução de problemas

No caso de necessitar de validar corretamente um certificado, utilize o [Gestor de Certificados](certificate-manager.md) no dispositivo para verificar se o seu certificado está presente.  

>[!WARNING]
> Embora possa ver certificados implantados pelo MDM no Certificate Manager, não pode desinstalá-los no Certificate Manager. Deve desinstalá-los através do MDM.


