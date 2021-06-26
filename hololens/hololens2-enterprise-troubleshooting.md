---
title: Implementação hololens 2 e resolução de problemas geridos do dispositivo
description: Resolução de problemas HoloLens 2 dispositivos em um ambiente enterprise
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: resolução de problemas
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961641"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Implementação de resolução de problemas e dispositivos geridos 

Este artigo descreve como resolver várias questões ou responder a questões relativas à implementação e gestão do HoloLens 2.

>[!IMPORTANT]
> Antes de iniciar qualquer procedimento de resolução de problemas, certifique-se de que o seu dispositivo está carregado até **20 a 40%** da capacidade da bateria, se possível. As [luzes indicadoras](hololens2-setup.md#lights-that-indicate-the-battery-level) da bateria localizadas sob o botão de alimentação são uma forma rápida de verificar a capacidade da bateria sem iniciar sessão no dispositivo.


<a id="list"></a>
- [Resolução de problemas da EAP](#eap-troubleshooting)
- [Resolução de problemas wi-fi](#wi-fi-troubleshooting)
- [Resolução de problemas de rede](#network-troubleshooting)
- [Não pode entrar num dispositivo HoloLens previamente configurado](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Não pode iniciar sessão depois de atualizar para o Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Resolução de problemas do piloto automático](#autopilot-troubleshooting)
- [FaQs de dispositivos HoloLens geridos](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Resolução de problemas da EAP
1. Verifique duas vezes Wi-Fi perfil tem as definições certas:
    - O tipo EAP é configurado corretamente, tipos comuns de EAP: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).
    - Wi-Fi nome SSID é certo e coincide com a cadeia HEX.
    - Para o EAP-TLS, o TrustedRootCA contém o hash SHA-1 do certificado de CA de raiz fidedigna do servidor. No comando "certutil.exe-dump cert_file_name" do Windows PC, o comando mostrará a cadeia de haxixe SHA-1 de um certificado.
2. Colete a captura de pacotes de rede nos registos do Access Point ou do Controlador ou do servidor AAA para saber onde a sessão EAP falha.
    - Se a identidade EAP fornecida pela HoloLens não for esperada, verifique se a identidade foi corretamente fornecida através de Wi-Fi perfil ou certificado de cliente.
    - Se o servidor rejeitar o certificado de cliente HoloLens, verifique se o certificado de cliente exigido foi a provisionado no dispositivo.
    - Se o HoloLens rejeitar o certificado do servidor, verifique se o certificado de CA raiz do servidor foi a provisionado no HoloLens.
3. Se o perfil da empresa for a provisionado através de Wi-Fi pacote de provisionamento, considere aplicar o pacote de provisionamento num PC windows 10. Se também falhar no PC do Windows 10, siga o guia de resolução de problemas de autenticação do cliente Windows 802.1X.
4. Envie-nos feedback através do Feedback Hub.

[De volta à lista](#list)

## <a name="wi-fi-troubleshooting"></a>Resolução de problemas Wi-Fi

Aqui estão algumas coisas a experimentar se não consegue ligar os hololens a uma rede Wi-Fi:

1. Certifique-se de que Wi-Fi está ligado. Para verificar, utilize o gesto Iniciar e, em seguida, selecione Definições > Rede & Internet > Wi-Fi. Se Wi-Fi estiver ligado, tente desligá-lo e depois ligado novamente.
2. Aproxime o computador do router ou do ponto de acesso.
3. Reinicie o router Wi-Fi e reinicie os HoloLens. Tente ligar de novo.
4. Se nenhuma destas coisas funcionar, verifique se o seu router está a utilizar o firmware mais recente. Pode encontrar esta informação no site do fabricante.

Quando você assina uma conta empresarial ou organizacional no dispositivo, também pode aplicar a política de Gestão de Dispositivos Móveis (MDM), se a política for configurada pelo seu administrador de TI.

## <a name="network-troubleshooting"></a>Resolução de problemas de rede
Se os problemas de rede são um obstáculo à implementação e utilização com sucesso do HoloLens 2 na sua organização, saiba como duas ferramentas de diagnóstico de rede bem conhecidas, Fiddler e Wireshark podem ajudá-lo a digitalizar, diagnosticar e identificar problemas. Confira este [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) para mais detalhes.

[De volta à lista](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Não pode entrar num dispositivo HoloLens previamente configurado

Se o seu dispositivo foi previamente configurado para outra pessoa, seja para um cliente ou para um ex-funcionário, e não tiver a sua palavra-passe para desbloquear o dispositivo, pode usar o Intune para [limpar](https://docs.microsoft.com/intune/remote-actions/devices-wipe) remotamente o dispositivo. Em seguida, o aparelho volta a piscar sozinho.  
> [!IMPORTANT]
> Quando limpar o dispositivo, certifique-se de deixar o **estado de inscrição e a conta do utilizador** sem controlo.
[De volta à lista](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Não pode iniciar sessão depois de atualizar para o Windows Holographic 21H1

### <a name="symptoms"></a>Sintomas
- A utilização de PIN para logon falhará após a entrada no PIN correto.
- A utilização do método de início de sessão da Web falhará após a sua assinatura na página web.
- O dispositivo não está listado como "Azure AD aderido" no [portal Azure](https://portal.azure.com/) -> Azure Ative Directory -> Dispositivos.

### <a name="cause"></a>Causa
O dispositivo impactado pode ter sido apagado do inquilino AZure AD. Por exemplo, isto pode acontecer porque:

- Um administrador ou utilizador eliminou o dispositivo no portal Azure ou na utilização do PowerShell.
- O dispositivo foi removido do inquilino da AD Azure devido à inatividade. Para um ambiente eficientemente gerido, recomendamos normalmente que os administradores de TI [removam dispositivos inativos e velhos do seu inquilino AD Azure.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)

Quando um dispositivo impactado tentar contactar novamente o inquilino Azure AD depois de ter sido eliminado, deixará de autenticar com a Azure AD. Este efeito é muitas vezes invisível para o utilizador do dispositivo, uma vez que a logon em cache via PIN continuará a permitir que o utilizador se insi.ndo.

### <a name="mitigation"></a>Mitigação
Não existe atualmente forma de adicionar um dispositivo HoloLens eliminado de volta ao Azure AD. Os dispositivos afetados terão de ser reassusados seguindo as instruções de [reflashing](hololens-recovery.md#clean-reflash-the-device)do seu dispositivo .

## <a name="autopilot-troubleshooting"></a>Resolução de problemas do piloto automático

Os seguintes artigos podem ser um recurso útil para você aprender mais informações e resolver problemas de piloto automático Problemas, no entanto, esteja ciente de que estes artigos são baseados no Windows 10 Desktop e nem todas as informações podem aplicar-se a HoloLens:

- [Windows Autopilot - problemas conhecidos](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Problemas de inscrição de dispositivos Windows na Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - Conflitos Políticos](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>FaQs de dispositivos HoloLens geridos

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Posso utilizar o Gestor de Configuração do Centro de Sistema (SCCM) para gerir dispositivos HoloLens?

N.º Tens de usar um sistema MDM para gerir dispositivos HoloLens.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Posso utilizar os Serviços de Domínio do Diretório Ativo (DS AD) para gerir as contas de utilizadores do HoloLens?

N.º Tem de utilizar o Azure Ative Directory (Azure AD) para gerir as contas dos utilizadores dos dispositivos HoloLens.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Os HoloLens são capazes de matricular automaticamente os Sistemas automatizados de captura de dados (ADCS).

N.º

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Os HoloLens podem participar na Autenticação Integrada do Windows?

N.º

### <a name="does-hololens-support-branding"></a>A HoloLens suporta a marca?

N.º No entanto, pode contornar esta questão utilizando uma das seguintes abordagens:

- Crie uma aplicação personalizada e, em seguida, ative o [modo Quiosque](hololens-kiosk.md). A aplicação personalizada pode ter marca, e pode lançar outras aplicações (como o Remote Assist).  
- Altere todas as fotos do perfil do utilizador no Azure AD para o logótipo da sua empresa. No entanto, isto pode não ser desejável para todos os cenários.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Que capacidades de registo os HoloLens 2 oferecem?

O registo está limitado a vestígios que podem ser capturados em cenários de desenvolvimento ou resolução de problemas, ou telemetria que os dispositivos enviam para servidores da Microsoft.

## <a name="questions-about-securing-hololens-devices"></a>Perguntas sobre a segurança de dispositivos HoloLens

Consulte as [nossas informações de segurança HoloLens 2](security-overview.md).
Para dispositivos HoloLens 1st Gen, por favor [reveja este FAQ](hololens1-faq-security.md).

[De volta à lista](#list)
