---
title: Guia de implantação de clientes externos
description: Guia de implementação para HoloLens 2 para Clientes Externos (com assistência remota como exemplo)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378542"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Implantação de HoloLens 2 a Clientes Externos com Assistência Remota

Este guia ajuda os profissionais de TI com os seguintes objetivos a implementar dispositivos Microsoft HoloLens 2 na sua organização:

1. Cloud conecta dispositivos HoloLens 2
1. Emprestar holoLens 2 dispositivos a clientes externos para uso
1. Dispositivos emprestados seguros

Este guia fornecerá [recomendações gerais de implantação hololes 2](#general-deployment-recommendations-and-instructions) que são aplicáveis à maioria dos cenários de implementação hololes 2 e [preocupações comuns](#common-concerns) que os clientes têm ao implementar assistência remota para uso externo.

## <a name="scenario-description"></a>Descrição do Cenário

Para efeitos deste documento, a Empresa Contoso quer enviar um dispositivo HoloLens 2 para uma fábrica de clientes externos para uso a curto ou longo prazo. Quando o cliente necessitar de máquinas de assistência, o cliente entrará no dispositivo HoloLens 2 usando credenciais fornecidas pela Companhia Contoso e utilizará o Remote Assist para contactar os especialistas da Empresa Contoso.

Saiba mais sobre o Remote Assist [aqui.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Requisitos para este Cenário

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Gestor de Dispositivos Móveis - como [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Licença de Assistência Remota
    1. [Comprar Assistência Remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Assistência remota de julgamento](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Preocupações Comuns

- [Como garantir que os clientes externos não têm a capacidade de comunicar uns com os outros](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Como garantir que os clientes não têm acesso aos recursos da empresa](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Como restringir apps](#how-to-restrict-apps)
- [Como gerir senhas](#how-to-manage-passwords)
- [Como garantir que os clientes não têm acesso ao histórico de chat](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Como garantir que os clientes externos não têm a capacidade de comunicar uns com os outros

Uma vez que as chamadas De Assistência Remota HoloLens para HoloLens não são suportadas, os clientes são capazes de procurar, mas são incapazes de comunicar uns com os outros. Para restringir ainda mais quem os clientes podem procurar e ligar,  [as barreiras de informação](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) podem restringir com quem um cliente pode comunicar. Outra opção a considerar é a utilização de [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Uma vez que o sinal único está ativado, é importante desativar o navegador utilizando o [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Se um cliente externo abrir o navegador e utilizar a versão web do Teams, o cliente terá acesso ao histórico de chamadas/chat.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Como garantir que os clientes não têm acesso aos recursos da empresa

Há duas opções a considerar.

A primeira opção é uma abordagem em várias camadas:

1. Apenas atribua licenças que o utilizador necessita. Se não atribuir OneDrive, Outlook, SharePoint, Yammer, etc. ao utilizador, não terá acesso a esses recursos. As únicas licenças que os utilizadores vão precisar são as licenças de Assistência Remota, Intune e AAD para começar.
1. Bloqueie aplicações (como e-mail) que não quer que os clientes acedam (Ver [Como restringir as aplicações).](#how-to-restrict-apps)
1. NÃO partilhe nomes de utilizador nem senha com clientes. Para iniciar sessão no HoloLens 2, é necessário um e-mail e um PIN numérico.

A segunda opção é criar um inquilino separado que acolhe clientes (ver Imagem 1.1).

**Imagem 1.1**

![Imagem do inquilino de serviço](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Como restringir apps

[Modo quiosque](https://docs.microsoft.com/hololens/hololens-kiosk) e/ou [WDAC (Controlo de Aplicações do Windows Defender)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) são opções para restringir as aplicações.

### <a name="how-to-manage-passwords"></a>Como gerir senhas

1. Remova a expiração da palavra-passe. No entanto, isto aumenta a possibilidade de uma conta ser comprometida. A recomendação da palavra-passe NIST é alterar palavras-passe a cada 30-90 dias.
1. Prolongue a expiração da palavra-passe para os dispositivos HoloLens 2 para ultrapassar os 90 dias.
1. Os dispositivos devem ser devolvidos a Contoso para alterar as palavras-passe. No entanto, isto pode causar problemas se os dispositivos se espera que estejam na fábrica do cliente por mais de 90 dias.  
1. Para dispositivos que são enviados a vários clientes, reinicie as palavras-passe antes de enviar o dispositivo para os clientes.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Como garantir que os clientes não têm acesso ao histórico de chat

Remote Assist limpa o histórico de conversas após cada sessão. No entanto, o histórico de conversas estará disponível para o utilizador da Microsoft Teams.

> [!NOTE]
> Uma vez que o sinal único está ativado, é importante desativar o navegador utilizando o [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Se um cliente externo abrir o navegador e utilizar a versão web do Teams, o cliente terá acesso ao histórico de chamadas/chat.

## <a name="general-deployment-recommendations-and-instructions"></a>Recomendações e instruções gerais de implantação

Recomendamos o seguinte para hololens 2 Etapas de implantação:

1. Utilize o [mais recente lançamento hololens OS](https://aka.ms/hololens2download) como base.
1. Atribuir licenças baseadas no utilizador ou baseadas em dispositivos:
    1. As licenças baseadas no utilizador e no dispositivo seguem ambas as seguintes etapas:
        1. [Crie um grupo em AAD e adicione membros](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) para utilizadores HoloLens/RA.
        1. [Atribua licenças baseadas em dispositivos ou baseadas no utilizador](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) a este grupo.
        1. (Opcional) Podes direcionar grupos para políticas de MDM.

1. Os dispositivos devem ser AAD unidos ao seu inquilino, [Auto Inscrito,](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)e configurados através [do Piloto Automático](https://docs.microsoft.com/hololens/hololens2-autopilot).
    1. Por favor, note que o primeiro utilizador do dispositivo será o proprietário do dispositivo.
    1. Por favor, note que se o dispositivo for a aderido a AAD, o utilizador que executou a junta é o proprietário do dispositivo.
    1. Para mais informações, consulte [o Proprietário do Dispositivo.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)
1. [O inquilino tranca](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) o dispositivo para que só possa juntar-se ao seu inquilino.
    1. **Link adicional:** [Inquilino trava CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).
1. Configure o quiosque utilizando o acesso global atribuído a [aqui.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)
1. Recomendamos desativar as capacidades seguintes (opcionais):
    1. Capacidade de colocar o dispositivo no modo de desenvolvimento [aqui](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).
    1. Capacidade de ligar os HoloLens a um PC para copiar data [desative USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Se não pretender desativar USB mas quiser a capacidade de aplicar um pacote de provisionamento no dispositivo utilizando USB, siga as instruções [**aqui**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)enumeradas .

1. Utilize [o WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) para permitir ou bloquear aplicações no dispositivo HoloLens 2.
1. Atualize o Remote Assist para a versão mais recente como parte da configuração. Existem duas opções para o fazer:
    1. Isto pode ser feito indo para a Microsoft **Store -- > Remote Assist --> e App de atualização**.
    1. [O ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - que permite atualizações automáticas de aplicações - é ativado por padrão. Mantenha o dispositivo ligado para receber atualizações.
1. [Desative todas as páginas de definições,](https://docs.microsoft.com/hololens/settings-uri-list) exceto as definições de rede para permitir que os utilizadores se conectem às redes de hóspedes em sites de clientes.
1. [Gerir atualizações hololens](https://docs.microsoft.com/hololens/hololens-updates)
    1. Opção de [controlar as atualizações do SO](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) ou permitir fluir livremente.
1. [Restrições comuns do dispositivo](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).
