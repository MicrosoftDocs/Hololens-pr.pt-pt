---
title: Inscreva HoloLens em MDM
description: Saiba como inscrever holoLens na gestão de dispositivos móveis (MDM) para uma gestão mais fácil de vários dispositivos.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378628"
---
# <a name="enroll-hololens-in-mdm"></a>Inscreva HoloLens em MDM

Pode gerir vários dispositivos Microsoft HoloLens simultaneamente utilizando soluções como [o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Poderá gerir as definições, selecionar aplicações para instalar e definir configurações de segurança adaptadas às necessidades da sua organização. Consulte [gerir os dispositivos que executam o Windows Holographic com o Microsoft Intune,](https://docs.microsoft.com/intune/windows-holographic-for-business)os [fornecedores de serviços de configuração (CSPs) que são suportados no Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), e as [políticas suportadas pelo Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> A gestão de dispositivos móveis (MDM), incluindo as funcionalidades do modo VPN, Bitlocker e modo quiosque, só está disponível quando [fizer o upgrade para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisitos

 A sua organização terá de ter a Mobile Device Management (MDM) configurada para gerir dispositivos HoloLens. O seu fornecedor DEM pode ser o Microsoft Intune ou um fornecedor de terceiros que utiliza APIs do Microsoft MDM.
 
## <a name="different-ways-to-enroll"></a>Diferentes formas de se inscrever

Dependendo do tipo de [identidade](hololens-identity.md) escolhida durante o OOBE ou pós-in, existem diferentes métodos de inscrição.

- Se a identidade for Azure AD, então durante o OOBE ou o botão de acesso à **aplicação de definições**  ->  ou o botão de ligação **escolar.**  ->  
    - Para a Azure AD, [a inscrição automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) só ocorre se a Azure AD tiver sido configurada com URLs de inscrição.
     
- Se a Identidade for AZure AD e o dispositivo tiver sido pré-registado no servidor INtune MDM com perfil de configuração específico atribuído a ele, então a Azure AD-Join e [a inscrição automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) ocorrerão durante o OOBE.
    - Também chamado [de fluxo autopiloto](hololens2-autopilot.md) Disponível em [19041.1103+ constrói.](hololens-release-notes.md#windows-holographic-version-2004)
    

- Se a identidade for MSA, então utilize o trabalho de acesso à **aplicação de definições**  ->  ou o botão de ligação **escolar.**  ->  
    - Também chamado fluxo de Conta de Trabalho Adicionar (AWA).
- Se a Identidade for Utilizador Local, então utilize o Trabalho de Acesso à **Aplicação de Definições**  ->  **ou**  ->  **a Inscrição escolar apenas no link de gestão de dispositivos.**
    - Também chamado fluxo de inscrição de MDM puro.

Uma vez que o dispositivo esteja matriculado com o seu servidor MDM, a aplicação Definições irá agora refletir que o dispositivo está inscrito na gestão do dispositivo.

## <a name="auto-enrollment-in-mdm"></a>Inscrição automática em MDM

Se a sua organização tiver uma [subscrição Azure Premium,](https://azure.microsoft.com/overview/)está a utilizar o Azure Ative Directory (Azure AD) e uma solução MDM que aceita um token AD AZure para autenticação (atualmente, apenas suportado no Microsoft Intune e AirWatch), o seu administrador de TI pode configurar a Azure AD para permitir automaticamente a inscrição do MDM após a inscrição do utilizador com a sua conta Azure AD. [Saiba como configurar a inscrição em Ad Azure.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando a inscrição automática está ativada, não é necessária nenhuma inscrição manual extra. Quando o utilizador assina com uma conta AD Azure, o dispositivo é matriculado em MDM após completar a experiência de primeira execução.

Quando um dispositivo é Azure AD AD Se junta, pode afetar quem considerou o proprietário do [dispositivo](security-adminless-os.md#device-owner).

## <a name="unenroll-hololens-from-intune"></a>Unenroll HoloLens de Intune

Dependendo do método de inscrição, a não inscrição do seu dispositivo pode não estar disponível.

Se o seu dispositivo foi matriculado com uma conta AD Azure ou Autopilot, não pode ser desenrolado a partir de Intune. Se desejar desacomprar holoLens da Azure AD ou voltar a juntar-se a um inquilino diferente do AD AZure, tem de [reiniciar/reafinar](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) o dispositivo.

Se o seu dispositivo foi matriculado a partir de uma conta MSA que adicionou uma conta de trabalho ou de uma conta Local que se inscreveu apenas na gestão do dispositivo, então pode desacordá-lo. Abra o menu Iniciar e, em seguida, selecione Definições De Acesso à **Aplicação**  ->  **Trabalho ou Escola** O  ->  botão Desligar *a Contagem.*  ->  