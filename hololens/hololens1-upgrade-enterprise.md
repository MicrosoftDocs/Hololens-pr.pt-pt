---
title: Desbloqueie funcionalidades de Windows Holographic for Business
description: Ao fazer upgrade para Windows Holographic for Business, HoloLens fornece funcionalidades extra que são projetadas para o negócio.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 7cf35a10a5f18dc0ccca876230b1677c6eca54ad116f0b2045fc1b269ac6c4b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661910"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Desbloqueie funcionalidades de Windows Holographic for Business

> [!IMPORTANT]
> Esta página aplica-se apenas a HoloLens 1ª Gen.

Microsoft HoloLens está disponível na *Edição de Desenvolvimento,* que decorre Windows Holographic (edição de Windows 10 que é projetada para HoloLens), e na [Suite Comercial,](hololens-commercial-features.md)que oferece funcionalidades extra desenhadas para o negócio.

Ao comprar a Suite Comercial, recebe uma licença que atualiza Windows Holographic para Windows Holographic for Business. Pode aplicar esta licença ao dispositivo, utilizando o fornecedor de gestão de [dispositivos móveis (MDM)](#edition-upgrade-by-using-mdm) da organização ou um [pacote de provisionamento.](#edition-upgrade-by-using-a-provisioning-package)

> [!TIP]
> Em Windows 10, versão 1803, pode verificar se o HoloLens foi atualizado para a edição de negócios selecionando **Definições**  >  **System.**

## <a name="edition-upgrade-by-using-mdm"></a>Upgrade de edição usando MDM

A licença da empresa pode ser aplicada por qualquer fornecedor de MDM que suporte o [prestador de serviços de configuração WindowsLicensing (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx). A versão mais recente da API do Microsoft MDM irá suportar o WindowsLicensing CSP.

Para obter instruções passo a passo para atualizar HoloLens utilizando Microsoft Intune, consulte [os dispositivos de atualização Windows Holográfico para Windows Holographic for Business](/intune/holographic-upgrade).

 Em outros fornecedores de MDM, as medidas específicas para a criação e implementação da política podem variar.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Upgrade de edição usando um pacote de provisionamento

Os pacotes de provisionamento são ficheiros criados pela ferramenta Windows Configuration Designer que aplicam uma configuração especificada a um dispositivo.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Criar um pacote de provisionamento que melhore a Windows edição Holográfica

1. [Crie um pacote de provisionamento para HoloLens.](hololens-provisioning.md)
1. Vá às **definições de tempo de**  >  **execução EditionUpgrade** e selecione **EditionUpgradeWithLicense**.

    ![Edição de upgrade com definição de licença selecionada](images/icd1.png)

1. Encontre o ficheiro de licença XML que foi fornecido quando adquiriu a Suite Comercial.

    > [!NOTE]
    > Pode configurar [definições adicionais no pacote de provisionamento](hololens-provisioning.md).

1. No menu **File** (Ficheiro), selecione **Save** (Guardar). 

1. Leia o aviso de que os ficheiros do projeto podem conter informações sensíveis e clicar **em OK**.

    > [!IMPORTANT]
    > Ao construir um pacote de provisionamento, poderá incluir informações sensíveis nos ficheiros do projeto e no ficheiro do pacote de provisionamento (.ppkg). Embora tenha a opção de encriptar o ficheiro .ppkg, os ficheiros do projeto não estão encriptados. Deve armazenar os ficheiros do projeto num local seguro e eliminar os ficheiros do projeto quando já não for necessário.

1. No menu **Exportar,** selecione **Pacote de Provisionamento**.

1. Alterar **Proprietário** para **IT Admin,** que define a precedência deste pacote de provisionamento para ser superior a outros aplicados a este dispositivo de diferentes fontes, e, em seguida, selecione **Next**.

1. Desa estação de valor para **a versão pacote**.

    > [!TIP]
    > Pode escoar alterações nos pacotes existentes e alterar o número da versão para atualizar pacotes previamente aplicados.

1. Em **Detalhes de segurança selecionados para o pacote de provisionamento**, selecione **Next**.

1. Selecione **Next** para especificar o local de saída onde deseja que o pacote de provisionamento vá assim que for construído. Por predefinição, Windows ICD utiliza a pasta do projeto como localização de saída.

    Opcionalmente, pode selecionar **procurar** para alterar o local de saída predefinido.

1. Selecione **Seguinte**.

1. Selecione **Build** para começar a construir o pacote. A página de construção exibe a informação do projeto, e a barra de progresso indica o estado de construção.

1. Quando a construção terminar, **selecione Acabamento**.

### <a name="apply-the-provisioning-package-to-hololens"></a>Aplicar o pacote de provisionamento à HoloLens

1. Utilizando o cabo USB, ligue o dispositivo a um PC. Inicie o dispositivo, mas não continue além da página **de ajuste** da experiência inicial de configuração (a primeira página com a caixa azul). No PC, HoloLens aparece como um dispositivo no Explorador de Ficheiros.

    > [!NOTE]
    > Se o dispositivo HoloLens estiver a funcionar Windows 10, versão 1607 ou mais cedo, abra o File Explorer premindo e libertando simultaneamente os botões **Volume Down** e **Power** no dispositivo.

1. No File Explorer, arraste e deixe cair o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.

1. Enquanto HoloLens ainda estiver na página **de ajuste,** prima e solte brevemente os botões **Volume Down** e **Power** simultaneamente.

1. HoloLens pergunta se confia no pacote e gostaria de aplicá-lo. Confirme que confia no pacote.

1. Verá se o pacote foi aplicado com sucesso ou não. Se não foi aplicado com sucesso, pode consertar a sua encomenda e tentar novamente. Se for bem sucedido, proceda à configuração do dispositivo.
