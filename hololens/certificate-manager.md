---
title: Gestor de Certificados
description: Aprenda a instalar, gerir e remover manualmente certificados em dispositivos de realidade mista HoloLens 2.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378515"
---
# <a name="certificate-manager"></a><span data-ttu-id="a1445-103">Gestor de Certificados</span><span class="sxs-lookup"><span data-stu-id="a1445-103">Certificate Manager</span></span>

- <span data-ttu-id="a1445-104">Melhoria da auditoria, diagnóstico e validação da segurança do dispositivo e cumprimento através do novo Gestor de Certificados.</span><span class="sxs-lookup"><span data-stu-id="a1445-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="a1445-105">Esta capacidade permitir-lhe-á implantar, resolver problemas e validar os seus certificados em escala em ambientes comerciais.</span><span class="sxs-lookup"><span data-stu-id="a1445-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="a1445-106">No Windows Holographic, versão 20H2, estamos a adicionar um Certificate Manager na aplicação HoloLens 2 Settings.</span><span class="sxs-lookup"><span data-stu-id="a1445-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="a1445-107">Ir a **Definições > Atualizar & Certificados de segurança > de segurança**.</span><span class="sxs-lookup"><span data-stu-id="a1445-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="a1445-108">Esta funcionalidade fornece uma forma simples e fácil de visualizar, instalar e remover certificados no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a1445-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="a1445-109">Com o novo Gestor de Certificados, os administradores e utilizadores têm agora uma ferramenta melhorada de auditoria, diagnóstico e validação para garantir que os dispositivos se mantenham seguros e conformes.</span><span class="sxs-lookup"><span data-stu-id="a1445-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="a1445-110">**Auditoria:** Capacidade de validar que um certificado é implantado corretamente ou de confirmar que foi removido adequadamente.</span><span class="sxs-lookup"><span data-stu-id="a1445-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="a1445-111">**Diagnóstico:** Quando surgem problemas, validar que os certificados adequados existem no dispositivo poupa tempo e ajuda na resolução de problemas.</span><span class="sxs-lookup"><span data-stu-id="a1445-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="a1445-112">**Validação:** Verificar se um certificado serve o fim pretendido e é funcional, pode economizar tempo significativo, particularmente em ambientes comerciais antes de implantar certificados em maior escala.</span><span class="sxs-lookup"><span data-stu-id="a1445-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="a1445-113">Para encontrar rapidamente um certificado específico na lista, existem opções para classificar pelo nome, loja ou data de validade.</span><span class="sxs-lookup"><span data-stu-id="a1445-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="a1445-114">Os utilizadores também podem procurar diretamente um certificado.</span><span class="sxs-lookup"><span data-stu-id="a1445-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="a1445-115">Para ver as propriedades individuais do certificado, selecione o certificado e clique em **Informação**.</span><span class="sxs-lookup"><span data-stu-id="a1445-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="a1445-116">A instalação do certificado suporta atualmente ficheiros .cer e .crt.</span><span class="sxs-lookup"><span data-stu-id="a1445-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="a1445-117">Os Proprietários de Dispositivos podem instalar certificados na Máquina Local e no Utilizador Atual;  todos os outros utilizadores só podem instalar-se no Utilizador Atual.</span><span class="sxs-lookup"><span data-stu-id="a1445-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="a1445-118">Os utilizadores só podem remover certificados instalados diretamente a partir do UI de Definições.</span><span class="sxs-lookup"><span data-stu-id="a1445-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="a1445-119">Se um certificado tiver sido instalado através de outros meios, deve também ser removido pelo mesmo mecanismo.</span><span class="sxs-lookup"><span data-stu-id="a1445-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="a1445-120">Para instalar um certificado:</span><span class="sxs-lookup"><span data-stu-id="a1445-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="a1445-121">Ligue os HoloLens 2 a um PC.</span><span class="sxs-lookup"><span data-stu-id="a1445-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="a1445-122">Coloque o ficheiro de certificado que pretende instalar num local no seu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a1445-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="a1445-123">Navegue para **Definições App > Atualizar & Certificados de segurança >** e selecione Instalar um certificado.</span><span class="sxs-lookup"><span data-stu-id="a1445-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="a1445-124">Clique em **'Importar' e** navegue para o local onde guardou o certificado.</span><span class="sxs-lookup"><span data-stu-id="a1445-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="a1445-125">Selecione **a localização da loja**.</span><span class="sxs-lookup"><span data-stu-id="a1445-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="a1445-126">Selecione **Certificate Store**.</span><span class="sxs-lookup"><span data-stu-id="a1445-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="a1445-127">Clique em **Install** (Instalar).</span><span class="sxs-lookup"><span data-stu-id="a1445-127">Click **Install**.</span></span>

<span data-ttu-id="a1445-128">O certificado deve agora ser instalado no aparelho.</span><span class="sxs-lookup"><span data-stu-id="a1445-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="a1445-129">Para remover um certificado:</span><span class="sxs-lookup"><span data-stu-id="a1445-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="a1445-130">Embora possa ver certificados implantados pelo MDM no Certificate Manager, não pode desinstalá-los no Certificate Manager.</span><span class="sxs-lookup"><span data-stu-id="a1445-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="a1445-131">Deve desinstalá-los através do MDM.</span><span class="sxs-lookup"><span data-stu-id="a1445-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="a1445-132">Navegue para **definições app > atualização e segurança > certificados**.</span><span class="sxs-lookup"><span data-stu-id="a1445-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="a1445-133">Procure o certificado pelo nome na caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a1445-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="a1445-134">Selecione o certificado.</span><span class="sxs-lookup"><span data-stu-id="a1445-134">Select the certificate.</span></span>
1. <span data-ttu-id="a1445-135">Clique **em Remover**</span><span class="sxs-lookup"><span data-stu-id="a1445-135">Click **Remove**</span></span>
1. <span data-ttu-id="a1445-136">Selecione **Sim** quando solicitado para confirmação.</span><span class="sxs-lookup"><span data-stu-id="a1445-136">Select **Yes** when prompted for confirmation.</span></span>



![Espectador de certificado na aplicação Definições sob Certificados](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar o Certificado UI para instalar um certificado em Definições.](images/certificate-device-install.jpg)
