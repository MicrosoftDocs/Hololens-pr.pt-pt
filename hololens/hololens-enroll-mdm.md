---
title: Inscreva-se HoloLens no MDM
description: Saiba como se inscrever HoloLens na gestão de dispositivos móveis (MDM) para uma gestão mais fácil de vários dispositivos.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fa114633afe70a11a180c67fedbd40eb423ece99
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034183"
---
# <a name="enroll-hololens-in-mdm"></a>Inscreva-se HoloLens no MDM

Pode gerir vários dispositivos de Microsoft HoloLens simultaneamente utilizando soluções como [Microsoft Intune](/intune/windows-holographic-for-business). Poderá gerir as definições, selecionar aplicações para instalar e definir configurações de segurança adaptadas às necessidades da sua organização. Consulte [gerir os dispositivos em execução Windows Holográfico com Microsoft Intune,](/intune/windows-holographic-for-business) [os prestadores de serviços de configuração (CSPs) que são suportados em Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), e as [políticas suportadas por Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> A gestão de dispositivos móveis (MDM), incluindo as funcionalidades do modo VPN, Bitlocker e modo quiosque, só está disponível quando [fizer o upgrade para Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisitos

 A sua organização terá de ter a Mobile Device Management (MDM) configurada para gerir HoloLens dispositivos. O seu fornecedor DEDM pode ser Microsoft Intune ou um fornecedor de terceiros que utiliza APIs do Microsoft MDM.

## <a name="different-ways-to-enroll"></a>Diferentes formas de se inscrever

Dependendo do tipo de [identidade](hololens-identity.md) escolhida durante o OOBE ou pós-in, existem diferentes métodos de inscrição.

- Se a Identidade for Azure AD, então durante o OOBE ou Definições o botão de acesso à **aplicação**  ->  **ou**  ->  **Ligação** escolar.
    - Para o Azure AD, [a inscrição automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) só ocorre se o Azure AD tiver sido configurado com URLs de inscrição.

- Se a Identidade for Azure AD e o dispositivo tiver sido pré-registado no servidor INtune MDM com perfil de configuração específico atribuído a ele, então a Azure AD-Join e [a inscrição automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) ocorrerão durante o OOBE.
    - Também chamado [de fluxo autopiloto](hololens2-autopilot.md) Disponível em [19041.1103+ constrói.](hololens-release-notes.md#windows-holographic-version-2004)


- Se a identidade for MSA, então utilize Definições o trabalho de acesso à **aplicação**  ->  ou o botão de Ligação **escolar.**  ->  
    - Também chamado fluxo de Conta de Trabalho De Adicionar (AWA).
- Se a Identidade for Utilizador Local, então utilize Definições Trabalho de Acesso à **Aplicação**  ->  **ou Inscrição escolar**  ->  apenas no link de **gestão de dispositivos.**
    - Também chamado fluxo de inscrição de MDM puro.

Uma vez que o dispositivo esteja matriculado no seu servidor MDM, a aplicação Definições irá agora refletir que o dispositivo está inscrito na gestão do dispositivo.

## <a name="auto-enrollment-in-mdm"></a>Inscrição automática em MDM

Se a sua organização tiver uma [subscrição Azure Premium,](https://azure.microsoft.com/overview/)está a utilizar Azure Ative Directory (Azure AD) e uma solução MDM que aceita um token AD AZure para autenticação (atualmente, apenas suportado em Microsoft Intune e AirWatch), o seu administrador de TI pode configurar a Azure AD para permitir automaticamente a inscrição do MDM após a inscrição do utilizador com o seu AD Azure conta. [Saiba como configurar a inscrição em Ad Azure.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando a inscrição automática está ativada, não é necessária nenhuma inscrição manual extra. Quando o utilizador assina com uma conta AD Azure, o dispositivo é matriculado em MDM após completar a experiência de primeira execução.

Quando um dispositivo é Azure AD Unidos pode afetar quem considerou o [proprietário do dispositivo](security-adminless-os.md#device-owner).

## <a name="unenroll-hololens-from-intune"></a>Unenroll HoloLens de Intune

Dependendo do método de inscrição, a não inscrição do seu dispositivo pode não estar disponível.

Se o seu dispositivo foi matriculado com uma conta AD AZure ou Autopilot, não pode ser desenrolado a partir do Intune. Se desejar desacompra HoloLens da Azure AD ou voltar a juntar-se a um inquilino diferente do AD AZure, tem de [reiniciar/reflash](hololens-recovery.md#restart-the-device) o dispositivo.

Se o seu dispositivo foi matriculado a partir de uma conta MSA que adicionou uma conta de trabalho ou de uma conta Local que se inscreveu apenas na gestão do dispositivo, então pode desacordá-lo. Abra a menu Iniciar e, em seguida, selecione Definições o funcionamento do acesso à **aplicação**  ->  ou o botão  ->    ->  **Desconexão** da Contagem Escolar.

## <a name="enrollment-troubleshooting"></a>Resolução de problemas de inscrição

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Garantir que a licença válida é atribuída ao utilizador

Consulte os [problemas de inscrição Windows de dispositivos de resolução de problemas em Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) especificamente seguindo as secções, ou seja, [verifique as restrições do tipo do dispositivo](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) e [atribua uma licença válida ao utilizador.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Certifique-se de que a inscrição do MDM não está bloqueada para dispositivos Windows

Para que a inscrição tenha sucesso, terá de se certificar de que os seus HoloLens dispositivos podem inscrever-se. Uma vez que HoloLens é considerado um dispositivo Windows, não terá de haver restrições de inscrição que possam bloquear a sua implementação. [Reveja esta lista de restrições](/mem/intune/enrollment/enrollment-restrictions-set) e certifique-se de que poderá inscrever os seus dispositivos.