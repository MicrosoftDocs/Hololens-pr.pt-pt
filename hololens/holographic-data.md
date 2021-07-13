---
title: Encontre e guarde ficheiros sobre HoloLens
description: Aprenda a usar o File Explorer no HoloLens para abrir, visualizar e gerir ficheiros no seu dispositivo de realidade mista.
keywords: como, picker de ficheiros, ficheiros, fotos, vídeos, imagens, OneDrive, armazenamento, explorador de ficheiros, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636185"
---
# <a name="find-open-and-save-files-on-hololens"></a>Encontre, abra e guarde ficheiros sobre HoloLens

Os ficheiros que cria no HoloLens, incluindo fotos e vídeos, são guardados diretamente no seu dispositivo HoloLens. Veja-os e gere-os da mesma forma que geriria ficheiros em Windows 10:

- Utilizar a aplicação File Explorer para aceder a pastas locais.
- Dentro do armazenamento de uma aplicação.
- Numa pasta especial (como a biblioteca de vídeo ou música).
- Utilizar um serviço de armazenamento que inclua uma aplicação e um selecionador de ficheiros (como OneDrive).
- Utilizando um PC de secretária ligado ao seu HoloLens utilizando um cabo USB, utilizando o suporte MTP (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>Ver ficheiros em HoloLens usando o Explorador de Ficheiros

> Aplica-se a todos os HoloLens 2 dispositivos e HoloLens (1ª gen) a partir da [Windows 10 atualização de abril de 2018 (RS4) para HoloLens](/windows/mixed-reality/release-notes-april-2018).

Utilize o File Explorer no HoloLens para visualizar e gerir ficheiros no seu dispositivo, incluindo objetos 3D, documentos e imagens. Vá para **iniciar**   >  **todas as aplicações**   >  **File Explorer** para começar.

> [!TIP]
> Se não houver ficheiros listados no Explorador de Ficheiros, selecione **Este Dispositivo** no painel superior esquerdo.

Se não vir ficheiros no File Explorer, o filtro "Recente" pode estar ativo (o ícone do relógio é realçado no painel esquerdo). Para corrigir isto, selecione o ícone do documento **deste dispositivo** no painel esquerdo (por baixo do ícone do relógio) ou abra o menu e selecione **Este Dispositivo**.

## <a name="find-and-view-your-photos-and-videos"></a>Encontre e veja as suas fotos e vídeos

[A captura de realidade mista](holographic-photos-and-videos.md) permite-lhe tirar fotos e vídeos de realidade mista no HoloLens.  Estas fotos e vídeos são guardados na pasta Camera Roll do dispositivo.

Pode aceder a fotos e vídeos tirados com HoloLens:

- aceder à Câmara Rolar diretamente através da [aplicação Fotos](holographic-photos-and-videos.md).
- o upload de fotos e vídeos para o armazenamento em nuvem sincronizando as suas fotos e vídeos para OneDrive.
- utilizando a página de Captura de Realidade Mista do Portal do [Dispositivo Windows](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Aplicação Fotografias

A aplicação Fotos é uma das aplicações predefinidos no menu **Iniciar,** e vem incorporada com HoloLens. Saiba mais sobre [a utilização da aplicação Fotos para visualizar o conteúdo.](holographic-photos-and-videos.md)

Também pode instalar a [aplicação OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) a partir do Microsoft Store para sincronizar fotos para outros dispositivos.

### <a name="onedrive-app"></a>OneDrive app

[OneDrive](https://onedrive.live.com/) permite-lhe aceder, gerir e partilhar as suas fotos e vídeos com qualquer dispositivo e com qualquer utilizador. Para aceder às fotos e vídeos capturados no HoloLens, descarregue a [aplicação OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) a partir do Microsoft Store no seu HoloLens. Uma vez descarregado, abra a aplicação OneDrive e selecione **Definições**  >  **upload da Câmara**, e ligue o upload da **Câmara**.

### <a name="connect-to-a-pc"></a>Ligação para um PC

Se o seu HoloLens estiver a executar a [atualização Windows 10 abril de 2018](/windows/mixed-reality/release-notes-april-2018) ou mais tarde, pode ligar o seu HoloLens a um PC Windows 10 utilizando um cabo USB para navegar em fotografias e vídeos no dispositivo utilizando MTP (protocolo de transferência de meios). Terá de se certificar de que o dispositivo está desbloqueado para navegar em ficheiros se tiver um PIN ou uma palavra-passe configurado no seu dispositivo.  

Se tiver ativado o Portal do [Dispositivo Windows,](/windows/mixed-reality/using-the-windows-device-portal)pode usá-lo para navegar, recuperar e gerir as fotos e vídeos armazenados no seu dispositivo.

## <a name="access-files-within-an-app"></a>Aceder a ficheiros dentro de uma aplicação

Se uma aplicação guardar ficheiros no seu dispositivo, pode utilizar essa aplicação para aceder aos mesmos.

### <a name="requesting-files-from-another-app"></a>Solicitando ficheiros de outra app

Uma aplicação pode solicitar para guardar um ficheiro ou abrir um ficheiro de outra aplicação utilizando [pickers de ficheiros](/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Pastas conhecidas

HoloLens suporta uma série de [pastas conhecidas](/windows/mixed-reality/app-model#known-folders) que as aplicações podem solicitar permissão para aceder.

## <a name="view-hololens-files-on-your-pc"></a>Ver ficheiros HoloLens no seu PC

Semelhante a outros dispositivos móveis, conecte-se HoloLens ao seu PC de secretária utilizando MTP (Media Transfer Protocol) e abra o File Explorer no PC para aceder às suas bibliotecas HoloLens para facilitar a transferência.

Para ver os seus ficheiros HoloLens no Explorador de Ficheiros no seu PC:

1. Inscreva-se para HoloLens e, em seguida, ligue-o ao PC utilizando o cabo USB que veio com o HoloLens.

1. Selecione **Dispositivo Aberto para visualizar ficheiros com o Explorador de Ficheiros,** ou abra o Explorador de Ficheiros no PC e navegue para o dispositivo.

Para ver informações sobre o seu HoloLens, clique com o botão direito no nome do dispositivo no Explorador de Ficheiros no seu PC e, em seguida, selecione **Propriedades**.

> [!NOTE]
> HoloLens (1º gênero) não suporta a ligação a discos rígidos externos ou cartões SD.

## <a name="sync-to-the-cloud"></a>Sincronizar com a nuvem

Para sincronizar fotos e outros ficheiros do seu HoloLens para a nuvem, instale e instale OneDrive no HoloLens. Para obter OneDrive, procure-o no Microsoft Store na sua HoloLens.

HoloLens não faz o back-up de ficheiros e dados de aplicações, por isso é uma boa ideia guardar as suas coisas importantes para OneDrive. Desta forma, se reiniciar o seu dispositivo ou desinstalar uma aplicação, a sua informação será apoiada.
