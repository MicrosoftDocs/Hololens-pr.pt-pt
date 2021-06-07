---
title: Configurar HoloLens em um ambiente comercial
description: Saiba mais sobre a implementação e gestão de HoloLens em ambientes empresariais, incluindo infraestruturas, diretório ativo azul e gestão de dispositivos móveis.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378587"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>Implantação e gestão de empresas HoloLens 2

Esta visão geral destina-se a ajudar os profissionais de TI a compreender considerações para implementar e gerir dispositivos Microsoft HoloLens 2 dentro da empresa.

O HoloLens 2 funciona no Windows 10 Holographic que fornece às organizações tecnologias robustas, flexíveis, incorporadas para dispositivos móveis e gestão de aplicações. O Windows 10 Holographic suporta a gestão do ciclo de vida do dispositivo de ponta a ponta para dar às empresas o controlo sobre os seus dispositivos, dados e apps. O HoloLens 2 pode ser facilmente incorporado em práticas padrão de ciclo de vida, desde a inscrição, configuração e gestão de aplicações do dispositivo até à manutenção e reforma usando uma solução abrangente de gestão de dispositivos móveis.

## <a name="prepare"></a>Preparação

À medida que se prepara para implantar hololes 2 para o seu ambiente de empresa corporativa, existem várias considerações que devem ser revistas e compreendidas à medida que começa a planear a implantação em escala dos HoloLens 2.

### <a name="infrastructure-essentials"></a>Infraestruturas Essenciais

Para o HoloLens 2 num cenário de implantação de empresas corporativas, existem certos serviços de infraestrutura essenciais necessários para suportar todo o conjunto de capacidades. O HoloLens 2 foi construído com [a Modern Mobile Device Management](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) em mente para implementação e gestão. Com a Azure AD Join + MDM como o principal meio de alcançar isso numa força de trabalho móvel cada vez maior. Os tópicos abaixo fornecem uma breve visão geral de cada componente de infraestrutura que deve ser considerado no seu planeamento de implantação para HoloLens 2.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD é um serviço de diretório baseado na nuvem que fornece gestão de identidade e acesso. Pode integrá-lo com diretórios existentes no local para criar uma solução de identidade híbrida. As organizações que utilizam o Microsoft Office 365 ou o Intune já estão a utilizar o Azure AD, que tem três edições: Grátis, Premium P1 e Premium P2 (ver [edições do Azure Ative Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions/) Todas as edições suportam o registo do dispositivo Azure AD, mas o Premium P1 é necessário para permitir a inscrição automática do MDM. HoloLens 2 requer Azure Ative Directory Join para ativar a maioria das funcionalidades e funcionalidades de nível empresarial.

> [!NOTE]
> Nas instalações, o Ative Directory Join não é suportado no HoloLens 2.

### <a name="mobile-device-management"></a>Gestão de Dispositivos Móveis
O HoloLens 2 foi concebido especificamente para ser gerido por sistemas de Gestão de Dispositivos Móveis (MDM) num ambiente empresarial. O Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), parte da Enterprise Mobility + Security, é um sistema MDM baseado na nuvem que gere dispositivos na empresa. Tal como o Office 365, a Intune utiliza a Azure AD para gestão de identidade, pelo que os colaboradores usam as mesmas credenciais para inscrever dispositivos no Intune que usam para assinar no Office 365. Vários sistemas MDM suportam o Windows 10 e a maioria suporta cenários de implementação de dispositivos pessoais e corporativos. Os sistemas MDM também podem gerir implementações de aplicações e atualizações para os HoloLens 2 também. Outros fornecedores de MDM que suportam hololes 2 atualmente incluem: AirWatch, MobileIron, e outros. Todos os fornecedores de sistemas MDM têm acesso igual aos fornecedores de serviços de configuração de gestão de dispositivos do Windows 10 (CSP)s, dando às organizações de TI a liberdade de selecionarem qualquer sistema que melhor se adapte aos seus requisitos de gestão, seja o Microsoft Intune ou um produto MDM de terceiros.

