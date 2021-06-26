---
title: Atualizar HoloLens 2
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
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924116"
---
# <a name="update-hololens-2"></a>Atualizar HoloLens 2

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

## <a name="go-back-to-a-previous-version"></a>Volte para uma versão anterior

Em alguns casos, talvez queira voltar a uma versão anterior do software HoloLens. Os passos recomendados são:

1. Contacte o Suporte para ver se eles podem corrigir o seu problema.
    1. Certifique-se de que a telemetria **Opcional** ou **Completa** está ativada - isto torna o seu bug mais accuível e mais fácil para os engenheiros diagnosticarem.
    1. [O feedback do ficheiro](hololens-feedback.md) é o mais descritivo possível. Tome nota do título ou use a funcionalidade de partilha para que possa partilhar o seu bug com o Suporte.
    1. [Suporte de](https://aka.ms/hlsupport)contato . Se o seu problema for um problema que precisa de ser resolvido retornando a uma versão anterior, eles podem fornecer-lhe a FFU para piscar o seu dispositivo.

1. Se isso não funcionar, em seguida, [reinicie ou reflash seus HoloLens 2 com o Companheiro de Recuperação Avançado](hololens-recovery.md).
    1. No seu PC, descarregue o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.
    1. Certifique-se de que não tem telefones ou dispositivos Windows ligados ao seu PC.
    1. Escolha a versão a que pretende piscar:
        1. Você pode baixar o [mais recente lançamento HoloLens 2](https://aka.ms/hololens2download).
        1. Pode utilizar a construção padrão que o ARC acolhe. (Se escolher esta opção, salte o passo seguinte.)
        1. Você pode usar uma construção Suporte fornecido com você.
    1. Quando terminar estes downloads, abra as  >  **transferências do** File Explorer . Clique com o botão direito na pasta com fecho que acabou de descarregar e **selecione Extrair todo** o  >  **Extrato** para desapertá-la.
    1. Ligue os HoloLens ao seu PC utilizando um cabo USB-A a USB-C. (Mesmo que tenha usado outros cabos para ligar os hololens, este funciona melhor.)
    1. O Companheiro de Recuperação Avançada deteta automaticamente os seus HoloLens. Selecione o azulejo **microsoft HoloLens.**
    1. No ecrã seguinte, selecione **Manual** e, em seguida, selecione o ficheiro de instalação contido na pasta que abriu no passo 4. (Procure um ficheiro com a extensão .ffu.)
    1. **Selecione Instalar o software** e seguir as instruções.

> [!NOTE]
> Voltar a uma versão anterior elimina os seus ficheiros e configurações pessoais.

Além disso, se pretender manter-se no seu desbloqueio instalado atualmente, também pode interromper manualmente [as atualizações](hololens-updates.md#pause-updates-via-device). Isto dará tempo à Equipa de Engenharia para resolver o problema.

## <a name="windows-insider-program-on-hololens"></a>Programa Insider do Windows em HoloLens

Quer ver as últimas funcionalidades em HoloLens?  Em caso afirmativo, junte-se ao Programa Insider do Windows; terá acesso a pré-visualizações de atualizações de software HoloLens antes de estarem disponíveis para o público em geral.

[Obtenha a pré-visualização do Windows Insider para o Microsoft HoloLens](hololens-insider.md).
