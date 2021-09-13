---
title: Use a sua voz para operar HoloLens
description: Saiba como Cortana pode ajudá-lo a fazer todo o tipo de coisas no seu HoloLens dispositivos de realidade mista, incluindo comandos de voz, ditados e interações de hologramas.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036277"
---
# <a name="use-your-voice-to-operate-hololens"></a>Use a sua voz para operar HoloLens

Pode usar a sua voz para fazer quase tudo no HoloLens, como tirar uma fotografia rápida ou abrir uma aplicação. Muitos comandos de voz são incorporados em HoloLens, enquanto outros estão disponíveis através de Cortana.

Este artigo ensina-nos a controlar HoloLens e o mundo holográfico com a sua voz e com Cortana.

> [!NOTE]
> A fala só é apoiada em [algumas línguas.](hololens2-language-support.md) A linguagem da fala baseia-se na linguagem de exibição Windows, não na linguagem de teclado.  
>  
> Pode verificar o Windows o idioma de exibição selecionando **Definições**  >  **tempo e**  >  **linguagem** linguística .

## <a name="built-in-voice-commands"></a>Comandos de voz incorporados

Desa cos para HoloLens mais rápido com estes comandos básicos. Para os utilizar, é necessário ativar o Speech durante a primeira execução do dispositivo ou em **Definições** Discurso de  >  **Privacidade**  >  . Pode sempre verificar se a fala está ativada olhando para o estado no topo do menu Iniciar. Para obter os melhores resultados de reconhecimento de voz, HoloLens 2 utiliza os serviços baseados na nuvem da Microsoft. No entanto, pode utilizar Definições para desativar esta funcionalidade. Para isso, em Definições, desligue **o reconhecimento de voz online.** Depois de alterar esta definição, HoloLens 2 só processará dados de voz localmente para reconhecer comandos e ditados, e Cortana não estará disponível.

### <a name="general-speech-commands"></a>Comandos gerais da fala

Use estes comandos ao longo Windows Mixed Reality para se deslocar mais rápido. Alguns comandos usam o cursor de olhar, que você fala dizendo "selecione".

> [!NOTE]
> Os raios de mão não são suportados em HoloLens (1ª Gen).

| Diga isto | Para efetuar isto |
| - | - |
| "Selecione" | Diga "selecione" para trazer o cursor de olhar. Em seguida, vire a cabeça para posicionar o cursor na coisa que deseja selecionar e diga "selecione" novamente. |
| "Vai começar" |  Abrir o menu Iniciar |
| "Fechar"  | Feche a menu Iniciar |
| Diga "Vá para começar" para trazer o menu de ações rápidas, e depois diga "Casa da realidade mista".  | Deixe uma aplicação imersiva |
| "Hide hand ray" / "Show hand ray" | Esconda e mostre o raio da mão |
| "O que posso dizer?"  | Ver comandos de fala disponíveis |

Começando pela versão 19041.x de HoloLens 2, também pode utilizar estes comandos:

| Diga isto | Para efetuar isto |
| - | - |
| "Reiniciar dispositivo" | Faça um diálogo para confirmar que pretende reiniciar o dispositivo. Podes dizer "sim" para recomeçar. |
| "Dispositivo de paragem" | Faça um diálogo para confirmar que pretende desligar o dispositivo. Pode dizer "sim" para confirmar. |
| "Brilho para cima/para baixo" | Aumente ou diminua o brilho do visor em 10%. |
| "Volume para cima/para baixo" | Aumente ou diminua o volume em 10%. |
| "Qual é o meu endereço IP" | Apresente um diálogo que exiba o atual endereço IP do seu dispositivo na rede local. |
| "Tira uma fotografia" | Capture uma foto de realidade mista do que está a ver atualmente. |
| "Tira um vídeo" | Comece a gravar um vídeo de realidade mista. | 
| "Pare de gravar" | Para a atual gravação de vídeo de realidade mista se uma estiver em andamento. |

### <a name="hologram-commands"></a>Comandos hologramas

Para utilizar estes comandos, olhe para um objeto 3D, holograma ou janela de aplicações.

