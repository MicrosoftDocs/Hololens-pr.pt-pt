---
title: Partilhe o seu HoloLens com várias pessoas
description: Pode configurar HoloLens para serem partilhados por várias contas Azure Ative Directory ou por vários utilizadores que utilizem uma única conta.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663082"
---
# <a name="share-your-hololens-with-multiple-people"></a>Partilhe o seu HoloLens com várias pessoas

É comum partilhar um HoloLens com muitas pessoas ou ter muitas pessoas a partilhar um conjunto de dispositivos HoloLens.  Este artigo descreve as diferentes formas de partilhar um dispositivo.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Partilhe com várias pessoas, cada uma usando a sua própria conta

**Pré-requisito**: O dispositivo HoloLens deve estar em funcionamento Windows 10, versão 1803 ou posterior.  HoloLens (1ª geração) também precisam de ser [atualizados para Windows Holographic for Business](hololens-upgrade-enterprise.md).

Quando utilizam as suas próprias contas de Azure Ative Directory (Azure AD), vários utilizadores podem manter as suas próprias definições de utilizador e dados do utilizador no dispositivo.

Para garantir que várias pessoas podem usar as suas próprias contas na sua HoloLens, siga estes passos para configurá-lo:

1. Certifique-se de que o aparelho está em funcionamento Windows 10, versão 1803 ou posterior.
   > [!IMPORTANT]
   > Se estiver a utilizar um dispositivo HoloLens (1ª geração), [atualize o dispositivo para Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Quando configurar o dispositivo, selecione O meu trabalho ou escola é dono dele e **inscreva-se** utilizando uma conta AD Azure.
1. Depois de terminar a configuração, certifique-se de que as definições da conta (**Definições**  >  **Contas)** incluem **Outros utilizadores**.

Para utilizar HoloLens, cada utilizador segue estes passos:

1. Se outro utilizador tiver usado o dispositivo, faça um dos seguintes:
   - Pressione o botão de alimentação uma vez para ir para o standby e, em seguida, pressione o botão de alimentação novamente para voltar ao ecrã de bloqueio
   - HoloLens 2 utilizadores podem selecionar o azulejo do utilizador a partir do menu Iniciar para assinar o utilizador atual.

1. Utilize as suas credenciais de conta AZure AD para iniciar scontabilidade no dispositivo.  
    Se esta é a primeira vez que usa o dispositivo, tem de [calibrar](hololens-calibration.md) HoloLens aos seus próprios olhos.

Para ver uma lista dos utilizadores do dispositivo ou para remover um utilizador do dispositivo, vá a **Definições**  >  **Contas**  >  **Outros utilizadores**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Partilhar com várias pessoas, todos usando a mesma conta

Vários utilizadores também podem partilhar um dispositivo HoloLens enquanto utilizam uma única conta de utilizador.

**No dia 2 HoloLens**, quando um novo utilizador coloca o dispositivo na cabeça pela primeira vez (mantendo a mesma conta assinada), o dispositivo solicita ao novo utilizador que calibra e personalize rapidamente a experiência de visualização. O dispositivo pode armazenar a informação de calibração para que, no futuro, o dispositivo possa otimizar automaticamente a qualidade e o conforto da experiência de visualização de cada utilizador. Os utilizadores não precisam de voltar a calibrar o dispositivo.

**No HoloLens (1º género)** os utilizadores que partilhem uma conta terão de pedir para recalibrar na aplicação Definições.  Leia mais sobre [a calibração.](hololens-calibration.md)
