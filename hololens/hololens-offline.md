---
title: Gerir pontos finais de ligação para HoloLens
description: Aprenda a configurar uma HoloLens sobre uma rede Wi-Fi enquanto gere e configura os pontos finais de ligação.
keywords: hololens, offline, OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f2d9faafac2f84b727b1e10be83d4d1b53a707b4
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427263"
---
# <a name="manage-connection-endpoints-for-hololens"></a>Gerir pontos finais de ligação para HoloLens

Alguns HoloLens componentes, apps e serviços relacionados transferem dados para os pontos finais da rede microsoft. Este artigo lista diferentes pontos finais e URLs que precisam de ser permitidos na sua configuração de rede (por exemplo, proxy ou firewall) para que esses componentes estejam funcionais.    

## <a name="near-offline-setup"></a>Configuração quase offline

HoloLens suporta um conjunto limitado de experiências offline para clientes que têm restrições ao ambiente de rede. No entanto, HoloLens precisa de ligação à rede para passar pela configuração inicial do dispositivo e devem ser ativados os seguintes URLs:

| Objetivo | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| Pino AAD | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| Pino MSA | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>Configuração do ponto final

Além da lista acima, para tirar o máximo partido da funcionalidade HoloLens, os seguintes pontos finais precisam de ser ativados na configuração da sua rede.


| Objetivo | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Multi-Factor Authentication do Azure AD                | https://secure.aadcdn.microsoftonline-p.com                         |
| Configurações Intune e MDM                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| Certificados                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana e Pesquisa                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| Autenticação do dispositivo                               | login.live.com*                                                     |
| Metadados de dispositivo                                     | dmd.metaservices.microsoft.com                                      |
| Localização                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| Dados de Diagnóstico                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com*                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| Licenciamento                                           | licensing.mp.microsoft.com                                          |
| Conta Microsoft                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Serviço de redirecionamento de ligação para a frente da Microsoft (FWLink) | go.microsoft.com                                                    |
| Loja Microsoft                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | .md.mp.microsoft.com                                                |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| Indicador de Estado de Ligação à Rede (NCSI)          | www.msftconnecttest.com*                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.aria                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| App fotos                                          | evoke-windowsservices-tas.msedge.net                                |
| Definições                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| Destaque do Windows                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>Referências

> [!NOTE]
> Se estiver a implementar o D365 Remote Assist, terá de ativar os pontos finais listados para SharePoint Online e OneDrive para Empresas nos [intervalos de OFFICE 365 URLs e endereços IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- [Configurar dados de diagnóstico Windows na sua organização](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Gerir pontos finais de ligação para Windows 10 Enterprise, versão 1903](/windows/privacy/manage-windows-1903-endpoints)
- [Gerir as ligações desde Windows 10 componentes do sistema operativo até à serviços Microsoft](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Gerir ligações desde Windows 10 componentes do sistema operativo até serviços Microsoft utilizando Microsoft Intune Servidor MDM](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Largura de banda e requisitos de configuração de rede do Intune](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Pontos finais da rede para Microsoft Intune](/intune/fundamentals/intune-endpoints)
- [Intervalos de endereços IP e URLs do Office 365](/office365/enterprise/urls-and-ip-address-ranges)
- [Pré-requisitos do Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>limitações HoloLens

Após a configuração do seu HoloLens, pode usá-lo sem uma ligação Wi-Fi, mas as aplicações que utilizam ligações à Internet terão capacidades limitadas quando utilizar HoloLens offline.
