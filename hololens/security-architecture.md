---
title: Arquitetura de segurança HoloLens
description: Arquitetura de segurança
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, hololens 2, hololens2 segurança, visão geral de segurança, arquitetura de segurança, arquitetura, hololens 2 arquitetura
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379863"
---
# <a name="security-overview-and-architecture"></a><span data-ttu-id="e9192-104">Visão geral de segurança e arquitetura</span><span class="sxs-lookup"><span data-stu-id="e9192-104">Security overview and architecture</span></span>

<span data-ttu-id="e9192-105">A arquitetura de segurança HoloLens 2 foi projetada e projetada do zero para ser livre de problemas de segurança antigas, enquanto criava uma superfície de ataque minimizada.</span><span class="sxs-lookup"><span data-stu-id="e9192-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="e9192-106">Esta nova arquitetura inovadora oferece locais de armazenamento seguros e elementos de segurança avançados, com mecanismos capazes de proteger os sistemas operativos de potenciais ameaças e vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="e9192-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="e9192-107">O HoloLens 2 combina hardware, software, networking e serviços para fornecer segurança de ponta a ponta, ao mesmo tempo que proporciona ao utilizador uma experiência ideal.</span><span class="sxs-lookup"><span data-stu-id="e9192-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="e9192-108">Com holoLens 2, uma grande maioria das funcionalidades de segurança são agora ligadas automaticamente, minimizando o esforço necessário para configurar e configurar corretamente o sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e9192-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="e9192-109">O Windows HoloLens 2 e a arquitetura do sistema operativo oferecem estas funcionalidades de segurança inovadoras:</span><span class="sxs-lookup"><span data-stu-id="e9192-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="e9192-110">**Separação do Estado e isolamento**: Esta nova arquitetura protege partes críticas do sistema operativo HoloLens 2 da mudança - como as necessárias para que o sistema operativo central entre em estado de confiança.</span><span class="sxs-lookup"><span data-stu-id="e9192-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="e9192-111">A tecnologia de isolamento é usada para limitar aplicações não fided assediadas numa área de sandbox, garantindo que não podem afetar a segurança do sistema.</span><span class="sxs-lookup"><span data-stu-id="e9192-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="e9192-112">Todo o sistema operativo é segmentado em secções seguras, com cada secção protegida por uma combinação de diferentes tecnologias de segurança.</span><span class="sxs-lookup"><span data-stu-id="e9192-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="e9192-113">**Proteção de Dados**: Se o dispositivo de um utilizador for perdido ou roubado, o HoloLens 2 impede que aplicações não autorizadas leiam informações sensíveis, baseando-se na encriptação de dados bitLocker.</span><span class="sxs-lookup"><span data-stu-id="e9192-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="e9192-114">**Sistema operativo sem palavra-passe**: Os sistemas operativos mais antigos e baseados em palavras-passe poderiam expor inadvertidamente os utilizadores a ameaças de phishing e eram muitas vezes responsáveis por contas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="e9192-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="e9192-115">O Windows Holographic for Business elimina o uso de palavras-passe para o sismo MSA e Azure AD e reforça a proteção de identidade do utilizador com o Windows Hello™ e fido2.</span><span class="sxs-lookup"><span data-stu-id="e9192-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="e9192-116">Para ter suporte FIDO2, o dispositivo deve estar na Construção 19041 ou superior.</span><span class="sxs-lookup"><span data-stu-id="e9192-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="e9192-117">**Segurança da rede**: O HoloLens 2 oferece ao utilizador uma maior segurança da rede através de protocolos melhorados e definições predefinidas.</span><span class="sxs-lookup"><span data-stu-id="e9192-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
