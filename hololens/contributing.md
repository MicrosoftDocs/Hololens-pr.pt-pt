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
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="da30d-103">Contribuindo para a documentação HoloLens</span><span class="sxs-lookup"><span data-stu-id="da30d-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="da30d-104">Bem-vindo à [documentação HoloLens!](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="da30d-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="da30d-105">Quaisquer artigos que crie ou edite neste repo **serão visíveis ao público.**</span><span class="sxs-lookup"><span data-stu-id="da30d-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="da30d-106">HoloLens docs são exibidos na plataforma docs.microsoft.com, que usa GitHub com características de Markdig.</span><span class="sxs-lookup"><span data-stu-id="da30d-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="da30d-107">O conteúdo que edita neste repo é formatado em páginas estilizadas que aparecem em /hololens.</span><span class="sxs-lookup"><span data-stu-id="da30d-107">The content you edit in this repo gets formatted into stylized pages that show up at /hololens.</span></span>

<span data-ttu-id="da30d-108">Esta página abrange os passos básicos e diretrizes para contribuir e ligações ao básico de Markdown.</span><span class="sxs-lookup"><span data-stu-id="da30d-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="da30d-109">Obrigado pela sua contribuição!</span><span class="sxs-lookup"><span data-stu-id="da30d-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="da30d-110">Repos disponíveis</span><span class="sxs-lookup"><span data-stu-id="da30d-110">Available repos</span></span>

