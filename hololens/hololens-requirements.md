---
title: Cenários comuns de implantação
description: Saiba mais sobre a implementação e gestão de HoloLens em ambientes empresariais, incluindo infraestruturas, Azure Ative Directory e gestão de dispositivos móveis.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 5a4f251f3ca6eae5e85e4d763074e035039159cb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428760"
---
# <a name="common-deployment-scenarios"></a>Cenários comuns de implantação

## <a name="overview"></a>Descrição Geral

Descobrir como implementar um novo dispositivo pode ser uma luta quando se experimenta pela primeira vez. Aqui, partilhamos diferentes formas de implantar e gerir Microsoft HoloLens 2 dispositivos dentro da organização.

Quer soluções implantadas em escala. Queremos levá-lo lá. Vamos primeiro falar sobre os passos para implementar dispositivos, portanto hologramas, para obter valor para o seu cenário de realidade mista alvo, quer esteja a usar D365 Remote Assist, Guides, ou uma aplicação ativada pelo serviço de realidade mista Azure que criou.

Você pode ser um decisor de negócios, profissional de TI, ou uma equipe de inovação que procura adotar HoloLens dentro da sua organização. À medida que se constrói a partir da prova de conceito para uma implantação em escala, os nossos guias de implantação fazem sentido HoloLens dentro da sua infraestrutura de TI - não importa o tamanho ou o pequeno. Os seguintes cenários de implantação são os mais comuns:

| Scenario |Utilização | Pontos principais |
|---------|---------|---------|
| [Cenário A: Dispositivos ligados à nuvem](hololens2-cloud-connected-overview.md) | Quando iniciar a sua implementação, poderá iniciar um pequeno dispositivo ligado à nuvem apenas para ver o processo básico. | Os dispositivos serão ligados a serviços na nuvem e internet pública. Isto é mais adequado para casos de uso do cliente, serviços de campo e prova de conceito.|
| [Cenário B: Rede da organização](hololens2-corp-connected-overview.md) | À medida que se implanta para a produção em escala, poderá ter de se integrar com a rede da sua própria organização. | Os dispositivos serão ligados a uma rede wi-fi "Corporativa". Isto é mais adequado para utilizadores internos, ou uso dentro do ambiente corporativo.|
| [Cenário C: Ambiente seguro offline](hololens-common-scenarios-offline-secure.md) | Alguns processos críticos da missão ou algumas políticas corporativas podem exigir o uso de ambientes offline. | Os dispositivos serão ligados a uma rede altamente restritiva ou serão dispositivos puramente offline. Isto é mais adequado para ambientes altamente seguros, ou restrições de conectividade à Internet em áreas remotas. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Cenário A: Implementar para dispositivos ligados à nuvem

Este cenário é comparável à implementação de dispositivos móveis geridos dentro de uma empresa. HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa. Os recursos corporativos não são acedidos ou podem ser limitados através da VPN.

