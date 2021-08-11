---
title: HoloLens 2 Compliance e RGPD
description: Documentação do RGPD
keywords: HoloLens, RGPD, privacidade, PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3365e69c8408b75a5d4e1177df938f435dec05d9dc181c698d7991159645d15a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660146"
---
# <a name="hololens-2-privacy-statement"></a>Declaração de Privacidade HoloLens 2

Um dos elementos fundamentais do RGPD é a "proteção de dados por conceção". Este conceito aplica-se especialmente a dispositivos móveis, como o HoloLens 2, devido à sua portabilidade, conexões ilimitadas à Internet e canais de comunicação abertos. Consequentemente, a [segurança](/hololens/security-architecture) do HoloLens 2 foi redesenhada para fornecer proteção avançada e inovadora de segurança e privacidade, de ponta a ponta, incorporando a abordagem da Microsoft à privacidade e aos regulamentos do [RGPD.](https://privacy.microsoft.com/)

 >[!NOTE]
> Este documento não se aplica a HoloLens (1ª geração).

## <a name="privacy-overview"></a>Visão geral da privacidade

HoloLens 2 é um computador Windows independente, executado Windows Holographic, que executa apps e soluções num ambiente de realidade mista imersiva. Pode ser usado como um dispositivo offline seguro ou implementado como um [dispositivo gerido](/mem/intune/fundamentals/windows-holographic-for-business) dentro da sua organização. Consulte os seguintes links para entender como o HoloLens 2 e a Microsoft utiliza e protege os seus dados:

1. [A Microsoft Privacy Statement - HoloLens](https://privacy.microsoft.com/privacystatement) - expanda a secção Enterprise e **developer** no menu de navegação à esquerda e selecione software **e eletrodomésticos enterprise e developer**. Vá para a secção **HoloLens.**
2. [Windows 10 e os seus serviços online](https://privacy.microsoft.com/windows10privacy)
3. [Guia de Conformidade Windows 10 & Privacidade](/windows/privacy/windows-10-and-privacy-compliance)
4. [Dados pessoais e privacidade no Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Segurança de Rede
Seguindo os HoloLens 2 [Cenários De Implantação Comum,](/hololens/common-scenarios)os seus dados serão protegidos pela [conformidade de classe mundial da Azure,](/azure/compliance/) juntamente com a integração de normas legais/regulamentares. Se é novo no AZure AD e Dynamics 365 Remote Assist, consulte a [lista de verificação de prontidão de prestação de contas Azure e Dynamics 365 para o RGPD](/compliance/regulatory/gdpr-arc-azure-dynamics).

Além disso, Windows Defender Firewall fornece funcionalidades críticas para garantir a conectividade do dispositivo. Com HoloLens 2, a firewall está sempre ativada e não há formas de desativá-la programáticamente ou através da UI. Quando o HoloLens 2 é implementado como um dispositivo gerido usando [o Intune,](/mem/intune/protect/device-compliance-get-started)mais funcionalidade de conformidade está disponível com a integração para [Endpoint com Microsoft Intune](/mem/intune/protect/advanced-threat-protection) como solução de Defesa de Ameaças Móveis.

Saiba mais sobre a [segurança e arquitetura](/hololens/security-architecture)HoloLens 2.

## <a name="os-security"></a>Segurança oss
As atualizações são feitas automaticamente (por padrão) pelo que o seu HoloLens 2 está sempre atualizado com a mais recente versão de Windows aplicações Holográficas e quaisquer aplicações instaladas. Veja o seguinte para entender mais sobre como o nosso sistema operativo é projetado de forma segura:

1. [Separação do Estado e isolamento](/hololens/security-state-separation-isolation)
1. [Sistema operativo sem administração](/hololens/security-adminless-os)
1. [Limitação da utilização de palavras-passe](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Segurança Física
HoloLens 2 tem memória flash que está protegida pela [encriptação BitLocker](/hololens/security-encryption-data-protection). O seu dispositivo, e os seus dados locais, podem ser intermitentes offline utilizando [o Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) ou limpo remotamente através do MDM se este tiver sido implementado como um dispositivo gerido.

## <a name="data-protection"></a>Proteção de Dados
Windows atualizações são executadas automaticamente (por padrão) e [a integração do Azure](/hololens/security-encryption-data-protection#Azure-integration) protege os dados que viajam entre si e a nuvem.

Ao implementar HoloLens 2 para clientes externos, [a Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) garante que os dados e recursos sensíveis da empresa são separados e seguros.

A partilha de dados de diagnóstico com a Microsoft pode ser configurada manualmente pelo MDM ou pelo utilizador durante o OOBE. Existem duas opções: dados de diagnóstico opcionais e dados de diagnóstico necessários. Se a sua definição de diagnóstico original tiver de ser alterada posteriormente para efeitos de resolução de problemas, pode ser alterada pelo utilizador em **Definições -> > De diagnóstico & Feedback** ou o Administrador de TI (MDM) se for um dispositivo gerido. Veja mais sobre [Diagnósticos, feedback e privacidade em Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> Os registos de diagnóstico do dispositivo contêm informações pessoalmente identificáveis (PII), tais como sobre que processos ou aplicações o utilizador inicia durante as operações típicas. Quando vários utilizadores partilham um dispositivo HoloLens (por exemplo, os utilizadores iniciam sessão no mesmo dispositivo utilizando diferentes contas de Microsoft Azure Ative Directory (Azure AD) os registos de diagnóstico podem conter informações pii que se aplicam a vários utilizadores.

Existem [vários métodos de recolha e políticas](/hololens/hololens-diagnostic-logs) de retenção de dados para recolha de dados de diagnóstico do HoloLens 2.  Para obter mais informações sobre como a Microsoft recolhe e utiliza dados de diagnóstico, consulte [a Microsoft Privacy Statement - Diagnostics](https://privacy.microsoft.com/privacystatement) - expanda **Windows** no menu de navegação esquerda e selecione **Diagnósticos**. Vá à secção **de Diagnóstico.**
