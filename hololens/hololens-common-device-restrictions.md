---
title: Restrições comuns do dispositivo
description: Mantenha-se atualizado com as restrições e configurações comuns do dispositivo de realidade mista HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378479"
---
# <a name="common-device-restrictions"></a>Restrições comuns do dispositivo 

Este guia ajuda os profissionais de TI a compreender as opções de gestão mais utilizadas disponíveis para o SISTEMA Holográfico Windows 10 na empresa. Consulte a documentação do sistema MDM para entender como estas políticas são ativadas pelo seu fornecedor DEM. Nem todos os sistemas MDM suportam todas as definições descritas neste guia. Alguns suportam políticas personalizadas através de ficheiros OMA-URI XML. Consulte [o suporte do Microsoft Intune para políticas personalizadas.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) As convenções de nomeação também podem variar entre os fornecedores de MDM.

## <a name="prevent-changing-of-settings"></a>Evitar a alteração das definições
Os colaboradores são normalmente autorizados a alterar determinadas configurações de dispositivos pessoais que pode querer bloquear em dispositivos corporativos. Os colaboradores podem ajustar interativamente certas definições dos HoloLens através das definições de UI. Usando o MDM, pode limitar o que os utilizadores podem alterar. As seguintes listas são comumente utilizadas configurações de MDM que o Windows 10 Holographic suporta para configurar restrições de definições:
-   [Permitir VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite ao utilizador alterar as definições de VPN
-   [Permitir configuração wi-fi manual:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite que os utilizadores façam ligações Wi-Fi fora das redes adUC
-   [Permitir o desenrolar manual do MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Se os utilizadores estão autorizados a apagar a conta no local de trabalho (isto é, desenrolar o dispositivo a partir do sistema MDM)

Adicionado no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos HoloLens 2:
- [Permitir adicionar pacote de provisionamento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Alternar se os utilizadores podem adicionar novos pacotes de provisionamento, sobreescrita com novos valores.
- [Permitir remover pacote de provisionamento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Alternar se os utilizadores puderem remover pacotes de provisionamento, permitindo-lhes alternar as definições previamente bloqueadas.

Encontre mais detalhes sobre as opções políticas nos HoloLens apoiados [pelos CSPs](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Restrições de hardware
Os dispositivos holográficos do Windows 10 utilizam tecnologia de ponta que inclui funcionalidades de hardware populares, como câmaras, microfones, altifalantes, interfaces USB, interfaces Bluetooth e Wi-Fi. Pode utilizar restrições de hardware para controlar a disponibilidade destas funcionalidades.
As seguintes listas são comumente utilizadas configurações de MDM que o Windows 10 Holographic suporta para configurar restrições de hardware:

> [!NOTE]
> Algumas destas restrições de hardware afetam a conectividade e ajudam na proteção de dados.

-   [Permitir Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os utilizadores podem ativar e utilizar o rádio Wi-Fi nos seus dispositivos.
-   [Permitir a ligação USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a ligação USB está ativada (não afeta o carregamento USB.)
-   [Permitir Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se os utilizadores podem ativar e utilizar o rádio Bluetooth nos seus dispositivos.
-   [Câmara restrita:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Especifica se as aplicações do Windows podem aceder à câmara.
-   [Restringir os microfones:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Especifica se as aplicações do Windows podem aceder ao microfone.

Adicionado no [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos HoloLens 2. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Desapaixe o tempo até que o visor se desligue e, desligando o visor, bloqueia o dispositivo. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Desapaixe o tempo até que o visor se desligue e, desligando o visor, bloqueia o dispositivo. 
