---
title: Questões conhecidas para HoloLens (1ª Gen)
description: Mantenha-se atualizado com a nossa lista de problemas e soluções alternativas conhecidas que podem afetar clientes e desenvolvedores hololens usando a Unidade e o Portal do Dispositivo Windows.
keywords: resolução de problemas, questão conhecida, ajuda
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923555"
---
# <a name="known-issues-for-hololens-1st-gen"></a>Questões conhecidas para HoloLens (1ª Gen)

Aqui está a lista atual de problemas conhecidos para dispositivos HoloLens. Verifique aqui primeiro se está a ver um comportamento estranho. Esta lista será mantida atualizada à medida que novos problemas forem descobertos ou relatados, ou como os problemas são abordados em futuras atualizações de software HoloLens.

>[!NOTE]
> - Se descobrir um problema que não esteja a bloquear, por favor, reporte-o no seu dispositivo HoloLens via [Feedback Hub](hololens-feedback.md).
> - Se o problema que está a enfrentar estiver a bloqueá-lo, para além de apresentar feedback, por favor [apresente um pedido de apoio](https://aka.ms/hlsupport).


- [Questões conhecidas para todas as gerações HoloLens](#known-issues-for-all-hololens-generations)
- [Questões conhecidas para HoloLens (1ª Gen)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Questões conhecidas para todas as gerações HoloLens

### <a name="unity"></a>Unity

- Consulte [instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para a versão mais atualizada da Unidade recomendada para o desenvolvimento do HoloLens.
- Os problemas conhecidos com a Pré-visualização técnica da Unidade HoloLens estão documentados nos [fóruns hololelens da Unidade.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Portal do Dispositivo Windows

- A funcionalidade de visualização ao vivo na captura de Realidade Mista pode apresentar vários segundos de latência.

- Na página Entrada Virtual, os controlos Gesture e Scroll na secção Gestos Virtuais não estão funcionais. Usá-los não terá efeito. O teclado virtual na página de entrada virtual funciona corretamente.

- Depois de ativar o modo de desenvolvimento em Definições, pode demorar alguns segundos até que o interruptor ligue o Portal do Dispositivo.

### <a name="onedrive-camera-upload"></a>Upload de câmara OneDrive

A aplicação OneDrive para HoloLens não suporta o upload automático de câmaras para trabalho ou contas escolares.

Soluções alternativas:

- Se for viável para o seu negócio, o upload automático de câmaras é suportado nas contas da Microsoft do consumidor. Pode iniciar sôms na sua conta Microsoft para além do seu trabalho ou conta escolar (a aplicação OneDrive suporta o duplo s-in). A partir do seu perfil de conta Microsoft dentro do OneDrive pode ativar o upload automático do rolo de câmara de fundo.

- Se não conseguir utilizar com segurança uma conta de consumidor da Microsoft para o upload das suas fotos automaticamente, pode enviar manualmente fotografias para o seu trabalho ou conta escolar a partir da aplicação OneDrive. Para isso, certifique-se de que está inscrito no seu trabalho ou na conta escolar na aplicação OneDrive. Selecione o **+** botão e escolha **Upload**. Encontre as fotos ou vídeos que pretende fazer o upload navegando para **o Pictures > Camera Roll**. Selecione as fotos ou vídeos que pretende carregar e, em seguida, selecione o botão **Abrir.**

## <a name="known-issues-for-hololens-1st-gen"></a>Questões conhecidas para HoloLens (1ª Gen)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Incapaz de ligar e implementar para HoloLens através do Visual Studio

> [!NOTE]
> Última Atualização: 8/8 @ 5:11PM - O Visual Studio lançou a versão 16.2 do VS 2019, que inclui uma correção para este problema. Recomendamos a atualização para esta versão mais recente para evitar este erro.

O Visual Studio lançou a versão 16.2 do VS 2019, que inclui uma correção para este problema. Recomendamos a atualização para esta versão mais recente para evitar este erro.

Causa raiz de problema: Os utilizadores que utilizaram o Visual Studio 2015 ou os lançamentos antecipados do Visual Studio 2017 para implementar e depurar aplicações nos seus HoloLens e posteriormente utilizaram as versões mais recentes do Visual Studio 2017 ou do Visual Studio 2019 com os mesmos HoloLens serão afetados. Os mais recentes lançamentos do Visual Studio implementam uma nova versão de um componente, mas os ficheiros da versão mais antiga são deixados no dispositivo, fazendo com que a versão mais recente falhe.  Isto causa a seguinte mensagem de erro: DEP0100: Certifique-se de que o dispositivo-alvo tem o modo de desenvolvimento ativado. Não foi possível obter uma licença de programador \<ip\> devido ao erro 80004005.

#### <a name="workaround"></a>Solução

A nossa equipa está neste momento a trabalhar numa correção. Entretanto, pode utilizar os seguintes passos para contornar o problema e ajudar a desbloquear a implementação e a depuração:  

1. Abra o Visual Studio.

1. Selecione **o**  >  **novo**  >  **projeto de arquivo**.

1. Selecione **Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework)**.

1. Dê ao projeto um nome (como "HoloLensDeploymentFix") e certifique-se de que o Quadro está definido para pelo menos .NET Framework 4.5, em seguida, Selecione **OK**.

1. Clique com o botão de **referência** no Solution Explorer e adicione as seguintes referências (selecione para a secção **procurar** e selecione **Procurar):**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Se não tiver 10.0.18362.0 instalados, use a versão mais recente que tem.

1. Clique com o botão direito no projeto no Solution Explorer e **selecione Adicionar** O  >  **Item Existente.**

1. Navegue para C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 e mude o filtro para **Todos os Ficheiros \* \* (. )**.

1. Selecione SirepClient.dll e SshClient.dll e Selecione **Add**.

1. Localizar e selecionar ambos os ficheiros no Solution Explorer (devem estar na parte inferior da lista de ficheiros) e alterar **copy to Output Directory** na janela **Propriedades** para **Copiar sempre**.

1. No topo do ficheiro, adicione o seguinte à lista de `using` declarações existente:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. No interior de `static void Main(...)` , adicione o seguinte código:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Selecione **a**  >  **solução build build**.

1. Abra uma janela de pedido de comando e um cd na pasta que contém o ficheiro .exe compilado (por exemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Execute o executável e forneça o endereço IP do dispositivo como argumento de linha de comando. (Se estiver ligado através de USB, pode utilizar 127.0.0.1, caso contrário utilize o endereço IP Wi-Fi do dispositivo.)  Por exemplo, "HoloLensDeploymentFix 127.0.0.1".

1. Depois de a ferramenta ter saído sem mensagens (isto deve demorar apenas alguns segundos), poderá agora ser capaz de implementar e depurar do Visual Studio 2017 ou mais recente.  Não é necessária uma utilização continuada da ferramenta.

Forneceremos novas atualizações à medida que forem disponibilizadas.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problemas no lançamento da Microsoft Store e aplicações em HoloLens

> [!NOTE]
> Última Atualização: 4/2 @ 10 AM - Emissão resolvida.

Pode experimentar problemas ao tentar lançar a Microsoft Store e aplicações em HoloLens. Determinámos que o problema ocorre quando as atualizações de aplicações de fundo implementam uma versão mais recente de pacotes-quadro em sequências específicas, enquanto uma ou mais das suas aplicações dependentes ainda estão em execução. Neste caso, uma atualização automática de aplicações entregou uma nova versão do .NET Native Framework (versão 10.0.25531 a 10.0.27413) fez com que as aplicações que estão em execução não atualizassem corretamente todas as aplicações em execução que consumissem a versão anterior do quadro.  O fluxo para a atualização do quadro é o seguinte:

1. O novo pacote-quadro é descarregado da loja e instalado.

1. Todas as aplicações que utilizam a estrutura mais antiga são 'atualizadas' para utilizar a versão mais recente.

Se o passo 2 for interrompido antes de ser concluído, então quaisquer aplicações para as quais o quadro mais recente não foi registado não serão lançadas a partir do menu inicial.  Acreditamos que qualquer aplicação no HoloLens pode ser afetada por este problema.

Alguns utilizadores relataram que fechar apps penduradas e lançar outras apps como Feedback Hub, 3D Viewer ou Photos resolve o problema para as mesmas - no entanto, isso não funciona a 100% das vezes.

Temos causado raízes que este problema não foi causado a atualização em si, mas um bug no SO que resultou na atualização de quadro .NET Native sendo manuseada incorretamente. Temos o prazer de anunciar que identificamos uma correção e lançámos uma atualização (versão OS 17763.380) contendo a correção.  

Para ver se o seu dispositivo pode receber a atualização:

1. Vá à aplicação Definições e abra **a atualização & Segurança**.

1. Selecione **Verificar se há atualizações**.

1. Se estiver disponível uma atualização para 17763.380, por favor atualize esta construção para receber a correção para o bug Do Hang da App.

1. Ao atualizar para esta versão do SISTEMA, as Apps devem funcionar como esperado.

Além disso, como fazemos com todas as versões hololensOS, publicámos a imagem FFU no [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).

Caso não queira receber a atualização, lançámos uma nova versão da aplicação UWP da Microsoft Store a partir de 3/29. Depois de ter a versão atualizada da Loja:

1. Abra a Loja e confirme que está carregada.
1. Use o gesto de flor para abrir o menu.
1. Tente abrir aplicações previamente quebradas.
1. Se ainda não puder ser lançado, toque e segure o ícone da aplicação partida e selecione desinstalar.
1. Reinstalar estas aplicações a partir da loja.

Se o seu dispositivo ainda não conseguir carregar aplicações, pode carregar lateralmente uma versão do .NET Native Framework e Runtime através do centro de descarregamento seguindo estes passos:

1. Por favor, descarregue [este ficheiro zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) do Microsoft Download Center. Desapertar produzirá dois ficheiros.  Microsoft.NET.Native.Runtime.1.7.appx e Microsoft.NET.Native.Framework.1.7.appx.

1. Verifique se o seu dispositivo está desbloqueado.  Se nunca o fez antes, consulte [a utilização do Portal do Dispositivo do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para obter instruções.

1. Em seguida, pretende entrar no Portal do Dispositivo Windows. A nossa recomendação é fazê-lo através de USB e você faria isso digitando http://127.0.0.1:10080 no seu navegador.

1. Depois de ter o Portal do Dispositivo do Windows em cima, precisamos que "carregue lateralmente" os dois ficheiros que descarregou. Para isso, é necessário descer pela barra lateral esquerda até chegar à secção **Apps** e selecionar **Apps**.

1. Em seguida, verá um ecrã semelhante ao abaixo.  Você quer ir para a secção que diz **Instalar App** e navegar para onde você abriu os dois ficheiros APPX. Só é possível fazer um de cada vez, por isso, depois de selecionar o primeiro, clique em "Go" na secção 'Implementar'. Em seguida, faça isto para o segundo ficheiro APPX.

   ![Portal do Dispositivo Windows para instalar Side-Loaded app](images/20190322-DevicePortal.png)

1. Neste momento acreditamos que as suas aplicações devem começar a funcionar novamente e que também pode chegar à Loja.

1. Em alguns casos, é necessário executar o passo adicional de lançar a app 3D Viewer antes do lançamento das aplicações afetadas.

Agradecemos a sua paciência à medida que passamos pelo processo para resolver esta questão, e estamos ansiosos por continuar a trabalhar com a nossa comunidade para criar experiências de realidade mista bem sucedidas.

### <a name="device-update"></a>Atualização do Dispositivo

- 30 segundos depois de uma nova atualização, a concha pode desaparecer uma vez. Por favor, execute o gesto **de florescimento** para retomar a sua sessão.

### <a name="visual-studio"></a>Visual Studio

- Consulte [instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Visual Studio que é recomendada para o desenvolvimento do HoloLens.

- Ao implementar uma aplicação do Visual Studio para os seus HoloLens, poderá ver o erro: **A operação solicitada não pode ser executada num ficheiro com uma secção mapeada pelo utilizador aberta. (Exceção da HRESULT: 0x800704C8)**. Se isto acontecer, tente de novo e a sua implantação será geralmente bem sucedida.

### <a name="api"></a>API

- Se a aplicação definir o [ponto de focagem](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) atrás do utilizador ou o normal para camera.forward, os hologramas não aparecerão em fotos ou vídeos de Captura de Realidade Mista. Até que este bug seja corrigido no Windows, se as aplicações definirem ativamente o [ponto de focagem,](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) devem garantir que o plano normal está definido em frente à câmara para a frente (por exemplo, normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Controlador Sem Fios Xbox

- O Controlador Sem Fios Xbox S tem de ser atualizado antes de poder ser utilizado com HoloLens. Certifique-se de que está [atualizado](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) antes de tentar emparelhar o seu controlador com um HoloLens.

- Se reiniciar os HoloLens enquanto o Controlador Sem Fios Xbox estiver ligado, o controlador não voltará a ligar-se automaticamente aos HoloLens. A luz do botão Guia piscará lentamente até que o controlador desligue após 3 minutos. Para voltar a ligar o controlador imediatamente, desligue o controlador premindo o botão Guia até que a luz se api.00. Quando voltar a ligar o controlador, voltará a ligar-se aos HoloLens.

- Se os holoLens entrarem em espera enquanto o Controlador Sem Fios Xbox estiver ligado, qualquer entrada no controlador acordará os HoloLens. Pode evitar isto desligando o seu controlador quando terminar de o utilizar.

