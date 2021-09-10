---
title: Limitação da utilização de palavras-passe
description: limitando o uso de palavra-passe para HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, limitação do uso de senha, palavra-passe, senha hololens, entrada, entrada, windows hello, hello, gestor de conta do Windows, FIDO2, FIDO 2, WEBAUTHN, conta local, segurança hololens
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 24cd9b81d0d99afaa0479787b846b423310c6739
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428459"
---
# <a name="limiting-password-use"></a>Limitação da utilização de palavras-passe

A maioria dos sistemas informáticos hoje em dia utilizam as credenciais dos utilizadores como base para a segurança, tornando-as dependentes de senhas reutilizáveis e criadas pelo utilizador. Isto resultou em senhas que se tornaram também a causa mais comum de compromisso de conta e violações de dados. Como exemplo disso, as palavras-passe podem ser intercetadas na transmissão ou roubadas de um servidor (por ataques de phishing ou spray de palavra-passe) e comprometidas para ter acesso a uma conta de utilizador.

Para melhorar a segurança e a proteção da conta, HoloLens 2 tem a capacidade de ativar credenciais "sem palavras-passe" (incluindo Windows Hello) para o início do dispositivo, oferecendo acesso sem emenda à nuvem da Microsoft.

## <a name="signing-in-from-another-device"></a>Iniciar sessão a partir de outro dispositivo

HoloLens 2 oferece opções de entrada de dispositivos remotos para Azure Ative Directory contas de trabalho durante a configuração inicial do dispositivo e o acesso ao utilizador para reduzir a necessidade de escrever senhas complexas e minimizar a necessidade de palavras-passe como credenciais. Os utilizadores e organizações que usam smartcards para autenticar têm dificuldade em usar essas credenciais em dispositivos como HoloLens 2, e muitas vezes as organizações desenvolvem sistemas complicados e processos dispendiosos para contornar o problema. Para resolver este problema, o Azure AD oferece duas opções para o início de súm insusimento sem palavra-passe no HoloLens 2.

O primeiro método de autenticação baseia-se em novas capacidades na aplicação Microsoft Authenticator para fornecer autenticação baseada em chaves que permite uma credencial do utilizador ligada a um dispositivo. Uma vez ativado um inquilino pelo administrador, os utilizadores serão mostrados uma mensagem durante HoloLens configuração do dispositivo, dizendo-lhes para tocarem num número na sua aplicação. Devem então corresponder o número na sua aplicação autenticadora, escolher Aprovar, fornecer o seu PIN ou uma autenticação biométrica e completa para que a sua configuração HoloLens prossiga. Isto é descrito com maior detalhe no [início de sing-in sem palavras-passe](/azure/active-directory/authentication/howto-authentication-passwordless-phone).

O segundo é um fluxo de código do dispositivo que é intuitivo para os utilizadores e não requer nenhuma infraestrutura adicional.  Este comportamento de entrada remota baseia-se em outro dispositivo fidedigno que suporta o mecanismo de autenticação preferido da organização e, quando concluído, os tokens são emitidos de volta para o HoloLens para completar a entrada ou configuração do dispositivo. Os passos neste fluxo são:

  1. Um utilizador que passe pela configuração inicial do dispositivo ou fluxos de entrada no OOBE é apresentado com uma ligação "Iniciar súm em outro dispositivo" e toques nele. Isto inicia um sinal remoto em sessão.
  1. O utilizador é então mostrado uma página de sondagens, que contém um URI curto ( [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) ) que aponta para o ponto final de autenticação do dispositivo do Serviço de Token Seguro AD Ad (STS). O utilizador também é apresentado com um código único que é gerado de forma segura na nuvem e tem um tempo máximo de 15 minutos. Juntamente com a geração de códigos, o Azure AD também cria uma sessão encriptada após o início do sinal remoto a pedido no passo anterior e em conjunto, o URI e o código são usados para aprovar o pedido de entrada remota.
  1. Em seguida, o utilizador navega para o URI a partir de outro dispositivo e é solicitado a introduzir o código apresentado no seu dispositivo HoloLens 2.
  1. Assim que o utilizador introduz o código, o Azure AD STS apresenta uma página indicando o HoloLens 2 dispositivo do utilizador que desencadeou o sinal remoto a pedido e solicitou a geração do código. O utilizador é então solicitado para confirmação para evitar quaisquer ataques de phishing.
  1. Se o utilizador optar por continuar a iniciar sessão na 'aplicação' apresentada, o Azure AD STS solicita ao utilizador as suas credenciais. Na autenticação bem sucedida, o Azure AD STS atualiza a sessão remota em cache como "aprovada" juntamente com um código de autorização.
  1. Por fim, a página de sondagens no dispositivo HoloLens 2 do utilizador recebe uma resposta 'Autorizada' da Azure AD e procede à validação do código do utilizador, ao seu código de autorização armazenado associado e gera fichas OAuth como solicitado para completar a configuração do dispositivo. O token de autenticação criado é válido por 1 hora e o token de atualização tem uma vida útil de 90 dias.

