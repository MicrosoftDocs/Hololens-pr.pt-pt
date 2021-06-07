---
title: Configure CSPs e visão geral da gestão de dispositivos
description: Saiba como configurar CSPs, política e gestão de dispositivos usando a Gestão de Dispositivos Móveis e pacotes de provisionamento.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378629"
---
# <a name="configure-csps-and-device-management-overview"></a>Configure CSPs e visão geral da gestão de dispositivos

Os administradores de TI podem definir e implementar definições de política no HoloLens 2. Que configurações utilizas diferirá com base no cenário de implementação, e os dispositivos corporativos oferecerão à TI a maior gama de controlo. No Windows 10, os Fornecedores de Serviços de Configuração (CSP) são uma interface para ler, definir, modificar ou eliminar definições de configuração no dispositivo. Estas definições mapeiam para obter chaves ou ficheiros de registo. Alguns fornecedores de serviços de configuração suportam o formato WAP, alguns suportam o SyncML e alguns suportem ambos.

Para obter mais informações sobre os CSPs de gestão de dispositivos Holográficos do Windows 10, consulte a lista completa de [CSPs suportados em dispositivos HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).
Os administradores de TI também podem gerir a Política CSP em dispositivos, ver a lista completa de [CSPs de política suportados por HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## <a name="configuration-methods"></a>Métodos de configuração

### <a name="configure-with-mdm"></a>Configure com MDM

Os CSPs e Políticas podem ser facilmente geridos em qualquer dispositivo pessoal ou corporativo matriculado num sistema MDM. Uma vez que um dispositivo esteja matriculado na sua solução MDM, poderá gerir esse dispositivo, ou definir dispositivos utilizando configurações do dispositivo. Saiba mais sobre como [gerir os seus dispositivos HoloLens através do MDM.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Configure com pacotes de provisionamento

O HoloLens 2 também suporta a definição de um conjunto limitado de configurações CSP para dispositivos HoloLens 2 através de pacotes de provisionamento personalizados. Os pacotes de provisionamento são normalmente alavancados para dispositivos não geridos por MDM e exigem ser aplicados manualmente a cada dispositivo. Leia informações sobre a construção [de pacotes de provisionamento personalizados para HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).

## <a name="configurations"></a>Configurações

### <a name="common-device-restrictions"></a>Restrições comuns do dispositivo

Algumas restrições ao dispositivo são tão simples e desativam uma funcionalidade ou ligação ao dispositivo. Para saber mais sobre estas leituras sobre [restrições comuns de dispositivos.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Modos de quiosque

Utilize o modo Quiosque para controlar quais identidades têm acesso às quais as aplicações por padrão. Os quiosques podem ser usados para uma única aplicação ou experiência UI de várias aplicações. As configurações do quiosque vão desde uma única aplicação para qualquer pessoa que utilize o dispositivo, até diferentes seleções de apps para diferentes grupos. O modo quiosque não impede que "aplicações permitidas" lançassem outras apps e não se destinava a nunca. Saiba mais [ao ler sobre os modos quiosques e como utilizá-los](hololens-kiosk.md).

### <a name="settings-page-visibility"></a>Definições Visibilidade da página

Use a política de aplicações de Definições para controlar quais identidades têm acesso a definições por padrão. Utilizando esta política, a aplicação Definições pode ser configurada para mostrar apenas as páginas selecionadas ou ocultar todas as páginas selecionadas. [Leia sobre como configurar as páginas disponíveis](settings-uri-list.md).

Atualmente, esta funcionalidade só está disponível nas [construções do Windows Insider.](hololens-insider.md) Certifique-se de que os dispositivos para os seguintes a utilizar estão na construção 19041.1349+.

### <a name="wdac"></a>WDAC

Utilize a configuração WDAC para controlar quais aplicações/processos são permitidos/não autorizados a serem lançados independentemente de o sistema estar ou não em modo quiosque.
[Consulte a nossa visão geral para o WDAC.](windows-defender-application-control-wdac.md)
