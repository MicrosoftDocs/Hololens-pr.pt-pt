---
title: Partilhe o seu HoloLens com várias pessoas
description: Pode configurar HoloLens para serem partilhados por várias contas Azure Ative Directory ou por vários utilizadores que utilizem uma única conta.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033911"
---
# <a name="share-your-hololens-with-multiple-people"></a>Partilhe o seu HoloLens com várias pessoas

## <a name="overview"></a>Descrição Geral
As empresas muitas vezes investem em muitos dispositivos de HoloLens partilhados. A forma como utiliza HoloLens é flexível em todo o tabuleiro, dependendo dos seus requisitos individuais. Aqui está um exemplo de algumas experiências multiutilizadores: 

- Dispositivos carregados e com Dinâmicas 365 Guias e permitem que os seus colaboradores abram a aplicação Definições para fazer ajustes para Wi-Fi necessários, mas a política de visibilidade da Página Definições está habilitada a limitar as páginas de valor disponíveis na aplicação Definições.
- Dispositivos que são para Assistência Remota, e a sua linha de aplicação de negócios que são alugados a outras empresas. Estes dispositivos têm quiosques que incluem apenas a sua app e Assistência Remota. O WDAC é usado para impedir que a aplicação Definições e Microsoft Edge seja lançada. Incluído com o aluguer é uma bateria USB-C para manter os dispositivos em carga completa durante vários turnos.
- Todos os seus dispositivos estão configurado para o Autopilot e descarregam todas as aplicações da sua empresa. Você definiu alguns perfis de quiosque diferentes, direcionando diferentes grupos AD Azure. Cada utilizador entra no HoloLens utilizando as teclas FIDO2 e assinando na sua própria conta AZure AD, e é apresentado com uma experiência personalizada.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Partilhe com várias pessoas, cada uma usando a sua própria conta

**Pré-requisito**: O dispositivo HoloLens deve estar em funcionamento Windows 10, versão 1803 ou posterior.  HoloLens (1ª geração) também precisam de ser [atualizados para Windows Holographic for Business](hololens-upgrade-enterprise.md).

Quando utilizam as suas próprias contas de Azure Ative Directory (Azure AD), vários utilizadores podem manter as suas próprias definições de utilizador e dados do utilizador no dispositivo.

Para garantir que várias pessoas podem usar as suas próprias contas na sua HoloLens, siga estes passos para configurá-lo:

1. Certifique-se de que o aparelho está a funcionar Windows 10, versão 1803 ou posterior.
   > [!IMPORTANT]
   > Se estiver a utilizar um dispositivo HoloLens (1ª geração), [atualize o dispositivo para Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Quando configurar o dispositivo, selecione O meu trabalho ou escola é dono dele e **inscreva-se** utilizando uma conta AD Azure.
1. Depois de terminar a configuração, certifique-se de que as definições da conta (**Definições**  >  **Contas)** incluem **Outros utilizadores**.

Para utilizar HoloLens, cada utilizador segue estes passos:

1. Se outro utilizador tiver usado o dispositivo, escolha uma das seguintes opções:
   - Pressione o botão de alimentação uma vez para ir para o standby e, em seguida, pressione o botão de alimentação novamente para voltar ao ecrã de bloqueio
   - HoloLens 2 utilizadores podem selecionar o azulejo do utilizador a partir do menu Iniciar para assinar o utilizador atual.

1. Utilize as suas credenciais de conta AZure AD para iniciar scontabilidade no dispositivo.  
    Se é a primeira vez que usas o dispositivo, tens de [calibrar](hololens-calibration.md) HoloLens aos teus próprios olhos.

Para ver uma lista dos utilizadores do dispositivo ou para remover um utilizador do dispositivo, vá a **Definições**  >  **Contas**  >  **Outros utilizadores**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Partilhar com várias pessoas, todos usando a mesma conta

Vários utilizadores também podem partilhar um dispositivo HoloLens enquanto utilizam uma única conta de utilizador.

**No dia 2 HoloLens**, quando um novo utilizador coloca o dispositivo na cabeça pela primeira vez (mantendo a mesma conta assinada), o dispositivo solicita ao novo utilizador que calibra e personalize rapidamente a experiência de visualização. O dispositivo pode armazenar a informação de calibração para que, no futuro, o dispositivo possa otimizar automaticamente a qualidade e o conforto da experiência de visualização de cada utilizador. Os utilizadores não precisam de voltar a calibrar o dispositivo.

**No HoloLens (1º género)** os utilizadores que partilhem uma conta terão de pedir para recalibrar na aplicação Definições.  Leia mais sobre [a calibração.](hololens-calibration.md)