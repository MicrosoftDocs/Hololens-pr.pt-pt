---
title: Configure HoloLens utilizando um pacote de provisionamento (HoloLens)
description: Windows provisão facilita aos administradores de TI a configuração de dispositivos de utilizador final sem imagem.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 999e16f117e4f0838c4a0cb6d6bafcbbf72e1d5a
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859039"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Configure HoloLens utilizando um pacote de provisionamento

[Windows provisão](/windows/configuration/provisioning-packages/provisioning-packages) facilita aos administradores de TI a configuração de dispositivos de utilizador final sem imagem. Windows Configuration Designer é uma ferramenta para configurar imagens e configurações de tempo de execução que são depois incorporadas em pacotes de provisionamento.

Algumas das configurações HoloLens que pode aplicar num pacote de provisionamento incluem:

- Upgrade para [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Criar uma conta local
- Criar uma ligação Wi-Fi
- Aplicar certificados no dispositivo
- Ativar o modo de desenvolvimento
- Configure o modo quiosque seguindo as [nossas instruções detalhadas](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens).

## <a name="provisioning-package-hololens-wizard"></a>Pacote de provisionamento HoloLens assistente

O assistente HoloLens ajuda-o a configurar as seguintes definições num pacote de provisionamento:

- Upgrade para a edição da empresa

    > [!NOTE]
    > Isto só deve ser utilizado para dispositivos de 1ª geração HoloLens. Definições num pacote de provisionamento só são aplicadas se o pacote de provisionamento incluir uma licença de atualização de edição para Windows Holographic for Business ou se [o dispositivo já tiver sido atualizado para Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- Configure a primeira experiência HoloLens (OOBE)
- Configurar a rede Wi-Fi
- Inscreva o dispositivo em Azure Ative Directory ou crie uma conta local
- Adicionar certificados
- Ativar o modo de desenvolvimento
- Configure o modo de quiosque seguindo [instruções detalhadas](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens).

> [!WARNING]
> Tem de executar Windows Configuration Designer no Windows 10 para configurar Azure Ative Directory inscrição utilizando qualquer um dos assistentes.

O fornecimento de pacotes pode incluir instruções e políticas de gestão, conexões e políticas de rede personalizadas, e muito mais.

> [!TIP]
> Utilize o assistente de ambiente de trabalho para criar um pacote com as definições comuns e, em seguida, mude para o editor avançado para adicionar outras definições, apps, políticas, etc.

## <a name="steps-for-creating-provisioning-packages"></a>Medidas para a criação de pacotes de provisionamento

1. **Opção 1:** [A partir de Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Isto inclui HoloLens 2 capacidades.
2. **Opção 2:** [Do Kit de Avaliação e Implantação de Windows (ADK) para Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Se instalar Windows Configuration Designer a partir do Windows ADK, selecione o Designer de **Configuração** a partir do **Select as funcionalidades que pretende instalar na** caixa de diálogo. Esta opção não inclui HoloLens 2 capacidades.

> [!NOTE]
> Se souber que vai utilizar um PC offline que precisa de acesso ao Windows Configuration Designer, siga as instruções de instalação de aplicações offline (hololens-recovery.md#downloading-arc-without-use-the-app-store) para Advanced Recovery Companion. Faça Windows Configuração Designer a sua seleção. 

### <a name="2-create-the-provisioning-package"></a>2. Criar o pacote de provisionamento

Utilize a ferramenta Windows Configuration Designer para criar um pacote de provisionamento.

1. Open Windows Configuration Designer (por padrão, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imagiing and Configuration Designer\x86\ICD.exe).

2. Selecione **dispositivos de HoloLens de provisão**.

   ![Opções de início do ICD](images/icd-create-options-1703.png)

3. Nomeie o seu projeto e **selecione Acabamento**.

4. Leia as instruções na página **'Iniciar'e** selecione **Seguinte**. As páginas para o fornecimento de ambiente de trabalho acompanham-no nos seguintes passos.
  
> [!IMPORTANT]
> Ao construir um pacote de provisionamento, poderá incluir informações sensíveis nos ficheiros do projeto e no ficheiro do pacote de provisionamento (.ppkg). Embora tenha a opção de encriptar o ficheiro .ppkg, os ficheiros do projeto não estão encriptados. Deve armazenar os ficheiros do projeto num local seguro e eliminar os ficheiros do projeto quando já não forem necessários.

### <a name="configure-settings"></a>Configurar definições

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Navegue e selecione o ficheiro de licença da empresa para atualizar a edição HoloLens.</br></br>Também pode alternar <strong>Sim</strong> ou <strong>Não</strong> para esconder partes da primeira experiência.</br></br>Para configurar o dispositivo sem a necessidade de ligar a uma rede Wi-Fi, <strong>alternar a configuração Skip Wi-Fi</strong> para <strong>On</strong>.</br></br>Selecione uma região e um timezone em que o dispositivo será utilizado. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>Nesta secção, pode introduzir os detalhes da rede sem fios Wi-Fi a que o dispositivo deve ligar-se automaticamente. Para isso, selecione <strong>On</strong>, insira o SSID, o tipo de rede<strong>(Aberto</strong> ou <strong>WPA2-Personal)</strong>e (se <strong>WPA2-Personal) a palavra-passe</strong>para a rede sem fios.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Pode inscrever o dispositivo em Azure Ative Directory ou criar uma conta local no dispositivo</br></br>Antes de utilizar um assistente de design de configuração Windows para configurar a inscrição a granel Azure AD, <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">crie a Azure AD junte-se à sua organização.</a> O <strong>número máximo de dispositivos por utilizador</strong> na definição do seu inquilino AZure AD determina quantas vezes o sinal a granel que obtém no assistente pode ser utilizado. Para inscrever o dispositivo no Azure AD, selecione essa opção e introduza um nome amigável para o token a granel que irá utilizar o assistente. Desmarcar uma data de validade para o token (máximo é de 30 dias a contar da data em que obtém o token). <strong>Selecione Obter ficha a granel</strong>. No <strong>Let&#39;o faças assinar na</strong> janela, insira uma conta que tenha permissões para se juntar a um dispositivo ao AZure AD e, em seguida, a palavra-passe. Selecione <strong>Aceitar</strong> dar ao Designer de Configuração Windows as permissões necessárias. </br></br>Para criar uma conta local, selecione essa opção e introduza um nome de utilizador e senha. </br></br><strong>Importante:</strong> <br />(Para Windows 10, apenas versão 1607) Se criar uma conta local no pacote de provisionamento, tem de alterar a palavra-passe utilizando a aplicação <strong>Definições</strong> a cada 42 dias. Se a palavra-passe não for alterada durante esse período, a conta poderá estar bloqueada e incapaz de iniciar scontabilidade.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Para obter o dispositivo com um certificado, clique em <strong>Adicionar um certificado</strong>. Introduza um nome para o certificado e, em seguida, navegue para e selecione o certificado a utilizar.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Alternar <strong>Sim</strong> ou <strong>Não</strong> para ativar o Modo de Desenvolvimento no HoloLens. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Saiba mais sobre o Modo Developer.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Não desafine uma palavra-passe para proteger o seu pacote de provisionamento. Se o pacote de provisionamento estiver protegido por uma palavra-passe, o fornecimento do dispositivo HoloLens falhará.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Depois de terminar, **selecione Criar**. Leva apenas alguns segundos. Quando a embalagem é construída, o local onde a embalagem é armazenada é apresentado como uma hiperligação na parte inferior da página.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. Criar um pacote de provisionamento para HoloLens utilizando provisões avançadas

> [!NOTE]
> Um pacote de provisionamento que você cria em **provisões avançadas** não precisa incluir uma licença de upgrade de edição para Windows Holographic for Business aplicar com sucesso a um HoloLens (1º gênero). [Veja mais na Windows Holographic for Business para HoloLens (1ª geração)](hololens1-upgrade-enterprise.md).

1. Na página inicial do Windows Configuration Designer, selecione **Provisão Avançada**.
2. Na janela de detalhes do **projeto Enter,** especifique um nome para o seu projeto e a localização do seu projeto. Opcionalmente, introduza uma breve descrição para descrever o seu projeto.

3. Selecione **Seguinte**.

4. Na **janela Escolha quais as definições para visualizar e configurar** a janela, selecione **Windows 10 Holographic** e, em seguida, selecione **Seguinte**.

5. Selecione **Concluir**.

6. Expanda **as definições de tempo de execução** e personalize o pacote utilizando qualquer uma das definições [descritas mais tarde neste artigo](#what-you-can-configure).

    > [!IMPORTANT]
    > (Para Windows 10, apenas versão 1607) Se criar uma conta local no pacote de provisionamento, tem de alterar a palavra-passe utilizando a aplicação **Definições** a cada 42 dias. Se a palavra-passe não for alterada durante esse período, a conta poderá estar bloqueada e incapaz de iniciar scontabilidade. Se a conta do utilizador estiver bloqueada, tem de [efetuar uma recuperação completa do dispositivo](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).

7. Selecione **guardar**  >  **ficheiros**.

8. Leia o aviso de que os ficheiros do projeto podem conter informações sensíveis e selecione **OK**.

    > [!IMPORTANT]
    > Ao construir um pacote de provisionamento, poderá incluir informações sensíveis nos ficheiros do projeto e no ficheiro do pacote de provisionamento (.ppkg). Embora tenha a opção de encriptar o ficheiro .ppkg, os ficheiros do projeto não estão encriptados. Deve armazenar os ficheiros do projeto num local seguro e eliminar os ficheiros do projeto quando já não forem necessários.

9. Selecione   >  **pacote de provisão de exportação**.

10. Alterar **proprietário** para **administrador de TI**. Isto define a precedência deste pacote de provisionamento superior ao que os pacotes de provisionamento aplicados a este dispositivo a partir de outras fontes. Selecione **Seguinte**.

11. Desa estação de valor para **a versão pacote**.

    > [!TIP]
    > Pode escoar alterações nos pacotes existentes e alterar o número da versão para atualizar pacotes previamente aplicados.

12. Nos **dados de segurança Select para o pacote de provisionamento**, selecione **Next**.

    > [!WARNING]
    > Se encriptar o pacote de provisionamento, o fornecimento do dispositivo HoloLens falhará.  

13. Selecione **Next** para especificar o local de saída onde deseja que o pacote de provisionamento vá assim que for construído. Por predefinição, Windows Configuration Designer utiliza a pasta do projeto como localização de saída.

    Opcionalmente, pode selecionar **procurar** para alterar o local de saída predefinido.

14. Selecione **Seguinte**.

15. Selecione **Build** para começar a construir o pacote. A informação do projeto é exibida na página de construção e a barra de progresso indica o estado de construção.

16. Quando a construção terminar, **selecione Acabamento**.

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Aplicar um pacote de provisionamento para HoloLens durante a configuração

HoloLens 2 dispositivos em Windows Holographic, versão 2004 ou construir [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) ou mais tarde, podem utilizar uma unidade USB para aplicar um pacote de provisionamento. Basta copiar o ficheiro .ppkg para a raiz da unidade USB. Os pacotes de provisionamento só serão aplicados se estiverem na raiz da unidade USB. O pacote de provisionamento múltiplo presente será aplicado sequencialmente.

HoloLens 2 dispositivos Windows na [versão Holográfica 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou mais tarde têm funcionalidades mais recentes para ajudar a simplificar e simplificar este processo tornando-o automático. Por favor, reveja as seguintes secções:

- [Provisão de lançamento automático a partir de USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Pacotes de provisão automática em OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Provisionamento automático sem utilização de UI](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Utilize o cabo USB para ligar o dispositivo a um PC (ou unidade USB para HoloLens 2, como mencionado acima) e, em seguida, ligue o dispositivo. Não continue além da primeira página de **momento interagivel** da OOBE.
    - No HoloLens (1º gágeno), esta página contém uma caixa azul.
    - No HoloLens 2, esta página contém o beija-flor.

2. Pressione e solte brevemente os botões **Volume Down** e **Power** simultaneamente.

3. HoloLens aparece como um dispositivo no Explorador de Ficheiros no PC.

4. No File Explorer, arraste e deixe cair o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.

5. Prima e solte brevemente os botões **Volume Down** e **Power** em simultâneo novamente enquanto na primeira página de **momento interagiível** de OOBE.

6. O dispositivo pergunta-lhe se confia no pacote e gostaria de aplicá-lo. Confirme que confia no pacote.

7. Verá se o pacote foi aplicado com sucesso ou não. Se falhar, pode consertar o seu pacote e tentar novamente. Se tiver sucesso, proceda com a OOBE.

> [!NOTE]
> Se o dispositivo foi adquirido antes de agosto de 2016, terá de iniciar scontabilidade no dispositivo utilizando uma conta Microsoft, obter a mais recente atualização do sistema operativo e, em seguida, redefinir o sistema operativo para aplicar o pacote de provisionamento.

### <a name="auto-launch-provisioning-from-usb"></a>Provisão de lançamento automático a partir de USB

- Processos automatizados que permitem uma menor interação do utilizador, quando as unidades USB com Pacotes de Provisionamento são utilizadas durante o OOBE.

Antes desta libertação, os utilizadores tiveram de lançar manualmente o ecrã de provisionamento durante o OOBE para obterem uma combinação de botões. Agora os utilizadores podem saltar a combinação de botões, utilizando um Pacote de Provisionamento numa unidade de armazenamento USB.

1. Ligue a unidade USB com o pacote de provisionamento durante o primeiro momento interagivel da OOBE
1. Quando o dispositivo estiver pronto para ser a provisionado, abrirá automaticamente o pedido com a página de provisionamento.

Nota: Se uma unidade USB for deixada ligada durante o arranque do dispositivo, então o OOBE enumerará o dispositivo de armazenamento USB existente, bem como o relógio para outros que estão ligados.

Continuar a ler [A aplicação de pacotes de provisionamento durante o OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Pacotes de provisão automática em OOBE
- O processo automatizado permite uma menor interação do utilizador, quando a página 'Pacote de Provisionamento' for apresentada, aplicará automaticamente todos os pacotes listados.

Quando o ecrã principal de provisionamento aparecer, o OOBE irá contar 10 segundos antes de começar automaticamente a aplicar todos os pacotes de provisionamento. Os utilizadores ainda podem confirmar ou cancelar dentro destes 10 segundos depois de verificarem as embalagens que esperavam.

### <a name="automatic-provisioning-without-using-ui"></a>Provisionamento automático sem utilização de UI
- Processos automáticos combinados para interações reduzidas do dispositivo para o provisionamento. 

Ao combinar o lançamento automático do fornecimento de dispositivos USB e a confirmação automática de pacotes de provisionamento, um utilizador pode providenciar HoloLens 2 dispositivos automaticamente sem utilizar o UI do dispositivo ou mesmo usar o dispositivo. Pode continuar a utilizar a mesma unidade USB e pacote de provisionamento para vários dispositivos. Isto é útil para a implementação de vários dispositivos ao mesmo tempo na mesma área. 

1. [Crie um pacote de provisionamento](hololens-provisioning.md) utilizando [Windows Designer de Configuração](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie a embalagem para uma unidade de armazenamento USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) a [19041.1361 ou construção mais recente](https://aka.ms/hololens2previewdownload). 
1. Quando [o Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) tiver completado o piscar, o seu dispositivo desliga o cabo USB-C. 
1. Ligue a sua unidade USB ao dispositivo.
1. Quando o HoloLens 2 botas de dispositivo para o OOBE, irá detetar automaticamente o pacote de provisionamento na unidade USB e lançar a página de provisionamento.
1. Após 10 segundos, o dispositivo aplicará automaticamente o pacote de provisionamento. 

O seu dispositivo está agora configurado e apresentará o ecrã "Provisioning Successful".

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Aplicar/Remover um pacote de provisionamento para HoloLens após a configuração

> [!NOTE]
> Estes passos aplicam-se a todos os dispositivos HoloLens 2 dispositivos e dispositivos HoloLens (1ª gen) em Windows Holographic, versão 1809 ou acima.

No seu PC, siga estes passos:
1. Criar um pacote de provisionamento, tal como descrito na [Criação de um pacote de provisionamento para HoloLens utilizando o assistente HoloLens](hololens-provisioning.md).
2. Ligação o dispositivo HoloLens a um PC utilizando um cabo USB. HoloLens aparece como um dispositivo no Explorador de Ficheiros no PC.
3. Arraste e deixe cair o pacote de provisionamento na pasta Documentos no HoloLens.

Na sua HoloLens, siga estes passos:
1. Vá a **Definições**  >  **Contas**  >  **Acesso ao trabalho ou à escola.** 
2. Em **Definições Relacionados,** selecione **Adicionar ou remova um pacote de provisionamento**.
3. Na página seguinte, **selecione Adicione um pacote** para lançar o selecionador de ficheiros e selecione o seu pacote de provisionamento. Se a pasta estiver vazia, certifique-se de que seleciona **este dispositivo** e selecione **Documentos**.

Depois de a sua embalagem ter sido aplicada, aparece na lista de **pacotes instalados.** Para ver os detalhes da embalagem ou para remover a embalagem do dispositivo, selecione a embalagem listada.

## <a name="what-you-can-configure"></a>O que pode configurar

Os pacotes de provisionamento utilizam os prestadores de serviços de configuração (CSPs). Se não estiver familiarizado com os CSPs, consulte [Introdução aos prestadores de serviços de configuração (CSPs) para profissionais de TI](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

Em Windows Configuration Designer, quando cria um pacote de provisionamento para Windows Holographic, as definições em **personalizações disponíveis** são baseadas [em CSPs que são suportados em Windows Holográfico](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices). A tabela que se segue descreve as definições que poderá querer configurar para HoloLens.

![Configurações comuns de tempo de execução para HoloLens](images/icd-settings.png)

| Definições | Descrição |
| --- | --- |
| **Certificados** | Desloque um certificado para HoloLens.  |
| **ConectividadeProfilos** | Desloque um perfil Wi-Fi para HoloLens.   |
| **EditionUpgrade** | [Upgrade para Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Políticas** | Permitir ou prevenir o modo de desenvolvimento no HoloLens. [Políticas apoiadas por Windows Holographic for Business](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Instalação de aplicativos através do Pacote de Provisionamento

As aplicações podem ser instaladas através de pacotes de provisionamento em HoloLens 2 dispositivos. Isto permite um pacote facilmente reutilizável que pode usar para ajudá-lo a distribuir as suas aplicações. Leia as instruções completas para [a implementação de aplicativos através de Pacotes de Provisionamento](app-deploy-provisioning-package.md).  

> [!NOTE]
> HoloLens (1ª geração) tem aplicações de instalação de suporte limitado **(UniversalAppInstall**) utilizando um pacote de provisionamento. HoloLens dispositivos (1ª geração) só suportam a instalação de uma aplicação via PPKG apenas durante o OOBE e apenas com instalações de contexto do utilizador.
