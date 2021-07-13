---
title: Utilizar o Endpoint Manager Intune da Microsoft para gerir dispositivos HoloLens
description: Aprenda a usar o MDM para configurar a CSP, a política e gerir HoloLens dispositivos de realidade mista em escala usando o Intune.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640287"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Utilizar o Endpoint Manager Intune da Microsoft para gerir dispositivos HoloLens

Existem inúmeras configurações diferentes que pode gerir através do MDM. A utilização de dispositivos Intune pode ser agrupada em conjunto e as configurações podem ser implementadas nesses grupos de utilizadores ou dispositivos. As aplicações também podem ser implementadas e geridas, configurando dispositivos para ligar à sua rede, bem como configurar atualizações a ocorrer no momento pretendido e no anel de atualização necessário. 

## <a name="how-to-manage-via-intune"></a>Como gerir via Intune

### <a name="device-categories-and-groups"></a>Grupos e categorias de dispositivos
Utilizando o Intune, pode criar categorias de dispositivos para adicionar automaticamente dispositivos a grupos baseados em categorias que cria, tais como Engenharia, Medicina, Desenvolvedores, e assim por diante. A ideia é simplificar a gestão dos seus dispositivos com o Windows Holographic for Business.
Leia mais: [Categorize dispositivos em grupos](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Perfis de configuração de dispositivos
O Intune inclui definições e funcionalidades que pode ativar ou desativar em diferentes dispositivos na sua organização. Estas definições e funcionalidades são geridas com perfis. Por exemplo, pode criar um perfil que permita Cortana ou utilize o Microsoft Defender Smart Screen nos seus dispositivos em execução Windows Holographic for Business.
Nos seus perfis, pode utilizar definições de OMA-URI para personalizar algumas definições, criar restrições de dispositivos e configurar uma rede privada virtual (VPN) e Wi-Fi.
[Começa com perfis de configuração](/mem/intune/configuration/device-profiles)e [visão geral do perfil](/mem/intune/configuration/device-profile-create).

## <a name="examples-of-what-can-be-managed-and-configured"></a>Exemplos do que pode ser gerido e configurado

A utilização do MDM para gerir dispositivos dá uma grande variedade de itens que podem ser selecionados. 

### <a name="wi-fi"></a>Wi-Fi
As [definições de Wi-Fi](/mem/intune/configuration/wi-fi-settings-configure) atribuem definições de rede sem fios a utilizadores e dispositivos. Quando atribui um perfil Wi-Fi, os utilizadores têm acesso ao seu Wi-Fi corporativo sem terem de o configurar por si próprios.
Saiba mais sobre [a configuração da sua rede para HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Certificados
Os certificados ajudam a melhorar a segurança fornecendo a autenticação de conta, a autenticação Wi-Fi, a encriptação VPN e a encriptação SSL de conteúdos web. Embora os administradores possam gerir certificados em dispositivos manualmente através do provisionamento de pacotes, é uma boa prática usar o seu sistema MDM para gerir esses certificados durante todo o seu ciclo de vida – desde a inscrição até à renovação e revogação. O seu sistema MDM pode implantar automaticamente estes certificados nas lojas de certificados dos dispositivos depois de inscrever o dispositivo (desde que o sistema MDM suporte o Protocolo de Inscrição de Certificados Simples (SCEP) ou as Normas de Criptografia de Chaves Públicas #12 (PKCS#12)). O MDM também pode consultar e apagar certificados de cliente inscritos ou desencadear um novo pedido de inscrição antes de expirar o certificado atual. 

### <a name="proxy"></a>Proxy
A maioria das redes intranet corporativas aproveitam um representante para gerir o tráfego interno. Com HoloLens 2 pode configurar um servidor proxy para ligações ethernet e Wi-Fi. Estas definições não se aplicam às ligações VPN. Para obter mais detalhes sobre as definições de procuração para Windows 10, consulte [NetworkProxy CSP](/windows/client-management/mdm/networkproxy-csp).

### <a name="vpn"></a>VPN
As organizações usam frequentemente uma VPN para controlar o acesso a apps e recursos na intranet da sua empresa. HoloLens 2 suporta ligações VPN SSL, que requerem um plugin descarregador do Microsoft Store e são específicos para o fornecedor VPN à sua escolha. 
- Leia mais sobre [a VPN na HoloLens.](hololens-network.md#vpn)
- Para obter mais detalhes sobre os perfis VPN, consulte o [VPNv2 CSP](/windows/client-management/mdm/vpnv2-csp).

### <a name="deploy-and-manage-apps"></a>Implementar e gerir aplicações
Com o Intune, pode adicionar aplicações aos seus dispositivos com o Windows Holographic for Business. Uma solução MDM permite que os decisores e administradores de TI instalem (empurrem) as suas aplicações internamente, linha de negócios ou comprem aplicações através da loja para um grupo de utilizadores. Existem várias formas de implementar aplicações, incluindo:
-   [Intune e Portal da Empresa]( app-deploy-intune.md)
-   [Loja Microsoft para Empresas]( app-deploy-store-business.md)

Saiba mais sobre a gestão de aplicações através do Intune.
-   [Adicionar aplicações ao Intune](/mem/intune/apps/apps-add)
-   [Adicionar aplicações da Microsoft Store](/mem/intune/apps/store-apps-windows)
-   [Adicionar aplicações que cria](/mem/intune/apps/lob-apps-windows)
- [Atribuir aplicações a grupos](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Atualizações de software
O Intune inclui uma funcionalidade denominada cadência de atualizações para dispositivos com o Windows 10. Esta cadência de atualizações inclui um grupo de definições que determinam como as atualizações são instaladas. Por exemplo, pode criar uma janela de manutenção para instalar atualizações ou pode optar por reiniciar após as atualizações serem instaladas. Uma cadência de atualizações pode ser aplicada a múltiplos dispositivos com o Windows Holographic for Business.
Leia mais sobre como [gerir HoloLens atualizações](hololens-updates.md) e [gerir atualizações de software via Intune](/mem/intune/protect/windows-update-for-business-configure).

### <a name="configure-kiosk-mode"></a>Configurar o modo de quiosque
Com as funcionalidades de PC partilhadas ou de convidado disponíveis no Intune, pode configurar dispositivos com o Windows Holographic for Business para que sejam executados como um quiosque. Estes dispositivos podem executar uma aplicação (modo de quiosque de aplicação única) ou múltiplas aplicações (modo de quiosque de várias aplicações). O modo quiosque é um UI para controlar quais identidades têm acesso a que aplicações por padrão.
Saiba como [configurar HoloLens como quiosque]( hololens-kiosk.md)

