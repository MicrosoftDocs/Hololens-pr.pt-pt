---
title: Gerir a identidade do utilizador e iniciar s-in para HoloLens
description: Saiba como gerir a identidade do utilizador, suporte a vários utilizadores, segurança, autenticação da empresa e iniciar sação para dispositivos HoloLens.
keywords: HoloLens, utilizador, conta, AAD, Azure AD, adfs, conta microsoft, MSA, credenciais, referência
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e4c68ad6535293f916cc92c42204954110edc4fe
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189550"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Gerir a identidade do utilizador e iniciar s-in para HoloLens

> [!NOTE]
> Este artigo é uma referência técnica para profissionais de TI e entusiastas da tecnologia. Se estiver à procura de HoloLens configurar instruções, leia "[Configurar o seu HoloLens (1ª gen)](hololens1-start.md)" ou "[Configurar o seu HoloLens 2](hololens2-start.md)".

Tal como outros dispositivos Windows, HoloLens funciona sempre num contexto de utilizador. Há sempre uma identidade de utilizador. HoloLens trata a identidade quase da mesma forma que outros dispositivos Windows. Este artigo é uma referência profunda para a identidade em HoloLens, e foca-se em como HoloLens difere de outros dispositivos Windows.

HoloLens suporta vários tipos de identidades de utilizador. Pode utilizar uma ou mais contas de utilizador para iniciar scontabilidade. Aqui está uma visão geral dos tipos de identidade e opções de autenticação no HoloLens:

