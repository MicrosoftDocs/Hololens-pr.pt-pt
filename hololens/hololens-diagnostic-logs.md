---
title: Recolher e utilizar informações de diagnóstico de dispositivos HoloLens
description: Saiba como recolher, usar e reter informações de diagnóstico a partir de HoloLens dispositivos.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 9/12/2021
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4f62a70430d78087157b3adcdf76af53183db708
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924417"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Recolher e utilizar informações de diagnóstico de dispositivos HoloLens

HoloLens utilizadores e administradores podem escolher entre quatro métodos diferentes para recolher informações de diagnóstico de HoloLens:

- App Feedback Hub
- CSP de Diagnóstico
- Definições app
- Diagnósticos Offline

> [!IMPORTANT]  
> Os registos de diagnóstico do dispositivo contêm informações pessoalmente identificáveis (PII), tais como sobre que processos ou aplicações o utilizador começa durante as operações típicas. Quando vários utilizadores partilham um dispositivo HoloLens (por exemplo, os utilizadores iniciam sessão no mesmo dispositivo utilizando diferentes contas de Microsoft Azure Ative Directory (Azure AD) os registos de diagnóstico podem conter informações pii que se aplicam a vários utilizadores. Para mais informações, consulte a [declaração de Privacidade da Microsoft.](https://privacy.microsoft.com/privacystatement)

A tabela a seguir compara diferentes métodos de recolha. Os nomes do método ligam-se a informações mais detalhadas nas secções que seguem a tabela.

|Método |Pré-requisitos |Localizações dos dados |Acesso e utilização de dados |Retenção de dados |
| --- | --- | --- | --- | --- |
|[Centro de Feedback](#feedback-hub) |Ligação de rede e internet<br /><br />App Feedback Hub<br /><br />Permissão para enviar ficheiros para a nuvem da Microsoft |Nuvem da Microsoft<br /><br />HoloLens dispositivo (opcional) |O utilizador solicita assistência, concorda com os termos de utilização e envia os dados<br /><br />Os colaboradores da Microsoft vêem os dados, de acordo com os termos de utilização |Os dados na nuvem são retidos durante o período definido pela Next Generation Privacy (NGP). Em seguida, os dados são eliminados automaticamente.<br /><br />Os dados sobre o dispositivo podem ser eliminados a qualquer momento por um utilizador que tenha permissões **do proprietário do Dispositivo** ou do **Administrador.** |
|[Definições Resolução de problemas](#settings-troubleshooter) |Definições app |HoloLens dispositivo<br /><br />Computador conectado (opcional) |O utilizador armazena os dados e apenas o utilizador acede aos dados (a menos que o utilizador partilhe especificamente os dados com outro utilizador). |Os dados são retidos no dispositivo até que o utilizador os elimine.* |
|[CSP de Diagnóstico](#diagnosticlog-csp) |Ligação de rede<br /><br />Ambiente MDM que suporta o CSP do DiagnosticLog |Administrador configura locais de armazenamento |No ambiente gerido, o utilizador consente implicitamente no acesso do administrador aos dados.<br /><br />O administrador configura funções e permissões de acesso. | Os dados são retidos no armazenamento em nuvem e o administrador configura a política de retenção. |
|[Diagnósticos offline](#offline-diagnostics) |Configuração do dispositivo:<ul><li>Ligado e ligado ao computador</li><li>Botões de potência e volume funcionando</li></ul> |HoloLens dispositivo<br /><br />Computador conectado |O utilizador armazena os dados e apenas o utilizador acede aos dados (a menos que o utilizador partilhe especificamente os dados com outro utilizador). |Os dados são retidos no dispositivo até que o utilizador os elimine. |

* O utilizador final é responsável por partilhar os registos de forma responsável com outra pessoa. Estes ficheiros são essencialmente úteis quando contactam o serviço de apoio e suporte ao cliente.  

## <a name="feedback-hub"></a>Centro de Feedback

Um utilizador HoloLens pode utilizar a aplicação de desktop do Microsoft Feedback Hub para enviar informações de diagnóstico para o Microsoft Support. Para mais detalhes e instruções completas, consulte [Dar-nos feedback](hololens-feedback.md).  

> [!NOTE]  
> **Utilizadores comerciais ou empresariais:** Se utilizar a aplicação Feedback Hub para reportar um problema relacionado com MDM, provisionamento ou qualquer outro aspeto de gestão de dispositivos, altere a categoria de aplicação para a categoria de Dispositivo **de Gestão**  >  **Empresarial**.

>[!IMPORTANT]
> Para fornecer os melhores dados possíveis para corrigir problemas, recomendamos vivamente que deite o seu dispositivo de telemetria para **Opcional**. Pode definir este valor durante a Experiência Out-of-Box (OOBE), ou utilizando a aplicação **Definições.** Para isso, utilizando Definições, selecione **Iniciar > Definições > Privacidade > App Diagnostics > On**.

### <a name="prerequisites"></a>Pré-requisitos

- O dispositivo está ligado a uma rede.
- A aplicação Feedback Hub está disponível no computador de secretária do utilizador e o utilizador pode enviar ficheiros para a nuvem da Microsoft.

### <a name="data-locations-access-and-retention"></a>Localizações de dados, acesso e retenção

Ao concordar com os termos de utilização do Feedback Hub, o utilizador consente explicitamente no armazenamento e utilização dos dados (conforme definido por esse acordo).

O Feedback Hub fornece dois locais para o utilizador armazenar informações de diagnóstico:

- **A nuvem microsoft**. Os dados que o utilizador envia utilizando a aplicação Feedback Hub são armazenados para o número de dias que é consistente com os requisitos de Privacidade da Próxima Geração (NGP). Os colaboradores da Microsoft podem usar um espectador compatível com NGP para aceder à informação durante este período.

   > [!NOTE]  
   > Estes requisitos aplicam-se aos dados em todas as categorias do Feedback Hub.

- **O dispositivo HoloLens.** Ao apresentar um relatório no Feedback Hub, o utilizador pode selecionar **Guardar uma cópia local de diagnósticos e anexos criados ao dar feedback**. Se o utilizador selecionar esta opção, o Feedback Hub armazena uma cópia da informação de diagnóstico no dispositivo HoloLens. Esta informação permanece acessível ao utilizador (ou a qualquer pessoa que utilize essa conta para iniciar scontabilidade para HoloLens). Para eliminar estas informações, um utilizador deve ter permissões **do proprietário do Dispositivo** ou da **Administração** no dispositivo. Um utilizador que tenha as permissões adequadas pode iniciar sessão no Feedback Hub, selecione **Definições**  >  **Ver registos de diagnóstico** e eliminar as informações.

## <a name="settings-troubleshooter"></a>Definições Resolução de problemas

Um utilizador HoloLens pode utilizar a aplicação **Definições** no dispositivo para resolver problemas e recolher informações de diagnóstico. Para tal, siga estes passos:

1. Abra a aplicação Definições e selecione a página **'Atualizar &**  >  **resolução de problemas de** segurança'.
1. Selecione a área apropriada e **selecione Iniciar**.
1. Reproduza o problema.
1. Depois de reproduzir o problema, volte a Definições e, em seguida, **selecione Stop**.

Um utilizador também pode configurar o comportamento do Fallback Diagnostics a partir da aplicação **Definições.** Navegue para a página **de resolução de problemas privacy->** para configurar esta definição.
> [!NOTE]
> Se houver uma política de MDM configurada para o dispositivo, o utilizador não poderá anular esse comportamento.

### <a name="os-update-troubleshooter"></a>Resolução de problemas do OS Update

Nas construções [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e em diante:
- Além dos anteriores problemas dentro da aplicação Definições, foi adicionada uma nova resolução de problemas com a adição da nova app Definições para atualizações do OS. Navegue para **Definições -> Update & Security -> Troubleshoot -> Windows Update** e selecione **Start**. Isto permite-lhe recolher vestígios enquanto reproduz o seu problema com as Atualizações de OS para ajudar melhor na resolução de problemas com o seu TI ou suporte.

### <a name="prerequisites"></a>Pré-requisitos

- A  Definições aplicação está instalada no dispositivo e está disponível para o utilizador.

### <a name="data-locations-access-and-retention"></a>Localizações de dados, acesso e retenção

Como o utilizador inicia a recolha de dados, o utilizador consente implicitamente no armazenamento da informação de diagnóstico. Apenas o utilizador, ou qualquer pessoa com quem o utilizador partilhe os dados, pode aceder aos dados.

A informação de diagnóstico é armazenada no dispositivo. Se o dispositivo estiver ligado ao computador do utilizador, a informação também reside no computador no seguinte ficheiro:

> Este pc \\ \<*HoloLens device name*> \\ Armazenamento \\ documentos \\ trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> Neste caminho e nome do ficheiro, \<*HoloLens device name*> representa o nome do dispositivo HoloLens, e representa a data e a hora em que o ficheiro foi \<*ddmmyyhhmmss*> criado.

A informação de diagnóstico permanece nestes locais até que o utilizador a elimine.

### <a name="view-diagnostic-report"></a>Ver relatório de diagnóstico

Para ver os Diagnósticos DO MDM no HoloLens 2, selecione o seu ícone WiFi e, em seguida, navegue para **Definições**  ->  **Contas**  >  **Access ou escola** e selecione Export your management **logs**. HoloLens envia os ficheiros de registo para a sua conta e exibe a sua localização no seu pc de secretária.

## <a name="diagnosticlog-csp"></a>CSP de Diagnóstico

Num ambiente de Gestão de Dispositivos Móveis (MDM), o administrador de TI pode utilizar o [fornecedor de serviços de configuração DiagnosticLog (CSP)](/windows/client-management/mdm/diagnosticlog-csp) para configurar definições de diagnóstico em dispositivos HoloLens matriculados. O administrador de TI pode configurar estas definições para recolher registos de dispositivos matriculados.

Veja mais:
- [Recolher diagnósticos de um dispositivo de Windows](/mem/intune/remote-actions/collect-diagnostics)
- [Pré-visualização pública intune - diagnósticos de dispositivos de Windows 10](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Pré-requisitos

- O dispositivo está ligado a uma rede.
- O dispositivo está matriculado num ambiente MDM que suporta o CSP do DiagnosticLog.

### <a name="data-locations-access-and-retention"></a>Localizações de dados, acesso e retenção

Como o dispositivo faz parte do ambiente gerido, o utilizador consente implicitamente no acesso administrativo à informação de diagnóstico.

O administrador de TI utiliza o CSP do DiagnosticLog para configurar as políticas de armazenamento, retenção e acesso de dados, incluindo as políticas que regem as seguintes:

- A infraestrutura em nuvem que armazena a informação de diagnóstico.
- O período de retenção para a informação de diagnóstico.
- Permissões que controlam o acesso à informação de diagnóstico.

## <a name="offline-diagnostics"></a>Diagnósticos offline

Em situações em que o dispositivo não é capaz de recolher diagnósticos através do Feedback Hub ou do Definições Troubleshooter, pode recolher diagnósticos manualmente. Um dos cenários em que isso é necessário é quando o dispositivo não consegue ligar-se a Wi-Fi ou não pode aceder a outros métodos acima mencionados. Os diagnósticos recolhem depósitos e registos de falhas do dispositivo que ajudam um engenheiro de suporte da Microsoft a isolar problemas.

Isto funciona quando o dispositivo aparece no File Explorer depois de o ligar a um PC através de um cabo USB.

> [!NOTE]
> A geração e gestão de diagnóstico offline é controlada de forma diferente dependendo da sua versão OS. Anteriormente era controlado pela definição de telemetria, mas agora é controlado diretamente através da política de MDM. Se for desativado através da definição ou da política DEDM, os registos de diagnóstico não podem ser recolhidos utilizando este mecanismo.

Comportamento antes [de Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2):
 - Os diagnósticos offline só são ativados quando o utilizador está a passar pelo OOBE ou [pelo System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) value é definido como Full (O valor básico é o valor predefinido no HoloLens). 
- Para desativar os diagnósticos offline, vá à **página de privacidade > Definições App e** selecione **Basic** in **Diagnostic Data**. Nas construções em que os diagnósticos offline dependem da definição de telemetria, só impacta se os registos são recolhidos ou não. Não afeta os ficheiros recolhidos.
- Se o dispositivo estiver bloqueado, os registos não aparecerão.

Nas construções [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) e em diante:
- Quando os diagnósticos de retorno de outono estiverem ativados serão controlados por uma política específica de MDM com a definição correspondente [De Realidade Mista/Falómagósticos de Retorno](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Se o dispositivo estiver bloqueado, os registos não aparecerão.

Veja este vídeo para saber mais.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Siga estes passos para recolher diagnósticos:

1.  Ligação o dispositivo com um cabo USB para o seu PC.

2.  No File Explorer no seu PC, navegue para **'This PC \<hololens-device> \Internal Armazenamento'.**

3.  Se a pasta **de Armazenamento Interna** não aparecer, o dispositivo aguarda a inscrição de um utilizador. Ou iniciar sôm ou ligar o aparelho premindo o botão POWER durante 10 segundos.

4.  Prima e solte imediatamente os botões **Power + Volume Down** juntos.

5.  Aguarde um minuto para que o dispositivo prepare os arquivos de zíper. (Um ficheiro temporário chamado HololensDiagnostics.temp pode tornar-se visível enquanto o dispositivo gera os arquivos zip. Não aceda nem guarde o ficheiro. Quando o processo terminar, será substituído pelos arquivos zip.)

6.  Asse o explorador de ficheiros e navegue para a pasta **'\Documentos'.**

7.  Copie os ficheiros ZIP de diagnóstico e partilhe-os com a equipa de suporte da Microsoft.

> [!NOTE]
> Alguns dos ficheiros ZIP de diagnóstico podem conter PII.

### <a name="offline-diagnostics-notifications"></a>Notificações de Diagnóstico Offline

- Introduzida em [Windows Holographic, versão 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

Esta é uma atualização para uma funcionalidade existente chamada [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics). Anteriormente, não havia um indicador claro para os utilizadores de que tinham desencadeado a recolha de diagnóstico ou que tinham concluído.
Agora adicionado em Windows builds Insider, existem duas formas de feedback audiovisual para diagnósticos offline. A primeira a ser torras notificações exibidas para ambos quando a recolha começa e completa. Estes serão apresentados quando o utilizador iniciar sessão e tiver visuais.

![Torrada para recolher troncos.](./images/logcollection1.jpg)

![Torradas quando a recolha de registos estiver completa.](./images/logcollection2.jpg)

Como os utilizadores usam frequentemente o Offline Diagnostics como um mecanismo de recolha de registos de recuo para quando não têm acesso a um ecrã, não podem fazer login ou ainda estão no OOBE, haverá também uma sugestão de áudio reproduzida quando os registos são recolhidos. Este som será reproduzido para além da notificação de torradas.

Esta nova funcionalidade será ativada quando o seu dispositivo atualizar, e não necessita de ser ativado ou gerido. Em qualquer caso que este novo feedback não possa ser exibido ou ouvido, o Offline Diagnostics continuará a ser gerado.

Esperamos que com esta mais recente adição de feedback audiovisual seja mais fácil recolher dados de diagnóstico e, mais rapidamente, ser capaz de resolver os seus problemas.

### <a name="low-storage-log-collection-improvements"></a>Melhorias na recolha de registos de baixo armazenamento

- Introduzida em [Windows Holographic, versão 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

Em cenários em que um dispositivo parece estar com pouco espaço no disco quando são recolhidos registos de diagnóstico, será criado um relatório adicional chamado **StorageDiagnostics.zip.** O limiar de armazenamento baixo é determinado automaticamente por Windows [sentido de armazenamento](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48).

## <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Ver relatório de diagnóstico avançado em Definições sobre HoloLens

- Introduzida em [Windows Holographic, versão 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

Para dispositivos geridos ao resolver o comportamento, confirmar que uma configuração de política esperada é aplicada é um passo importante. Anteriormente a esta nova funcionalidade, esta tinha de ser feita fora do dispositivo através do MDM ou perto do dispositivo depois de exportar registos de diagnóstico do MDM recolhidos através **de Definições**  ->  **Contas** Access  >  **ou escola**, e selecione **Exporte os seus registos de gestão** e seja visualizado num PC próximo.

Agora o DIAGNÓSTICO MDM pode ser visto no dispositivo usando o navegador Edge. Para ver mais facilmente o relatório de diagnóstico do MDM, navegue para a página de Access work ou school, e **selecione Ver relatório de diagnóstico avançado**. Isto irá gerar e abrir o relatório numa nova janela Edge.

![Consulte o relatório de diagnóstico avançado na aplicação Definições.](./images/view-advanced-diagnostic-report.jpg)
