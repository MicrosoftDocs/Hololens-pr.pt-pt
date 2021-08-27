---
title: Configurar HoloLens como um quiosque
description: Aprenda a configurar e usar uma configuração de quiosque para bloquear as aplicações em dispositivos HoloLens.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 28c431397385c06fb94de410a0763e24e18e4509
ms.sourcegitcommit: 749d617f3f0ce3e6363ff6cd1a03f87b9280f418
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/26/2021
ms.locfileid: "122979377"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configurar HoloLens como um quiosque

## <a name="what-is-kiosk-mode"></a>O que é o modo quiosque?

O modo quiosque é uma funcionalidade onde é possível controlar quais as aplicações que são mostradas no menu inicial quando um utilizador se inscreve para HoloLens. Existem 2 cenários apoiados:

1. **Modo quiosque de aplicações únicas** – Não é apresentado nenhum menu inicial e uma única aplicação é lançada automaticamente, quando o utilizador assina. <br> *Exemplo usa*: Um dispositivo que executa apenas a aplicação Dynamics 365 Guides.
2. **Vários modos de quiosque de aplicações** – menu Iniciar mostra apenas as aplicações, que foram especificadas na configuração do quiosque quando um utilizador assina. Uma aplicação pode ser escolhida para ser lançada automaticamente se desejar. <br> *Exemplo usa*: Um dispositivo que mostra apenas a aplicação Store, o Feedback Hub e Definições app no menu inicial.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Descrição da experiência do modo quiosque quando um utilizador assina

A tabela seguinte lista as capacidades de funcionalidade nos diferentes modos de quiosque.

| &nbsp; |Menu Iniciar |Menu de Ações Rápidas |Câmera e vídeo |Miracast |Cortana |Comandos de voz incorporados |
| --- | --- | --- | --- | --- | --- | --- |
|Quiosque de aplicações únicas |Desativado |Desativado |Desativado |Desativado   |Desativado |Ativado* |
|Quiosque multi-aplicativo |Ativado |Ativado*  |Disponível*  |Disponível* |Disponível*   |Ativado*  |

