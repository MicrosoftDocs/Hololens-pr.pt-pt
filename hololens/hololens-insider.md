---
title: Pré-visualização de insider para Microsoft HoloLens
description: Saiba como começar com as construções do Insider e forneça feedback valioso para a nossa próxima grande atualização do sistema operativo para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 52503c0e1ff8c937211500203b91a30806cd317d
ms.sourcegitcommit: 74f5b64c67026881c8ae46410f272b22862ff582
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/26/2021
ms.locfileid: "114696323"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Pré-visualização de insider para Microsoft HoloLens

Bem-vindos às mais recentes construções de Insider Preview para HoloLens! É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer feedback valioso para a nossa próxima grande atualização do sistema operativo para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notas de lançamento de insider

Estamos entusiasmados por começar a voar novas funcionalidades para Windows Insiders novamente. Novas construções serão voadas para os Canais Dev e Beta para as últimas atualizações. Continuaremos a atualizar esta página à medida que adicionamos mais funcionalidades e atualizações ao nosso Windows o Insider constrói. Fique animado e pronto para misturar estas atualizações na sua realidade.

| Funcionalidade                 | Descrição                | Utilizador ou Cenário | Construção introduzida |
|-------------------------|----------------------------|--------------|------------------|
| [Alterações do CSP para reportar detalhes HoloLens](#csp-changes-for-reporting-hololens-details) | Novos CSPs para consulta de dados | Administradores de TI    | 20348.1403                 |
| [Política de login automático controlada pela CSP](#auto-login-policy-controlled-by-csp) | Usado para iniciar sessão numa conta automaticamente | Administradores de TI | 20348.1405 |
| [Suporte de ficheiro PFX para Gestor de Certificados](#pfx-file-support-for-certificate-manager) | Adicione pfx certs via Definições UI | Utilizador Final | 20348.1405 |
| [Ver relatório de diagnóstico avançado em Definições sobre HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Ver registos de diagnóstico do MDM no dispositivo | Resolução de problemas | 20348.1405 |
| [Notificações de Diagnóstico Offline](#offline-diagnostics-notifications) | Feedback audiovisual para coleção de registos | Resolução de problemas | 20348.1405 |
| [Utilize apenas aplicativos de loja privada apenas para Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Configure a app da loja para mostrar apenas apps da organização | Administrador de TI | 20348.1408 |
| [Correções e melhorias](hololens-insider.md#fixes-and-improvements) | Correções e melhorias para HoloLens. | Todos | 20348.1408 |

### <a name="csp-changes-for-reporting-hololens-details"></a>Alterações do CSP para reportar detalhes HoloLens

- Introduzido em Windows insider build, 20348.1403

Os seguintes CSPs foram atualizados com novas formas de reportar informações dos seus dispositivos HoloLens.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - Armazenamento grátis

O DevDetail CSP também informa agora espaço de armazenamento gratuito no HoloLens dispositivo. Isto deve corresponder aproximadamente ao valor mostrado na página de Armazenamento da app Definições. Segue-se o nó específico que contém esta informação.

- ./DevDetail/Ext/Microsoft/FreeStorage (apenas operação GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP - SSID e BSSID

O DeviceStatus CSP informa agora também o SSID e o BSSID de Wi-Fi rede com a qual HoloLens está ativamente ligado. Seguem-se os nós específicos que contêm esta informação.

- ./Fornecedor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address do adaptador de Wi-Fi*/SSID
- ./Fornecedor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address do adaptador Wi-Fi*/BSSID

Blob de sincronização de exemplo (para fornecedores de MDM) para consulta para NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>Política de login automático controlada pela CSP

Esta nova política DomLogonUser controla se um utilizador será automaticamente iniciado. Alguns clientes querem configurar dispositivos que estejam ligados a uma identidade, mas não querem qualquer experiência de inscrição. Imagine pegar num dispositivo e utilizar imediatamente assistência remota. Ou ter o benefício de poder distribuir rapidamente HoloLens dispositivos e permitir que os seus utilizadores finais acelerem o login.

Quando a apólice é definida como um valor não vazio, especifica o endereço de e-mail do utilizador de início de sím em si. O utilizador especificado deve apresentar-se ao dispositivo pelo menos uma vez para ativar o início de sísmis automático.

O OMA-URI do novo valor de cadeia de políticas `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- O utilizador com o mesmo endereço de e-mail terá o início de são automático ativado.

Num dispositivo em que esta política está configurada, o utilizador especificado na política terá de se apresentar pelo menos uma vez. As reinicializações subsequentes do dispositivo após o primeiro início de sessão terão o utilizador especificado automaticamente ligado. Apenas um único utilizador de início de sítido automático é suportado. Uma vez ativado, o utilizador registado automaticamente não poderá iniciar sessão manualmente. Para se apresentar como um utilizador diferente, a política deve primeiro ser desativada.

> [!NOTE]
> - Alguns eventos, como as principais atualizações do SO, podem exigir que o utilizador especificado volte a apresentar-se ao dispositivo para retomar o comportamento do início de sé. 
> - O logotipo automático só é suportado para utilizadores de MSA e AAD.

### <a name="pfx-file-support-for-certificate-manager"></a>Suporte de ficheiro PFX para Gestor de Certificados

Introduzido em Windows insider build 20348.1405. Adicionámos apoio ao [Gestor de Certificados](certificate-manager.md) para agora usar certificados .pfx. Quando os utilizadores navegam para **Definições**  >  **Atualizar &**  >  **Certificados de** Segurança , e selecione **Instalar um certificado,** o UI agora suporta o ficheiro de certificado .pfx.
Os utilizadores podem importar certificado .pfx, com chave privada, para a loja de utilizadores ou loja de máquinas.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Ver relatório de diagnóstico avançado em Definições sobre HoloLens

Para dispositivos geridos quando o comportamento de resolução de problemas, confirmar que uma configuração de política esperada é aplicada é um passo importante. Anteriormente a esta nova funcionalidade, esta tinha de ser feita fora do dispositivo via MDM ou perto do dispositivo depois de exportar registos de diagnóstico do MDM recolhidos através **do Definições**  ->  **Contas** Access  >  **ou escola**, e selecione **Exporte os seus registos de gestão** e seja visualizado num PC próximo.

Agora o DIAGNÓSTICO MDM pode ser visto no dispositivo usando o navegador Edge. Para ver mais facilmente o relatório de diagnóstico do MDM, navegue para a página de Access work ou school, e **selecione Ver relatório de diagnóstico avançado**. Isto gerará e abrirá o relatório numa nova janela Edge.

![Consulte o relatório de diagnóstico avançado na aplicação Definições.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Notificações de Diagnóstico Offline

Esta é uma atualização para uma funcionalidade existente chamada [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics). Anteriormente, não havia um indicador claro para os utilizadores de que tinham desencadeado a recolha de diagnóstico ou que tinham concluído.
Agora adicionado no Windows builds Insider, existem duas formas de feedback audiovisual para diagnóstico offline. A primeira a ser torras notificações exibidas para ambos quando a recolha começa e completa. Estes serão apresentados quando o utilizador iniciar sessão e tiver visuais.

![Torrada para recolher troncos.](./images/logcollection1.jpg)

![Torradas quando a recolha de registos estiver completa.](./images/logcollection2.jpg)
 
Como os utilizadores usam frequentemente o Offline Diagnostics como um mecanismo de recolha de registos de recuo para quando não têm acesso a um ecrã, não podem fazer login ou ainda estão no OOBE, haverá também uma sugestão de áudio reproduzida quando os registos são recolhidos. Este som será reproduzido para além da notificação de torradas.

Esta nova funcionalidade será ativada quando o dispositivo atualizar, e não necessita de ser ativada ou gerida. Em qualquer caso que este novo feedback não possa ser exibido ou ouvido, o Offline Diagnostics continuará a ser gerado.

Esperamos que com esta mais recente adição de feedback audiovisual seja mais fácil recolher dados de diagnóstico e, mais rapidamente, ser capaz de resolver os seus problemas.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Utilize apenas aplicativos de loja privada para Microsoft Store

A política RequerPrivateStoreOnly foi ativada para HoloLens. Esta política permite configurar a aplicação Microsoft Store apenas para mostrar a loja privada configurada para a sua organização. Limitando o acesso apenas às aplicações que disponibilizou.

Saiba mais sobre [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="fixes-and-improvements"></a>Correções e melhorias

- Corrigiu um [problema conhecido para o Portal do Dispositivo onde não havia qualquer solicitação de descarregamento de ficheiros bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Corrigi um [problema conhecido para o Portal do Dispositivo com upload de ficheiros e descarregamento de tempo.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Aborda questões relacionadas com a denúncia de propriedades de conformidade a partir de dispositivos HoloLens; pode ser necessário reiniciar para que o relatório correto seja acionado nas construções insider.  
- Atualize a versão in-box do Remote Assist que está instalada em flashes frescos.


## <a name="start-receiving-insider-builds"></a>Comece a receber construções insider

> [!NOTE]
> Se ainda não foi atualizado recentemente, por favor reinicie o seu dispositivo para atualizar o estado e obter a mais recente construção.
> - O comando de voz "Reboot device" funciona bem. 
> - Também pode escolher o botão de reinício no programa insider Definições/Windows.
>
> Tivemos uma escuta na parte de trás que podes ter encontrado e isto vai pôr-te de volta aos trilhos.

Num dispositivo HoloLens 2, vá para **Definições**  >  **Update & Security** Windows Insider  >  **Program** e **selecione Get start**. Ligue a conta que usou para se registar como Windows Insider.

Windows infiltrado está agora a mudar-se para os Canais. O anel **Rápido** tornar-se-á o **Canal Dev**, o anel **Lento** passará a ser o **Canal Beta**, e o anel **de pré-visualização** de lançamento tornar-se-á o **Canal de Pré-visualização de Lançamento**. Aqui está o que o mapeamento parece:

![Windows Explicação dos Canais Internos](images/WindowsInsiderChannels.png)

Para mais informações, consulte [a introdução Windows canais Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nos blogs Windows.
Em seguida, selecione **Ative development of Windows**, escolha se gostaria de receber construções de **Dev Channel** ou Beta **Channel** e reveja os termos do programa.
**Selecione Confirm > Reinicie agora** para terminar. Depois de o seu dispositivo ter sido reiniciado, vá a **Definições > Update & Security > Verifique se há novidades** para obter a mais recente construção.

### <a name="update-error-0x80070490-work-around"></a>Atualizar erro 0x80070490 trabalho

Se encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, experimente o seguinte trabalho de curto prazo. Envolve mover o seu canal de insider, pegar na atualização e, em seguida, mover o seu canal Insider de volta.

#### <a name="stage-one---release-preview"></a>Fase um - Visualização de lançamento

1.  Definições, Update & Security, Windows Insider Program, selecione **Release Preview Channel**.

2.  Definições, Atualizar segurança &, Windows Update, **verificar as atualizações**. Depois da atualização, continue para a fase dois.

#### <a name="stage-two---dev-channel"></a>Fase dois - Canal Dev

1. Definições, Update & Security, Windows Insider Program, selecione **Dev Channel**.

2. Definições, Atualizar segurança &, Windows Update, **verificar as atualizações**.

## <a name="ffu-download-and-flash-directions"></a>Direções de descarregamento e flash da FFU

Para testar com um voo assinado ffu, primeiro tem de voar desbloqueando o seu dispositivo antes de piscar o voo assinado ffu.

1. No PC:
    1. Faça o download para o seu PC a partir de [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instalar o ARC (Advanced Recovery Companion) a partir do Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. No HoloLens - Desbloqueio de voo: Abrir **Definições**  >  **atualizar & segurança** Windows Insider  >  **Program** e depois inscrever-se, reiniciar o dispositivo.

1. Flash FFU - Agora pode piscar o voo assinado FFU usando ARC.

### <a name="provide-feedback-and-report-issues"></a>Fornecer problemas de feedback e relatório

Por favor, use [a aplicação Feedback Hub](hololens-feedback.md) no seu HoloLens para fornecer problemas de feedback e relatório. A utilização do Feedback Hub garante que todas as informações necessárias de diagnóstico estão incluídas para ajudar os nossos engenheiros a depurar e resolver rapidamente o problema.  Os problemas com a versão chinesa e japonesa de HoloLens devem ser reportados da mesma forma.

> [!NOTE]
> Não se esqueça de aceitar a solicitação que pergunta se pretende que o Feedback Hub aceda à pasta Documentos (selecione **Sim** quando solicitado).

## <a name="note-for-developers"></a>Nota para desenvolvedores

É bem-vindo e encorajado a tentar desenvolver as suas aplicações usando as construções insider de HoloLens.  Confira a [documentação do programador HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar. As mesmas instruções funcionam com as construções de HoloLens.  Pode usar as mesmas construções de Unidade e Visual Studio que já está a usar para HoloLens desenvolvimento.

## <a name="stop-receiving-insider-builds"></a>Pare de receber builds Insider

Se já não quiser receber as construções insider de Windows Holographic, pode optar por sair quando o seu HoloLens estiver a executar uma construção de produção, ou pode recuperar o [seu dispositivo](hololens-recovery.md) utilizando o Advanced Recovery Companion para recuperar o seu dispositivo para uma versão não-Insider de Windows Holographic.

> [!CAUTION]
> Existe um problema conhecido em que os utilizadores que não se matriculam no Insider Preview constroem depois de reinstalarem manualmente uma nova construção de pré-visualização experimentariam um ecrã azul. Depois, devem recuperar manualmente o seu dispositivo. Para mais detalhes sobre se você seria impactado ou não, por favor, veja mais sobre esta [Edição Conhecida.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Para verificar se o seu HoloLens está a executar uma construção de produção:

1. Vá ao **Definições > System > About**, e encontre o número de construção.

1. [Consulte as notas de lançamento para os números de construção de produção](hololens-release-notes.md).

Para excluir as construções insider:

1. Numa HoloLens executar uma construção de produção, vá a **Definições > Update & Security > Windows Insider Program**, e selecione **Builds Stop Insider**.

1. Siga as instruções para desativar o seu dispositivo.
