---
title: Windows Autopilot para o HoloLens 2
description: Aprenda a configurar, configurar e resolver problemas O Piloto Automático em HoloLens 2 dispositivos.
author: qianw211
ms.author: v-qianwen
ms.date: 10/11/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: piloto automático
manager: sekerawa
ms.openlocfilehash: 46b57e44186b8944e58e68da66306bbe445b704a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924439"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot para o HoloLens 2

## <a name="overview"></a>Descrição Geral

Para implantar em escala, recomendamos começar com Windows Autopilot. É considerado "baixo toque" na forma como simplifica drasticamente a criação de HoloLens tanto para os utilizadores de TI como para os utilizadores finais. 

A um nível elevado, um administrador de TI normalmente criará as configurações prontas para o negócio e registará HoloLens 2 dispositivos em portais MDM. Quando HoloLens 2 dispositivos iniciam com experiência fora de caixa (OOBE) e se conectam com a Internet, as configurações prontas para o negócio para o dispositivo HoloLens 2 registado são automaticamente descarregadas e aplicadas para tornar os dispositivos prontos para o negócio sem qualquer intervenção do utilizador.

Para mais informações, consulte a [visão geral da | de piloto automático Windows Artigo da Microsoft Docs.](/mem/autopilot/windows-autopilot)

## <a name="supported-autopilot-scenario-on-hololens-2"></a>Cenário de piloto automático apoiado no HoloLens 2

> [!NOTE]
> A configuração do piloto automático para HoloLens em Microsoft Endpoint Manager está a transitar da **Visualização Pública** para a **Disponibilidade Geral**. Todos os inquilinos poderão configurar o Autopilot no centro de administração MEM.

Começando pela versão holográfica Windows 2004, HoloLens 2 suporta Windows [modo de auto-implantação](/mem/autopilot/self-deploying) do Autopilot com Microsoft Intune (os MDMs de terceiros não são suportados). Esta configuração reduz a sobrecarga de gestão de inventário, o custo da preparação prática do dispositivo e as chamadas de suporte dos colaboradores durante a experiência de configuração. Saiba mais na documentação [Windows Autopilot.](/mem/autopilot/windows-autopilot)

