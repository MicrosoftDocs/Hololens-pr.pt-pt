---
title: Pré-visualização de insider para Microsoft HoloLens
description: Saiba como começar com as construções insider e forneça feedback valioso para a nossa próxima grande atualização do sistema operativo para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924364"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Pré-visualização de insider para Microsoft HoloLens

Bem-vindos às mais recentes construções de Insider Preview para HoloLens! É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer feedback valioso para a nossa próxima grande atualização do sistema operativo para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notas de lançamento de insider

Estamos entusiasmados por todas as nossas recentes funcionalidades do Insider terem vindo a público! Se quiser ler sobre estes, por favor, veja a página de [notas de lançamento](hololens-release-notes.md)

## <a name="start-receiving-insider-builds"></a>Comece a receber construções insider

> [!NOTE]
> Se ainda não foi atualizado recentemente, por favor reinicie o seu dispositivo para atualizar o estado e obter a mais recente construção.
>
> - O comando de voz "Reboot device" funciona bem.
> - Também pode escolher o botão de reinício no Programa Insider Definições/Windows.
>
> Tivemos uma escuta na parte de trás que podes ter encontrado e isto vai pôr-te de volta nos eixos.

Num dispositivo HoloLens 2, vá para **Definições**  >  **Update & Security** Windows Insider  >  **Program** e **selecione Get start**. Ligue a conta que usou para se registar como Windows Insider.

> [!NOTE]
> Para inscrever o seu dispositivo nas construções Insider, terá de ativar a telemetria opcional. Se ainda não o fez, abra a aplicação Definições e selecione **o Feedback**& de Diagnóstico de Privacidade  ->   e, em seguida, selecione **dados de diagnósticos opcionais**.

Windows infiltrado está agora a mudar-se para os canais. O anel **Rápido** passará a ser o **Canal Dev,** o anel **Lento** passará a ser o **Canal Beta**, e o anel de **pré-visualização** de lançamento passará a ser o **Canal de Pré-visualização de Lançamento**. Aqui está o que o mapeamento parece:

![Windows Explicação dos Canais Internos.](images/WindowsInsiderChannels.png)

Para mais informações, consulte [a introdução Windows canais Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nos blogs Windows.
Em seguida, **selecione Ative development of Windows**, escolha se gostaria de receber construções de **Dev Channel** ou Beta **Channel** e reveja os termos do programa.
**Selecione Confirm > Reinicie agora** para terminar. Depois de o seu dispositivo ter sido reiniciado, vá a **Definições > Update & Security > Verifique se há novidades** para obter a mais recente construção.

### <a name="update-error-0x80070490-work-around"></a>Atualizar erro 0x80070490 trabalho

Se encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, experimente o seguinte trabalho de curto prazo. Envolve mover o seu canal de insider, pegar na atualização e, em seguida, mover o seu canal Insider de volta.

#### <a name="stage-one---release-preview"></a>Fase um - Visualização de lançamento

1. Definições, Update & Security, Windows Insider Program, selecione **Release Preview Channel**.

2. Definições, Atualizar segurança &, Windows Update, **verificar se há atualizações**. Após a atualização, continue para a fase dois.

#### <a name="stage-two---dev-channel"></a>Fase dois - Canal Dev

1. Definições, Update & Security, Windows Insider Program, selecione **Dev Channel**.

2. Definições, Atualizar segurança &, Windows Update, **verificar se há atualizações**.

## <a name="ffu-download-and-flash-directions"></a>Instruções de descarregamento e flash da FFU

Para testar com um voo assinado ffu, primeiro tem de voar para desbloquear o seu dispositivo antes de piscar o voo assinado.

1. No PC:
    1. Faça o download para o seu PC a partir de [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Instalar o ARC (Advanced Recovery Companion) a partir do Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. Em HoloLens - Desbloqueia o voo: Abrir **Definições**  >  **atualizar & segurança** Windows Programa  >  **Insider** e depois inscrever-se, reiniciar o dispositivo.

1. Flash FFU - Agora pode piscar o voo assinado FFU usando ARC.

### <a name="provide-feedback-and-report-issues"></a>Fornecer problemas de feedback e relatório

Por favor, use [a aplicação Feedback Hub](hololens-feedback.md) no seu HoloLens para fornecer problemas de feedback e relatório. A utilização do Feedback Hub garante que todas as informações necessárias de diagnóstico estão incluídas para ajudar os nossos engenheiros a depurar e resolver o problema rapidamente.  Os problemas com a versão chinesa e japonesa de HoloLens devem ser reportados da mesma forma.

> [!NOTE]
> Não se esqueça de aceitar a solicitação que pergunta se pretende que o Feedback Hub aceda à pasta Documentos (selecione **Sim** quando solicitado).

## <a name="note-for-developers"></a>Nota para desenvolvedores

É bem-vindo e encorajado a tentar desenvolver as suas aplicações usando as construções insider de HoloLens.  Confira a [documentação do programador HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar. As mesmas instruções funcionam com as construções de HoloLens.  Pode usar as mesmas construções de Unidade e Visual Studio que já está a usar para HoloLens desenvolvimento.

## <a name="stop-receiving-insider-builds"></a>Pare de receber builds Insider

Se já não quiser receber as construções insider de Windows Holographic, pode optar quando o seu HoloLens estiver a executar uma construção de produção, ou pode recuperar o [seu dispositivo](hololens-recovery.md) utilizando o Advanced Recovery Companion para recuperar o seu dispositivo para uma versão não-Insider de Windows Holographic.

> [!CAUTION]
> Existe um problema conhecido em que os utilizadores que não se matriculam no Insider Preview constroem depois de reinstalarem manualmente uma nova construção de pré-visualização experimentariam um ecrã azul. Depois, devem recuperar manualmente o seu dispositivo. Para mais detalhes sobre se você seria impactado ou não, por favor, veja mais sobre esta [Edição Conhecida.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Para verificar se o seu HoloLens está a executar uma construção de produção:

1. Vá ao **Definições > System > About**, e encontre o número de construção.

1. [Consulte as notas de lançamento para os números de construção de produção](hololens-release-notes.md).

Para excluir as construções insider:

1. Numa HoloLens executar uma construção de produção, vá a **Definições > Update & Security > Windows Insider Program**, e selecione **Builds Stop Insider**.

1. Siga as instruções para desativar o seu dispositivo.
