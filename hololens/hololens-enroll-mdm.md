---
title: Inscreva-se HoloLens no MDM
description: Saiba como inscrever HoloLens na gestão de dispositivos móveis (MDM) para uma gestão mais fácil de vários dispositivos.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a368c622c137374ea9cc544490d3492fa9d3f8c1
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032935"
---
# <a name="enroll-hololens-in-mdm"></a>Inscreva-se HoloLens no MDM

Pode gerir vários dispositivos de Microsoft HoloLens simultaneamente utilizando soluções como [Microsoft Intune](/intune/windows-holographic-for-business). Poderá gerir as definições, selecionar aplicações para instalar e definir configurações de segurança adaptadas às necessidades da sua organização. Consulte [gerir os dispositivos em execução Windows Holográfico com Microsoft Intune,](/intune/windows-holographic-for-business) [os prestadores de serviços de configuração (CSPs) que são suportados em Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), e as [políticas apoiadas por Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> A gestão de dispositivos móveis (MDM), incluindo as funcionalidades do modo VPN, Bitlocker e modo quiosque, só está disponível quando [fizer o upgrade para Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisitos

 A sua organização terá de ter a Gestão de Dispositivos Móveis (MDM) configurada para gerir HoloLens dispositivos. O seu fornecedor DEM pode ser Microsoft Intune ou um fornecedor de terceiros que utiliza APIs do Microsoft MDM.

## <a name="different-ways-to-enroll"></a>Diferentes formas de se inscrever

Dependendo do tipo de [identidade](hololens-identity.md) escolhida durante o OOBE ou pós-in, existem diferentes métodos de inscrição.

- Se a identidade for Azure AD, então durante o OOBE ou Definições o botão de acesso à **aplicação**  ->  **ou**  ->  **Ligação** escolar.
    - Para a Azure AD, [a inscrição automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) só ocorre se a Azure AD tiver sido configurada com URLs de inscrição.

- Se a Identidade for AZure AD e o dispositivo tiver sido pré-registado no servidor INtune MDM com perfil de configuração específico atribuído a ele, então a Azure AD-Join e [a inscrição automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) ocorrerão durante o OOBE.
    - Também chamado [de fluxo autopiloto](hololens2-autopilot.md) Disponível em [19041.1103+ constrói.](hololens-release-notes.md#windows-holographic-version-2004)


- Se a identidade for MSA, então utilize Definições o trabalho de acesso à **aplicação**  ->  ou o botão de Ligação **escolar.**  ->  
    - Também chamado fluxo de Conta de Trabalho Adicionar (AWA).
- Se a Identidade for Utilizador Local, então utilize Definições Trabalho de Acesso à **Aplicação**  ->  **ou Inscrição escolar**  ->  apenas no link de **gestão de dispositivos.**
    - Também chamado fluxo de inscrição de MDM puro.

Uma vez que o dispositivo esteja matriculado com o seu servidor MDM, a aplicação Definições irá agora refletir que o dispositivo está inscrito na gestão do dispositivo.

## <a name="auto-enrollment-in-mdm"></a>Inscrição automática em MDM

Se a sua organização tiver uma [subscrição Azure Premium,](https://azure.microsoft.com/overview/)está a utilizar Azure Ative Directory (Azure AD) e uma solução MDM que aceita um token AD Azure para autenticação (atualmente, apenas suportado em Microsoft Intune e AirWatch), o seu administrador de TI pode configurar a Azure AD para permitir automaticamente a inscrição do MDM após o utilizador assinar com a sua conta Azure AD. [Saiba como configurar a inscrição em Ad Azure.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando a inscrição automática está ativada, não é necessária nenhuma inscrição manual extra. Quando o utilizador assina com uma conta AD Azure, o dispositivo é matriculado em MDM após completar a experiência de primeira execução.

Quando um dispositivo é Azure AD AD Se junta, pode afetar quem considerou o proprietário do [dispositivo](security-adminless-os.md#device-owner).

## <a name="unenroll-hololens-from-intune"></a>Unenroll HoloLens de Intune

Dependendo do método de inscrição, a não inscrição do seu dispositivo pode não estar disponível.

Se o seu dispositivo foi matriculado com uma conta AD Azure ou Autopilot, não pode ser desenrolado a partir de Intune. Se desejar desacompra HoloLens da Azure AD ou voltar a juntar-se a um inquilino diferente do AD AZure, tem de [reiniciar/reflash](hololens-recovery.md#reset-the-device) o dispositivo.

Se o seu dispositivo foi matriculado a partir de uma conta MSA que adicionou uma conta de trabalho ou de uma conta Local que se inscreveu apenas na gestão do dispositivo, então pode desacordá-lo. Abra a menu Iniciar e, em seguida, selecione Definições o "Trabalho de Acesso à **Aplicação"**  ->  ou o botão **"Desligar a Contagem**  ->    ->   escolar".

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Certifique-se de que a inscrição do MDM não está bloqueada para dispositivos Windows

Para que a inscrição tenha sucesso, terá de se certificar de que os seus HoloLens dispositivos podem inscrever-se. Uma vez que HoloLens é considerado um dispositivo Windows, não terá de haver restrições de inscrição que possam bloquear a sua implementação. [Reveja esta lista de restrições](/mem/intune/enrollment/enrollment-restrictions-set) e certifique-se de que poderá inscrever os seus dispositivos.