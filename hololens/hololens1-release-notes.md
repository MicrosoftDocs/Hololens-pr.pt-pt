---
title: HoloLens notas de lançamento da 1ª (gen)
description: Saiba mais sobre as atualizações em cada novo lançamento HoloLens.
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
- HoloLens 1
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033638"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens notas de lançamento da 1ª (gen)

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1ª gen) Manutenção a longo prazo
HoloLens (1º género) entrou no estado de Manutenção de Longo Prazo (LTS). As futuras atualizações centrar-se-ão nas correções de problemas e segurança, mantendo a paridade de funcionalidades com o Windows 10 Holographic, versão 1809 para HoloLens (1ª geração).

Para os desenvolvedores, isto significa que HoloLens aplicações (1ª geração) não suportam a API OpenXR.  Estes auscultadores continuam suportados na Unity 2019 LTS com o backend winrt API para o ciclo de vida completo da Unity 2019 LTS até meados de 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, versão 1809

> **Aplica-se a:** HoloLens (1ª geração)

| Funcionalidade | Detalhes |
|---|---|
| **Menu de ações rápidas** | Quando estiver numa aplicação, o gesto Bloom irá agora abrir um menu de ações Rápidas para lhe dar acesso rápido às funcionalidades do sistema comumente utilizadas sem ter de sair da aplicação. <br> Consulte [configurar HoloLens no modo quiosque](hololens-kiosk.md) para obter informações sobre o menu de ações rápidas no modo quiosque.<br><br> |
| **Pare a captura de vídeo do menu Iniciar ou ações rápidas** | Se iniciar a captura de vídeo a partir do menu de menu Iniciar ou ações rápidas, poderá parar de gravar a partir do mesmo local. (Não se esqueça, pode sempre fazer isso com comandos de voz também.) |
| **Project a um dispositivo ativado por Miracast** | Project o seu conteúdo HoloLens para um dispositivo Surface ou TV/Monitor próximo se utilizar o adaptador Microsoft Display.  On **Start**, selecione **Ligação** e, em seguida, selecione o dispositivo a que pretende projetar. **Nota:** Pode implementar HoloLens para utilizar Miracast projeção sem ativar o modo de desenvolvimento. |
| **Novas notificações** | Veja e responda a brindes de notificação no HoloLens, tal como faz num PC. Olhe para responder ou descartá-los (ou se estiver numa experiência imersiva, use o gesto de floração). |
| **sobreposições HoloLens**<br>(apanhador de ficheiros, teclado, diálogos, etc.) | Agora verá sobreposições como o teclado, diálogos, picker de ficheiros, etc. quando utilizar aplicações imersivas. |
| **Feedback visual sobrepõe UI para mudança de volume** | Quando utilizar os botões de volume para cima/para baixo no seu HoloLens verá uma visualização do nível de volume. |
| **Novo UI para arranque de dispositivo** | Foi adicionado um indicador de carregamento durante o processo de arranque para fornecer feedback visual que o sistema está a carregar. Reinicie o seu dispositivo para ver o novo indicador de carregamento — está entre a mensagem "Olá" e o logótipo de arranque Windows. |
| **Partilha nas proximidades** | Além da experiência Windows Nearby Sharing, permitindo-lhe partilhar uma captura com um dispositivo de Windows próximo. Quando capturar uma fotografia ou vídeo no HoloLens (ou utilizar o botão de partilha a partir de uma aplicação como Microsoft Edge), selecione um dispositivo de Windows próximo para partilhar. |
| **Partilhar do Microsoft Edge** | O botão de partilha está agora disponível nas janelas Microsoft Edge HoloLens. Em Microsoft Edge, **selecione Partilhar**. Utilize o HoloLens o selecionador de partilha para partilhar conteúdo sonoro. |

#### <a name="for-international-customers"></a>Para clientes internacionais

| Funcionalidade | Detalhes |
| --- | --- |
| Construções chinesas e japonesas localizadas | Utilize HoloLens com interface de utilizador localizada para chinês ou japonês simplificado, incluindo teclado pinyin localizado, ditado e comandos de voz.<br>[Saiba como instalar as versões chinesa e japonesa de HoloLens.](hololens1-install-localized.md) |
| Síntese de Fala (TTS) | A funcionalidade de síntese da fala suporta agora chinês, japonês e inglês. |

#### <a name="for-administrators"></a>Para administradores