| Tipo de identidade | Contas por dispositivo | Opções de autenticação |
| --- | --- | --- |
| [Azure Ative Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Fornecedor de credenciais web Azure</li><li>App Azure Authenticator</li><li>Biométrico (Íris) &ndash; HoloLens 2 apenas<sup>2</sup> </li><li>Chave de segurança FIDO2</li><li>PIN &ndash; Opcional para HoloLens (1ª gen), necessário para HoloLens 2</li><li>Palavra-passe</li></ul> |
| [Conta Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biométrico (Íris) &ndash; HoloLens 2</li><li>PIN &ndash; Opcional para HoloLens (1ª gen), necessário para HoloLens 2</li><li>Palavra-passe</li></ul> |
| [Conta local](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Palavra-passe |

As contas ligadas à nuvem (Azure AD e MSA) oferecem mais funcionalidades porque podem usar os serviços Azure.  
> [!IMPORTANT]
> 1 - não é necessário Azure AD Premium para entrar no aparelho. No entanto, é necessário para outras funcionalidades de uma implementação baseada em nuvem de baixo toque, como a inscrição automática e o Autopilot.

> [!NOTE]
> 2 - Enquanto um dispositivo HoloLens 2 pode suportar até 64 contas AZure AD, apenas 31 dessas contas podem inscrever-se na Autenticação iris. Isto está alinhado com outras [opções de autenticação biométrica para Windows Hello para o Negócio](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

> [!IMPORTANT]
> 3 - Uma conta local só pode ser configurada num dispositivo [através de um pacote de provisionamento durante o OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup), não pode ser adicionada mais tarde na aplicação de definições. Se quiser utilizar uma conta local num dispositivo que já está configurado, terá de voltar a [ser reflash ou reiniciar o dispositivo.](hololens-recovery.md)

## <a name="setting-up-users"></a>Criação de utilizadores

Há duas formas de criar um novo utilizador no HoloLens. A forma mais comum é durante a experiência fora de caixa HoloLens (OOBE). Se utilizar Azure Ative Directory, [outros utilizadores podem iniciar sessão](#setting-up-multi-user-support-azure-ad-only) após o OOBE utilizando as suas credenciais AZure AD. HoloLens dispositivos que são inicialmente configurado com uma msa ou conta local durante o OOBE não suportam vários utilizadores. Consulte configuração do seu [HoloLens (1º gênero)](hololens1-start.md) ou [HoloLens 2](hololens2-start.md).

Se utilizar uma conta empresarial ou organizacional para iniciar scontabilidade para HoloLens, HoloLens se inscreve na infraestrutura de TI da organização. Esta inscrição permite ao seu Administrador de TI configurar a Gestão de Dispositivos Móveis (MDM) para enviar políticas de grupo para o seu HoloLens.

Tal como Windows noutros dispositivos, a sessão durante a configuração cria um perfil de utilizador no dispositivo. O perfil do utilizador armazena aplicações e dados. A mesma conta também fornece O Único Sign-on para aplicações, como Edge ou o Microsoft Store, utilizando as APIs do Gestor de Conta Windows.

Por padrão, como para outros dispositivos Windows 10, terá de iniciar sposição novamente quando HoloLens reiniciar ou retomar de espera. Pode usar a aplicação Definições para alterar este comportamento, ou o comportamento pode ser controlado pela política do grupo.

### <a name="linked-accounts"></a>Contas ligadas

Tal como na versão desktop de Windows, pode ligar credenciais adicionais de conta web à sua conta HoloLens. Esta ligação facilita o acesso a recursos através ou dentro de apps (como a Loja) ou para combinar o acesso a recursos pessoais e de trabalho. Depois de ligar uma conta ao dispositivo, pode conceder permissão para usar o dispositivo em apps para que não tenha de iniciar scontabilidade em cada aplicação individualmente.

A ligação de contas não separa os dados do utilizador criados no dispositivo, como imagens ou downloads.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Criação de suporte multiutilizador (apenas AZure AD)

HoloLens suporta vários utilizadores do mesmo inquilino AZure AD. Para utilizar esta funcionalidade, tem de utilizar uma conta que pertença à sua organização para configurar o dispositivo. Posteriormente, outros utilizadores do mesmo inquilino podem iniciar sôms no dispositivo a partir do ecrã de inscrição ou tocando no azulejo do utilizador no painel Iniciar. Apenas um utilizador pode ser inscrito de cada vez. Quando um utilizador assina, HoloLens assina o utilizador anterior. 

>[!IMPORTANT]
> O primeiro utilizador do dispositivo é considerado o proprietário do dispositivo, exceto no caso do Azure AD Join, [saiba mais sobre os proprietários do dispositivo](security-adminless-os.md#device-owner).

Todos os utilizadores podem utilizar as aplicações instaladas no dispositivo. No entanto, cada utilizador tem os seus próprios dados e preferências de aplicações. A remoção de uma aplicação do dispositivo remove-a para todos os utilizadores.  

Os dispositivos configurados com contas AD Azure não permitirão iniciar sessão no dispositivo com uma Conta Microsoft. Todas as contas subsequentes utilizadas devem ser contas AD Azure do mesmo inquilino que o dispositivo. Pode ainda [iniciar sôs-lhe a utilização de uma Conta Microsoft para aplicações](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) que a suportam (como a Microsoft Store). Para alterar a utilização de contas AD AZure para as Contas da Microsoft para iniciar sessão no dispositivo, tem de voltar a utilizar [o dispositivo](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1ª gen)** começou a apoiar vários utilizadores de AD Azure na Atualização de Windows 10 abril de [2018](/windows/mixed-reality/release-notes-april-2018) como parte de [Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Vários utilizadores listados no Sinal no ecrã

Anteriormente, o ecrã Sign In apresentava apenas o mais recentemente assinado no utilizador, bem como um ponto de entrada "Outro utilizador". Recebemos o feedback do cliente de que isso não é suficiente se vários utilizadores se inscreverem no dispositivo. Ainda eram obrigados a reescrever o seu nome de utilizador, etc.

Introduzido em [Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)ao selecionar **Outro utilizador** que está localizado à direita do campo de entrada PIN, o Sinal no ecrã apresentará vários utilizadores com o qual já se tenham assinado previamente no dispositivo. Isto permite que os utilizadores selecionem o seu perfil de utilizador e, em seguida, inscrevam-se utilizando as suas credenciais de Windows Hello. Um novo utilizador também pode ser adicionado ao dispositivo a partir desta página de Outros utilizadores através do botão **de conta Adicionar.**

Quando estiver no menu Outros utilizadores, o botão Outros utilizadores apresentará o último utilizador assinado no dispositivo. Selecione este botão para voltar ao Sinal no ecrã para este utilizador.

![Predefinição do ecrã de inscrição.](./images/multiusers1.jpg)

<br>

![Teste de saturação de outros utilizadores.](./images/multiusers2.jpg)

## <a name="removing-users"></a>Remoção de utilizadores

Pode remover um utilizador do dispositivo indo para **Definições**  >  **Contas Outras**  >  **pessoas**. Esta ação também recupera espaço removendo todos os dados da aplicação do utilizador do dispositivo.  

## <a name="using-single-sign-on-within-an-app"></a>Usando um único sinal dentro de uma aplicação

Como desenvolvedor de aplicações, pode tirar partido das identidades ligadas no HoloLens utilizando as [APIs do Gestor de Conta Windows](/uwp/api/Windows.Security.Authentication.Web.Core), tal como faria noutros dispositivos Windows. Algumas amostras de código para estas APIs estão disponíveis em GitHub: [Amostra de gestão de conta web](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Qualquer conta interrompe que possa ocorrer, como solicitar o consentimento do utilizador para informações de conta, autenticação de dois fatores, etc., deve ser tratada quando a app solicitar um token de autenticação.

Se a sua aplicação necessitar de um tipo de conta específico que não tenha sido previamente ligado, a sua aplicação pode solicitar ao utilizador que adicione um. Este pedido desencadeia o painel de definições da conta para ser lançado como uma criança modal da sua aplicação. Para aplicações 2D, esta janela renderiza diretamente sobre o centro da sua aplicação. Para aplicações Unidade, este pedido retira brevemente o utilizador da sua aplicação holográfica para tornar a janela da criança. Para obter informações sobre a personalização dos comandos e ações neste painel, consulte [a Classe WebAccountCommand](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Empresa e outra autenticação

Se a sua aplicação utilizar outros tipos de autenticação, como NTLM, Basic ou Kerberos, pode utilizar [Windows UI credencial](/uwp/api/Windows.Security.Credentials.UI) para recolher, processar e armazenar as credenciais do utilizador. A experiência do utilizador para recolher estas credenciais é muito semelhante a outras interrupções de conta baseadas na nuvem, e aparece como uma aplicação infantil em cima da sua aplicação 2D ou suspende brevemente uma aplicação Unidade para mostrar a UI.

## <a name="deprecated-apis"></a>APIs precatados

Uma das formas pelas quais o desenvolvimento para HoloLens difere do desenvolvimento para desktop é que a API [onlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) não é totalmente suportada. Embora a API devolva um token se a conta principal estiver em boas condições, as interrupções como as descritas neste artigo não exibem UI para o utilizador e não autenticam corretamente a conta.

## <a name="frequently-asked-questions"></a>Perguntas mais frequentes

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>A Windows Hello para o Negócios é apoiada na HoloLens (1ª Gen)?

Windows Hello for Business (que suporta a utilização de um PIN para iniciar sedus) é suportado para HoloLens (1ª Gen). Para permitir Windows Hello para o sôm-in do Business PIN em HoloLens:

1. O dispositivo HoloLens deve ser [gerido pelo MDM](hololens-enroll-mdm.md).
1. Tem de Windows Hello ativar o Negócios para o dispositivo. (Ver[instruções para Microsoft Intune.](/intune/windows-hello))
1. No HoloLens, o utilizador pode então utilizar **Definições**  >  **Opções de Inscrição**  >  **Adicionar PIN** para configurar um PIN.

> [!NOTE]
> Os utilizadores que iniciarem sôms usando uma conta Microsoft também podem configurar um PIN em **Definições**  >  **Opções de Inscrição**  >  **Adicionar PIN**. Este PIN está associado a [Windows Hello,](https://support.microsoft.com/help/17215/windows-10-what-is-hello)em vez de [Windows Hello para o Negócios.](/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Como é implementada a autenticação biométrica da Iris no dia 2 HoloLens?

HoloLens 2 suporta a autenticação iris. A Iris baseia-se na tecnologia Windows Hello e é suportada para utilização tanto por Azure Ative Directory como pelas Contas Microsoft. A íris é implementada da mesma forma que outras tecnologias Windows Hello, e alcança [a segurança biométrica FAR de 1/100K](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello).

Consulte os [requisitos e especificações biométricos para Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) para obter mais informações. Saiba mais sobre [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) e [Windows Hello para Negócios.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="where-is-iris-biometric-information-stored"></a>Onde é armazenada a informação biométrica da Iris?

A informação biométrica da íris é armazenada localmente em cada HoloLens por [Windows Hello especificações](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored). Não é partilhado e está protegido por duas camadas de encriptação. Não é acessível a outros utilizadores, mesmo a um administrador, porque não existe uma conta de administrador numa HoloLens.

### <a name="do-i-have-to-use-iris-authentication"></a>Tenho de usar a autenticação da Iris?
Não, pode saltar este passo durante a configuração. 

![Trama iris.](./images/setup-iris.png)

HoloLens 2 oferece muitas opções diferentes para a autenticação, incluindo chaves de segurança FIDO2.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>A informação da Iris pode ser removida do HoloLens?
Sim, pode removê-lo manualmente em Definições.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Como é que o tipo de conta afeta o comportamento de inscrição?

Se aplicar políticas de inscrição, a política é sempre respeitada. Se não for aplicada nenhuma política de inscrição, estes são os comportamentos predefinidos para cada tipo de conta:

- **Azure AD**: pede a autenticação por defeito e configurável por **Definições** para deixar de pedir a autenticação.
- **Conta Microsoft**: o comportamento de bloqueio é diferente permitindo o desbloqueio automático, no entanto, o sinal de autenticação ainda é necessário no reboot.
- **Conta local**: pede sempre a autenticação sob a forma de uma palavra-passe, não configurável em **Definições**

> [!NOTE]
> Atualmente, os temporizadores de inatividade não são suportados, o que significa que a política **AllowIdleReturnWithoutPassword** só é respeitada quando o dispositivo entra em StandBy.

## <a name="additional-resources"></a>Recursos adicionais

Leia muito mais sobre a proteção de identidade do utilizador e autenticação na [documentação de segurança e identidade Windows 10](/windows/security/identity-protection/).

Saiba mais sobre a criação de infraestruturas de identidade híbridas completamente a [documentação de identidade Azure Hybrid.](/azure/active-directory/hybrid/)
