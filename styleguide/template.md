---
title:
- ЗАГОЛОВОК СТАТЬИ
description: ''
author:
- GITHUB USERNAME
ms.author:
- MICROSOFT ALIAS OF INTERNAL OWNER
ms.date:
- CREATION/UPDATE DATE - MM/dd/yyyy
ms.topic:
- TOPIC TYPE
ms.prod:
- PRODUCT VALUE
helpviewer_keywords:
- OFFLINE BOOK INDEX ENTRIES
ms.openlocfilehash: 3674508c25e9a4b166f994e7ca16df04e484956b
ms.sourcegitcommit: 1e72e2990220b3635cebc39586828af9deb72d8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2019
ms.locfileid: "71306361"
---
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="435a5-102">Шаблон метаданных и разметки Markdown</span><span class="sxs-lookup"><span data-stu-id="435a5-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="435a5-103">Этот шаблон dotnet/docs содержит примеры синтаксиса Markdown, а также указания по заданию метаданных.</span><span class="sxs-lookup"><span data-stu-id="435a5-103">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="435a5-104">Чтобы использовать шаблон наиболее эффективно, следует просматривать как [необработанную разметку Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md), так и [подготовленное к просмотру представление](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (например, в необработанной разметке Markdown виден блок метаданных, а в подготовленном к просмотру представлении — нет).</span><span class="sxs-lookup"><span data-stu-id="435a5-104">To get the most of it, you must view both the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) and the [rendered view](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (for instance, the raw Markdown shows the metadata block, while the rendered view does not).</span></span>

<span data-ttu-id="435a5-105">При создании файла Markdown следует скопировать этот шаблон в новый файл, заполнить метаданные, как указано ниже, задать заголовок H1 в соответствии с названием статьи и удалить содержимое.</span><span class="sxs-lookup"><span data-stu-id="435a5-105">When creating a Markdown file, you should copy this template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span>

## <a name="metadata"></a><span data-ttu-id="435a5-106">Metadata</span><span class="sxs-lookup"><span data-stu-id="435a5-106">Metadata</span></span>

<span data-ttu-id="435a5-107">Полный блок метаданных (в [необработанной разметке Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)) разделен на четыре обязательных поля и необязательные поля.</span><span class="sxs-lookup"><span data-stu-id="435a5-107">The full metadata block is above (in the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), divided into required fields and optional fields.</span></span> <span data-ttu-id="435a5-108">Ключевые замечания:</span><span class="sxs-lookup"><span data-stu-id="435a5-108">Some key notes:</span></span>

