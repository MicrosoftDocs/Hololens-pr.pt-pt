---
title: Gerir atualizações de HoloLens
description: Saiba como os seus administradores podem utilizar a gestão de dispositivos móveis para gerir atualizações para HoloLens dispositivos.
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
ms.openlocfilehash: 3afe3d2aecd64c2b4724f4805571cb3c46112875
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190043"
---
# <a name="manage-hololens-updates"></a>Gerir atualizações de HoloLens

HoloLens utiliza Windows Update da mesma forma que outros dispositivos Windows 10. Quando uma atualização está disponível, é automaticamente descarregada e instalada da próxima vez que o seu dispositivo estiver ligado e ligado à internet. Este artigo descreve como gerir atualizações em uma empresa ou outro ambiente gerido. Para obter informações sobre como gerir atualizações para dispositivos HoloLens individuais, consulte [Update HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Gerir atualizações automaticamente

### <a name="managing-updates-by-using-windows-update-for-business"></a>Gerir atualizações utilizando Windows Update for Business

Windows Holographic for Business podem usar [Windows Update para o Negócios](/windows/deployment/update/waas-manage-updates-wufb) para gerir atualizações. Todos os HoloLens 2 dispositivos podem ser utilizados Windows Holographic for Business. Certifique-se de que utilizam Windows Holographic for Business construir 10.0.18362.1042 ou uma construção posterior. Se tiver HoloLens dispositivos (1ª geração), tem de [os atualizar para Windows Holographic for Business](hololens1-upgrade-enterprise.md) para gerir as suas atualizações.

Windows A atualização para o Negócio liga HoloLens dispositivos diretamente ao serviço Windows Update. Ao utilizar Windows Update for Business, é possível controlar vários aspetos do processo de atualização que é, quais os &mdash; dispositivos que obtêm quais atualizações a que horas. Por exemplo, pode lançar atualizações para um subconjunto de dispositivos para testes e, posteriormente, lançar atualizações para os restantes dispositivos. Ou, pode definir diferentes horários de atualização para diferentes tipos de atualizações.

> [!NOTE]  
> Para HoloLens dispositivos, pode gerir automaticamente as atualizações de funcionalidades (lançadas duas vezes por ano) e atualizações de qualidade (lançadas mensalmente ou conforme necessário, incluindo atualizações críticas de segurança). Para obter mais informações sobre os tipos de atualização, consulte [tipos de atualizações geridos por Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Pode configurar Windows Atualização para definições de Negócio para HoloLens utilizando políticas numa solução de Gestão de Dispositivos Móveis (MDM), como Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Gerir Windows atualização para negócios utilizando Microsoft Intune

Para uma discussão detalhada sobre como usar o Intune para configurar Windows Update for Business, consulte [Gerir Windows 10 atualizações de software no Intune](/intune/protect/windows-update-for-business-configure). Para obter mais informações sobre a funcionalidade específica do Intune que HoloLens suporta, consulte [as funções de gestão de atualização intune que HoloLens suporta.](#intune-update-management-functions-that-hololens-supports)

> [!IMPORTANT]  
> A Intune fornece dois tipos de política para gerir atualizações: *Windows 10 anel de atualização* e *Windows 10 atualização de funcionalidades*. O tipo de política de atualização de funcionalidades Windows 10 está em pré-visualização pública neste momento e não é suportado para HoloLens.
>  
> Pode utilizar Windows 10 políticas de toque de atualização para gerir HoloLens 2 atualizações.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Configure políticas de atualização para HoloLens 2 ou HoloLens (1ª geração)

Esta secção descreve as políticas que pode utilizar para gerir atualizações para HoloLens 2 ou HoloLens (1ª geração). Para obter mais informações sobre a funcionalidade que está disponível para HoloLens 2, consulte [Plano e configurar os lançamentos de atualizações para HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

[Política CSP - Atualização](/windows/client-management/mdm/policy-csp-update) define as políticas que configuram Windows Atualização para Negócios.

> [!NOTE]  
> Para obter uma lista de prestadores de serviços de configuração de políticas específicas (CSPs) que são suportados por edições específicas de HoloLens, consulte [os CSPs de política suportados por dispositivos HoloLens](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### <a name="configure-automatic-checks-for-updates"></a>Configurar controlos automáticos para atualizações

Pode utilizar a política **Update/AllowAutoUpdate** para gerir o comportamento de atualização automática, como digitalização, descarregamento e instalação de atualizações. Para obter mais informações sobre as definições disponíveis para esta política, consulte [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> Em Microsoft Intune, pode utilizar **o Comportamento de Atualização Automática** para alterar esta política. Para obter mais informações, consulte [Gerir Windows 10 atualizações de software no Intune](/intune/windows-update-for-business-configure).

#### <a name="configure-an-update-schedule"></a>Configurar um calendário de atualização

Para configurar como e quando as atualizações são aplicadas, utilize as seguintes políticas:

- [Atualização/DatadasInto](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Valores: **0**-**7** (0 = todos os dias, 1 = Domingo, 7 = Sábado)
  - Valor predefinido: **0** (todos os dias)
- [Atualização/Hora de Instalação Programada](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Valores: 0-23 (0 = meia-noite, 23 = 23 pm)
  - Valor predefinido: 3 am

#### <a name="configure-active-hours"></a>Configure horas ativas
Começando [por Windows Holographic, a versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) um Administrador DE TI pode especificar a gama de horas ativas para HoloLens 2 dispositivos.

As horas ativas identificam o período de tempo em que espera que o dispositivo esteja a ser utilizado. O recomeça automático após a atualização ocorrer fora das horas ativas. O intervalo especificado será contado a partir da hora de início das horas ativas. Pode utilizar o MDM, conforme descrito na [configuração de horas ativas com MDM](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). O MDM utiliza as definições Update/ActiveHoursStart e Update/ActiveHoursEnd e Update/ActiveHoursMaxRange no CSP de política para configurar horas ativas.

-   [Atualização/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) - Este valor define o tempo de fim. Há um máximo de 12 horas desde a hora de início.
    -   Os valores suportados são 0-23, onde 0 é 12:00, 1 é 1 am, etc.
    -   O padrão é de 17 (17:00).
-   [Atualização/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - Este valor define o número máximo de horas ativas a partir da hora de início.
    -   Os valores suportados são 8-18.
    -   O valor predefinido é de 18 (horas).
-   [Atualização/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - Este valor define a hora de início. Há um máximo de 12 horas a partir do fim do tempo.
    -   Os valores suportados são 0-23, onde 0 é 12:00, 1 é 1 am, etc.
    -   O valor predefinido é de 8 (8 da manhã).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Para dispositivos que funcionam Windows 10, versão 1607 apenas

Pode utilizar as seguintes políticas de atualização para configurar dispositivos para obter atualizações a partir do serviço de atualização do servidor Windows (WSUS), em vez de a partir de Windows Update:

- [Atualização/Permitir Serviço de Acesso](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Atualização/Exigir Aprovação de Aplicação](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Atualização/ActualizaçãoServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Plano e configurar atualização para HoloLens 2

HoloLens 2 suporta mais funcionalidades de automatização de atualização do que HoloLens (1ª geração) suporta. Isto é especialmente verdade se utilizar Microsoft Intune para gerir Windows atualização para políticas empresariais. Estas funcionalidades facilitam o plano e implementam lançamentos de atualizações em toda a sua organização.

#### <a name="plan-the-update-strategy"></a>Planeie a estratégia de atualização

Windows As atualizações para negócios suportam políticas de diferimento. Depois de a Microsoft lançar uma atualização, pode utilizar uma política de diferimento para definir quanto tempo esperar até instalar essa atualização nos dispositivos. Ao associar subconjuntos dos seus dispositivos (também conhecidos como anéis de *atualização)* com diferentes políticas de diferimento, pode coordenar uma estratégia de lançamento de atualização para a sua organização.

Por exemplo, considere uma organização que tem 1.000 dispositivos, e tem que atualizar os dispositivos em cinco ondas. A organização pode criar cinco anéis de atualização, como mostrado na tabela seguinte.

|Group |Número de dispositivos |Diferimento (dias) |
| ---| :---: | :---: |
|Grp 1 (pessoal de TI) |5 |0 |
|Grp 2 (primeiros adotantes) |50 |60 |
|Grp 3 (principal 1) |250 |120 |
|Grp 4 (principal 2) |300 |150 |
|Grp 5 (principal 3) |395 |180 |

Eis como o lançamento progride ao longo do tempo para toda a organização.

![Linha do tempo para implementar atualizações.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Configure uma política de adiamento de atualização

Uma política de diferimento especifica o número de dias entre a data em que uma atualização fica disponível e a data em que a atualização é oferecida a um dispositivo.

Pode configurar diferentes diferimentos para atualizações de funcionalidades e atualizações de qualidade. A tabela que se segue enumera as políticas específicas a utilizar para cada tipo e o máximo de diferimento para cada um.

|Categoria |Política |Diferimento máximo |
| --- | --- | --- |
|Atualizações de funcionalidades |DiferirFeatureUpdatesPeriodInDays |365 dias |
|Atualizações de qualidade |Diferimento DeQualityUpdatesPeriodInDays |30 dias |

#### <a name="pause-updates-via-device"></a>Pausa atualizações via dispositivo

Se um utilizador não tiver acesso ao MDM, pode fazer uma pausa individualmente durante 35 dias manualmente num dispositivo HoloLens 2 na construção [Windows Holographic, versão 2004](hololens-release-notes.md#windows-holographic-version-2004) ou posterior. Os utilizadores podem chegar a esta definição navegando para **Definições > Atualização & Opções avançadas > de segurança** deslocam-se para **atualizações de pausa** e selecionam a data até à qual irão interromper as atualizações. Uma vez que um utilizador atingiu o limite de pausa, o dispositivo terá de obter novas atualizações antes de poder parar novamente. 

Começando [por Windows Holographic, versão 20H2,](hololens-release-notes.md#windows-holographic-version-20h2)esta função de atualizações de pausa pode ser gerida para HoloLens 2 dispositivos. 
- [Atualização/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (padrão) - Ativado
    - 1 - Deficientes

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Intune atualizar funções de gestão que HoloLens suporta

Pode utilizar as seguintes funções de gestão de atualização do Intune para gerir atualizações para HoloLens.

- **Criar** e **Atribuir**: Estas funções adicionam um anel de atualização Windows 10 à lista de anéis de atualização. Para obter mais informações, consulte [criar e atribuir anéis de atualização](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Pausa**: Se encontrar um problema quando implementar uma atualização de funcionalidade ou qualidade, pode interromper a atualização durante 35 dias (a partir de uma data especificada). Esta pausa impede que outros dispositivos instalem a atualização até que resolva ou atenue o problema. Se interromper uma atualização de funcionalidade, ainda são oferecidas atualizações de qualidade aos dispositivos para garantir que se mantêm seguras. Quando um tipo de atualização é pausado, o painel de visão geral para o anel mostra quantos dias restam antes que o tipo de atualização retome. Após o tempo especificado ter passado, a pausa expira automaticamente e o processo de atualização recomeça.

  Enquanto o anel de atualização estiver parado, pode selecionar qualquer uma das seguintes opções:

  - **Prorrogar**: Prolongar o período de pausa por um tipo de atualização durante 35 dias.
  - **Currículo**: Restaurar as atualizações para o anel para o funcionamento ativo. Pode fazer uma pausa no anel de atualização novamente, se for necessário.

  > [!NOTE]  
  > A operação **Desinstalar** para os anéis de atualização não é suportada para HoloLens 2 dispositivos.

### <a name="delivery-optimization-preview"></a>Pré-visualização da otimização de entregas

[Windows Holographic, a versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) permitiu uma pré-visualização antecipada para as definições de otimização de entrega para reduzir o consumo de largura de banda para downloads de vários dispositivos HoloLens. Uma descrição mais completa desta funcionalidade juntamente com a configuração recomendada da rede está disponível aqui: [Otimização de Entrega para atualizações Windows 10](/windows/deployment/update/waas-delivery-optimization).

As seguintes definições são ativadas como parte da superfície de gestão e [podem ser configuradas a partir de Intune](/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Algumas ressalvas sobre esta oferta de pré-visualização:

- HoloLens suporte é limitado apenas nesta pré-visualização às atualizações do SO.
- Windows Holographic for Business suporta apenas os modos de descarregamento HTTP e downloads a partir de um ponto final da [Cache Conectada microsoft](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); os modos de descarregamento peer-to-peer e as atribuições de grupo não são suportados para dispositivos HoloLens neste momento.
- HoloLens não suporta a otimização de implementação ou entrega para Windows Server Update Services pontos finais.
- A resolução de problemas requer diagnósticos no servidor Cache Conectado ou a recolha de vestígios de HoloLens no HoloLens através **de Definições**  >  **Atualização &**  >   **resolução de problemas de** segurança  >   **Windows Update**.

## <a name="manually-check-for-updates"></a>Verifique manualmente se há atualizações

Embora HoloLens verifica periodicamente as atualizações do sistema, pode haver circunstâncias em que pretende verificar manualmente.

Para verificar manualmente se há atualizações, consulte **Definições**  >  **Atualização & Verificação de Segurança** para obter  >  **atualizações**. Se a aplicação Definições indicar que o seu dispositivo está atualizado, tem todas as atualizações que estão atualmente disponíveis.

## <a name="manually-roll-back-an-update"></a>Reverta manualmente uma atualização

Em alguns casos, é melhor voltar a uma versão anterior do software HoloLens. O processo para o fazer depende se está a utilizar HoloLens 2 ou HoloLens (1ª geração).

### <a name="revert-to-a-previous-version-hololens-2"></a>Reverter para uma versão anterior (HoloLens 2)

Pode reverter as atualizações e voltar a uma versão anterior do HoloLens 2, utilizando o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) para redefinir o seu HoloLens para a versão anterior.

> [!NOTE]
> Reverter para uma versão anterior elimina os seus ficheiros e configurações pessoais.

Para reverter para uma versão anterior de HoloLens 2, siga estes passos:

1. Certifique-se de que não tem telefones ou Windows dispositivos ligados ao computador.
1. No seu computador, descarregue o Companheiro de [Recuperação Avançada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) do Microsoft Store.
1. Descarregue o [mais recente lançamento HoloLens 2](https://aka.ms/hololens2download).
1. Depois de terminar estes downloads, abra **o Explorador** de  >  **Ficheiros Downloads,** clique com o botão direito na pasta comprimida (.zip) que acabou de descarregar e, em seguida, selecione **Extrair todo** o  >  **Extrato** para expandir o ficheiro.
1. Utilize um cabo USB-A a USB-C para ligar o seu HoloLens dispositivo ao computador. Mesmo que tenha usado outros cabos para ligar o seu HoloLens, este tipo de cabo funciona melhor.
1. O Avançado Recovery Companion deteta automaticamente o seu dispositivo HoloLens. Selecione o **azulejo Microsoft HoloLens.**
1. No ecrã seguinte, selecione Manual de **encomendas** e, em seguida, abra a pasta que expandiu anteriormente.
1. Selecione o ficheiro de instalação (.ffu).
1. **Selecione Instalar o software** e, em seguida, seguir as instruções.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Reverter para uma versão anterior (HoloLens (1ª gen))

Pode reverter as atualizações e voltar a uma versão anterior de HoloLens (1ª gen) utilizando a [Ferramenta de Recuperação de Dispositivos Windows (WDRT)](https://support.microsoft.com/help/12379) para redefinir o seu HoloLens para a versão anterior.

> [!NOTE]
> Reverter para uma versão HoloLens anterior elimina os seus ficheiros e configurações pessoais.

Para reverter para uma versão anterior de HoloLens (1ª geração), siga estes passos:

1. Certifique-se de que não tem telefones ou dispositivos Windows ligados ao computador.
1. No seu computador, descarregue a [Ferramenta de Recuperação de Dispositivos Windows (WDRT)](https://support.microsoft.com/help/12379).
1. Descarregue o [pacote de recuperação da Atualização de Aniversário HoloLens](https://aka.ms/hololensrecovery).
1. Depois de terminarem as transferências, abra o **Explorador** de  >  **Ficheiros Downloads,** clique com o botão direito na pasta comprimida (.zip) que acabou de descarregar e, em seguida, selecione **Extrair todo** o  >  **Extrato** para expandir o ficheiro.
1. Utilize o cabo micro-USB fornecido juntamente com o seu dispositivo HoloLens para ligar o seu dispositivo HoloLens ao computador. Mesmo que tenha usado outros cabos para ligar o seu dispositivo HoloLens, este funciona melhor.
1. O WDRT deteta automaticamente o seu dispositivo HoloLens. Selecione o **azulejo Microsoft HoloLens.**
1. No ecrã seguinte, selecione Manual de **encomendas** e, em seguida, abra a pasta que expandiu anteriormente.
1. Selecione o ficheiro de instalação (.ffu).
1. **Selecione Instalar o software** e, em seguida, seguir as instruções.

**Se o WDRT não detetar o seu dispositivo**

Se o WDRT não detetar o seu dispositivo HoloLens, tente reiniciar o computador. Se isso não funcionar, selecione **O meu dispositivo não foi detetado**, selecione **Microsoft HoloLens** e, em seguida, siga as instruções.

## <a name="related-articles"></a>Artigos relacionados

- [HoloLens 2 notas de lançamento](hololens-release-notes.md)
- [O que é Windows Atualização para Negócios?](/windows/deployment/update/waas-manage-updates-wufb)
- [Atribuir dispositivos a canais de manutenção para atualizações Windows 10](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Gerir atualizações de software do Windows 10 no Intune](/mem/intune/protect/windows-update-for-business-configure)
