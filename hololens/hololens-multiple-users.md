---
title: Partilhe o seu HoloLens com várias pessoas
description: Pode configurar HoloLens para serem partilhados por várias contas Azure Ative Directory ou por vários utilizadores que utilizem uma única conta.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600734"
---
# <a name="share-your-hololens-with-multiple-people"></a>Partilhe o seu HoloLens com várias pessoas

## <a name="overview"></a>Descrição Geral

As empresas muitas vezes investem em muitos dispositivos de HoloLens partilhados. A forma como utiliza HoloLens é flexível em todo o tabuleiro, dependendo dos seus requisitos individuais. Aqui está um exemplo de algumas experiências multiutilizadores:

- Uma frota de HoloLens 2 dispositivos é criada através do Windows Autopilot para HoloLens 2, com um portfólio consistente de aplicações da empresa em cada dispositivo. Você definiu alguns perfis de quiosque diferentes, direcionando diferentes grupos AD Azure. Cada utilizador entra no HoloLens utilizando as teclas FIDO2 e assinando na sua própria conta AZure AD, e é apresentado com uma experiência personalizada.
- Um fornecedor de software independente (ISV) aluga HoloLens 2 Dispositivos com Assistência Remota D365 e a sua aplicação de linha de negócios (LOB) para a empresa de um cliente. Estes dispositivos estão configurados para quiosques que incluem apenas a sua aplicação LOB e Remote Assist, e são partilhados em vários utilizadores finais. O WDAC é usado para impedir que a aplicação Definições e Microsoft Edge seja lançada. Incluído com o aluguer é uma bateria USB-C para manter os dispositivos em carga completa durante vários turnos.
- Um utilizador final de uma empresa tenta fazer ajustes para Bluetooth no dispositivo para que possam ligar um novo dispositivo, mas a política de visibilidade da página Definições está habilitada a limitar a página de Dispositivos de serem visualizados. Ainda lhes é permitido aceder a outras páginas conforme necessário, como Wi-Fi para que possam utilizar o Remote Assist em vários locais com o mesmo HoloLens.

## <a name="best-practices"></a>Melhores práticas

Ao planear partilhar os seus dispositivos, existem várias considerações para otimizar o ambiente do dispositivo com base nas necessidades do seu negócio.

