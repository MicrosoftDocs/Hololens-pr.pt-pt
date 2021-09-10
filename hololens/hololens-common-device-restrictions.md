---
title: Restrições comuns do dispositivo
description: Mantenha-se atualizado com as restrições e configurações comuns do dispositivo para o HoloLens dispositivo de realidade mista.
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
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427955"
---
# <a name="common-device-restrictions"></a>Restrições comuns do dispositivo 

Este guia ajuda os profissionais de TI a compreender as opções de gestão mais utilizadas disponíveis para o Windows 10 Holographic OS na empresa. Consulte a documentação do sistema MDM para entender como estas políticas são ativadas pelo seu fornecedor DEM. Nem todos os sistemas MDM suportam todas as definições descritas neste guia. Alguns suportam políticas personalizadas através de ficheiros OMA-URI XML. Consulte [Microsoft Intune suporte para Políticas Personalizadas.](/mem/intune/configuration/custom-settings-windows-10) As convenções de nomeação também podem variar entre os fornecedores de MDM.

## <a name="prevent-changing-of-settings"></a>Evitar a alteração das definições
Os colaboradores são normalmente autorizados a alterar determinadas configurações de dispositivos pessoais que pode querer bloquear em dispositivos corporativos. Os colaboradores podem ajustar interativamente determinadas definições do HoloLens através das definições de UI. Usando o MDM, pode limitar o que os utilizadores podem alterar. As seguintes listas comumente utilizadas configurações de MDM que Windows 10 Holographic suporta para configurar restrições de configurações:
-   [Permitir VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite ao utilizador alterar as definições de VPN
-   [Permitir configuração wi-fi manual:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite que os utilizadores façam ligações Wi-Fi fora das redes adUC
-   [Permitir o desenrolar manual do MDM](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Se os utilizadores estão autorizados a apagar a conta no local de trabalho (isto é, desenrolar o dispositivo a partir do sistema MDM)

Adicionado em [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para HoloLens 2 dispositivos:
- [Permitir adicionar pacote de provisionamento:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Alternar se os utilizadores podem adicionar novos pacotes de provisionamento, sobreescrita com novos valores.
- [Permitir remover pacote de provisionamento:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Alternar se os utilizadores puderem remover pacotes de provisionamento, permitindo-lhes alternar as definições previamente bloqueadas.

Saiba mais detalhes sobre as opções políticas nos [CSPs de política](/windows/client-management/mdm/policy-csps-supported-by-hololens2) HoloLens apoiados

## <a name="hardware-restrictions"></a>Restrições de hardware
Windows 10 Holographic dispositivos utilizam tecnologia de última geração que inclui funcionalidades de hardware populares, como câmaras, microfones, colunas, interfaces USB, interfaces Bluetooth e Wi-Fi. Pode utilizar restrições de hardware para controlar a disponibilidade destas funcionalidades.
As seguintes listas comumente utilizadas configurações de MDM que Windows 10 Holographic suporta para configurar restrições de hardware:

> [!NOTE]
> Algumas destas restrições de hardware afetam a conectividade e ajudam na proteção de dados.

-   [Permitir Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os utilizadores podem ativar e utilizar o rádio Wi-Fi nos seus dispositivos.
-   [Permitir a ligação USB:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a ligação USB está ativada (não afeta o carregamento USB.)
-   [Permitir Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se os utilizadores podem ativar e utilizar o Bluetooth rádio nos seus dispositivos.
-   [Câmara restrita:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Especifica se Windows aplicações podem aceder à câmara.
-   [Restringir os microfones:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Especifica se Windows aplicações podem aceder ao microfone.

Adicionado em [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para HoloLens 2 dispositivos. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Desapaixe o tempo até que o visor se desligue e, desligando o visor, bloqueia o dispositivo. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Desapaixe o tempo até que o visor se desligue e, desligando o visor, bloqueia o dispositivo. 