A geração de códigos e os algoritmos de encriptação utilizados neste fluxo são ambos compatíveis com o FIPS. HoloLens 2 dispositivos utilizam o TPM para proteger as chaves do dispositivo e encriptar fichas geradas após a autenticação do utilizador utilizando chaves protegidas por hardware. Mais informações sobre a segurança simbólica no HoloLens 2 são partilhadas no [What is a Primary Refresh Token (PRT)](/azure/active-directory/devices/concept-primary-refresh-token).

## <a name="device-sign-in-with-windows-hello"></a>Iniciar sôs-in com Windows Hello

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) oferece opções sem senha incorporadas diretamente no sistema operativo, permitindo que os utilizadores assinem o dispositivo usando Iris ou PIN. O PIN está sempre disponível como credencial e é necessário para a configuração do dispositivo, enquanto a Íris é opcional e pode ser ignorada. Os utilizadores podem iniciar sintrodução em dispositivos HoloLens utilizando a sua conta pessoal da Microsoft ou [Azure Ative Directory conta de trabalho *sem* introduzir uma palavra-passe](/azure/active-directory/authentication/concept-authentication-passwordless). Opções como estas oferecem aos utilizadores um acesso rápido e seguro à sua experiência de Windows completa, apps, dados, websites e serviços. A estratégia da Microsoft para experiências sem palavras-passe é detalhada aqui.

Quando uma credencial Windows Hello é criada, estabelece uma relação de confiança com um fornecedor de identidade e cria um par-chave assimétrico para a autenticação. Um gesto Windows Hello (como íris ou PIN) proporciona entropia para desencriptar uma chave privada apoiada pelo chip de Plataforma Fidedigna (TPM) do dispositivo. Esta chave privada é então utilizada para assinar pedidos enviados para um servidor autenticado e, após a autenticação bem sucedida, o utilizador tem acesso ao seu correio, imagens e outras definições de conta.

Para mais informações, consulte a seguinte infografia:

  ![Windows Hello Sindundo-se.](images/security-hello-sign-in.png)
  
No gráfico acima apresentado, note que nonce é significa "número uma vez", e é um número gerado aleatório ou semi-aleatório. Uma vez configurada a credencial biométrica ou PIN Windows Hello, nunca sai do dispositivo em que está aloque-se. Mesmo que o PIN Windows Hello do utilizador seja roubado, como por exemplo através de um ataque de phishing, é [inútil sem o dispositivo físico do utilizador](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password).

Para uma maior segurança, as credenciais Windows Hello estão protegidas pelo Módulo de Plataforma Fidedigna (TPM) para tornar as credenciais resistentes e complementadas com proteções anti-martelar contra múltiplas entradas incorretas e proteção de software maliciosa para evitar exposição. Para obter mais informações sobre Sign-On Individuais (SSO), leia esta [visão geral dos métodos SSO](/azure/active-directory/manage-apps/what-is-single-sign-on).