- [Identidade e Autenticação](#identity-and-authentication)
- [Gestão de Dispositivos](#device-management)
- [Gestão avançada de dispositivos - Quiosque e WDAC](#advanced-device-management---kiosk-and-wdac)
- [Gestão Física](#physical-management)

### <a name="identity-and-authentication"></a>[Identidade e Autenticação](hololens-identity.md)

Se está a planear ter várias contas num dispositivo, então terá contas AD Azure com todos os modos de autenticação. Estes métodos de autenticação basear-se-ão em [Windows Hello,](/windows-hardware/design/device-experiences/windows-hello)incluindo as teclas Iris e FIDO2.

- As teclas de segurança FIDO 2 são excelentes se tiver vários dispositivos, muitos utilizadores ou estiver constantemente a utilizar novos dispositivos.
- Se tiver 10 ou menos utilizadores, a Iris é uma solução rápida para iniciar solução nos utilizadores que já assinaram o mesmo dispositivo.

### <a name="device-management"></a>[Gestão de Dispositivos](hololens-csp-policy-overview.md)

Se os dispositivos estiverem a ser partilhados entre os utilizadores, é provável que deva utilizar as restrições do dispositivo. Ao utilizar a gestão do dispositivo, pode definir algumas políticas para permitir melhor aos seus utilizadores utilizarem o dispositivo, gerirem as atualizações ou limitarem o que o dispositivo pode fazer. Recomenda-se que reveja as [nossas restrições comuns](hololens-common-device-restrictions.md)para dispositivos , e veja se estas recomendações parecem encaixar-se na sua organização. Assim que souber que políticas pretende utilizar, pode aplicá-las através [dos pacotes de Endpoint Manager (MDM) ou](hololens-mdm-configure.md) de provisionamento da Microsoft.

### <a name="advanced-device-management---kiosk-and-wdac"></a>Gestão avançada de [dispositivos](hololens-kiosk.md) - Quiosque e [WDAC](windows-defender-application-control-wdac.md)

Em alguns casos, pode querer limitar quais as aplicações que podem ser acedidas pelos utilizadores finais. Pode limitar o que os utilizadores de aplicações são apresentados no menu inicial usando o [modo Quiosque](hololens-kiosk.md). O quiosque pode ser configurado para apresentar diferentes menus iniciais baseados no utilizador, grupos Azure ou tipos especiais de utilizadores; tais visitantes ou excluindo os proprietários de dispositivos. Pode escolher várias aplicações, ou apenas uma aplicação. Um quiosque de várias aplicações não impede que uma aplicação lance outra, por isso, se a loja ou outra aplicação estiver disponível, os utilizadores ainda podem lançar outra app.

Também pode querer parar completamente o lançamento de apps ou serviços usando [Windows Defender Application Control (WDAC)](windows-defender-application-control-wdac.md) para restringir as aplicações. O WDAC é diferente do quiosque, porque não altera o UI de HoloLens mas não permite o lançamento de uma aplicação bloqueada.

[Página Definições Visibilidade](settings-uri-list.md) é outra forma de adicionar restrições a um dispositivo. No caso de precisar de conceder aos utilizadores acesso a algumas páginas da aplicação Definições, mas nem tudo o que pode usar página Definições Visibilidade para limitar o acesso. Isto é útil, por exemplo, se os seus utilizadores precisarem de alterar o Wi-Fi, mas não quer que acedam à página Contas.

### <a name="physical-management"></a>Gestão Física

Ao partilhar o dispositivo entre vários utilizadores, existem algumas considerações físicas.

- Certifique-se de que os dispositivos estão a carregar entre os turnos.
- Se um dispositivo for necessário para uma mudança, e precisar de durar vários turnos, considere a utilização de uma bateria externa no início de um turno enquanto o dispositivo ainda tem uma carga significativa por cada [direções de controlo](hololens2-charging.md#managing-heat)de calor .
- Ao armazenar dispositivos, mantenha-os ligados e ligados a uma rede. Esta é a melhor maneira de garantir atualizações de SISTEMA e aplicações.
- Considere como planeia [limpar o dispositivo](hololens2-maintenance.md) entre os utilizadores.
- Para um dispositivo com um único utilizador partilhado se utilizar um PIN/password partilhado para um único utilizador, não coloque o PIN/password na parte lateral do dispositivo.
- Para vários dispositivos com um único utilizador partilhado, utilize várias PINs/passwords.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Partilhe com várias pessoas, cada uma usando a sua própria conta

As contas Azure Ative Directory individuais (Azure AD) são o caso de utilização de identidade preferido e mais seguro para HoloLens 2 utilizadores. Ao utilizar as suas próprias contas AZure AD, vários utilizadores podem manter as suas próprias definições de utilizador e dados do utilizador no dispositivo. Apenas um utilizador pode ser inscrito de cada vez. Quando um utilizador se inscreve, HoloLens assina o utilizador anterior.

Para garantir que várias pessoas podem usar as suas próprias contas no seu HoloLens, siga estes passos para configurá-lo:

1. Quando [configurar o dispositivo,](hololens2-start.md)selecione O meu trabalho ou escola é dono dele e **inscreva-se** utilizando uma conta AD Azure.
1. Depois de terminar a configuração, certifique-se de que as definições da conta (Definições > Contas) incluem **Outros utilizadores**.

> [!NOTE]
> Se o seu dispositivo não foi configurado com uma conta Azure AD, tem de ser [reiniciado ou reatado](hololens-recovery.md) e configurado corretamente.

Para utilizar HoloLens, cada utilizador segue estes passos:

1. Se outro utilizador tiver usado o dispositivo, escolha uma das seguintes opções:
   - Pressione o botão de alimentação uma vez para ir para o standby e, em seguida, pressione o botão de alimentação novamente para voltar ao ecrã de bloqueio
   - Selecione o azulejo do utilizador a partir do **menu Iniciar** ou escolha o sinal no **menu 'Energia'** para iniciar a assinatura do utilizador atual.

1. Utilize as suas credenciais de conta Azure AD para iniciar scontabilidade no dispositivo.  
    - Se for a primeira vez que usa o dispositivo, vai pedir-lhe para [calibrar](hololens-calibration.md) o HoloLens aos seus próprios olhos.
    - Se já utilizou o dispositivo:
        - [Windows Holographic, versão 20H2, construa 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2) ou superior, o ecrã ajusta-se perfeitamente para a qualidade e uma experiência de visualização confortável.
        - As construções anteriores precisarão de calibração manual para se ajustarem aos olhos.

> [!TIP]
> Se um utilizador ainda não se inscreveu num dispositivo, experimente um destes dois métodos para um login mais rápido:
>
> - **Tecla de segurança FIDO 2** : A sua chave de segurança FIDO2 será automaticamente reconhecida e o utilizador não precisará de digitar as suas credenciais de utilizador ou utilizar OFM. Este é o método mais rápido para iniciar sôm num novo dispositivo.
> - **Autenticação na Web** : Quando iniciar súm num novo dispositivo, pode selecionar o link **Iniciar sção a partir de outro dispositivo** que irá gerar um código de caracteres de 9 que pode utilizar no [aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) para iniciar súm na web como utilizador no dispositivo, ou digitar o seu nome de utilizador e palavra-passe usando um teclado para sua conveniência.

Para ver uma lista dos utilizadores do dispositivo ou para remover um utilizador do dispositivo, vá a **contas Definições**  >    >  **Outros utilizadores**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Partilhar com várias pessoas, todos usando a mesma conta

Vários utilizadores também podem partilhar um dispositivo HoloLens enquanto utilizam uma única conta de utilizador. Embora seja preferível que HoloLens utilizadores iniciem sessão no dispositivo com as suas identidades individuais (contas AZure AD), esta não é uma opção em algumas organizações.

Existem dois métodos de dispositivo partilhados disponíveis:

- **Vários utilizadores finais que partilham 1 dispositivo** - um dispositivo HoloLens é atribuído a um espaço designado onde qualquer funcionário pode usar o dispositivo. Exemplos seriam uma sala limpa ou uma suite cirúrgica.

- **Vários utilizadores finais que partilham vários dispositivos** - HoloLens dispositivos estão num espaço de armazenamento partilhado onde os funcionários podem usar qualquer dispositivo. Exemplos seriam uma plataforma petrolífera ou uma concessionária de automóveis/garagem.

Quando um novo utilizador coloca o dispositivo pela primeira vez mantendo a mesma conta assinada, o dispositivo solicita ao utilizador que calibra e personalize rapidamente a experiência de visualização. O dispositivo armazenará a informação de calibração para otimizar automaticamente a qualidade e o conforto da experiência de visualização de cada utilizador. Os utilizadores não precisarão de calibrar o dispositivo novamente.