Tal como nos dispositivos Surface, recomenda-se que os clientes trabalhem com o seu Microsoft [Fornecedor de Soluções em Nuvem](https://partner.microsoft.com/cloud-solution-provider) (revendedor ou distribuidor) para obter dispositivos registados no serviço Autopilot através do Partner Center.

Quando um utilizador inicia o processo de auto-implantação do Autopilot, o Autopilot completa os seguintes passos:

1. Junte o dispositivo para Azure Ative Directory (Azure AD). O Autopilot para HoloLens não suporta a participação do Ative Directory ou a ad AZure Híbrida.

1. Utilize a Azure AD para inscrever o dispositivo em Microsoft Endpoint Manager (ou noutro serviço MDM).

1. Descarregue e aplique políticas, certificados, perfis de rede e aplicações direcionadas para dispositivos.

1. Apresente o sinal no ecrã ao utilizador.

## <a name="configuring-autopilot-for-hololens-2"></a>Configurar o Piloto Automático para HoloLens 2

Siga os passos abaixo para configurar o seu ambiente:

1. [Rever os requisitos para Windows Autopilot para HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Ativar inscrição automática de MDM](#2-enable-automatic-mdm-enrollment)

1. (Apenas para Intune) [Certifique-se de que a inscrição do MDM não está bloqueada para dispositivos Windows.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Registar dispositivos em Windows Autopilot.](#4-register-devices-in-windows-autopilot)

1. [Criar um grupo de dispositivos.](#5-create-a-device-group)

1. [Crie o perfil do piloto automático e atribua-o ao grupo de dispositivos.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Crie a configuração da Página de Estado de Inscrição (ESP) e atribua-a ao grupo de dispositivos.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [Verifique o estado do perfil dos dispositivos HoloLens.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Requisitos de revisão para Windows Piloto Automático para HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Reveja as seguintes secções do artigo Windows requisitos do Piloto Automático:

- [Requisitos de rede](/mem/autopilot/networking-requirements)  
- [Requisitos de licenciamento](/mem/autopilot/licensing-requirements)  
- [Requisitos de configuração](/mem/autopilot/configuration-requirements)

**Reveja a secção "[Requisitos](/windows/deployment/windows-autopilot/self-deploying#requirements)" do Windows o artigo modo Self-Deploying autopiloto.** O seu ambiente tem de satisfazer estes requisitos e os requisitos padrão Windows Autopilot. Não é preciso rever as secções "Passo a passo" e "Validação" do artigo. Os procedimentos posteriores neste artigo fornecem passos correspondentes específicos à HoloLens.

Certifique-se de que os dispositivos já não são membros da Azure AD, e não estão matriculados no Intune (ou noutro sistema MDM). O processo de auto-implantação do Autopilot completa estes passos. Para se certificar de que todas as informações relacionadas com o dispositivo estão **limpas,** verifique as páginas de Dispositivos tanto em AD AD como em Portais Intune. Neste momento, a função "Converter todos os dispositivos direcionados para o Autopilot" não é suportada HoloLens.

#### <a name="review-hololens-os-requirements"></a>Rever HoloLens os requisitos de OS:

Para confirmar a versão de construção no seu dispositivo ou reflash para o mais recente SO, utilize o [Companheiro de Recuperação Avançada (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) e [as instruções de reflash](hololens-recovery.md)do nosso dispositivo . Os dispositivos entregues até ao final de setembro de 2020 têm Windows versão Holográfica de 1903 pré-instalada. Contacte o seu revendedor para garantir que os dispositivos prontos para o Autopilot sejam enviados para si.

 Versão mínima do sistema operativo | Recurso suportado | Observações
 ------ | ------ | ------  
 [Windows Holographic, versão 2004](hololens-release-notes.md#windows-holographic-version-2004) (construção 19041.1103) ou posterior | 1. Cenário de auto-implantação do Piloto Automático no HoloLens 2. | O download de perfil de piloto automático é suportado apenas via Ethernet. Certifique-se de que a HoloLens está ligada à ethernet utilizando um adaptador "USB-C para Ethernet" **antes de o ligar**.  Se está a planear um lançamento de Piloto Automático para muitos dispositivos HoloLens, recomendamos que planeie a infraestrutura do adaptador. Não recomendamos que os centros USB sejam instalados, uma vez que muitas vezes exigem a instalação de condutores de terceiros que não são suportados em HoloLens.
 [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (construção 19041.1128) ou posterior | 1. Descarregar o perfil do piloto automático sobre o Wi-Fi. <br> 2. [Bloqueio de inquilino CSP e Autopilot](#tenant-lockdown-csp-and-autopilot) para bloquear dispositivos com o inquilino especificado autopiloto. | Pode ainda utilizar adaptadores ethernet, se desejar. Para dispositivos ligados via Wi-fi, o utilizador deve apenas: <ul> <li> Passe pela cena do beija-flor. </li> <li> Escolha o idioma e local. </li> <li> Calibrar os olhos. </li> <li> Conecte-se com sucesso com a rede wi-fi desejada. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Permitir a inscrição automática do MDM:

Para que o Autopilot tenha sucesso, terá de ativar a Inscrição Automática de MDM no seu portal Azure. Isto permitirá que o dispositivo se inscreva sem um utilizador.

Reveja o seguinte guia curto [sobre como permitir a inscrição automática do MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) ou o guia de arranque rápido de [inscrição automática](/mem/intune/enrollment/quickstart-setup-auto-enrollment) para obter ainda mais informações.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Certifique-se de que a inscrição no MDM não está bloqueada para dispositivos Windows.

Para que o Autopilot tenha sucesso, terá de se certificar de que os seus HoloLens dispositivos podem inscrever-se. Uma vez que HoloLens é considerado um dispositivo Windows, não terá de haver restrições de inscrição que possam bloquear a sua implementação. [Reveja esta lista de restrições](/mem/intune/enrollment/enrollment-restrictions-set) e certifique-se de que poderá inscrever os seus dispositivos.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Registar dispositivos em Windows Autopilot

Os seus dispositivos devem estar registados Windows Autopilot antes da primeira configuração.

Existem três formas primárias de registar HoloLens dispositivos:

 - **O revendedor pode registar dispositivos no Centro De Parceiros quando es faz uma encomenda.**

   > [!NOTE]  
   > Este é o caminho recomendado para a adição de dispositivos ao serviço Autopilot. [Saiba mais](/mem/autopilot/partner-registration).  

 - **Pode [submeter um pedido de suporte](hololens2-autopilot-registration-support.md) diretamente à Microsoft.**
 - **Recupere o hash de hardware (também conhecido como ID de hardware) e registe o dispositivo manualmente no centro de administração MEM**.

#### <a name="obtain-hardware-hash"></a>Obtenha haxixe de hardware

Pode recuperar o hash de hardware do dispositivo. O dispositivo regista o seu hash de hardware num ficheiro CSV durante o processo OOBE, ou mais tarde quando um proprietário do dispositivo inicia o processo de recolha de registos de diagnóstico (descrito no seguinte procedimento). Normalmente, o proprietário do dispositivo é o primeiro utilizador a iniciar sôms no dispositivo.

> [!WARNING]
> Em construções anteriores a 20H2, se passou pelo OOBE e a telemetria foi definida como Necessária, não é possível recolher o hash de hardware para o Autopilot através deste método. Para recolher o seu hash de hardware através deste método, desloque a sua opção de telemetria para Full através da App Definições e selecione  >  **Diagnósticos de** Privacidade .

1. Inicie o dispositivo HoloLens 2.

1. No aparelho, prima os botões **De alimentação** e **volume para baixo** ao mesmo tempo e, em seguida, solte-os. O dispositivo recolhe registos de diagnóstico e haxixe de hardware e armazena-os num conjunto de ficheiros .zip.

1. Para mais detalhes e um vídeo instrutivo sobre como realizar esta leitura sobre [o Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).

1. Utilize um cabo USB-C para ligar o dispositivo a um computador.

1. No computador, abra o Explorador de Ficheiros. Abra <b>Este \\ HoloLens</b>nome do dispositivo para < *PC* > <b> \\ \\ Documentos de Armazenamento</b>internos e localize o ficheiro AutopilotDiagnostics.zip.  

   > [!NOTE]  
   > O ficheiro .zip pode não estar imediatamente disponível. Se o ficheiro ainda não estiver pronto, poderá ver um ficheiro HoloLensDiagnostics.temp na pasta Documentos. Para atualizar a lista de ficheiros, refresque a janela.

1. Extrair o conteúdo do ficheiro AutopilotDiagnostics.zip.

1. Nos ficheiros extraídos, localize o ficheiro CSV que tenha um prefixo de nome de ficheiro de "DeviceHash". Copie esse ficheiro para uma unidade no computador onde poderá aceder mais tarde.  

   > [!IMPORTANT]  
   > Os dados do ficheiro CSV devem utilizar o seguinte formato de cabeçalho e linha:
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>Registar dispositivo através do MEM

1. No [centro de administração Microsoft Endpoint Manager](https://endpoint.microsoft.com), selecione **Dispositivos**  >  **Windows** Windows  >  **inscrição**, e, em seguida, selecione **Dispositivos**  >  **Importados** ao abrigo **do Programa Windows Autopilot Deployment**.

1. Em **Adicionar Windows dispositivos Autopilot**, selecione o ficheiro CSV deviceHash, selecione **Abrir** e, em seguida, selecione **Import**.  

   > [!div class="mx-imgBorder"]
   > ![Use o comando Import para importar o hash de hardware.](./images/hololens-ap-hash-import.png)

1. Após o acabamento da importação, selecione **Dispositivos**  >  **Windows**  >  **Windows registo** de  >  **dispositivos**  >  **sync**. O processo pode demorar alguns minutos a ser concluído, dependendo do número de dispositivos que estão a ser sincronizados. Para ver o dispositivo registado, selecione **Refresh**.  

   > [!div class="mx-imgBorder"]
   > ![Utilize os comandos Sync e Refresh para visualizar a lista de dispositivos.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Criar um grupo de dispositivos

1. No [Microsoft Endpoint Manager centro de administração,](https://endpoint.microsoft.com)selecione **Grupos**  >  **Novos** grupos .

1. Para **o tipo de grupo**, selecione **Security**, e, em seguida, introduza um nome de grupo e descrição.

1. Para **o tipo de adesão**, selecione dispositivo **atribuído** ou **dinâmico**.

1. Faça um dos seguintes:  

   - Se selecionou O tipo **atribuído** para **membro** no passo anterior, selecione **Membros** e adicione dispositivos Autopilot ao grupo. Os dispositivos piloto automático que ainda não estão matriculados estão listados utilizando o número de série do dispositivo como nome do dispositivo.
   - Se selecionou **Dispositivos Dinâmicos** para **o tipo de Membro** no passo anterior, selecione **membros do dispositivo Dynamic** e introduza código na regra **Avançada** que se assemelha ao seguinte:
     - Se quiser criar um grupo que inclua todos os seus dispositivos Autopilot, escreva: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Os mapas de campo de tag de grupo da Intune para o atributo **OrderID** em dispositivos AD Azure. Se pretender criar um grupo que inclua todos os seus dispositivos Autopilot que tenham uma etiqueta de grupo específica (o dispositivo AD AD AZure), deve escrever: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Se quiser criar um grupo que inclua todos os seus dispositivos Autopilot que tenham um ID de encomenda de compra específico, escreva: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Estas regras visam atributos exclusivos dos dispositivos Autopilot.
1. **Selecione Guardar** e, em seguida, selecione **Criar**.

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. Criar perfil de piloto automático e atribuí-lo ao grupo de dispositivos

1. No [centro de administração Microsoft Endpoint Manager,](https://endpoint.microsoft.com)selecione **Dispositivos**  >  **Windows**  >  **Windows de inscrição** Windows perfis de  >  **implantação de piloto automático** Crie  >    >  **HoloLens** de perfil .
   ![Criar o dropdown de perfil inclui um item HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Introduza um nome de perfil e descrição e, em seguida, selecione **Seguinte**.  
   Deve ver uma lista que inclua **HoloLens.** Se esta opção não estiver presente, utilize uma das opções [de Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) para nos contactar.

   > [!div class="mx-imgBorder"]
   > ![Adicione um nome de perfil e descrição.](./images/hololens-ap-profile-name.png)

1. Na página **out-of-box experience (OOBE),** a maioria das definições são pré-configuradas para simplificar o OOBE para esta avaliação. Opcionalmente, pode configurar as seguintes definições:  

   - **Idioma (Região)**: Selecione o idioma para OOBE. Recomendamos que selecione um idioma da lista de [idiomas suportados para HoloLens 2](hololens2-language-support.md).
   - **Configurar automaticamente o teclado**: Para se certificar de que o teclado corresponde ao idioma selecionado, selecione **Sim**.
   - **Aplicar o modelo de nome do dispositivo**: Para definir automaticamente o nome do dispositivo durante o OOBE, selecione **Sim** e, em seguida, introduza a frase do modelo e os espaços reservados em Introduzir **um nome** Por exemplo, introduzir um prefixo e um espaço reservado para um número aleatório de `%RAND:4%` &mdash; quatro dígitos.
     > [!NOTE]  
     > Se utilizar um modelo de nome do dispositivo, o processo OOBE reinicia o dispositivo uma vez depois de aplicar o nome do dispositivo e antes de se juntar ao Azure AD. Este reinício permite que o novo nome produza efeitos.  

   > [!div class="mx-imgBorder"]
   > ![Configurar as definições OOBE.](./images/hololens-ap-profile-oobe.png)

1. Depois de configurar as definições, selecione **Seguinte**.
1. Na página **de tags Scope,** adicione opcionalmente as etiquetas de âmbito que pretende aplicar a este perfil. Para obter mais informações sobre etiquetas de âmbito, consulte [utilizar o controlo de acesso baseado em funções e etiquetas de âmbito para TI distribuídos.](/mem/intune/fundamentals/scope-tags.md) Quando terminar, selecione **Seguinte**.
1. Na página **Atribuições,** selecione **grupos selecionados** para **atribuir a**.
1. Em **GRUPOS SELECIONADOS**, selecione **+ Selecione grupos para incluir.**
1. Nos **grupos Select para incluir a** lista, selecione o grupo de dispositivos que criou para os dispositivos de HoloLens autopiloto e, em seguida, selecione **Next**.  
  
   Se pretender excluir quaisquer grupos, **selecione grupos selecionados para excluir,** e selecione os grupos que pretende excluir.

   > [!div class="mx-imgBorder"]
   > ![Atribuindo um grupo de dispositivos ao perfil.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Na página **'Rever + Criar',** rever as definições e, em seguida, selecionar **Criar** para criar o perfil.  

   > [!div class="mx-imgBorder"]
   > ![Review + criar.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Criar configuração de página de estado de inscrição (ESP) e atribuí-la ao grupo de dispositivos

A Página de Estado de Inscrição (ESP) apresenta o estado do processo completo de configuração do dispositivo que funciona quando um utilizador gerido pelo MDM assina num dispositivo pela primeira vez. Certifique-se de que a sua configuração ESP se assemelha ao seguinte e verifique se as atribuições estão corretas.  

> [!div class="mx-imgBorder"]
> ![Configuração ESP.](./images/hololens-ap-profile-settings.png)

Para obter mais informações sobre o ESP, consulte a [Configuração da Página do Estado de Inscrição - Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Verificar o estado do perfil dos dispositivos HoloLens

1. No Microsoft Endpoint Manager Centro de Administração, selecione **Dispositivos**  >  **Windows**  >  Windows dispositivos **de inscrição**  >  .

1. Verifique se os dispositivos HoloLens estão listados e se o seu estado de perfil é **atribuído**.  

   > [!NOTE]  
   > Pode levar alguns minutos para que o perfil seja atribuído ao dispositivo.  

   > [!div class="mx-imgBorder"]
   > ![Atribuição de dispositivos e perfis.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Piloto automático para HoloLens 2 Experiência de Utilizador

Uma vez concluídas as instruções acima, os seus utilizadores HoloLens 2 passarão pela seguinte experiência para providenciar os seus HoloLens dispositivos:  

1. A experiência do piloto automático requer acesso à Internet. Utilize uma das seguintes opções para fornecer acesso à Internet:

    - Ligação o seu dispositivo a uma rede Wi-Fi em OOBE e, em seguida, deixe-o detetar automaticamente a experiência do Autopilot. Esta é a única altura em que terá de interagir com o OOBE até que a experiência do Autopilot se concretize por si só.

    - Ligação o seu dispositivo com o Ethernet utilizando adaptadores "USB-C para Ethernet" para a conectividade da internet com fios e deixe HoloLens 2 completar automaticamente a experiência do Autopilot.

    - Ligação o seu dispositivo com adaptadores "USB-C para Wi-Fi" para conectividade com internet sem fios e deixe HoloLens 2 experimentar automaticamente o Autopilot completo.

        > [!IMPORTANT]  
       > Os dispositivos que tentem utilizar redes Wi-Fi em OOBE para Piloto Automático devem estar Windows [holográfica, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Para os dispositivos que utilizam adaptadores ethernet, deve ligar o dispositivo à rede antes do arranque da Experiência Fora da Caixa (OOBE). O dispositivo determina se está a ser abascida como um dispositivo Autopilot enquanto está no primeiro ecrã OOBE. Se o dispositivo não conseguir ligar-se à rede, ou se optar por não providenciar o dispositivo como um dispositivo Autopilot, não poderá alterar o fornecimento de Piloto Automático posteriormente. Em vez disso, teria de recomeçar este procedimento para poder providenciar o dispositivo como um dispositivo Autopilot.

1. O dispositivo deve iniciar automaticamente o OOBE. Não interage com o OOBE.

    > [!IMPORTANT]
    > Não interaja com o OOBE ou pressione o botão de alimentação para colocar o sistema em modo de espera/paragem, enquanto o piloto automático está em andamento. Isto pode fazer com que o fluxo do piloto automático não esteja completo.

   Deixe HoloLens 2 detetar a conectividade da rede e permitir que complete o OOBE automaticamente. O aparelho pode reiniciar durante o OOBE. Os ecrãs OOBE devem assemelhar-se ao seguinte.

   ![OOBE passo 1. ](./images/autopilot-welcome.jpg)
    ![ Passo OOBE 2. ](./images/autopilot-step-complete.jpg)
    ![ Passo OOBE 3.](./images/autopilot-device-setup.jpg)

1. No final do OOBE, pode iniciar sôms no dispositivo utilizando o seu nome de utilizador e senha.

   <img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>CSP de inquilino e Piloto Automático

HoloLens 2 dispositivos suportam o TenantLockdown CSP a partir de Windows Holographic, versão 20H2. Este CSP mantém dispositivos no inquilino da organização, trancando-os ao inquilino mesmo através do reset ou reflash do dispositivo.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) A CSP permite que HoloLens 2 estejam ligados à inscrição de MDM usando apenas o Autopilot. Uma vez que o nó requere de CSP do TenantLockdown CSP é definido para um valor verdadeiro ou falso (inicialmente definido) no HoloLens 2, esse valor permanece no dispositivo apesar de reflashing, atualizações de SO, etc.

Uma vez que o nó de RequerenetworkInOOBE do TenantLockdown é definido para ser verdadeiro no HoloLens 2, o OOBE aguarda indefinidamente para que o perfil do Piloto Automático seja descarregado e aplicado com sucesso, após a conectividade da rede.

Uma vez que o nó de RequerenetworkInOOBE do TenantLockdown cSPs seja definido para ser verdadeiro em HoloLens 2, as seguintes operações são proibidas em OOBE:

- Criar utilizador local utilizando o fornecimento de tempo de execução
- Realização Azure AD aderir operação através do provisionamento de tempo de execução
- Selecionando quem é o dono do dispositivo na experiência OOBE

#### <a name="how-to-set-this-using-intune"></a>Como definir isto usando o Intune?

1. Crie um perfil de configuração de dispositivo OMA URI personalizado e especifique o caso true for RequireNetworkInOOBE, conforme mostrado abaixo.
O valor OMA-URI deve ser ./Fornecedor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configurar o bloqueio do tennant via OMA-URI.](images/hololens-tenant-lockdown.png)

1. Crie um grupo e atribua o perfil de configuração do dispositivo a esse grupo de dispositivos.

1. Faça o HoloLens 2 membro do dispositivo do grupo criado em sincronização de passo e gatilho anteriores.  

Verifique no portal Intune que a configuração do dispositivo foi aplicada com sucesso. Uma vez que esta configuração do dispositivo se aplique com sucesso no dispositivo HoloLens 2, os efeitos do TenantLockdown estarão ativos.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Como desajustar o TenantLockdown's RequireNetworkInOOBE em HoloLens 2 usando o Intune?

1. Remova o HoloLens 2 do grupo de dispositivos ao qual a configuração do dispositivo acima foi atribuída anteriormente.

1. Crie um perfil de configuração personalizado do dispositivo baseado em OMA URI e especifique falso para RequireNetworkInOOBE, como mostrado abaixo.
O valor OMA-URI deve ser ./Fornecedor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot de configuração RequerNetworkInOOBE falso via OMA URI em Intune.](images/hololens-tenant-lockdown-false.png)

1. Crie um grupo e atribua o perfil de configuração do dispositivo a esse grupo de dispositivos.

1. Faça o HoloLens 2 membro do dispositivo do grupo criado em sincronização de passo e gatilho anteriores.

Verifique no portal Intune que a configuração do dispositivo foi aplicada com sucesso. Uma vez que esta configuração do dispositivo se aplique com sucesso no dispositivo HoloLens 2, os efeitos do TenantLockdown ficarão inativos.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>O que aconteceria durante o OOBE, se o perfil do Piloto Automático não fosse atribuído a uma HoloLens depois do TenantLockdown ter sido definido como verdadeiro?

A OOBE aguardará indefinidamente o download do perfil do Piloto Automático e será apresentado o diálogo seguinte. Para eliminar os efeitos do TenantLockdown, o dispositivo deve ser matriculado com o seu inquilino original primeiro usando o Autopilot e o RequireNetworkInOOBE deve ser desatado como descrito em passo anterior antes de as restrições introduzidas pelo TenantLockdown CSP serem removidas.

![Vista no dispositivo para quando a política é aplicada no dispositivo.](images/hololens-autopilot-lockdown.png)

#### <a name="why-did-i-not-see-autopilot-experience-even-though-the-autopilot-profile-is-assigned-in-intune"></a>Porque é que não vi a experiência do Piloto Automático, apesar do perfil do Piloto Automático ser atribuído no Intune?

Por predefinição, HoloLens 2 espera 15 segundos para detetar o Autopilot depois de detetar a internet. Se não for detetado nenhum perfil de piloto automático dentro de 15 segundos, isso significa que o Autopilot não foi descoberto corretamente, e verá a página EULA.

Reinicie o seu dispositivo e tente de novo. Para obter mais informações, consulte [Questões e Limitações Conhecidas](hololens2-autopilot.md#known-issues-and-limitations) ou [Resolução de Problemas](hololens2-autopilot.md#troubleshooting).

## <a name="known-issues-and-limitations"></a>Limitações e problemas conhecidos

### <a name="why-do-i-see-0x80180014-during-autopilot"></a>Por que vejo 0x80180014 durante o Piloto Automático?

Este é um erro mostrado durante o processo autopiloto no dispositivo. Esta questão mostrada só se aplica quando um dispositivo HoloLens tiver feito o seguinte:

1. Já passaram pelo Piloto Automático pelo menos uma vez.
1. Está agora a ser reiniciado e reutilizadamente para o Autopilot.

A experiência é que a experiência do Autopilot falhará com um erro específico.

![HoloLens Código de erro de falha do piloto automático](images/autopilot-0x80180014-failure.jpg)

Que medidas devem ser tomadas para resolver este erro?

1. Siga os passos na importação e inscrição do [dispositivo Descodão](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) de Resolução de Problemas para remover o dispositivo do Intune.
1. [Reinicie / Reflash HoloLens](hololens-recovery.md) dispositivo e, em seguida, tente Autopilot.

### <a name="troubleshooting"></a>Resolução de problemas

Os seguintes artigos podem ser um recurso útil para você aprender mais informações e resolver problemas De piloto automático Problemas, no entanto estes artigos são baseados em Windows 10 Desktop e nem todas as informações podem ser aplicadas a HoloLens:

- [Windows Autopilot - questões conhecidas](/mem/autopilot/known-issues)
- [Resolução de problemas Windows problemas de inscrição de dispositivos em Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - Conflitos Políticos](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Feedback e suporte para Autopilot

Para fornecer problemas de feedback ou relatório, utilize um dos seguintes métodos:

- Para obter suporte no registo do dispositivo, contacte o seu revendedor ou distribuidor.
- Para consultas de suporte geral sobre Windows Autopilot, ou para questões como atribuições de perfis, criação de grupo ou controlos do portal MEM, [contacte Microsoft Endpoint Manager suporte](/mem/get-support)  
- Se o seu dispositivo estiver registado no serviço Autopilot e o perfil for atribuído no portal MEM, contacte HoloLens [suporte](/hololens/) (ver cartão 'Suporte'). Abra um bilhete de suporte e, se aplicável, inclua imagens e registos capturando [registos](hololens-diagnostic-logs.md#offline-diagnostics) de diagnóstico offline durante a experiência fora da caixa (OOBE).
- Para reportar um problema a partir do dispositivo, utilize a aplicação Feedback Hub no seu HoloLens. No Feedback Hub, selecione a categoria **dispositivo de gestão**  >   empresarial.
- Para fornecer feedback geral sobre o Autopilot para HoloLens, pode submeter este [inquérito](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Eliminar dispositivos Autopilot

Pode desejar deixar de utilizar um dispositivo para o Autopilot ou registar os seus dispositivos a um inquilino diferente. Se quiser fazê-lo, leia [como eliminar dispositivos Autopilot.](/mem/autopilot/add-devices#delete-autopilot-devices)
