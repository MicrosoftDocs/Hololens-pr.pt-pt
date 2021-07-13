---
title: Instruções que contribuem
description: Aprenda a contribuir para os HoloLens docs na plataforma docs.microsoft.com usando o GitHub-sabor Markdown.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 73b6e8bcd634cb4d45171bda0a85f2e991a977c9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635675"
---
# <a name="contributing-to-the-hololens-documentation"></a>Contribuindo para a documentação HoloLens

Bem-vindo à [documentação HoloLens!](https://github.com/MicrosoftDocs/Hololens) Quaisquer artigos que crie ou edite neste repo **serão visíveis ao público.** 

HoloLens docs são exibidos na plataforma docs.microsoft.com, que usa GitHub com características de Markdig. O conteúdo que edita neste repo é formatado em páginas estilizadas que aparecem em /hololens.

Esta página abrange os passos básicos e diretrizes para contribuir e ligações ao básico de Markdown. Obrigado pela sua contribuição!

## <a name="available-repos"></a>Repos disponíveis

| Nome do repositório | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/realidade mista](/windows/mixed-reality) |
| Guia de Entusiastas do VR | [MicrosoftDocs/mixed-reality/entusiasta-guia](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Antes de começar

Se ainda não tiver uma, terá de [criar uma conta GitHub.](https://github.com/join)

>[!NOTE]
>Se for um funcionário da Microsoft, ligue a sua conta GitHub ao seu pseudónimo Microsoft no [portal Microsoft Open Source](https://repos.opensource.microsoft.com/). Junte-se às organizações **"Microsoft"** e **"MicrosoftDocs".**

Ao configurar a sua conta GitHub, recomendamos também estas precauções de segurança:
- Crie uma [palavra-passe forte para a sua conta GitHub.](https://github.com/settings/admin)
- Ativar [a autenticação de dois fatores.](https://github.com/settings/two_factor_authentication/configure)
- Guarde os seus [códigos de recuperação](https://github.com/settings/auth/recovery-codes) num local seguro.
- Atualize as [definições de perfil público](https://github.com/settings/profile).
   - Defina o seu nome e considere definir o seu *e-mail público* para *Não mostrar o meu endereço de e-mail.*
   - Recomendamos que faça upload de uma imagem de perfil porque uma miniatura é mostrada nas páginas de docs para as quais contribui.
- Se pretender utilizar a linha de comando, considere criar o [Git Credential Manager para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). Assim, não terás de introduzir a tua palavra-passe sempre que fizeres uma contribuição.

O sistema editorial está ligado a GitHub, pelo que estes passos são importantes. Você será listado como autor ou colaborador de cada artigo usando o seu pseudónimo GitHub.

## <a name="editing-an-existing-article"></a>Edição de um artigo existente

Utilize o seguinte fluxo de trabalho para fazer atualizações a *um artigo existente* através de GitHub num navegador web:

1. Navegue para o artigo que pretende editar na pasta "mixed-reality-docs".

2. Selecione o botão de edição (ícone de lápis) no superior direito, que irá automaticamente desviar um ramo descartável do ramo 'master'.

   ![Editar um artigo.](images/editpage.png)
   
3. Editar o conteúdo do artigo de acordo com o ["Básico de Markdown".](#markdown-basics)

4. Atualizar metadados no topo de cada artigo:

   * **título**: Título de página que aparece no separador do navegador quando o artigo está a ser visto. Os títulos de página são usados para SEO e indexação, por isso não altere o título a menos que seja necessário (embora isto seja menos crítico antes que a documentação seja pública).
   * **descrição**: Escreva uma breve descrição do conteúdo do artigo, que impulsiona o SEO e a descoberta.
   * **autor**: Se você é o principal proprietário da página, adicione o seu pseudónimo GitHub aqui.
   * **ms.author**: Se você é o principal proprietário da página, adicione o seu pseudónimo Microsoft aqui (você não precisa @microsoft.com , apenas o pseudónimo).
   * **ms.date**: Atualize a data se estiver a adicionar conteúdo importante à página, mas não para correções como esclarecimento, formatação, gramática ou ortografia.
   * **palavras-chave**: Ajuda às palavras-chave no SEO (otimização do motor de busca). Adicione palavras-chave, separadas por uma vírgula e um espaço, específicas do seu artigo, mas sem pontuação após a última palavra-chave da sua lista. Não é preciso adicionar palavras-chave globais que se aplicam a todos os artigos, uma vez que estes são geridos em outros lugares. 
   
5. Quando tiver concluído as edições de artigo, desloque-se para baixo e **selecione Alterar ficheiros**.

6. Na página seguinte, selecione **Criar pedido de puxar** para fundir o seu ramo criado automaticamente em 'master'.

7. Repita os passos acima para o próximo artigo que pretende editar.

## <a name="renaming-or-deleting-an-existing-article"></a>Renomear ou apagar um artigo existente

Se a sua alteração mudar de nome ou eliminar um artigo existente, certifique-se de adicionar um redirecionamento. Assim, qualquer pessoa com ligação ao artigo existente ainda acabará no lugar certo. Os redirecionamentos são geridos pelo .openpublishing.redirection.jsno ficheiro na raiz do repo.

Para adicionar um redirecionamento para .openpublishing.redirection.js, adicione uma entrada na `redirections` matriz:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- É `source_path` o caminho relativo do repositório para o velho artigo que está a remover. Certifique-se de que o caminho começa `mixed-reality-docs` e termina com `.md` .

- A `redirect_url` URL relativa do público do artigo antigo ao novo artigo. Certifique-se de que este URL **não** contém `mixed-reality-docs` `.md` ou, como se refere ao URL público e não ao caminho do repositório. É permitida a ligação a uma secção dentro do novo artigo `#section` que utiliza. Você também pode usar um caminho absoluto para outro site aqui, se necessário.

- `redirect_document_id` indica se gostaria de manter o documento iD do ficheiro anterior. A predefinição é `false`. Utilize `true` se quiser preservar o valor do atributo a partir do artigo `ms.documentid` redirecionado. Se preservar o ID do documento, os dados, tais como visualizações de páginas e rankings, serão transferidos para o artigo-alvo. Faça isto se o redirecionamento for principalmente um renome, e não um ponteiro para um artigo diferente que cubra apenas alguns dos mesmos conteúdos.

Se adicionar um redirecionamento, certifique-se de eliminar o ficheiro antigo também.

## <a name="creating-a-new-article"></a>Criar um novo artigo

Utilize o seguinte fluxo de trabalho para *criar novos artigos* na documentação repo via GitHub num navegador web:

1. Crie um garfo fora do ramo 'master' microsoftDocs/de realidade mista (utilizando o botão **Fork** no topo direito).

   ![Fork o ramo principal.](images/forkbranch.png)
   
2. Na pasta "mixed reality-docs", selecione **Criar um novo ficheiro** no topo direito.

3. Crie um nome de página para o artigo (use hífens em vez de espaços e não use pontuação ou apóstrofos) e apê-lo ".md"

   ![Diga o nome da sua nova página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Certifique-se de que cria o novo artigo a partir da pasta "mixed reality-docs". Pode confirmar isto verificando "/mixed-reality-docs/" na nova linha de nomes de ficheiros.

4. No topo da sua nova página, adicione o seguinte bloco de metadados:

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. Preencha os campos de metadados relevantes de acordo com as instruções na [secção acima](#editing-an-existing-article).

6. Escreva conteúdo de artigos utilizando [o básico de Markdown](#markdown-basics).

7. Adicione uma `## See also` secção na parte inferior do artigo com links para outros artigos relevantes.

8. Quando terminar, **selecione Comprometa novo ficheiro**.

9. Selecione **novo pedido de puxar** e misture o ramo 'master' do seu garfo no MicrosoftDocs/mixed-reality 'master' (certifique-se de que a seta está a apontar para o caminho correto).

   ![Crie o pedido de puxar do seu garfo para o MicrosoftDocs/mixed-reality](images/pr-to-master.png)

## <a name="markdown-basics"></a>Noções básicas de markdown

Os seguintes recursos irão ajudá-lo a aprender a editar documentação utilizando a linguagem Markdown:

- [Noções básicas de markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Recursos adicionais para escrever Markdown para docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Adicionar tabelas

Devido à forma como docs.microsoft.com tabelas de estilos, eles não terão fronteiras ou estilos personalizados, mesmo que experimente o CSS inline. Parece funcionar por um curto período de tempo, mas eventualmente a plataforma irá tirar o styling da mesa. Então planeie com antecedência e mantenha as suas mesas simples. [Aqui está um site que facilita as mesas de Markdown.](https://www.tablesgenerator.com/markdown_tables)

A [extensão de markdown do Docs para Visual Studio Código](/teamblog/docs-extension) também facilita a geração de mesas se estiver a utilizar Visual Studio Código [(ver abaixo)](#using-visual-studio-code) para editar a documentação.

### <a name="adding-images"></a>Adicionar imagens

Terá de fazer o upload das suas imagens para a pasta "mixed-reality-docs/images" no repo e, em seguida, faz referência adequadamente no artigo. As imagens aparecerão automaticamente em tamanho real, o que significa que imagens grandes preencherão toda a largura do artigo. Recomendamos pré-dimensionamento das suas imagens antes de as enviar. A largura recomendada é entre 600 e 700 pixels, embora deva ter um tamanho para cima ou para baixo se for uma imagem densa ou uma fração de uma imagem, respectivamente.

>[!IMPORTANT]
>Só é possível fazer o upload de imagens para o seu repo antes de se fundir. Por isso, se planeia adicionar imagens a um artigo, terá de [utilizar Visual Studio Código](#using-visual-studio-code) para adicionar as imagens à pasta "imagens" do seu garfo primeiro ou certificar-se de que fez o seguinte num navegador web:
>
>1. Forked the MicrosoftDocs/mixed-reality repo.
>2. Editou o artigo no seu garfo.
>3. Carregou as imagens a que se refere no seu artigo para a pasta "mixed-reality-docs/images" no seu garfo.
>4. Criei um **pedido de puxar** para fundir o seu garfo no ramo 'master' do MicrosoftDocs/mixed-reality.
>
>Para aprender a configurar o seu próprio repo forcado, siga as instruções para [criar um novo artigo](#creating-a-new-article).

## <a name="previewing-your-work"></a>Pré-visualização do seu trabalho

Ao editar em GitHub através de um navegador web, pode selecionar o **separador Pré-visualização** perto do topo da página para pré-visualizar o seu trabalho antes de se comprometer. 

>[!NOTE]
>Pré-visualizar as suas alterações no review.docs.microsoft.com só está disponível para os colaboradores da Microsoft

Funcionários da Microsoft: uma vez que as suas contribuições tenham sido fundidas na sucursal 'master', pode rever o conteúdo antes de ser divulgado em </hololens?branch=master>. Encontre o seu artigo utilizando a tabela de conteúdos na coluna esquerda.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Edição no navegador vs. edição com um cliente de desktop

A edição no navegador é a forma mais fácil de fazer mudanças rápidas, no entanto, existem algumas desvantagens:

- Não se ouve o feitiço.
- Não obtém qualquer ligação inteligente a outros artigos (tem de escrever manualmente o nome de ficheiro do artigo).
- Pode ser um ausoso carregar e fazer referência a imagens.

Se preferir não lidar com estes problemas, use um cliente de desktop como [Visual Studio Code](https://code.visualstudio.com/) com [algumas extensões úteis](#useful-extensions) ao contribuir.

## <a name="using-visual-studio-code"></a>Utilizar o Visual Studio Code

Pelas razões [acima](#editing-in-the-browser-vs-editing-with-a-desktop-client)enumeradas, pode preferir usar um cliente de ambiente de trabalho para editar documentação em vez de um navegador web. Recomendamos a utilização [do Código Visual Studio](https://code.visualstudio.com/).

### <a name="setup"></a>Configuração

Siga estes passos para configurar Visual Studio Código para trabalhar com este repo:

1. Num navegador web:
    1. Instale [git para o seu PC](https://git-scm.com/downloads).
    2. Instale [Visual Studio Código](https://code.visualstudio.com/).
    3. [Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) se ainda não o fez.
    4. No seu garfo, selecione **Clone ou descarregue** e copie o URL.
2. Crie um clone local do seu garfo no Código Visual Studio:
    1. No menu **Ver,** selecione **Paleta de Comando**.
    2. Escreva "Git: Clone".
    3. Cole a URL que copiou.
    4. Escolha onde guardar o clone no seu PC.
    5. Selecione **Repo Open** no pop-up.

### <a name="editing-documentation"></a>Documentação de edição

Utilize o seguinte fluxo de trabalho para erosão da documentação com Visual Studio Código:

>[!NOTE]
>Todas as orientações para [a edição](#editing-an-existing-article) e [criação](#creating-a-new-article) de artigos, e os [fundamentos da edição de Markdown,](#markdown-basics)de cima, aplicam-se ao utilizar Visual Studio Código também.

1. Certifique-se de que o seu garfo clonado está atualizado com o repo oficial.

   1. Num navegador web, crie um pedido de puxar para sincronizar as recentes alterações de outros contribuintes no MicrosoftDocs/mixed-reality 'master' para o seu garfo (certifique-se de que a seta está apontando para o caminho certo).
      
      ![Sync alterações de MicrosoftDocs/mixed-reality para o seu garfo](images/sync-repos.png)
      
   2. Em Visual Studio Código, selecione o botão de sincronização para sincronizar o garfo recentemente atualizado para o clone local.
      
      ![Clique na imagem do botão de sincronização](images/sync-clone.png)
      
2. Crie ou edite artigos no seu repo clonado utilizando Visual Studio Código.

   1. Editar um ou mais artigos (adicione imagens à pasta "imagens"), se necessário).
   
   2. **Guardar** alterações no **Explorer**.
      
      ![Escolha "Guardar tudo" no Explorer](images/explorer-save.png)
      
   3. **Escreva todas as** alterações no **Controlo de Origem** (escreva mensagem de compromisso quando solicitada).
   
      ![Escolha "Cometer tudo" no Controlo de Origem](images/source-control-commit.png)
      
   4. Selecione o botão **de sincronização** para sincronizar as alterações de volta à origem (o garfo no GitHub).
      
      ![Clique no botão de sincronização](images/sync-back.png)
      
3. Num navegador web, crie um pedido de puxar para sincronizar novas alterações no seu garfo de volta ao MicrosoftDocs/mixed-reality 'master' (certifique-se de que a seta está a apontar para o caminho correto).

   ![Crie o pedido de puxar do seu garfo para o MicrosoftDocs/mixed-reality](images/pr-to-master.png)

### <a name="useful-extensions"></a>Extensões úteis

As seguintes extensões Visual Studio código são úteis na edição da documentação:

- [Extensão de markdown do Docs para Visual Studio Código](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** para apresentar um menu de opções de autoria de docs como:
   - Procure e faça o upload de imagens de referência.
   - Adicione formatação como listas, tabelas e chamadas específicas de docs como `>[!NOTE]` .
   - Pesquisar e fazer referência links internos e marcadores (links para secções específicas dentro de uma página).
   - Os erros de formatação são realçados (paire o rato sobre o erro para saber mais).
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - serão sublinhadas palavras mal escritas; clique à direita numa palavra mal soletcionada para alterá-la ou guardá-la para o dicionário.
