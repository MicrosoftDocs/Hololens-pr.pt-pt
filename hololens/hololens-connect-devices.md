---
title: Ligação para dispositivos Bluetooth e USB-C
description: Começa a ligar-te a dispositivos e acessórios Bluetooth e USB-C dos seus HoloLens dispositivos de realidade mista.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639102"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Ligação para dispositivos Bluetooth e USB-C

## <a name="pair-bluetooth-devices"></a>Emparelhar dispositivos Bluetooth

HoloLens 2 suporta as seguintes classes de dispositivos Bluetooth:

- [HID:](/windows-hardware/drivers/hid/)
    - Rato
    - Teclado
- Dispositivos de saída de áudio (A2DP)

HoloLens 2 suporta as seguintes APIs Bluetooth:
- [Servidor](/windows/uwp/devices-sensors/gatt-server) e [Cliente](/windows/uwp/devices-sensors/gatt-client) do GATT
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Poderá ter de instalar aplicações de acompanhantes correspondentes a partir de Microsoft Store para utilizar os dispositivos HID e GATT.

HoloLens (1ª geração) suporta as seguintes classes de dispositivos Bluetooth:

- Rato
- Teclado
- [clicker HoloLens (1ª gen)](hololens1-clicker.md)

> [!NOTE]
> Outros tipos de dispositivos Bluetooth, como altifalantes, auscultadores, smartphones e almofadas de jogo, podem estar listados como disponíveis em HoloLens configurações. No entanto, estes dispositivos não são suportados em HoloLens (1ª geração). Para mais informações, consulte [HoloLens Definições lista os dispositivos disponíveis, mas os dispositivos não funcionam](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Emparelhar um teclado ou rato Bluetooth

1. Ligue o teclado ou o rato e torne-o detetável. Para aprender a tornar o dispositivo detetável, procure informações sobre o dispositivo (ou a sua documentação) ou visite o site do fabricante.

1. Utilize o gesto de floração (HoloLens (1º gen)) ou o gesto de partida (HoloLens 2) para ir para **Iniciar**, e, em seguida, selecione **Definições**.

1. Selecione **Dispositivos** e certifique-se de que Bluetooth está ligado.  

1. Quando vir o nome do dispositivo, selecione **Emparelhar** e, em seguida, siga as instruções.

## <a name="disable-bluetooth"></a>Desativar Bluetooth

Este procedimento desliga os componentes RF do rádio Bluetooth e desativa todas as funcionalidades Bluetooth no Microsoft HoloLens.

1. Utilize o gesto de floração (HoloLens (1º gen)) ou o gesto de partida (HoloLens 2) para ir para **iniciar**, e, em seguida, selecione   >  **Definições Dispositivos**.

1. Desloque o interruptor de deslize para **Bluetooth** para a posição **desligada.**

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Ligação dispositivos USB-C

HoloLens 2 suporta as seguintes classes de dispositivos USB-C:

- Dispositivos de armazenamento em massa (como pendrives)
- Adaptadores Ethernet (incluindo ethernet mais carregamento)
- Adaptadores de áudio digitais USB-C-a-3.5mm
- Auscultadores de áudio digitais USB-C (incluindo adaptadores de auscultadores mais carregamento)
- Microfones Externos USB-C[(Windows Holográfico, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e superior)
- Rato com fios
- Teclado com fios
- Conjunto de cubos de PD (carregamento USB A mais PD)


> [!NOTE]
> Em resposta ao feedback do cliente, permitimos um suporte limitado para a conectividade celular diretamente ao HoloLens via USB-C. Consulte [Ligação celular e 5G](hololens-cellular.md) para obter mais informações.

### <a name="usb-c-external-microphone-support"></a>Suporte externo do microfone USB-C

> [!IMPORTANT]
> A ligação **de um microfone USB não o definirá automaticamente como o dispositivo de entrada**. Ao ligar um conjunto de auscultadores USB-C, os utilizadores observarão que o áudio do auscultador será automaticamente redirecionado para os auscultadores, mas o HoloLens OS prioriza a matriz interna do microfone acima de qualquer outro dispositivo de entrada. **Para utilizar um microfone USB-C, siga os passos abaixo.**

> [!NOTE]
> Os microfones externos não podem ser utilizados em construções antes [de Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e superior. 

Os utilizadores podem selecionar microfones externos ligados a USB-C utilizando o painel de definições **de som.** Os microfones USB-C podem ser utilizados para chamadas, gravações, etc.

Abra a aplicação **Definições** e selecione **System**  >  **Sound**.

![Som Definições](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para utilizar microfones externos com **Assistência Remota,** os utilizadores terão de clicar na hiperligação "Gerir dispositivos de som".
>
> Em seguida, utilize o drop-down para definir o microfone externo como **Predefinido** ou **Padrão de Comunicações.** Escolher **o Predefinido** significa que o microfone externo será utilizado em todo o lado.
>
> Escolher o **Padrão de Comunicações** significa que o microfone externo será utilizado em aplicações de Assistência Remota e outras aplicações de comunicações, mas o HoloLens conjunto de microfones ainda pode ser usado para outras tarefas.

![Gerir dispositivos de som](images/usbc-mic-2.png)

<br>

![Definir padrão do microfone](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>E Bluetooth suporte ao microfone?

Infelizmente, Bluetooth microfones ainda não estão suportados no HoloLens 2.

### <a name="usb-c-hubs"></a>USB-C Hubs

Alguns utilizadores podem precisar de ligar vários dispositivos ao mesmo tempo. Para os utilizadores que gostariam de utilizar um [microfone USB-C](#usb-c-external-microphone-support) juntamente com outro dispositivo conectado, os hubs USB-C podem corresponder às necessidades do cliente. A Microsoft não testou estes dispositivos, nem podemos recomendar marcas específicas.

**Requisitos para o hub USB-C e dispositivos conectados:**

- Os dispositivos ligados não devem exigir a instalação de um controlador.
- A potência total de todos os dispositivos ligados deve ser inferior a 4,5 Watts.

## <a name="connect-to-miracast"></a>Ligação para Miracast

Para utilizar Miracast, siga estes passos:

1. Faça um dos seguintes:  

   - Abra o menu **Iniciar** e selecione o ícone **'Mostrar'.**
   - Diga "Ligação" enquanto olha para o menu **Iniciar.**  

1. Na lista de dispositivos que aparecem, selecione um dispositivo disponível.

1. Complete o emparelhamento para começar a projetar.
