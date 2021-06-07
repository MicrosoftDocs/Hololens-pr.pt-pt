---
title: Reiniciar, reiniciar ou recuperar HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Como usar o Advanced Recovery Companion para mostrar uma imagem ao HoloLens 2.
keywords: como, reiniciar, reiniciar, recuperar, reset duro, reset suave, ciclo de potência, HoloLens, desligado, arco, companheiro de recuperação avançado
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: afd782df1c68e8441b14823e0d961317914140e3
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379903"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Reiniciar, reiniciar ou recuperar HoloLens 2

## <a name="charge-the-device"></a>Carregue o dispositivo

>[!IMPORTANT]
> Antes de iniciar qualquer procedimento de resolução de problemas, certifique-se de que o seu dispositivo está carregado até **20 a 40%** da capacidade da bateria, se possível. As [luzes indicadoras](hololens2-setup.md#lights-that-indicate-the-battery-level) da bateria localizadas sob o botão de alimentação são uma forma rápida de verificar a capacidade da bateria sem iniciar sessão no dispositivo.

Utilize o [carregador e o cabo USB Type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) que veio com o HoloLens 2, pois esta é a melhor maneira de carregar o seu dispositivo. O carregador fornece 18W de potência (9V a 2A). Utilizando o carregador de parede fornecido, os dispositivos HoloLens 2 podem carregar a bateria até à totalidade em menos de 65 minutos quando o dispositivo estiver em modo de espera. Se esses acessórios não estiverem disponíveis, certifique-se de que o carregador disponível pode suportar pelo menos 15W de energia.

> [!NOTE]
> Se possível, evite utilizar um PC para carregar o dispositivo em USB, o que é lento.

Se o dispositivo estiver corretamente iniciado e em funcionamento, existem três formas de verificar o nível de carga da bateria:

- A partir do menu principal do dispositivo HoloLens UI.
- Ver o LED perto do botão de alimentação (para uma carga de 40%, deverá ver pelo menos dois LED sólidos).
    - Quando o aparelho está a carregar, o indicador da bateria acende-se para indicar o nível de carga atual.  A última luz desvanece-se para dentro e para fora para indicar o carregamento ativo.
    - Quando os HoloLens estiverem ligados, o indicador da bateria mostra o nível da bateria em cinco incrementos.
    - Quando apenas uma das cinco luzes está acesa, o nível da bateria está abaixo dos 20%.
    - Se o nível da bateria estiver criticamente baixo e tentar ligar o dispositivo, uma luz piscará brevemente e apagar-se-á.
- No seu PC anfitrião, abra o **File Explorer** e procure o seu dispositivo HoloLens 2 no lado esquerdo sob **este PC**. Clique com o botão direito no dispositivo e selecione **Propriedades**. Uma caixa de diálogo mostrará o nível de carga da bateria.

   ![Um ecrã de propriedades HoloLens 2 mostra o nível de mudança de bateria](images/ResetRecovery2.png)

Se o dispositivo não conseguir arrancar no menu de arranque, note a aparência LED e a enumeração do dispositivo no PC anfitrião. Em seguida, siga o [guia de resolução de problemas](hololens-troubleshooting.md). Se o estado do dispositivo não corresponder a nenhum dos estados listados no guia de resolução de problemas, execute o [procedimento de reset duro](hololens-recovery.md#hard-reset-procedure) com o dispositivo ligado à alimentação elétrica e não com o seu PC anfitrião. Espere pelo menos uma hora para o dispositivo carregar.

## <a name="reset-the-device"></a>Reiniciar o dispositivo

Em determinadas circunstâncias, poderá ter de reiniciar manualmente o dispositivo sem utilizar o UI do software.

### <a name="standard-procedure"></a>Procedimento padrão

1. Desligue o cabo Type-C para desligar o dispositivo da alimentação ou do PC de hospedeiro.

2. Pressione e segure o botão **de alimentação** durante 15 segundos. Todos os LEDs devem estar desligados.

3. Aguarde 2-3 segundos e, em seguida, pressione o botão **de alimentação.** Os LEDs perto do botão de alimentação acendem-se e o dispositivo começará a arrancar.

4. Ligue o dispositivo ao PC anfitrião e, em seguida, abra o Gestor de Dispositivos. (Para o Windows 10, prima a tecla **Windows** e, em seguida, a tecla **X** e, em seguida, selecione **o Gestor de Dispositivos**.) Certifique-se de que o dispositivo enumera corretamente como *Microsoft HoloLens* como mostrado na seguinte imagem:

   ![HoloLens 2 MicrosoftHoloLensRecovery gestor devive](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Procedimento de reset difícil

Se o procedimento de reset padrão não funcionar, utilize o procedimento de reset rígido:

1. Desligue o cabo Type-C para desligar o dispositivo da alimentação ou do PC de hospedeiro.

2. Mantenha **premidos** os  +  botões **de potência** durante 15 segundos. O aparelho reiniciará automaticamente.

4. Ligue o dispositivo ao PC anfitrião.

5. Abra o Gestor de Dispositivos (para o Windows 10 prima a tecla **Windows** e, em seguida, a tecla **X** e, em seguida, selecione **o Gestor de Dispositivos).** Certifique-se de que o dispositivo enumera corretamente como *Microsoft HoloLens* como mostrado na seguinte imagem:

   ![HoloLens 2 MicrosoftHoloLensRecovery dispositivo maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Limpar o dispositivo

Em situações extraordinárias, pode ter de "limpar" os HoloLens 2. Por favor, note que não se espera que o reflash limpo afete os seguintes problemas:
- [Uniforme de cor do ecrã](hololens2-display.md)
- Arranque com som mas sem saída de exibição
- [Padrão de 1-3-5-LED](hololens2-setup.md#lights-to-indicate-problems)
- [Sobreaquecimento](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Acidentes de SO (que são distintos de falhas de aplicação)

Há duas maneiras de reflash o dispositivo. Para ambos, tem primeiro de [instalar o Advanced Recovery Companion a partir da Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).

>[!WARNING]
>Se voltar a colocar o seu dispositivo, todos os seus dados pessoais, aplicações e configurações serão apagados, incluindo informações de reset TPM.

Por predefinição, Advanced Recovery Companion está programado para descarregar a mais recente construção de lançamento de funcionalidades, consulte aqui para ler as [nossas notas de Lançamento](hololens-release-notes.md#) para saber mais sobre a versão mais recente da funcionalidade. Para obter o mais recente pacote HoloLens 2 Full Flash Update (FFU) para reflash o seu dispositivo através do Advanced Recovery Companion, [clique aqui para descarregar a mais recente imagem mensal dos HoloLens 2](https://aka.ms/hololens2download). Esta versão é a mais recente construção geralmente disponível.

Antes de iniciar o procedimento de reflash, certifique-se de que a aplicação está instalada e a funcionar no seu PC Windows 10 e pronta para detetar o dispositivo. Certifique-se também de que os seus HoloLens são cobrados a um mínimo de 40%.

![HoloLens 2 tiro de tela de reflash limpo](images/ARC1.png)

### <a name="normal-procedure"></a>Procedimento normal

1. Enquanto o dispositivo HoloLens estiver em funcionamento, conecte-o ao PC do Windows 10, onde abriu previamente a aplicação Advanced Recovery Companion.
 
   O dispositivo será detetado automaticamente e a UI da aplicação Advanced Recovery Companion iniciará o processo de atualização:

   ![HoloLens 2 limpa reflash ecrã inicial](images/ARC2.png)

3. Selecione o dispositivo HoloLens 2 na UI da aplicação Advanced Recovery Companion e siga as instruções para completar o reflash.

### <a name="manual-procedure"></a>Procedimento manual

Se o HoloLens 2 não arrancar corretamente ou se o Avançado Recovery Companion não conseguir detetar o dispositivo, poderá ter de colocar o dispositivo no modo de recuperação:

1. Desligue o cabo Type-C para desligar o dispositivo da alimentação ou do PC de hospedeiro.

2. Pressione e segure o botão **de alimentação** durante 15 segundos. Todos os LEDs devem desligar.

3. Enquanto pressiona o botão **de volume para cima,** prima e liberte o botão **de alimentação** para ligar o dispositivo. Aguarde 15 segundos e, em seguida, liberte o botão **de volume para cima.** Apenas o LED médio dos cinco LEDs acende-se.

4. Ligue o dispositivo ao PC anfitrião e abra o Gestor de Dispositivos. (Para o Windows 10 prima a tecla **Windows** e, em seguida, a tecla **X** e, em seguida, selecione **O Gestor de Dispositivos**.) Certifique-se de que o dispositivo enumera corretamente como Microsoft HoloLens como mostrado na seguinte imagem:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   O dispositivo será detetado automaticamente e a UI da aplicação Advanced Recovery Companion iniciará o processo de atualização:

   ![HoloLens 2 ecrã de reflash limpo](images/ARC2.png)

6. Selecione o dispositivo HoloLens 2 na UI da aplicação Advanced Recovery Companion e, em seguida, siga as instruções para completar o reflash.

## <a name="troubleshoot-advanced-recovery-companion"></a>Troubleshoot Advanced Recovery Companion

1. Certifique-se de que o seu dispositivo está carregado até 40% ou mais antes de tentar piscar.

2. Verifique se o seu dispositivo está desbloqueado.

3. Se o ARC não detetar o seu dispositivo, certifique-se de que pode ligar-se ao seu dispositivo através do File Explorer no seu PC. Se não puder;

    1.  É possível que o seu dispositivo possa ter políticas USB que desativem essa ligação. Em caso afirmativo, experimente [o modo de piscar manual](hololens-recovery.md#manual-procedure).
    2.  Se não houver políticas, experimente um cabo USB diferente.

1. Verifique se o seu dispositivo não apresenta um [padrão de 1-3-5 LED](hololens2-setup.md#lights-to-indicate-problems).

## <a name="download-arc-without-using-the-app-store"></a>Descarregue o ARC sem utilizar a loja de aplicações

Se o ambiente de TI impedir a utilização da aplicação windows Store ou limitar o acesso à loja de retalho, o administrador de TI pode disponibilizar esta aplicação através de uma via de implementação "offline".

 >[!NOTE]
 > - Os administradores de TI também podem distribuir esta aplicação através do System Center Configuration Manager (SCCM) ou do Intune.
 > - Este guia foca-se no Advanced Recovery Companion, mas o processo também pode ser usado para outras aplicações "offline".

Siga estes passos para permitir a via de implantação:

1. Vá à [Microsoft Store for Business](https://businessstore.microsoft.com) e inscreva-se com uma identidade do Azure Ative Directory.

1. Ir para **Gerir – Definições**. Ligue **as aplicações offline do Show** sob **experiência de Compras.**

1. Vá às **compras para o meu grupo** e procure o Avançado Recovery [**_Companion._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)

1. Altere o **Tipo de Licença** para **_offline_*_, e selecione _* Gerir**.

1. Em **Descarregue o pacote para uso offline,** selecione o segundo botão azul **Descarregar.** Certifique-se de que a extensão do ficheiro é *.appxbundle*.

    - Nesta fase, se o Pc desktop tiver acesso à Internet, clique duas vezes no pacote para instalar a aplicação.

    - Se o destino PC não tiver conectividade com a Internet, siga estes passos:
       1. Selecione a licença não codificada e, em seguida, **selecione Gerar licença**.
       2. Nos **quadros necessários**, selecione **Download**.
       3. Utilize o DISM para aplicar a embalagem com a dependência e a licença. A partir de um pedido de comando do administrador, executar o seguinte comando:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > O número da versão neste exemplo de código pode não corresponder à versão atualmente disponível. Você também pode ter escolhido um local de descarregamento diferente do que no exemplo. Faça quaisquer alterações ao comando conforme necessário.

> [!TIP]
> Quando planeia utilizar o Advanced Recovery Companion para instalar um FFU offline, pode ser útil descarregar a sua imagem flash. [**Descarregue a imagem atual para HoloLens 2**](https://aka.ms/hololens2download).


Outros recursos:
- [Distribuir aplicativos offline](/microsoft-store/distribute-offline-apps) 
- [Pacote de aplicativos DISM (.appx ou .appxbundle) opções de linha de comando](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