- <span data-ttu-id="435a5-109">Между двоеточием (:) и значением элемента метаданных **должен** быть пробел.</span><span class="sxs-lookup"><span data-stu-id="435a5-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="435a5-110">Если необязательный элемент метаданных не имеет значения, закомментируйте элемент символом # или удалите его (не оставляйте его пустым и не используйте "НД").</span><span class="sxs-lookup"><span data-stu-id="435a5-110">If an optional metadata element doesn't have a value, comment out the element with a # or remove it (don't leave it blank or use "na").</span></span> <span data-ttu-id="435a5-111">Если вы добавляете значение к элементу, который был закомментирован, не забудьте удалить #.</span><span class="sxs-lookup"><span data-stu-id="435a5-111">If you're adding a value to an element that was commented out, be sure to remove the #.</span></span>
- <span data-ttu-id="435a5-112">Двоеточия в значении (например, названии) нарушают работу средства анализа метаданных.</span><span class="sxs-lookup"><span data-stu-id="435a5-112">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="435a5-113">В этом случае заключите название в двойные кавычки (например, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="435a5-113">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="435a5-114">Поле **title**. Отображается в результатах поисковой системы.</span><span class="sxs-lookup"><span data-stu-id="435a5-114">**title**: Appears in search engine results.</span></span> <span data-ttu-id="435a5-115">Заголовок не обязательно должен совпадать с названием в заголовке H1 и должен содержать не более 60 символов.</span><span class="sxs-lookup"><span data-stu-id="435a5-115">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="435a5-116">**description**: содержит сводку по содержимому статьи.</span><span class="sxs-lookup"><span data-stu-id="435a5-116">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="435a5-117">Обычно отображается на странице результатов поиска, но не используется для ранжирования поиска.</span><span class="sxs-lookup"><span data-stu-id="435a5-117">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="435a5-118">Его длина должна составлять 115–145 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="435a5-118">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="435a5-119">**author** и **ms.author**: поле author должно содержать **имя пользователя GitHub**, принадлежащее автору, а не его псевдоним.</span><span class="sxs-lookup"><span data-stu-id="435a5-119">**author** and **ms.author**: The author field should contain the **GitHub username** of the author, not his/her alias.</span></span>  <span data-ttu-id="435a5-120">Поле **ms.author**, с другой стороны, должно содержать псевдоним Майкрософт и указывает лицо, ответственное за сопровождение статьи.</span><span class="sxs-lookup"><span data-stu-id="435a5-120">The **ms.author** field, on the other hand, should contain a Microsoft alias and indicates the person responsible for maintaining the article.</span></span>
- <span data-ttu-id="435a5-121">**ms.topic**: тип раздела.</span><span class="sxs-lookup"><span data-stu-id="435a5-121">**ms.topic**: The topic type.</span></span> <span data-ttu-id="435a5-122">Наиболее распространенное значение — `conceptual`. Оно устанавливается на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="435a5-122">The most common value is `conceptual` and is set at a global level.</span></span> <span data-ttu-id="435a5-123">Используются и другие распространенные значения: `tutorial`, `overview` и `reference`.</span><span class="sxs-lookup"><span data-stu-id="435a5-123">Other common values used are `tutorial`, `overview`, and `reference`.</span></span>
- <span data-ttu-id="435a5-124">**ms.devlang** определяет языковой фильтр, отображаемый для раздела.</span><span class="sxs-lookup"><span data-stu-id="435a5-124">**ms.devlang** defines the language filter displayed for the topic.</span></span> <span data-ttu-id="435a5-125">Список поддерживаемых значений можно просмотреть в разделе [Поддерживаемые языки](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="435a5-125">You can see a list of the supported values in the [Supported languages](#supported-languages) section.</span></span> <span data-ttu-id="435a5-126">Необходимо устанавливать только в том случае, если в разделе содержится более одного языка программирования.</span><span class="sxs-lookup"><span data-stu-id="435a5-126">Only needs to be set when there's more than one programming language covered in the topic.</span></span> <span data-ttu-id="435a5-127">Как правило, для этого значения в содержимом используются только `csharp`, `vb`, `fsharp` и `cpp`.</span><span class="sxs-lookup"><span data-stu-id="435a5-127">Typically, we only use `csharp`, `vb`, `fsharp`, and `cpp` for this value in our content.</span></span>
- <span data-ttu-id="435a5-128">**ms.prod**: идентификатор продукта, используемый для бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="435a5-128">**ms.prod**: Product identification used for BI purposes.</span></span> <span data-ttu-id="435a5-129">Обычно они устанавливаются на глобальном уровне, поэтому не отображаются в блоке метаданных каждой статьи.</span><span class="sxs-lookup"><span data-stu-id="435a5-129">They're usually set at a global level, so they don't usually appear in the metadata block of each article.</span></span>
- <span data-ttu-id="435a5-130">**ms.technology**: дополнительная классификация бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="435a5-130">**ms.technology**: Additional BI classification.</span></span> <span data-ttu-id="435a5-131">Некоторые из поддерживаемых значений: `devlang-csharp` для разделов по C#, `devlang-fsharp` для разделов по F# и `devlang-visual-basic` для разделов по VB.</span><span class="sxs-lookup"><span data-stu-id="435a5-131">Some of the supported values are: `devlang-csharp` for C# topics, `devlang-fsharp` for F# topics, and `devlang-visual-basic` for VB topics.</span></span> <span data-ttu-id="435a5-132">Для других руководств значения будут различаться, поэтому обратитесь к участнику группы за рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="435a5-132">For other guides, the values will vary, so ask a member of the team for guidance.</span></span>
- <span data-ttu-id="435a5-133">**ms.date**: дата в формате MM/ДД/ГГГГ.</span><span class="sxs-lookup"><span data-stu-id="435a5-133">**ms.date**: A date in the format MM/dd/yyyy.</span></span> <span data-ttu-id="435a5-134">Отображается на опубликованной странице, чтобы указать время последнего существенного изменения статьи или гарантировать ее актуальность (то есть статья была проверена и признана актуальной).</span><span class="sxs-lookup"><span data-stu-id="435a5-134">Displayed on the published page to indicate the last time the article was substantially edited or guaranteed "fresh" (that is, the article was reviewed and considered up-to-date).</span></span>
- <span data-ttu-id="435a5-135">**helpviewer_keywords**: Записи используются для автономного индексирования книг (функция в Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="435a5-135">**helpviewer_keywords**: Entries are used for the offline books index (functionality in Visual Studio).</span></span>
- <span data-ttu-id="435a5-136">**f1_keywords**: Подключает статью к клавише F1 (функция в Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="435a5-136">**f1_keywords**: Connects the article to the F1 key (functionality in Visual Studio).</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="435a5-137">Базовая разметка Markdown, GFM и специальные символы</span><span class="sxs-lookup"><span data-stu-id="435a5-137">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="435a5-138">Поддерживаются все возможности базовой разметки Markdown и GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="435a5-138">All basic and GitHub Flavored Markdown (GFM) is supported.</span></span> <span data-ttu-id="435a5-139">Дополнительные сведения см. в следующих ресурсах.</span><span class="sxs-lookup"><span data-stu-id="435a5-139">For more information on these, see:</span></span>

- [<span data-ttu-id="435a5-140">Базовый синтаксис Markdown</span><span class="sxs-lookup"><span data-stu-id="435a5-140">Baseline Markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="435a5-141">Документация GFM</span><span class="sxs-lookup"><span data-stu-id="435a5-141">GFM documentation</span></span>](https://guides.github.com/features/mastering-markdown)

<span data-ttu-id="435a5-142">Для форматирования в Markdown используются специальные символы, такие как \*, \` и \#.</span><span class="sxs-lookup"><span data-stu-id="435a5-142">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="435a5-143">Если вы хотите включить в содержимое один из этих символов, нужно выполнить одно из двух действий:</span><span class="sxs-lookup"><span data-stu-id="435a5-143">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="435a5-144">поставить обратную косую черту перед специальным символом для его экранирования (например, `\*` для символа \*);</span><span class="sxs-lookup"><span data-stu-id="435a5-144">Put a backslash before the special character to "escape" it (for example, `\*` for a \*)</span></span>
- <span data-ttu-id="435a5-145">использовать [код сущности HTML](https://www.ascii.cl/htmlcodes.htm) для символа (например, `&#42;` для &#42;).</span><span class="sxs-lookup"><span data-stu-id="435a5-145">Use the [HTML entity code](https://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for a &#42;).</span></span>

## <a name="file-name"></a><span data-ttu-id="435a5-146">Имя файла</span><span class="sxs-lookup"><span data-stu-id="435a5-146">File name</span></span>

<span data-ttu-id="435a5-147">В отношении имен файлов действуют указанные ниже правила.</span><span class="sxs-lookup"><span data-stu-id="435a5-147">File names use the following rules:</span></span>

- <span data-ttu-id="435a5-148">Содержат только строчные буквы, цифры и дефисы.</span><span class="sxs-lookup"><span data-stu-id="435a5-148">Contain only lowercase letters, numbers, and hyphens.</span></span>
- <span data-ttu-id="435a5-149">Пробелы и знаки препинания недопустимы.</span><span class="sxs-lookup"><span data-stu-id="435a5-149">No spaces or punctuation characters.</span></span> <span data-ttu-id="435a5-150">Для разделения слов и чисел в именах файлов используйте дефисы.</span><span class="sxs-lookup"><span data-stu-id="435a5-150">Use the hyphens to separate words and numbers in the file name.</span></span>
- <span data-ttu-id="435a5-151">Для обозначения действий используйте глаголы, например develop, buy, build, troubleshoot.</span><span class="sxs-lookup"><span data-stu-id="435a5-151">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="435a5-152">Использование слов, оканчивающихся на -ing, не допускается.</span><span class="sxs-lookup"><span data-stu-id="435a5-152">No -ing words.</span></span>
- <span data-ttu-id="435a5-153">Нельзя использовать служебные (короткие) слова, такие как a, and, the, in, or и т. д.</span><span class="sxs-lookup"><span data-stu-id="435a5-153">No small words - don't include a, and, the, in, or, etc.</span></span>
- <span data-ttu-id="435a5-154">Необходимо использовать формат Markdown и расширение имени файла .md.</span><span class="sxs-lookup"><span data-stu-id="435a5-154">Must be in Markdown and use the .md file extension.</span></span>
- <span data-ttu-id="435a5-155">Имена файлов не должны быть слишком длинными.</span><span class="sxs-lookup"><span data-stu-id="435a5-155">Keep file names reasonably short.</span></span> <span data-ttu-id="435a5-156">Они являются частью URL-адресов статей.</span><span class="sxs-lookup"><span data-stu-id="435a5-156">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="435a5-157">Заголовки</span><span class="sxs-lookup"><span data-stu-id="435a5-157">Headings</span></span>

<span data-ttu-id="435a5-158">Прописные буквы следует использовать как в предложениях.</span><span class="sxs-lookup"><span data-stu-id="435a5-158">Use sentence-style capitalization.</span></span> <span data-ttu-id="435a5-159">Первое слово заголовка всегда должно начинаться с прописной буквы, но не начинайте с него слово, идущее после двоеточия в заголовке или названии (например, "How to: sort an array").</span><span class="sxs-lookup"><span data-stu-id="435a5-159">Always capitalize the first word of a heading, but don't capitalize the word following a colon in a title or heading (for example, "How to: sort an array").</span></span>

<span data-ttu-id="435a5-160">Заголовки следует оформлять в стиле atx, то есть использовать для указания заголовка 1–6 символов решетки (#) в начале строки, что соответствует уровням заголовков HTML с H1 по H6.</span><span class="sxs-lookup"><span data-stu-id="435a5-160">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="435a5-161">Выше приведены примеры заголовков первого и второго уровней.</span><span class="sxs-lookup"><span data-stu-id="435a5-161">Examples of first- and second-level headers are used above.</span></span>

<span data-ttu-id="435a5-162">В статье **должен** быть только один заголовок первого уровня (H1), который будет отображаться на странице как название.</span><span class="sxs-lookup"><span data-stu-id="435a5-162">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="435a5-163">Если заголовок заканчивается символом `#`, для его правильного отображения в конце нужно добавить еще один символ `#`.</span><span class="sxs-lookup"><span data-stu-id="435a5-163">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="435a5-164">Например, `# Async Programming in F# #`.</span><span class="sxs-lookup"><span data-stu-id="435a5-164">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="435a5-165">На основе заголовков второго уровня будет сформировано оглавление, которое приводится в разделе "Содержимое статьи" под названием статьи.</span><span class="sxs-lookup"><span data-stu-id="435a5-165">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="435a5-166">Заголовок третьего уровня</span><span class="sxs-lookup"><span data-stu-id="435a5-166">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="435a5-167">Заголовок четвертого уровня</span><span class="sxs-lookup"><span data-stu-id="435a5-167">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="435a5-168">Заголовок пятого уровня</span><span class="sxs-lookup"><span data-stu-id="435a5-168">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="435a5-169">Заголовок шестого уровня</span><span class="sxs-lookup"><span data-stu-id="435a5-169">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="435a5-170">Стиль текста</span><span class="sxs-lookup"><span data-stu-id="435a5-170">Text styling</span></span>

<span data-ttu-id="435a5-171">*Курсив* — используйте для имен файлов, папок и путей (если из-за большой длины они выносятся в отдельные строки), новых терминов.</span><span class="sxs-lookup"><span data-stu-id="435a5-171">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="435a5-172">**Полужирный** — используйте для элементов пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="435a5-172">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="435a5-173">`Code` — используется для встроенного кода, ключевых слов языка, имен пакетов NuGet, команд командной строки, имен таблиц и столбцов базы данных, а также URL-адресов, по которым не нужно переходить.</span><span class="sxs-lookup"><span data-stu-id="435a5-173">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="435a5-174">Ссылки</span><span class="sxs-lookup"><span data-stu-id="435a5-174">Links</span></span>

### <a name="internal-links"></a><span data-ttu-id="435a5-175">Внутренние ссылки</span><span class="sxs-lookup"><span data-stu-id="435a5-175">Internal Links</span></span>

<span data-ttu-id="435a5-176">Чтобы создать ссылку на заголовок в том же файле Markdown (ссылку привязки), необходимо определить идентификатор заголовка, на который должна указывать ссылка.</span><span class="sxs-lookup"><span data-stu-id="435a5-176">To link to a header in the same Markdown file (also known as anchor links), you'll need to find out the id of the header you're trying to link to.</span></span> <span data-ttu-id="435a5-177">Для этого просмотрите исходный код обработанной статьи, найдите идентификатор заголовка (например, `id="blockquote"`) и создайте ссылку, поставив перед идентификатором символ # (например, `#blockquote`).</span><span class="sxs-lookup"><span data-stu-id="435a5-177">To confirm the ID, view the source of the rendered article, find the id of the header (for example, `id="blockquote"`), and link using # + id (for example, `#blockquote`).</span></span>
<span data-ttu-id="435a5-178">Идентификатор формируется автоматически на основе текста заголовка.</span><span class="sxs-lookup"><span data-stu-id="435a5-178">The id is auto-generated based on the header text.</span></span> <span data-ttu-id="435a5-179">Например, для уникального раздела под названием `## Step 2` идентификатор будет выглядеть так: `id="step-2"`.</span><span class="sxs-lookup"><span data-stu-id="435a5-179">So, for example, given a unique section named `## Step 2`, the id would look like this `id="step-2"`.</span></span>

- <span data-ttu-id="435a5-180">Пример: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` создает [объявление встроенных блоков с идентификатором языка](#inline-code-blocks-with-language-identifier).</span><span class="sxs-lookup"><span data-stu-id="435a5-180">Example: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produces [Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier).</span></span>

<span data-ttu-id="435a5-181">Чтобы создать ссылку на файл Markdown в том же репозитории, используйте [относительную ссылку](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), указав расширение .md в конце имени файла.</span><span class="sxs-lookup"><span data-stu-id="435a5-181">To link to a Markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), including the ".md" at the end of the filename.</span></span>

- <span data-ttu-id="435a5-182">Пример: `[Readme file](../README.md)` создает [файл сведений](../README.md).</span><span class="sxs-lookup"><span data-stu-id="435a5-182">Example: `[Readme file](../README.md)` produces [Readme file](../README.md).</span></span> <span data-ttu-id="435a5-183">(Обратите внимание, что в ссылках учитывается регистр.)</span><span class="sxs-lookup"><span data-stu-id="435a5-183">(Note that links are case-sensitive.)</span></span>
- <span data-ttu-id="435a5-184">Пример: `[Welcome to .NET](../docs/welcome.md)` создает [Добро пожаловать в .NET](../docs/welcome.md).</span><span class="sxs-lookup"><span data-stu-id="435a5-184">Example: `[Welcome to .NET](../docs/welcome.md)` produces [Welcome to .NET](../docs/welcome.md).</span></span>

<span data-ttu-id="435a5-185">Чтобы создать ссылку на заголовок в файле Markdown в том же репозитории, используйте относительную ссылку + ссылку с символом решетки.</span><span class="sxs-lookup"><span data-stu-id="435a5-185">To link to a header in a Markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="435a5-186">Пример: `[.NET Community](../docs/welcome.md#open-source)` создает [Сообщество .NET](../docs/welcome.md#open-source).</span><span class="sxs-lookup"><span data-stu-id="435a5-186">Example: `[.NET Community](../docs/welcome.md#open-source)` produces [.NET Community](../docs/welcome.md#open-source).</span></span>

<span data-ttu-id="435a5-187">В большинстве случаев мы используем относительные ссылки и не рекомендуем использовать `~/` в ссылках, так как относительные ссылки разрешаются в источнике на GitHub.</span><span class="sxs-lookup"><span data-stu-id="435a5-187">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="435a5-188">Однако при ссылке на файл в зависимом репозитории мы будем использовать символ `~/` для предоставления пути.</span><span class="sxs-lookup"><span data-stu-id="435a5-188">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="435a5-189">Так как файлы в зависимом репозитории находятся в другом расположении на GitHub, ссылки не будут правильно разрешаться с относительными ссылками независимо от того, как они были написаны.</span><span class="sxs-lookup"><span data-stu-id="435a5-189">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>

<span data-ttu-id="435a5-190">Спецификации языков C# и Visual Basic включены в документы .NET путем включения источника из репозиториев языка.</span><span class="sxs-lookup"><span data-stu-id="435a5-190">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="435a5-191">Источники Markdown управляются в репозиториях [csharplang](https://github.com/dotnet/csharplang) и [visual basic](https://github.com/dotnet/vblang).</span><span class="sxs-lookup"><span data-stu-id="435a5-191">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [visual basic](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="435a5-192">Ссылки на спецификацию должны указывать на исходные каталоги, в которых включены эти спецификации.</span><span class="sxs-lookup"><span data-stu-id="435a5-192">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="435a5-193">Для C# это **~/_csharplang/spec**, а для VB — **~/_vblang/spec**.</span><span class="sxs-lookup"><span data-stu-id="435a5-193">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**.</span></span>

- <span data-ttu-id="435a5-194">Пример: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` создает [выражения запросов C#](~/_csharplang/spec/expressions.md#query-expressions).</span><span class="sxs-lookup"><span data-stu-id="435a5-194">Example: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` produces [C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions).</span></span>

### <a name="external-links"></a><span data-ttu-id="435a5-195">Внешние ссылки</span><span class="sxs-lookup"><span data-stu-id="435a5-195">External Links</span></span>

<span data-ttu-id="435a5-196">Чтобы создать ссылку на внешний файл, используйте полный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="435a5-196">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="435a5-197">Пример: `[GitHub](https://www.github.com)` создает [GitHub](https://www.github.com).</span><span class="sxs-lookup"><span data-stu-id="435a5-197">Example: `[GitHub](https://www.github.com)` produces [GitHub](https://www.github.com).</span></span>

<span data-ttu-id="435a5-198">Если URL-адрес включается в файл Markdown, он преобразуется в активную ссылку.</span><span class="sxs-lookup"><span data-stu-id="435a5-198">If a URL appears in a Markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="435a5-199">Пример: `<https://www.github.com>` создает <https://www.github.com>.</span><span class="sxs-lookup"><span data-stu-id="435a5-199">Example: `<https://www.github.com>` produces <https://www.github.com>.</span></span>

<span data-ttu-id="435a5-200">Используйте протокол `https` для внешних ссылок.</span><span class="sxs-lookup"><span data-stu-id="435a5-200">Prefer the `https` protocol for external links.</span></span> <span data-ttu-id="435a5-201">Используйте ссылки `http` только для тех сайтов, которые не поддерживают `https`.</span><span class="sxs-lookup"><span data-stu-id="435a5-201">Only use `http` links for sites that do not support `https`.</span></span>

### <a name="links-to-apis"></a><span data-ttu-id="435a5-202">Ссылки на интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="435a5-202">Links to APIs</span></span>

<span data-ttu-id="435a5-203">Система сборки имеет ряд расширений, которые позволяют ссылаться на основные интерфейсы API .NET, не используя внешние ссылки.</span><span class="sxs-lookup"><span data-stu-id="435a5-203">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span>
<span data-ttu-id="435a5-204">Для ссылки на интерфейс API можно использовать его уникальный идентификатор (UID), который формируется автоматически на основе исходного кода.</span><span class="sxs-lookup"><span data-stu-id="435a5-204">When linking to an API, you can use its unique identifier (UID) that is auto-generated from the source code.</span></span>

<span data-ttu-id="435a5-205">Уникальный идентификатор соответствует полному типу и имени члена.</span><span class="sxs-lookup"><span data-stu-id="435a5-205">The UID equates to the fully qualified type and member name.</span></span>

<span data-ttu-id="435a5-206">При добавлении \* (или %2A) после уникального идентификатора ссылка представляет страницу перегрузки, а не конкретный API.</span><span class="sxs-lookup"><span data-stu-id="435a5-206">If you add a \* (or %2A) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="435a5-207">Например, используйте это для ссылки на страницу [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) обычным способом вместо конкретной перегрузки, например [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span><span class="sxs-lookup"><span data-stu-id="435a5-207">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="435a5-208">Также можно использовать \* для ссылки на страницу элемента, если элемент не перегружен. Это позволяет избежать включения списка параметров в уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="435a5-208">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="435a5-209">Чтобы создать ссылку на определенную перегрузку метода, включите полное имя типа каждого из параметров метода.</span><span class="sxs-lookup"><span data-stu-id="435a5-209">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="435a5-210">Например, \<xref:System.DateTime.ToString> ссылается на метод [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) без параметров, а \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> ссылается на метод [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_).</span><span class="sxs-lookup"><span data-stu-id="435a5-210">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span> <span data-ttu-id="435a5-211">Уникальные идентификаторы определенного перегруженного элемента можно найти в `https://xref.docs.microsoft.com/autocomplete`.</span><span class="sxs-lookup"><span data-stu-id="435a5-211">You can find the UIDs of a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="435a5-212">Строка запроса "?text= *\<type-member-name>* " определяет тип или элемент, уникальный идентификатор которого вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="435a5-212">The query string "?text=*\<type-member-name>*" identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="435a5-213">Например, `https://xref.docs.microsoft.com/autocomplete?text=string.format` получает перегрузки [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format).</span><span class="sxs-lookup"><span data-stu-id="435a5-213">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span>

<span data-ttu-id="435a5-214">Чтобы создать ссылку на универсальный тип, например [System.Collections.Generic.ListT\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), используйте символ (%60), за которым следует число параметров универсального типа.</span><span class="sxs-lookup"><span data-stu-id="435a5-214">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (%60) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="435a5-215">Например, \<xref:System.Nullable%601> ссылается на тип [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), а \<xref:System.Func%602> ссылается на делегат [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).</span><span class="sxs-lookup"><span data-stu-id="435a5-215">For example, \<xref:System.Nullable%601> links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while \<xref:System.Func%602> links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

<span data-ttu-id="435a5-216">Можно использовать один из следующих вариантов синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="435a5-216">You can use one of the following syntax:</span></span>

1. <span data-ttu-id="435a5-217">Автоматическая ссылка: `<xref:UID>` или `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="435a5-217">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="435a5-218">Параметр запроса `displayProperty` создает полный текст ссылки.</span><span class="sxs-lookup"><span data-stu-id="435a5-218">The `displayProperty` query    parameter produces a fully qualified link text.</span></span> <span data-ttu-id="435a5-219">По умолчанию текст ссылки показывает только имя элемента или типа.</span><span class="sxs-lookup"><span data-stu-id="435a5-219">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="435a5-220">Ссылка Markdown: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="435a5-220">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="435a5-221">Используется, если вы хотите настроить отображаемый текст ссылки.</span><span class="sxs-lookup"><span data-stu-id="435a5-221">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="435a5-222">Примеры:</span><span class="sxs-lookup"><span data-stu-id="435a5-222">Examples:</span></span>

- <span data-ttu-id="435a5-223">`<xref:System.String>` преобразуется как [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="435a5-223">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="435a5-224">`<xref:System.String?displayProperty=nameWithType>` преобразуется как [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="435a5-224">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="435a5-225">`[String class](xref:System.String)` преобразуется как [класс String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="435a5-225">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="435a5-226">Дополнительные сведения об использовании этой нотации см. в разделе [Использование перекрестных ссылок](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span><span class="sxs-lookup"><span data-stu-id="435a5-226">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="435a5-227">Есть два способа найти уникальный идентификатор:</span><span class="sxs-lookup"><span data-stu-id="435a5-227">There are two ways to find the UID:</span></span>

- <span data-ttu-id="435a5-228">Просмотрите исходный код для страницы API, на которую вы хотите сослаться, и найдите значение ms.assetid.</span><span class="sxs-lookup"><span data-stu-id="435a5-228">View the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="435a5-229">Обратите внимание, что отдельные значения перегрузки не показаны в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="435a5-229">Note that individual overload values are not shown in the source.</span></span>
- <span data-ttu-id="435a5-230">Используйте следующее средство для поиска уникальных идентификаторов: https://xref.docs.microsoft.com/autocomplete?text=tostring (замените tostring на части имени API, который вы пытаетесь найти).</span><span class="sxs-lookup"><span data-stu-id="435a5-230">Use the following tool to search for UIDs: https://xref.docs.microsoft.com/autocomplete?text=tostring (replace tostring with parts of the API name you're trying to find).</span></span> <span data-ttu-id="435a5-231">Средство выполняет поиск указанного параметра запроса `text` в любой части уникального идентификатора.</span><span class="sxs-lookup"><span data-stu-id="435a5-231">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="435a5-232">Например, вы можете искать имя элемента (ToString), частичное имя элемента (ToStri), имя типа и элемента (Double.ToString) и т. д.</span><span class="sxs-lookup"><span data-stu-id="435a5-232">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="435a5-233">Если уникальный идентификатор содержит специальные символы \`, \# или \*, они должны быть представлены в значении идентификатора в кодировке HTML как `%60`, `%23` и `%2A` соответственно.</span><span class="sxs-lookup"><span data-stu-id="435a5-233">When the UID contains the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="435a5-234">Иногда круглые скобки кодируются, но это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="435a5-234">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="435a5-235">Примеры:</span><span class="sxs-lookup"><span data-stu-id="435a5-235">Examples:</span></span>

- <span data-ttu-id="435a5-236">System.Threading.Tasks.Task\`1 преобразуется в `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="435a5-236">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="435a5-237">System.Exception.\#ctor преобразуется в `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="435a5-237">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="435a5-238">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) преобразуется в `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="435a5-238">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

## <a name="lists"></a><span data-ttu-id="435a5-239">Списки</span><span class="sxs-lookup"><span data-stu-id="435a5-239">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="435a5-240">Упорядоченные списки</span><span class="sxs-lookup"><span data-stu-id="435a5-240">Ordered lists</span></span>

1. <span data-ttu-id="435a5-241">Это</span><span class="sxs-lookup"><span data-stu-id="435a5-241">This</span></span>
1. <span data-ttu-id="435a5-242">Пример</span><span class="sxs-lookup"><span data-stu-id="435a5-242">Is</span></span>
1. <span data-ttu-id="435a5-243">Обычного</span><span class="sxs-lookup"><span data-stu-id="435a5-243">An</span></span>
1. <span data-ttu-id="435a5-244">Упорядоченного</span><span class="sxs-lookup"><span data-stu-id="435a5-244">Ordered</span></span>
1. <span data-ttu-id="435a5-245">Списка</span><span class="sxs-lookup"><span data-stu-id="435a5-245">List</span></span>

#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="435a5-246">Упорядоченный список с внедренным списком.</span><span class="sxs-lookup"><span data-stu-id="435a5-246">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="435a5-247">А</span><span class="sxs-lookup"><span data-stu-id="435a5-247">Here</span></span>
1. <span data-ttu-id="435a5-248">это</span><span class="sxs-lookup"><span data-stu-id="435a5-248">comes</span></span>
1. <span data-ttu-id="435a5-249">пример</span><span class="sxs-lookup"><span data-stu-id="435a5-249">an</span></span>
1. <span data-ttu-id="435a5-250">внедренного</span><span class="sxs-lookup"><span data-stu-id="435a5-250">embedded</span></span>
    1. <span data-ttu-id="435a5-251">Мисс Скарлетт</span><span class="sxs-lookup"><span data-stu-id="435a5-251">Miss Scarlett</span></span>
    1. <span data-ttu-id="435a5-252">Профессор Плам</span><span class="sxs-lookup"><span data-stu-id="435a5-252">Professor Plum</span></span>
1. <span data-ttu-id="435a5-253">упорядоченного</span><span class="sxs-lookup"><span data-stu-id="435a5-253">ordered</span></span>
1. <span data-ttu-id="435a5-254">list</span><span class="sxs-lookup"><span data-stu-id="435a5-254">list</span></span>

### <a name="unordered-lists"></a><span data-ttu-id="435a5-255">Неупорядоченные списки</span><span class="sxs-lookup"><span data-stu-id="435a5-255">Unordered Lists</span></span>

- <span data-ttu-id="435a5-256">Вот</span><span class="sxs-lookup"><span data-stu-id="435a5-256">This</span></span>
- <span data-ttu-id="435a5-257">это</span><span class="sxs-lookup"><span data-stu-id="435a5-257">is</span></span>
- <span data-ttu-id="435a5-258">пример</span><span class="sxs-lookup"><span data-stu-id="435a5-258">a</span></span>
- <span data-ttu-id="435a5-259">маркированного</span><span class="sxs-lookup"><span data-stu-id="435a5-259">bulleted</span></span>
- <span data-ttu-id="435a5-260">списка</span><span class="sxs-lookup"><span data-stu-id="435a5-260">list</span></span>

#### <a name="unordered-list-with-an-embedded-list"></a><span data-ttu-id="435a5-261">Неупорядоченный список с внедренным списком</span><span class="sxs-lookup"><span data-stu-id="435a5-261">Unordered list with an embedded list</span></span>

- <span data-ttu-id="435a5-262">Этот</span><span class="sxs-lookup"><span data-stu-id="435a5-262">This</span></span>
- <span data-ttu-id="435a5-263">маркированный</span><span class="sxs-lookup"><span data-stu-id="435a5-263">bulleted</span></span>
- <span data-ttu-id="435a5-264">list</span><span class="sxs-lookup"><span data-stu-id="435a5-264">list</span></span>
  - <span data-ttu-id="435a5-265">Миссис Пикок</span><span class="sxs-lookup"><span data-stu-id="435a5-265">Mrs. Peacock</span></span>
  - <span data-ttu-id="435a5-266">Мистер Грин</span><span class="sxs-lookup"><span data-stu-id="435a5-266">Mr. Green</span></span>
- <span data-ttu-id="435a5-267">содержит</span><span class="sxs-lookup"><span data-stu-id="435a5-267">contains</span></span>
- <span data-ttu-id="435a5-268">другие</span><span class="sxs-lookup"><span data-stu-id="435a5-268">other</span></span>
  1. <span data-ttu-id="435a5-269">Полковник Мастард</span><span class="sxs-lookup"><span data-stu-id="435a5-269">Colonel Mustard</span></span>
  1. <span data-ttu-id="435a5-270">Миссис Уайт</span><span class="sxs-lookup"><span data-stu-id="435a5-270">Mrs. White</span></span>
- <span data-ttu-id="435a5-271">списки</span><span class="sxs-lookup"><span data-stu-id="435a5-271">lists</span></span>

## <a name="horizontal-rule"></a><span data-ttu-id="435a5-272">Горизонтальная линия</span><span class="sxs-lookup"><span data-stu-id="435a5-272">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="435a5-273">Таблицы</span><span class="sxs-lookup"><span data-stu-id="435a5-273">Tables</span></span>

| <span data-ttu-id="435a5-274">Таблицы</span><span class="sxs-lookup"><span data-stu-id="435a5-274">Tables</span></span>        | <span data-ttu-id="435a5-275">Это</span><span class="sxs-lookup"><span data-stu-id="435a5-275">Are</span></span>           | <span data-ttu-id="435a5-276">Здорово</span><span class="sxs-lookup"><span data-stu-id="435a5-276">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="435a5-277">столбец 3</span><span class="sxs-lookup"><span data-stu-id="435a5-277">col 3 is</span></span>      | <span data-ttu-id="435a5-278">выровнен по правому краю</span><span class="sxs-lookup"><span data-stu-id="435a5-278">right-aligned</span></span> | <span data-ttu-id="435a5-279">$1600</span><span class="sxs-lookup"><span data-stu-id="435a5-279">$1600</span></span> |
| <span data-ttu-id="435a5-280">столбец 2</span><span class="sxs-lookup"><span data-stu-id="435a5-280">col 2 is</span></span>      | <span data-ttu-id="435a5-281">выровнен по центру</span><span class="sxs-lookup"><span data-stu-id="435a5-281">centered</span></span>      |   <span data-ttu-id="435a5-282">$12</span><span class="sxs-lookup"><span data-stu-id="435a5-282">$12</span></span> |
| <span data-ttu-id="435a5-283">столбец 1 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="435a5-283">col 1 is default</span></span> | <span data-ttu-id="435a5-284">выровнен по левому краю</span><span class="sxs-lookup"><span data-stu-id="435a5-284">left-aligned</span></span>     |    <span data-ttu-id="435a5-285">$1</span><span class="sxs-lookup"><span data-stu-id="435a5-285">$1</span></span> |

<span data-ttu-id="435a5-286">Для удобства можно использовать [средство создания таблиц Markdown](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="435a5-286">You can use a [Markdown table generator tool](https://www.tablesgenerator.com/markdown_tables) to help creating them more easily.</span></span>

## <a name="code"></a><span data-ttu-id="435a5-287">Код</span><span class="sxs-lookup"><span data-stu-id="435a5-287">Code</span></span>

<span data-ttu-id="435a5-288">Лучший способ добавления кода — включение фрагментов из рабочего образца.</span><span class="sxs-lookup"><span data-stu-id="435a5-288">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="435a5-289">Создайте образец согласно инструкциям в [руководстве по добавлению кода](../CONTRIBUTING.md#contributing-to-samples).</span><span class="sxs-lookup"><span data-stu-id="435a5-289">Create your sample following the instructions in the [contributing guide](../CONTRIBUTING.md#contributing-to-samples).</span></span>

<span data-ttu-id="435a5-290">Код можно включить с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="435a5-290">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- <span data-ttu-id="435a5-291">`-<language>` (*необязательно*, но *рекомендуется*)</span><span class="sxs-lookup"><span data-stu-id="435a5-291">`-<language>` (*optional* but *recommended*)</span></span>
  - <span data-ttu-id="435a5-292">Язык фрагмента кода, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="435a5-292">Language of the code snippet being referenced.</span></span> <span data-ttu-id="435a5-293">Список поддерживаемых значений см. в разделе [Поддерживаемые языки ](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="435a5-293">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

- <span data-ttu-id="435a5-294">`<name>` (*необязательно*)</span><span class="sxs-lookup"><span data-stu-id="435a5-294">`<name>` (*optional*)</span></span>
  - <span data-ttu-id="435a5-295">Имя фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="435a5-295">Name for the code snippet.</span></span> <span data-ttu-id="435a5-296">Оно не влияет на выходные данные HTML, но его можно использовать для повышения удобочитаемости источника Markdown.</span><span class="sxs-lookup"><span data-stu-id="435a5-296">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

- <span data-ttu-id="435a5-297">`<pathToFile>` (*обязательно*)</span><span class="sxs-lookup"><span data-stu-id="435a5-297">`<pathToFile>` (*mandatory*)</span></span>
  - <span data-ttu-id="435a5-298">Относительный путь в файловой системе, указывающий на файл фрагмента кода для ссылки.</span><span class="sxs-lookup"><span data-stu-id="435a5-298">Relative path in the file system that indicates the code snippet file to reference.</span></span>

- <span data-ttu-id="435a5-299">`<queryoption>` и `<queryoptionvalue>` (*необязательно*)</span><span class="sxs-lookup"><span data-stu-id="435a5-299">`<queryoption>` and `<queryoptionvalue>` (*optional*)</span></span>
  - <span data-ttu-id="435a5-300">Используется совместно для указания способа извлечения кода из файла:</span><span class="sxs-lookup"><span data-stu-id="435a5-300">Used together to specify how the code should be retrieved from the file:</span></span>
    - <span data-ttu-id="435a5-301">`#`: `#L{startlinenumber}-L{endlinenumber}` (диапазон строк) *или* `#{tagname}` (имя тега).</span><span class="sxs-lookup"><span data-stu-id="435a5-301">`#`:  `#L{startlinenumber}-L{endlinenumber}` (line range) *or* `#{tagname}` (tag name).</span></span>
    <span data-ttu-id="435a5-302">Мы не рекомендуем использовать номера строк, так отдельные строки слишком отрывочны.</span><span class="sxs-lookup"><span data-stu-id="435a5-302">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="435a5-303">Лучше используйте имя тега для ссылки на фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="435a5-303">Tag name is the preferred way of referencing code snippets.</span></span>
    - <span data-ttu-id="435a5-304">`range`: `?range=1,3-5` Диапазон строк.</span><span class="sxs-lookup"><span data-stu-id="435a5-304">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="435a5-305">Этот пример включает строки 1, 3, 4 и 5.</span><span class="sxs-lookup"><span data-stu-id="435a5-305">This example includes lines 1, 3, 4, and 5.</span></span>
    - <span data-ttu-id="435a5-306">`dedent`: `?dedent=8` Укорачивает строки на число пробелов — в данном случае 8.</span><span class="sxs-lookup"><span data-stu-id="435a5-306">`dedent`: `?dedent=8` Dedents the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="435a5-307">Это можно сочетать с `range` и другими параметрами запросов, которые выбирают подмножество строк файла.</span><span class="sxs-lookup"><span data-stu-id="435a5-307">This can be combined with the `range` and other query options that select a subset of the lines of a file.</span></span>
    - <span data-ttu-id="435a5-308">`outdent`: `?outdent=8` Отменяет отступ строк на число пробелов — в данном случае 8.</span><span class="sxs-lookup"><span data-stu-id="435a5-308">`outdent`: `?outdent=8` Reverses the indent of the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="435a5-309">Это можно сочетать с `range` и другими параметрами запросов, которые выбирают подмножество строк файла.</span><span class="sxs-lookup"><span data-stu-id="435a5-309">This can be combined with `range` and other query options that select a subset of the lines of a file.</span></span>

<span data-ttu-id="435a5-310">По возможности рекомендуется использовать параметр имени тега.</span><span class="sxs-lookup"><span data-stu-id="435a5-310">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="435a5-311">Имя тега — это имя региона или комментария к коду в формате `Snippettagname`, присутствующее в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="435a5-311">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="435a5-312">В приведенном ниже примере показано, как ссылаться на имя тега `1`:</span><span class="sxs-lookup"><span data-stu-id="435a5-312">The following example shows how to refer to the tag name `1`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

<span data-ttu-id="435a5-313">Вы видите, как фрагменты кода структурированы в [этом исходном файле](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span><span class="sxs-lookup"><span data-stu-id="435a5-313">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span></span> <span data-ttu-id="435a5-314">Дополнительные сведения о представлении имени тега в исходных файлах фрагментов кода по языку см. в [руководстве по DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span><span class="sxs-lookup"><span data-stu-id="435a5-314">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="435a5-315">Включение фрагментов из полных программ обеспечивает выполнение всего кода в нашей системе непрерывной интеграции (CI).</span><span class="sxs-lookup"><span data-stu-id="435a5-315">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="435a5-316">Однако если вам нужно показать фрагмент, который вызывает ошибки во время компиляции или выполнения, вы можете использовать встроенные блоки кода.</span><span class="sxs-lookup"><span data-stu-id="435a5-316">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

### <a name="inline-code-blocks-with-language-identifier"></a><span data-ttu-id="435a5-317">Встроенные блоки кода с идентификатором языка</span><span class="sxs-lookup"><span data-stu-id="435a5-317">Inline code blocks with language identifier</span></span>

<span data-ttu-id="435a5-318">Чтобы применить к блоку кода цветовое выделение синтаксиса, характерное для данного языка, используйте три обратных апострофа (\`\`\`) и идентификатор языка.</span><span class="sxs-lookup"><span data-stu-id="435a5-318">Use three backticks (\`\`\`) + a language ID to apply language-specific color coding to a code block.</span></span> <span data-ttu-id="435a5-319">Ниже приведен список поддерживаемых языков, в которых отображается метка Markdown для каждого идентификатора языка.</span><span class="sxs-lookup"><span data-stu-id="435a5-319">Here is the list of supported languages showing the markdown label for each language ID.</span></span>

#### <a name="supported-languages"></a><span data-ttu-id="435a5-320">Поддерживаемые языки</span><span class="sxs-lookup"><span data-stu-id="435a5-320">Supported languages</span></span>

|<span data-ttu-id="435a5-321">ИМЯ</span><span class="sxs-lookup"><span data-stu-id="435a5-321">Name</span></span>|<span data-ttu-id="435a5-322">Метка Markdown</span><span class="sxs-lookup"><span data-stu-id="435a5-322">Markdown label</span></span>|
|-----|-------|
|<span data-ttu-id="435a5-323">Консоль .NET</span><span class="sxs-lookup"><span data-stu-id="435a5-323">.NET Console</span></span>|<span data-ttu-id="435a5-324">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="435a5-324">dotnetcli</span></span>|
|<span data-ttu-id="435a5-325">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="435a5-325">ASP.NET (C#)</span></span>|<span data-ttu-id="435a5-326">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="435a5-326">aspx-csharp</span></span>|
|<span data-ttu-id="435a5-327">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="435a5-327">ASP.NET (VB)</span></span>|<span data-ttu-id="435a5-328">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="435a5-328">aspx-vb</span></span>|
|<span data-ttu-id="435a5-329">Инфраструктура CLI Azure</span><span class="sxs-lookup"><span data-stu-id="435a5-329">Azure CLI</span></span>|<span data-ttu-id="435a5-330">azurecli</span><span class="sxs-lookup"><span data-stu-id="435a5-330">azurecli</span></span>|
|<span data-ttu-id="435a5-331">AzCopy</span><span class="sxs-lookup"><span data-stu-id="435a5-331">AzCopy</span></span>|<span data-ttu-id="435a5-332">azcopy</span><span class="sxs-lookup"><span data-stu-id="435a5-332">azcopy</span></span>|
|<span data-ttu-id="435a5-333">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="435a5-333">Azure PowerShell</span></span>|<span data-ttu-id="435a5-334">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="435a5-334">azurepowershell</span></span>|
|<span data-ttu-id="435a5-335">Bash</span><span class="sxs-lookup"><span data-stu-id="435a5-335">Bash</span></span>|<span data-ttu-id="435a5-336">bash</span><span class="sxs-lookup"><span data-stu-id="435a5-336">bash</span></span>|
|<span data-ttu-id="435a5-337">C++</span><span class="sxs-lookup"><span data-stu-id="435a5-337">C++</span></span>|<span data-ttu-id="435a5-338">cpp</span><span class="sxs-lookup"><span data-stu-id="435a5-338">cpp</span></span>|
|<span data-ttu-id="435a5-339">C++/CX</span><span class="sxs-lookup"><span data-stu-id="435a5-339">C++/CX</span></span>|<span data-ttu-id="435a5-340">cppcx</span><span class="sxs-lookup"><span data-stu-id="435a5-340">cppcx</span></span>|
|<span data-ttu-id="435a5-341">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="435a5-341">C++/WinRT</span></span>|<span data-ttu-id="435a5-342">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="435a5-342">cppwinrt</span></span>|
|<span data-ttu-id="435a5-343">C#</span><span class="sxs-lookup"><span data-stu-id="435a5-343">C#</span></span>|<span data-ttu-id="435a5-344">csharp</span><span class="sxs-lookup"><span data-stu-id="435a5-344">csharp</span></span>|
|<span data-ttu-id="435a5-345">C# в браузере</span><span class="sxs-lookup"><span data-stu-id="435a5-345">C# in browser</span></span>|<span data-ttu-id="435a5-346">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="435a5-346">csharp-interactive</span></span>|
|<span data-ttu-id="435a5-347">Консоль</span><span class="sxs-lookup"><span data-stu-id="435a5-347">Console</span></span>|<span data-ttu-id="435a5-348">console</span><span class="sxs-lookup"><span data-stu-id="435a5-348">console</span></span>|
|<span data-ttu-id="435a5-349">CSHTML</span><span class="sxs-lookup"><span data-stu-id="435a5-349">CSHTML</span></span>|<span data-ttu-id="435a5-350">cshtml</span><span class="sxs-lookup"><span data-stu-id="435a5-350">cshtml</span></span>|
|<span data-ttu-id="435a5-351">DAX</span><span class="sxs-lookup"><span data-stu-id="435a5-351">DAX</span></span>|<span data-ttu-id="435a5-352">dax</span><span class="sxs-lookup"><span data-stu-id="435a5-352">dax</span></span>|
|<span data-ttu-id="435a5-353">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="435a5-353">Dockerfile</span></span>|<span data-ttu-id="435a5-354">dockerfile</span><span class="sxs-lookup"><span data-stu-id="435a5-354">dockerfile</span></span>|
|<span data-ttu-id="435a5-355">F#</span><span class="sxs-lookup"><span data-stu-id="435a5-355">F#</span></span>|<span data-ttu-id="435a5-356">fsharp</span><span class="sxs-lookup"><span data-stu-id="435a5-356">fsharp</span></span>|
|<span data-ttu-id="435a5-357">Go</span><span class="sxs-lookup"><span data-stu-id="435a5-357">Go</span></span>|<span data-ttu-id="435a5-358">go</span><span class="sxs-lookup"><span data-stu-id="435a5-358">go</span></span>|
|<span data-ttu-id="435a5-359">HTML</span><span class="sxs-lookup"><span data-stu-id="435a5-359">HTML</span></span>|<span data-ttu-id="435a5-360">html</span><span class="sxs-lookup"><span data-stu-id="435a5-360">html</span></span>|
|<span data-ttu-id="435a5-361">HTTP</span><span class="sxs-lookup"><span data-stu-id="435a5-361">HTTP</span></span>|<span data-ttu-id="435a5-362">http</span><span class="sxs-lookup"><span data-stu-id="435a5-362">http</span></span>|
|<span data-ttu-id="435a5-363">Java</span><span class="sxs-lookup"><span data-stu-id="435a5-363">Java</span></span>|<span data-ttu-id="435a5-364">java</span><span class="sxs-lookup"><span data-stu-id="435a5-364">java</span></span>|
|<span data-ttu-id="435a5-365">JavaScript</span><span class="sxs-lookup"><span data-stu-id="435a5-365">JavaScript</span></span>|<span data-ttu-id="435a5-366">javascript</span><span class="sxs-lookup"><span data-stu-id="435a5-366">javascript</span></span>|
|<span data-ttu-id="435a5-367">JSON</span><span class="sxs-lookup"><span data-stu-id="435a5-367">JSON</span></span>|<span data-ttu-id="435a5-368">json</span><span class="sxs-lookup"><span data-stu-id="435a5-368">json</span></span>|
|<span data-ttu-id="435a5-369">Язык запросов Kusto</span><span class="sxs-lookup"><span data-stu-id="435a5-369">Kusto Query Language</span></span>|<span data-ttu-id="435a5-370">kusto</span><span class="sxs-lookup"><span data-stu-id="435a5-370">kusto</span></span>|
|<span data-ttu-id="435a5-371">Разметка Markdown</span><span class="sxs-lookup"><span data-stu-id="435a5-371">Markdown</span></span>|<span data-ttu-id="435a5-372">md</span><span class="sxs-lookup"><span data-stu-id="435a5-372">md</span></span>|
|<span data-ttu-id="435a5-373">Node.js</span><span class="sxs-lookup"><span data-stu-id="435a5-373">NodeJS</span></span>|<span data-ttu-id="435a5-374">nodejs</span><span class="sxs-lookup"><span data-stu-id="435a5-374">nodejs</span></span>|
|<span data-ttu-id="435a5-375">Objective-C</span><span class="sxs-lookup"><span data-stu-id="435a5-375">Objective-C</span></span>|<span data-ttu-id="435a5-376">objc</span><span class="sxs-lookup"><span data-stu-id="435a5-376">objc</span></span>|
|<span data-ttu-id="435a5-377">OData</span><span class="sxs-lookup"><span data-stu-id="435a5-377">OData</span></span>|<span data-ttu-id="435a5-378">odata</span><span class="sxs-lookup"><span data-stu-id="435a5-378">odata</span></span>|
|<span data-ttu-id="435a5-379">PHP</span><span class="sxs-lookup"><span data-stu-id="435a5-379">PHP</span></span>|<span data-ttu-id="435a5-380">php</span><span class="sxs-lookup"><span data-stu-id="435a5-380">php</span></span>|
|<span data-ttu-id="435a5-381">PowerApps (десятичный разделитель — точка)</span><span class="sxs-lookup"><span data-stu-id="435a5-381">PowerApps (dot decimal separator)</span></span>|<span data-ttu-id="435a5-382">powerapps-dot</span><span class="sxs-lookup"><span data-stu-id="435a5-382">powerapps-dot</span></span>|
|<span data-ttu-id="435a5-383">PowerApps (десятичный разделитель — запятая)</span><span class="sxs-lookup"><span data-stu-id="435a5-383">PowerApps (comma decimal separator)</span></span>|<span data-ttu-id="435a5-384">powerapps-comma</span><span class="sxs-lookup"><span data-stu-id="435a5-384">powerapps-comma</span></span>|
|<span data-ttu-id="435a5-385">PowerShell</span><span class="sxs-lookup"><span data-stu-id="435a5-385">PowerShell</span></span>|<span data-ttu-id="435a5-386">powershell</span><span class="sxs-lookup"><span data-stu-id="435a5-386">powershell</span></span>|
|<span data-ttu-id="435a5-387">Python</span><span class="sxs-lookup"><span data-stu-id="435a5-387">Python</span></span>|<span data-ttu-id="435a5-388">python</span><span class="sxs-lookup"><span data-stu-id="435a5-388">python</span></span>|
|<span data-ttu-id="435a5-389">Q#</span><span class="sxs-lookup"><span data-stu-id="435a5-389">Q#</span></span>|<span data-ttu-id="435a5-390">qsharp</span><span class="sxs-lookup"><span data-stu-id="435a5-390">qsharp</span></span>|
|<span data-ttu-id="435a5-391">R</span><span class="sxs-lookup"><span data-stu-id="435a5-391">R</span></span>|<span data-ttu-id="435a5-392">r</span><span class="sxs-lookup"><span data-stu-id="435a5-392">r</span></span>|
|<span data-ttu-id="435a5-393">Ruby</span><span class="sxs-lookup"><span data-stu-id="435a5-393">Ruby</span></span>|<span data-ttu-id="435a5-394">ruby</span><span class="sxs-lookup"><span data-stu-id="435a5-394">ruby</span></span>|
|<span data-ttu-id="435a5-395">SQL</span><span class="sxs-lookup"><span data-stu-id="435a5-395">SQL</span></span>|<span data-ttu-id="435a5-396">sql</span><span class="sxs-lookup"><span data-stu-id="435a5-396">sql</span></span>|
|<span data-ttu-id="435a5-397">Swift</span><span class="sxs-lookup"><span data-stu-id="435a5-397">Swift</span></span>|<span data-ttu-id="435a5-398">swift</span><span class="sxs-lookup"><span data-stu-id="435a5-398">swift</span></span>|
|<span data-ttu-id="435a5-399">TypeScript</span><span class="sxs-lookup"><span data-stu-id="435a5-399">TypeScript</span></span>|<span data-ttu-id="435a5-400">typescript</span><span class="sxs-lookup"><span data-stu-id="435a5-400">typescript</span></span>|
|<span data-ttu-id="435a5-401">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="435a5-401">Visual Basic</span></span>|<span data-ttu-id="435a5-402">vb</span><span class="sxs-lookup"><span data-stu-id="435a5-402">vb</span></span>|
|<span data-ttu-id="435a5-403">VBScript</span><span class="sxs-lookup"><span data-stu-id="435a5-403">VBScript</span></span>|<span data-ttu-id="435a5-404">vbscript</span><span class="sxs-lookup"><span data-stu-id="435a5-404">vbscript</span></span>|
|<span data-ttu-id="435a5-405">XAML</span><span class="sxs-lookup"><span data-stu-id="435a5-405">XAML</span></span>|<span data-ttu-id="435a5-406">xaml</span><span class="sxs-lookup"><span data-stu-id="435a5-406">xaml</span></span>|
|<span data-ttu-id="435a5-407">XML</span><span class="sxs-lookup"><span data-stu-id="435a5-407">XML</span></span>|<span data-ttu-id="435a5-408">Xml</span><span class="sxs-lookup"><span data-stu-id="435a5-408">xml</span></span>|

<span data-ttu-id="435a5-409">Имя `csharp-interactive` указывает язык C# и возможность запуска примеров из браузера.</span><span class="sxs-lookup"><span data-stu-id="435a5-409">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="435a5-410">Эти фрагменты кода компилируются и выполняются в контейнере Docker, и результаты выполнения программы отображаются в окне браузера пользователя.</span><span class="sxs-lookup"><span data-stu-id="435a5-410">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

<span data-ttu-id="435a5-411">Ниже приведены примеры блоков кода с использованием идентификаторов языков для C# (\`\`\`csharp), Python (\`\`\`python) и PowerShell (\`\`\`powershell).</span><span class="sxs-lookup"><span data-stu-id="435a5-411">The following are examples of code blocks using the language IDs for C# (\`\`\`csharp), Python (\`\`\`python), and PowerShell (\`\`\`powershell).</span></span>

##### <a name="c9839"></a><span data-ttu-id="435a5-412">C&#9839;</span><span class="sxs-lookup"><span data-stu-id="435a5-412">C&#9839;</span></span>

```csharp
using System;
namespace HelloWorld
{
    class Hello
    {
        static void Main()
        {
            Console.WriteLine("Hello World!");

            // Keep the console window open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

#### <a name="python"></a><span data-ttu-id="435a5-413">Python</span><span class="sxs-lookup"><span data-stu-id="435a5-413">Python</span></span>

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a><span data-ttu-id="435a5-414">PowerShell</span><span class="sxs-lookup"><span data-stu-id="435a5-414">PowerShell</span></span>

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a><span data-ttu-id="435a5-415">Общий блок кода</span><span class="sxs-lookup"><span data-stu-id="435a5-415">Generic code block</span></span>

<span data-ttu-id="435a5-416">Для общего выделения синтаксиса в блоке кода используйте три обратных апострофа (&#96;&#96;&#96;).</span><span class="sxs-lookup"><span data-stu-id="435a5-416">Use three backticks (&#96;&#96;&#96;) for generic code block coding.</span></span>

> <span data-ttu-id="435a5-417">Рекомендуемым подходом является использование блоков кода с идентификаторами языков, как описано в предыдущем разделе, для обеспечения правильного выделения синтаксиса на сайте документации.</span><span class="sxs-lookup"><span data-stu-id="435a5-417">The recommended approach is to use code blocks with language identifiers as explained in the previous section to ensure the proper syntax highlighting in the documentation site.</span></span> <span data-ttu-id="435a5-418">Используйте общие блоки кода только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="435a5-418">Use generic code blocks only when necessary.</span></span>

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a><span data-ttu-id="435a5-419">Блок цитирования</span><span class="sxs-lookup"><span data-stu-id="435a5-419">Blockquotes</span></span>

> <span data-ttu-id="435a5-420">Засуха продолжалась десять миллионов лет, и царству ужасных ящеров уже давно пришел конец.</span><span class="sxs-lookup"><span data-stu-id="435a5-420">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="435a5-421">Здесь, близ экватора, на материке, который позднее назовут Африкой, с новой яростью вспыхнула борьба за существование, и еще не ясно было, кто выйдет из нее победителем.</span><span class="sxs-lookup"><span data-stu-id="435a5-421">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="435a5-422">На этой бесплодной, иссушенной зноем земле благоденствовать или хотя бы просто выжить могли только маленькие, или ловкие, или свирепые.</span><span class="sxs-lookup"><span data-stu-id="435a5-422">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="435a5-423">Изображения</span><span class="sxs-lookup"><span data-stu-id="435a5-423">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="435a5-424">Статическое изображение или анимационный GIF</span><span class="sxs-lookup"><span data-stu-id="435a5-424">Static Image or Animated gif</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![это замещающий текст](../images/Logo_DotNet.png)

### <a name="linked-image"></a><span data-ttu-id="435a5-426">Связанное изображение</span><span class="sxs-lookup"><span data-stu-id="435a5-426">Linked Image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

<span data-ttu-id="435a5-427">[![замещающий текст для связанного изображения](../images/Logo_DotNet.png)](https://dot.net)</span><span class="sxs-lookup"><span data-stu-id="435a5-427">[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)</span></span>

## <a name="videos"></a><span data-ttu-id="435a5-428">Видео</span><span class="sxs-lookup"><span data-stu-id="435a5-428">Videos</span></span>

<span data-ttu-id="435a5-429">В настоящее время вы можете внедрить видео Channel 9 и YouTube с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="435a5-429">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="435a5-430">Канал 9</span><span class="sxs-lookup"><span data-stu-id="435a5-430">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="435a5-431">Чтобы получить правильный URL-адрес видео, выберите вкладку **Внедрить** под видеокадром и скопируйте URL-адрес из элемента `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="435a5-431">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="435a5-432">Например:</span><span class="sxs-lookup"><span data-stu-id="435a5-432">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="435a5-433">YouTube</span><span class="sxs-lookup"><span data-stu-id="435a5-433">YouTube</span></span>

<span data-ttu-id="435a5-434">Чтобы получить правильный URL-адрес видео, щелкните видео правой кнопкой мыши, выберите **Копировать код внедрения** и скопируйте URL-адрес из элемента `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="435a5-434">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="435a5-435">Например:</span><span class="sxs-lookup"><span data-stu-id="435a5-435">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="435a5-436">Расширения docs.microsoft</span><span class="sxs-lookup"><span data-stu-id="435a5-436">docs.microsoft extensions</span></span>

<span data-ttu-id="435a5-437">docs.microsoft предоставляет несколько дополнительных расширений для GitHub Flavored Markdown.</span><span class="sxs-lookup"><span data-stu-id="435a5-437">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="alerts"></a><span data-ttu-id="435a5-438">Оповещения</span><span class="sxs-lookup"><span data-stu-id="435a5-438">Alerts</span></span>

<span data-ttu-id="435a5-439">Необходимо использовать показанные ниже стили оповещений, чтобы они правильно отображались на сайте документации.</span><span class="sxs-lookup"><span data-stu-id="435a5-439">It's important to use the following alert styles so they render with the proper style in the documentation site.</span></span> <span data-ttu-id="435a5-440">Однако модуль отрисовки GitHub не различает их.</span><span class="sxs-lookup"><span data-stu-id="435a5-440">However, the rendering engine on GitHub doesn't diferentiate them.</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="435a5-441">Отображение будет таким: ![Стили оповещений](../images/alerts.png)</span><span class="sxs-lookup"><span data-stu-id="435a5-441">And they'll render like this: ![Alert styles](../images/alerts.png)</span></span>

### <a name="includes"></a><span data-ttu-id="435a5-442">Включает</span><span class="sxs-lookup"><span data-stu-id="435a5-442">Includes</span></span>

<span data-ttu-id="435a5-443">Вы можете внедрить Markdown одного файла в другой, используя include.</span><span class="sxs-lookup"><span data-stu-id="435a5-443">You can embed the Markdown of one file into another using an include.</span></span>

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a><span data-ttu-id="435a5-444">Отмеченные списки</span><span class="sxs-lookup"><span data-stu-id="435a5-444">Checked lists</span></span>

<span data-ttu-id="435a5-445">Пользовательский стиль доступен для списков.</span><span class="sxs-lookup"><span data-stu-id="435a5-445">A custom style is available for lists.</span></span> <span data-ttu-id="435a5-446">Можно отобразить списки с зелеными галочками.</span><span class="sxs-lookup"><span data-stu-id="435a5-446">You can render lists with green check marks.</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="435a5-447">как создать приложение .NET Core;</span><span class="sxs-lookup"><span data-stu-id="435a5-447">How to create a .NET Core app</span></span>
> - <span data-ttu-id="435a5-448">как добавить ссылку на пакет Microsoft.XmlSerializer.Generator;</span><span class="sxs-lookup"><span data-stu-id="435a5-448">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="435a5-449">как изменить MyApp.csproj для добавления зависимостей;</span><span class="sxs-lookup"><span data-stu-id="435a5-449">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="435a5-450">как добавить класс и XmlSerializer;</span><span class="sxs-lookup"><span data-stu-id="435a5-450">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="435a5-451">как собрать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="435a5-451">How to build and run the application</span></span>

<span data-ttu-id="435a5-452">Пример отмеченных списков в действии см. в [документации по .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span><span class="sxs-lookup"><span data-stu-id="435a5-452">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="435a5-453">Кнопки</span><span class="sxs-lookup"><span data-stu-id="435a5-453">Buttons</span></span>

> [!div class="button"]
> [<span data-ttu-id="435a5-454">ссылки кнопок</span><span class="sxs-lookup"><span data-stu-id="435a5-454">button links</span></span>](../docs/core/index.md)

<span data-ttu-id="435a5-455">Примеры кнопок в действии можно увидеть в [документации по Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="435a5-455">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="selectors"></a><span data-ttu-id="435a5-456">Селекторы</span><span class="sxs-lookup"><span data-stu-id="435a5-456">Selectors</span></span>

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

<span data-ttu-id="435a5-459">Примеры селекторов в действии можно увидеть в [документации по Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span><span class="sxs-lookup"><span data-stu-id="435a5-459">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="435a5-460">Пошаговые инструкции</span><span class="sxs-lookup"><span data-stu-id="435a5-460">Step-By-Steps</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="435a5-461">[Назад](../docs/csharp/expression-trees-interpreting.md)
>[Вперед](../docs/csharp/expression-trees-translating.md)</span><span class="sxs-lookup"><span data-stu-id="435a5-461">[Previous](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)</span></span>

<span data-ttu-id="435a5-462">Примеры пошаговых операций можно увидеть в [руководстве по C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span><span class="sxs-lookup"><span data-stu-id="435a5-462">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