> [!NOTE]
> Os sistemas tradicionais de gestão de PC como o System Center Configuration Manager não são suportados no HoloLens 2.

### <a name="windows-update-for-business"></a>Windows Update para Empresas
A Microsoft desenhou o Windows Update para fornecer aos administradores de TI capacidades de gestão centradas no Windows Update, tais como a capacidade de implementar atualizações em grupos de dispositivos e definir janelas de manutenção para instalar atualizações. Consulte a documentação [de atualizações hololens](https://docs.microsoft.com/hololens/hololens-updates) para obter detalhes sobre a gestão das atualizações do HoloLens 2.

### <a name="certificates"></a>Certificados
O HoloLens 2 suporta a colocação de certificados através do MDM se o seu ambiente necessitar de certificados para a autenticação da rede corp Wi-Fi ou acesso a outros recursos. Algumas configurações de infraestrutura de MDM podem ser necessárias para permitir a implantação de certificados para HoloLens 2. Leia sobre como [preparar certificados e perfis de rede para HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network). Se estiver a utilizar o Intune, consulte os detalhes da configuração da [certificação.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)

## <a name="configure"></a>Configurar

Os administradores do MDM podem definir e implementar definições de política em qualquer dispositivo corporativo matriculado num sistema MDM. Que configurações utilizas diferirão com base no cenário de implantação. No Windows 10, os Fornecedores de Serviços de Configuração (CSP) são uma interface para ler, definir, modificar ou eliminar definições de configuração no dispositivo. Estas definições mapeiam para obter chaves ou ficheiros de registo. Para obter mais informações sobre os CSPs de gestão de dispositivos do Windows 10 para HoloLens 2, consulte a lista completa de [CSPs suportados em dispositivos HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

O HoloLens 2 também suporta a definição de um conjunto limitado de configurações de CSP através de pacotes de provisionamento personalizados. Os pacotes de provisionamento são normalmente alavancados para dispositivos geridos não-MDM e exigem ser aplicados manualmente em cada dispositivo. Consulte a [documentação do HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning) para obter informações sobre a construção de pacotes de provisionamento personalizados.

> [!NOTE]
> O HoloLens 2 suporta [o Windows Autopilot,](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)fornecendo um processo fácil e simples para gerir as configurações do seu dispositivo Windows 10 corporativo.

### <a name="identity-management"></a>Gestão de Identidades

Os colaboradores podem usar apenas uma conta para inicializar um dispositivo, pelo que&#39;é imperativo que a sua organização controle qual a conta ativada primeiro. A conta escolhida determinará quem controla o dispositivo e influencia as suas capacidades de gestão. O HoloLens 2 suporta 3 tipos de conta: Conta de Utilizador Local, Conta Pessoal da Microsoft e Contas de Diretório Ativo Azure. É altamente recomendado alavancar o Azure Ative Directory para a sua solução de gestão de identidade da empresa, pois irá permitir todas as capacidades nos seus dispositivos HoloLens 2. Confira a [identidade dos HoloLens](https://docs.microsoft.com/hololens/hololens-identity) para mais detalhes sobre identidades para HoloLens 2.

### <a name="network-and-connectivity"></a>Rede e Conectividade

Como o HoloLens 2 é um primeiro dispositivo em nuvem, o acesso à rede aos recursos online é necessário para que a funcionalidade e capacidades completas sejam disponibilizadas. Se estiver a implementar dispositivos HoloLens 2 com conectividade com a sua rede intranet corporativa, poderá ser obrigado a atualizar as suas regras de procuração/firewall para permitir o acesso aos serviços de nuvem HoloLens 2. Para obter mais informações, veja a lista de [pontos finais comuns para o sistema operativo HoloLens 2](https://docs.microsoft.com/hololens/hololens-offline). O acesso a pontos finais adicionais pode ser necessário para que aplicações ou outros serviços na nuvem sejam executados em HoloLens 2 com sucesso.

Alguns serviços hololes 2 comuns que requerem acesso adicional ao ponto final são os seguintes:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guias D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (Infraestrutura de Equipas O365)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Implantação de certificados

Se forem necessários certificados para o acesso a redes de Wi-Fi corporativas ou outros serviços dentro da sua organização, o HoloLens 2 suporta a implementação de certificados de utilizador e dispositivo através do MDM. Nota: A sua solução MDM pode necessitar de uma configuração adicional de infraestrutura para implantar certificados em dispositivos Windows 10.

### <a name="security-review"></a>Revisão de Segurança

A maioria dos departamentos de TI da empresa exigirá a avaliação e revisão de novos dispositivos que estão a ser implantados numa rede empresarial. Se a sua organização precisar de uma revisão de segurança do HoloLens 2, pode encontrar mais detalhes para ajudar na [obtenção de aprovações de segurança.](https://docs.microsoft.com/hololens/security-overview)

### <a name="common-hololens-2-device-settings"></a>Configurações comuns do dispositivo HoloLens 2

Ao implementar dispositivos HoloLens 2 para um ambiente empresarial, existem várias configurações comuns de dispositivos que podem ser consideradas ao planear a sua implementação de HoloLens 2. Esta lista destaca configurações e configurações que são consideradas bastante comuns, e não inclui uma lista completa de opções disponíveis:

| Definição do dispositivo | Breve descrição.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restrições de hardware](hololens-requirements.md#hardware-restrictions)               | As restrições de hardware reduzem a conectividade e ajudam na proteção de dados.                        |
| [Perfis Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configurar perfis Wi-Fi sem intervenção ou interação do utilizador.                              |
| [Certificados](hololens-requirements.md#certificates-1)               | Fornecer a autenticação de conta e/ou Wi-Fi, encriptação VPN e encriptação SSL de conteúdo web. |
| [Proxy](hololens-requirements.md#proxy)              | Gerir o tráfego interno.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Controle o acesso a apps e recursos na intranet da sua empresa.                               |
| [Modo quiosque](hololens-requirements.md#kiosk-mode) | Limita as aplicações que são apresentadas aos utilizadores através da UI. |

#### <a name="hardware-restrictions"></a>Restrições de hardware

O HoloLens 2 utiliza tecnologia de ponta que inclui funcionalidades de hardware populares, como câmaras, microfones, altifalantes, interfaces USB, interfaces Bluetooth e Wi-Fi. Pode utilizar restrições de hardware para controlar a disponibilidade destas funcionalidades.

As seguintes listas listam as definições de MDM mais usadas que o HoloLens 2 suporta para configurar restrições de hardware. Algumas destas restrições de hardware fornecem conectividade e ajudam na proteção de dados.

- [**Permitir Wi-Fi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os utilizadores podem ativar e utilizar o rádio Wi-Fi nos seus dispositivos
- [**Permitir a ligação USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a ligação USB está ativada (não&#39;afetar o carregamento USB)
- [**Permitir Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se os utilizadores podem ativar e utilizar o rádio Bluetooth nos seus dispositivos

Leia mais sobre [outras restrições comuns do dispositivo.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Perfis Wi-Fi

A maioria das redes de Wi-Fi corporativos requer certificados e outras informações complexas para restringir e garantir o acesso do utilizador. Esta informação avançada Wi-Fi é difícil para os utilizadores típicos configurar, mas os sistemas MDM podem configurar totalmente estes perfis Wi-Fi sem a intervenção do utilizador. Pode criar vários perfis de Wi-Fi no seu sistema DEDM.

Para obter mais detalhes sobre as definições Wi-Fi para o Windows 10, consulte [as definições wifi do perfil da empresa](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

#### <a name="certificates"></a>Certificados

Os certificados ajudam a melhorar a segurança fornecendo a autenticação de conta, a autenticação Wi-Fi, a encriptação VPN e a encriptação SSL de conteúdos web. Embora os administradores possam gerir os certificados nos dispositivos manualmente através do provisionamento de pacotes,&#39;é uma boa prática utilizar o seu sistema DEM para gerir esses certificados ao longo de todo o seu ciclo de vida – desde a inscrição até à renovação e revogação. O seu sistema MDM pode implantar automaticamente estes certificados nos dispositivos&#39; lojas de certificados após a inscrição do dispositivo (desde que o sistema MDM suporte o Protocolo de Inscrição de Certificados Simples (SCEP) ou normas de criptografia de chaves públicas #12 (PKCS#12)). O MDM também pode consultar e apagar certificados de cliente inscritos ou desencadear um novo pedido de inscrição antes de expirar o certificado atual.

Leia mais sobre como [preparar certificados e perfis de rede para HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy

A maioria das redes intranet corporativas aproveitam um representante para gerir o tráfego interno. Com hololens 2 pode configurar um servidor proxy para ligações ethernet e Wi-Fi. Estas definições não se aplicam às ligações VPN.

Para obter mais detalhes sobre as definições de procuração para o Windows 10, consulte [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### <a name="vpn"></a>VPN

As organizações usam frequentemente uma VPN para controlar o acesso a apps e recursos na sua empresa&#39;intranet. O HoloLens 2 suporta ligações VPN SSL, que requerem um plugin descarregado da Microsoft Store e são específicos do fornecedor VPN à sua escolha.

Para mais detalhes sobre perfis VPN, consulte o [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### <a name="kiosk-mode"></a>Modo quiosque

Pode configurar um dispositivo HoloLens 2 para funcionar como um dispositivo de uso fixo, também chamado de quiosque, configurando o dispositivo para funcionar em modo de quiosque. O modo quiosque limita as aplicações (ou utilizadores) que estão disponíveis no dispositivo. O modo quiosque é uma funcionalidade conveniente que pode usar para dedicar um dispositivo HoloLens 2 a aplicações empresariais ou usar o dispositivo HoloLens 2 numa demonstração de aplicações.

Para obter mais detalhes sobre a configuração de um HoloLens 2 no modo quiosque, consulte [o Setup HoloLens como um quiosque](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>Implementar

### <a name="mdm-device-enrollment"></a>Inscrição de dispositivos MDM

Para implementações empresariais, recomenda-se [inscrever dispositivos](https://docs.microsoft.com/hololens/hololens-enroll-mdm) em MDM como dispositivos corporativos apenas com a aderimento AZure AD e inscrição automática de MDM (Azure AD+MDM). Isto requer Azure AD Premium e suporta a inscrição automática em vários fornecedores de MDM, incluindo Intune.

Saiba mais sobre o método de inscrição auto-implantação [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### <a name="application-deployment"></a>Implementação de Aplicação

A produtividade dos utilizadores em dispositivos móveis é frequentemente impulsionada por aplicações.

O Windows 10 permite desenvolver aplicações que funcionem perfeitamente em vários dispositivos utilizando a Plataforma Universal windows (UWP) para aplicações windows.

Existem várias formas de implementar aplicações para dispositivos HoloLens 2. As aplicações podem ser implementadas diretamente através do MDM, a Microsoft Store for Business, ou sideloaded através de um pacote de provisionamento. Consulte a documentação de implementação da [aplicação](https://docs.microsoft.com/hololens/app-deploy-overview) para mais detalhes.

> [!NOTE]
> HoloLens 2 suporta apenas o funcionamento de aplicações UWP ARM64.

## <a name="maintain"></a>Manter

Nos ambientes de TI empresariais, a necessidade de segurança e controlo de custos deve ser equilibrada contra o desejo de fornecer aos utilizadores as tecnologias mais recentes. Uma vez que os ciberataques se tornaram uma ocorrência diária, é importante manter adequadamente o estado dos seus dispositivos Windows 10. A TI precisa de controlar as definições de configuração, impedindo-as de sair da conformidade, bem como impor quais os dispositivos que podem aceder a aplicações internas. O HoloLens 2 oferece as capacidades de gestão de operações móveis necessárias para garantir que os dispositivos estão em conformidade com a política corporativa.

### <a name="os-servicing-options"></a>Opções de manutenção do OS

**Um processo de atualização simplificado**

A Microsoft tem dinamizado o ciclo de engenharia e lançamento de produtos Windows para que novas funcionalidades, experiências e funcionalidades exigidas pelo mercado possam ser entregues mais rapidamente do que nunca. A Microsoft planeia entregar duas Atualizações de Funcionalidades por ano (período de 12 meses). **As Atualizações de Recursos** estabelecem um Ramo Atual ou CB e têm uma versão associada.

A Microsoft também irá fornecer e instalar atualizações para segurança e estabilidade diretamente para dispositivos HoloLens 2. Estas **Atualizações de Qualidade** , lançadas sob o controlo da Microsoft através do Windows Update, estão disponíveis mensalmente. O HoloLens 2 consome atualizações de funcionalidades e atualizações de qualidade como parte do mesmo processo de atualização padrão.

Os clientes empresariais podem gerir a experiência e processo de atualização em HoloLens 2s usando um sistema MDM. Na maioria dos casos, as políticas de gestão do processo de atualização aplicar-se-ão tanto às atualizações de funcionalidades como à qualidade. Mais detalhes na [configuração do MDM para atualizações hololens](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="managing-applications"></a>Gestão de Aplicações

Os administradores de TI podem controlar quais as aplicações que podem ser instaladas nos HoloLens 2 e como devem ser mantidas atualizadas.

O HoloLens 2 suporta o [Controlo de Aplicações do Windows Defender (WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)que permite aos administradores criar, permitir ou não permitir listas de aplicações a partir da Microsoft Store. Esta capacidade estende-se também a aplicações integradas. A capacidade de permitir ou negar aplicações ajuda a garantir que as pessoas usam os seus dispositivos para os fins a que se destinam. No entanto, nem sempre é uma abordagem fácil encontrar um equilíbrio entre o que os colaboradores precisam ou solicitam e questões de segurança. A criação de listas de permitir ou despromudê-los também requer manter-se com o cenário de aplicações em mudança na Microsoft Store.

Para mais detalhes, consulte [o Controlo de Aplicações CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### <a name="retire"></a>Extinguir

A reforma do dispositivo é a última fase do ciclo de vida do dispositivo. É&#39;importante que os dispositivos que estão a ser substituídos por modelos mais recentes sejam retirados de forma segura, uma vez que não&#39;que nenhum dado da empresa permaneça em dispositivos descartados que possam comprometer a confidencialidade dos seus dados. A TI também precisa de uma forma de suportar adequadamente os utilizadores que necessitem de limpar dispositivos que são perdidos ou roubados.

HoloLens 2 suporta 3 métodos de limpeza do dispositivo

**Limpeza da fábrica de MDM:** Repõe os HoloLens 2 de volta à imagem de fábrica através do comando MDM iniciado pelo administrador. Apaga todos os dados armazenados no dispositivo.

**Reposição do dispositivo a partir de definições:** Os utilizadores finais podem reiniciar manualmente o HoloLens 2 dentro da aplicação Definições do dispositivo. Apaga todos os dados armazenados no dispositivo.

**Companheiro de Recuperação Avançada (ARC):** A partir de um PC que executa a ferramenta ARC, um utilizador ou administrador pode piscar um HoloLens 2 ligado ao PC através do cabo USB. Apaga todos os dados armazenados no dispositivo.

> [!div class="nextstepaction"]
> [Cenários comuns de implantação](common-scenarios.md)