\*Para obter mais informações sobre como ativar funcionalidades desativadas ou como os comandos de voz interagem com funcionalidades e Cortana ver [HoloLens AUMIDs para aplicações.](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Principais considerações gerais antes de configurar o modo quiosque

1. Determine o tipo de conta de utilizador que se inscreva em HoloLens no seu ambiente - HoloLens suporta contas Azure Ative Directory (AAD), Contas Microsoft (MSA) e contas Locais. Além disso, as contas criadas temporariamente chamadas de hóspedes/visitantes também são suportadas (apenas para dispositivos de junção AAD). Saiba mais na [Managed identidade do utilizador e iniciar sôms para HoloLens](hololens-identity.md).
2. Determine os alvos da experiência do modo quiosque – Seja todos, um único utilizador, certos utilizadores ou utilizadores que sejam membros do grupo(s) AAD, etc.
3. Para o modo de quiosque de várias aplicações, determine as aplicações para mostrar no menu inicial. Para cada aplicação, será necessário o seu [ID do Modelo de Utilizador de Aplicação (AUMID).](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)
4. Determine se o modo quiosque será aplicado a HoloLens através de pacotes de provisionamento de tempo de execução ou servidor de Gestão de Dispositivos Móveis (MDM).

## <a name="security-considerations"></a>Considerações de segurança

O modo quiosque não deve ser considerado como um método de segurança, mas como um meio para controlar a experiência de arranque no início da s inscrever-se. Pode combinar experiência no modo quiosque com opções mencionadas abaixo se existirem necessidades específicas relacionadas com a segurança:

- Quando Definições aplicação estiver configurada para mostrar no modo quiosque e quiser controlar quais as páginas que são mostradas na Definições app, consulte a [Página Definições Visibilidade](settings-uri-list.md)
- Quando pretende controlar o acesso a determinadas capacidades de hardware, por exemplo, câmara, Bluetooth, etc. para determinadas aplicações, etc. consulte [políticas em CSP de política suportadas por HoloLens 2 - Windows Gestão de Clientes](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2). Pode rever as [nossas restrições comuns](hololens-common-device-restrictions.md) de dispositivos para ideias.
- O modo quiosque não bloqueia uma aplicação (configurada como parte da experiência do quiosque) de lançar outras aplicações. Quando pretender bloquear completamente o lançamento de determinadas aplicações/processos no HoloLens, consulte o [Use Windows Defender Application Control em HoloLens 2 dispositivos em Microsoft Intune - Azure](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Principais considerações técnicas para o modo quiosque para HoloLens

Só se aplica se estiver a planear utilizar pacotes de provisionamento de tempo de execução ou criar configurações de quiosque manualmente. A configuração do modo quiosque utiliza uma estrutura hierárquica baseada em XML:

- Um perfil de acesso atribuído define quais as aplicações que são apresentadas no menu inicial no modo quiosque. Pode definir vários perfis na mesma estrutura XML, que podem ser referenciados mais tarde.
- Uma configuração de acesso atribuída refere um perfil e um utilizador-alvo desse perfil, por exemplo, um utilizador específico, ou grupo AAD ou visitante, etc. Pode definir várias configurações na mesma estrutura XML dependendo da complexidade dos seus cenários de utilização (ver secção de cenários suportados abaixo).
- Para saber mais, consulte o [CSP do Cecess Cpcess](/windows/client-management/mdm/assignedaccess-csp)Atribuído.

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Cenários apoiados para modo quiosque baseados no tipo de identidade

Consulte [links de referência](hololens-kiosk-reference.md#kiosk-xml-code-samples) para exemplos baseados no seu cenário e atualize conforme necessário antes da cópia-cola.

> [!NOTE]
> Utilize XML apenas se não utilizar o UI do Intune para criar configuração de quiosque.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Para utilizadores que se inscrevam como conta local ou MSA

| **Experiência de quiosque desejada** | **Configuração recomendada do quiosque** | **Formas de configuração**  | **Observações** |
| --- | --- | --- | --- |
| Todos os utilizadores que assinam recebem experiência de quiosque. | [Configure vários aplicativos Global Assigned Access profile](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução - Multi app](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Acesso global atribuído requer [20H2 e construções mais recentes](hololens-release-notes.md#windows-holographic-version-20h2) |
| O utilizador específico que assina recebe experiência de quiosque.  | [Configure o perfil de acesso único ou múltiplo (conforme necessário) especificando o nome de um utilizador específico.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Consulte as opções suportadas abaixo.](#steps-in-configuring-kiosk-mode-for-hololens) | Para o modo quiosque de aplicações únicas, apenas a conta de utilizador local ou a conta MSA são suportadas no HoloLens. <br> Para vários modos de quiosque de aplicações, apenas a conta MSA ou a conta AAD são suportadas no HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Para utilizadores que se inscrevam como conta AAD

| **Experiência de quiosque desejada** | **Configuração recomendada do quiosque** | **Formas de configuração** | **Observações** |
| --- | --- | --- | --- |
| Todos os utilizadores que assinam recebem experiência de quiosque. | [Configure vários aplicativos Global Assigned Access profile](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução - Multi app](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Acesso global atribuído requer [20H2 e construções mais recentes](hololens-release-notes.md#windows-holographic-version-20h2) |
| Todos os utilizadores que assinam recebem experiência de quiosque, exceto certos utilizadores. | [Configure vários aplicativos Global Assigned Access profile, excluindo certos utilizadores (que devem ser proprietários de dispositivos)](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners). | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução - Multi app](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Acesso global atribuído requer [20H2 e construções mais recentes](hololens-release-notes.md#windows-holographic-version-20h2) |
| Cada utilizador AAD obtém experiência de quiosque separada específica para esse utilizador. | [Configurar a configuração de acesso atribuída para cada utilizador especificando o seu nome de conta AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução - Multi app](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Os utilizadores de diferentes grupos AAD experimentam o modo quiosque que é apenas para o seu grupo. | [Configurar configuração de acesso atribuída para cada grupo AAD pretendido.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução - Multi app](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Quando um utilizador assina e HoloLens está ligado à Internet, se se constatar que esse utilizador é membro do grupo AAD para o qual existe configuração de quiosque, o utilizador pode experimentar quiosque para esse grupo AAD. <br> • [Se não houver internet disponível quando o utilizador iniciar a sação, o utilizador sentirá HoloLens comportamento do modo de avaria.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Se a disponibilidade de internet não for garantida quando o quiosque baseado no grupo AAD tiver de ser utilizado, [considere a utilização da política do AADGroupMembershipCacheValidityInDayspolicy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk). |
| Os utilizadores que precisam de utilizar HoloLens para fins temporários obtêm experiência de quiosque. | [Configuração de acesso atribuída para visitantes](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução - Aplicação única](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • A conta de utilizador temporária é criada automaticamente por HoloLens no momento da sindução e é removida quando o utilizador temporário assina. <br> • Considere a [política de auto-login do visitante.](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Passos na configuração do modo quiosque para HoloLens

As configurações do quiosque podem ser criadas e aplicadas de seguintes formas:

1. Com a UI do servidor MDM, por exemplo, os modelos de quiosque do Intune ou as configurações personalizadas de OMA-URI, que são depois aplicadas remotamente a HoloLens.
2. Com pacotes de provisionamento de tempo de execução, que são então aplicados diretamente a HoloLens.

Aqui estão as seguintes formas de configurar, selecione o separador correspondente ao processo que pretende utilizar.

1. [Microsoft Intune modelo de quiosque de aplicativo único](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune modelo de quiosque de vários aplicativos](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Fornecimento de tempo de execução - Multi app](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Fornecimento de tempo de execução - Aplicação única](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Perguntas Mais Frequentes

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>Como podem as contas dos visitantes automaticamente apresentar-se à experiência do quiosque?

Nas construções [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e em diante:

- As configurações AAD e Non-ADD suportam as contas dos visitantes a serem auferidas para modos quiosque.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>A experiência do quiosque é suportada em HoloLens (1ª geração)?

O modo quiosque só está disponível se o dispositivo tiver Windows Holographic for Business. Todos os HoloLens 2 dispositivos enviam com Windows Holographic for Business e não há outras edições. Cada HoloLens 2 dispositivo é capaz de executar o modo quiosque fora da caixa.

HoloLens dispositivos (1ª geração) precisam de ser atualizados tanto em termos de construção de SISTEMA como de edição de SISTEMA. Aqui está mais informações sobre a atualização de um HoloLens (1ª gen) para [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edição. Para atualizar um dispositivo HoloLens (1ª geração) para utilizar o modo quiosque, deve primeiro certificar-se de que o dispositivo funciona Windows 10, versão 1803 ou versão posterior. Se utilizou a Ferramenta de Recuperação de Dispositivos Windows para recuperar o dispositivo HoloLens (1ª gen) para a sua construção predefinida, ou se instalou as atualizações mais recentes, o seu dispositivo está pronto a configurar.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Como utilizar o portal do dispositivo para configurar quiosques em ambientes não produtivos?

Configurar o [dispositivo HoloLens para utilizar o Portal do Dispositivo Windows](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal). O Portal do Dispositivo é um servidor web no seu HoloLens a que pode ligar a partir de um navegador web no seu PC.

 > [!CAUTION]
 > Quando configurar HoloLens utilizar o Portal do Dispositivo, tem de ativar o Modo de Desenvolvimento no dispositivo. O Modo de Desenvolvimento num dispositivo que tem Windows Holographic for Business permite-lhe carregar as aplicações laterais. No entanto, esta definição cria o risco de um utilizador poder instalar aplicações que não tenham sido certificadas pela Microsoft Store. Os administradores podem bloquear a capacidade de ativar o Modo de Desenvolvimento utilizando a definição de Desbloqueio de **Desenvolvimento de Aplicações/Permitir desbloquear** o desenvolvimento na [Definição de CSP de política](/windows/client-management/mdm/policy-configuration-service-provider). [Saiba mais sobre o Modo Developer.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

O modo quiosque pode ser definido através da API REST do Portal do Dispositivo fazendo um POST para /api/holographic/kioskmode/configurações com um parâmetro de cadeia de consulta exigido ("kioskModeEnabled" com um valor de "verdadeiro" ou "falso") e um parâmetro opcional ("startupApp" com o valor de um nome de pacote). Tenha em mente que o Portal do Dispositivo se destina apenas a programadores e não deve ser ativado em dispositivos não desenvolvedores. A API REST está sujeita a alterações em futuras atualizações/lançamentos.

## <a name="troubleshooting"></a>Resolução de problemas

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problema - Não são mostradas aplicações no menu inicial no modo quiosque

**Sintomas**

Ao encontrar falhas na aplicação do modo quiosque, aparece o seguinte comportamento:

- Antes de Windows Holographic, a versão 20H2 - HoloLens irá mostrar todas as aplicações no menu Iniciar.
- Windows Holográfico, versão 20H2 - se um dispositivo tiver uma configuração de quiosque, que é uma combinação de acesso global atribuído e membro do grupo AAD atribuído acesso, se determinar a adesão ao grupo AAD falhar, o utilizador verá menu "nada mostrado no início".

    ![Imagem do que o modo Quiosque agora parece quando falha.](images/hololens-kiosk-failure-behavior.png )

- Começando [por Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)o modo quiosque procura o Global Assigned Access antes de mostrar um menu inicial vazio. A experiência do quiosque recairá para uma configuração global de quiosque (se presente) se houver falhas durante o modo quiosque do grupo AAD.

**Passos de resolução de problemas**

- Verifique se a AUMID da aplicação está corretamente especificada e não contém versões. Consulte [HoloLens AUMIDs](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) para aplicações de caixa de entrada, por exemplo.
- Certifique-se de que a aplicação está instalada no dispositivo para esse utilizador.
- Se a configuração do quiosque for baseada em grupos AAD, certifique-se de que a conectividade da Internet está presente quando o utilizador AAD entrar. Se desejar configurar a política [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) para que esta possa funcionar sem internet também.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Emissão - Construir um pacote com modo quiosque falhou

**Sintomas**

É mostrado um diálogo como abaixo.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Passos de resolução de problemas**

1. Clique no hiperligação mostrado como no diálogo acima.
1. Abrir .log ICD num editor de texto e o seu conteúdo deve indicar o erro.

> [!NOTE]
> Se tiver feito várias tentativas, verifique as datas no registo. Isto irá ajudá-lo a verificar apenas os problemas atuais.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Emissão – Pacote de provisionamento construído com sucesso, mas não se aplicava.

**Sintomas**

O erro é mostrado ao aplicar o pacote de provisionamento em Hololens

**Passos de resolução de problemas**

1. Navegue na pasta onde existe Windows projeto de Design de Configuração para pacote de provisionamento de tempo de execução.
1. Abra o ICD.log e certifique-se de que não há erros no registo enquanto constrói o pacote de provisionamento. Alguns erros não estão a aparecer durante a construção, mas ainda estão registados no ICD.log

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Emissão – Várias aplicações atribuídas ao grupo AAD não funcionam

**Sintomas**

No sôm-in do utilizador AAD, o dispositivo não entra no modo quiosque

**Passos de resolução de problemas**

- Confirme na configuração de acesso atribuído XML que o GUID do grupo AAD de que o utilizador inscrito é membro do utilizador é utilizado e não o GUIADOr do utilizador AAD.
- Confirme que no portal Intune o utilizador AAD é de facto mostrado como membro do grupo AAD direcionado.