A autenticação da íris recai sobre o PIN. Para configurar um novo PIN (um autenticador forte) no dispositivo, o utilizador deve ter passado recentemente pela [Autenticação Multifactor (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) para completar o processo.

## <a name="single-sign-on-with-web-account-manager"></a>Único s-on com Gestor de Conta Web

O único sindução (SSO) permite que os utilizadores sem palavra-passe assinem o dispositivo, utilizando a conta pessoal do utilizador ou o seu trabalho ou conta escolar. O utilizador é automaticamente autorizado com SSO em todas as aplicações e serviços integrados através das [APIs do Gestor de Conta Web](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

Uma vez que uma identidade tenha sido adicionada através de uma aplicação, pode, com o consentimento do utilizador, ficar disponível para todas as aplicações e serviços usando a integração ao nível do sistema. Isto reduz significativamente o sinal de aplicação em carga e proporciona aos utilizadores uma experiência de identidade perfeita.

Para obter mais informações sobre a implementação de APIs do Gestor de Conta Web, aceda a [APIs do Gestor de Contas Web implementantes.](/windows/uwp/security/web-account-manager)

  ![API de segurança.](images/security-api-img.png)
  
Para suítes de aplicativos com requisitos de autenticação especializados, o quadro do Gestor de Conta Web (WAM) é extensível aos fornecedores de identidade personalizados. Os utilizadores podem descarregar o fornecedor de identidade personalizado, embalado como uma aplicação universal Windows Platform (UWP) a partir do Microsoft Store, para permitir o SSO em outras aplicações integradas com esse fornecedor de identidade.

Para obter mais informações sobre a implementação de fornecedores personalizados de identidade WAM, consulte [a referência API do Fornecedor de Identidade WAM Personalizada.](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello e FIDO2 com WebAuthn

HoloLens 2 pode empregar credenciais de utilizador sem palavra-passe (como chaves de segurança Windows Hello ou FIDO2) para iniciar seduca na web de forma segura através de Microsoft Edge e para sites que suportam o WebAuthn. O FIDO2 permite que as credenciais dos utilizadores aproveitem os dispositivos baseados em padrões para autenticar em serviços online.

> [!Note]
> As especificações [WebAuthn](https://www.w3.org/TR/webauthn/) e FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) são implementadas em serviços. Os metadados assinados especificados pela WebAuthn e pelo FIDO2 fornecem informações – como se o utilizador esteve presente – e verificam a autenticação através do gesto local.

Tal como acontece com Windows Hello, quando o utilizador cria e regista uma credencial FIDO2, o dispositivo (HoloLens 2 ou a chave de segurança FIDO2), gera uma chave privada e pública no dispositivo. A chave privada é armazenada de forma segura no dispositivo, e só pode ser utilizada depois de ser desbloqueada utilizando um gesto local, como um biométrico ou PIN. Quando a chave privada é armazenada, a chave pública é enviada para o sistema de conta Microsoft na nuvem e registada na conta de utilizador associada.

Após iniciar sessão com uma conta MSA e Azure AD, o sistema envia um número ou variável de dados gerado para o dispositivo HoloLens 2 ou FIDO2. O HoloLens 2 ou dispositivo utiliza a chave privada para assinar a identificação. A identificação e os metadados assinados são enviados de volta para o sistema de conta Microsoft e verificados utilizando a chave pública.

Windows Hello e dispositivos FIDO2 implementam credenciais baseadas no dispositivo HoloLens, especificamente o enclave seguro do Módulo de Plataforma Fidedigna incorporado. O enclave TPM armazena a chave privada e requer um biométrico ou PIN para desbloqueá-la. Da mesma forma, uma chave de segurança FIDO2 é um pequeno dispositivo externo com um enclave seguro incorporado que armazena a chave privada e requer um biométrico ou PIN para desbloqueá-lo.

Ambas as opções oferecem autenticação de dois fatores num só passo, requerendo tanto um dispositivo registado como um biométrico ou PIN para iniciar súm. Para mais informações, consulte a autenticação forte com o gráfico e processo gráfico da chave de segurança FIDO2, que se segue.

### <a name="strong-authentication-with-fido2-security-key"></a>Autenticação forte com chave de segurança FIDO2

  ![FIDO IMG.](images/security-fido2-whfb-smaller.png)

1. Utilizador liga chave de segurança FIDO2 para HoloLens 2
1. Windows deteta chave de segurança FIDO2
1. HoloLens envia pedido de auth
1. Azure AD envia de volta nonce
1. Utilizador completa gesto para desbloquear lojas privadas chave no enclave seguro da chave de segurança
1. Chave de segurança FIDO2 assina nonce com chave privada
1. PrT token pedido com nonce assinado é enviado para Azure AD
1. Azure AD verifica a chave FIDO
1. Azure AD devolve PRT e TGT para permitir o acesso aos recursos

MSA e Azure AD estão entre as primeiras partes que contam para apoiar a autenticação sem palavra-passe implementando o WebAuthn.

Para obter mais informações sobre a utilização do WebAuthn com aplicações e/ou SDKs, aceda a [APIs webAuthn para autenticação sem palavra-passe no Windows 10](/windows/security/identity-protection/hello-for-business/webauthnapis).

HoloLens 2 suporta dispositivos de segurança FIDO2 que são implementados para especificar e satisfazer os requisitos listados no [Azure Ative Directory as chaves de segurança FIDO2 sem palavras-passe](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) devem ser suportadas.

## <a name="local-accounts"></a>Contas locais

Uma única conta local pode ser configurada para implementações de modo offline. As contas locais não são ativadas por defeito e devem ser configuradas durante o fornecimento do dispositivo. Devem iniciar sação através de uma palavra-passe e não suportam métodos de autenticação alternativos (como [Windows Hello para Negócios](/windows/security/identity-protection/hello-for-business/hello-overview) ou [Windows Hello).](/windows-hardware/design/device-experiences/windows-hello)

Mais detalhes sobre HoloLens contas de utilizador podem ser encontrados na [HoloLens Identidade](hololens-identity.md).

Os administradores de TI ajustam se o utilizador está autorizado a utilizar uma conta MSA para autenticação e serviços de conexão não relacionados com e-mail através do [AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection). Para políticas de configuração de palavras-passe, políticas de idling e políticas de ecrã de bloqueio, consulte [Bloqueio de Dispositivo](/windows/client-management/mdm/policy-csp-devicelock).
