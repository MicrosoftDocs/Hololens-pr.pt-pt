---
title: Guia de Implementação - HoloLens 2 conectado corporativo com Dinâmica 365 Guias - Visão geral
description: Saiba como inscrever HoloLens 2 dispositivos com Dinâmica 365 Guides sobre uma rede conectada corporativa.
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
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637018"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Guia de Implementação - Corporate Connected HoloLens 2 com Dinâmica 365 Guias - Visão geral

Este guia ajudará os profissionais de TI a planear e implementar Microsoft HoloLens 2 dispositivos com Guias Dinâmicos 365 (Guias) para a sua organização. Este guia é ótimo para pilotos, bem como implementações de produção e é semelhante ao Cenário B: Implementar dentro do guia [de rede da sua organização.](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) Depois de testar a sua prova de conceito, utilize este guia para avançar com a integração HoloLens na sua organização.

Neste guia, vamos cobrir como inscrever os seus dispositivos na gestão de dispositivos existentes, aplicar licenças conforme necessário, e validar que os seus utilizadores finais são capazes de operar um Guia Dinâmico 365, bem como usar a linha personalizada de aplicações empresariais, após a configuração do dispositivo. 

## <a name="prerequisites"></a>Pré-requisitos

As infraestruturas que se seguem já devem estar em vigor:
- Wi-Fi
    - Rede corporativa interna com acesso a recursos internos e acesso limitado aos serviços da Internet ou Cloud
    - Autenticação de certificados baseado em dispositivo.
- Azure Ative Directory (Azure AD) Junte-se à inscrição automática do MDM[(Azure AD P1](/azure/active-directory/fundamentals/active-directory-whatis) necessária)
- MDM (Intune) Gerido
    - Uma ou mais aplicações são implementadas via MDM.
- Rede 
    - Certificados (SCEP ou PKCS)
    - Configuração do proxy
- Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)
    - É suportado um único ou múltiplo por dispositivo.
- Níveis variados de configurações de bloqueio do dispositivo aplicados com base em casos de utilização específicos, desde o Quiosque de Aplicações Totalmente Abertos a Single App.

## <a name="guides-licensing-and-requirements"></a>[Guias licenciamento e requisitos](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Conta do Azure AD
- Dinâmica 365 Guias aplicações PC e HoloLens
- Assinatura dinâmica 365 guias
    - Microsoft Dataverse (incluído)
    - Power Apps (incluído)
- Power BI Desktop
- Conectividade da rede

[![Diagrama de rede ligado à corp, fase 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagrama de rede ligado à corp, fase 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>Neste guia:
### <a name="prepare"></a>Preparação
> [!div class="checklist"]
>- [Conheça os elementos essenciais da infraestrutura para HoloLens 2 dispositivos.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Saiba mais sobre o AZure AD e crie um se não o tiver.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Saiba mais sobre a gestão de identidade e como configurar melhor as contas AD da Azure.](hololens2-corp-connected-prepare.md#identity-management)
>- [Saiba mais sobre o MDM e prepare-se com o Intune se ainda não tiver um pronto.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Familiarize-se com Wi-Fi baseado em certificados.](hololens2-corp-connected-prepare.md#certificates)
>- [Familiarize-se com Proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Compreenda como pode usar a Linha de Aplicações Empresariais.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Saiba mais sobre como pode usar guias para a sua organização.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Configurar
> [!div class="checklist"]
>- [Como criar utilizadores e grupos.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Como configurar a Inscrição Automática.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Como configurar certificados e perfis Wi-Fi para a Conectividade Wi-Fi Corporativa.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Pacotes de aplicações upload e Assign Line of Business (LOB).](hololens2-corp-connected-configure.md#app-deployment)
>- [Configurar Dinâmicos 365 Guias.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Como configurar o modo quiosque (opcional).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Como configurar o WDAC (opcional).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Implementar
> [!div class="checklist"]
>-  [Validar a inscrição através do dispositivo e do MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Validar Wi-Fi certificados.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Validar a instalação da aplicação LOB.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Validar Guias através da autoria e funcionamento.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Manter
> [!div class="checklist"]
>- [Atualização HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Como atualizar Guias (aplicações de loja).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Como atualizar aplicações LOB.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Plano de desenvolvimento.](hololens2-corp-connected-maintain.md#development-plan) 
>- [A fazer um plano de apoio.](hololens2-corp-connected-maintain.md#support-plan)
>- [Opções de gestão de dispositivos.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Passo seguinte 
> [!div class="nextstepaction"]
> [Implementação conectada corporativa - Prepare-se](hololens2-corp-connected-prepare.md)
