---
title: Visão geral da Nuvem conectada HoloLens 2 com Assistência Remota
description: Saiba como inscrever HoloLens 2 dispositivos através de uma rede Cloud Connected utilizando o Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635131"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guia de Implementação - Cloud conectado HoloLens 2 com Assistência Remota – Visão Geral

Este guia ajudará os profissionais de TI a planear e implementar Microsoft HoloLens 2 dispositivos com Assistência Remota à sua organização. Isto servirá como um modelo para implementações de prova de conceito para a sua organização em vários casos de HoloLens 2. A configuração é semelhante ao [cenário A: Implementar para dispositivos de ligação em nuvem](https://docs.microsoft.com/hololens/common-scenarios#scenario-a). 

Durante o guia, iremos cobrir como inscrever os seus dispositivos na gestão do seu dispositivo, aplicar licenças conforme necessário e validar que os seus utilizadores finais são capazes de utilizar imediatamente o Remote Assist após a configuração do dispositivo. Para isso, vamos analisar as importantes infraestruturas necessárias para se instalar e funcionar – conseguir a implantação em escala com HoloLens 2. Nenhuma outra restrição ou configurações do dispositivo será aplicada neste guia, no entanto, encorajamos-o a explorar essas opções após o acabamento.

## <a name="prerequisites"></a>Pré-requisitos

Devem estar em vigor as infraestruturas que se seguem para implantar o HoloLens 2. Caso contrário, a criação de Azure e Intune está incluída neste guia:

Esta é uma configuração semelhante ao [cenário A: Implementar para dispositivos de ligação em nuvem](/hololens/common-scenarios#scenario-a), que é uma boa opção para muitas implementações de Prova de Conceito, que incluirá:

- Wi-Fi redes estão tipicamente totalmente abertas aos serviços da Internet e cloud
- Azure AD Junte-se à Inscrição automática do MDM -- MDM (Intune) Gerido
- Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)
    - É suportado um único ou múltiplo por dispositivo.

:::image type="content" alt-text="Cenário conectado à nuvem" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Saiba mais sobre assistência remota

O Remote Assist permite a manutenção e reparação colaborativa, inspeção remota, bem como partilha e formação de conhecimentos. Ao ligar pessoas em diferentes funções e locais, um técnico que usa Assistência Remota pode ligar-se a um colaborador remoto em Microsoft Teams. Podem combinar vídeo, imagens e anotações para resolver problemas em tempo real, mesmo quando são&#39;não no mesmo local. Os colaboradores remotos podem inserir imagens de referência, esquemas e outras informações úteis que o técnico&#39;espaço físico para que possam consultar o esquema enquanto trabalham no heads-up e mãos-livres no HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Licenciamento e Requisitos de Assistência Remota

- Conta AZURE AD (necessária para a aquisição da subscrição e atribuição de licenças)
- [Subscrição de Assistência Remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [Ensaio de Assistência Remota)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist utilizador

- Licença de Assistência Remota
- Conectividade da rede

#### <a name="microsoft-teams-user"></a>Microsoft Teams utilizador

- Microsoft Teams ou [Teams Freemium.](https://products.office.com/microsoft-teams/free)
- Conectividade de rede

Se planeia implementar este [cenário de inquilinos cruzados,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)poderá necessitar de uma licença de Barreiras de Informação. Consulte [este artigo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se é necessária uma Licença de Barreira de Informação.

## <a name="in-this-guide-you-will"></a>Neste guia:

Preparar:

> [!div class="checklist"]
> - [Conheça os elementos essenciais da infraestrutura para HoloLens 2 dispositivos.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Saiba mais sobre o Azure AD e crie um se não&#39;o tiver.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Saiba mais sobre a gestão de identidade e como configurar melhor as contas AD da Azure.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Saiba mais sobre o MDM e prepare-se com o Intune se não&#39;já não tenha um pronto.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Conheça os requisitos de networking do Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Opcionalmente: VPN para ligar aos recursos organizacionais](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configure:

> [!div class="checklist"]
> - [Como criar Utilizadores e Grupos.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Como configurar a inscrição automática dentro do Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Como atribuir as suas licenças de inscrição.](hololens2-cloud-connected-configure.md#application-licenses)

Implementação:

> [!div class="checklist"]
> - [Crie o seu HoloLens 2 e valide a inscrição.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Valide que pode esporar uma chamada de Assistência Remota.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Manter:

> [!div class="checklist"]
> - [Como atualizar o Remote Assist utilizando a aplicação Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [A fazer um plano de apoio.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plano de desenvolvimento.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Passo seguinte

> [!div class="nextstepaction"]
> [Implementação ligada à nuvem - Prepare-se](hololens2-cloud-connected-prepare.md)

