---
title: Visão geral - Gestão de Aplicações
description: Começa com uma visão geral da gestão de aplicações de realidade mista com a gestão de dispositivos móveis, loja da Microsoft para negócios e pacotes de provisionamento.
keywords: HoloLens, utilizador, conta, app, gestão de aplicações,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033063"
---
# <a name="app-management-overview"></a>Gestão de Aplicativos: Visão geral

Pode implementar aplicações em quatro caminhos diferentes: **Mobile Device Management (MDM)**, **Microsoft Store para Empresas**, **Microsoft Store**, ou instalando-as através **do Provisioning**.

## <a name="mobile-device-management-mdm"></a>Gestão de Dispositivos Móveis (MDM)

Uma solução MDM permite que os decisores e administradores de TI instalem (empurrem) as suas aplicações internamente, linha de negócios ou comprem aplicações através da loja para um grupo de utilizadores. HoloLens dispositivos funcionam melhor com Microsoft Endpoint Manager (Intune) para [gestão de aplicações.](app-deploy-intune.md) A Intune também oferece aos utilizadores um controlo mais fino sobre aplicações geridas por TI através da experiência Portal da Empresa transferível.

> [!NOTE]
> As seguintes instruções são para os utilizadores que pretendam gerir as suas aplicações com o Intune. A Microsoft recomenda a utilização do Intune para a gestão de aplicações e dispositivos.

A Gestão de Dispositivos Móveis (MDM) é aplicável para:

* MDM implantado + Portal da Empresa
* Aplicativos line of Business (não públicos)
* Instalação manual de aplicações disponíveis através de Portal da Empresa
* Administração empurra através da política do MDM
* Atualização automática através do MDM

## <a name="microsoft-store-for-business"></a>Loja Microsoft para Empresas

O [Microsoft Store para Empresas](app-deploy-store-business.md) fornece aos decisores e administradores de TI nas empresas para encontrar, adquirir, gerir e distribuir aplicações gratuitas e pagas. Os administradores de TI podem gerir Microsoft Store aplicações e aplicações privadas de linha de negócios num único inventário, além de atribuir e reutilizar licenças conforme necessário. Para mais informações, visite [Pré-requisitos para a utilização do Microsoft Store para Empresas](/microsoft-store/prerequisites-microsoft-store-for-business).

O Microsoft Store para Empresas é aplicável para:

* Aplicativos públicos ou de linha de negócios
* Instalação automática de aplicações necessárias através da associação MDM
* Utilizador descarrega manualmente apps
* Atualização automática

## <a name="microsoft-store-apps"></a>Aplicações da Loja Microsoft

O Microsoft Store fornece aos decisores e administradores de TI nas empresas para encontrar, adquirir, gerir e distribuir aplicações públicas.

Esta Microsoft Store é aplicável para:

* Apenas aplicações públicas
* Utilizador descarrega manualmente apps
* Atualização automática se estiver ligado à Internet

Para mais informações, visite [as Aplicações da Loja Holográfica.](/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>Instalar através de Pacotes de Provisionamento

[O Provisioning Packages](app-deploy-provisioning-package.md) permite instalar aplicações personalizadas ou de Linha de Negócios, permitindo que profissionais e administradores de TI instalem rapidamente aplicações num(s) dispositivo(s) local via USB. Esta instalação pode ser feita sem ligação à Internet e para qualquer tipo de identidade.

A instalação através de Pacotes de Provisionamento é aplicável para:

* Linha de aplicações de Negócios / Auto-desenvolvidas (não públicas)
* Aplicativos públicos (se o instalador offline estiver disponível)
* Apenas carregamento lateral USB
* Nenhuma atualização automática (requer atualizações manuais através do Pacote de Provisionamento)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Instale apps no HoloLens 2 através do Instalador de Aplicações

A utilização do [App Installer](app-deploy-app-installer.md) pode ter uma experiência simples de instalar apps em dispositivos locais ou partilhar uma aplicação com outra pessoa que não esteja familiarizada com outros métodos de instalação de aplicações em HoloLens. Isto pode ser feito sem necessidade de ativar o Modo de Desenvolvimento ou utilizar o Portal do Dispositivo. Este é um método simples de distribuir uma aplicação completamente construída. Independentemente de pretender simplesmente despromupro ser a sua app para outro utilizador com um HoloLens, ou se pretende implementar a sua app, este método funciona facilmente.

A instalação através do Instalador de Aplicações é aplicável para:

* Linha de Negócios / Self desenvolvido (não público) apps
* Apenas carga lateral
* Não requer modo de desenvolvimento ou portal do dispositivo
* Fácil de instalar o utilizador final
