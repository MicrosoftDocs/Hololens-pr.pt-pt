---
title: Segurança da rede
description: segurança de rede
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, rede, segurança de rede
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379871"
---
# <a name="network-security"></a>Segurança da rede

## <a name="network-protocols"></a>Protocolos de rede

O NetBIOS desatualizado (Network Basic Input/Output System) foi amplamente utilizado no passado em cenários LAN – muitas vezes para fornecer resolução de nome a um computador e pastas partilhadas. Mas com o passar do tempo, o NetBIOS provou ser suscetível a múltiplos ataques, e a sua relevância diminuiu em favor de outros protocolos mais seguros. Para remover este problema de vulnerabilidade, o HoloLens 2 eliminou o código relacionado com o NetBIOS do sistema operativo.

Os protocolos TLS (Transport Layer Security) estão em constante evolução. Para acompanhar as várias façanhas de segurança que foram descobertas nesta área, a indústria informática formou-se em versões mais recentes e eficazes. Devido ao tempo necessário para que todas as implementações do servidor adotem as novas versões do protocolo TLS, pode ser implementado um mecanismo de retorno que permite ao cliente e servidores em diferentes versões de protocolo predefinidos ainda poderem comunicar durante o período de transição.

## <a name="secure-connectivity"></a>Conectividade segura 

O Windows Defender Firewall fornece funcionalidades críticas para garantir a conectividade do dispositivo. Com hololens 2, a firewall está sempre ativada e não há formas de desativá-la programáticamente ou através da UI.

O acesso remoto e a privacidade de conexão para clientes móveis podem ser assegurados através da [plataforma plug-in UWP VPN](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041). Os fornecedores de VPN de terceiros podem criar os seus próprios plug-ins utilizando ASPIs WinRT que funcionarão dentro da caixa de areia AppContainer, eliminando a complexidade e os problemas frequentemente associados aos controladores de nível de escrita do sistema.
