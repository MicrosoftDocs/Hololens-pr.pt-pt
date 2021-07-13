---
title: Guia de implementação - Implementação HoloLens 2 ligada à nuvem em escala com assistência remota - Prepare
description: Saiba como se preparar para inscrever HoloLens dispositivos através de uma rede Cloud Connected utilizando diretório ativo azul e gestão de identidade.
keywords: HoloLens, gestão, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Device Management
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f747a2893ed3551e91a81bdbf5971deefbf6ce46
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637137"
---
# <a name="prepare---cloud-connected-guide"></a>Preparar - Guia ligado à nuvem

No final deste artigo terá configurado Azure AD, MDM, e entender mais sobre a utilização de contas AD AZure e requisitos de rede. Esta secção do guia irá ajudá-lo e a sua organização a preparar-se para implementar HoloLens 2 para a nuvem e utilizar o Dynamics 365 Remote Assist. Irá superar a importância de cada peça da sua infraestrutura, bem como fornecer links para guias para ajudá-lo a configurar essas peças conforme necessário.

## <a name="infrastructure-essentials"></a>Infraestruturas Essenciais

Para cenários de implantação pessoal e corporativo, um sistema MDM é a infraestrutura essencial necessária para implantar e gerir dispositivos Windows 10 Holographic. Uma subscrição premium Azure É recomendada como um fornecedor de identidade e necessária para suportar determinadas capacidades.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD é um serviço de diretório baseado na nuvem que fornece gestão de identidade e acesso. As organizações que usam Microsoft Office 365 ou Intune já estão a utilizar o Azure AD, que tem três edições: Grátis, Premium P1 e Premium P2 (ver [Azure Ative Directory edições](https://azure.microsoft.com/documentation/articles/active-directory-editions).) Todas as edições suportam o registo do dispositivo Azure AD, mas Premium P1 é necessário para permitir a inscrição automática do MDM que iremos utilizar neste guia mais tarde.

> [!IMPORTANT]
> É essencial ter um Azure Ative Directory uma vez que HoloLens dispositivos não suportam a ad adere no local. Se você não&#39;já tem um Azure Ative Directory configurado, vá para [criar um novo inquilino em Azure Ative Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Gestão de Identidades

Os colaboradores podem usar apenas uma conta para inicializar um dispositivo, pelo que&#39;é imperativo que a sua organização controle qual a conta ativada primeiro. A conta escolhida determinará quem controla o dispositivo e influencia as suas capacidades de gestão.

Neste guia escolhemos que para a [Identidade](/hololens/hololens-identity) utilizada utilizaremos contas AZURE AD, ou contas Azure Ative Directory. Existem vários benefícios para as contas AD Azure que gostaríamos de usar, tais como:

- Os colaboradores utilizam a sua conta Azure AD para registar o dispositivo em Azure AD e matriculam-no automaticamente na organização&#39;solução MDM (Azure AD+MDM – requer Azure AD Premium).
- As contas AD da AZure suportam [o Signo Único .](/azure/active-directory/manage-apps/what-is-single-sign-on) Quando um utilizador assinar no Remote Assist, a sua Identidade a partir do utilizador AD assinado no Azure será reconhecida e o utilizador será assinado na app para uma experiência simplificada.
- As contas AD da Azure têm [opções](/hololens/hololens-identity) de autenticação adicionais através [de Windows Hello para Negócios.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) Além do login da Iris, os utilizadores podem iniciar sessão a partir de outro dispositivo ou utilizar as teclas de segurança FIDO.

### <a name="mobile-device-management"></a>Gestão de Dispositivos Móveis

O Microsoft [Intune](/mem/intune/fundamentals/what-is-intune), parte do Enterprise Mobility + Security, é um sistema MDM baseado na nuvem que gere dispositivos ligados ao seu inquilino. Tal como Office 365, a Intune utiliza o Azure AD para a gestão de identidades, pelo que os colaboradores usam as mesmas credenciais para inscrever dispositivos no Intune que usam para assinar Office 365. A Intune também suporta dispositivos que executam outros sistemas operativos, como iOS e Android, para fornecer uma solução DEDM completa. Para efeitos deste guia,&#39;vamos focar-nos na utilização do Intune para permitir uma implantação em nuvem em escala com HoloLens 2.

> [!IMPORTANT]
> É essencial ter Gestão de Dispositivos Móveis. Se você não&#39;já não o tenha configurado siga este guia e [começar com Intune](/mem/intune/fundamentals/free-trial-sign-up).

> [!NOTE]
> Vários sistemas mDM suportam Windows 10 e a maioria suporta cenários de implementação de dispositivos pessoais e corporativos. Os fornecedores de MDM que suportam Windows 10 Holographic atualmente incluem: AirWatch, MobileIron, entre outros. A maioria dos fornecedores de MDM líderes da indústria já apoiam a integração com a Azure AD. Pode encontrar os fornecedores de MDM que suportam a Azure AD no [Azure Marketplace.](https://azure.microsoft.com/marketplace/)

## <a name="network"></a>Rede

Nesta configuração, antecipamos HoloLens 2 dispositivos que se conectam à Internet a partir de qualquer rede de Wi-Fi aberta disponível. Uma vez que um utilizador poderia ter de alterar a ligação de rede com base na localização, deve aprender a [ligar HoloLens dispositivos ao Wi-Fi.](/hololens/hololens-network)

Para a Dynamics 365 Remote Assist existem uma variedade de condições de rede, incluindo largura de banda, latência, nervosismo e perda de pacotes, que podem afetar a sua experiência de chamada de vídeo. Embora as chamadas de áudio e vídeo possam ser possíveis em ambientes com largura de banda reduzida, poderá experimentar uma degradação de recursos. Ao utilizar o Dynamics 365 Remote Assist em HoloLens aqui estão os requisitos da rede a ter em conta:

**Mínimo** : 1,5 Mbps para cima/para baixo é necessário para a chamada de vídeo de qualidade HD peer-to-peer com resolução de HD 1080p a 30 fps.

**Ideal:** Para a chamada de vídeo de qualidade hd peer-to-peer com resolução de HD 1080p, 4-5 Mbps para cima/para baixo deve ser esperado.

Mais Informações:

- [Requisitos de rede](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Recomendações de otimização de rede](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Opcional: Ligação o seu HoloLens à VPN

Os dispositivos que estão a ser ligados a este guia vão ligar-se à rede através da rede e da rede de nuvem externa. Pode ser que para aceder aos recursos da empresa que&#39;terá de ligar os seus dispositivos através da VPN. Existem várias formas diferentes de ligar os seus dispositivos à VPN, tanto onde o utilizador final pode ligar-se através da UI do dispositivo, ou os dispositivos podem ser geridos e receber o perfil VPN de um PPKG ou MDM. Como configurar a VPN ganhou&#39;não ser abrangida neste artigo, por isso, se&#39;gostaria de saber mais sobre os diferentes protocolos ou formas de gerir a VPN, visite [estes guias para obter informações sobre HoloLens e VPN.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>Passo seguinte

> [!div class="nextstepaction"]
> [Implementação ligada à nuvem - Configure](hololens2-cloud-connected-configure.md)
