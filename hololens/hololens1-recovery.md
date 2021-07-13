---
title: Reiniciar, reiniciar ou recuperar HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Como utilizar Windows Ferramenta de Recuperação de Dispositivos para mostrar uma imagem a HoloLens 1ª Gen.
keywords: como, reiniciar, reiniciar, recuperar, reset duro, reset suave, ciclo de potência, HoloLens, desligar, wdrt, ferramenta de recuperação do dispositivo windows
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635233"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Reiniciar, reiniciar ou recuperar HoloLens (1ª Gen)

Se estiver a ter problemas com o seu HoloLens, pode querer reiniciar ou reiniciar ou até reflash o dispositivo utilizando a recuperação do dispositivo. Este artigo guia-o através dos passos de recuperação recomendados em ordem.

Se procura recuperar um HoloLens 2, consulte [Recuperar um HoloLens 2](hololens-recovery.md), uma vez que esse processo difere.

> [!NOTE]
> Este artigo centra-se no dispositivo e software HoloLens. Se os seus hologramas não parecerem adequados, consulte **[HoloLens considerações ambientais](hololens-environment-considerations.md)** para obter informações sobre fatores que melhorem a qualidade do holograma.

## <a name="restart"></a>Reiniciar

### <a name="do-a-safe-restart-by-using-cortana"></a>Faça um reinício seguro utilizando Cortana

A forma mais segura de reiniciar o HoloLens é usando Cortana, que geralmente é a primeira coisa a tentar quando se experimenta um problema com HoloLens.

> [!NOTE] 
> Cortana não está disponível em todos os dispositivos.
> - Cortana está disponível em todos os dispositivos HoloLens (1ª Gen). 
> - Cortana está disponível em HoloLens 2 dispositivos em construções antes da atualização holograpic, versão 2004 da Windows.

1. Ligue o HoloLens.
1. Certifique-se de que um utilizador está a iniciar sessão e que o dispositivo não está à espera de uma palavra-passe para o desbloquear.
2. Diz "Ei Cortana, reinicie" ou "Ei Cortana, reinicie".
3. Cortana responderão e pedir-lhe-ão que confirme. Espere um som para tocar depois da pergunta, e depois diga "Sim". O dispositivo vai reiniciar.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Use o botão de alimentação para fazer um reinício seguro

Se ainda não conseguir reiniciar o seu dispositivo, tente reiniciá-lo utilizando o botão **de alimentação:**

1. Pressione e segure o botão **de alimentação** durante 5 segundos. Após 1 segundo, todos os cinco LEDs iluminar-se-ão e, em seguida, desligar-se-ão lentamente um a um da direita para a esquerda. Após 5 segundos, todos os LEDs estarão desligados, indicando uma paragem bem sucedida.
      
   > [!IMPORTANT]
   > Pare de premir o botão imediatamente depois de todos os LEDs terem desligado.
1. Espere 1 minuto para a paralisação estar completa. A paralisação pode ainda estar em curso mesmo depois de os visores estarem desligados.
2. Volte a ligar o aparelho premindo e segurando o botão **de alimentação** durante 1 segundo.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Faça um reinício seguro utilizando o Portal do Dispositivo Windows

> [!NOTE]
> Para este processo, HoloLens tem de ser configurado como um dispositivo de desenvolvimento. Saiba mais no [Portal Windows dispositivo.](/windows/mixed-reality/using-the-windows-device-portal)

Se o procedimento anterior não funcionar, tente reiniciar o dispositivo utilizando [Windows Portal do Dispositivo](/windows/mixed-reality/using-the-windows-device-portal). No canto superior direito, encontre a opção de reiniciar ou desligar o dispositivo.

### <a name="do-an-unsafe-forced-restart"></a>Faça um reinício forçado inseguro

Se os métodos anteriores não reiniciarem a sua HoloLens, force um recomeço. Este método equivale a remover e reinstalar a bateria. É perigoso porque pode deixar o seu dispositivo num estado corrompido. Se isso acontecer, terás de mostrar a tua HoloLens.  

> [!WARNING]
> Este é um método potencialmente prejudicial e só deve ser usado se os métodos anteriormente citados não funcionarem.

1. Pressione e segure o botão **de alimentação** durante pelo menos 10 segundos.
   - Não faz mal segurar o botão por mais de 10 segundos.
   - É seguro ignorar qualquer atividade LED.
1. Solte o botão e aguarde 2-3 segundos.
1. Pressione e segure o botão **de alimentação** durante 1 segundo.
1. Se ainda tiver problemas, prima o botão **de alimentação** durante 4 segundos, até que todos os indicadores da bateria se desvaneçam e o ecrã deixe de exibir hologramas. Aguarde 1 minuto e, em seguida, prima novamente o botão **de alimentação** para ligar o dispositivo.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Volte para uma versão anterior - HoloLens (1ª Gen)

Em alguns casos, é melhor voltar a uma versão anterior do software HoloLens. Pode fazê-lo utilizando a Ferramenta de Recuperação do Dispositivo Windows para redefinir o seu HoloLens para a versão anterior.

> [!NOTE]
> Voltar a uma versão anterior elimina os seus ficheiros e configurações pessoais.

