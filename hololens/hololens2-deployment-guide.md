---
title: Implementar nuvem conectada HoloLens 2 a clientes externos
description: Guia de implementação para HoloLens 2 para Clientes Externos (com assistência remota como exemplo)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033404"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>Implementar nuvem conectada HoloLens 2 a clientes externos

Este guia é um suplemento para o [Guia de Implementação Ligado à Nuvem.](hololens2-cloud-connected-overview.md) É usado em situações em que a sua organização quer enviar HoloLens 2 dispositivos para as instalações de um cliente externo para uso curto ou longo. O cliente externo entrará no HoloLens 2 dispositivo utilizando credenciais fornecidas pela sua organização e utilizará o [Remote Assist](/dynamics365/mixed-reality/remote-assist/ra-overview) para contactar os seus especialistas. Este guia fornece [recomendações gerais HoloLens 2](#general-deployment-recommendations) que são aplicáveis à maioria dos cenários de implementação de HoloLens 2 externos e [preocupações comuns](#common-external-client-deployment-concerns) que os clientes têm ao implementar assistência remota para uso externo. 

## <a name="prerequisites"></a>Pré-requisitos

A infraestrutura a seguir deve estar em vigor de acordo com o [Guia de Implantação Ligado](hololens2-cloud-connected-overview.md) à Nuvem para implantar o HoloLens 2 externamente.

- Azure AD Junte-se à Inscrição automática do MDM — gerida pelo MDM (Intune)
- Os utilizadores insinuam-se com a sua própria conta corporativa (Azure AD)
    - Os utilizadores individuais ou múltiplos por dispositivo são suportados.

### <a name="remote-assist-licensing-and-requirements"></a>Licenciamento e requisitos de Assistência Remota

- Conta AZURE AD (necessária para a aquisição da subscrição e atribuição de licenças)
- [Subscrição de Assistência Remota](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [Ensaio de Assistência Remota)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

Ver [Mais sobre Assistência Remota](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist utilizador

- Licença de Assistência Remota
- Conectividade da rede

### <a name="microsoft-teams-user"></a>Microsoft Teams utilizador

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Conectividade de rede

## <a name="general-deployment-recommendations"></a>Recomendações gerais de implantação

Recomendamos os seguintes passos para a implantação de HoloLens 2 externos:

1. Utilize o [mais recente HoloLens o sistema operativo como](https://aka.ms/hololens2download) base.
1. Atribuir licenças baseadas no utilizador ou no dispositivo seguindo os passos abaixo:
    1. [Crie um grupo em AAD e adicione membros](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) para utilizadores de HoloLens/RA.
    1. [Atribua licenças baseadas em dispositivos ou baseadas no utilizador](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) a este grupo.
    1. (Opcional) Grupos-alvo para políticas [de gestão de dispositivos móveis (MDM).](hololens-enroll-mdm.md)

1. Junte-se aos dispositivos AAD ao seu inquilino, [inscreva-se automaticamente](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)e configuure-se através [do Autopilot.](/hololens/hololens2-autopilot) Para mais informações, consulte [o proprietário do dispositivo.](/hololens/security-adminless-os#device-owner)
    1. O primeiro utilizador do dispositivo será o proprietário do dispositivo.
    1. Se o dispositivo for aderido a AAD, o utilizador que executou a junta é o proprietário do dispositivo.
    
1. [O inquilino tranca](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) o dispositivo para que só possa ser acompanhado pelo seu inquilino.
    1. Consulte também [o Bloqueio de Inquilino CSP.](/windows/client-management/mdm/tenantlockdown-csp)

1. [Configure o modo quiosque utilizando o acesso global atribuído](/hololens/hololens-global-assigned-access-kiosk).

1. Desativar as seguintes capacidades (opcionais):
    1. Capacidade de colocar o dispositivo no modo de desenvolvimento [aqui](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).
    1. Capacidade de ligar o HoloLens a um PC para copiar data [desative USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Se não quiser desativar USB mas quiser a capacidade de aplicar um pacote de provisionamento ao dispositivo utilizando USB, siga as [instruções sobre como permitir a instalação do pacote de provisionamento](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).

1. Utilize [Windows Defender Controlo de Aplicações (WDAC)](/hololens/windows-defender-application-control-wdac) para permitir ou bloquear aplicações no dispositivo HoloLens 2.
1. Atualize o Remote Assist para a versão mais recente como parte da configuração. Considere as seguintes duas opções:
    1. Vá a Windows **Microsoft Store --> Remote Assist --> e App de Atualização**.
    1. [O ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - que permite atualizações automáticas de aplicações - é ativado por padrão. Mantenha o dispositivo ligado para receber atualizações.
1. [Desative todas as páginas de definições,](/hololens/settings-uri-list) exceto as definições de rede para permitir que os utilizadores se conectem às redes de hóspedes em sites de clientes.
1. [Gerir atualizações de HoloLens](/hololens/hololens-updates)
    1. Opção de [controlar as atualizações do SO](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) ou permitir fluir livremente.
1. Desemote [as restrições comuns do dispositivo](/hololens/hololens-common-device-restrictions).

Agora os seus clientes externos estão prontos para usar o seu HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Preocupações comuns de implantação de clientes externos

- [Garantindo que os clientes não se comunicam uns com os outros](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Garantindo que os clientes não podem aceder aos recursos da empresa](#ensure-that-clients-wont-have-access-to-company-resources)
- [Ocultar ou restringir apps](#hidden-or-restricted-apps)
- [Gerir senhas para os seus clientes](#password-management-for-your-clients) 
- [Garantindo que os clientes não podem aceder ao histórico de chat](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Certifique-se de que os clientes externos não podem comunicar uns com os outros

As HoloLens de Assistência Remota para HoloLens chamadas não são suportadas. Os clientes podem procurar, mas não podem comunicar uns com os outros. [As barreiras de informação em Microsoft 365](/microsoft-365/compliance/information-barriers) podem restringir ainda mais com quem um cliente pode pesquisar e ligar. Outra opção é utilizar [Microsoft Teams pesquisa de diretórios.](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Uma vez que o sinal único está ativado, é importante desativar o navegador utilizando [Windows Defender Controlo de Aplicações (WDAC)](/hololens/windows-defender-application-control-wdac). Se um cliente externo abrir o navegador e utilizar a versão web do Teams, o cliente terá acesso ao seu histórico de chat.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Garantir que os clientes não terão acesso aos recursos da empresa

Há duas opções a considerar.

A primeira opção é uma abordagem em várias camadas:

1. Apenas atribua licenças que o utilizador necessita. Se não atribuir OneDrive, Outlook, SharePoint, Yammer, etc., o utilizador não terá acesso a esses recursos. As únicas licenças que os utilizadores vão precisar são as licenças de Assistência Remota, Intune e AAD para começar.
1. Bloqueie aplicações (como e-mail) que não quer que os clientes acedam (Ver [Apps são ocultas ou restritas).](#apps are hidden or restricted)
1. Não partilhe nomes de utilizadores nem palavra-passe com os clientes. Para iniciar sessão no HoloLens 2, é necessário um e-mail e um PIN numérico.

A segunda opção é criar um inquilino separado que acolhe clientes (ver Imagem 1.1).

**Imagem 1.1**

![Imagem do Inquilino de Serviço.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Aplicativos ocultos ou restritos

[Modo quiosque](/hololens/hololens-kiosk) e/ou [Windows Defender Controlo de Aplicações (WDAC)](/hololens/windows-efender-application-control-wdac) são opções para ocultar e/ou restringir aplicações.

### <a name="password-management-for-your-clients"></a>Gestão de passwords para os seus clientes

1. Remova a expiração da palavra-passe. No entanto, esta opção pode aumentar a possibilidade de uma conta ser comprometida. A recomendação da palavra-passe NIST é alterar palavras-passe a cada 30-90 dias.
1. Prolongue a expiração da palavra-passe para HoloLens 2 dispositivos superiores a 90 dias.
1. Os dispositivos devem ser devolvidos à sua organização para alterar as palavras-passe. No entanto, esta opção pode causar problemas se se espera que os dispositivos estejam na fábrica do cliente durante mais de 90 dias.  
1. Para dispositivos que são enviados a vários clientes, reinicie as palavras-passe antes de enviar o dispositivo para os clientes.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Certifique-se de que os clientes não terão acesso ao histórico de chat

Remote Assist limpa o histórico de conversas após cada sessão. No entanto, o histórico de chat estará disponível para utilizadores Microsoft Teams.

> [!NOTE]
> Uma vez que o sinal único está ativado, é importante desativar o navegador utilizando [Windows Defender Controlo de Aplicações (WDAC)](/hololens/windows-defender-application-control-wdac).  Se um cliente externo abrir o navegador e utilizar a versão web do Teams, o cliente terá acesso ao histórico de chamadas/chat.
