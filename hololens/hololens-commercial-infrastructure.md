---
title: Orientações sobre infraestruturas para HoloLens
description: Conheça as diretrizes de infraestrutura para dispositivos HoloLens, incluindo suporte à rede sem fios, assistência remota e gestão de dispositivos móveis.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9b306b10ff82603fd238f195beacc300f1a82bf6
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859005"
---
# <a name="configure-your-network-for-hololens"></a>Configure a sua rede para HoloLens

Esta parte do documento requer as seguintes pessoas:

1. Administração de rede com permissões para estois para fazer alterações no proxy/firewall
2. Azure Active Directory Administrador
3. Administrador de Dispositivos Móveis

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura

HoloLens é, no fundo, um Windows dispositivo móvel integrado ao Azure.  Funciona melhor em ambientes comerciais com disponibilidade de rede sem fios (wi-fi) e acesso a serviços Microsoft.

Os serviços de nuvem crítica incluem:

- Diretório ativo Azure (Azure AD)
- Windows Atualização (WU)

Os clientes comerciais precisarão de uma infraestrutura de gestão da mobilidade empresarial (EMM) ou de gestão de dispositivos móveis (MDM) para gerir HoloLens dispositivos em escala.  Este guia utiliza [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) como exemplo, embora qualquer fornecedor com suporte total para a Microsoft Policy possa suportar HoloLens.  Pergunte ao seu fornecedor de gestão de dispositivos móveis se eles suportam HoloLens 2.

HoloLens suporta um conjunto limitado de experiências desligadas em nuvem.

### <a name="wireless-network-eap-support"></a>Suporte eAP de rede sem fios

- PEAP-MS-CHAPV2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens Requisitos específicos da rede

Certifique-se de que [esta lista](hololens-offline.md) de pontos finais é permitida na sua firewall de rede. Isto permitirá que HoloLens funcionem corretamente.

### <a name="remote-assist-specific-network-requirements"></a>Requisitos de rede específico de assistência remota