| Funcionalidade |  Detalhes  |
|---|----|
| [Permitir o provisionamento pós-configuração](hololens-provisioning.md) | Pode agora aplicar um pacote de provisionamento de tempo de execução a qualquer momento utilizando **Definições**. |
| Acesso atribuído a grupos AD Azure | Agora pode utilizar grupos AD AZure para configuração de Windows acesso atribuído para configurar uma configuração de quiosque único ou multi-aplicações. |
| Pin-in no switch de perfil a partir do ecrã de inscrição | O s-in PIN já está disponível para **outro utilizador.** |
| Iniciar sessão com o Fornecedor de Credenciais Web usando senha | Agora pode selecionar a opção de entrada no Globe para lançar o s-in web com a sua palavra-passe. A partir do ecrã de insinusamento, selecione **opções de 'Iniciar's** e selecione a opção Globe para lançar o s-in web. Insira o seu nome de utilizador, se necessário, então a sua palavra-passe. <br>**Nota:** Pode optar por contornar quaisquer opções PIN/Smartcard quando solicitadas durante o sôm-in na Web. |
| Leia informações de hardware do dispositivo através do MDM para que os dispositivos possam ser rastreados pelo número de série | Os administradores de TI podem ver e rastrear HoloLens pelo número de série do dispositivo na sua consola MDM. Consulte a documentação do SEU MDM para obter a disponibilidade e instruções do recurso. |
| Desacorda HoloLens nome do dispositivo através do MDM (renomear) | Os administradores de TI podem ver e renomear HoloLens dispositivos na sua consola MDM. Consulte a documentação do SEU MDM para obter a disponibilidade e instruções do recurso. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, versão 1803 para Microsoft HoloLens

> **Aplica-se a:** HoloLens (1ª geração)

Windows 10, versão 1803, é a primeira atualização de funcionalidades a Windows Holographic for Business desde o seu lançamento em Windows 10, versão 1607. Esta atualização introduz as seguintes alterações:

- Anteriormente, só foi possível verificar se a licença de upgrade para a Suite Comercial tinha sido aplicada ao seu dispositivo HoloLens, verificando se a VPN era uma opção disponível no dispositivo. Agora, **Definições**  >  **Sistema** apresentará **Windows Holographic for Business** após a aplicação da licença de atualização. [Saiba como desbloquear Windows Holographic for Business funcionalidades.](hololens1-upgrade-enterprise.md)

- Pode ver o número de construção do sistema operativo nas propriedades do dispositivo na aplicação Do Explorador de Ficheiros e na [Ferramenta de Recuperação de Dispositivos Windows (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- O fornecimento de um dispositivo HoloLens é agora mais fácil com o novo assistente **de dispositivos de HoloLens de Provisão** na ferramenta Windows Configuration Designer. No assistente, pode configurar a experiência de configuração e as ligações de rede, definir o modo de desenvolvedor e obter fichas AD Azure a granel. [Saiba como utilizar o simples assistente de provisão para HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Quando se cria uma conta local num pacote de provisionamento, a palavra-passe já não expira a cada 42 dias.

- Pode [configurar HoloLens como um quiosque de aplicações únicas ou multi-aplicações.](hololens-kiosk.md) O modo quiosque multi-aplicações permite-lhe configurar um HoloLens para executar apenas as aplicações que especifica e impede os utilizadores de fazerem alterações.

- O Protocolo de Transferência de Meios de Comunicação Social (MTP) está ativado para que possa ligar o dispositivo HoloLens a um PC por USB e transferir ficheiros entre HoloLens e o PC. Também pode utilizar a aplicação File Explorer para mover e eliminar ficheiros dentro de HoloLens.

- Anteriormente, depois de ter assinado o dispositivo com uma conta de Azure Ative Directory (Azure AD), teve de **adicionar acesso** ao trabalho em **Definições** para ter acesso aos recursos corporativos. Agora, você insiná-lo com uma conta AD Azure e a inscrição acontece automaticamente.

- Antes de iniciar s dia, pode escolher o ícone de rede abaixo do campo de palavra-passe para escolher uma rede Wi-Fi diferente para se ligar. Você também pode conectar-se a uma rede de hóspedes, como em um hotel, centro de conferências ou negócios.

- Agora pode partilhar facilmente [HoloLens com várias pessoas](hololens-multiple-users.md) usando contas AD Azure.

- Quando a configuração ou o login falharem, escolha a nova opção **de informação Recolha** para obter registos de diagnóstico para resolução de problemas.

- Os utilizadores individuais podem sincronizar o seu email corporativo sem inscrever o seu dispositivo na gestão de dispositivos móveis (MDM). Pode utilizar o dispositivo com uma Conta Microsoft, descarregar e instalar a aplicação Mail e adicionar uma conta de e-mail diretamente.

- Pode verificar o estado de sincronização do MDM para um dispositivo em **Definições**  >  **Contas**  >  **Access Work ou School**  >  **Info**. Na secção de **estado de sincronização** do Dispositivo, pode iniciar uma sincronização, ver áreas geridas pelo MDM e criar e exportar um relatório de diagnóstico avançado.
