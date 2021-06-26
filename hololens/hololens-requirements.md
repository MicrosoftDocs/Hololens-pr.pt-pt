---
title: Planeamento holoLens 2 implantação em ambiente comercial
description: Saiba mais sobre a implementação e gestão de HoloLens em ambientes empresariais, incluindo infraestruturas, Diretório Ativo Azure e gestão de dispositivos móveis.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924609"
---
# <a name="common-deployment-scenarios"></a>Cenários comuns de implantação

## <a name="overview"></a>Descrição Geral

Esta página fornece uma visão geral de arquitetura de alto nível para três cenários comuns ao implementar e gerir dispositivos Microsoft HoloLens 2 dentro da empresa.

Muitas vezes, a forma como gere os seus dispositivos e acede aos recursos da sua organização é em grande parte determinada por fatores já em vigor. Com base na sua infraestrutura existente, convidamo-lo a rever o estilo comum de gestão de dispositivos (MDM) nos seguintes cenários e depois ler [o Planeamento holoLens 2 implementações em ambiente comercial](hololens-core-components.md) para determinar que cenário corresponde às suas necessidades. Existem também três guias correspondentes disponíveis para utilização durante a sua implantação.


 1. [Guia de implementação de ambiente conectado com nuvem](hololens2-cloud-connected-overview.md)
     1. [Guia de implementação de ambiente conectado em nuvem (clientes externos)](hololens2-deployment-guide.md)
 1. [Guia de implementação de rede corporativa](hololens2-corp-connected-overview.md)
 1. [Guia de implementação de ambiente seguro offline](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Cenário A: Implementar para dispositivos ligados à nuvem

Este cenário é comparável à implementação de dispositivos móveis geridos dentro de uma empresa. HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa. Os recursos corporativos não são acedidos ou podem ser limitados através da VPN. 
 * Configurações comuns básicas
   * Wi-Fi redes estão normalmente totalmente abertas aos serviços da Internet e da Cloud.
   * Azure AD Junte-se à Gestão de Dispositivos Móveis (MDM) Inscrição automática--MDM (Intune) Gerido
   * Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)
     * Utilizadores únicos ou múltiplos por dispositivo suportado
   * Níveis variados de configurações de bloqueio do dispositivo são aplicados com base em casos de utilização específicos, desde o Quiosque de Aplicações Totalmente Abertos a Single App.
   * Uma ou mais aplicações são implementadas via MDM

* Desafios Comuns
   * Determinar quais as configurações do MDM a aplicar aos HoloLens 2 com base nos requisitos do cenário.

[![Cenário Um diagrama ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

O guia ligado à Cloud correspondente cobre como inscrever hololes 2 na gestão do seu dispositivo, aplicar licenças conforme necessário e validar que os seus utilizadores finais são capazes de utilizar imediatamente o Remote Assist após a configuração do dispositivo. Utilize o guia de Clientes Externos para implantar dispositivos num local remoto para utilização externa a curto ou longo prazo.

> [!div class="nextstepaction"]
> [Guia de implementação de ambiente conectado com nuvem](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Guia de implementação de ambiente conectado em nuvem (clientes externos)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Cenário B: Implementar dentro da rede da sua organização

Este cenário é idêntico a uma versão clássica para a maioria dos PCs do Windows 10. O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos. Os serviços de internet e nuvem podem ser limitados. 

 * Configurações comuns básicas
   * Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado aos serviços de internet ou Cloud.
   * Azure AD Junte-se à Inscrição Automática do MDM
   * MDM (Intune) Gerido
   * Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)
     * Utilizadores únicos ou múltiplos por dispositivo suportado
   * Níveis variados de configurações de bloqueio do dispositivo são aplicados com base em casos de utilização específicos, desde o Quiosque de Aplicações Totalmente Abertos a Single App.
   * Uma ou mais aplicações são implementadas via MDM

 * Desafios Comuns
   * HoloLens 2 não suporta em instalações ad join ou SCCM. Apenas a Azure AD se junta ao MDM. Muitas empresas ainda hoje implementam PCs windows 10 neste cenário como em dispositivos de ad de instalações, geridos pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerir dispositivos internos do Windows 10 através de soluções MDM baseadas na nuvem.
   * Como o HoloLens 2 é um primeiro dispositivo em nuvem, depende fortemente de serviços ligados à internet e cloud para autenticação do utilizador, atualizações de SISTEMA, gestão de MDM, e assim por diante. Ao ligar-se a uma rede corporativa, as regras Proxy/Firewall provavelmente terão de ser ajustadas para permitir o acesso aos HoloLens 2 e às aplicações que nela funcionam.
   * A conectividade Wi-Fi corporativa normalmente requer certificados para autenticar o dispositivo ou o utilizador para a rede. A infraestrutura ou configurações necessárias para a implementação de certificados para dispositivos Windows 10 através do MDM podem ser desafiantes para configurar.

[Diagrama do cenário ![ ](images/deployment-guides-revised-scenario-b-01-1.png) B1 ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[Diagrama do cenário ![ ](images/deployment-guides-revised-scenario-b-02-1.png) B2 ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

O guia de rede Corporativo correspondente instrui sobre como inscrever hololens 2 na sua gestão de dispositivos existente, aplicar licenças conforme necessário, e validar que os seus utilizadores finais são capazes de operar um Guia Dynamics 365, bem como usar a linha personalizada de aplicações empresariais, após a configuração do dispositivo.

> [!div class="nextstepaction"]
> [Guia de implementação de rede corporativa](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Cenário C: Implementar em ambiente offline seguro

Esta é uma implementação típica para locais altamente seguros ou confidenciais. HoloLens 2 é implantado para uso principalmente offline sem rede ou acesso à internet. 
 * Configurações comuns básicas
   * Wi-Fi conectividade é desativada. Se necessário, o Ethernet via USB pode ser ativado para a conectividade LAN.
   * Não consegui.
   * Conta de utilizador local para o sômin do dispositivo.
     * HoloLens 2 suporta apenas uma conta local.
   * Níveis variados de configurações de bloqueio do dispositivo são aplicados através de Pacotes de Provisionamento com base em casos de utilização específicos. Estas configurações são normalmente restritas devido a requisitos ambientais seguros.
   * Uma ou mais aplicações são implementadas através do Pacote de Provisionamento

 * Desafios Comuns
   * Há um conjunto limitado de configurações disponíveis através de Pacotes de Provisionamento
   * Os serviços em nuvem não são capazes de ser usados, limitando assim as capacidades hololens 2.
   * Sobrecarga administrativa mais elevada, uma vez que estes dispositivos têm de ser configurados, configurados e atualizados manualmente.

[![Diagrama de segurança offline 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

O guia de segurança offline correspondente fornece instruções para a aplicação de uma amostra de pacote de provisionamento que bloqueie um HoloLens 2 para utilização em ambientes seguros.

> [!div class="nextstepaction"]
> [Guia de implementação de ambiente seguro offline](hololens-common-scenarios-offline-secure.md)


