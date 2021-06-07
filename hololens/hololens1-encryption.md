---
title: Encriptação HoloLens BitLocker
description: Saiba como ativar a encriptação do dispositivo BitLocker para proteger ficheiros armazenados nos seus dispositivos de realidade mista HoloLens.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378474"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>Encriptação Do HoloLens (1ª Gen) BitLocker

HoloLens (1º gênero) e HoloLens 2 ambos suportam encriptação do dispositivo usando BitLocker, no entanto, BitLocker está sempre ativado em HoloLens 2.

Este artigo irá ajudá-lo a ativar e gerir o BitLocker no HoloLens (1º género).

No HoloLens (1º gênero) pode ativar a encriptação do dispositivo BitLocker manualmente ou utilizar a gestão de dispositivos móveis (MDM). Siga estas instruções para permitir a [encriptação do dispositivo BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) para proteger ficheiros e informações armazenados nos HoloLens. A encriptação do dispositivo ajuda a proteger os seus dados utilizando o método de encriptação AES-CBC 128, que é equivalente ao [método 3 do Método EncryptionMethodByDriveType](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) no fornecedor de serviços de configuração BitLocker (CSP). O pessoal que tiver a chave de encriptação correta (como uma palavra-passe) pode desencriptar ou efetuar uma recuperação de dados.

## <a name="enable-device-encryption-using-mdm"></a>Ativar a encriptação do dispositivo usando o MDM

Pode utilizar o seu fornecedor de Gestão de Dispositivos Móveis (MDM) para aplicar uma política que exija encriptação do dispositivo. A política a utilizar é a [definição de Segurança/RequerDeviceEncrição](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) na Política CSP.

[Consulte as instruções para ativar a encriptação do dispositivo utilizando o Microsoft Intune.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

Para outras ferramentas DEDM, consulte a documentação do seu fornecedor de MDM para obter instruções. Se o seu fornecedor DEMS necessitar de URI personalizado para encriptação do dispositivo, utilize a seguinte configuração:

- **Nome**: um nome à sua escolha
- **Descrição**: opcional
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- Tipo de **dados**: inteiro
- **Valor:**`1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Ativar a encriptação do dispositivo utilizando um pacote de provisionamento

Os pacotes de provisionamento são ficheiros criados pela ferramenta Design de Configuração do Windows que aplicam uma configuração especificada a um dispositivo. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Crie um pacote de provisionamento que atualize a edição holográfica do Windows e permita encriptação

1. [Crie um pacote de provisões para hololens.](hololens-provisioning.md)
1. Vá para **configurações de tempo de**  >    >  **execução Segurança** políticas e selecione **RequireDeviceEncryption**.

    ![Requerer a configuração de encriptação do dispositivo configurado para sim](images/device-encryption.png)

1. Encontre o ficheiro de licença XML que foi fornecido quando adquiriu a Suite Comercial.

1. Navegue e selecione o ficheiro de licença XML que foi fornecido quando adquiriu a Suite Comercial.
    > [!NOTE]
    > Pode configurar [definições adicionais no pacote de provisionamento](hololens-provisioning.md).

1. No menu **Ficheiro**, clique em **Guardar**. 

1. Leia o aviso explicando que os ficheiros do projeto podem conter informações sensíveis e clicar **em OK**.

    > [!IMPORTANT]
    > Ao construir um pacote de provisionamento, poderá incluir informações sensíveis nos ficheiros do projeto e no ficheiro do pacote de provisionamento (.ppkg). Embora tenha a opção de encriptar o ficheiro .ppkg, os ficheiros do projeto não estão encriptados. Deve armazenar os ficheiros do projeto num local seguro e eliminar os ficheiros do projeto quando já não for necessário.

1. No menu **Exportação,** clique no **pacote De provisionamento.**
1. Alterar **Proprietário** para **IT Admin,** que definirá a precedência deste pacote de provisionamento superior ao que os pacotes de provisionamento aplicados a este dispositivo a partir de outras fontes, e, em seguida, selecione **Next**.
1. Desa estação de valor para **a versão pacote**.

    > [!TIP]
    > Pode escoar alterações nos pacotes existentes e alterar o número da versão para atualizar pacotes previamente aplicados.

1. Nos **detalhes de segurança Select para o pacote de provisionamento,** clique em **Seguinte**.
1. Clique em **seguida** para especificar o local de saída onde deseja que o pacote de provisionamento vá assim que for construído. Por predefinição, o Windows ICD utiliza a pasta do projeto como localização de saída.

    Opcionalmente, pode clicar em navegar para alterar o local de saída predefinido.

1. Clique em **Seguinte**.
1. Clique **em Build** para começar a construir o pacote. A informação do projeto é exibida na página de construção e a barra de progresso indica o estado de construção.
1. Quando a construção estiver concluída, clique em **Terminar**.

### <a name="apply-the-provisioning-package-to-hololens"></a>Aplicar o pacote de provisionamento aos HoloLens

1. Ligue o dispositivo via USB a um PC e inicie o dispositivo, mas não continue além da página **de ajuste** da experiência inicial de configuração (a primeira página com a caixa azul).
1. Pressione e solte brevemente os botões **Volume Down** e **Power** simultaneamente.
1. Os HoloLens aparecerão como um dispositivo no File Explorer no PC.
1. No File Explorer, arraste e deixe cair o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.
1. Prima e solte brevemente os botões **Volume Down** e **Power** simultaneamente enquanto estiver na página **de ajuste.**
1. O dispositivo irá perguntar-lhe se confia no pacote e gostaria de aplicá-lo. Confirme que confia no pacote.
1. Verá se o pacote foi aplicado com sucesso ou não. Se falhar, pode consertar o seu pacote e tentar novamente. Se tiver sido bem sucedido, proceda com a configuração do dispositivo.

> [!NOTE]
> Se o dispositivo foi adquirido antes de agosto de 2016, terá de iniciar sedutar no dispositivo com uma conta Microsoft, receber a mais recente atualização de SO e, em seguida, redefinir o SISTEMA para aplicar o pacote de provisionamento.

## <a name="verify-device-encryption"></a>Verificar encriptação do dispositivo

A encriptação é silenciosa nos HoloLens. Para verificar o estado de encriptação do dispositivo:

- No HoloLens, vá ao **Sistema de Definições**  >    >  **Sobre**. **O BitLocker** **está ativado** se o dispositivo estiver encriptado. 

    ![Sobre o ecrã mostrando BitLocker ativado](images/about-encryption.png)
