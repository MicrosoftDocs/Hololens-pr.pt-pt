---
title: Pré-visualização insider para Microsoft HoloLens
description: Saiba como começar com as construções insider e forneça feedback valioso para a nossa próxima grande atualização do sistema operativo para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378606"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Pré-visualização insider para Microsoft HoloLens

Bem-vindos às mais recentes construções insider preview para HoloLens! É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer feedback valioso para a nossa próxima grande atualização do sistema operativo para holoLens.

## <a name="windows-insider-release-notes"></a>Notas de lançamento do Windows Insider

Estamos entusiasmados por voltar a voar novas funcionalidades para o Windows Insiders. Novas construções serão voadas para os Canais Dev e Beta para as últimas atualizações. Continuaremos a atualizar esta página à medida que adicionamos mais funcionalidades e atualizações às nossas construções do Windows Insider. Fique animado e pronto para misturar estas atualizações na sua realidade. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive para trabalho ou escola Camera Roll upload

*Introduzido na construção 20346.1402*

Adicionámos uma nova funcionalidade à aplicação HoloLens 2 Settings, que permite aos clientes carregarem automaticamente fotos e vídeos de realidade mista a partir da pasta Pictures > Camera Roll do dispositivo para o OneDrive correspondente para trabalho ou pasta escolar. Esta funcionalidade aborda uma [lacuna de funcionalidades dentro da aplicação OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) no HoloLens 2, que suporta apenas o upload automático do Camera Roll para a conta pessoal da Microsoft (e não para o seu trabalho ou conta escolar).

**Como funciona**

- Visite **Definições > Sistema > Câmara de Realidade Mista** para permitir o "upload da câmara".
- Ao definir esta função para a posição **On,** quaisquer fotografias ou vídeos de realidade mista capturados no seu dispositivo serão automaticamente enviados para o upload para a pasta De rolo de câmara > imagens do seu OneDrive para trabalho ou conta escolar.
    >[!NOTE]
    >As fotos e vídeos capturados antes de ativar esta funcionalidade *não serão* enviados para upload e ainda terão de ser carregados manualmente.
- Uma mensagem de estado na página Definições mostrará o número de ficheiros pendentes de upload (ou lerá "OneDrive está atualizado" quando todos os ficheiros pendentes tiverem sido carregados).
- Se estiver preocupado com a largura de banda ou quiser "fazer uma pausa" no upload por qualquer motivo, pode mudar a função para a posição **Off.** Desativar temporariamente a funcionalidade garante que a fila de upload continuará a aumentar à medida que adiciona novos ficheiros à pasta Do Rolo da Câmara, mas os ficheiros não serão carregados até que volte a ativar a funcionalidade.
- Os ficheiros mais recentes serão carregados primeiro (o último a entrar, o primeiro a sair).
- Se a sua conta OneDrive tiver problemas (por exemplo, após a alteração da palavra-passe), aparecerá na página 'Definições' um botão **'Corrigir'.**
- Não existe o tamanho máximo do ficheiro, mas note que os ficheiros grandes demorarão mais tempo a ser carregados (especialmente se a largura de banda do upload estiver limitada). Se "parar" ou desligar o upload enquanto um ficheiro grande está a ser carregado, ele cancelará imediatamente o upload. O upload recomeçará quando voltar a ativar a funcionalidade; não perderá nenhum ficheiro, mas o upload parcial será descartado.

**Questões e ressalvas conhecidas**

- Esta definição não tem nenhuma configuração construída em estrangulamento com base no uso atual da largura de banda. Se precisar de maximizar a largura de banda para outro cenário, desligue a definição manualmente. O upload será interrompido, mas a funcionalidade continuará a monitorizar ficheiros recém-adicionados para o Camera Roll. Re-activar o upload quando estiver pronto para continuar.
- Esta funcionalidade deve ser ativada para cada conta de utilizador no dispositivo, e apenas pode fazer upload de ficheiros para o utilizador que se encontra atualmente inscrito no dispositivo.
- Se estiver a tirar fotografias ou vídeos enquanto vê a contagem de upload na página Definições em tempo real, note que a contagem de ficheiros pendentes pode não ser alterada até que o ficheiro atual tenha concluído o upload.
- O upload fará uma pausa se o seu dispositivo adormecer ou estiver desligado. Para garantir que os uploads pendentes estão completos, utilize ativamente o dispositivo até que a página Definições leia "OneDrive está atualizado" ou ajuste as definições **de & de alimentação.**

## <a name="start-receiving-insider-builds"></a>Comece a receber construções insider
> [!NOTE]
> Se ainda não foi atualizado recentemente, por favor reinicie o seu dispositivo para atualizar o estado e obter a mais recente construção.
> - O comando de voz "Reboot device" funciona bem. 
> - Também pode escolher o botão de reinício em Definições/Programa Insider do Windows.
>
> Tivemos uma escuta na parte de trás que podes ter encontrado e isto vai pôr-te de volta aos trilhos.

