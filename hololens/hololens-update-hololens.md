---
title: Atualizar HoloLens
description: Saiba como verificar o número de construção dos HoloLens, mantenha-se atualizado com as atualizações do dispositivo, junte-se ao Programa Insiders e reverta as atualizações.
keywords: como, atualizar, reverter, HoloLens, verificar construção, número de construção
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378585"
---
# <a name="update-hololens"></a>Atualizar HoloLens

O HoloLens utiliza o Windows Update, tal como outros dispositivos Windows 10. Os holoLens descarregarão e instalarão automaticamente atualizações do sistema sempre que estiver ligado à energia e ligado à Internet, mesmo quando este se encontra em modo de espera.

Este artigo irá percorrer as ferramentas HoloLens para:

- visualizando a sua versão atual do sistema operativo (número de construção)
- verificação de atualizações
- atualizar manualmente HoloLens
- voltando para uma atualização mais antiga

## <a name="check-your-operating-system-version-build-number"></a>Verifique a versão do seu sistema operativo (número de construção)

Pode verificar o número da versão do sistema (número de construção) abrindo a aplicação Definições e selecionando **System**  >  **About**.

## <a name="check-for-updates-and-manually-update"></a>Verifique as atualizações e atualização manual

Pode verificar se há atualizações a qualquer momento nas definições.  Para ver as atualizações disponíveis e verificar novas atualizações:

1. Abra a aplicação **Definições**.
1. Navegue para **atualizar & atualização do** Windows de segurança  >  .
1. Selecione **Procurar atualizações**.

Se houver uma atualização disponível, começará a descarregar a nova versão. Depois de concluída a transferência, selecione o botão **Restart Now** para ativar a instalação. Se o seu dispositivo estiver abaixo dos 40% e não estiver ligado, o reinício não começará a instalar a atualização.

Enquanto os HoloLens estiverem a instalar a atualização, apresentará engrenagens giratórias e um indicador de progresso. Não desligue os HoloLens durante este tempo. Reiniciar-se-á automaticamente depois de concluída a instalação.

HoloLens aplica uma atualização de cada vez.  Se o seu HoloLens estiver a mais de uma versão por trás da mais recente, poderá ter de passar várias vezes pelo processo de atualização para o atualizar completamente.

## <a name="go-back-to-a-previous-version---hololens-2"></a>Volte para uma versão anterior - HoloLens 2

Em alguns casos, talvez queira voltar a uma versão anterior do software HoloLens. Pode fazê-lo utilizando o Advanced Recovery Companion para redefinir os hololens para a versão anterior.

> [!NOTE]
> Voltar a uma versão anterior elimina os seus ficheiros e configurações pessoais.

Para voltar a uma versão anterior do HoloLens 2, siga estes passos:

1. Certifique-se de que não tem telefones ou dispositivos Windows ligados ao seu PC.
1. No seu PC, descarregue o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.
1. Descarregue o [mais recente lançamento holoLens 2](https://aka.ms/hololens2download).
1. Quando terminar estes downloads, abra os downloads **do Explorador de**  >  **Ficheiros**. Clique com o botão direito na pasta com fecho que acabou de descarregar e **selecione Extrair todo** o  >  **Extrato** para desapertá-la.
1. Ligue os HoloLens ao seu PC utilizando um cabo USB-A a USB-C. (Mesmo que tenha usado outros cabos para ligar os hololens, este funciona melhor.)
1. O Companheiro de Recuperação Avançada deteta automaticamente os seus HoloLens. Selecione o azulejo **microsoft HoloLens.**
1. No ecrã seguinte, selecione **Manual** e, em seguida, selecione o ficheiro de instalação contido na pasta que abriu no passo 4. (Procure um ficheiro com a extensão .ffu.)
1. **Selecione Instalar o software** e seguir as instruções.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Volte para uma versão anterior - HoloLens (1ª Gen)

Em alguns casos, talvez queira voltar a uma versão anterior do software HoloLens. Pode fazê-lo utilizando a Ferramenta de Recuperação de Dispositivos do Windows para redefinir os HoloLens para a versão anterior.

> [!NOTE]
> Voltar a uma versão anterior elimina os seus ficheiros e configurações pessoais.

Para voltar a uma versão anterior do HoloLens 1, siga estes passos:

1. Certifique-se de que não tem telefones ou dispositivos Windows ligados ao seu PC.
1. No seu PC, descarregue a [Ferramenta de Recuperação de Dispositivos windows (WDRT)](https://support.microsoft.com/help/12379).
1. Descarregue o pacote de recuperação da [Atualização de Aniversário holoLens](https://aka.ms/hololensrecovery).
1. Quando os downloads terminarem, abra o **Explorador de**  >  **Ficheiros Downloads**. Clique com o botão direito na pasta com fecho que acabou de descarregar e **selecione Extrair todo** o  >  **Extrato** para desapertá-la.
1. Ligue os HoloLens ao seu PC utilizando o cabo micro-USB que ele veio. (Mesmo que tenha usado outros cabos para ligar os hololens, este funciona melhor.)
1. O WDRT detetará automaticamente os seus HoloLens. Selecione o azulejo **microsoft HoloLens.**
1. No ecrã seguinte, selecione **Manual** e escolha o ficheiro de instalação contido na pasta que abriu no passo 4. (Procure um ficheiro com a extensão .ffu.)
1. **Selecione Instalar o software** e seguir as instruções.

> [!NOTE]
> Se o WDRT não detetar os hololens, tente reiniciar o seu PC. Se isso não funcionar, selecione **O meu dispositivo não foi detetado**, selecione Microsoft **HoloLens** e, em seguida, siga as instruções.

## <a name="windows-insider-program-on-hololens"></a>Programa Insider do Windows em HoloLens

Quer ver as últimas funcionalidades em HoloLens?  Em caso afirmativo, junte-se ao Programa Insider do Windows; terá acesso a pré-visualizações de atualizações de software HoloLens antes de estarem disponíveis para o público em geral.

[Obtenha a pré-visualização do Windows Insider para o Microsoft HoloLens](hololens-insider.md).
