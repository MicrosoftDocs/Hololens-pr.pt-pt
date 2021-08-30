---
title: Cenários Comuns - Offline Secure HoloLens 2
description: Saiba como configurar um cenário de implementação e implementação de aplicações de segurança offline com provisão para dispositivos HoloLens.
keywords: HoloLens, gestão, offline, offline seguro
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 10d1955249630202a05fbf2057e1d175855ce0b5
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189125"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Cenários Comuns - Offline Secure HoloLens 2

## <a name="overview"></a>Descrição Geral

Este guia fornece orientações para a aplicação de um pacote de provisionamento de amostra que bloqueie um HoloLens 2 para utilização em ambientes seguros com as seguintes restrições:

-   Desativar o Wi-Fi.
-   Desative o BlueTooth.
-   Desative os microfones.
-   Evita a adição ou remoção de pacotes de provisionamento.
-   Nenhum utilizador pode ativar qualquer um dos componentes restritos acima referidos.

[![Cenário de segurança offline. ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Preparação

Windows 10 Configuração do PC
1. [Descarregue o mais recente ficheiro HoloLens 2 OS](https://aka.ms/hololens2download) diretamente para um PC. 
   1. O suporte para esta configuração está incluído na Build 19041.1117 ou acima.
1. Descarregue/Instale a ferramenta Advanced Recovery Companion (ARC) [do Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) para o seu PC
1. Descarregue/Instale a mais recente ferramenta [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) do Microsoft Store para o seu PC.
1. [Descarregue a pasta OfflineSecureHL2_Sample com os ficheiros do projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para construir o PPKG.
1. Prepare a sua aplicação offline [Line of Business para a implementação ppkg](app-deploy-provisioning-package.md). 


## <a name="configure"></a>Configurar

Construa um pacote de provisionamento de configuração segura

1. Lance a ferramenta WCD no seu PC.
1. Selecione **o projeto De arquivo -> Open**.
  1. Navegue até à localização da pasta OfflineSecureHL2_Sample previamente guardada e selecione: OfflineSecureHL2_Sample.icdproj.xml
1. O projeto deve abrir e deverá agora ter uma lista de personalizações disponíveis:

   > [!div class="mx-imgBorder"]
   > ![Screenshot do pacote de configuração aberto em WCD.](images/offline-secure-sample-wcd.png)

   Configurações definidas neste pacote de provisionamento:
   
   |     Item                                                |     Definições                       |     Descrição                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Contas / Utilizadores                                    |     Nome de utilizador local & palavra-passe    |     Para estes dispositivos offline, um único nome de utilizador e senha terá de ser definido e partilhado por todos os utilizadores do dispositivo.          |
   |     Primeira Experiência / HoloLens / SkipCalibration       |     Verdadeiro                          |     Salta a calibração apenas durante a configuração inicial do dispositivo                                                                             |
   |     Primeira Experiência / HoloLens / SkipTraining          |     Verdadeiro                          |     Ignora o treino do dispositivo durante a configuração inicial do dispositivo                                                                              |
   |     Primeira Experiência / HoloLens / Wi-Fi                  |     Verdadeiro                          |     Salta Wi-Fi config durante a configuração inicial do dispositivo                                                                                 |
   |     Políticas/Conectividade/Permitir Bluetooth                |     No                            |     Desativa Bluetooth                                                                                                             |
   |     Políticas/Experiência/Permitir aCortana                    |     No                            |     Desativa Cortana (para eliminar potenciais problemas uma vez que os microfones estão desativados)                                          |
   |     Políticas/Realidade Mista/MicrofoneDisabled            |     Yes                           |     Desativa o microfone                                                                                                            |
   |     Políticas/Privacidade/LetAppsAccessLocalização              |     Força negar                    |     Impede que as Aplicações tentem aceder aos dados de localização (para eliminar potenciais problemas uma vez que o rastreio de Localização está desativado)    |
   |     Políticas/Privacidade/LetAppsAccessMicrophone            |     Força negar                    |     Impede que as Apps tentem aceder aos microfones (para eliminar potenciais problemas uma vez que os microfones estão desactivdos)           |
   |     Políticas/Segurança/Permitir a Embalagem deProvisão       |     No                            |     Impede qualquer pessoa de adicionar pacotes de provisionamento que possam tentar anular políticas bloqueadas.                         |
   |     Políticas/Segurança/Permitir a Embalagem deProvisão    |     No                            |     Impede qualquer pessoa de remover este pacote de provisionamento bloqueado.                                                           |
   |     Políticas/Sistema/PermitirLocalização                       |     No                            |     Impede que o dispositivo tente rastrear os dados de localização.                                                                        |
   |     Políticas/Wi-Fi/AllowWiFi                             |     No                            |     Desativa Wi-Fi                                                                                                                 |

1. Em Definições de tempo de execução, selecione **Contas / Utilizadores / Nome do Utilizador: Holo / Password**.

   Observe a palavra-passe e reinicie se desejar.

1. Navegue para UniversalAppInstall / UserContextApp e [configuure a aplicação LOB](app-deploy-provisioning-package.md) que irá implementar nestes dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Screenshot de onde adicionar a sua aplicação no WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Uma vez concluído, selecione o botão "Exportar" e siga todas as instruções até que o seu pacote de provisionamento seja criado.

   > [!div class="mx-imgBorder"]
   > ![Screenshot do botão Exportação para este pacote em WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Implementar

1. Ligação o HL2 ao seu pc Windows 10 via cabo USB.
1. Lance a ferramenta ARC e selecione **HoloLens 2**

   ![HoloLens ecrã inicial de reflash limpo de 2.](images/ARC2.png)

1. No ecrã seguinte selecione **Manual .**

   ![HoloLens ecrã de informação de 2 ARC.](images/arc_device_info.png)

1. Navegue para o ficheiro .ffu previamente descarregado e selecione **Open**.
1. Na página de Advertência **selecione Continue**.

   ![HoloLens ecrã de aviso 2 ARC.](images/arc_warning.png)

1. Aguarde que a ferramenta ARC preencha a instalação de HoloLens 2 OS.
1. Assim que o dispositivo completar a instalação e as botas de volta, do seu PC navegue para o File Explorer e copie o ficheiro PPKG previamente guardado para a pasta do dispositivo.

   > [!div class="mx-imgBorder"]
   > ![Ficheiro PPKG no PC na janela do Explorador de Ficheiros.](images/offline-secure-file-explorer.png)

1. No HoloLens 2, prima a combinação seguinte do botão para executar o Pacote de Provisionamento: Toque no **botão de baixo volume** e **de alimentação** ao mesmo tempo.
1. Será solicitado para aplicar o Pacote de Provisionamento, **selecione Confirmar**
1. Uma vez que o pacote de provisionamento complete, selecione **OK**.
1. Em seguida, deve ser solicitado que assine no dispositivo com a conta local partilhada e a palavra-passe.

## <a name="maintain"></a>Manter

Com esta configuração, recomenda-se reiniciar o processo acima e relançar o dispositivo com a ferramenta ARC e aplicar um novo PPKG para então fazer quaisquer atualizações ao(s) e/ou aplicações.
