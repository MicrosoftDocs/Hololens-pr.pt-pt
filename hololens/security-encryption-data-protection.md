---
title: Encriptação e Proteção de Dados
description: Saiba mais sobre encriptação e proteção de dados em HoloLens 2 dispositivos, incluindo a integração bitLocker e Azure.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, encriptação, proteção de dados, dispositivo BitLocker, BitLocker, bitlocker, encriptação bitlocker, integração azure,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639374"
---
# <a name="encryption-and-data-protection"></a>Encriptação e proteção de dados

A encriptação e proteção de dados protege os dados quando o dispositivo é perdido ou roubado e impede que aplicações não autorizadas acedam a informações sensíveis.

## <a name="bitlocker-device-encryption"></a>Encriptação do dispositivo BitLocker

BitLocker é uma funcionalidade de encriptação de volume completo para a proteção da integridade dos meios de comunicação Read Only (RO) e proteção da privacidade dos meios de comunicação.  Desde a sua criação, tem sido um escudo eficaz contra o acesso não autorizado aos dados durante ataques offline. HoloLens 2 permite a encriptação do dispositivo Bitlocker (BDE) por padrão para proteger os dados de qualquer acesso físico não autorizado ao dispositivo. Sempre evoluindo para atender às necessidades do futuro, a Microsoft continua a investir e a melhorar esta tecnologia.

O BDE é uma funcionalidade de proteção de dados que emprega encriptação AES-XTS-256 em todos os volumes do layout separados pelo estado do dispositivo. O BDE fornece encriptação de nível do dispositivo num layout separado pelo Estado. A encriptação do dispositivo BitLocker é ativada automaticamente no sistema operativo e nos volumes de dados fixos e não pode ser desligada, mesmo por administradores de TI, para que o dispositivo esteja sempre protegido.

As chaves de encriptação do BDE são então utilizadas para desencriptar de forma transparente binários e os dados necessários para iniciar o dispositivo. À medida que o volume do sistema operativo é desbloqueado e um sistema está a ser iniciado, outros volumes tornam-se acessíveis utilizando uma versão específica do volume do protetor de desbloqueio automático. Não existem outros protetores disponíveis para manter a privacidade do utilizador e a unidade só pode ser desbloqueada no mesmo dispositivo. Leia Apenas a execução (RO) nos volumes necessários é aplicada e aplicada imediatamente, a partir da primeira bota. A chave de recuperação bitlocker não é necessária no ciclo de vida HoloLens 2.

## <a name="azure-integration"></a>Integração do Azure 

HoloLens 2 permite que os clientes integrem os seus dispositivos com os serviços Azure. As comunicações entre HoloLens 2 dispositivos e o Azure utilizam o protocolo TLS (Transport Layer Security) para proteger os dados que viajam entre si e os serviços na nuvem, que fornecem autenticação forte, privacidade de mensagens e integridade. Todos os serviços da Azure suportam totalmente o TLS 1.2 e quaisquer serviços em que os clientes utilizem apenas TLS 1.2 apenas aceitam o tráfego TLS 1.2. Os padrões de encriptação do Azure para os dados em trânsito são detalhados na visão geral da [encriptação do Azure](/azure/security/fundamentals/encryption-overview). Visite a documentação do Azure para saber mais sobre [as melhores práticas para a segurança e encriptação de dados do Azure.](/azure/security/fundamentals/data-encryption-best-practices) 

OneDrive, um exemplo de integração na nuvem com HoloLens 2, tem uma funcionalidade de upload automático onde os seus ficheiros e documentos podem ser automaticamente carregados para a nuvem quando ligados à internet. A pausa na sincronização automática de ficheiros não pode ser desligada através da política, mas é diretamente configurável através do UX. 