Para voltar a uma versão anterior do HoloLens 1, siga estes passos:

1. Certifique-se de que não tem telefones ou dispositivos Windows ligados ao seu PC.
1. No seu PC, descarregue a [Ferramenta de Recuperação de Dispositivos Windows (WDRT)](https://support.microsoft.com/help/12379).
1. Descarregue o [pacote de recuperação da Atualização de Aniversário HoloLens](https://aka.ms/hololensrecovery).
1. Quando os downloads terminarem, abra o **Explorador de**  >  **Ficheiros Downloads**. Clique com o botão direito na pasta com fecho que acabou de descarregar e **selecione Extrair todo** o  >  **Extrato** para desapertá-la.
1. Ligação o seu HoloLens para o seu PC utilizando o cabo micro-USB que ele veio. (Mesmo que tenha usado outros cabos para ligar o seu HoloLens, este funciona melhor.)
1. O WDRT detetará automaticamente o seu HoloLens. Selecione o **azulejo Microsoft HoloLens.**
1. No ecrã seguinte, selecione **Manual** e escolha o ficheiro de instalação contido na pasta que abriu no passo 4. (Procure um ficheiro com a extensão .ffu.)
1. **Selecione Instalar o software** e seguir as instruções.

> [!NOTE]
> Se o WDRT não detetar a sua HoloLens, tente reiniciar o seu PC. Se isso não funcionar, selecione **O meu dispositivo não foi detetado**, selecione **Microsoft HoloLens** e, em seguida, siga as instruções.

## <a name="reset-to-factory-settings"></a>Reset para as definições de fábrica

> [!NOTE]
> A bateria precisa de pelo menos uma carga de 40% para ser reposta.

Se o seu HoloLens ainda tiver um problema, tente repor o estado da fábrica. Este passo mantém a versão do software Holográfico Windows que está instalado no mesmo e devolve tudo o resto às definições de fábrica.

>[!WARNING]
> Se reiniciar o seu dispositivo, todos os seus dados pessoais, aplicações e configurações serão apagados, incluindo informações de reset TPM. A reposição só instalará a versão mais recente instalada do Windows Holographic. Terá de refazer todos os passos de inicialização (calibrar, ligar ao Wi-Fi, criar uma conta de utilizador, descarregar apps, e assim por diante).

1. Abra a aplicação Definições e, em seguida, selecione **Update**  >  **Recovery**.
1. Selecione a opção **do dispositivo Reset** e leia a mensagem de confirmação.
1. Confirme o reset. O aparelho reiniciará e exibirá um conjunto de engrenagens giratórias e uma barra de progresso.
1. Espere cerca de 30 minutos para que este processo esteja concluído. Quando estiver feito, o dispositivo reiniciará a experiência "fora da caixa".

## <a name="reinstall-the-operating-system"></a>Reinstalar o sistema operativo

Se o dispositivo ainda tiver um problema após o reinício e reinicialização, pode utilizar uma ferramenta de recuperação no seu computador para reinstalar o sistema operativo HoloLens e o firmware.  

Os dados que HoloLens necessidades para o reset são embalados numa Atualização Flash Completa (FFU), que é semelhante a um ficheiro .iso, .wim ou .vhd. [Saiba mais sobre os formatos de ficheiros de imagem FFU.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Pode instalar um novo sistema operativo no seu HoloLens (1º gênero) utilizando a Ferramenta de Recuperação de Dispositivos Windows. Antes de utilizar esta ferramenta, consulte se reiniciar ou reiniciar o seu HoloLens corrige o problema.

O processo de recuperação pode demorar um pouco. Quando estiver feito, será instalada a versão mais recente do software Holográfico Windows.

Para utilizar a ferramenta, precisa de um computador a funcionar Windows 10 ou mais tarde com pelo menos 4 GB de espaço de armazenamento gratuito. Não podes executar esta ferramenta numa máquina virtual.

### <a name="recover-your-hololens"></a>Recupere o seu HoloLens

1. Descarregue e instale a [Ferramenta de Recuperação de Dispositivos Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) no seu computador.
1. Ligação o HoloLens (1º gênero) ao seu computador utilizando o cabo Micro USB que veio com o seu HoloLens.
1. Abra a ferramenta de recuperação do dispositivo Windows e siga as instruções.

Se a HoloLens (1ª gen) não for detetada automaticamente, selecione **O meu dispositivo não foi detetado**. Em seguida, siga as instruções para colocar o aparelho no modo de recuperação.

### <a name="manual-flashing-mode"></a>Modo de piscar manual

Se o seu dispositivo não for detetado, siga estes passos para colocá-lo no modo intermitente:

1. Desligue o aparelho de qualquer fonte de energia.
1. Se o dispositivo estiver ligado, mantenha premida o botão **de alimentação** até que se desligue completamente.
2. Segure o botão **de volume para cima** e toque brevemente no botão de **alimentação.** O aparelho deve iniciar e exibir apenas o LED médio.
3. Ligue o dispositivo ao seu PC.
4. Abra a ferramenta de recuperação do dispositivo Windows.
5. Selecione **O meu dispositivo não foi detetado** e, em seguida, **HoloLens**. 
6. Siga as instruções para recuperar o seu dispositivo.
