---
title: Ligue hololens a uma rede
description: Saiba como configurar e conectar-se à internet com holoLens e como identificar o endereço IP do dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, wireless, internet, ip, endereço ip
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: d68c75dcb2249a67f2e07c77cb1b69997eb0ae72
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379908"
---
# <a name="connect-hololens-to-a-network"></a>Ligue hololens a uma rede

Para fazer a maioria das coisas nos hololens, tem que estar ligado a uma rede. O HoloLens contém um rádio 802.11ac, 2x2 Wi-Fi e ligá-lo a uma rede é semelhante a ligar um dispositivo Windows 10 Desktop ou Mobile a uma rede Wi-Fi. Este guia irá ajudá-lo:

- Ligue-se a uma rede que utilize Wi-Fi, ou apenas para HoloLens 2, Wi-Fi Direct ou Ethernet sobre USB-C
- Desativar e reativar Wi-Fi

Leia mais sobre [a utilização de HoloLens offline](hololens-offline.md).

## <a name="connecting-for-the-first-time"></a>Ligação pela primeira vez

A primeira vez que usar os HoloLens, será guiado através da ligação a uma rede Wi-Fi. Se tiver problemas em ligar-se a Wi-Fi durante a configuração, certifique-se de que a sua rede é uma rede aberta, protegida por palavras-passe ou uma rede de portal cativo. Além disso, confirme que a rede não requer que utilize um certificado para se ligar. Após a configuração, pode ligar-se a outros tipos de redes Wi-Fi.

