---
title: Configurar HoloLens como um quiosque
description: Aprenda a configurar e a usar uma configuração de quiosque para bloquear as aplicações em dispositivos HoloLens.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e7f1efa99cc16b1003bd7063817451013ed2ec2661dbdf02edcd89c7984d0980
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663969"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configurar HoloLens como um quiosque

Pode configurar um dispositivo HoloLens para funcionar como um dispositivo de uso fixo, também chamado de *quiosque*, configurando o dispositivo para funcionar em modo de quiosque. O modo quiosque limita as aplicações (ou utilizadores) que estão disponíveis no dispositivo. O modo quiosque é uma funcionalidade conveniente que pode usar para dedicar um dispositivo HoloLens a aplicações empresariais ou para utilizar o dispositivo HoloLens numa demonstração de apps.

Este artigo fornece informações sobre aspetos da configuração do quiosque que são específicos para HoloLens dispositivos. Para obter informações gerais sobre os diferentes tipos de quiosques baseados em Windows e como configurá-los, consulte [quiosques de configuração e sinais digitais nas edições Windows desktop](/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> O modo quiosque determina quais as aplicações disponíveis quando um utilizador assina o dispositivo. No entanto, o modo quiosque não é um método de segurança. Não impede que uma aplicação "permitida" abra outra aplicação que não é permitida. Para bloquear a abertura de apps ou processos, utilize [Windows Defender CSP do Controlo de Aplicações (WDAC)](/windows/client-management/mdm/applicationcontrol-csp) para criar políticas adequadas.
>
> Saiba mais sobre o serviços Microsoft para dar aos utilizadores um nível avançado de segurança que HoloLens 2 utiliza, leia mais sobre [separação e isolamento do Estado - Proteções do Defender](security-state-separation-isolation.md#defender-protections). Ou aprenda a [usar o WDAC e Windows PowerShell para permitir ou bloquear aplicações em HoloLens 2 dispositivos com Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

Pode utilizar o modo quiosque numa única aplicação ou numa configuração multi-aplicação, e pode utilizar um dos três processos para configurar e implementar a configuração do quiosque.

> [!IMPORTANT]  
> A eliminação da configuração multi-aplicações remove os perfis de bloqueio do utilizador que a funcionalidade de acesso atribuída criou. No entanto, não reverte todas as mudanças de política. Para reverter estas políticas, tem de redefinir o dispositivo para as definições de fábrica.

## <a name="plan-the-kiosk-deployment"></a>Planeie a implantação do quiosque

Ao planear o seu quiosque, terá de ser capaz de responder às seguintes perguntas. Aqui estão algumas decisões a considerar ao ler esta página e algumas considerações para estas questões.
1. **Quem vai usar o seu Quiosque, e que [tipo de conta](hololens-identity.md) eles vão usar?** Esta é uma decisão que provavelmente já tomou e não deve ser ajustada por causa do seu quiosque, mas irá afetar a forma como o Quiosque é atribuído mais tarde.
1. **Precisa de ter quiosques diferentes por utilizador/grupo ou um quiosque não habilitado para alguns?** Em caso afirmativo, deverá criar o seu Quiosque via XML. 
1. **Quantas aplicações estarão no seu quiosque?** Se tiver mais de 1 aplicação, precisará de um Quiosque multi-aplicações. 
1. **Que aplicativo(s) estará no seu Quiosque?** Por favor, use a nossa lista de AUMIDs abaixo para adicionar quaisquer aplicações In-Box além das suas.
1. **Como planeia implantar o seu quiosque?** Se está a inscrever o dispositivo no MDM, então sugerimos que use o MDM para implantar o seu quiosque. Se não estiver a utilizar o MDM, a implementação com o Pacote de Provisionamento está disponível.  

### <a name="kiosk-mode-requirements"></a>Requisitos do modo quiosque

Pode configurar qualquer dispositivo HoloLens 2 para utilizar o modo quiosque.

> [!IMPORTANT]
> O modo quiosque só está disponível se o dispositivo tiver Windows Holographic for Business. Todos os HoloLens 2 dispositivos enviam com Windows Holographic for Business e não há outras edições. Cada HoloLens 2 dispositivos é capaz de executar o modo quiosque fora da caixa.
>
> HoloLens dispositivos (1ª geração) precisam de ser atualizados tanto em termos de construção de SISTEMA como de edição de SISTEMA. Aqui está mais informações sobre a atualização de um HoloLens (1ª gen) para [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edição. Para atualizar um dispositivo HoloLens (1ª geração) para utilizar o modo quiosque, deve primeiro certificar-se de que o dispositivo funciona Windows 10, versão 1803 ou versão posterior. Se utilizou a Ferramenta de Recuperação de Dispositivos Windows para recuperar o dispositivo HoloLens (1ª gen) para a sua construção predefinida, ou se instalou as atualizações mais recentes, o seu dispositivo está pronto a configurar.

> [!IMPORTANT]  
> Para ajudar a proteger os dispositivos que funcionam no modo quiosque, considere adicionar políticas de gestão de dispositivos que desativam funcionalidades como a conectividade USB. Além disso, verifique as definições do anel de atualização para se certificar de que as atualizações automáticas não ocorrem durante o horário comercial.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Decida entre um quiosque de uma única aplicação ou um quiosque multi-aplicações

Um quiosque de uma única aplicação inicia a aplicação especificada quando o utilizador se inscreve no dispositivo. O menu Iniciar está desativado, assim como Cortana. Um dispositivo HoloLens 2 não responde ao gesto [Iniciar.](hololens2-basic-usage.md#start-gesture) Um dispositivo HoloLens (1ª gen) não responde ao gesto [de floração.](hololens1-basic-usage.md) Como apenas uma aplicação pode ser executada, o utilizador não pode colocar outras aplicações.

Um quiosque multi-aplicações exibe o menu Iniciar quando o utilizador assina o dispositivo. A configuração do quiosque determina quais as aplicações disponíveis no menu Iniciar. Você pode usar um quiosque multi-aplicações para fornecer uma experiência fácil de entender para os utilizadores, apresentando-lhes apenas as coisas que eles têm que usar, e removendo as coisas que eles não precisam usar.

A tabela seguinte lista as capacidades de funcionalidade nos diferentes modos de quiosque.

| &nbsp; |Menu Iniciar |Menu de Ações Rápidas |Câmera e vídeo |Miracast |Cortana |Comandos de voz incorporados |
| --- | --- | --- | --- | --- | --- | --- | 
|Quiosque de aplicações únicas |Desativado |Desativado |Desativado |Desativado   |Desativado |Habilidoso<sup>1</sup> |
|Quiosque multi-aplicativo |Ativado |Ativado<sup>2</sup> |Disponível<sup>2</sup> |Disponível<sup>2</sup> |Disponível<sup>2, 3</sup>  |Habilidoso<sup>1</sup> |

> <sup>1</sup> Os comandos de voz que se relacionam com as funcionalidades desativadas não funcionam.  
> <sup>2</sup> Para obter mais informações sobre como configurar estas funcionalidades, consulte [as aplicações de quiosque Select](#plan-kiosk-apps).  
> <sup>3</sup> Mesmo que Cortana esteja desativado, os comandos de voz incorporados estão ativados.

A tabela que se segue lista as funcionalidades de suporte do utilizador dos diferentes modos de quiosque.

| &nbsp; |Tipos de utilizadores suportados | Inscrição automática | Vários níveis de acesso |
| --- | --- | --- | --- |
|Quiosque de aplicações únicas | Conta Microsoft (MSA) em Azure Ative Directory (Azure AD) ou conta local |Yes |No |
|Quiosque multi-aplicativo |Conta do Azure AD |No |Yes |

Por exemplo, como utilizar estas capacidades, consulte a tabela seguinte.

|Utilize um quiosque de uma única aplicação para: |Utilize um quiosque multi-aplicações para: |
| --- | --- |
|Um dispositivo que executa apenas um Guia Dinâmico 365 para novos colaboradores. |Um dispositivo que executa guias e assistência remota para uma série de funcionários. |
|Um dispositivo que executa apenas uma aplicação personalizada. |Um dispositivo que funciona como um quiosque para a maioria dos utilizadores (executando apenas uma aplicação personalizada), mas funciona como um dispositivo padrão para um grupo específico de utilizadores. |

### <a name="plan-kiosk-apps"></a>Planeie aplicativos de quiosque

Para obter informações gerais sobre como escolher aplicações de quiosque, consulte [Diretrizes para escolher uma aplicação para acesso atribuído (modo quiosque)](/windows/configuration/guidelines-for-assigned-access-app).

Se utilizar o Portal do Dispositivo Windows para configurar um quiosque de uma única aplicação, selecione a aplicação durante o processo de configuração.  

Se utilizar um sistema de Gestão de Dispositivos Móveis (MDM) ou um pacote de provisionamento para configurar o modo quiosque, utilize o [Fornecedor de Serviços de Configuração de Configuração de Acordos (CSP)](/windows/client-management/mdm/assignedaccess-csp) atribuído para especificar aplicações. O CSP utiliza [IDs de Modelo de Utilizador de Aplicações (AUMIDs)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) para identificar aplicações. A tabela que se segue lista os AUMIDs de algumas aplicações na caixa que pode utilizar num quiosque multi-aplicações.

> [!IMPORTANT]
> O modo quiosque determina quais as aplicações disponíveis quando um utilizador assina o dispositivo. No entanto, o modo quiosque não é um método de segurança. Não impede que uma aplicação "permitida" abra outra aplicação que não é permitida. Como não restringimos este comportamento, as aplicações ainda podem ser lançadas a partir de Edge, Explorer de Ficheiros e aplicações Microsoft Store. Se existirem aplicações específicas que não pretende serem lançadas a partir de um quiosque, utilize [Windows Defender CSP de Controlo de Aplicações (WDAC)](/windows/client-management/mdm/applicationcontrol-csp) para criar políticas apropriadas. 
> 
> Além disso, o Mixed Reality Home não pode ser definido como uma aplicação de quiosque.

<a id="aumids"></a>

|Nome da Aplicação |AUMID |
| --- | --- |
|Espectador 3D |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Calendário |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Câmara<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Picker de dispositivo em HoloLens (1ª geração) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Picker do dispositivo no HoloLens 2 |A Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DispositivosFlowHost |
|Dinâmica 365 Guias |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dinâmico 365 Assistência Remota |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Centro de Feedback &nbsp; |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Explorador de Ficheiros |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Correio |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Nova Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Loja Microsoft |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> |&nbsp; |
|Filmes & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Fotografias |A Microsoft. Windows. Fotos \_ 8wekyb3d8bbwe \! App |
|Definições |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nova Definições |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Sugestões |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Para ativar a captura de fotografias ou vídeos, tem de ativar a aplicação Camera como uma aplicação de quiosque.  
> <sup>2</sup> Quando ativar a aplicação Camera, esteja atento às seguintes condições:
> - O menu Quick Actions inclui os botões Fotografia e Vídeo.  
> - Também deve ativar uma aplicação (como Fotos, Correio ou OneDrive) que possa interagir ou recuperar fotografias.  
>  
> <sup>3</sup> Mesmo que não ative Cortana como uma aplicação de quiosque, os comandos de voz incorporados estão ativados. No entanto, os comandos que estão relacionados com funcionalidades desativadas não têm qualquer efeito.  
> <sup>4</sup> Não é possível ativar diretamente Miracast. Para permitir Miracast como uma aplicação de quiosque, ativar a aplicação Camera e a app Device Picker.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Planear perfis de quiosque para utilizadores ou grupos

Ao criar o ficheiro xml ou utilizar a UI do Intune para configurar um quiosque, terá de considerar quem será o utilizador do Quiosque. Uma configuração de quiosque pode ser limitada a uma conta individual ou a grupos AD Azure. 

Normalmente, os quiosques são ativados para um utilizador ou grupo de utilizadores. No entanto, se planeia escrever o seu próprio Quiosque XML, então é melhor considerar o Acesso Atribuído Global, no qual o Quiosque é aplicado ao nível do dispositivo, independentemente da Identidade. Se isto apelar para [ler mais sobre os quiosques de acesso atribuídos globais.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Se estiver a criar um ficheiro XML:
-   Vocês criam vários perfis de Quiosque e atribuem cada um a diferentes utilizadores/grupos. Como um quiosque para o seu Grupo AD Azure que tem muitas aplicações, e um Visitante que tem um quiosque de aplicações múltiplas com uma app singular.
-   A configuração do seu quiosque será chamada de **Id de Perfil** e terá um GUID.
-   Irá atribuir esse Perfil na secção configs especificando o tipo de utilizador e utilizando o mesmo GUID para o **Id PadrãoProfile**.
- Um ficheiro XML pode ser criado mas ainda aplicado a um dispositivo via MDM, criando um perfil de configuração de dispositivo OMA URI personalizado e aplicando-o a HoloLens grupo de dispositivos utilizando o valor URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Se está a criar um quiosque em Intune.
-   Cada dispositivo só pode receber um único perfil de Quiosque, caso contrário criará um conflito e não receberá nenhuma configuração de quiosque. 
    -   Outros tipos de perfis e políticas, tais como restrições de dispositivos que não estão relacionadas com o perfil de configuração do quiosque, não entram em conflito com o perfil de configuração do quiosque.
-   O quiosque será ativado para todos os utilizadores que façam parte do tipo de logon do Utilizador, este será definido com um utilizador ou grupo AD AZure. 
-   Depois de definida a configuração do quiosque e do **tipo de logon do Utilizador** (utilizadores que podem iniciar sessão no quiosque) e as Aplicações serem selecionadas, a Configuração do Dispositivo ainda deve ser atribuída a um grupo. O(s) grupo(s) atribuído determina quais os dispositivos que recebem a configuração do dispositivo quiosque, no entanto não interage se o quiosque estiver ativado ou não. 
    - Para uma discussão completa sobre os efeitos da atribuição de perfis de configuração no Intune, consulte [os perfis do utilizador e do dispositivo de atribuição em Microsoft Intune](/intune/configuration/device-profile-assign).

### <a name="select-a-deployment-method"></a>Selecione um método de implementação

Pode selecionar um dos seguintes métodos para implementar configurações de quiosque:

- [Microsoft Intune ou outro serviço de gestão de dispositivos móveis (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Pacote de provisionamento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Portal do Dispositivo](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Uma vez que este método requer que o Modo de Desenvolvimento seja ativado no dispositivo, recomendamos que o utilize apenas para demonstrações.

A tabela que se segue lista as capacidades e benefícios de cada um dos métodos de implantação.

| &nbsp; |Implementar utilizando Windows Portal do Dispositivo |Implementar utilizando um pacote de provisionamento |Implementar utilizando o MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Implementar quiosques de aplicações únicas   | Yes           | Yes                  | Yes  |
|Implementar quiosques multi-aplicativos    | No            | Yes                  | Yes  |
|Implementar apenas para dispositivos locais | Yes           | Yes                  | No   |
|Implementar utilizando o Modo de Desenvolvimento |Necessário       | não é necessário            | não é necessário   |
|Implementar utilizando Azure Ative Directory (Azure AD)  | não é necessário            | não é necessário                   | Necessário  |
|Implementar automaticamente      | No            | No                   | Yes  |
|Velocidade de implantação            | Rápido       | Rápido                 | Lento |
|Implementar à escala | Não recomendado    | Recomendado        | Recomendado |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Utilize Microsoft Intune ou outros MDM para configurar um quiosque de aplicações únicas ou multi-aplicações

Para configurar o modo quiosque utilizando Microsoft Intune ou outro sistema MDM, siga estes passos.

1. [Prepare-se para inscrever os dispositivos.](#mdmenroll)
1. [Crie um perfil de configuração de quiosque](#mdmprofile).
1. Configuure o quiosque.
   - [Configure as definições para um quiosque de uma única aplicação](#mdmconfigsingle).
   - [Configure as definições para um quiosque multi-aplicações](#mdmconfigmulti).
1. [Atribua o perfil de configuração do quiosque a um grupo](#mdmassign).
1. Desdobre os dispositivos.
   - [Implemente um quiosque de uma única aplicação.](#mdmsingledeploy)
   - [Implemente um quiosque multi-aplicações.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, passo 1 &ndash; Prepare-se para inscrever os dispositivos

Pode configurar o seu sistema MDM para inscrever HoloLens dispositivos automaticamente quando o utilizador entrar pela primeira vez ou fazer com que os utilizadores inscrevam os dispositivos manualmente. Os dispositivos também devem ser unidos ao seu domínio AZure AD, e atribuídos aos grupos apropriados.

Para obter mais informações sobre como inscrever os dispositivos, consulte [inscrever HoloLens nos](hololens-enroll-mdm.md) métodos de inscrição de MDM e [Intune para dispositivos Windows](/mem/intune/enrollment/windows-enrollment-methods).

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, passo 2 &ndash; Criar um perfil de configuração de quiosque

1. Abra o portal [Azure](https://portal.azure.com/) e inscreva-se na sua conta de administrador Intune.
1. Selecione **Microsoft Intune**  >  **configuração do dispositivo - Perfis** Criar  >  **perfil**.
1. Insira um nome de perfil.
1. Selecione **plataforma**  >  **Windows 10 e mais tarde**, e, em seguida, selecione   > **restrições do tipo** de perfil dispositivo .
1. Selecione **Configure**  >  **Kiosk**, e, em seguida, selecione um dos seguintes:
   - Para criar um quiosque de uma única aplicação, selecione  >  **quiosque de aplicações únicas** do Modo Kiosk .
   - Para criar um quiosque multi-aplicações, selecione   >  **quiosque multi-aplicação** Modo Kiosk Mode .
1. Para começar a configurar o quiosque, selecione **Add**.

Os próximos passos diferem consoante o tipo de quiosque que deseja. Para mais informações, selecione uma das seguintes opções:  

- [Quiosque de aplicações únicas](#mdmconfigsingle)
- [Quiosque multi-aplicativo](#mdmconfigmulti)

Para obter mais informações sobre como criar um perfil de configuração de quiosque, consulte [as definições Windows 10 e Windows Holographic for Business do dispositivo para funcionar como um quiosque dedicado usando o Intune](/intune/configuration/kiosk-settings).

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, passo 3 (single-app) &ndash;  Configurar as definições para um quiosque de uma única aplicação

Esta secção resume as configurações que um quiosque de uma única aplicação requer. Para mais detalhes, consulte os seguintes artigos:

- Para obter informações sobre como configurar um perfil de configuração de quiosque em Intune, consulte [Como configurar o modo de quiosque utilizando Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obter mais informações sobre as definições disponíveis para quiosques de aplicações únicas no Intune, consulte [quiosques de aplicações de ecrã completo single](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Para outros serviços de MDM, consulte a documentação do seu fornecedor para obter instruções. Se tiver de utilizar uma configuração XML personalizada para configurar um quiosque no seu serviço MDM, [crie um ficheiro XML que defina a configuração do quiosque](#ppkioskconfig).

1. Selecione **a conta de utilizador do tipo utilizador**  >  **Local**, e, em seguida, insira o nome de utilizador da conta local (dispositivo) ou da Conta Microsoft (MSA) que pode iniciar scontabilidade no quiosque.
   > [!NOTE]  
   > Os tipos de conta de utilizador de **início de sessão automático** não são suportados pelo Windows Holographic for Business.
1. Selecione **aplicação de tipo de**  >  **aplicação Application Store** e, em seguida, selecione uma aplicação da lista.

O teu próximo passo é [atribuir](#mdmassign) o perfil a um grupo.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, passo 3 (multi-app) &ndash; Configurar as definições para um quiosque multi-aplicações

Esta secção resume as configurações que um quiosque multi-aplicações requer. Para obter informações mais detalhadas, veja os seguintes artigos:

- Para obter informações sobre como configurar um perfil de configuração de quiosque em Intune, consulte [Como configurar o modo de quiosque utilizando Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obter mais informações sobre as configurações disponíveis para quiosques multi-aplicações no Intune, consulte [quiosques multi-aplicações](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Para outros serviços de MDM, consulte a documentação do seu fornecedor para obter instruções. Se precisar de utilizar uma configuração XML personalizada para configurar um quiosque no seu serviço MDM, [crie um ficheiro XML que defina a configuração do quiosque](#ppkioskconfig). Se utilizar um ficheiro XML, certifique-se de que inclui o [layout Iniciar](#start-layout-for-hololens).  
- Pode utilizar opcionalmente um layout de início personalizado com intune ou outros serviços DEDM. Para obter mais informações, consulte [o ficheiro de layout iniciar para MDM (Intune e outros)](#start-layout-file-for-mdm-intune-and-others).

1. Selecione **Windows 10-alvo nos dispositivos do modo**  >  **S Nº**.  
>[!NOTE]  
> O modo S não é suportado na Windows Holographic for Business.

1. Selecione **o utilizador do tipo**  >  **Azure AD do tipo Azure** ou grupo ou do tipo de início de **súm HoloLens**  >  **visitante**, e adicione um ou mais grupos ou contas de utilizadores.  

   Apenas os utilizadores que pertençam aos grupos ou contas que especifique no **tipo de início de saúde do Utilizador** podem utilizar a experiência do quiosque.

1. Selecione uma ou mais aplicações utilizando as seguintes opções:
   - Para adicionar uma aplicação de linha de negócios carregada, selecione **adicionar a aplicação da loja** e, em seguida, selecione a aplicação que deseja.
   - Para adicionar uma aplicação especificando o seu AUMID, **selecione Adicionar por AUMID** e, em seguida, insira o AUMID da aplicação. [Consulte a lista de AUMIDs disponíveis](#aumids)

O teu próximo passo é [atribuir](#mdmassign) o perfil a um grupo.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, passo 4 &ndash; Atribua o perfil de configuração do quiosque a um grupo

Utilize a página **atribuições** do perfil de configuração do quiosque para definir onde pretende que a configuração do quiosque seja implantada. No caso mais simples, atribua o perfil de configuração do quiosque a um grupo que conterá o dispositivo HoloLens quando o dispositivo se matricula no MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, passo 5 (single-app) &ndash; Implementar um quiosque de aplicações únicas

Quando utilizar um sistema MDM, pode inscrever o dispositivo em MDM durante o OOBE. Depois de terminar o OOBE, iniciar sessão no dispositivo é fácil.

Durante a OOBE, siga estes passos:

1. Faça o sessão utilizando a conta especificada no perfil de configuração do quiosque.
1. Inscreva o dispositivo. Certifique-se de que o dispositivo é adicionado ao grupo a que o perfil de configuração do quiosque está atribuído.
1. Aguarde que o OOBE termine, para que a app da loja descarregue e instale, e que as políticas sejam aplicadas. Em seguida, reinicie o dispositivo.

Da próxima vez que iniciar sôs no dispositivo, a aplicação de quiosque deve começar automaticamente.

Se não vir a configuração do quiosque neste momento, [verifique o estado de atribuição](/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, passo 5 (multi-app) &ndash; Implementar um quiosque multi-aplicações

Quando utilizar um sistema MDM, pode juntar o dispositivo ao seu inquilino AZure AD e inscrever o dispositivo em MDM durante o OOBE. Se adequado, forneça as informações de inscrição aos utilizadores para que os disponibilizem durante o processo OOBE.

> [!NOTE]  
> Se atribuiu o perfil de configuração do quiosque a um grupo que contém utilizadores, certifique-se de que uma dessas contas de utilizador é a primeira conta a iniciar sessão no dispositivo.

Durante a OOBE, siga estes passos:

1. Inscreva-se utilizando a conta que pertence ao grupo do **tipo de início de sção** do Utilizador.
1. Inscreva o dispositivo.
1. Aguarde por quaisquer aplicações que fazem parte do perfil de configuração do quiosque para descarregar e instalar. Além disso, aguarde que as políticas sejam aplicadas.  
1. Depois de terminar o OOBE, pode instalar aplicações adicionais a partir da loja da Microsoft ou por sideloading. [Aplicações necessárias](/mem/intune/apps/apps-deploy#assign-an-app) para o grupo que o dispositivo pertence para instalar automaticamente.
1. Após o fim da instalação, reinicie o aparelho.

Da próxima vez que iniciar serção no dispositivo utilizando uma conta que pertença ao **tipo de logon do Utilizador,** a aplicação de quiosque deverá ser lançada automaticamente.

Se não vir a configuração do quiosque neste momento, [verifique o estado de atribuição](/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Utilize um pacote de provisionamento para configurar um quiosque de aplicações únicas ou multi-aplicações

Para configurar o modo quiosque utilizando um pacote de provisionamento, siga estes passos.

1. [Crie um ficheiro XML que defina a configuração do quiosque,](#ppkioskconfig)incluindo um [layout Iniciar](#start-layout-for-hololens).
2. [Adicione o ficheiro XML a um pacote de provisionamento.](#ppconfigadd)
3. [Aplique o pacote de provisionamento à HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Pacote de provisionamento, passo 1 &ndash; Crie um ficheiro XML de configuração de quiosque

Siga [as instruções gerais para criar um ficheiro XML de configuração](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)de quiosque para Windows ambiente de trabalho, com exceção das seguintes:

- Não inclua aplicações de Windows Clássicas (Win32). HoloLens não apoia estas aplicações.
- Utilize o layout de arranque do [espaço reservado XML](#start-layout-for-hololens) para HoloLens.
- Opcional: Adicione o acesso dos hóspedes à configuração do quiosque

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Opcional: Adicione o acesso dos hóspedes à configuração do quiosque

Na [secção **Configs** do ficheiro XML,](/windows/configuration/lock-down-windows-10-to-specific-apps#configs)pode configurar um grupo especial chamado **Visitante** para permitir que os hóspedes utilizem o quiosque. Quando o quiosque é configurado para apoiar o grupo especial **visitante,** uma opção "**Convidado**" é adicionada à página de inscrição. A conta **Do Cliente** não requer uma senha, e quaisquer dados que esteja associados à conta são eliminados quando a conta assina.

Para ativar a conta **Do Hóspede,** adicione o seguinte corte à configuração do quiosque XML:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Ativar autóloga do visitante

Nas construções [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e em diante:
- As configurações AAD e Non-ADD suportam as contas dos visitantes a serem automaticamente orientadas para os modos quiosque.

##### <a name="non-aad-configuration"></a>Configuração não-AAD

1. Criar um pacote de provisionamento que:
    1. Configurações de tempo de execução/Atribuição De Acesso para permitir contas do Visitante.
    1. Inativamente inscreve o dispositivo em MDM (definições de tempo de execução/Local de Trabalho/Inscrições) para que possa ser gerido mais tarde.
    1. Não crie uma conta local
2. [Aplicar o pacote de provisionamento.](hololens-provisioning.md)

##### <a name="aad-configuration"></a>Configuração AAD

Os dispositivos de aad configurados para o modo quiosque podem assinar numa conta do Visitante com um único toque de botão a partir do sinal no ecrã. Uma vez iniciado na conta do visitante, o dispositivo não solicitará novamente o início até que o Visitante seja explicitamente assinado a partir do menu inicial ou o dispositivo seja reiniciado.

O início de sísmis do Visitor Auto pode ser gerido através da [política personalizada OMA-URI](/mem/intune/configuration/custom-settings-windows-10):

- Valor URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Política |Description |Configurações 
| --------------------------- | ------------- | -------------------- |
| Realidade Mista/VisitanteAutoLogon | Permite um visitante a apresentar um início de saúde a um quiosque. | 1 (Sim), 0 (Não, padrão.) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Layout de início de espaço reservado para HoloLens

Se utilizar um [pacote de provisionamento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) para configurar um quiosque multi-aplicações, o procedimento requer um layout Iniciar. Iniciar a personalização do layout não é suportado em Windows Holographic for Business. Portanto, terá de utilizar um layout de início de espaço reservado.

> [!NOTE]  
> Como um quiosque de uma única aplicação inicia a aplicação de quiosque quando um utilizador assina, não usa um menu Iniciar e não tem de ter um layout Iniciar.

> [!NOTE]  
> Se utilizar [o MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) para configurar um quiosque multi-aplicações, pode utilizar opcionalmente um layout Iniciar. Para obter mais informações, consulte [o ficheiro de layout Do EspaçoHolder Start para MDM (Intune e outros)](#start-layout-file-for-mdm-intune-and-others).

Para o layout Iniciar, adicione a seguinte secção **StartLayout** ao ficheiro XML de provisão de quiosque:

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Espaço reservado Iniciar o ficheiro de layout para MDM (Intune e outros)

Guarde a seguinte amostra como ficheiro XML. Pode utilizar este ficheiro quando configurar o quiosque multi-aplicações em Microsoft Intune (ou em outro serviço MDM que forneça um perfil de quiosque).

> [!NOTE]
> Se tiver de utilizar uma configuração personalizada e uma configuração XML completa para configurar um quiosque no seu serviço MDM, utilize as [instruções de layout Iniciar para um pacote de provisionamento](#start-layout-for-hololens).

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>O Prov. pacote, passo 2 &ndash; Adicione o ficheiro XML de configuração de quiosque a um pacote de provisionamento

1. [Open Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Selecione **Provisão Avançada,** insira um nome para o seu projeto e, em seguida, selecione **Next**.
1. Selecione **Windows 10 Holographic** e, em seguida, selecione **Seguinte**.
1. Selecione **Concluir**. O espaço de trabalho para o seu pacote abre.
1. Selecione **configurações de tempo de**  >  **execução AtribuídasAccess**  >  **MultiAppAssignedAccessettings**.
1. No painel central, **selecione Procurar** para localizar e selecionar o ficheiro XML de configuração de quiosque que criou.

   ![Screenshot do campo MultiAppAssignedAccessettings no Windows Configuration Designer](./images/multiappassignedaccesssettings.png)

1. **Opcional.** (Se pretender aplicar o pacote de provisionamento após a configuração inicial do dispositivo, e houver um utilizador administrativo já disponível no dispositivo de quiosque, ignore este passo.) Selecione **as definições de tempo** de execução &gt;  &gt; **Utilizadores** e, em seguida, crie uma conta de utilizador. Forneça um nome de utilizador e uma palavra-passe e, em seguida, selecione Administradores **do Grupo** de Utilizador  >  .  
  
     Ao utilizar esta conta, pode visualizar o estado de provisionamento e os registos.  
1. **Opcional.** (Se já tiver uma conta não administrada no dispositivo de quiosque, salte este passo.) Selecione **as definições de runtime** &gt;  &gt; **Utilizadores** e, em seguida, crie uma conta de utilizador local. Certifique-se de que o nome de utilizador é o mesmo que na conta que especificou na configuração XML. Selecione   >  **Utilizadores padrão** do Grupo de Utilizador .
1. Selecione **guardar**  >  **ficheiros**.
1. Selecione **pacote**  >  **de provisionamento de exportação** e, em seguida, selecione **Owner**  >  **IT Admin**. Isto define a precedência deste pacote de provisionamento superior ao que os pacotes de provisionamento que são aplicados a este dispositivo a partir de outras fontes.
1. Selecione **Seguinte**.
1. Na página de segurança do **pacote De provisionamento,** selecione uma opção de segurança.
   > [!IMPORTANT]  
   > Se selecionar **Ativar a assinatura do pacote,** também tem de selecionar um certificado válido para utilizar para a assinatura do pacote. Para isso, **selecione Procurar** e selecione o certificado que pretende utilizar para assinar a embalagem.
   
   > [!CAUTION]  
   > Não selecione **Ativar a encriptação do pacote**. Nos dispositivos HoloLens, esta definição faz com que o provisionamento falhe.
1. Selecione **Seguinte**.
1. Especifique o local de saída onde deseja que o pacote de provisionamento vá quando for construído. Por predefinição, Windows Configuration Designer utiliza a pasta do projeto como localização de saída. Se pretender alterar a localização da saída, **selecione Procurar**. Quando terminar, selecione **Seguinte**.
1. Selecione **Build** para começar a construir o pacote. O pacote de provisionamento não demora muito a construir. A página de construção exibe a informação do projeto, e a barra de progresso indica o estado de construção.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Pacote de provisionamento, passo 3 &ndash; Aplicar o pacote de provisionamento à HoloLens

O artigo "Configurar HoloLens através de um pacote de provisionamento" fornece instruções pormenorizadas para aplicar o pacote de provisionamento nas seguintes circunstâncias:

- Pode inicialmente [aplicar um pacote de provisionamento para HoloLens durante a configuração](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- Também pode [aplicar um pacote de provisionamento para HoloLens após a configuração](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Utilize o Portal do Dispositivo Windows para configurar um quiosque de aplicações únicas

Para configurar o modo quiosque utilizando o Portal do Dispositivo Windows, siga estes passos.

1. [Configurar o dispositivo HoloLens para utilizar o Portal do Dispositivo Windows](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). O Portal do Dispositivo é um servidor web no seu HoloLens a que pode ligar a partir de um navegador web no seu PC.

    > [!CAUTION]
    > Quando configurar HoloLens utilizar o Portal do Dispositivo, tem de ativar o Modo de Desenvolvimento no dispositivo. O Modo de Desenvolvimento num dispositivo que tem Windows Holographic for Business permite-lhe carregar as aplicações laterais. No entanto, esta definição cria o risco de um utilizador poder instalar aplicações que não tenham sido certificadas pela Microsoft Store. Os administradores podem bloquear a capacidade de ativar o Modo de Desenvolvimento utilizando a definição de Desbloqueio de **Desenvolvimento de Aplicações/Permitir desbloquear** o desenvolvimento na [Definição de CSP de política](/windows/client-management/mdm/policy-configuration-service-provider). [Saiba mais sobre o Modo Developer.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Num computador, ligue-se ao HoloLens utilizando [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) ou [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).

1. Faça um dos seguintes:
   - Se estiver a ligar-se ao Portal do Dispositivo Windows pela primeira vez, [crie um nome de utilizador e uma palavra-passe](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Introduza o nome de utilizador e a palavra-passe que configura previamente.

    > [!TIP]
    > Se vir um erro de certificado no navegador, siga [estes passos de resolução de problemas](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).

1. No Portal do Dispositivo Windows, selecione **o modo quiosque**.

1. Selecione **Ativar o Modo quiosque,** selecione uma aplicação para executar quando o dispositivo começar e, em seguida, selecione **Guardar**.

    ![Modo quiosque](images/kiosk.png)
1. Reiniciar HoloLens. Se ainda tiver a página do Portal do Dispositivo aberta, pode **selecionar Restart** no topo da página.

> [!NOTE]
> O modo quiosque pode ser definido através da API REST do Portal do Dispositivo fazendo um POST para /api/holographic/kioskmode/configurações com um parâmetro de cadeia de consulta exigido ("kioskModeEnabled&quot; com um valor de &quot;verdadeiro&quot; ou &quot;falso") e um parâmetro opcional ("startupApp" com o valor de um nome de pacote). Tenha em mente que o Portal do Dispositivo se destina apenas a programadores e não deve ser ativado em dispositivos não desenvolvedores. A API REST está sujeita a alterações em futuras atualizações/lançamentos.

## <a name="more-information"></a>Mais informações

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Observe como configurar um quiosque utilizando um pacote de provisionamento.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Global Assigned Access – Modo Quiosque
- Gestão de identidade reduzida para quiosque, permitindo o novo método do quiosque que aplica o modo quiosque ao nível do sistema.

Esta nova funcionalidade permite que um Administrador de TI configuure um dispositivo HoloLens 2 para o modo de quiosque de várias aplicações, que é aplicável a nível do sistema, não possui qualquer afinidade com qualquer identidade no sistema e aplica-se a todos os que assinam no dispositivo. Consulte a [documentação global de quiosque de acesso HoloLens para](hololens-global-assigned-access-kiosk.md) mais detalhes sobre esta nova funcionalidade.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Lançamento automático de uma aplicação em modo quiosque de várias aplicações 
- Experiência focada no lançamento automático de aplicações, aumentando ainda mais as seleções de UI e apps escolhidas para experiências em modo quiosque.

Aplica-se apenas ao modo quiosque de várias aplicações e apenas uma aplicação pode ser designada para lançamento automático utilizando o atributo realçado abaixo na configuração de Acesso Atribuído. 

A aplicação é lançada automaticamente quando o utilizador se inscreve. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Mudanças de comportamento no modo quiosque para lidar com falhas
Ao encontrar falhas na aplicação do modo quiosque, surge o seguinte comportamento:

- Antes de Windows Holographic, a versão 20H2 - HoloLens irá mostrar todas as aplicações no menu Iniciar.
- Windows Holográfico, versão 20H2 - se um dispositivo tiver uma configuração de quiosque que seja uma combinação de acesso global atribuído e membro do grupo AAD atribuído acesso, se determinar a adesão ao grupo AAD falhar, o utilizador verá menu "nada mostrado no início".

![Imagem do que o modo Quiosque agora parece quando falha.](images/hololens-kiosk-failure-behavior.png )


- Começando [por Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)o modo quiosque procura o Global Assigned Access antes de mostrar um menu inicial vazio. A experiência do quiosque irá recair para uma configuração global de quiosque (se presente) em caso de falhas durante o modo quiosque do grupo AAD.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Adesão ao Grupo AD cache Azure para quiosque offline

- Modo quiosque mais seguro eliminando aplicações disponíveis em falhas no modo Kiosk.
- Os quiosques offline habilitados a serem utilizados com grupos AD Azure durante um até 60 dias.

Esta política controla por quantos dias, a cache de membro do grupo AD Azure é permitida para configurações de acesso atribuído direcionadas para grupos AD Azure para serem assinados no utilizador. Uma vez que este valor de política é definido para valor superior a 0 apenas, então cache é usado de outra forma não.  

Nome: AADGroupMembershipCacheValidityInDays valor: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 dias  
Máximo - 60 dias 

Medidas para utilizar corretamente esta política: 
1. Crie um perfil de configuração do dispositivo para quiosques direcionados para os grupos AZure AD e atribua-o a HoloLens dispositivos). 
1. Crie uma configuração personalizada do dispositivo baseado em OMA URI que define este valor de política para o número de dias desejado (> 0) e atribua-o a HoloLens dispositivos). 
    1. O valor URI deve ser introduzido na caixa de texto OMA-URI como ./Fornecedor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode ser entre min/max permitido.
1. Inscreva HoloLens dispositivos e verifique se ambas as configurações são aplicadas no dispositivo. 
1. Deixe o utilizador AD AD 1 iniciar sposição quando a internet estiver disponível, uma vez que a subscrição do grupo AD do utilizador é confirmada com sucesso, a cache será criada. 
1. Agora, o utilizador AD AD 1 pode tirar HoloLens offline e usá-lo para o modo quiosque, desde que o valor da política permita o número de dias X. 
1. Os passos 4 e 5 podem ser repetidos para qualquer outro utilizador Azure AD N. O ponto chave aqui é que qualquer utilizador AD AD Azure deve iniciar sação para o dispositivo usando a Internet para que pelo menos uma vez que possamos determinar que eles são membros do grupo AZure AD para o qual a configuração do Quiosque é alvo. 
 
> [!NOTE]
> Até que o passo 4 seja realizado para um utilizador AD Azure irá experimentar o comportamento de falha mencionado em ambientes "desligados". 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Amostras de código de quiosque XML para HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Modo de quiosque de várias aplicações direcionado para um grupo Azure AD. 
Este quiosque implementa um quiosque que, para os utilizadores do grupo AZure AD, terão um Quiosque ativado que inclui as 3 aplicações: Definições, Remote Assist e Feedback Hub. Para modificar esta amostra a ser utilizada imediatamente, certifique-se de alterar o GUID realçado abaixo para corresponder a um Grupo AD Azure próprio. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Modo de quiosque de várias aplicações direcionado para a conta Azure AD.
Este quiosque implementa um quiosque para um único utilizador, eles terão um Quiosque ativado que inclui as 3 aplicações: Definições, Remote Assist e Feedback Hub. Para modificar esta amostra a ser utilizada imediatamente, certifique-se de alterar a conta abaixo realçada para corresponder a uma Conta AD Azure própria. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

