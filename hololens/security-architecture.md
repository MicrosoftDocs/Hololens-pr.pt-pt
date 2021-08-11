---
title: arquitetura de segurança HoloLens
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
ms.openlocfilehash: fd6409f5087ef7d6e7ab90d6ef8dcb83e1c490746803ad869ef075dace24bae7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665527"
---
# <a name="security-overview-and-architecture"></a>Visão geral de segurança e arquitetura

A arquitetura de segurança HoloLens 2 foi projetada e projetada do zero para ser livre de questões de segurança antigas, enquanto criava uma superfície de ataque minimizada. Esta nova arquitetura inovadora oferece locais de armazenamento seguros e elementos de segurança avançados, com mecanismos capazes de proteger os sistemas operativos de potenciais ameaças e vulnerabilidades.

HoloLens 2 combina hardware, software, networking e serviços para fornecer segurança de ponta a ponta, ao mesmo tempo que proporciona ao utilizador uma experiência ideal. Com HoloLens 2, uma grande maioria das funcionalidades de segurança são agora ligadas automaticamente, minimizando o esforço necessário para configurar e configurar corretamente o sistema operativo.

Windows HoloLens 2 e a arquitetura do sistema operativo oferece estas características de segurança inovadoras:

  * **Separação e isolamento** do Estado : Esta nova arquitetura protege partes críticas do sistema operativo HoloLens 2 da mudança - como as necessárias para que o sistema operativo central entre em estado de confiança. A tecnologia de isolamento é usada para limitar aplicações não fided assediadas numa área de sandbox, garantindo que não podem afetar a segurança do sistema. Todo o sistema operativo é segmentado em secções seguras, com cada secção protegida por uma combinação de diferentes tecnologias de segurança.
  
  * **Proteção de Dados**: Se o dispositivo de um utilizador for perdido ou roubado, HoloLens 2 impede que aplicações não autorizadas leiam informações sensíveis, baseando-se na encriptação de dados bitLocker. 
  
  * **Sistema operativo sem palavra-passe**: Os sistemas operativos mais antigos e baseados em palavras-passe poderiam expor inadvertidamente os utilizadores a ameaças de phishing e eram muitas vezes responsáveis por contas comprometidas. Windows Holographic for Business elimina o uso de palavras-passe para o sismo MSA e Azure AD e reforça a proteção da identidade do utilizador com Windows Hello™ e fido2. 
  
    > [!NOTE]
    > Para ter suporte FIDO2, o dispositivo deve estar na Construção 19041 ou superior. 

  * **Segurança da rede**: HoloLens 2 oferece ao utilizador uma segurança de rede aumentada através de protocolos melhorados e definições predefinidas.