1. A largura de banda recomendada para um melhor desempenho do Remote Assist é de 1,5Mbps. Consulte os [requisitos de rede detalhados](/MicrosoftTeams/prepare-network) para obter informações adicionais.
**(Por favor, note que se não tiver velocidades de rede de pelo menos 1,5Mbps, o Remote Assist continuará a funcionar. No entanto, a qualidade pode sofrer).**
1. Certifique-se de que estas portas e URLs são permitidos na sua firewall de rede para permitir que Microsoft Teams funcionem. Mantenha-se atualizado com a [última lista de portos.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- Saiba mais sobre os [requisitos específicos da rede para assistência remota.](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements) 
- Saiba mais sobre como preparar a [rede da sua organização para Microsoft Teams](/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Guia requisitos específicos de rede

Os guias apenas requerem acesso à rede para descarregar e usar a aplicação.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory Orientação

> [!NOTE]
> Este passo só é necessário se a sua empresa planeia gerir o HoloLens.

1. Certifique-se de que tem uma Licença AD Azure.
Por [favor, HoloLens requisitos de licenças](hololens-licenses-requirements.md) para obter informações adicionais.

1. Se planeia utilizar a Inscrição Automática, terá de configurar a [inscrição Azure AD.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Certifique-se de que os utilizadores da sua empresa estão em Azure Ative Directory (Azure AD).
Consulte as [seguintes instruções](/azure/active-directory/fundamentals/add-users-azure-active-directory) para adicionar os utilizadores.

1. Sugerimos que os utilizadores que precisam de licenças semelhantes sejam adicionados ao mesmo grupo.
    1. [Criar um Grupo](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Adicionar utilizadores a grupos](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Certifique-se de que os utilizadores da sua empresa (ou grupo de utilizadores) recebem as licenças necessárias.
Se precisar de atribuir licenças, siga estas [instruções.](/azure/active-directory/fundamentals/license-users-groups)

1. Só faça este passo se se espera que os utilizadores inscrevam o seu dispositivo HoloLens/Mobile em si (Existem três opções) Estes passos garantem que os utilizadores da sua empresa (ou um grupo de utilizadores) podem adicionar dispositivos.
    1. **Opção 1:** Dê permissão a todos os utilizadores para se juntarem a dispositivos ao Azure AD.
**Inscreva-se no portal Azure como administrador**  >  **Azure Ative Directory**  >  **Dispositivos**  >  **Definições do dispositivo**  >
 **Definir Utilizadores podem juntar dispositivos para Azure AD a *Todos***

    1. **Opção 2:** Dar aos utilizadores/grupos selecionados permissão para juntar dispositivos para Azure AD **Iniciar sação no portal Azure como administrador**  >  **Azure Ative Directory** dispositivo dispositivo de  >  **dispositivos**  >  **Definições**  >
 **Utilizadores definidos podem juntar dispositivos para Azure AD a imagem *selecionada*** 
 ![ que mostra Configuração de Dispositivos AD AD Azure](images/azure-ad-image.png)

    1. **Opção 3:** Pode impedir que todos os utilizadores juntem os seus dispositivos ao domínio. Isto significa que todos os dispositivos terão de ser matriculados manualmente.

## <a name="mobile-device-manager-guidance"></a>Orientação do gestor de dispositivos móveis

### <a name="ongoing-device-management"></a>Gestão contínua de dispositivos

> [!NOTE]
> Este passo só é necessário se a sua empresa planeia gerir o HoloLens.

A gestão contínua de dispositivos dependerá da sua infraestrutura de gestão de dispositivos móveis.  A maioria tem a mesma funcionalidade geral, mas a interface do utilizador pode variar muito.

1. [O CSPs (Fornecedores de Serviços de Configuração)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) permite criar e implementar definições de gestão para os dispositivos da sua rede. Consulte a [lista de HoloLens CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) para referência.

1. [As políticas de conformidade](/intune/device-compliance-get-started) são regras e configurações que os dispositivos devem cumprir para serem compatíveis com a sua infraestrutura corporativa. Utilize estas políticas com Acesso Condicional para bloquear o acesso aos recursos da empresa para dispositivos que não estejam em conformidade. Por exemplo, pode criar uma política que exija que o Bitlocker esteja ativado.

1. [Criar Política de Conformidade](/intune/protect/compliance-policy-create-windows).

1. O Acesso Condicional permite/nega dispositivos móveis e aplicações móveis a partir do acesso aos recursos da empresa. Dois documentos que poderá achar úteis são [planear a sua implantação](/azure/active-directory/conditional-access/plan-conditional-access) e [boas práticas.](/azure/active-directory/conditional-access/best-practices)

1. [Este artigo](/intune/fundamentals/windows-holographic-for-business) fala sobre as ferramentas de gestão da Intune para HoloLens.

1. [Criar um perfil de dispositivo](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Gerir atualizações

O Intune inclui uma funcionalidade chamada Update rings for Windows 10 devices, incluindo HoloLens 2 e HoloLens v1 (com Holographic for Business). Os anéis de atualização incluem um grupo de definições que determinam como e quando as atualizações são instaladas.

Por exemplo, pode criar uma janela de manutenção para instalar atualizações ou pode optar por reiniciar após as atualizações serem instaladas.  Também pode optar por interromper indefinidamente as atualizações até estar pronto para atualizar.

Leia mais sobre [a configuração dos anéis de atualização com o Intune](/intune/windows-update-for-business-configure).

### <a name="application-management"></a>Gestão de aplicações

Gerir HoloLens aplicações através de:

1. Loja Microsoft  
  O Microsoft Store é a melhor forma de distribuir e consumir aplicações na HoloLens.  Existe um grande conjunto de aplicações de HoloLens já disponíveis na loja ou pode publicar as [suas próprias.](/windows/uwp/publish/)  
  Todas as aplicações na loja estão disponíveis publicamente para todos, mas se não for aceitável, o check-out da Microsoft Store para Empresas.  

1. [Loja Microsoft para Empresas](/microsoft-store/)  
  Microsoft Store para Empresas e Educação é uma loja personalizada para o seu ambiente corporativo.  Permite-lhe usar o Microsoft Store incorporado em Windows 10 e HoloLens para encontrar, adquirir, distribuir e gerir apps para a sua organização.  Também permite implementar aplicações específicas para o seu ambiente comercial, mas não para o mundo.

1. Implementação e gestão de aplicações via Intune ou outra solução de gestão de dispositivos móveis  
  A maioria das soluções de gestão de dispositivos móveis, incluindo a Intune, fornecem uma forma de implementar uma linha de aplicações empresariais diretamente para um conjunto de dispositivos matriculados.  Consulte este artigo para [instalar aplicações Intune.](/intune/apps-deploy)

1. _não recomendado_ Portal do Dispositivo  
  As aplicações também podem ser instaladas no HoloLens utilizando diretamente o Portal do Dispositivo Windows.  Isto não é recomendado, uma vez que o Modo de Desenvolvimento tem de ser ativado para utilizar o portal do dispositivo.

Leia mais sobre [a instalação de aplicações no HoloLens.](hololens-install-apps.md)

### <a name="certificates"></a>Certificados

Pode distribuir certificados através do seu fornecedor DEDM. Se a sua empresa necessitar de certificados, a Intune suporta PKCS, PFX e SCEP. É importante entender qual o certificado certo para a sua empresa. Visite a documentação das [configurações](/intune/protect/certificates-configure) do certificado para determinar qual o cert que é o melhor para si. Se pretender utilizar certificados para HoloLens Autenticação, PFX ou SCEP pode ser adequado para si.

Consulte os seguintes passos para a utilização [do SCEP](/intune/protect/certificates-profile-scep).

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Como fazer upgrade para Holographics para Business Commercial Suite

> [!NOTE]
> Windows A Holographics for Business (suite comercial) destina-se apenas a dispositivos de 1ª geração HoloLens. O perfil não será aplicado a HoloLens 2 dispositivos.

Você pode encontrar direções para upgrade para a suíte comercial na documentação [de upgrade holográfico.](/intune/configuration/holographic-upgrade)

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Como configurar o modo quiosque usando Microsoft Intune

1. Sincronizar Microsoft Store a Intune (Ver as [seguintes instruções).](/intune/apps/windows-store-for-business)

1. Verifique as definições da sua aplicação
    1. Inicie sessão na sua conta Microsoft Store Negócios
    1. **Gerir > Produtos e Serviços > Aplicações e > de Software Selecione a aplicação que pretende sincronizar > Disponibilidade de Lojas Privadas > Selecione "Todos" ou "Grupos Específicos"**
        >[!NOTE]
        >Se não vir a app que pretende, terá de "obter" a aplicação procurando na loja a sua aplicação. **Clique na barra "Search" no canto superior direito > tipo no nome da aplicação > clicar na aplicação > selecionar "Get".**
    1. Se não vir as suas apps no **Intune > aplicações de > aplicações** do cliente, poderá ter de [sincronizar novamente as suas aplicações.](/intune/apps/windows-store-for-business#synchronize-apps)

1. [Criar um perfil de dispositivo para o modo quiosque](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Pode configurar diferentes utilizadores para terem diferentes experiências do Modo Quiosque utilizando o "Azure AD" como o "tipo de início de súprico do utilizador". No entanto, esta opção apenas está disponível no modo quiosque Multi-App. O modo quiosque multi-App funcionará com apenas uma aplicação, bem como com várias aplicações.

![Imagem que mostra configuração do modo quiosque em Intune](images/aad-kioskmode.png)

Para outros serviços de MDM, consulte a documentação do seu fornecedor para obter instruções. Consulte as instruções [de quiosque HoloLens](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) se precisar de utilizar uma configuração personalizada e uma configuração XML completa para configurar um quiosque no seu serviço MDM.

## <a name="certificates-and-authentication"></a>Certificados e Autenticação

Os certificados podem ser implantados através do seu MDM (ver "certificados" na [secção MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) Os certificados também podem ser distribuídos para o HoloLens através do fornecimento de pacotes. Consulte [HoloLens Provisioning](hololens-provisioning.md) para obter informações adicionais.

### <a name="additional-intune-quick-links"></a>Ligações rápidas intune adicionais

1. [Criar Perfis:](/intune/configuration/device-profile-create) Os perfis permitem-lhe adicionar e configurar definições que serão empurradas para os dispositivos da sua organização.

