---
title: Visão geral da Cloud conectada HoloLens 2 com Assistência Remota
description: Saiba como inscrever os dispositivos HoloLens 2 através de uma rede Cloud Connected utilizando o Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378484"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guia de Implementação - HoloLens ligado à nuvem 2 com Assistência Remota – Visão geral

Este guia ajuda os profissionais de TI a planear e implementar dispositivos Microsoft HoloLens 2 para a sua organização com o objetivo geral de ter esses dispositivos em nuvem ligados à sua organização com o Dynamics 365 Remote Assist prontos a usar. Tenha em mente que este servirá como um modelo para implementações de prova de conceito para a sua organização em vários casos de utilização hololens 2.

Durante o guia, iremos cobrir como inscrever os seus dispositivos na gestão do dispositivo, aplicar licenças conforme necessário e validar que os seus utilizadores finais podem utilizar imediatamente o Remote Assist após a configuração do dispositivo. Para isso, iremos analisar as importantes peças de infraestrutura necessárias para se instalar e funcionar – conseguindo a implantação em escala com hololens 2.

[![Cenário conectado à ](./images/deployment-guides-revised-scenario-a.png) nuvem](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>Neste Guia

Este guia tem como objetivo específico a criação de Assistência Remota dentro da sua organização nos seus dispositivos HoloLens. Cobriremos as necessidades necessárias para atingir esse objetivo. De forma a manter o foco neste objetivo, determinadas preparações e configurações serão pré-selecionadas de forma a otimizar esta implementação ou reduzir os itens necessários à configuração. Você será informado destas escolhas, e pode personalizar a sua implementação com base nas necessidades do seu negócio.

Esta é uma configuração semelhante ao [cenário A: Implementar para dispositivos de ligação em nuvem](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), que é uma boa opção para muitas implementações de Prova de Conceito, que incluirá:

- Wi-Fi redes estão tipicamente totalmente abertas aos serviços da Internet e cloud
- Azure AD Junte-se à Inscrição automática do MDM -- MDM (Intune) Gerido
- Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)
  - Utilizadores únicos ou múltiplos por dispositivo suportado
- Níveis variados de configurações de bloqueio de dispositivos são aplicados com base em casos de utilização específico, de Quiosque de Aplicações Totalmente Abertos a Únicos



Nenhuma outra restrição ou configurações do dispositivo será aplicada neste guia, no entanto encorajamos-o a explorar essas opções após o acabamento.

## <a name="learn-about-remote-assist"></a>Saiba mais sobre assistência remota

O Remote Assist permite a manutenção e reparação colaborativa, inspeção remota, bem como partilha e formação de conhecimentos. Ao ligar pessoas em diferentes funções e locais, um técnico que usa o Remote Assist pode ligar-se a um colaborador remoto nas Equipas microsoft. Podem combinar vídeo, imagens e anotações para resolver problemas em tempo real, mesmo quando são&#39;não no mesmo local. Os colaboradores remotos podem inserir imagens de referência, esquemas e outras informações úteis que o técnico&#39;espaço físico para que possam consultar o esquema enquanto trabalham heads-up e mãos-livres nos HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>Neste guia:

Preparar:

> [!div class="checklist"]
> - [Conheça o essencial da infraestrutura para dispositivos HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Saiba mais sobre o Azure AD e crie um se não&#39;o tiver.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Saiba mais sobre a gestão de identidade e como configurar melhor as contas AD da Azure.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Saiba mais sobre o MDM e prepare-se com o Intune se não&#39;já não tenha um pronto.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Conheça os requisitos de networking do Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Opcionalmente: VPN para ligar aos recursos organizacionais](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configure:

> [!div class="checklist"]
> - [Como criar Utilizadores e Grupos.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Como configurar a inscrição automática dentro do Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Como atribuir as suas licenças de inscrição.](hololens2-cloud-connected-configure.md#application-licenses)

Implementação:

> [!div class="checklist"]
> - [Configurar os hololens 2 e validar a inscrição.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Valide que pode esporar uma chamada de Assistência Remota.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Manter:

> [!div class="checklist"]
> - [Como atualizar o Remote Assist utilizando a aplicação Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [A fazer um plano de apoio.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plano de desenvolvimento.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Passo seguinte

> [!div class="nextstepaction"]
> [Implementação ligada à nuvem - Prepare-se](hololens2-cloud-connected-prepare.md)

