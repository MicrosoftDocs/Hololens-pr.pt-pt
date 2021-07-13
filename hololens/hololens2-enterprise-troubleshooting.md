---
title: HoloLens implementação 2 e conseguiu resolver problemas com dispositivos
description: Resolução de problemas HoloLens 2 dispositivos em ambiente empresarial
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
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636882"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Implementação de resolução de problemas e dispositivos geridos 

Este artigo descreve como resolver várias questões ou responder a questões relativas à implementação e gestão de HoloLens 2.

>[!IMPORTANT]
> Antes de iniciar qualquer procedimento de resolução de problemas, certifique-se de que o seu dispositivo está carregado até **20 a 40%** da capacidade da bateria, se possível. As [luzes indicadoras](hololens2-setup.md#lights-that-indicate-the-battery-level) da bateria localizadas sob o botão de alimentação são uma forma rápida de verificar a capacidade da bateria sem iniciar sessão no dispositivo.


<a id="list"></a>
- [Resolução de problemas da EAP](#eap-troubleshooting)
- [Resolução de problemas wi-fi](#wi-fi-troubleshooting)
- [Resolução de problemas de rede](#network-troubleshooting)
- [Não pode entrar num dispositivo de HoloLens previamente configurado](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Não pode iniciar sessão depois de atualizar para Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Resolução de problemas do piloto automático](#autopilot-troubleshooting)
- [Perguntas frequentes de dispositivos de HoloLens geridos](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Resolução de problemas da EAP
1. Verifique duas vezes Wi-Fi perfil tem as definições certas:
    - O tipo EAP é configurado corretamente, tipos comuns de EAP: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).
    - Wi-Fi nome SSID é certo e coincide com a cadeia HEX.
    - Para o EAP-TLS, o TrustedRootCA contém o hash SHA-1 do certificado de CA de raiz fidedigna do servidor. No Windows comando "certutil.exe-dump cert_file_name" do PC mostrará a cadeia de haxixe SHA-1 de um certificado.
2. Colete a captura de pacotes de rede nos registos do Access Point ou do Controlador ou do servidor AAA para saber onde a sessão EAP falha.
    - Se a identidade EAP fornecida por HoloLens não for esperada, verifique se a identidade foi corretamente fornecida através de Wi-Fi perfil ou certificado de cliente.
    - Se o servidor rejeitar HoloLens certificado de cliente, verifique se o certificado de cliente exigido foi a provisionado no dispositivo.
    - Se HoloLens rejeitar o certificado do servidor, verifique se o certificado de CA raiz do servidor foi a provisionado no HoloLens.
3. Se o perfil da empresa for previsto através de Wi-Fi pacote de provisionamento, considere a aplicação do pacote de provisionamento num pc Windows 10. Se também falhar Windows 10 PC, siga o guia de resolução de problemas de autenticação do cliente Windows 802.1X.
4. Envie-nos feedback através do Feedback Hub.

[De volta à lista](#list)

## <a name="wi-fi-troubleshooting"></a>Resolução de problemas Wi-Fi

Aqui estão algumas coisas a experimentar se não consegue ligar o seu HoloLens a uma rede Wi-Fi:

1. Certifique-se de que Wi-Fi está ligado. Para verificar, utilize o gesto Iniciar e, em seguida, selecione Definições > Rede & Internet > Wi-Fi. Se Wi-Fi estiver ligado, tente desligá-lo e depois ligado novamente.
2. Aproxime o computador do router ou do ponto de acesso.
3. Reinicie o router Wi-Fi e reinicie HoloLens. Tente ligar de novo.
4. Se nenhuma destas coisas funcionar, verifique se o seu router está a utilizar o firmware mais recente. Pode encontrar esta informação no site do fabricante.

Quando você assina uma conta empresarial ou organizacional no dispositivo, também pode aplicar a política de Gestão de Dispositivos Móveis (MDM), se a política for configurada pelo seu administrador de TI.

[De volta à lista](#list)

## <a name="network-troubleshooting"></a>Resolução de problemas de rede
Se os problemas de rede forem um obstáculo à implementação e utilização com sucesso HoloLens 2 na sua organização, configurar o Fiddler e/ou o Wireshark para capturar e analisar o tráfego HTTP/HTTPS. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Configure o violinista para capturar o tráfego HTTP
O Fiddler é um proxy de depuração web e é usado para resolver problemas http(s). Captura todos os pedidos HTTP que o computador faz e regista tudo o que lhe está associado. Descobrir problemas de autenticação de utilizador final para as suas aplicações HTTPS impulsiona uma melhor produtividade e eficiência para os seus casos de utilização HoloLens 2. 

#### <a name="prerequisites"></a>Pré-requisitos
 
- HoloLens 2 dispositivos e o seu PC devem estar na mesma rede
- Note o endereço IP do seu PC

#### <a name="install-and-configure-fiddler"></a>Instalar e Configurar Violinista

1. No seu PC - [instale](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) e inicie o Fiddler.  
1. No seu PC - configure o Fiddler para permitir a ligação de computadores remotos.
    1. Ir a Fiddler Definições -> Conexões
    1. Note a porta de audição para Violinista (por defeito é 8866)
    1. Verifique permitir a ligação de computadores remotos
    1. Clicar em Guardar
3. No seu HoloLens 2 – configurar o Violinista como o servidor proxy<sup>1</sup>:
    1. Abra a menu Iniciar e selecione Definições
    1. Selecione Rede & Internet e, em seguida, Proxy no menu esquerdo
    1. Desloque-se para baixo para configuração de procuração manual e alterne Use um servidor proxy para On
    1. Insira o endereço IP do PC onde o Fiddler está instalado
    1. Introduza o número de porta acima indicado (o padrão é 8866)
    1. Clicar em Guardar

<sup>1</sup> Para as construções 20279.1006+ (Insiders e o próximo lançamento), utilize os seguintes passos para configurar o proxy:
1. Abra a menu Iniciar e vá para a página propriedades da sua rede de Wi-Fi 
1. Desça até Proxy
1. Alteração para Configuração Manual
1. Insira o endereço IP do PC onde o Fiddler está instalado
1. Introduza o número da porta acima indicado. (o padrão é 8866)
1. Clique em Aplicar
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>Desencriptar tráfego HTTPS de HoloLens 2

1. No seu PC – exporte o certificado Fiddler.
    1. Vá ao Fiddler Definições -> HTTPS e expanda a Definições Avançada
    2. Clique no certificado de Violino de Exportação. Poupará para o seu ambiente de trabalho
    3. Mova o certificado para a pasta Downloads no seu HoloLens 2

2.  No seu HoloLens 2 - importe o certificado Fiddler.
    1. Ir para Definições -> atualização e segurança -> certificados
    2. Clique em Instalar Certificado, navegue na pasta Downloads e selecione o certificado Fiddler
    3. Alterar a localização da loja para máquina local
    4. Alterar Loja de Certificados para raiz
    5. Selecione instalar
    6. Confirme que o certificado está na lista de certificados. Caso contrário, repita os passos acima

#### <a name="inspect-https-sessions"></a>Inspecionar sessões HTTP(S)

No seu PC, o Fiddler apresentará as sessões HTTP(S) ao vivo do HoloLens 2. O painel de inspetores em Violino pode mostrar http(S) pedido/resposta em diferentes pontos de vista - por exemplo, a visão "Raw" mostra o pedido bruto ou a resposta em texto simples. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Configure o Wireshark para capturar o tráfego da rede
O Wireshark é um analisador de protocolo de rede e é utilizado para inspecionar o tráfego TCP/UDP de e para os seus HoloLens 2 dispositivos. Isto torna fácil identificar que tráfego está atravessando a sua rede para o seu HoloLens 2, quanto dela, com que frequência, quanta latência existe entre certos lúpulos, e assim por diante.

#### <a name="prerequisites"></a>Pré-requisitos:
- O PC deve ter acesso à Internet e apoiar a partilha de Internet ao longo de Wi-Fi

#### <a name="install-and-configure-wireshark"></a>Instalar e Configurar o Arame
1. No seu PC - instale [o Wireshark](https://www.wireshark.org/#download) 
1. No seu PC - permita ao Hotspot Mobile partilhar a sua ligação à Internet a partir de Wi-Fi.
1. No seu PC - inicie o Wireshark e capture o tráfego a partir da interface de hotspot Mobile. 
1. No seu HoloLens 2 – altere a sua rede de Wi-Fi para o hotspot Mobile do PC. HoloLens tráfego IP 2 aparecerão em Wireshark.

#### <a name="analyze-wireshark-logs"></a>Analisar troncos de arame
Os filtros de arame podem ajudar a filtrar os pacotes de interesses. 

Confira o [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)original.

[De volta à lista](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Não pode entrar num dispositivo de HoloLens previamente configurado

Se o seu dispositivo foi previamente configurado para outra pessoa, seja para um cliente ou para um ex-funcionário, e não tiver a sua palavra-passe para desbloquear o dispositivo, pode usar o Intune para [limpar](/intune/remote-actions/devices-wipe) remotamente o dispositivo. Em seguida, o aparelho volta a piscar sozinho.  
> [!IMPORTANT]
> Quando limpar o dispositivo, certifique-se de deixar o **estado de inscrição e a conta do utilizador** sem controlo.

[De volta à lista](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Não pode iniciar sessão depois de atualizar para Windows Holographic 21H1

### <a name="symptoms"></a>Sintomas
- A utilização de PIN para logon falhará após a entrada no PIN correto.
- A utilização do método de início de sessão da Web falhará após a sua assinatura na página web.
- O dispositivo não está listado como "Azure AD unidos" em dispositivos de > [portal Azure](https://portal.azure.com/) -> Azure Ative Directory..

### <a name="cause"></a>Causa
O dispositivo impactado pode ter sido apagado do inquilino AZure AD. Por exemplo, isto pode acontecer porque:

- Um administrador ou utilizador eliminou o dispositivo no portal Azure ou na utilização do PowerShell.
- O dispositivo foi removido do inquilino da AD Azure devido à inatividade. Para um ambiente eficientemente gerido, recomendamos normalmente que os administradores de TI [removam dispositivos inativos e velhos do seu inquilino AD Azure.](/azure/active-directory/devices/manage-stale-devices)

Quando um dispositivo impactado tentar contactar novamente o inquilino Azure AD depois de ter sido eliminado, deixará de autenticar com a Azure AD. Este efeito é muitas vezes invisível para o utilizador do dispositivo, uma vez que a logon em cache via PIN continuará a permitir que o utilizador se insi.ndo.

### <a name="mitigation"></a>Mitigação
Não existe atualmente forma de adicionar um dispositivo de HoloLens eliminado de volta ao Azure AD. Os dispositivos afetados terão de ser reassusados seguindo as instruções de [reflashing](hololens-recovery.md#clean-reflash-the-device)do seu dispositivo .

[De volta à lista](#list)

## <a name="autopilot-troubleshooting"></a>Resolução de problemas do piloto automático

Os seguintes artigos podem ser um recurso útil para você aprender mais informações e resolver problemas de piloto automático Problemas, no entanto, esteja ciente de que estes artigos são baseados em Windows 10 Desktop e nem todas as informações podem ser aplicadas a HoloLens:

- [Windows Autopilot - questões conhecidas](/mem/autopilot/known-issues)
- [Resolução de problemas Windows problemas de inscrição de dispositivos em Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - Conflitos Políticos](/mem/autopilot/policy-conflicts)

[De volta à lista](#list)

## <a name="managed-hololens-devices-faqs"></a>Perguntas frequentes de dispositivos de HoloLens geridos

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Posso utilizar System Center Configuration Manager (SCCM) para gerir dispositivos HoloLens?

N.º Tem de usar um sistema MDM para gerir HoloLens dispositivos.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Posso utilizar os Serviços de Domínio do Diretório Ativo (DS AD) para gerir HoloLens contas de utilizador?

N.º Tem de utilizar Azure Ative Directory (Azure AD) para gerir as contas dos utilizadores para HoloLens dispositivos.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>A HoloLens é capaz de matricular automaticamente os Sistemas automatizados de captura de dados (ADCS).

N.º

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Pode HoloLens participar na Autenticação integrada Windows?

N.º

### <a name="does-hololens-support-branding"></a>A HoloLens suporta a marca?

N.º No entanto, pode contornar esta questão utilizando uma das seguintes abordagens:

- Crie uma aplicação personalizada e, em seguida, ative o [modo Quiosque](hololens-kiosk.md). A aplicação personalizada pode ter marca, e pode lançar outras aplicações (como o Remote Assist).  
- Altere todas as fotos do perfil do utilizador no Azure AD para o logótipo da sua empresa. No entanto, isto pode não ser desejável para todos os cenários.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Que capacidades de registo HoloLens 2 oferecem?

O registo está limitado a vestígios que podem ser capturados em cenários de desenvolvimento ou resolução de problemas, ou telemetria que os dispositivos enviam para servidores da Microsoft.

## <a name="questions-about-securing-hololens-devices"></a>Perguntas sobre a segurança de dispositivos de HoloLens

Consulte as [nossas informações de segurança HoloLens 2.](security-overview.md)
Para HoloLens dispositivos da 1ª Gen, por favor [reveja este FAQ](hololens1-faq-security.yml).

[De volta à lista](#list)