Nos dispositivos HoloLens 2, um utilizador também pode [utilizar um adaptador USB-C para Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para ligar diretamente a Wi-Fi para ajudar a configurar o dispositivo. Uma vez configurado o dispositivo, um utilizador pode continuar a utilizar o adaptador ou pode desligar o dispositivo do adaptador e [ligar-se ao wi-fi após a instalação](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Ligação a Wi-Fi após a configuração

1. Pré-forma o **gesto Iniciar** e selecione **Definições**. A aplicação Definições será colocada automaticamente à sua frente.
1. Selecione **Rede &**  >  **Wi-Fi de** Internet. Certifique-se de que o Wi-Fi está ativado. Se não vires a tua rede, percorra a lista.
1. Selecione uma rede e, em seguida, selecione **Connect**.
1. Se for solicitado para uma palavra-passe de rede escreva-a e, em seguida, selecione **Next**.

![HoloLens Wi-Fi configurações](./images/hololens-2-wifi-settings.jpg)

Para confirmar que está ligado a uma rede Wi-Fi, verifique o estado Wi-Fi no menu **Iniciar:**

1. Abra o menu **Iniciar.**
1. Olhe para o lado superior esquerdo do menu **Iniciar** para Wi-Fi estado. O estado de Wi-Fi e o SSID da rede conectada serão mostrados.

> [!TIP]
> Se Wi-Fi não estiver disponível, também pode [ligar-se às redes Cellular e 5G.](https://docs.microsoft.com/hololens/hololens-cellular)

> [!IMPORTANT]
> Por design, os utilizadores não podem afinar o comportamento de roaming Wi-Fi dos HoloLens 2 - **a única maneira de refrescar a lista de Wi-Fi é alternar o Wi-Fi Off and On**. Isto evita muitos problemas, como quando um dispositivo pode permanecer "preso" a um AP uma vez que está fora de alcance.

## <a name="troubleshooting-your-connection-to-wi-fi"></a>Resolução de problemas da sua ligação com Wi-Fi

Se tiver problemas de ligação ao Wi-Fi, veja [se não consigo ligar-me ao Wi-Fi.](./hololens-faq.md#i-cant-connect-to-wi-fi)

Quando você assina uma conta empresarial ou organizacional no dispositivo, também pode aplicar a política de Gestão de Dispositivos Móveis (MDM), se a política for configurada pelo seu administrador de TI.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Ligue hololens à Enterprise Wi-Fi Network

Os perfis Wi-Fi empresa utilizam o Protocolo de Autenticação Extensível (EAP) para autenticar ligações Wi-Fi. HoloLens Enterprise Wi-Fi perfil pode ser configurado através de MDM ou pacote de provisionamento criado pelo [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).

Para o dispositivo gerido microsoft Intune, consulte [o Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para obter instruções de configuração.

Para criar um pacote de provisionamento Wi-Fi em WCD, é necessário um perfil de Wi-Fi pré-configurado .xml ficheiro. Aqui está uma amostra Wi-Fi perfil para WPA2-Enterprise com autenticação EAP-TLS:

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


O certificado de CA raiz do servidor e o certificado de cliente podem ter de ser a provisionados no dispositivo, dependendo do tipo EAP.

Recursos adicionais:

- WLANv1Profile Schema: [[MS-GPWL]: Perfil de LAN sem fios v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

## <a name="eap-troubleshooting"></a>Resolução de problemas da EAP
> [!TIP]
> A maioria dos problemas de rede são o resultado de uma das 3 definições abaixo do 3 estar incorreta no perfil Wi-FI. 
1. Verifique duas vezes Wi-Fi perfil tem as definições certas:
   1. O tipo EAP é configurado corretamente, tipos comuns de EAP: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).
   1. Wi-Fi nome SSID é certo e coincide com a cadeia HEX.
   1. Para o EAP-TLS, o TrustedRootCA contém o hash SHA-1 do servidor&#39;certificado de CA de raiz fidedigna. No Windows &quot; PC,certutil.exe comando de nome de ficheiro cert de despejo \_ \_ &quot; mostrará um certificado&#39;cadeia de hash SHA-1 do Windows PC.

2. Colete a captura de pacotes de rede nos registos do Access Point ou do Controlador ou do servidor AAA para saber onde a sessão EAP falha.
   1. Se a identidade EAP fornecida pela HoloLens não for esperada, verifique se a identidade foi corretamente fornecida através de Wi-Fi perfil ou certificado de cliente.
   1. Se o servidor rejeitar o certificado de cliente HoloLens, verifique se o certificado de cliente exigido foi a provisionado no dispositivo.
   1. Se o HoloLens rejeitar o certificado do servidor, verifique se o certificado de CA raiz do servidor foi a provisionado no HoloLens.
1. Se o perfil da empresa for a provisionado através de Wi-Fi pacote de provisionamento, considere aplicar o pacote de provisionamento num PC windows 10. Se também falhar no PC do Windows 10, siga o [guia de resolução de problemas de autenticação do cliente Windows 802.1X](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).
1. Desaponte a sua telemetria para Full ou Optional (dependendo da sua construção) e, em seguida, envie-nos feedback através [do Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).

### <a name="additional-resources"></a>Recursos adicionais:
- [Exportar definições de Wi-Fi a partir de um dispositivo Windows](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="configure-network-proxy"></a>Configure Rede Proxy

Esta secção abrange o proxy de rede para aplicações HoloLens OS e Universal Windows Platform (UWP) utilizando a pilha HTTP do Windows. As aplicações que utilizam a pilha HTTP não-Windows podem ter a sua própria configuração e manuseamento de procuração. 

### <a name="proxy-configurations"></a>Configurações proxy 

- Script Proxy Auto-Config (PAC): um [ficheiro PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (abre um site não Microsoft) contém uma função JavaScript FindProxyForURL (url, anfitrião). 
- Procuração Estática: na forma de Servidor:Porta.  
- Web Proxy Auto-Discovery Protocol (WPAD): fornecer URL de ficheiro de configuração de procuração através de DHCP ou DNS. 

### <a name="proxy-provisioning-methods"></a>Métodos de provisionamento por procuração 
Há três formas de providenciar proxies:

 

1.  **Definições UI:** 
    1. Procuração por utilizador (20H2 ou mais cedo):
        1. Abra o menu Iniciar e selecione Definições.
        2. Selecione Network & Internet e, em seguida, Proxy no menu esquerdo.
        3. Desloque-se para a configuração de procuração manual e altere Use um servidor proxy para On.
        4. Insira o endereço IP do servidor proxy.
        5. Introduza o número da porta.
        6. Clique em Guardar.
      1. Procuração WiFi (21H1 ou superior):
          1. Abra o menu Iniciar e vá para a página Wi-Fi 'Propriedades' da Rede.
          1. Desça até Proxy
          1. Alteração para Configuração Manual
          1. Insira o endereço IP do servidor proxy.
          1. Introduza o número da porta.
          1. Clique em Aplicar.
        
 2. **MDM** 
     1. Intune - Use estes [passos](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para configurar o proxy em Intune. Terá de deslocar-se para o fundo da secção.
     1. Outras soluções DE MDM de terceiros - Use um [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).

3. **PPKG** 
    1. Open Windows Configuration Designer
    1. Clique em Provisionamento Avançado, insira o nome para o seu novo Projeto e clique em Seguinte.
    1. Selecione o Windows Holographic (HoloLens 2) e clique em Seguinte.
    1. Importe o seu PPKG (opcional) e clique em Terminar.
    1. Expandir configurações de tempo de execução -> Perfis de conectividade -> WLAN -> WLAN Proxy.
    1. Introduza o SSID da sua rede de Wi-Fi e clique em Adicionar.
    1. Selecione a sua rede Wi-Fi na janela esquerda e introduza as personalizações desejadas. As personalizações ativadas aparecerão em negrito no menu esquerdo.
    1. Clique em Guardar e Sair.
    1. [Aplique](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) o pacote de provisionamento aos HoloLens.

[Os CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) estão por detrás de muitas das tarefas e políticas de gestão do Windows 10, tanto no Microsoft Intune como em prestadores de serviços não-Microsoft MDM. Também pode utilizar [o Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) para criar um pacote de [provisionamento](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) e aplicá-lo no HoloLens 2.
Os CSPs mais prováveis que serão aplicados aos seus HoloLens 2 são:

- [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): procuração por perfil Wi-Fi 

[Outros CSPs suportados em dispositivos HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
Uma ligação VPN pode ajudar a fornecer uma ligação mais segura e acesso à rede da sua empresa e à Internet. HoloLens 2 suporta o cliente VPN incorporado e o plug-in VPN da Plataforma Universal windows (UWP). 

Protocolos VPN incorporados suportados:
- IKEv2
- L2TP
- PPTP

Se o certificado for utilizado para a autenticação para o cliente VPN incorporado, o certificado de cliente necessário deve ser adicionado à loja de certificados do utilizador. Para saber se um plug-in VPN de 3ª parte suporta HoloLens 2, vá à Loja para localizar a aplicação VPN e verificar se o HoloLens está listado como um dispositivo suportado e na página System Requirement a app suporta a arquitetura ARM ou ARM64. O HoloLens só suporta aplicações da Plataforma Universal windows para VPN de terceiros.

 A VPN pode ser gerida pelo MDM através [de Definições/AllowVPN,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)e definida através da  [política VPNv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

Saiba mais sobre [como configurar a VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) com [estes guias.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)  

### <a name="vpn-via-ui"></a>VPN via UI

A VPN não é ativada por padrão, mas pode ser ativada manualmente abrindo a aplicação **Definições** e navegando para  **a Rede & Internet -> VPN**.
1. Selecione um fornecedor VPN.
1. Crie um nome de ligação. 
1. Insira o nome ou endereço do seu servidor.
1. Selecione o tipo VPN.
1. Selecione o tipo de informação de login. 
1. Opcionalmente adicione o nome de utilizador e a palavra-passe.
1. Aplique as definições VPN. 

![Configurações hololens VPN](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>VPN definido através do pacote de provisionamento

> [!TIP] 
> No nosso Windows Holographic, versão 20H2, corrigimos um problema de configuração proxy para a ligação VPN. Por favor, considere atualizar dispositivos para esta construção se pretender utilizar este fluxo.

1. Lançar Designer de Configuração do Windows.
1. Clique em **dispositivos Provision HoloLens,** em seguida, selecione o dispositivo-alvo e **next**.
1. Insira o nome e o caminho do pacote.
1. Clique **em Switch para editor avançado.**
1. Configurações de **tempo de execução abertas**  ->  **ConectividadeProfiles**  ->  **VPN**  ->  **VPNSettings**.
1. Configure VPNProfileName
1. Selecione ProfileType: **Native** or **Third Part**.
    1. Para o perfil nativo, selecione **NativeProtocolType**, em seguida, configurar servidor, política de encaminhamento, tipo de autenticação e outras definições.
    1. Para o perfil de "Terceiros", configurar o URL do servidor, o nome da família do pacote plug-in VPN (apenas 3 configurações predefinidas) e personalizadas.
1. Exporte o seu pacote.
1. Ligue os HoloLens e copie o ficheiro .ppkg ao dispositivo. 
1. No HoloLens, aplique o VPN .ppkg abrindo o menu Iniciar e selecionando **Definições** De Acesso à  ->  **Conta**  ->  **ou escola**  ->  **Adicionar ou remover pacote de provisionamento** -> Selecione o seu pacote VPN.


### <a name="setting-up-vpn-via-intune"></a>Criação de VPN via Intune
Basta seguir os documentos do Intune para começar. Ao seguir estes passos, tenha em mente os protocolos VPN incorporados que os dispositivos HoloLens suportam. 

[Crie perfis VPN para ligar aos servidores VPN no Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).

[Windows 10 e Windows Holographic device configurações para adicionar ligações VPN usando Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).

Quando terminar, lembre-se de [atribuir o perfil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).

### <a name="vpn-via-3rd-party-mdm-solutions"></a>VPN através de soluções MDM de 3º partido
Exemplo de ligação VPN de 3ª parte:
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

Exemplo nativo do IKEv2 VPN:
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Desativação Wi-Fi em HoloLens (1ª geração)

### <a name="using-the-settings-app-on-hololens"></a>Utilização da aplicação Definições em HoloLens

1. Abra o menu **Iniciar.**
1. Selecione a aplicação **Definições** a partir do **Início** ou da lista **de Todas as Aplicações** no menu **'Início'** à direita. A aplicação **Definições** será colocada automaticamente à sua frente.
1. Selecione **Rede & Internet**.
1. Selecione o interruptor de slider Wi-Fi para movê-lo para a posição **Off.** Isto irá desligar os componentes RF do rádio Wi-Fi e desativar todas as funcionalidades Wi-Fi em HoloLens.

    > [!WARNING]
    > Quando o rádio Wi-Fi estiver desativado, os HoloLens não poderão carregar automaticamente os seus [espaços](hololens-spaces.md).

1. Mova o interruptor de slider para a posição **On** para ligar o rádio Wi-Fi e restaurar a funcionalidade Wi-Fi no Microsoft HoloLens. O estado de rádio Wi-Fi selecionado **(Ligado** ou **Desligado)** persistirá através de reboots.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identificação do endereço IP dos seus HoloLens na rede Wi-Fi

### <a name="by-using-the-settings-app"></a>Utilizando a aplicação Definições

1. Abra o menu **Iniciar.**
1. Selecione a aplicação **Definições** a partir do **Início** ou da lista **de Todas as Aplicações** no menu **'Início'** à direita. A aplicação **Definições** será colocada automaticamente à sua frente.
1. Selecione **Rede & Internet**.
1. Desloque-se para baixo para baixo da lista de redes Wi-Fi disponíveis e selecione **propriedades de Hardware**.

    ![Propriedades de hardware em configurações Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   O endereço IP aparece ao lado **do endereço IPv4**.

### <a name="by-using-voice-commands"></a>Usando comandos de voz

Dependendo da construção dos seus dispositivos, pode utilizar comandos de voz incorporados ou cortana para exibir o seu endereço IP. Sobre as construções depois de [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) falar "Qual é o meu endereço IP?" e será exibido. Para construções anteriores ou HoloLens (1ª gen) dizer "Hey Cortana, Qual é o meu endereço IP?" e cortana mostrará e lerá o seu endereço IP.

### <a name="by-using-windows-device-portal"></a>Utilizando o Portal do Dispositivo Windows

1. Num navegador web no seu PC, abra o portal do [dispositivo](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Navegue para a secção **de Networking.**  
   Esta secção apresenta o seu endereço IP e outras informações de rede. Ao utilizar este método, pode copiar e colar o endereço IP no seu PC de desenvolvimento.

## <a name="change-ip-address-to-static-address"></a>Alterar endereço IP para endereço estático
### <a name="by-using-settings"></a>Utilizando Definições
 
1. Abra o menu **Iniciar.**
1. Selecione a aplicação **Definições** a partir do **Início** ou da lista **de Todas as Aplicações** no menu **'Início'** à direita. A aplicação **Definições** será colocada automaticamente à sua frente.
1. Selecione **Rede & Internet**.
1. Desloque-se para baixo para baixo da lista de redes Wi-Fi disponíveis e selecione **propriedades de Hardware**.
1. Na janela de **definições IP de edição,** altere o primeiro campo para **Manual**.
1. Insira a configuração IP desejada nos campos restantes e, em seguida, clique em **Guardar**.

### <a name="by-using-windows-device-portal"></a>Utilizando o Portal do Dispositivo Windows

1. Num navegador web no seu PC, abra o portal do [dispositivo](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Navegue para a secção **de Networking.**
1. Selecione o botão **de configuração IPv4.**
1. Selecione **Utilize o seguinte endereço IP** e insira a configuração TCP/IP desejada.
1. Selecione **Utilize os seguintes endereços de servidor DNS** e introduza os endereços de servidor DNS preferidos e alternativos, se necessário.
1. Clique em **Guardar**. 