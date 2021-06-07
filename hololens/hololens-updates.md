---
title: Gerir atualizações hololens
description: Saiba como os seus administradores podem utilizar a gestão de dispositivos móveis para gerir atualizações para dispositivos HoloLens.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 6c9d1551b2a3348a6ff9962180c2d5552eb100f1
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379897"
---
# <a name="manage-hololens-updates"></a>Gerir atualizações hololens

O HoloLens utiliza o Windows Update da mesma forma que outros dispositivos Windows 10. Quando uma atualização está disponível, é automaticamente descarregada e instalada da próxima vez que o seu dispositivo estiver ligado e ligado à internet. Este artigo descreve como gerir atualizações em uma empresa ou outro ambiente gerido. Para obter informações sobre como gerir atualizações para dispositivos HoloLens individuais, consulte [Update HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Gerir atualizações automaticamente

### <a name="managing-updates-by-using-windows-update-for-business"></a>Gerir atualizações utilizando o Windows Update for Business

O Windows Holographic for Business pode utilizar [o Windows Update para gerir](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) as atualizações. Todos os dispositivos HoloLens 2 podem utilizar o Windows Holographic para Negócios. Certifique-se de que utilizam o Windows Holographic para Business 10.0.18362.1042 ou uma construção posterior. Se tiver dispositivos HoloLens (1º género), tem de [os atualizar para o Windows Holographic for Business](hololens1-upgrade-enterprise.md) para gerir as suas atualizações.

O Windows Update for Business liga os dispositivos HoloLens diretamente ao serviço De atualização do Windows. Ao utilizar o Windows Update for Business, é possível controlar vários aspetos do processo de atualização que é, quais os &mdash; dispositivos que obtêm quais as atualizações a que horas. Por exemplo, pode lançar atualizações para um subconjunto de dispositivos para testes e, posteriormente, lançar atualizações para os restantes dispositivos. Ou, pode definir diferentes horários de atualização para diferentes tipos de atualizações.

> [!NOTE]  
> Para dispositivos HoloLens, pode gerir automaticamente as atualizações de funcionalidades (lançadas duas vezes por ano) e atualizações de qualidade (lançadas mensalmente ou conforme necessário, incluindo atualizações críticas de segurança). Para obter mais informações sobre os tipos de atualização, consulte [tipos de atualizações geridos pelo Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Pode configurar o Windows Update para as definições de Negócios para HoloLens utilizando políticas numa solução de Gestão de Dispositivos Móveis (MDM), como o Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Gerir o Windows Update for Business utilizando o Microsoft Intune

Para uma discussão detalhada sobre como usar o Intune para configurar o Windows Update for Business, consulte [gerir as atualizações de software do Windows 10 no Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure). Para obter mais informações sobre a funcionalidade específica intune que o HoloLens suporta, consulte [as funções de gestão de atualização intune que a HoloLens suporta.](#intune-update-management-functions-that-hololens-supports)

> [!IMPORTANT]  
> O Intune fornece dois tipos de políticas para gerir atualizações: *o anel de atualização do Windows 10* e *a atualização de funcionalidades do Windows 10*. O tipo de atualização de funcionalidades do Windows 10 encontra-se em pré-visualização pública neste momento e não é suportado por HoloLens.
>  
> Pode utilizar as políticas de toque de atualização do Windows 10 para gerir as atualizações do HoloLens 2.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Configure políticas de atualização para HoloLens 2 ou HoloLens (1ª geração)

Esta secção descreve as políticas que pode utilizar para gerir atualizações para HoloLens 2 ou HoloLens (1º género). Para obter mais informações sobre a funcionalidade que está disponível para HoloLens 2, consulte [Plano e configurar os lançamentos de atualização para HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

[Política CSP - Atualização](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) define as políticas que configuram a Atualização do Windows para o Negócio.

> [!NOTE]  
> Para obter uma lista de fornecedores específicos de serviços de configuração de políticas (CSPs) que são suportados por edições específicas de HoloLens, consulte [os CSPs de política suportados por dispositivos HoloLens](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### <a name="configure-automatic-checks-for-updates"></a>Configurar controlos automáticos para atualizações

Pode utilizar a política **Update/AllowAutoUpdate** para gerir o comportamento de atualização automática, como digitalização, descarregamento e instalação de atualizações. Para obter mais informações sobre as definições disponíveis para esta política, consulte [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> No Microsoft Intune, pode utilizar **o Comportamento de Atualização Automática** para alterar esta política. Para obter mais informações, consulte [gerir as atualizações de software do Windows 10 no Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

#### <a name="configure-an-update-schedule"></a>Configurar um calendário de atualização

Para configurar como e quando as atualizações são aplicadas, utilize as seguintes políticas:

- [Atualização/DatadasInto](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Valores: **0**-**7** (0 = todos os dias, 1 = Domingo, 7 = Sábado)
  - Valor predefinido: **0** (todos os dias)
- [Atualização/Hora de Instalação Programada](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Valores: 0-23 (0 = meia-noite, 23 = 23 pm)
  - Valor predefinido: 3 PM

#### <a name="configure-active-hours"></a>Configure horas ativas
Começando pelo [Windows Holographic, a versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) um Administrador DE TI pode especificar a gama de horas ativas para dispositivos HoloLens 2.

As horas ativas identificam o período de tempo em que espera que o dispositivo esteja a ser utilizado. O recomeça automático após a atualização ocorrer fora das horas ativas. O intervalo especificado será contado a partir da hora de início das horas ativas. Pode utilizar o MDM, conforme descrito na [configuração de horas ativas com MDM](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). O MDM utiliza as definições Update/ActiveHoursStart e Update/ActiveHoursEnd e Update/ActiveHoursMaxRange no CSP de política para configurar horas ativas.

-   [Atualização/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) - Este valor define o tempo de fim. Há um máximo de 12 horas desde a hora de início.
    -   Os valores suportados são 0-23, onde 0 é 12:00, 1 é 1 am, etc.
    -   O padrão é de 17 (17:00).
-   [Atualização/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - Este valor define o número máximo de horas ativas a partir da hora de início.
    -   Os valores suportados são 8-18.
    -   O valor predefinido é de 18 (horas).
-   [Atualização/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - Este valor define a hora de início. Há um máximo de 12 horas a partir do fim do tempo.
    -   Os valores suportados são 0-23, onde 0 é 12:00, 1 é 1 am, etc.
    -   O valor predefinido é de 8 (8 da manhã).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Para dispositivos que executam o Windows 10, apenas versão 1607

Pode utilizar as seguintes políticas de atualização para configurar dispositivos para obter atualizações a partir do Serviço de Atualização do Windows Server (WSUS), em vez de a partir de Windows Update:

- [Atualização/Permitir Serviço de Acesso](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Atualização/Exigir Aprovação de Aplicação](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Atualização/ActualizaçãoServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Plano e configurar atualização para HoloLens 2

HoloLens 2 suporta mais funcionalidades de automação de atualização do que holoLens (1ª geração) suporta. Isto é especialmente verdade se utilizar o Microsoft Intune para gerir o Windows Update para políticas empresariais. Estas funcionalidades facilitam o plano e implementam lançamentos de atualizações em toda a sua organização.

#### <a name="plan-the-update-strategy"></a>Planeie a estratégia de atualização

As atualizações do Windows para Empresas suportam políticas de diferimento. Depois de a Microsoft lançar uma atualização, pode utilizar uma política de diferimento para definir quanto tempo esperar até instalar essa atualização nos dispositivos. Ao associar subconjuntos dos seus dispositivos (também conhecidos como anéis de *atualização)* com diferentes políticas de diferimento, pode coordenar uma estratégia de lançamento de atualização para a sua organização.

Por exemplo, considere uma organização que tem 1.000 dispositivos, e tem que atualizar os dispositivos em cinco ondas. A organização pode criar cinco anéis de atualização, como mostrado na tabela seguinte.

|Group |Número de dispositivos |Diferimento (dias) |
| ---| :---: | :---: |
|Grp 1 (pessoal de TI) |5 |0 |
|Grp 2 (primeiros adotantes) |50 |60 |
|Grp 3 (principal 1) |250 |120 |
|Grp 4 (principal 2) |300 |150 |
|Grp 5 (principal 3) |395 |180 |

Eis como o lançamento progride ao longo do tempo para toda a organização.

![Linha do tempo para implementar atualizações](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Configure uma política de adiamento de atualização

Uma política de diferimento especifica o número de dias entre a data em que uma atualização fica disponível e a data em que a atualização é oferecida a um dispositivo.

Pode configurar diferentes diferimentos para atualizações de funcionalidades e atualizações de qualidade. A tabela que se segue enumera as políticas específicas a utilizar para cada tipo e o máximo de diferimento para cada um.

|Categoria |Política |Diferimento máximo |
| --- | --- | --- |
|Atualizações de funcionalidades |DiferirFeatureUpdatesPeriodInDays |365 dias |
|Atualizações de qualidade |Diferimento DeQualityUpdatesPeriodInDays |30 dias |

#### <a name="pause-updates-via-device"></a>Pausa atualizações via dispositivo

Se um utilizador não tiver acesso ao MDM, pode fazer uma pausa individualmente durante 35 dias manualmente num dispositivo HoloLens 2 na construção [do Windows Holographic, versão 2004](hololens-release-notes.md#windows-holographic-version-2004) ou posterior. Os utilizadores podem chegar a esta definição navegando para **Definições -> Atualização & Opções avançadas de segurança ->** deslocar-se para **atualizações de pausa** e selecionar a data até à qual irão interromper as atualizações. Uma vez que um utilizador atingiu o limite de pausa, o dispositivo terá de receber novas atualizações, uma vez que pode voltar a fazer uma pausa. 

A partir do [Windows Holographic, versão 20H2,](hololens-release-notes.md#windows-holographic-version-20h2)esta função de atualizações de pausa pode ser gerida para dispositivos HoloLens 2. 
- [Atualização/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (padrão) - Ativado
    - 1 - Deficientes

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Intune atualiza funções de gestão que holoLens suporta

Pode utilizar as seguintes funções de gestão de atualização intune para gerir atualizações para HoloLens.

- **Criar** e **Atribuir**: Estas funções adicionam um anel de atualização do Windows 10 à lista de anéis de atualização. Para obter mais informações, consulte [criar e atribuir anéis de atualização](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Pausa**: Se encontrar um problema quando implementar uma atualização de funcionalidade ou qualidade, pode interromper a atualização durante 35 dias (a partir de uma data especificada). Esta pausa impede que outros dispositivos instalem a atualização até que resolva ou atenue o problema. Se interromper uma atualização de funcionalidade, ainda são oferecidas atualizações de qualidade aos dispositivos para garantir que se mantêm seguras. Quando um tipo de atualização é pausado, o painel de visão geral para o anel mostra quantos dias restam antes que o tipo de atualização retome. Após o tempo especificado ter passado, a pausa expira automaticamente e o processo de atualização recomeça.

  Enquanto o anel de atualização estiver parado, pode selecionar qualquer uma das seguintes opções:

  - **Prorrogar**: Prolongar o período de pausa por um tipo de atualização durante 35 dias.
  - **Currículo**: Restaurar as atualizações para o anel para o funcionamento ativo. Pode fazer uma pausa no anel de atualização novamente, se for necessário.

  > [!NOTE]  
  > A operação **Desinstalar** para os anéis de atualização não é suportada para dispositivos HoloLens 2.

### <a name="delivery-optimization-preview"></a>Pré-visualização da otimização de entregas

[O Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1) permitiu uma pré-visualização antecipada das definições de otimização de entregas para reduzir o consumo de largura de banda para downloads de vários dispositivos HoloLens. Uma descrição mais completa desta funcionalidade juntamente com a configuração recomendada da rede está disponível aqui: [Otimização de entrega para atualizações do Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

As seguintes definições são ativadas como parte da superfície de gestão e [podem ser configuradas a partir de Intune](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Algumas ressalvas sobre esta oferta de pré-visualização:

- O suporte holoLens é limitado apenas nesta pré-visualização às atualizações do SO.
- O Windows Holographic for Business suporta apenas os modos de descarregamento HTTP e downloads a partir de um ponto final da [Cache Conectada microsoft](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); os modos de descarregamento peer-to-peer e as atribuições de grupo não são suportados para dispositivos HoloLens neste momento.
- O HoloLens não suporta a otimização de implementação ou entrega para os pontos finais dos Serviços de Atualização do Windows Server.
- A resolução de problemas requer diagnósticos no servidor Cache Conectado ou a recolha de vestígios de HoloLens em HoloLens através da Atualização de **Definições**  >  **& a**  >   **resolução de problemas de** segurança do Windows  >   **Update**.

## <a name="manually-check-for-updates"></a>Verifique manualmente se há atualizações

Embora holoLens verifique periodicamente as atualizações do sistema, pode haver circunstâncias em que você deseja verificar manualmente.

Para verificar manualmente se há atualizações, consulte a Atualização **de Definições**  >  **& Verificação de Segurança** para obter  >  **atualizações**. Se a aplicação Definições indicar que o seu dispositivo está atualizado, tem todas as atualizações que estão atualmente disponíveis.

## <a name="manually-roll-back-an-update"></a>Reverta manualmente uma atualização

Em alguns casos, é melhor voltar a uma versão anterior do software HoloLens. O processo para o fazer depende se está a utilizar HoloLens 2 ou HoloLens (1º género).

### <a name="revert-to-a-previous-version-hololens-2"></a>Reverter para uma versão anterior (HoloLens 2)

Pode reverter as atualizações e regressar a uma versão anterior do HoloLens 2 utilizando o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) para redefinir os hololens para a versão anterior.

> [!NOTE]
> Reverter para uma versão anterior elimina os seus ficheiros e configurações pessoais.

Para reverter para uma versão anterior de HoloLens 2, siga estes passos:

1. Certifique-se de que não tem telefones ou dispositivos Windows ligados ao computador.
1. No seu computador, descarregue o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.
1. Descarregue o [mais recente lançamento holoLens 2](https://aka.ms/hololens2download).
1. Depois de terminar estes downloads, abra **o Explorador** de  >  **Ficheiros Downloads,** clique com o botão direito na pasta comprimida (.zip) que acabou de descarregar e, em seguida, selecione **Extrair todo** o  >  **Extrato** para expandir o ficheiro.
1. Utilize um cabo USB-A a USB-C para ligar o seu dispositivo HoloLens ao computador. Mesmo que tenha usado outros cabos para ligar os hololens, este tipo de cabo funciona melhor.
1. O Advanced Recovery Companion deteta automaticamente o seu dispositivo HoloLens. Selecione o azulejo **microsoft HoloLens.**
1. No ecrã seguinte, selecione Manual de **encomendas** e, em seguida, abra a pasta que expandiu anteriormente.
1. Selecione o ficheiro de instalação (.ffu).
1. **Selecione Instalar o software** e, em seguida, seguir as instruções.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Reverter para uma versão anterior (HoloLens (1ª gen))

Pode reverter as atualizações e regressar a uma versão anterior do HoloLens (1º género) utilizando a [Ferramenta de Recuperação de Dispositivos do Windows (WDRT)](https://support.microsoft.com/help/12379) para redefinir os HoloLens na versão anterior.

> [!NOTE]
> Reverter para uma versão HoloLens anterior elimina os seus ficheiros e configurações pessoais.

Para reverter para uma versão anterior de HoloLens (1ª geração), siga estes passos:

1. Certifique-se de que não tem telefones ou dispositivos Windows ligados ao computador.
1. No seu computador, descarregue a [Ferramenta de Recuperação de Dispositivos do Windows (WDRT)](https://support.microsoft.com/help/12379).
1. Descarregue o pacote de recuperação da [Atualização de Aniversário holoLens](https://aka.ms/hololensrecovery).
1. Depois de terminarem as transferências, abra o **Explorador** de  >  **Ficheiros Downloads,** clique com o botão direito na pasta comprimida (.zip) que acabou de descarregar e, em seguida, selecione **Extrair todo** o  >  **Extrato** para expandir o ficheiro.
1. Utilize o cabo micro-USB que foi fornecido juntamente com o seu dispositivo HoloLens para ligar o seu dispositivo HoloLens ao seu computador. Mesmo que tenha usado outros cabos para ligar o seu dispositivo HoloLens, este funciona melhor.
1. O WDRT deteta automaticamente o seu dispositivo HoloLens. Selecione o azulejo **microsoft HoloLens.**
1. No ecrã seguinte, selecione Manual de **encomendas** e, em seguida, abra a pasta que expandiu anteriormente.
1. Selecione o ficheiro de instalação (.ffu).
1. **Selecione Instalar o software** e, em seguida, seguir as instruções.

**Se o WDRT não detetar o seu dispositivo**

Se o WDRT não detetar o seu dispositivo HoloLens, tente reiniciar o computador. Se isso não funcionar, selecione **O meu dispositivo não foi detetado**, selecione Microsoft **HoloLens** e, em seguida, siga as instruções.

## <a name="related-articles"></a>Artigos relacionados

- [Notas de lançamento holoLens 2](https://docs.microsoft.com/hololens/hololens-release-notes)
- [O que é a Atualização do Windows para negócios?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Atribuir dispositivos a canais de manutenção para atualizações do Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Gerir atualizações de software do Windows 10 no Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
