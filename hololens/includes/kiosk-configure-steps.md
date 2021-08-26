---
ms.openlocfilehash: 7a7122790d3e0257c07cdd8bc8c7f658b3a0e279
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859429"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune modelo de quiosque de aplicativo único](#tab/uisak)

## <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune modelo de quiosque de aplicativo único

1. Criar um perfil de configuração <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Escolha o modelo de quiosque <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Escolha se uma aplicação única ou vários quiosques de aplicações e também escolha o tipo de utilizadores direcionados para o modo quiosque <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Escolha a app para correr em modo quiosque <br> 
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Deixe o resto das opções como está <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Escolha quais grupos/ dispositivos ou utilizadores este perfil de configuração deve ser atribuído <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Reveja e crie para guardar o perfil de configuração
8. Execute a sincronização de MDM a partir de qualquer dispositivo ou Intune para aplicar a configuração do dispositivo. [Sync dispositivos do Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou no dispositivo através **de Definições -> Contas -> Trabalho ou escola ->** selecione a conta conectada **-> Info -> Sync**
9. Inscreva-se como utilizador-alvo para experimentar quiosque.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune modelo de quiosque de vários aplicativos](#tab/uimak)

## <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune modelo de quiosque de vários aplicativos

1. Criar um perfil de configuração <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Escolha o modelo de quiosque <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Escolha se uma aplicação única ou vários quiosques de aplicações e também escolha o tipo de utilizadores direcionados para o modo quiosque <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Escolha a(s) aplicação para correr em modo quiosque <br> 
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Deixe o resto das opções como está <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Escolha quais grupos/ dispositivos ou utilizadores este perfil de configuração deve ser atribuído <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Reveja e crie para guardar o perfil de configuração
8. Execute a sincronização de MDM a partir de qualquer dispositivo ou Intune para aplicar a configuração do dispositivo. [Sync dispositivos do Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou no dispositivo através **de Definições -> Contas -> Trabalho ou escola ->** selecione a conta conectada **-> Info -> Sync**
9. Inscreva-se como utilizador-alvo para experimentar quiosque.

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune modelo personalizado](#tab/intunecustom)

## <a name="microsoft-intune-custom-template"></a>Microsoft Intune modelo personalizado

1. Crie configuração xml para a experiência de quiosque desejada. Veja [exemplos](../hololens-kiosk-reference.md#kiosk-xml-code-samples) aqui para começar.

1. Crie um perfil de configuração personalizado <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Especifique o nome do perfil de configuração personalizada e clique em "Adicionar" na secção "Configuração" para adicionar as definições OMA-URI. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Especificar o nome das definições OMA-URI.

    1. Na caixa de texto OMA-URI, **introduza ./Dispositivo/Fornecedor/MSFT/AtribuiçãoAccess/Configuração**
    1. Escolha o tipo de dados como **String.**
    1. Na caixa de texto de valor, copie a configuração de acesso atribuída xml (ver links de referência para exemplos baseados no seu cenário e atualização conforme necessário antes da cópia-colar).
    1. Selecione o botão de poupança para guardar a definição e a configuração.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Escolha quais grupos/dispositivos ou utilizadores este perfil de configuração deve ser atribuído. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Reveja e crie para guardar o perfil de configuração.
1. Execute a sincronização de MDM a partir de qualquer dispositivo ou Intune para aplicar a configuração do dispositivo. [Sync dispositivos do Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou no dispositivo através **de Definições -> Contas -> Trabalho ou escola ->** selecione a conta conectada **-> Info -> Sync**
1. Inscreva-se como utilizador-alvo para experimentar quiosque.

# <a name="runtime-provisioning---multi-app"></a>[Fornecimento de tempo de execução - Multi app](#tab/ppkgmak)

## <a name="runtime-provisioning---multi-app"></a>Fornecimento de tempo de execução - Multi app

1. Crie configuração xml para a experiência de quiosque desejada. Veja [exemplos](../hololens-kiosk-reference.md#kiosk-xml-code-samples) aqui para começar.

1. [Open Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Na página Iniciar **selecione Dispositivos HoloLens.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Selecione **Disposição HoloLens 2 dispositivos e,** em seguida, selecione em seguida. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Diga o nome do seu projeto. Opcionalmente, escreva uma descrição. **Selecione Acabamento** para prosseguir.

6. Na parte inferior esquerda do ecrã, selecione **Switch para editor avançado.** Confirme a mudança para o editor avançado selecionando **Sim.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. No lado esquerdo, expanda as definições de tempo de execução, atribuição deaccess e selecione **MultiAppAssignedAccess**. <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Selecione o botão **Procurar…** botão para abrir o explorador de ficheiros. E selecione o seu ficheiro kiosk xml configurado.

9. Selecione **Export** , em **seguida, Pacote de Provisionamento**.

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Alterar o tipo de proprietário para **o Administrador DE TI.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Selecione **Seguinte** três vezes. Em seguida, **selecione Build**.

12. Depois de construir o seu pacote de provisionamento, abra a pasta de localização de saída. O ficheiro .ppkg é o seu pacote de provisões. Passo opcional: Salvar o seu projeto.

13. Agora pode aplicar o seu pacote de provisionamento. Pode [aplicar um pacote de provisionamento para HoloLens durante a configuração](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ou aplicar um pacote de [provisionamento para HoloLens após a configuração](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

14. Inscreva-se como utilizador-alvo para experimentar quiosque.

# <a name="runtime-provisioning---single-app"></a>[Fornecimento de tempo de execução - Aplicação única](#tab/ppkgsak)

## <a name="runtime-provisioning---single-app"></a>Fornecimento de tempo de execução - Aplicação única

1. [Open Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Na página Iniciar **selecione Dispositivos HoloLens.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Selecione **Disposição HoloLens 2 dispositivos e,** em seguida, selecione em seguida. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Diga o nome do seu projeto. Opcionalmente, escreva uma descrição. **Selecione Acabamento** para prosseguir.

5. Na parte inferior esquerda do ecrã, selecione **Switch para editor avançado.** Confirme a mudança para o editor avançado selecionando **Sim.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. No lado esquerdo, expanda as definições de tempo de execução, atribuição de acessos e **selecione Atribuição DeSatribuição**. <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Defina o seu quiosque na caixa de texto. Por exemplo, o seguinte cria um único quiosque de aplicações para uma conta local chamada LocalAccount que é a aplicação de definições.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Selecione **Export** , em **seguida, Pacote de Provisionamento**. <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Alterar o tipo de proprietário para **o Administrador DE TI.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Selecione **Seguinte** três vezes. Em seguida, **selecione Build**.

11. Depois de construir o seu pacote de provisionamento, abra a pasta de localização de saída. O ficheiro .ppkg é o seu pacote de provisões. Passo opcional: Salvar o seu projeto.

12. Agora pode aplicar o seu pacote de provisionamento. Pode [aplicar um pacote de provisionamento para HoloLens durante a configuração](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ou aplicar um pacote de [provisionamento para HoloLens após a configuração](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).