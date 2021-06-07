---
title: Ligue-se ao Celular e 5G
description: Conectar-se a redes celulares a partir dos seus hololens misturou dispositivos de realidade.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 8318d011d6a593c1036b6bcf6f7973870b0dc294
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379839"
---
# <a name="connect-to-cellular-and-5g"></a>Ligue-se ao Celular e 5G

HoloLens 2 suporta dois métodos de ligação às redes celulares e 5G:

- Uma rede WiFi ad hoc fornecida pelo dispositivo celular, vulgarmente referida como um "Hotspot"
- Suporte limitado para dispositivos com tethers USB-C

## <a name="hotspot-wifi"></a>Hotspot (WiFi)

A maioria das necessidades de conectividade celular pode ser satisfeita com um hotspot. HoloLens 2 WiFi suporta 802.11ac, que pode fornecer os requisitos de largura de banda e latência necessários para a maioria dos casos de uso comum. O Wi-Fi também é livre de cabos e oferece compatibilidade com o maior número de dispositivos celulares.

### <a name="connecting-to-a-hotspot"></a>Ligação a um hotspot

1. Consulte o manual do seu dispositivo sobre como ativar o modo hotspot.
1. Ativar o modo hotspot, fornecendo um nome para a rede, bem como uma palavra-passe conhecida.
1. Nas definições de Rede HoloLens 2, localize a rede WiFi criada no passo 2 e junte-se a ela.

## <a name="usb-c-tethering"></a>USB-C Tethering

A tethering USB-C pode fornecer uma latência mais baixa para cargas de trabalho avançadas que precisam dela. [A renderização remota Azure,](https://azure.microsoft.com/services/remote-rendering)por exemplo, pode beneficiar da amarra. Note que a amarração requer um cabo entre o dispositivo celular e holoLens, e a amarração é suportada por um número limitado de dispositivos.

### <a name="usb-c-compatibility"></a>Compatibilidade USB-C

Um número limitado de dispositivos que se apresentam como um adaptador ethernet pode ser usado com a versão Holográfica do Windows 2004 e posteriormente.

Os dispositivos que não se apresentam como adaptador ethernet devem suportar o controlador genérico do Microsoft [RNDIS.](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Mas, apenas um número limitado desses dispositivos são compatíveis com hololens 2. Consulte o fabricante do seu dispositivo para obter mais informações sobre se suporta o controlador genérico do Microsoft RNDIS.

Os dispositivos que não são compatíveis com o RNDIS, ou que exigem a instalação de um controlador ou aplicação.

Embora a Microsoft não mantenha uma lista de dispositivos compatíveis, há uma discussão comunitária sobre o tema [aqui.](https://aka.ms/HLCommunityCell)

### <a name="connecting-to-a-tethered-device"></a>Ligação a um dispositivo amarrado

1. Consulte o manual do seu dispositivo sobre como permitir a partilha de dados em USB. Esta definição é frequentemente referida como "USB Tethering", "Data Sharing" ou "USB Modem".
1. Ativar a partilha de dados em USB.
1. Ligue o seu dispositivo à porta USB-C hololens.
1. Nas definições de Rede HoloLens 2, o dispositivo aparecerá automaticamente como uma ligação Ethernet.
