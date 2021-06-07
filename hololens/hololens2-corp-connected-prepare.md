---
title: Guia de Implementação - HoloLens conectados corporativos 2 com dinâmica 365 guias - Preparar
description: Saiba como se preparar para a inscrição de dispositivos HoloLens 2 numa rede conectada corporativa com a Dynamics 365 Guides.
keywords: HoloLens, gestão, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Device Management
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378580"
---
# <a name="prepare---corporate-connected-guide"></a>Preparar - Guia Conectado Corporativo
## <a name="infrastructure-essentials"></a>Infraestruturas Essenciais
Para cenários de implementação pessoal e corporativo, um sistema de Gestão de Dispositivos Móveis (MDM) é a infraestrutura essencial necessária para implementar e gerir dispositivos Windows 10, especialmente os HoloLens 2. Uma [subscrição Azure AD Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) é recomendada como um fornecedor de identidade e **necessária** para suportar certas capacidades.

> [!NOTE]
> Apesar de o HoloLens 2 estar implantado e gerido como um dispositivo móvel, é geralmente utilizado como um dispositivo partilhado entre muitos utilizadores.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD é um serviço de diretório baseado na nuvem que fornece gestão de identidade e acesso. As organizações que utilizam o Microsoft Office 365 ou o Intune já estão a utilizar o Azure AD, que tem três edições: Grátis, Premium P1 e Premium P2 (ver [edições do Azure Ative Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Todas as edições suportam o registo do dispositivo Azure AD, mas o Premium P1 é necessário para permitir a inscrição automática do MDM que iremos utilizar neste guia mais tarde.
> [!Important]
> É essencial ter um AD Azure, uma vez que os dispositivos HoloLens não suportam a ad join no local. Se ainda não tiver um AD Azure configurado, siga as instruções para começar e [Crie um novo inquilino no Azure Ative Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Gestão de Identidades
Neste guia, a [Identidade](https://docs.microsoft.com/hololens/hololens-identity) utilizada serão as contas AD da Azure. Existem vários benefícios para as contas AD da Azure, tais como:
- Os colaboradores utilizam a sua conta Azure AD para registar o dispositivo em Azure AD e podem matriculá-lo automaticamente com a solução MDM da organização (Azure AD+MDM – requer uma [subscrição Azure AD Premium).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)
- As contas AD da Azure têm opções de [autenticação](https://docs.microsoft.com/hololens/hololens-identity) adicionais através [do Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Além do login da Iris, os utilizadores podem iniciar sessão a partir de outro dispositivo ou utilizar as teclas de segurança FIDO.

> [!WARNING] 
> Os colaboradores podem usar apenas uma conta para inicializar um dispositivo, pelo **que é imperativo que a sua organização controle qual a conta ativada primeiro**. A conta escolhida determinará quem controla o dispositivo e influencia as suas capacidades de gestão.

## <a name="mobile-device-management"></a>Gestão de Dispositivos Móveis
O Microsoft Intune, parte da Enterprise Mobility + Security, é um sistema MDM baseado na nuvem que gere dispositivos ligados ao seu inquilino. Tal como o Office 365, a Intune utiliza a Azure AD para gestão de identidade, pelo que os colaboradores usam as mesmas credenciais para inscrever dispositivos no Intune que usam para assinar no Office 365. A Intune também suporta dispositivos que executam outros sistemas operativos, como iOS e Android, para fornecer uma solução DEDM completa. Para efeitos deste guia, vamos focar-nos na utilização do Intune para permitir uma implantação na sua rede interna com hololens 2.
> [!Important] 
> É essencial ter Gestão de Dispositivos Móveis. Se ainda não o tem configurado, siga este guia e inicie-se com o Intune.

> [!Important]
> Para utilizar os Guias, é necessária uma conta AD Azure.

> [!Note] 
> Vários sistemas MDM suportam o Windows 10 e a maioria suporta cenários de implementação de dispositivos pessoais e corporativos. Os fornecedores de MDM que suportam o Windows 10 Holographic incluem: AirWatch, MobileIron, entre outros. A maioria dos fornecedores de MDM líderes da indústria já apoiam a integração com a Azure AD. Pode encontrar a lista mais atual de fornecedores de MDM que suportam a Azure AD no [Azure Marketplace.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>Acesso à Rede 
Dynamics 365 Guides é uma aplicação baseada na nuvem. Se o administrador da sua rede tiver uma lista de aprovação, poderão ter de adicionar endereços IP e/ou pontos finais necessários para se ligarem aos servidores Dynamics 365. [Saiba mais sobre o desbloqueio de endereços IP e URLs](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls).

## <a name="certificates"></a>Certificados
Os certificados ajudam a melhorar a segurança fornecendo a autenticação de conta, a autenticação Wi-Fi, a encriptação VPN e a encriptação SSL de conteúdos web. Embora os administradores possam gerir certificados em dispositivos manualmente através do provisionamento de pacotes, é uma boa prática usar o seu sistema MDM para gerir esses certificados durante todo o seu ciclo de vida – desde a inscrição até à renovação e revogação. 

O seu sistema MDM pode implantar automaticamente estes certificados nas lojas de certificados dos dispositivos após a sua inscrição (desde que o seu sistema MDM suporte o **Protocolo de Inscrição de Certificados Simples (SCEP)** ou **normas de criptografia de chaves públicas #12 (PKCS#12)**). [Saiba mais sobre tipos de certificados e perfis que utiliza com o Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/certificates-configure) O MDM também pode consultar e apagar certificados de cliente inscritos ou desencadear um novo pedido de inscrição antes de expirar o certificado atual.
 
Se os seus sistemas MDM já estiverem configurados para certificados, consulte os certificados de referência [e os perfis de rede para hololes 2](https://docs.microsoft.com/hololens/hololens-certificates-network) para começar a implantar certificados e perfis para os seus dispositivos HoloLens 2.

## <a name="scep"></a>SCEP

São necessários os seguintes serviços para a implementação do SCEP, com exceção do Servidor de Procuração de Aplicações Web.
- [Autoridade de Certificação](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Função do servidor NDES](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Conector Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Também deve publicar o seu URL NDES externo à sua rede corporativa utilizando [o proxy de aplicação AD AZure ou o Proxy de Acesso Web.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Também pode usar outro representante inverso à sua escolha.

![Fluxo de dados SCEP](./images/hololens2-scep-info-flow.png)

Se a sua rede ainda não suporta o SCEP, ou se não tem a certeza se a sua rede está corretamente configurada para SCEP com Intune,  [referência Configure infraestrutura para apoiar o SCEP com a Intune](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure).

Se a sua infraestrutura já suporta o SCEP, terá de [criar](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) um [perfil](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) para cada certificado SCEP que o HoloLens 2 utilizará. Se tiver problemas com o SCEP, utilize [a utilização de perfis de certificado SCEP para obter certificados com o Microsoft Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles).

## <a name="pkcs"></a>PKCS
A Intune também apoia a utilização de certificados de chave privada e pública (PKCS). Referência [Utilize certificados chave privados e públicos no Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) para obter mais informações.

## <a name="proxy"></a>Proxy
A maioria das redes intranet corporativas aproveitam um proxy para gerir o tráfego externo. Com holoLens 2 pode configurar um servidor proxy para ligações ethernet, Wi-Fi e VPN.

Existem alguns tipos diferentes de procuração e formas de configurar proxy. Para efeitos deste guia, optamos por escolher o **proxy Wi-Fi, definido via PAC URL, e implementado via MDM.** Isto vem com as vantagens de ser implementado automaticamente através do MDM, ser capaz de atualizar o ficheiro PAC em vez de usar uma configuração de servidor:porta e, finalmente, usar Wi-Fi procuração para configurar o proxy apenas para aplicar a uma única ligação Wi-Fi permitindo que os dispositivos sejam ainda utilizados se ligados em outro local. 


Para obter mais detalhes sobre as definições de procuração para o Windows 10, consulte [Criar um perfil Wi-Fi para dispositivos no Microsoft Intune - Azure](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Linha de Aplicativos empresariais 
Apesar de várias aplicações poderem ser instaladas através da Microsoft Store, é provável que tenha a sua própria app personalizada que criou especificamente para utilizar na realidade mista. Estas aplicações personalizadas distribuídas por toda a sua organização para o seu negócio são chamadas aplicações Line of Business (LOB).
  
Existem várias formas de implementar aplicações para dispositivos HoloLens 2. As aplicações podem ser implementadas diretamente através do MDM, a Microsoft Store for Business (MSfB), ou sideloaded através de um Pacote de Provisionamento. Para o bem deste guia, iremos implementar aplicações via MDM, através da utilização da app necessária. Isto permitirá que as suas aplicações LOB sejam automaticamente descarregadas para os seus dispositivos HoloLens assim que terminarem a inscrição.

Para aqueles que não têm o seu próprio LOB, forneceremos uma aplicação de amostra para testar este fluxo de implementação. Esta aplicação será a aplicação [MRTK Examples,](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) e já foi pré-construída e embalada para testar a prova de conceito.
 
Mais detalhes sobre a implementação de aplicações podem ser encontrados em [App Management: Overview](https://docs.microsoft.com/hololens/app-deploy-overview).

> [!NOTE]
> HoloLens 2 suporta apenas o funcionamento de aplicações UWP ARM64.

## <a name="guides-playbook"></a>Livro de jogadas de guias
Os guias usam um ambiente microsoft Dataverse como a datastore para as suas aplicações Guides. É importante entender a imagem geral de como o seu ambiente Dataverse interage com as suas aplicações Guides e o seu inquilino. Não vamos cobrir como gerir o seu versão de dados neste guia, mas por favor reveja [os conceitos básicos para implementar a Dynamics 365 Guides - Dynamics 365 Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Passo seguinte 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa - Configure](hololens2-corp-connected-configure.md)