| <span data-ttu-id="da30d-111">Nome do repositório</span><span class="sxs-lookup"><span data-stu-id="da30d-111">Repository name</span></span> | <span data-ttu-id="da30d-112">URL</span><span class="sxs-lookup"><span data-stu-id="da30d-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="da30d-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="da30d-113">HoloLens</span></span> | [<span data-ttu-id="da30d-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="da30d-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="da30d-115">Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="da30d-115">Mixed Reality</span></span> | [<span data-ttu-id="da30d-116">MicrosoftDocs/realidade mista</span><span class="sxs-lookup"><span data-stu-id="da30d-116">MicrosoftDocs/mixed-reality</span></span>](/windows/mixed-reality) |
| <span data-ttu-id="da30d-117">Guia de Entusiastas do VR</span><span class="sxs-lookup"><span data-stu-id="da30d-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="da30d-118">MicrosoftDocs/mixed-reality/entusiasta-guia</span><span class="sxs-lookup"><span data-stu-id="da30d-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="da30d-119">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="da30d-119">Before you start</span></span>

<span data-ttu-id="da30d-120">Se ainda não tiver uma, terá de [criar uma conta GitHub.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="da30d-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="da30d-121">Se for um funcionário da Microsoft, ligue a sua conta GitHub ao seu pseudónimo Microsoft no [portal Microsoft Open Source](https://repos.opensource.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="da30d-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="da30d-122">Junte-se às organizações **"Microsoft"** e **"MicrosoftDocs".**</span><span class="sxs-lookup"><span data-stu-id="da30d-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="da30d-123">Ao configurar a sua conta GitHub, recomendamos também estas precauções de segurança:</span><span class="sxs-lookup"><span data-stu-id="da30d-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="da30d-124">Crie uma [palavra-passe forte para a sua conta GitHub.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="da30d-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="da30d-125">Ativar [a autenticação de dois fatores.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="da30d-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="da30d-126">Guarde os seus [códigos de recuperação](https://github.com/settings/auth/recovery-codes) num local seguro.</span><span class="sxs-lookup"><span data-stu-id="da30d-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="da30d-127">Atualize as [definições de perfil público](https://github.com/settings/profile).</span><span class="sxs-lookup"><span data-stu-id="da30d-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="da30d-128">Defina o seu nome e considere definir o seu *e-mail público* para *Não mostrar o meu endereço de e-mail.*</span><span class="sxs-lookup"><span data-stu-id="da30d-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="da30d-129">Recomendamos que faça upload de uma imagem de perfil porque uma miniatura é mostrada nas páginas de docs para as quais contribui.</span><span class="sxs-lookup"><span data-stu-id="da30d-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="da30d-130">Se pretender utilizar a linha de comando, considere criar o [Git Credential Manager para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="da30d-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="da30d-131">Assim, não terás de introduzir a tua palavra-passe sempre que fizeres uma contribuição.</span><span class="sxs-lookup"><span data-stu-id="da30d-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="da30d-132">O sistema editorial está ligado a GitHub, pelo que estes passos são importantes.</span><span class="sxs-lookup"><span data-stu-id="da30d-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="da30d-133">Você será listado como autor ou colaborador de cada artigo usando o seu pseudónimo GitHub.</span><span class="sxs-lookup"><span data-stu-id="da30d-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="da30d-134">Edição de um artigo existente</span><span class="sxs-lookup"><span data-stu-id="da30d-134">Editing an existing article</span></span>

<span data-ttu-id="da30d-135">Utilize o seguinte fluxo de trabalho para fazer atualizações a *um artigo existente* através de GitHub num navegador web:</span><span class="sxs-lookup"><span data-stu-id="da30d-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="da30d-136">Navegue para o artigo que pretende editar na pasta "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="da30d-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="da30d-137">Selecione o botão de edição (ícone de lápis) no superior direito, que irá automaticamente desviar um ramo descartável do ramo 'master'.</span><span class="sxs-lookup"><span data-stu-id="da30d-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Editar um artigo.](images/editpage.png)
   
3. <span data-ttu-id="da30d-139">Editar o conteúdo do artigo de acordo com o ["Básico de Markdown".](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="da30d-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="da30d-140">Atualizar metadados no topo de cada artigo:</span><span class="sxs-lookup"><span data-stu-id="da30d-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="da30d-141">**título**: Título de página que aparece no separador do navegador quando o artigo está a ser visto.</span><span class="sxs-lookup"><span data-stu-id="da30d-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="da30d-142">Os títulos de página são usados para SEO e indexação, por isso não altere o título a menos que seja necessário (embora isto seja menos crítico antes que a documentação seja pública).</span><span class="sxs-lookup"><span data-stu-id="da30d-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="da30d-143">**descrição**: Escreva uma breve descrição do conteúdo do artigo, que impulsiona o SEO e a descoberta.</span><span class="sxs-lookup"><span data-stu-id="da30d-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="da30d-144">**autor**: Se você é o principal proprietário da página, adicione o seu pseudónimo GitHub aqui.</span><span class="sxs-lookup"><span data-stu-id="da30d-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="da30d-145">**ms.author**: Se você é o principal proprietário da página, adicione o seu pseudónimo Microsoft aqui (você não precisa @microsoft.com , apenas o pseudónimo).</span><span class="sxs-lookup"><span data-stu-id="da30d-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="da30d-146">**ms.date**: Atualize a data se estiver a adicionar conteúdo importante à página, mas não para correções como esclarecimento, formatação, gramática ou ortografia.</span><span class="sxs-lookup"><span data-stu-id="da30d-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="da30d-147">**palavras-chave**: Ajuda às palavras-chave no SEO (otimização do motor de busca).</span><span class="sxs-lookup"><span data-stu-id="da30d-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="da30d-148">Adicione palavras-chave, separadas por uma vírgula e um espaço, específicas do seu artigo, mas sem pontuação após a última palavra-chave da sua lista.</span><span class="sxs-lookup"><span data-stu-id="da30d-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="da30d-149">Não é preciso adicionar palavras-chave globais que se aplicam a todos os artigos, uma vez que estes são geridos em outros lugares.</span><span class="sxs-lookup"><span data-stu-id="da30d-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="da30d-150">Quando tiver concluído as edições de artigo, desloque-se para baixo e **selecione Alterar ficheiros**.</span><span class="sxs-lookup"><span data-stu-id="da30d-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="da30d-151">Na página seguinte, selecione **Criar pedido de puxar** para fundir o seu ramo criado automaticamente em 'master'.</span><span class="sxs-lookup"><span data-stu-id="da30d-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="da30d-152">Repita os passos acima para o próximo artigo que pretende editar.</span><span class="sxs-lookup"><span data-stu-id="da30d-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="da30d-153">Renomear ou apagar um artigo existente</span><span class="sxs-lookup"><span data-stu-id="da30d-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="da30d-154">Se a sua alteração mudar de nome ou eliminar um artigo existente, certifique-se de adicionar um redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="da30d-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="da30d-155">Assim, qualquer pessoa com ligação ao artigo existente ainda acabará no lugar certo.</span><span class="sxs-lookup"><span data-stu-id="da30d-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="da30d-156">Os redirecionamentos são geridos pelo .openpublishing.redirection.jsno ficheiro na raiz do repo.</span><span class="sxs-lookup"><span data-stu-id="da30d-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="da30d-157">Para adicionar um redirecionamento para .openpublishing.redirection.js, adicione uma entrada na `redirections` matriz:</span><span class="sxs-lookup"><span data-stu-id="da30d-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="da30d-158">É `source_path` o caminho relativo do repositório para o velho artigo que está a remover.</span><span class="sxs-lookup"><span data-stu-id="da30d-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="da30d-159">Certifique-se de que o caminho começa `mixed-reality-docs` e termina com `.md` .</span><span class="sxs-lookup"><span data-stu-id="da30d-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="da30d-160">A `redirect_url` URL relativa do público do artigo antigo ao novo artigo.</span><span class="sxs-lookup"><span data-stu-id="da30d-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="da30d-161">Certifique-se de que este URL **não** contém `mixed-reality-docs` `.md` ou, como se refere ao URL público e não ao caminho do repositório.</span><span class="sxs-lookup"><span data-stu-id="da30d-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="da30d-162">É permitida a ligação a uma secção dentro do novo artigo `#section` que utiliza.</span><span class="sxs-lookup"><span data-stu-id="da30d-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="da30d-163">Você também pode usar um caminho absoluto para outro site aqui, se necessário.</span><span class="sxs-lookup"><span data-stu-id="da30d-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="da30d-164">`redirect_document_id` indica se gostaria de manter o documento iD do ficheiro anterior.</span><span class="sxs-lookup"><span data-stu-id="da30d-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="da30d-165">A predefinição é `false`.</span><span class="sxs-lookup"><span data-stu-id="da30d-165">The default is `false`.</span></span> <span data-ttu-id="da30d-166">Utilize `true` se quiser preservar o valor do atributo a partir do artigo `ms.documentid` redirecionado.</span><span class="sxs-lookup"><span data-stu-id="da30d-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="da30d-167">Se preservar o ID do documento, os dados, tais como visualizações de páginas e rankings, serão transferidos para o artigo-alvo.</span><span class="sxs-lookup"><span data-stu-id="da30d-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="da30d-168">Faça isto se o redirecionamento for principalmente um renome, e não um ponteiro para um artigo diferente que cubra apenas alguns dos mesmos conteúdos.</span><span class="sxs-lookup"><span data-stu-id="da30d-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="da30d-169">Se adicionar um redirecionamento, certifique-se de eliminar o ficheiro antigo também.</span><span class="sxs-lookup"><span data-stu-id="da30d-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="da30d-170">Criar um novo artigo</span><span class="sxs-lookup"><span data-stu-id="da30d-170">Creating a new article</span></span>

<span data-ttu-id="da30d-171">Utilize o seguinte fluxo de trabalho para *criar novos artigos* na documentação repo via GitHub num navegador web:</span><span class="sxs-lookup"><span data-stu-id="da30d-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="da30d-172">Crie um garfo fora do ramo 'master' microsoftDocs/de realidade mista (utilizando o botão **Fork** no topo direito).</span><span class="sxs-lookup"><span data-stu-id="da30d-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Fork o ramo principal.](images/forkbranch.png)
   
2. <span data-ttu-id="da30d-174">Na pasta "mixed reality-docs", selecione **Criar um novo ficheiro** no topo direito.</span><span class="sxs-lookup"><span data-stu-id="da30d-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="da30d-175">Crie um nome de página para o artigo (use hífens em vez de espaços e não use pontuação ou apóstrofos) e apê-lo ".md"</span><span class="sxs-lookup"><span data-stu-id="da30d-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Diga o nome da sua nova página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="da30d-177">Certifique-se de que cria o novo artigo a partir da pasta "mixed reality-docs".</span><span class="sxs-lookup"><span data-stu-id="da30d-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="da30d-178">Pode confirmar isto verificando "/mixed-reality-docs/" na nova linha de nomes de ficheiros.</span><span class="sxs-lookup"><span data-stu-id="da30d-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="da30d-179">No topo da sua nova página, adicione o seguinte bloco de metadados:</span><span class="sxs-lookup"><span data-stu-id="da30d-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="da30d-180">Preencha os campos de metadados relevantes de acordo com as instruções na [secção acima](#editing-an-existing-article).</span><span class="sxs-lookup"><span data-stu-id="da30d-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="da30d-181">Escreva conteúdo de artigos utilizando [o básico de Markdown](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="da30d-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="da30d-182">Adicione uma `## See also` secção na parte inferior do artigo com links para outros artigos relevantes.</span><span class="sxs-lookup"><span data-stu-id="da30d-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="da30d-183">Quando terminar, **selecione Comprometa novo ficheiro**.</span><span class="sxs-lookup"><span data-stu-id="da30d-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="da30d-184">Selecione **novo pedido de puxar** e misture o ramo 'master' do seu garfo no MicrosoftDocs/mixed-reality 'master' (certifique-se de que a seta está a apontar para o caminho correto).</span><span class="sxs-lookup"><span data-stu-id="da30d-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Crie o pedido de puxar do seu garfo para o MicrosoftDocs/mixed-reality](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="da30d-186">Noções básicas de markdown</span><span class="sxs-lookup"><span data-stu-id="da30d-186">Markdown basics</span></span>

<span data-ttu-id="da30d-187">Os seguintes recursos irão ajudá-lo a aprender a editar documentação utilizando a linguagem Markdown:</span><span class="sxs-lookup"><span data-stu-id="da30d-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="da30d-188">Noções básicas de markdown</span><span class="sxs-lookup"><span data-stu-id="da30d-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="da30d-189">Recursos adicionais para escrever Markdown para docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="da30d-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="da30d-190">Adicionar tabelas</span><span class="sxs-lookup"><span data-stu-id="da30d-190">Adding tables</span></span>

<span data-ttu-id="da30d-191">Devido à forma como docs.microsoft.com tabelas de estilos, eles não terão fronteiras ou estilos personalizados, mesmo que experimente o CSS inline.</span><span class="sxs-lookup"><span data-stu-id="da30d-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="da30d-192">Parece funcionar por um curto período de tempo, mas eventualmente a plataforma irá tirar o styling da mesa.</span><span class="sxs-lookup"><span data-stu-id="da30d-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="da30d-193">Então planeie com antecedência e mantenha as suas mesas simples.</span><span class="sxs-lookup"><span data-stu-id="da30d-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="da30d-194">[Aqui está um site que facilita as mesas de Markdown.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="da30d-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="da30d-195">A [extensão de markdown do Docs para Visual Studio Código](/teamblog/docs-extension) também facilita a geração de mesas se estiver a utilizar Visual Studio Código [(ver abaixo)](#using-visual-studio-code) para editar a documentação.</span><span class="sxs-lookup"><span data-stu-id="da30d-195">The [Docs Markdown Extension for Visual Studio Code](/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="da30d-196">Adicionar imagens</span><span class="sxs-lookup"><span data-stu-id="da30d-196">Adding images</span></span>

<span data-ttu-id="da30d-197">Terá de fazer o upload das suas imagens para a pasta "mixed-reality-docs/images" no repo e, em seguida, faz referência adequadamente no artigo.</span><span class="sxs-lookup"><span data-stu-id="da30d-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="da30d-198">As imagens aparecerão automaticamente em tamanho real, o que significa que imagens grandes preencherão toda a largura do artigo.</span><span class="sxs-lookup"><span data-stu-id="da30d-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="da30d-199">Recomendamos pré-dimensionamento das suas imagens antes de as enviar.</span><span class="sxs-lookup"><span data-stu-id="da30d-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="da30d-200">A largura recomendada é entre 600 e 700 pixels, embora deva ter um tamanho para cima ou para baixo se for uma imagem densa ou uma fração de uma imagem, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="da30d-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="da30d-201">Só é possível fazer o upload de imagens para o seu repo antes de se fundir.</span><span class="sxs-lookup"><span data-stu-id="da30d-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="da30d-202">Por isso, se planeia adicionar imagens a um artigo, terá de [utilizar Visual Studio Código](#using-visual-studio-code) para adicionar as imagens à pasta "imagens" do seu garfo primeiro ou certificar-se de que fez o seguinte num navegador web:</span><span class="sxs-lookup"><span data-stu-id="da30d-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="da30d-203">Forked the MicrosoftDocs/mixed-reality repo.</span><span class="sxs-lookup"><span data-stu-id="da30d-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="da30d-204">Editou o artigo no seu garfo.</span><span class="sxs-lookup"><span data-stu-id="da30d-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="da30d-205">Carregou as imagens a que se refere no seu artigo para a pasta "mixed-reality-docs/images" no seu garfo.</span><span class="sxs-lookup"><span data-stu-id="da30d-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="da30d-206">Criei um **pedido de puxar** para fundir o seu garfo no ramo 'master' do MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="da30d-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="da30d-207">Para aprender a configurar o seu próprio repo forcado, siga as instruções para [criar um novo artigo](#creating-a-new-article).</span><span class="sxs-lookup"><span data-stu-id="da30d-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="da30d-208">Pré-visualização do seu trabalho</span><span class="sxs-lookup"><span data-stu-id="da30d-208">Previewing your work</span></span>

<span data-ttu-id="da30d-209">Ao editar em GitHub através de um navegador web, pode selecionar o **separador Pré-visualização** perto do topo da página para pré-visualizar o seu trabalho antes de se comprometer.</span><span class="sxs-lookup"><span data-stu-id="da30d-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="da30d-210">Pré-visualizar as suas alterações no review.docs.microsoft.com só está disponível para os colaboradores da Microsoft</span><span class="sxs-lookup"><span data-stu-id="da30d-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="da30d-211">Funcionários da Microsoft: uma vez que as suas contribuições tenham sido fundidas na sucursal 'master', pode rever o conteúdo antes de ser divulgado em </hololens?branch=master>.</span><span class="sxs-lookup"><span data-stu-id="da30d-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at </hololens?branch=master>.</span></span> <span data-ttu-id="da30d-212">Encontre o seu artigo utilizando a tabela de conteúdos na coluna esquerda.</span><span class="sxs-lookup"><span data-stu-id="da30d-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="da30d-213">Edição no navegador vs. edição com um cliente de desktop</span><span class="sxs-lookup"><span data-stu-id="da30d-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="da30d-214">A edição no navegador é a forma mais fácil de fazer mudanças rápidas, no entanto, existem algumas desvantagens:</span><span class="sxs-lookup"><span data-stu-id="da30d-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="da30d-215">Não se ouve o feitiço.</span><span class="sxs-lookup"><span data-stu-id="da30d-215">You don't get spell-check.</span></span>
- <span data-ttu-id="da30d-216">Não obtém qualquer ligação inteligente a outros artigos (tem de escrever manualmente o nome de ficheiro do artigo).</span><span class="sxs-lookup"><span data-stu-id="da30d-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="da30d-217">Pode ser um ausoso carregar e fazer referência a imagens.</span><span class="sxs-lookup"><span data-stu-id="da30d-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="da30d-218">Se preferir não lidar com estes problemas, use um cliente de desktop como [Visual Studio Code](https://code.visualstudio.com/) com [algumas extensões úteis](#useful-extensions) ao contribuir.</span><span class="sxs-lookup"><span data-stu-id="da30d-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="da30d-219">Utilizar o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="da30d-219">Using Visual Studio Code</span></span>

<span data-ttu-id="da30d-220">Pelas razões [acima](#editing-in-the-browser-vs-editing-with-a-desktop-client)enumeradas, pode preferir usar um cliente de ambiente de trabalho para editar documentação em vez de um navegador web.</span><span class="sxs-lookup"><span data-stu-id="da30d-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="da30d-221">Recomendamos a utilização [do Código Visual Studio](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="da30d-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="da30d-222">Configuração</span><span class="sxs-lookup"><span data-stu-id="da30d-222">Setup</span></span>

<span data-ttu-id="da30d-223">Siga estes passos para configurar Visual Studio Código para trabalhar com este repo:</span><span class="sxs-lookup"><span data-stu-id="da30d-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="da30d-224">Num navegador web:</span><span class="sxs-lookup"><span data-stu-id="da30d-224">In a web browser:</span></span>
    1. <span data-ttu-id="da30d-225">Instale [git para o seu PC](https://git-scm.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="da30d-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="da30d-226">Instale [Visual Studio Código](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="da30d-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="da30d-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) se ainda não o fez.</span><span class="sxs-lookup"><span data-stu-id="da30d-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="da30d-228">No seu garfo, selecione **Clone ou descarregue** e copie o URL.</span><span class="sxs-lookup"><span data-stu-id="da30d-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="da30d-229">Crie um clone local do seu garfo no Código Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="da30d-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="da30d-230">No menu **Ver,** selecione **Paleta de Comando**.</span><span class="sxs-lookup"><span data-stu-id="da30d-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="da30d-231">Escreva "Git: Clone".</span><span class="sxs-lookup"><span data-stu-id="da30d-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="da30d-232">Cole a URL que copiou.</span><span class="sxs-lookup"><span data-stu-id="da30d-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="da30d-233">Escolha onde guardar o clone no seu PC.</span><span class="sxs-lookup"><span data-stu-id="da30d-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="da30d-234">Selecione **Repo Open** no pop-up.</span><span class="sxs-lookup"><span data-stu-id="da30d-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="da30d-235">Documentação de edição</span><span class="sxs-lookup"><span data-stu-id="da30d-235">Editing documentation</span></span>

<span data-ttu-id="da30d-236">Utilize o seguinte fluxo de trabalho para erosão da documentação com Visual Studio Código:</span><span class="sxs-lookup"><span data-stu-id="da30d-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="da30d-237">Todas as orientações para [a edição](#editing-an-existing-article) e [criação](#creating-a-new-article) de artigos, e os [fundamentos da edição de Markdown,](#markdown-basics)de cima, aplicam-se ao utilizar Visual Studio Código também.</span><span class="sxs-lookup"><span data-stu-id="da30d-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="da30d-238">Certifique-se de que o seu garfo clonado está atualizado com o repo oficial.</span><span class="sxs-lookup"><span data-stu-id="da30d-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="da30d-239">Num navegador web, crie um pedido de puxar para sincronizar as recentes alterações de outros contribuintes no MicrosoftDocs/mixed-reality 'master' para o seu garfo (certifique-se de que a seta está apontando para o caminho certo).</span><span class="sxs-lookup"><span data-stu-id="da30d-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Sync alterações de MicrosoftDocs/mixed-reality para o seu garfo](images/sync-repos.png)
      
   2. <span data-ttu-id="da30d-241">Em Visual Studio Código, selecione o botão de sincronização para sincronizar o garfo recentemente atualizado para o clone local.</span><span class="sxs-lookup"><span data-stu-id="da30d-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Clique na imagem do botão de sincronização](images/sync-clone.png)
      
2. <span data-ttu-id="da30d-243&quot;>Crie ou edite artigos no seu repo clonado utilizando Visual Studio Código.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;da30d-243&quot;>Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id=&quot;da30d-244&quot;>Editar um ou mais artigos (adicione imagens à pasta &quot;imagens"), se necessário).</span><span class="sxs-lookup"><span data-stu-id="da30d-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="da30d-245">**Guardar** alterações no **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="da30d-245">**Save** changes in **Explorer**.</span></span>
      
      ![Escolha "Guardar tudo" no Explorer](images/explorer-save.png)
      
   3. <span data-ttu-id="da30d-247">**Escreva todas as** alterações no **Controlo de Origem** (escreva mensagem de compromisso quando solicitada).</span><span class="sxs-lookup"><span data-stu-id="da30d-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Escolha "Cometer tudo" no Controlo de Origem](images/source-control-commit.png)
      
   4. <span data-ttu-id="da30d-249">Selecione o botão **de sincronização** para sincronizar as alterações de volta à origem (o garfo no GitHub).</span><span class="sxs-lookup"><span data-stu-id="da30d-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Clique no botão de sincronização](images/sync-back.png)
      
3. <span data-ttu-id="da30d-251">Num navegador web, crie um pedido de puxar para sincronizar novas alterações no seu garfo de volta ao MicrosoftDocs/mixed-reality 'master' (certifique-se de que a seta está a apontar para o caminho correto).</span><span class="sxs-lookup"><span data-stu-id="da30d-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Crie o pedido de puxar do seu garfo para o MicrosoftDocs/mixed-reality](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="da30d-253">Extensões úteis</span><span class="sxs-lookup"><span data-stu-id="da30d-253">Useful extensions</span></span>

<span data-ttu-id="da30d-254">As seguintes extensões Visual Studio código são úteis na edição da documentação:</span><span class="sxs-lookup"><span data-stu-id="da30d-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="da30d-255">[Extensão de markdown do Docs para Visual Studio Código](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** para apresentar um menu de opções de autoria de docs como:</span><span class="sxs-lookup"><span data-stu-id="da30d-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="da30d-256">Procure e faça o upload de imagens de referência.</span><span class="sxs-lookup"><span data-stu-id="da30d-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="da30d-257">Adicione formatação como listas, tabelas e chamadas específicas de docs como `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="da30d-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="da30d-258">Pesquisar e fazer referência links internos e marcadores (links para secções específicas dentro de uma página).</span><span class="sxs-lookup"><span data-stu-id="da30d-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="da30d-259">Os erros de formatação são realçados (paire o rato sobre o erro para saber mais).</span><span class="sxs-lookup"><span data-stu-id="da30d-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="da30d-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - serão sublinhadas palavras mal escritas; clique à direita numa palavra mal soletcionada para alterá-la ou guardá-la para o dicionário.</span><span class="sxs-lookup"><span data-stu-id="da30d-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
