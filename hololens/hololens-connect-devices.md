---
title: Ligue-se a dispositivos Bluetooth e USB-C
description: Começa a ligar-te a dispositivos Bluetooth e USB-C e acessórios dos seus dispositivos de realidade mista HoloLens.
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
ms.openlocfilehash: e02950bf6cb70e381e3bc5850509bc65267759c1
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924184"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Ligue-se a dispositivos Bluetooth e USB-C

## <a name="pair-bluetooth-devices"></a>Emparelhar dispositivos Bluetooth

O HoloLens 2 suporta as seguintes classes de dispositivos Bluetooth:

- [HID:](https://docs.microsoft.com/windows-hardware/drivers/hid/)
    - Rato
    - Teclado
- Dispositivos de saída de áudio (A2DP)

HoloLens 2 suporta as seguintes APIs Bluetooth:
- [Servidor](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) e [Cliente](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client) do GATT
- [RFCOMM](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Poderá ter de instalar aplicações de acompanhantes correspondentes da Microsoft Store para utilizar os dispositivos HID e GATT.

HoloLens (1º gêger) suporta as seguintes classes de dispositivos Bluetooth:

- Rato
- Teclado
- [Clicker HoloLens (1ª gen)](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> Outros tipos de dispositivos Bluetooth, tais como altifalantes, auscultadores, smartphones e almofadas de jogo, podem estar listados como disponíveis nas definições de HoloLens. No entanto, estes dispositivos não são suportados em HoloLens (1ª geração). Para obter mais informações, consulte [holoLens Settings lista os dispositivos como estão disponíveis, mas os dispositivos não funcionam](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Emparelhar um teclado ou rato Bluetooth

1. Ligue o teclado ou o rato e torne-o detetável. Para aprender a tornar o dispositivo detetável, procure informações sobre o dispositivo (ou a sua documentação) ou visite o site do fabricante.

1. Utilize o gesto de floração (HoloLens (1º gen)) ou o gesto de partida (HoloLens 2) para ir para **iniciar**, e, em seguida, selecione **Definições**.

1. Selecione **Dispositivos** e certifique-se de que o Bluetooth está ligado.  

1. Quando vir o nome do dispositivo, selecione **Emparelhar** e, em seguida, siga as instruções.

## <a name="disable-bluetooth"></a>Desativar Bluetooth

Este procedimento desliga os componentes RF do rádio Bluetooth e desativa toda a funcionalidade Bluetooth no Microsoft HoloLens.

1. Utilize o gesto de floração (HoloLens (1º gen)) ou o gesto de partida (HoloLens 2) para ir para **iniciar**, e, em seguida, selecione **Dispositivos de**  >  **Definições**.

1. Mova o interruptor de slider para **Bluetooth** para a posição **off.**

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Ligar dispositivos USB-C

HoloLens 2 suporta as seguintes classes de dispositivos USB-C:

- Dispositivos de armazenamento em massa (como pendrives)
- Adaptadores Ethernet (incluindo ethernet mais carregamento)
- Adaptadores de áudio digitais USB-C-a-3.5mm
- Auscultadores de áudio digitais USB-C (incluindo adaptadores de auscultadores mais carregamento)
- Microfones Externos USB-C[(Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e superior)
- Rato com fios
- Teclado com fios
- Conjunto de cubos de PD (carregamento USB A mais PD)


> [!NOTE]
> Em resposta ao feedback do cliente, permitimos um suporte limitado para a conectividade celular diretamente aos HoloLens via USB-C. Consulte [Connect to Cellular e 5G](hololens-cellular.md) para obter mais informações.

### <a name="usb-c-external-microphone-support"></a>Suporte externo do microfone USB-C

> [!IMPORTANT]
> A ligação **de um microfone USB não o definirá automaticamente como o dispositivo de entrada**. Ao ligar um conjunto de auscultadores USB-C, os utilizadores observarão que o áudio do auscultador será automaticamente redirecionado para os auscultadores, mas o HoloLens OS prioriza a matriz interna do microfone acima de qualquer outro dispositivo de entrada. **Para utilizar um microfone USB-C, siga os passos abaixo.**

> [!NOTE]
> Os microfones externos não podem ser utilizados em construções anteriores ao [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e superior. 

Os utilizadores podem selecionar microfones externos ligados a USB-C utilizando o painel de definições **de som.** Os microfones USB-C podem ser utilizados para chamadas, gravações, etc.

Abra a aplicação **Definições** e selecione **System**  >  **Sound**.

![Definições de som](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para utilizar microfones externos com **Assistência Remota,** os utilizadores terão de clicar na hiperligação "Gerir dispositivos de som".
>
> Em seguida, utilize o drop-down para definir o microfone externo como **Predefinido** ou **Padrão de Comunicações.** Escolher **o Predefinido** significa que o microfone externo será utilizado em todo o lado.
>
> Escolher o **Padrão de Comunicações** significa que o microfone externo será utilizado em aplicações de Assistência Remota e outras aplicações de comunicações, mas o conjunto de microfones HoloLens ainda pode ser usado para outras tarefas.

![Gerir dispositivos de som](images/usbc-mic-2.png)

<br>

![Definir padrão do microfone](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>E o suporte ao microfone Bluetooth?

Infelizmente, os microfones Bluetooth ainda não estão suportados no HoloLens 2.

### <a name="usb-c-hubs"></a>USB-C Hubs

Alguns utilizadores podem precisar de ligar vários dispositivos ao mesmo tempo. Para os utilizadores que gostariam de utilizar um [microfone USB-C](#usb-c-external-microphone-support) juntamente com outro dispositivo conectado, os hubs USB-C podem corresponder às necessidades do cliente. A Microsoft não testou estes dispositivos, nem podemos recomendar marcas específicas.

**Requisitos para o hub USB-C e dispositivos conectados:**

- Os dispositivos ligados não devem exigir a instalação de um controlador.
- A potência total de todos os dispositivos ligados deve ser inferior a 4,5 Watts.

## <a name="connect-to-miracast"></a>Ligue-se ao Miracast

Para utilizar o Miracast, siga estes passos:

1. Faça um dos seguintes:  

   - Abra o menu **Iniciar** e selecione o ícone **'Mostrar'.**
   - Diga "Conecte-se" enquanto olha para o menu **Iniciar.**  

1. Na lista de dispositivos que aparecem, selecione um dispositivo disponível.

1. Complete o emparelhamento para começar a projetar.
