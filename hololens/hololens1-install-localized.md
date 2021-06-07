---
title: Instalar versões localizadas de HoloLens
description: Saiba como instalar as versões localizadas do HoloLens (1º género), incluindo versões chinesas e japonesas.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378697"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Instalar versões localizadas de HoloLens (1º género)

Para mudar para a versão chinesa ou japonesa dos HoloLens, terá de utilizar a Ferramenta de Recuperação de Dispositivos do Windows (WDRT) para descarregar a construção para o idioma num PC e depois instalá-la nos seus HoloLens.

> [!IMPORTANT]
> A utilização do WDRT para instalar as construções chinesas ou japonesas de HoloLens elimina os dados existentes, tais como ficheiros pessoais e configurações, dos seus HoloLens. 

1. No seu PC, descarregue e instale [a Ferramenta de Recuperação de Dispositivos windows (WDRT)](https://support.microsoft.com/help/12379).
1. Descarregue o pacote para o idioma que deseja para o seu PC: [Chinês simplificado](https://aka.ms/hololensdownload-ch) ou [japonês.](https://aka.ms/hololensdownload-jp)
1. Quando o download terminar, selecione **Downloads do Explorador**  >  **de Ficheiros**. Clique com o botão direito na pasta com fecho que acabou de descarregar e **selecione Extrair todo** o  >  **Extrato** para desapertá-la.
1. Ligue os HoloLens ao seu PC utilizando o cabo micro-USB com o qual foi enviado. (Mesmo que tenha usado outros cabos para ligar os hololens, este funciona melhor.)
1. Depois de a ferramenta detetar automaticamente os hololens, selecione o azulejo Microsoft HoloLens.
1. No ecrã seguinte, selecione **Manual**   e selecione o ficheiro de instalação que reside na pasta que desapertou no passo 4. (Procure um ficheiro que tenha a extensão ".ffu".) 
1.  **Selecione Instalar o software** e seguir as instruções. 
1. Após a instalação da construção, a configuração HoloLens começa automaticamente. Coloque o dispositivo e siga as instruções de configuração. 

Quando terminar a configuração, vá ao **Update de Definições**  >  **& Programa De Segurança** Do Windows  >  **Insider** e verifique se está configurado para receber as mais recentes construções de pré-visualização. Tal como a pré-visualização em inglês, o Windows Insider Program mantém as versões chinesa e japonesa de HoloLens atualizadas com as mais recentes construções de pré-visualização.

> [!NOTE]
>  
> - Não é possível utilizar a aplicação Definições para alterar o idioma do sistema entre inglês, japonês e chinês. Piscar uma nova construção é a única forma suportada de alterar a linguagem do sistema do dispositivo.
> - Embora possa utilizar o teclado Pinyin no ecrã para introduzir textos chineses ou japoneses simplificados, usar um teclado de hardware Bluetooth para escrever texto chinês ou japonês simplificado não é suportado neste momento.  No entanto, em HoloLens chineses ou japoneses, pode continuar a utilizar um teclado Bluetooth para escrever em inglês (para alternar um teclado de hardware para escrever em inglês, prima a tecla ~).
