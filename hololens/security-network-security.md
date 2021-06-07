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
# <a name="network-security"></a><span data-ttu-id="e2ccd-104">Segurança da rede</span><span class="sxs-lookup"><span data-stu-id="e2ccd-104">Network security</span></span>

## <a name="network-protocols"></a><span data-ttu-id="e2ccd-105">Protocolos de rede</span><span class="sxs-lookup"><span data-stu-id="e2ccd-105">Network protocols</span></span>

<span data-ttu-id="e2ccd-106">O NetBIOS desatualizado (Network Basic Input/Output System) foi amplamente utilizado no passado em cenários LAN – muitas vezes para fornecer resolução de nome a um computador e pastas partilhadas.</span><span class="sxs-lookup"><span data-stu-id="e2ccd-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="e2ccd-107">Mas com o passar do tempo, o NetBIOS provou ser suscetível a múltiplos ataques, e a sua relevância diminuiu em favor de outros protocolos mais seguros.</span><span class="sxs-lookup"><span data-stu-id="e2ccd-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="e2ccd-108">Para remover este problema de vulnerabilidade, o HoloLens 2 eliminou o código relacionado com o NetBIOS do sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e2ccd-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="e2ccd-109">Os protocolos TLS (Transport Layer Security) estão em constante evolução.</span><span class="sxs-lookup"><span data-stu-id="e2ccd-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="e2ccd-110">Para acompanhar as várias façanhas de segurança que foram descobertas nesta área, a indústria informática formou-se em versões mais recentes e eficazes.</span><span class="sxs-lookup"><span data-stu-id="e2ccd-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="e2ccd-111">Devido ao tempo necessário para que todas as implementações do servidor adotem as novas versões do protocolo TLS, pode ser implementado um mecanismo de retorno que permite ao cliente e servidores em diferentes versões de protocolo predefinidos ainda poderem comunicar durante o período de transição.</span><span class="sxs-lookup"><span data-stu-id="e2ccd-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <a name="secure-connectivity"></a><span data-ttu-id="e2ccd-112">Conectividade segura</span><span class="sxs-lookup"><span data-stu-id="e2ccd-112">Secure connectivity</span></span> 

<span data-ttu-id="e2ccd-113">O Windows Defender Firewall fornece funcionalidades críticas para garantir a conectividade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e2ccd-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="e2ccd-114">Com hololens 2, a firewall está sempre ativada e não há formas de desativá-la programáticamente ou através da UI.</span><span class="sxs-lookup"><span data-stu-id="e2ccd-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="e2ccd-115">O acesso remoto e a privacidade de conexão para clientes móveis podem ser assegurados através da [plataforma plug-in UWP VPN](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span><span class="sxs-lookup"><span data-stu-id="e2ccd-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="e2ccd-116">Os fornecedores de VPN de terceiros podem criar os seus próprios plug-ins utilizando ASPIs WinRT que funcionarão dentro da caixa de areia AppContainer, eliminando a complexidade e os problemas frequentemente associados aos controladores de nível de escrita do sistema.</span><span class="sxs-lookup"><span data-stu-id="e2ccd-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