Num dispositivo HoloLens 2 aceda a **Definições**  >  **Atualizar & Programa de Segurança** Do Windows  >  **Insider** e **selecione Iniciar**. Ligue a conta que usou para registar como Um Insider do Windows.
O insider do Windows está agora a mudar-se para os Canais. O anel **Rápido** tornar-se-á o **Canal Dev**, o anel **Lento** passará a ser o **Canal Beta**, e o anel **de pré-visualização** de lançamento tornar-se-á o **Canal de Pré-visualização de Lançamento**. Eis o que esse mapeamento parece: ![ explicação dos canais Insider do Windows ](images/WindowsInsiderChannels.png) Para obter mais informações, consulte [a introdução dos canais Insider do Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nos blogs do Windows.
Em seguida, selecione **Ative development of Windows**, escolha se gostaria de receber construções de **Dev Channel** ou Beta **Channel** e reveja os termos do programa.
**Selecione Confirm > Reinicie agora** para terminar. Depois de o seu dispositivo ter sido reiniciado, vá a **Definições > Atualizar & Segurança > Verifique se há atualizações** para obter a mais recente construção.
### <a name="update-error-0x80070490-work-around"></a>Atualizar erro 0x80070490 trabalho
Se encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, experimente o seguinte trabalho de curto prazo. Envolve mover o seu canal de insider, pegar na atualização e, em seguida, mover o seu canal Insider de volta.
#### <a name="stage-one---release-preview"></a>Fase um - Visualização de lançamento
1.  Definições, Atualizar & Segurança, Programa De Insider do Windows, selecione **Release Preview Channel**.
2.  Definições, Atualizar & Segurança, Atualização do Windows, **Verificar atualizações**. Depois da atualização, continue para a fase dois.
#### <a name="stage-two---dev-channel"></a>Fase dois - Canal Dev
1. Definições, Atualizar & Segurança, Programa De Insider do Windows, selecione **Dev Channel**.
2. Definições, Atualizar & Segurança, Atualização do Windows, **Verificar atualizações**.
## <a name="ffu-download-and-flash-directions"></a>Direções de descarregamento e flash da FFU
Para testar com um voo assinado ffu, primeiro tem de voar desbloqueando o seu dispositivo antes de piscar o voo assinado ffu.
1. No PC:
    1. Faça o download para o seu PC a partir de [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale o ARC (Advanced Recovery Companion) a partir da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. No HoloLens - Desbloqueio de voo: Atualização de **definições abertas**  >  **& Programa de Segurança** Do Windows  >  **Insider,** em seguida, inscreva-se, reinicie o dispositivo.
1. Flash FFU - Agora pode piscar o voo assinado FFU usando ARC.
### <a name="provide-feedback-and-report-issues"></a>Fornecer problemas de feedback e relatório
Por favor, use [a aplicação Feedback Hub](hololens-feedback.md) nos seus HoloLens para fornecer problemas de feedback e relatório. A utilização do Feedback Hub garante que todas as informações necessárias de diagnóstico estão incluídas para ajudar os nossos engenheiros a depurar e resolver rapidamente o problema.  Os problemas com a versão chinesa e japonesa dos HoloLens devem ser relatados da mesma forma.
> [!NOTE]
> Não se esqueça de aceitar a solicitação que pergunta se pretende que o Feedback Hub aceda à pasta Documentos (selecione **Sim** quando solicitado).
## <a name="note-for-developers"></a>Nota para desenvolvedores
É bem-vindo e encorajado a tentar desenvolver as suas aplicações usando as construções Insider da HoloLens.  Consulte a [Documentação do Desenvolvedor holoLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar. As mesmas instruções funcionam com as construções insider dos HoloLens.  Pode utilizar as mesmas construções de Unidade e Estúdio Visual que já está a usar para o desenvolvimento do HoloLens.
## <a name="stop-receiving-insider-builds"></a>Pare de receber builds Insider
Se já não pretender receber as construções insider do Windows Holographic, pode optar por sair quando os hololes estiverem a executar uma produção, ou pode recuperar o [seu dispositivo](hololens-recovery.md) utilizando o Advanced Recovery Companion para recuperar o seu dispositivo para uma versão não-Insider do Windows Holographic.
> [!CAUTION]
> Existe um problema conhecido em que os utilizadores que não se matriculam no Insider Preview constroem depois de reinstalarem manualmente uma nova construção de pré-visualização experimentariam um ecrã azul. Depois, devem recuperar manualmente o seu dispositivo. Para mais detalhes sobre se você seria impactado ou não, por favor, veja mais sobre esta [Edição Conhecida.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)
Para verificar se os seus HoloLens estão a executar uma construção de produção:
1. Vá a **Definições > System > Sobre**, e encontre o número de construção.
1. [Consulte as notas de lançamento para os números de construção de produção](hololens-release-notes.md).
Para excluir as construções insider:
1. Num HoloLens que executa uma construção de produção, vá a **Definições > Atualização & Security > Programa Do Windows Insider**, e selecione **builds Stop Insider**.
1. Siga as instruções para desativar o seu dispositivo.