[![Cenário Um diagrama.](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Quando utilizar

Considere este modelo de implementação para:

* Implantação de prova de conceito, pilotos e serviços de campo
* Implementação de [Assistência Remota](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Configurações comuns básicas

* Wi-Fi redes estão tipicamente totalmente abertas aos serviços de internet e nuvem
* Azure AD Junte-se à Gestão de Dispositivos Móveis (MDM) Inscrição automática--MDM (Intune) Gerido
* Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)
  * Utilizadores únicos ou múltiplos por dispositivo suportado
* Níveis variados de configurações de bloqueio do dispositivo são aplicados com base em casos de utilização específicos, desde o Quiosque de Aplicações Totalmente Abertos a Single App.
* Uma ou mais aplicações são implementadas via MDM

### <a name="common-challenges"></a>Desafios Comuns

* Determinar quais as configurações do MDM a aplicar ao HoloLens 2 com base nos requisitos do cenário

O guia Cloud Connected correspondente cobre como inscrever HoloLens 2 na gestão do seu dispositivo, aplicar licenças conforme necessário e validar que os seus utilizadores finais podem utilizar imediatamente o Remote Assist após a configuração do dispositivo.

> [!div class="nextstepaction"]
> [Guia de implementação ligado à nuvem](hololens2-cloud-connected-overview.md)

Utilize o guia de Clientes Externos para implantar dispositivos num local remoto para utilização externa a curto ou longo prazo.

> [!div class="nextstepaction"]
> [Guia de implementação cloud connected (clientes externos)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Cenário B: Implementar dentro da rede da sua organização

Este cenário é idêntico a uma implantação clássica para a maioria dos PCs Windows 10. HoloLens 2 é implementado para uso principalmente na rede corporativa com acesso a recursos corporativos internos. Os serviços de internet e nuvem podem ser limitados. 

[![Cenário B1 diagrama.](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Cenário B2 diagrama.](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Quando utilizar

Considere este modelo de implementação para:

* Utilizadores internos
* Implantação em escala (Piloto e Produção) no ambiente corporativo

### <a name="basic-common-configurations"></a>Configurações comuns básicas

* Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado aos serviços de internet ou Cloud.
* Azure AD Junte-se à Inscrição Automática do MDM
* MDM (Intune) Gerido
* Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)
  * Utilizadores únicos ou múltiplos por dispositivo suportado
* Níveis variados de configurações de bloqueio do dispositivo são aplicados com base em casos de utilização específicos, desde o Quiosque de Aplicações Totalmente Abertos a Single App.
* Uma ou mais aplicações são implementadas via MDM

### <a name="common-challenges"></a>Desafios Comuns

* HoloLens 2 não suporta em instalações a aderir ou System Center Configuration Manager (SCCM). Apenas a Azure AD se junta ao MDM. Muitas empresas ainda hoje implantam PCs Windows 10 neste cenário como em dispositivos de ad instalações, geridos pela SCCM e que podem não ter a infraestrutura implantada/configurada para gerir dispositivos internos de Windows 10 através de soluções MDM baseadas na nuvem.
* Como HoloLens 2 é um primeiro dispositivo em nuvem, depende fortemente de serviços ligados à internet e cloud para autenticação de utilizadores, atualizações de SO, gestão de MDM, e assim por diante. Ao ligar-se a uma rede corporativa, as regras proxy/firewall provavelmente terão de ser ajustadas para permitir o acesso a HoloLens 2 e as aplicações que nela funcionam.
* A conectividade Wi-Fi corporativa normalmente requer certificados para autenticar o dispositivo ou o utilizador para a rede. A infraestrutura ou configurações necessárias para a implementação de certificados para Windows 10 dispositivos através do MDM podem ser desafiantes à configuração.

O guia Corporate Connected correspondente instrui sobre como inscrever HoloLens 2 na gestão do dispositivo existente, aplicar licenças conforme necessário, e validar que os seus utilizadores finais são capazes de operar um Guia Dinâmico 365, bem como usar a linha personalizada de aplicações empresariais, após a configuração do dispositivo.

> [!div class="nextstepaction"]
> [Guia de implementação corporate connected](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Cenário C: Implementar em ambiente offline seguro

Esta é uma implementação típica para locais altamente seguros ou confidenciais. HoloLens 2 é implementado para uso principalmente offline sem rede ou acesso à Internet.

[![Esquema de segurança offline 1.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Quando utilizar

Considere este modelo de implementação para:

* Ambientes altamente seguros onde os dados precisam de ser mantidos em casa
* "Experiências" onde o público vai usar os dispositivos
* Problema de conectividade da Internet na área remota

### <a name="basic-common-configurations"></a>Configurações comuns básicas

* Wi-Fi conectividade é desativada. Ethernet via USB pode ser ativado para conectividade LAN, se necessário
* Não Gerido
* Conta de utilizador local para o sômin do dispositivo
  * HoloLens 2 suporta apenas uma conta local
* Níveis variados de configurações de bloqueio do dispositivo são aplicados através de Pacotes de Provisionamento com base em casos de utilização específicos. Estas configurações são tipicamente restritas devido a requisitos ambientais seguros
* Uma ou mais aplicações são implementadas através do Pacote de Provisionamento

### <a name="common-challenges"></a>Desafios Comuns

* Há um conjunto limitado de configurações disponíveis através de pacotes de provisionamento
* Os serviços em nuvem não são capazes de ser utilizados, limitando assim as capacidades HoloLens 2.
* Sobrecarga administrativa mais elevada, uma vez que estes dispositivos têm de ser configurados, configurados e atualizados manualmente.

O guia de segurança offline correspondente fornece instruções para a aplicação de uma embalagem de provisão de amostra que bloqueie um HoloLens 2 para utilização em ambientes seguros.

> [!div class="nextstepaction"]
> [Guia de implementação de ambiente seguro offline](hololens-common-scenarios-offline-secure.md)
