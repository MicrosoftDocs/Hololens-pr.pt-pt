---
title: Loja Microsoft para Empresas
description: Aprenda a trabalhar com o Microsoft Store para Empresas para publicar as suas aplicações de realidade mista no seu negócio.
keywords: Microsoft Store para Empresas, msfb, implementação de aplicativos, loja
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924320"
---
# <a name="microsoft-store-for-business"></a>Loja Microsoft para Empresas

O [Microsoft Store para Empresas](/microsoft-store/microsoft-store-for-business-overview) é projetado principalmente para decisores e administradores de TI em empresas ou organizações com uma forma flexível de encontrar, adquirir, gerir e distribuir aplicações gratuitas e pagas em mercados selecionados para Windows 10 dispositivos em volume. 

Você pode gerir Microsoft Store aplicações e aplicações de linha de negócio privadas em um inventário, e atribuir e reutilizar licenças conforme necessário. Também pode escolher o melhor método de distribuição para a sua organização: atribuir diretamente aplicações a indivíduos e equipas, publicar aplicações para páginas privadas em Microsoft Store ou conectar-se com soluções de gestão para mais opções.

Quando Microsoft Store para Empresas é utilizado por um utilizador final, lançarão a aplicação Microsoft Store. Uma vez lançado o utilizador poderá selecionar o separador com o nome das suas organizações, e depois serão apresentadas com as aplicações disponíveis ou aquele dispositivo.

> [!Note]
> Microsoft Store para Empresas não descarrega automaticamente (push) aplicações para dispositivos. No entanto, as aplicações do Microsoft Store para Empresas podem ser associadas ao servidor de gestão de dispositivos (MDM) para direcionar e sincronizar aplicações para dispositivos.

Visite as seguintes páginas para saber mais sobre como usar o Microsoft Store para Empresas:

* [Níveis de permissões utilizados para instalar aplicações](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [Como adicionar uma app à sua Loja para Negócios](/mem/intune/apps/store-apps-windows)
* [Como atribuir aplicativos a grupos de colaboradores](/mem/intune/apps/windows-store-for-business)

Para associar o seu Microsoft Store para Empresas, visite [a Associate your Microsoft Store para Empresas com a Intune](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune).

> [!Tip]
> Saiba mais sobre [a distribuição de aplicações offline](/microsoft-store/distribute-offline-apps) ao utilizar apps como Advanced Recovery Companion (ARC) e Windows Configuration Designer (WCD).

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Utilize apenas aplicativos de loja privada para Microsoft Store

- Introduzida em [Windows Holographic, versão 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

A política RequerPrivateStoreOnly foi ativada para HoloLens. Esta política permite que a aplicação Microsoft Store seja configurada apenas para mostrar a loja privada configurada para a sua organização. Limitando o acesso apenas às aplicações que disponibilizou.

Saiba mais sobre [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>Smart Retry para atualizações de aplicações

- Introduzida em [Windows Holographic, versão 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

Agora ativada para HoloLens é uma nova política que permite aos Administradores de TI definir uma data recorrente ou uma data de tempo para reiniciar aplicações cuja atualização falhou devido à aplicação estar em uso permitindo que a atualização seja aplicada. Estes podem ser definidos com base em alguns gatilhos diferentes, tais como uma hora programada ou uma sindução. Para saber mais sobre como utilizar esta política, consulte [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).