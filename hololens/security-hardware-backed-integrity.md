---
title: Integridade apoiada por hardware e atestado de tempo de execução
description: Integridade apoiada por hardware e atestado de tempo de execução
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: segurança, hololens, integridade apoiada por hardware, atestado de tempo de execução, UEFI, boot seguro UEFI, boot seguro, TPM, proteção contra ameaças, Garantia Anti-Persistência do Windows, integridade do código, proteção de código,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0a89fa5e61e560f629444efd2728f6dd41db60d3
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379894"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Atestado de integridade e tempo de execução apoiados por hardware

A integridade e atestado de tempo de execução apoiados por hardware protege contra ameaças que se originam antes do início de um sistema operativo, durante o tempo de funcionamento, quando o dispositivo utiliza hardware e serviços de atestado remoto para garantir que a integridade é mantida no arranque e durante toda a duração do tempo de execução.

## <a name="uefi-secure-boot"></a>Bota segura UEFI

HoloLens 2 impõe sempre o Firmware Interface Extensível Unificado (UEFI) Secure Boot e a UEFI apenas botas Windows Holographic for Business.
O Secure Boot garante que toda a cadeia de arranque é verificada para a integridade e que o Windows funciona sempre com as políticas de segurança corretas aplicadas à sua. Saiba mais sobre [o Secure Boot](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

## <a name="tpm"></a>TPM

O Módulo plataforma fidedigna (TPM) é um chip especializado num dispositivo de ponto final. HoloLens 2 usa um TPM 2.0, que proporciona isolamento de chave imposto por hardware. Saiba mais sobre [os fundamentos da TPM.](https://docs.microsoft.com/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Proteção contra ameaças de acesso à persistência

O objetivo da maioria dos ciberataques é manter o acesso persistente a um dispositivo. No caso do cibercrime, a manutenção desta persistência permite que um dispositivo Windows comprometido se junte a uma botnet, venda de acesso ao dispositivo ou a outros utilizadores nefastos, ou para permitir o roubo repetido de dados. No mundo dos ataques direcionados, a persistência é essencial para um ciberataque bem-sucedido – seja num dispositivo ou (mais comummente), numa rede inteira.  

Na verdade, os ataques direcionados são considerados "ameaças persistentes avançadas", devido à sua necessidade estratégica de manter o acesso a um dispositivo ou rede alvo. Por esta razão, o Windows Holographic for Business considera que a defesa contra a persistência é absolutamente crucial e utiliza tecnologia anti-persistência para fazer uma promessa de segurança ao cliente.

### <a name="secure-boot"></a>Bota segura

HoloLens 2 impõe o Firmware Interface Extensível Unificado (UEFI) Arranque Seguro em todo o estado do sistema operativo principal. A UEFI apenas arranca as plataformas fidedignas da Microsoft, o que garante que toda a cadeia de arranque é verificada para a integridade, e que o Windows funciona sempre com as políticas de segurança corretas aplicadas à empresa. HoloLens 2 não garante o Arranque para ser desligado, nem permite que os carregadores de arranque de 3ª parte.

> [!Tip]
> Saiba mais sobre [a bota Secure](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

### <a name="windows-anti-persistence-assurance"></a>Garantia anti-persistência do Windows

A anti-persistência do HoloLens 2 garante aos seus utilizadores que mesmo na rara situação em que um compromisso de tempo de execução do sistema iria ocorrer – como é o caso de uma exploração remota – tal evento seria atenuado com todo o código malicioso removido do sistema simplesmente desligando o dispositivo. Para fortalecer ainda mais a sua anti-persistência, o HoloLens 2 adicionou uma poderosa proteção contra a integridade e colocou proteções apenas de leitura no lugar.

A persistência nos dados do sistema operativo sob a forma de dados ainda é possível, a menos que o utilizador efetue o reset do botão de push (PBR) do dispositivo que limpa todas as divisórias mutáveis. Embora a persistência em partições imutáveis seja dificultada, o utilizador precisa de PBR the HoloLens 2 para remover qualquer possível persistência de ameaças de partes mutáveis.

## <a name="code-integrity-protection"></a>Proteção contra integridade do código

A integridade do código (CI) é uma propriedade de segurança chave de um sistema operativo moderno. A aplicação do CI permite decisões de segurança sãs, pois garante que a proveniência do código é transparente tanto para o utilizador como para o sistema operativo. A integridade completa do código precisa de estender a assinatura de imagem binária passada e incluir a aplicação do tempo de execução, tais como integridade do fluxo de controlo e restrições dinâmicas de código. O CI é fundamental para prevenir várias classes de ataques, incluindo malware de engenharia social, como ransomware, explorações de execução remota de códigos e várias outras classes de ataque.
