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
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="31e43-103">Instalar versões localizadas de HoloLens (1º género)</span><span class="sxs-lookup"><span data-stu-id="31e43-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="31e43-104">Para mudar para a versão chinesa ou japonesa dos HoloLens, terá de utilizar a Ferramenta de Recuperação de Dispositivos do Windows (WDRT) para descarregar a construção para o idioma num PC e depois instalá-la nos seus HoloLens.</span><span class="sxs-lookup"><span data-stu-id="31e43-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31e43-105">A utilização do WDRT para instalar as construções chinesas ou japonesas de HoloLens elimina os dados existentes, tais como ficheiros pessoais e configurações, dos seus HoloLens.</span><span class="sxs-lookup"><span data-stu-id="31e43-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="31e43-106">No seu PC, descarregue e instale [a Ferramenta de Recuperação de Dispositivos windows (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="31e43-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="31e43-107">Descarregue o pacote para o idioma que deseja para o seu PC: [Chinês simplificado](https://aka.ms/hololensdownload-ch) ou [japonês.](https://aka.ms/hololensdownload-jp)</span><span class="sxs-lookup"><span data-stu-id="31e43-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="31e43-108">Quando o download terminar, selecione **Downloads do Explorador**  >  **de Ficheiros**.</span><span class="sxs-lookup"><span data-stu-id="31e43-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="31e43-109">Clique com o botão direito na pasta com fecho que acabou de descarregar e **selecione Extrair todo** o  >  **Extrato** para desapertá-la.</span><span class="sxs-lookup"><span data-stu-id="31e43-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="31e43-110">Ligue os HoloLens ao seu PC utilizando o cabo micro-USB com o qual foi enviado.</span><span class="sxs-lookup"><span data-stu-id="31e43-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="31e43-111">(Mesmo que tenha usado outros cabos para ligar os hololens, este funciona melhor.)</span><span class="sxs-lookup"><span data-stu-id="31e43-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="31e43-112">Depois de a ferramenta detetar automaticamente os hololens, selecione o azulejo Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="31e43-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="31e43-113">No ecrã seguinte, selecione **Manual**   e selecione o ficheiro de instalação que reside na pasta que desapertou no passo 4.</span><span class="sxs-lookup"><span data-stu-id="31e43-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="31e43-114">(Procure um ficheiro que tenha a extensão ".ffu".)</span><span class="sxs-lookup"><span data-stu-id="31e43-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="31e43-115"> *\*Selecione Instalar o software** e seguir as instruções.</span><span class="sxs-lookup"><span data-stu-id="31e43-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="31e43-116">Após a instalação da construção, a configuração HoloLens começa automaticamente.</span><span class="sxs-lookup"><span data-stu-id="31e43-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="31e43-117">Coloque o dispositivo e siga as instruções de configuração.</span><span class="sxs-lookup"><span data-stu-id="31e43-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="31e43-118">Quando terminar a configuração, vá ao **Update de Definições**  >  **& Programa De Segurança** Do Windows  >  **Insider** e verifique se está configurado para receber as mais recentes construções de pré-visualização.</span><span class="sxs-lookup"><span data-stu-id="31e43-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="31e43-119">Tal como a pré-visualização em inglês, o Windows Insider Program mantém as versões chinesa e japonesa de HoloLens atualizadas com as mais recentes construções de pré-visualização.</span><span class="sxs-lookup"><span data-stu-id="31e43-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="31e43-120">Não é possível utilizar a aplicação Definições para alterar o idioma do sistema entre inglês, japonês e chinês.</span><span class="sxs-lookup"><span data-stu-id="31e43-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="31e43-121">Piscar uma nova construção é a única forma suportada de alterar a linguagem do sistema do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="31e43-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="31e43-122">Embora possa utilizar o teclado Pinyin no ecrã para introduzir textos chineses ou japoneses simplificados, usar um teclado de hardware Bluetooth para escrever texto chinês ou japonês simplificado não é suportado neste momento.</span><span class="sxs-lookup"><span data-stu-id="31e43-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="31e43-123">No entanto, em HoloLens chineses ou japoneses, pode continuar a utilizar um teclado Bluetooth para escrever em inglês (para alternar um teclado de hardware para escrever em inglês, prima a tecla ~).</span><span class="sxs-lookup"><span data-stu-id="31e43-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
