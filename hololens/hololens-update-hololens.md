---
title: Atualização HoloLens 2
description: Saiba como verificar o seu HoloLens construir o número, manter-se atualizado com as atualizações do dispositivo, juntar-se ao Programa Insiders e reverter as atualizações.
keywords: como, atualizar, reverter, HoloLens, verificar construção, número de construção
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: f39fc2c6c0aaf16f304f38216a424c3811eb439d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427071"
---
# <a name="update-hololens-2"></a>Atualização HoloLens 2

## <a name="overview"></a>Descrição Geral

Estamos sempre a trabalhar em novas funcionalidades, correções de bugs e atualizações de segurança. Será notificado quando estas atualizações estiverem prontas.

Com base na sua preferência, o seu HoloLens descarregará e instalará automaticamente atualizações do sistema sempre que estiver ligado à energia, ligado à Internet e até mesmo em standby.

Para garantir que o seu HoloLens está sempre atualizado, deixe-o ligado ao carregador que o acompanha. Também quer que o seu HoloLens ligado à internet. Desta forma, irá descarregar e instalar automaticamente atualizações do sistema. 

Com Windows serviço Update, irá controlar vários aspetos do processo de atualização, tais como quais os dispositivos que obtêm quais atualizações a que horas. Este controlo é útil porque pode lançar atualizações para um subconjunto de HoloLens dispositivos para testes. Em seguida, lançar atualizações para as restantes. Ou, pode definir diferentes horários de atualização para diferentes tipos de atualizações.

## <a name="types-of-updates"></a>Tipos de atualizações

Para HoloLens, pode gerir automaticamente dois tipos de atualizações. 

- Atualizações de recursos: lançadas duas vezes por ano.
- Atualizações de qualidade: inclua atualizações críticas de segurança. São libertados mensalmente, ou conforme necessário.

Use **a atualização** / **AllowAutoUpdate** para gerir a digitalização, o download e a instalação de atualizações. 

## <a name="scheduling-updates"></a>Atualizações de agendamento

Também pode definir um calendário de atualização. Pode ser num dia em particular, ou todos os dias, num determinado momento. Por exemplo, a 5.m., ou fora do horário ativo.

Finalmente, algumas palavras sobre como planear a sua estratégia de atualização. Apoiamos atualização de adiamentos. Assim, pode decidir quanto tempo esperar depois de a Microsoft lançar uma atualização para instalar essa atualização nos dispositivos.

Por vezes, uma empresa gosta de experimentar todas as novidades primeiro para garantir que tudo funciona, e estão familiarizados com as novas atualizações para que a sua equipa de suporte esteja preparada. Assim que confirmarem que está tudo bem, lançam as atualizações para toda a empresa. Ao associar subconjuntos dos seus dispositivos com diferentes políticas de diferimento, conhecidas como anéis de atualização, pode coordenar uma estratégia de lançamento de atualização para a sua organização.

## <a name="hololens-update-tools"></a>HoloLens ferramentas de atualização

Esta secção irá acompanhá-lo através de HoloLens ferramentas para:

- verificação de atualizações
- atualizar manualmente HoloLens
- visualizando a sua versão atual do sistema operativo (número de construção)
- voltando para uma atualização mais antiga

### <a name="check-for-updates-and-manually-update"></a>Verifique as atualizações e atualização manual

Pode verificar se há atualizações a qualquer momento nas definições.  Para ver as atualizações disponíveis e verificar novas atualizações:

1. Abra a aplicação **Definições**.
1. Navegue para **atualizar Windows de segurança**&  >  **atualização**.
1. Selecione **Procurar atualizações**.

Se houver uma atualização disponível, começará a descarregar a nova versão. Depois de concluída a transferência, selecione o botão **Restart Now** para ativar a instalação. Se o seu dispositivo estiver abaixo dos 40% e não estiver ligado, o reinício não começará a instalar a atualização.

Enquanto o seu HoloLens estiver a instalar a atualização, apresentará engrenagens giratórias e um indicador de progresso. Não desligue a HoloLens durante este tempo. Reiniciar-se-á automaticamente depois de concluída a instalação.

HoloLens aplica uma atualização de cada vez.  Se o seu HoloLens for mais do que uma versão por trás da mais recente, poderá ter de passar várias vezes pelo processo de atualização para o atualizar completamente.

### <a name="check-your-operating-system-version-build-number"></a>Verifique a versão do seu sistema operativo (número de construção)

Pode verificar o número da versão do sistema (número de construção) abrindo **Definições** e selecione **System**  >  **About**.

### <a name="go-back-to-a-previous-version"></a>Volte para uma versão anterior

Em alguns casos, é melhor voltar a uma versão anterior do software HoloLens. Os passos recomendados são:

1. Contacte o Suporte para ver se eles podem corrigir o seu problema.
    1. Certifique-se de que a telemetria **Opcional** ou **Completa** está ativada - isto torna o seu bug mais accuível e mais fácil para os engenheiros diagnosticarem.
    1. [O feedback do ficheiro](hololens-feedback.md) é o mais descritivo possível. Tome nota do título ou use a funcionalidade de partilha para que possa partilhar o seu bug com o Suporte.
    1. [Suporte de](https://aka.ms/hlsupport)contato . Se o seu problema for um problema que precisa de ser resolvido retornando a uma versão anterior, eles podem fornecer-lhe a FFU para piscar o seu dispositivo.

1. Se isso não funcionar, [reinicie ou reflash o seu HoloLens 2 com o Companheiro de Recuperação Avançado](hololens-recovery.md).
    1. No seu PC, descarregue o [Avançado Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) do Microsoft Store.
    1. Certifique-se de que não tem telefones ou dispositivos Windows ligados ao seu PC.
    1. Escolha a versão a que pretende piscar:
        1. Pode baixar o [mais recente HoloLens versão 2](https://aka.ms/hololens2download).
        1. Pode utilizar a construção padrão que o ARC acolhe. (Se escolher esta opção, salte o passo seguinte.)
        1. Você pode usar uma construção Suporte fornecido com você.
    1. Quando terminar estes downloads, abra as  >  **transferências do** File Explorer . Clique com o botão direito na pasta com fecho que descarregou e **selecione Extrair todo o**  >  **Extrato** para desapertá-la.
    1. Ligação o seu HoloLens para o seu PC utilizando um cabo USB-A para USB-C. (Mesmo que tenha usado outros cabos para ligar o seu HoloLens, este funciona melhor.)
    1. O Companheiro de Recuperação Avançada deteta automaticamente o seu HoloLens. Selecione o **azulejo Microsoft HoloLens.**
    1. No ecrã seguinte, selecione **Manual** e, em seguida, selecione o ficheiro de instalação contido na pasta que abriu no passo 4. (Procure um ficheiro com a `.ffu` extensão.)
    1. **Selecione Instalar o software** e seguir as instruções.

> [!NOTE]
> Voltar a uma versão anterior elimina os seus ficheiros e configurações pessoais.

Além disso, se pretender manter-se no seu desbloqueio instalado atualmente, também pode interromper manualmente [as atualizações](hololens-updates.md#pause-updates-via-device). Isto dará tempo à Equipa de Engenharia para resolver o problema.

## <a name="windows-insider-program-on-hololens"></a>Windows Programa Insider em HoloLens

Quer ver as últimas funcionalidades em HoloLens?  Em caso afirmativo, junte-se ao Programa insider Windows; terá acesso a pré-visualizações de HoloLens atualizações de software antes de estarem disponíveis para o público em geral.

[Obtenha Windows pré-visualização do Insider para Microsoft HoloLens](hololens-insider.md).