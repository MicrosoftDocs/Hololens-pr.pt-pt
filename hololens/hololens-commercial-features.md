---
title: Características comerciais
description: Conheça as funcionalidades da Microsoft HoloLens Commercial Suite que facilitam a gestão de dispositivos HoloLens por parte das empresas.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, comerciais, recursos, mdm, gestão de dispositivos móveis, modo quiosque
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379833"
---
# <a name="commercial-features"></a>Características comerciais

O HoloLens inclui funcionalidades que facilitam a gestão de dispositivos HoloLens por parte das empresas.

Todos os dispositivos HoloLens 2 têm funcionalidades comerciais disponíveis.

A HoloLens (1ª gen) veio com duas opções de licenciamento, a licença de promotor e uma licença comercial. Para desbloquear as capacidades comerciais da HoloLens, atualize da licença de desenvolvedor para uma licença comercial. Para adquirir a Microsoft HoloLens Commercial Suite, contacte o gestor de conta local da Microsoft.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>Principais características comerciais

- **Modo quiosque.** Você pode usar HoloLens em experiências de demonstração ou showcase usando o modo quiosque, para limitar quais aplicações podem executar.

  ![Utilizando o modo quiosque, o HoloLens lança-se diretamente na aplicação à sua escolha.](images/201608-kioskmode-400px.png)

- **Gestão de Dispositivos Móveis (MDM) para HoloLens.** O seu departamento de TI pode gerir vários dispositivos HoloLens simultaneamente utilizando soluções como o Microsoft Intune. Pode gerir as definições, selecionar aplicações para instalar e definir configurações de segurança adaptadas às necessidades da sua organização.

  ![A Mobile Device Management em HoloLens fornece uma gestão de dispositivos de qualidade empresarial em vários dispositivos.](images/201608-enterprisemanagement-400px.png)

- **Atualização do Windows para Negócios.** O Windows Update for Business fornece atualizações controladas do sistema operativo para dispositivos e suporte para o canal de manutenção a longo prazo.
- **Segurança de dados.** A encriptação de dados BitLocker está ativada nos HoloLens para fornecer o mesmo nível de proteção de segurança que qualquer outro dispositivo Windows.
- **Acesso ao trabalho.** Qualquer pessoa na sua organização pode ligar-se remotamente à rede corporativa através de rede privada virtual (VPN) num HoloLens. Os HoloLens também podem aceder a redes Wi-Fi que requerem credenciais.
- **Microsoft Store para Negócios.** O seu departamento de TI também pode criar uma loja privada empresarial, contendo apenas aplicações da sua empresa para o seu uso específico de HoloLens. Distribua o software da empresa de forma segura a um grupo selecionado de utilizadores empresariais.

## <a name="feature-comparison-between-editions"></a>Comparação de recursos entre edições

|Funcionalidades |Edição de Desenvolvimento hololens (1º gênero) |Suíte Comercial HoloLens (1º gênero) |HoloLens 2 |
|---|:---:|:---:|:---:|
|Encriptação do dispositivo (BitLocker) | |✔️ |✔️ |
|Rede Privada Virtual (VPN) | |✔️ |✔️ |
|[Modo quiosque](hololens-kiosk.md) | |✔️ |✔️ |
|**Gestão e implantação** | | | |
|Gestão de Dispositivos Móveis (MDM) | |✔️ |✔️ |
|Capacidade de bloquear o desenrolar | |✔️ |✔️ |
|Acesso de Wi-Fi corporativa com sede em Cert | |✔️ |✔️ |
|Microsoft Store (Consumidor) |Consumidor |Filtrar utilizando o MDM |Filtrar utilizando o MDM |
|[Portal da Loja de Negócios](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Segurança e identidade** | | | |
|Inscreva-se utilizando a conta Azure Ative Directory (Azure AD) |✔️ |✔️ |✔️ |
|Iniciar scontabilidade utilizando a Conta Microsoft (MSA) |✔️ |✔️ |✔️ |
|Credenciais de próxima geração com desbloqueio PIN |✔️ |✔️ |✔️ |
|[Bota segura](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Manutenção e apoio** | | | |
|Atualizações automáticas do sistema à medida que chegam |✔️ |✔️ |✔️ |
|[Windows Update para Empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Long-Term Canal de Manutenção (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Habilitar características comerciais

O administrador de TI da sua organização pode configurar funcionalidades comerciais como a Microsoft Store para Negócios, o modo quiosque e o acesso Wi-Fi empresa. A documentação [do Microsoft HoloLens](index.yml) fornece instruções passo a passo para a inscrição de dispositivos e instalação de aplicações da Microsoft Store para o Negócio.

## <a name="see-also"></a>Ver também

- [Microsoft HoloLens](index.yml)
- [Modo quiosque](hololens-kiosk.md)
- [CSPs suportados em dispositivos HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store Para Negócios e linha de aplicações empresariais](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Trabalhar com aplicativos de linha de negócio](/microsoft-store/working-with-line-of-business-apps)