| Diga isto | Para efetuar isto |
| - | - |
| "Maior" | Torná-lo maior |
| "Menor" | Torná-lo menor |
| "Encarar-me" | Vire-o para te encarar. |
| "Move isto" | Mova-o (siga o seu olhar) |
| "Fechar" | Feche-o. |
| "Siga-me" / "Pare de seguir" | Faça-o segui-lo à medida que se move |

### <a name="see-it-say-it"></a>Vê-lo, dizê-lo.

Muitos botões e outros elementos no HoloLens também respondem à sua voz — por exemplo, **Siga-me** e **Feche** na barra de aplicações ou no botão **Back** in Edge. Para saber se um botão está ativado por voz, descanse o **cursor de olhar,** toque no **cursor** ou um raio de **mão** por um momento. Se o botão estiver ativado por voz, verá uma ponta de voz.

### <a name="dictation-mode"></a>Modo de ditado

Cansado de escrever? Mude para o modo de ditado sempre que o teclado holográfico estiver ativo. Para começar, selecione o botão do microfone ou diga "Comece a ditar". Para parar de ditar, selecione o botão novamente ou diga "Pare de ditar". Para apagar o que acabou de ditar, diga "Apague aquilo". 

> [!NOTE]
> Para utilizar o modo de ditado, tem de ter uma ligação à Internet.

HoloLens ditado usa pontuação explícita, o que significa que diz o nome da pontuação que quer usar. Por exemplo, pode dizer"Ei **vírgula,** o que estás a fazer para **questionar."**

Aqui estão as palavras-chave de pontuação que pode utilizar:

- Período, vírgula, ponto de interrogação, ponto de exclamação/ponto de exclamação
- Nova linha/novo parágrafo
- Ponto e vírgula, cólon
- Cotação aberta(s), cotação próxima(s)
- Hashtag, rosto sorridente/sorridente, franzido, piscar de olhos
- Dólar, por cento

Às vezes é útil soletrar coisas como endereços de e-mail. Por exemplo, para example@outlook.com ditar, você diria "E X A M P L E no outlook dot com."

## <a name="do-more-with-cortana"></a>Faça mais com Cortana

Cortana pode ajudá-lo a fazer todo o tipo de coisas no seu HoloLens, mas dependendo da versão de Windows Holographic que está a usar, as capacidades podem ser diferentes. Pode saber mais sobre as capacidades atualizadas da versão mais recente da Cortana aqui: [Cortana no próximo lançamento Windows 10: focado na sua produtividade com segurança e privacidade reforçadas.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/) 

![Olá Cortana!](images/cortana-on-hololens.png)

Aqui estão algumas coisas que pode tentar dizer (lembre-se de dizer "Hey Cortana" primeiro).

**Ei, Cortana...**

- O que posso dizer?
- Lançar <*nome de aplicativo*>.
- Que horas são?
- Mostra-me as últimas notas da NBA.
- Conta-me uma piada.

Se estiver a utilizar a *versão 18362.x ou mais cedo,* também pode utilizar estes comandos:

**Ei, Cortana...**

- Aumentar o volume.
- Diminua o brilho.
- Encerrar.
- Reiniciar.
- Ir dormir.
- Mudo.
- Mova <*nome de aplicação*> aqui (olhe para o local para onde pretende que a app se mude).
- Aceda a Iniciar.
- Tira uma fotografia.
- Começa a gravar. (Começa a gravar um vídeo.)
- Pare de gravar. (Para de gravar um vídeo.)
- Quantas baterias me restam?

Algumas funcionalidades Cortana a que está habituado a Windows no seu PC ou telefone (por exemplo, lembretes e notificações) não são suportadas em Microsoft HoloLens, e a experiência Cortana pode variar de uma região para outra.

### <a name="turn-cortana-off"></a>Desligue Cortana

Cortana é a primeira vez que se usa HoloLens quando se ativa a fala. Pode desligá-la nas definições de Cortana. Na lista **de aplicações All,** selecione **Cortana**  >  **Definições**. Em seguida, desligue Cortana pode dar-lhe sugestões, ideias, lembretes, alertas e muito mais.

Se Cortana não estiver a responder ao "Hey Cortana", verifique se o discurso está ativado no Start e vá para as definições de Cortana e verifique se está de pé.
