---
title: Guia de Implementação - Corporate connected HoloLens 2 com Dynamics 365 Guides - Configure
description: Saiba como configurar configurações para implementar HoloLens 2 dispositivos numa rede corporativa Conectada com Guias Dinâmicos 365.
keywords: HoloLens, gestão, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Device Management
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637086"
---
# <a name="configure---corporate-connected-guide"></a>Configure - Guia Ligado Corporativo

## <a name="azure-users-and-groups"></a>Utilizadores e Grupos Azure

Azure, e Intune por essa extensão, usa utilizadores e grupos para ajudar a atribuir configurações e licenças. Para validar este fluxo de implementação e poder verificar se pode ser autor e operar um guia,&#39;vai precisar de uma conta de utilizador.

Podemos fazer um único grupo de utilizadores especificamente para a atribuição de licenças.

Se não&#39;já não tem acesso a duas contas AD Azure num grupo de utilizadores que pode utilizar; aqui estão os guias de arranque rápido para:

- [Como criar um utilizador](/mem/intune/fundamentals/quickstart-create-user)
- [Como criar um grupo](/mem/intune/fundamentals/quickstart-create-group)
- [Adicionar utilizadores a um grupo](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Adicionar utilizadores criados para criar grupo
- [Configure Ad AD para permitir que um Grupo de Utilizadores se junte a dispositivos](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Certifique-se de que o novo grupo de utilizadores tem permissão para inscrever dispositivos no Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Inscrição automática no HoloLens 2

Para ter uma experiência suave e sem emenda, a criação de Azure Ative Directory Join (AADJ) e a Inscrição Automática para a Intune para HoloLens 2 dispositivos é o caminho a seguir. Isto permite que os utilizadores insiram as suas credenciais de login da organização durante o OOBE e registem-se automaticamente com a Azure AD e inscrevam o dispositivo no MDM.

Ao utilizar [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/#home)podemos selecionar serviços e navegar algumas páginas até podermos selecionar Obter um Premium teste. Pode notar que há Azure Ative Directory Premium 1 e 2 - para inscrição automática P1 é suficiente. Podemos selecionar Intune e selecionar o âmbito do utilizador para a inscrição automática e selecionar o grupo que foi previamente criado.

Para mais detalhes e passos, leia o guia sobre [como permitir a inscrição automática para o Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Conectividade Wi-Fi Corporativa

As ligações Wi-Fi corporativas requerem geralmente a autenticação baseada em certificados para os clientes que utilizem HoloLens 2. Você precisará de implementar esses certificados usando um Protocolo de Inscrição de Certificado Simples (SCEP) ou infraestrutura de certificados de Padrão de Criptografia de Chave Pública (PKCS) que esteja integrada com a sua solução MDM. A utilização do Intune para implementar perfis Wi-Fi, certificados e configurações de procuração cria uma experiência perfeita para os utilizadores finais.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Implementar certificados e perfis de Wi-Fi

Para implementar certificados e perfis através de Microsoft Endpoint Manager, siga estes passos:

1. Crie um perfil para cada um dos certificados Raiz e Intermediário (ver [Criar perfis de certificados fidedignos).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Cada um destes perfis deve ter uma descrição que inclua uma data de validade no formato DD/MM/YYYY.

    > [!CAUTION]
    > **Os perfis de certificado sem data de validade não serão implantados**.

2. Criar um perfil para cada certificado SCEP ou PKCS (ver [Criar um perfil de certificado SCEP ou criar um perfil de certificado PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Cada um destes perfis deve ter uma descrição que inclua uma data de validade no formato DD/MM/YYYY.

    > [!CAUTION]
    > **Os perfis de certificado sem data de validade não serão implantados.**

    > [!Note]
    > Uma vez que o HoloLens 2 é considerado para muitos como um dispositivo partilhado, ou seja, vários utilizadores por dispositivo, é recomendado a implantação de certificados do Dispositivo em vez de certificados de Utilizador para Wi-Fi autenticação sempre que possível.

3. Crie um perfil para a sua rede de Wi-Fi corporativa (consulte [as definições de Wi-Fi para dispositivos Windows 10 e posteriores).](/intune/wi-fi-settings-windows) Dentro do seu perfil Wi-Fi, pode selecionar para utilizar as definições de procuração dentro da sua organização.

    As opções são:
    - **Nenhuma**: não são configuradas definições de proxy.
    - **Configuração manual**: Introduza o **endereço IP do servidor Proxy** e o seu **número de porta**.
    - **Configurar automaticamente**: Introduza o URL apontando para um script de configuração automática proxy (PAC). Por exemplo, insira *http://proxy.contoso.com/proxy.pac* .

    Para obter mais informações sobre ficheiros PAC, consulte [o ficheiro Proxy Auto-Configuration (PAC)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (abre um site não Microsoft).
 
    > [!Note]
    > Recomenda-se que o perfil Wi-Fi seja atribuído aos grupos de Dispositivos e não aos grupos do Utilizador, sempre que possível.
     
    > [!Tip]
    > Também pode exportar um perfil de Wi-Fi de trabalho a partir de um pc Windows 10 na sua rede corporativa. Esta exportação cria um ficheiro XML com todas as definições atuais. Em seguida, importe este ficheiro para o Intune e use-o como o perfil Wi-Fi para os seus HoloLens 2 dispositivos. Veja [Exportar e importar definições de Wi-Fi para dispositivos com Windows](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Atribua](/mem/intune/configuration/device-profile-assign) os perfis do dispositivo ao grupo de dispositivos HoloLens.

2.  [Monitorize](/mem/intune/configuration/device-profile-monitor) os perfis do dispositivo no Intune.

Se houver problemas com perfis Wi-Fi, [referenciar a resolução de problemas Wi-Fi perfis de configuração do dispositivo no Intune](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Resolução de problemas acesso externo à Internet quando Corp Conectado
Quando os serviços tentam não passar por um Proxy definido, podem tentar ligar-se através da firewall. Pode adicionar uma lista de detalhes do ponto final às suas regras de firewall para resolver estes problemas.

Se estiver bloqueado em portas de firewall, ative alguns [pontos finais comuns](/hololens/hololens-offline) para HoloLens.

Também pode ativar as portas específicas dos Guias: [URLs acessíveis à Internet necessários para a conectividade Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Implementação de Aplicações

Implementar uma aplicação LOB via MDM é um método que é facilmente escalável e pode ser automaticamente implementado nos seus dispositivos após a inscrição num grupo criado.

Se ainda estiver a desenvolver as suas Apps ou ainda não tiver nenhuma, pode utilizar uma aplicação de amostra do hub de exemplos MRTK. Esta aplicação de amostra está pronta a ser utilizada e não requer o uso de unidade ou Visual Studio. [Descarregue a aplicação MRTK Examples Sample](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Se preferir usar a sua própria app ou se estiver interessado no desenvolvimento de aplicações para a Realidade Mista, então sinta-se livre para rever a nossa [documentação do desenvolvedor de Realidade Mista.](/windows/mixed-reality/design/design)

> [!NOTE]
> Os requisitos do sistema para dispositivos HoloLens baseiam-se na arquitetura da construção de aplicações. HoloLens 2 dispositivos utilizam a arquitetura ARM. Ao construir as suas aplicações em Visual Studio, certifique-se de que selecionou a arquitetura correta para o dispositivo e inclui quaisquer dependências necessárias.

> [!IMPORTANT]
> Ao implementar aplicações LOB, é importante também fazer o upload do certificado para o Intune, e atribuí-lo ao mesmo grupo que se destina a usar a app ou não irá instalar corretamente.

### <a name="upload-and-assign-the-app"></a>Upload e Atribuir a App

1. Navegue até ao [centro de administração MEM.](https://endpoint.microsoft.com/#home)

2. Selecione   ->  **Aplicativos Todas as aplicações** e selecione o botão **+ Adicionar.**

3. Por baixo de outras, selecione **linha de negócios .** Clique **em seleção**.

4. Selecione o ficheiro de pacote de aplicativos, este é o seu ficheiro APPXBUNDLE, ou no nosso caso deste exemplo a aplicação é _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle_.

5. Será notificado das dependências desaparecidas. Neste caso, precisamos de carregar _microsoft.VCLibs.ARM.14.00.appx_. Procure-o em **Selecione um ficheiro.**

6. Selecione OK.

7. No ecrã seguinte, os campos necessários serão preenchidos automaticamente. Selecione **Seguinte**.

8. De acordo com o Requerido, adicione o nosso grupo previamente criado para tornar esta app necessária para o grupo. Isto fará com que a aplicação descarregue automaticamente para dispositivos inscritos no grupo. Selecione **Seguinte**.

9. Selecione **Criar**.

Leia mais: [Atribuir aplicativos a grupos em Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Guias de configuração: Licenças de aplicação, versão de dados e autoria

Para utilizar os Guias Dinâmicos 365, terá de fazer alguma preparação. Há três áreas em que temos de nos preparar; utilizadores, dataverse, e os próprios guias.

### <a name="users-and-application-licenses"></a>Utilizadores e licenças de aplicação

Para que alguém utilize Guias, terá de utilizar uma conta AZure AD, que já criámos neste guia anteriormente.

Também terá de atribuir a licença Dynamics 365 Guides ao utilizador que criou. Vais fazer isto do [centro de administração do Microsoft 365.](https://admin.microsoft.com/AdminPortal/Home) Atribua também a licença à sua Conta Azure primária.

Siga [este pequeno guia](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) com imagens para instruções passo a passo sobre a aplicação de licenças de aplicação.

### <a name="set-up-the-dataverse"></a>Configurar o Dataverse

Para [criar um ambiente de produção,](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) terá de cumprir dois pré-requisitos. Tem de ter a [**função de Administrador de Sistema,**](/power-platform/admin/database-security) **e** tem de ter uma licença [**de Power Apps**](/power-platform/admin/signup-question-and-answer) (ou uma licença [**De Guias Dynamics 365**](/dynamics365/mixed-reality/guides/setup-step-one) que inclua uma licença de Power Apps). Se seguir este guia criou o AD Azure, então cumpre os requisitos de função para Administrador de Sistema. Também atribuímos uma Licença de Guias no passo anterior.

Neste guia para [criar um ambiente Microsoft Dataverse](/dynamics365/mixed-reality/guides/setup-step-two):

1. Comece por utilizar o [centro de administração da Plataforma de Energia](https://admin.powerplatform.microsoft.com/environments) e crie um Novo Ambiente.
2. Ao criar o **Novo Ambiente**, para o **Tipo** que&#39;estará a selecionar **Produção**.
3. É importante que altere **Criar uma base de dados para este ambiente?**  opção para  **Sim**.
4. Na caixa de diálogo  **de base de dados Adicionar,**  defina a opção  **de aplicações Enable Dynamics 365**  para  **Sim.**

Deverá aumentar o tamanho máximo de ficheiros de itens no seu conjunto de dados. Aumentar o tamanho do ficheiro máximo permitir-lhe-á carregar modelos 3D maiores ou ficheiros de vídeo que utilizará mais tarde nos seus guias. Siga um guia curto [para alterar o tamanho máximo do ficheiro de upload](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size).

Por último, terá de [instalar e configurar a solução.](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) No [centro de administração da Plataforma de Energia,](https://admin.powerplatform.microsoft.com/environments)selecione **Resources** \& gt;  **Dinâmica 365 aplicações**, selecione **Dynamics 365 Guides** na lista e, em seguida, selecione **Instalar**.  

É necessário [adicionar uma função de segurança guides](/dynamics365/mixed-reality/guides/assign-role) antes de poder utilizar as aplicações.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Crie um Guia de Teste no seu PC através da Autoria

Ao criar Guias, iniciará sempre o seu PC. Criar os passos, selecionar modelos e como ancorar o guia. Seguir-se-á a colocação de conteúdos para o seu guia no modo de autoria do seu dispositivo HoloLens. Para efeitos deste guia, sugerimos fazer um pequeno guia de teste com passos e modelos mínimos.

Se quiser começar a aprender sobre a autoria de Guias, comece aqui com a visão geral da [autoria.](/dynamics365/mixed-reality/guides/authoring-overview) Ou para obter uma visão geral rápida, veja este pequeno vídeo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Opcional: Modo quiosque

O modo quiosque é um modo que permite que um Admin IT configurar o UI do menu inicial para mostrar apenas uma única aplicação, ou seleção de aplicações. Um quiosque também pode ser aplicado a utilizadores, grupos específicos ou ao nível do dispositivo; e, em alguns casos, exclua certos utilizadores do Quiosque, permitindo-lhes ainda o acesso ao menu inicial regular.

O modo quiosque tem muitas variáveis diferentes, tanto no âmbito como nas configurações que podem ser definidas, bem como métodos de implantação do Quiosque para o HoloLens. Por causa de todas estas variáveis, o modo quiosque está sendo deixado como _opcional_ para este guia e não será revisitado. Se acredita que tem uma empresa que precisa de restringir as aplicações disponíveis aos utilizadores ou gostaria de aprender mais, então sinta-se livre para aprender a [configurar HoloLens como um quiosque.](/hololens/hololens-kiosk)

## <a name="optional-wdac"></a>Opcional: WDAC

O WDAC permite que um Administrador de TI configuure os seus dispositivos para bloquear o lançamento de aplicações em dispositivos. Isto é diferente dos métodos de restrição do dispositivo, como o modo Quiosque, onde o utilizador é apresentado com uma UI que esconde as aplicações no dispositivo, mas que ainda podem ser lançadas. Enquanto o WDAC é implementado, as aplicações ainda estão visíveis na lista de Todas as Aplicações, mas o WDAC impede que essas aplicações e processos possam ser lançados pelo utilizador do dispositivo.

Para mais informações, utilize o [WDAC e o Windows PowerShell para permitir ou bloquear aplicações em HoloLens 2 dispositivos com Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

[Windows Defender Controlo de Aplicações - WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Passo seguinte 
> [!div class="nextstepaction"]
> [Implementação de ligação corporativa - Implantação](hololens2-corp-connected-deploy.md)