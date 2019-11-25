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
ms.openlocfilehash: ed9fd55fd84606d2083e0576581391331769a1e6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089279"
---
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="df018-102">Шаблон метаданных и разметки Markdown</span><span class="sxs-lookup"><span data-stu-id="df018-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="df018-103">Этот шаблон dotnet/docs содержит примеры синтаксиса Markdown, а также указания по заданию метаданных.</span><span class="sxs-lookup"><span data-stu-id="df018-103">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="df018-104">Для максимально эффективного использования просмотрите [необработанный Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) и [отрисованное представление](https://github.com/dotnet/docs/blob/master/styleguide/template.md).</span><span class="sxs-lookup"><span data-stu-id="df018-104">To get the most of it, you must view both the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) and the [rendered view](https://github.com/dotnet/docs/blob/master/styleguide/template.md).</span></span>

<span data-ttu-id="df018-105">При создании файла Markdown следует скопировать этот шаблон в новый файл, заполнить метаданные, как указано ниже, задать заголовок H1 в соответствии с названием статьи и удалить содержимое.</span><span class="sxs-lookup"><span data-stu-id="df018-105">When creating a Markdown file, you should copy this template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span>

## <a name="metadata"></a><span data-ttu-id="df018-106">Metadata</span><span class="sxs-lookup"><span data-stu-id="df018-106">Metadata</span></span>

<span data-ttu-id="df018-107">Полный блок метаданных (в [необработанной разметке Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)) разделен на четыре обязательных поля и необязательные поля.</span><span class="sxs-lookup"><span data-stu-id="df018-107">The full metadata block is above (in the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), divided into required fields and optional fields.</span></span> <span data-ttu-id="df018-108">Ключевые замечания:</span><span class="sxs-lookup"><span data-stu-id="df018-108">Some key notes:</span></span>

- <span data-ttu-id="df018-109">Между двоеточием (:) и значением элемента метаданных **должен** быть пробел.</span><span class="sxs-lookup"><span data-stu-id="df018-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="df018-110">Если необязательный элемент метаданных не имеет значения, закомментируйте элемент символом # или удалите его (не оставляйте его пустым и не используйте "НД").</span><span class="sxs-lookup"><span data-stu-id="df018-110">If an optional metadata element doesn't have a value, comment out the element with a # or remove it (don't leave it blank or use "na").</span></span> <span data-ttu-id="df018-111">Если вы добавляете значение к элементу, который был закомментирован, не забудьте удалить #.</span><span class="sxs-lookup"><span data-stu-id="df018-111">If you're adding a value to an element that was commented out, be sure to remove the #.</span></span>
- <span data-ttu-id="df018-112">Двоеточия в значении (например, названии) нарушают работу средства анализа метаданных.</span><span class="sxs-lookup"><span data-stu-id="df018-112">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="df018-113">В этом случае заключите название в двойные кавычки (например, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="df018-113">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="df018-114">Поле **title**. Отображается в результатах поисковой системы.</span><span class="sxs-lookup"><span data-stu-id="df018-114">**title**: Appears in search engine results.</span></span> <span data-ttu-id="df018-115">Заголовок не обязательно должен совпадать с названием в заголовке H1 и должен содержать не более 60 символов.</span><span class="sxs-lookup"><span data-stu-id="df018-115">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="df018-116">**description**: содержит сводку по содержимому статьи.</span><span class="sxs-lookup"><span data-stu-id="df018-116">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="df018-117">Обычно отображается на странице результатов поиска, но не используется для ранжирования поиска.</span><span class="sxs-lookup"><span data-stu-id="df018-117">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="df018-118">Его длина должна составлять 115–145 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="df018-118">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="df018-119">**author** и **ms.author**: поле author должно содержать **имя пользователя GitHub**, принадлежащее автору, а не его псевдоним.</span><span class="sxs-lookup"><span data-stu-id="df018-119">**author** and **ms.author**: The author field should contain the **GitHub username** of the author, not his/her alias.</span></span>  <span data-ttu-id="df018-120">Поле **ms.author**, с другой стороны, должно содержать псевдоним Майкрософт и указывает лицо, ответственное за сопровождение статьи.</span><span class="sxs-lookup"><span data-stu-id="df018-120">The **ms.author** field, on the other hand, should contain a Microsoft alias and indicates the person responsible for maintaining the article.</span></span>
- <span data-ttu-id="df018-121">**ms.topic**: тип раздела.</span><span class="sxs-lookup"><span data-stu-id="df018-121">**ms.topic**: The topic type.</span></span> <span data-ttu-id="df018-122">Наиболее распространенное значение — `conceptual`. Оно устанавливается на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="df018-122">The most common value is `conceptual` and is set at a global level.</span></span> <span data-ttu-id="df018-123">Используются и другие распространенные значения: `tutorial`, `overview` и `reference`.</span><span class="sxs-lookup"><span data-stu-id="df018-123">Other common values used are `tutorial`, `overview`, and `reference`.</span></span>
- <span data-ttu-id="df018-124">**dev_langs** определяет языковой фильтр, отображаемый для раздела.</span><span class="sxs-lookup"><span data-stu-id="df018-124">**dev_langs** defines the language filter displayed for the topic.</span></span> <span data-ttu-id="df018-125">Список поддерживаемых значений можно просмотреть в разделе [Поддерживаемые языки](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="df018-125">You can see a list of the supported values in the [Supported languages](#supported-languages) section.</span></span> <span data-ttu-id="df018-126">Необходимо устанавливать только в том случае, если в разделе содержится более одного языка программирования.</span><span class="sxs-lookup"><span data-stu-id="df018-126">Only needs to be set when there's more than one programming language covered in the topic.</span></span> <span data-ttu-id="df018-127">Как правило, для этого значения в содержимом используются только `csharp`, `vb`, `fsharp` и `cpp`.</span><span class="sxs-lookup"><span data-stu-id="df018-127">Typically, we only use `csharp`, `vb`, `fsharp`, and `cpp` for this value in our content.</span></span>
- <span data-ttu-id="df018-128">**ms.prod**: идентификатор продукта, используемый для бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="df018-128">**ms.prod**: Product identification used for BI purposes.</span></span> <span data-ttu-id="df018-129">Обычно они устанавливаются на глобальном уровне, поэтому не отображаются в блоке метаданных каждой статьи.</span><span class="sxs-lookup"><span data-stu-id="df018-129">They're usually set at a global level, so they don't usually appear in the metadata block of each article.</span></span>
- <span data-ttu-id="df018-130">**ms.technology**: дополнительная классификация бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="df018-130">**ms.technology**: Additional BI classification.</span></span> <span data-ttu-id="df018-131">Некоторые из поддерживаемых значений: `devlang-csharp` для разделов по C#, `devlang-fsharp` для разделов по F# и `devlang-visual-basic` для разделов по VB.</span><span class="sxs-lookup"><span data-stu-id="df018-131">Some of the supported values are: `devlang-csharp` for C# topics, `devlang-fsharp` for F# topics, and `devlang-visual-basic` for VB topics.</span></span> <span data-ttu-id="df018-132">Для других руководств значения будут различаться, поэтому обратитесь к участнику группы за рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="df018-132">For other guides, the values will vary, so ask a member of the team for guidance.</span></span>
- <span data-ttu-id="df018-133">**ms.date**: дата в формате MM/ДД/ГГГГ.</span><span class="sxs-lookup"><span data-stu-id="df018-133">**ms.date**: A date in the format MM/dd/yyyy.</span></span> <span data-ttu-id="df018-134">Отображается на опубликованной странице, чтобы указать время последнего существенного изменения статьи или гарантировать ее актуальность (то есть статья была проверена и признана актуальной).</span><span class="sxs-lookup"><span data-stu-id="df018-134">Displayed on the published page to indicate the last time the article was substantially edited or guaranteed "fresh" (that is, the article was reviewed and considered up-to-date).</span></span>
- <span data-ttu-id="df018-135">**helpviewer_keywords**: Записи используются для автономного индексирования книг (функция в Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="df018-135">**helpviewer_keywords**: Entries are used for the offline books index (functionality in Visual Studio).</span></span>
- <span data-ttu-id="df018-136">**f1_keywords**: Подключает статью к клавише F1 (функция в Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="df018-136">**f1_keywords**: Connects the article to the F1 key (functionality in Visual Studio).</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="df018-137">Базовая разметка Markdown, GFM и специальные символы</span><span class="sxs-lookup"><span data-stu-id="df018-137">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="df018-138">Поддерживаются все возможности базовой разметки Markdown и GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="df018-138">All basic and GitHub Flavored Markdown (GFM) is supported.</span></span> <span data-ttu-id="df018-139">Дополнительные сведения см. в следующих ресурсах.</span><span class="sxs-lookup"><span data-stu-id="df018-139">For more information on these, see:</span></span>

- [<span data-ttu-id="df018-140">Базовый синтаксис Markdown</span><span class="sxs-lookup"><span data-stu-id="df018-140">Baseline Markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="df018-141">Документация GFM</span><span class="sxs-lookup"><span data-stu-id="df018-141">GFM documentation</span></span>](https://guides.github.com/features/mastering-markdown)

<span data-ttu-id="df018-142">Для форматирования в Markdown используются специальные символы, такие как \*, \` и \#.</span><span class="sxs-lookup"><span data-stu-id="df018-142">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="df018-143">Если вы хотите включить в содержимое один из этих символов, нужно выполнить одно из двух действий:</span><span class="sxs-lookup"><span data-stu-id="df018-143">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="df018-144">поставить обратную косую черту перед специальным символом для его экранирования (например, `\*` для символа \*);</span><span class="sxs-lookup"><span data-stu-id="df018-144">Put a backslash before the special character to "escape" it (for example, `\*` for an \*)</span></span>
- <span data-ttu-id="df018-145">использовать [код сущности HTML](https://www.ascii.cl/htmlcodes.htm) для символа (например, `&#42;` для &#42;).</span><span class="sxs-lookup"><span data-stu-id="df018-145">Use the [HTML entity code](https://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for an &#42;).</span></span>

## <a name="file-name"></a><span data-ttu-id="df018-146">Имя файла</span><span class="sxs-lookup"><span data-stu-id="df018-146">File name</span></span>

<span data-ttu-id="df018-147">В отношении имен файлов действуют указанные ниже правила.</span><span class="sxs-lookup"><span data-stu-id="df018-147">File names use the following rules:</span></span>

- <span data-ttu-id="df018-148">Содержат только строчные буквы, цифры и дефисы.</span><span class="sxs-lookup"><span data-stu-id="df018-148">Contain only lowercase letters, numbers, and hyphens.</span></span>
- <span data-ttu-id="df018-149">Пробелы и знаки препинания недопустимы.</span><span class="sxs-lookup"><span data-stu-id="df018-149">No spaces or punctuation characters.</span></span> <span data-ttu-id="df018-150">Для разделения слов и чисел в именах файлов используйте дефисы.</span><span class="sxs-lookup"><span data-stu-id="df018-150">Use the hyphens to separate words and numbers in the file name.</span></span>
- <span data-ttu-id="df018-151">Для обозначения действий используйте глаголы, например develop, buy, build, troubleshoot.</span><span class="sxs-lookup"><span data-stu-id="df018-151">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="df018-152">Не используйте суффикс -ing.</span><span class="sxs-lookup"><span data-stu-id="df018-152">No -ing words.</span></span>
- <span data-ttu-id="df018-153">Не используйте служебные слова, такие как a, and, the, in, or и т. д.</span><span class="sxs-lookup"><span data-stu-id="df018-153">No small words - don't include a, and, the, in, or, etc.</span></span>
- <span data-ttu-id="df018-154">Необходимо использовать формат Markdown и расширение имени файла .md.</span><span class="sxs-lookup"><span data-stu-id="df018-154">Must be in Markdown and use the .md file extension.</span></span>
- <span data-ttu-id="df018-155">Имена файлов не должны быть слишком длинными.</span><span class="sxs-lookup"><span data-stu-id="df018-155">Keep file names reasonably short.</span></span> <span data-ttu-id="df018-156">Они являются частью URL-адресов статей.</span><span class="sxs-lookup"><span data-stu-id="df018-156">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="df018-157">Заголовки</span><span class="sxs-lookup"><span data-stu-id="df018-157">Headings</span></span>

<span data-ttu-id="df018-158">Прописные буквы следует использовать как в предложениях.</span><span class="sxs-lookup"><span data-stu-id="df018-158">Use sentence-style capitalization.</span></span> <span data-ttu-id="df018-159">Используйте первую прописную букву в первом слове заголовка, именах собственных и первом слове после точки (например, "Руководство. Прогнозирование цен с помощью регрессии с ML.NET").</span><span class="sxs-lookup"><span data-stu-id="df018-159">Capitalize the first letter of the first word of a heading, proper nouns, and the first letter following a colon (for example, "Tutorial: Predict prices using regression with ML.NET").</span></span>

<span data-ttu-id="df018-160">Не добавляйте двоеточие после слов "Практическое руководство" (например, "Практическое руководство. Сортировка массива", а не "Практическое руководство: Sort an array (Практическое руководство. Сортировка массива).</span><span class="sxs-lookup"><span data-stu-id="df018-160">Don't add a colon after "How to" (for example, "How to sort an array" and not "How to: Sort an array").</span></span>

<span data-ttu-id="df018-161">Заголовки следует оформлять в стиле atx, то есть использовать для указания заголовка 1–6 символов решетки (#) в начале строки, что соответствует уровням заголовков HTML с H1 по H6.</span><span class="sxs-lookup"><span data-stu-id="df018-161">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="df018-162">Выше приведены примеры заголовков первого и второго уровней.</span><span class="sxs-lookup"><span data-stu-id="df018-162">Examples of first- and second-level headers are used above.</span></span>

<span data-ttu-id="df018-163">В статье **должен** быть только один заголовок первого уровня (H1), который будет отображаться на странице как название.</span><span class="sxs-lookup"><span data-stu-id="df018-163">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="df018-164">Если заголовок заканчивается символом `#`, его необходимо экранировать, чтобы заголовок отображался правильно.</span><span class="sxs-lookup"><span data-stu-id="df018-164">If your heading ends in a `#` character, you need to escape it for the title to render correctly.</span></span> <span data-ttu-id="df018-165">Например, `# Async programming in F\#`.</span><span class="sxs-lookup"><span data-stu-id="df018-165">For example, `# Async programming in F\#`.</span></span>

<span data-ttu-id="df018-166">На основе заголовков второго уровня будет сформировано оглавление, которое приводится в разделе "Содержимое статьи" под названием статьи.</span><span class="sxs-lookup"><span data-stu-id="df018-166">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="df018-167">Заголовок третьего уровня</span><span class="sxs-lookup"><span data-stu-id="df018-167">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="df018-168">Заголовок четвертого уровня</span><span class="sxs-lookup"><span data-stu-id="df018-168">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="df018-169">Заголовок пятого уровня</span><span class="sxs-lookup"><span data-stu-id="df018-169">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="df018-170">Заголовок шестого уровня</span><span class="sxs-lookup"><span data-stu-id="df018-170">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="df018-171">Стиль текста</span><span class="sxs-lookup"><span data-stu-id="df018-171">Text styling</span></span>

<span data-ttu-id="df018-172">*Курсив* — используйте для имен файлов, папок и путей (если из-за большой длины они выносятся в отдельные строки), новых терминов.</span><span class="sxs-lookup"><span data-stu-id="df018-172">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="df018-173">**Полужирный** — используйте для элементов пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="df018-173">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="df018-174">`Code` — используется для встроенного кода, ключевых слов языка, имен пакетов NuGet, команд командной строки, имен таблиц и столбцов базы данных, а также URL-адресов, по которым не нужно переходить.</span><span class="sxs-lookup"><span data-stu-id="df018-174">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="df018-175">Ссылки</span><span class="sxs-lookup"><span data-stu-id="df018-175">Links</span></span>

### <a name="internal-links"></a><span data-ttu-id="df018-176">Внутренние ссылки</span><span class="sxs-lookup"><span data-stu-id="df018-176">Internal Links</span></span>

<span data-ttu-id="df018-177">Чтобы создать ссылку на заголовок в том же файле Markdown (ссылку привязки), необходимо определить идентификатор заголовка, на который должна указывать ссылка.</span><span class="sxs-lookup"><span data-stu-id="df018-177">To link to a header in the same Markdown file (also known as anchor links), you'll need to find out the id of the header you're trying to link to.</span></span> <span data-ttu-id="df018-178">Для этого просмотрите исходный код обработанной статьи, найдите идентификатор заголовка (например, `id="blockquote"`) и создайте ссылку, поставив перед идентификатором символ # (например, `#blockquote`).</span><span class="sxs-lookup"><span data-stu-id="df018-178">To confirm the ID, view the source of the rendered article, find the id of the header (for example, `id="blockquote"`), and link using # + id (for example, `#blockquote`).</span></span>
<span data-ttu-id="df018-179">Идентификатор формируется автоматически на основе текста заголовка.</span><span class="sxs-lookup"><span data-stu-id="df018-179">The id is auto-generated based on the header text.</span></span> <span data-ttu-id="df018-180">Например, для уникального раздела под названием `## Step 2` идентификатор будет выглядеть так: `id="step-2"`.</span><span class="sxs-lookup"><span data-stu-id="df018-180">So, for example, given a unique section named `## Step 2`, the id would look like this `id="step-2"`.</span></span>

- <span data-ttu-id="df018-181">Пример: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` создает [объявление встроенных блоков с идентификатором языка](#inline-code-blocks-with-language-identifier).</span><span class="sxs-lookup"><span data-stu-id="df018-181">Example: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produces [Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier).</span></span>

<span data-ttu-id="df018-182">Чтобы создать ссылку на файл Markdown в том же репозитории, используйте [относительную ссылку](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), указав расширение .md в конце имени файла.</span><span class="sxs-lookup"><span data-stu-id="df018-182">To link to a Markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), including the ".md" at the end of the filename.</span></span>

- <span data-ttu-id="df018-183">Пример: `[Readme file](../README.md)` создает [файл сведений](../README.md).</span><span class="sxs-lookup"><span data-stu-id="df018-183">Example: `[Readme file](../README.md)` produces [Readme file](../README.md).</span></span> <span data-ttu-id="df018-184">(Обратите внимание, что в ссылках учитывается регистр.)</span><span class="sxs-lookup"><span data-stu-id="df018-184">(Note that links are case-sensitive.)</span></span>
- <span data-ttu-id="df018-185">Пример: `[Welcome to .NET](../docs/welcome.md)` создает [Добро пожаловать в .NET](../docs/welcome.md).</span><span class="sxs-lookup"><span data-stu-id="df018-185">Example: `[Welcome to .NET](../docs/welcome.md)` produces [Welcome to .NET](../docs/welcome.md).</span></span>

<span data-ttu-id="df018-186">Чтобы создать ссылку на заголовок в файле Markdown в том же репозитории, используйте относительную ссылку + ссылку с символом решетки.</span><span class="sxs-lookup"><span data-stu-id="df018-186">To link to a header in a Markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="df018-187">Пример: `[.NET Community](../docs/welcome.md#open-source)` создает [Сообщество .NET](../docs/welcome.md#open-source).</span><span class="sxs-lookup"><span data-stu-id="df018-187">Example: `[.NET Community](../docs/welcome.md#open-source)` produces [.NET Community](../docs/welcome.md#open-source).</span></span>

<span data-ttu-id="df018-188">В большинстве случаев мы используем относительные ссылки и не рекомендуем использовать `~/` в ссылках, так как относительные ссылки разрешаются в источнике на GitHub.</span><span class="sxs-lookup"><span data-stu-id="df018-188">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="df018-189">Однако при ссылке на файл в зависимом репозитории мы будем использовать символ `~/` для предоставления пути.</span><span class="sxs-lookup"><span data-stu-id="df018-189">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="df018-190">Так как файлы в зависимом репозитории находятся в другом расположении на GitHub, ссылки не будут правильно разрешаться с относительными ссылками независимо от того, как они были написаны.</span><span class="sxs-lookup"><span data-stu-id="df018-190">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>

<span data-ttu-id="df018-191">Спецификации языков C# и Visual Basic включены в документы .NET путем включения источника из репозиториев языка.</span><span class="sxs-lookup"><span data-stu-id="df018-191">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="df018-192">Источники Markdown управляются в репозиториях [csharplang](https://github.com/dotnet/csharplang) и [visual basic](https://github.com/dotnet/vblang).</span><span class="sxs-lookup"><span data-stu-id="df018-192">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [visual basic](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="df018-193">Ссылки на спецификацию должны указывать на исходные каталоги, в которых включены эти спецификации.</span><span class="sxs-lookup"><span data-stu-id="df018-193">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="df018-194">Для C# это **~/_csharplang/spec**, а для VB — **~/_vblang/spec**.</span><span class="sxs-lookup"><span data-stu-id="df018-194">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**.</span></span>

- <span data-ttu-id="df018-195">Пример: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` создает [выражения запросов C#](~/_csharplang/spec/expressions.md#query-expressions).</span><span class="sxs-lookup"><span data-stu-id="df018-195">Example: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` produces [C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions).</span></span>

### <a name="external-links"></a><span data-ttu-id="df018-196">Внешние ссылки</span><span class="sxs-lookup"><span data-stu-id="df018-196">External Links</span></span>

<span data-ttu-id="df018-197">Чтобы создать ссылку на внешний файл, используйте полный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="df018-197">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="df018-198">Пример: `[GitHub](https://www.github.com)` создает [GitHub](https://www.github.com).</span><span class="sxs-lookup"><span data-stu-id="df018-198">Example: `[GitHub](https://www.github.com)` produces [GitHub](https://www.github.com).</span></span>

<span data-ttu-id="df018-199">Если URL-адрес включается в файл Markdown, он преобразуется в активную ссылку.</span><span class="sxs-lookup"><span data-stu-id="df018-199">If a URL appears in a Markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="df018-200">Пример: `<https://www.github.com>` создает <https://www.github.com>.</span><span class="sxs-lookup"><span data-stu-id="df018-200">Example: `<https://www.github.com>` produces <https://www.github.com>.</span></span>

<span data-ttu-id="df018-201">Используйте протокол `https` для внешних ссылок.</span><span class="sxs-lookup"><span data-stu-id="df018-201">Prefer the `https` protocol for external links.</span></span> <span data-ttu-id="df018-202">Используйте ссылки `http` только для тех сайтов, которые не поддерживают `https`.</span><span class="sxs-lookup"><span data-stu-id="df018-202">Only use `http` links for sites that do not support `https`.</span></span>

### <a name="links-to-apis"></a><span data-ttu-id="df018-203">Ссылки на интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="df018-203">Links to APIs</span></span>

<span data-ttu-id="df018-204">Система сборки имеет ряд расширений, которые позволяют ссылаться на основные интерфейсы API .NET, не используя внешние ссылки.</span><span class="sxs-lookup"><span data-stu-id="df018-204">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span>
<span data-ttu-id="df018-205">Для ссылки на интерфейс API можно использовать его уникальный идентификатор (UID), который формируется автоматически на основе исходного кода.</span><span class="sxs-lookup"><span data-stu-id="df018-205">When linking to an API, you can use its unique identifier (UID) that is auto-generated from the source code.</span></span>

<span data-ttu-id="df018-206">Уникальный идентификатор соответствует полному типу и имени члена.</span><span class="sxs-lookup"><span data-stu-id="df018-206">The UID equates to the fully qualified type and member name.</span></span>

<span data-ttu-id="df018-207">При добавлении \* (или %2A) после уникального идентификатора ссылка представляет страницу перегрузки, а не конкретный API.</span><span class="sxs-lookup"><span data-stu-id="df018-207">If you add a \* (or %2A) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="df018-208">Например, используйте это для ссылки на страницу [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) обычным способом вместо конкретной перегрузки, например [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span><span class="sxs-lookup"><span data-stu-id="df018-208">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="df018-209">Также можно использовать \* для ссылки на страницу элемента, если элемент не перегружен. Это позволяет избежать включения списка параметров в уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="df018-209">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="df018-210">Чтобы создать ссылку на определенную перегрузку метода, включите полное имя типа каждого из параметров метода.</span><span class="sxs-lookup"><span data-stu-id="df018-210">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="df018-211">Например, \<xref:System.DateTime.ToString> ссылается на метод [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) без параметров, а \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> ссылается на метод [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_).</span><span class="sxs-lookup"><span data-stu-id="df018-211">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span> <span data-ttu-id="df018-212">Уникальные идентификаторы определенного перегруженного элемента можно найти в <https://xref.docs.microsoft.com/autocomplete>.</span><span class="sxs-lookup"><span data-stu-id="df018-212">You can find the UIDs of a particular overloaded member from <https://xref.docs.microsoft.com/autocomplete>.</span></span> <span data-ttu-id="df018-213">Строка запроса "?text= *\<type-member-name>* " определяет тип или элемент, уникальный идентификатор которого вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="df018-213">The query string "?text=*\<type-member-name>*" identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="df018-214">Например, <https://xref.docs.microsoft.com/autocomplete?text=string.format> получает перегрузки [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format).</span><span class="sxs-lookup"><span data-stu-id="df018-214">For example, <https://xref.docs.microsoft.com/autocomplete?text=string.format> retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span>

<span data-ttu-id="df018-215">Чтобы создать ссылку на универсальный тип, например [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), используйте символ \` (%60), за которым следует число параметров универсального типа.</span><span class="sxs-lookup"><span data-stu-id="df018-215">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (%60) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="df018-216">Например, \<xref:System.Nullable%601> ссылается на тип [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), а \<xref:System.Func%602> ссылается на делегат [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).</span><span class="sxs-lookup"><span data-stu-id="df018-216">For example, \<xref:System.Nullable%601> links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while \<xref:System.Func%602> links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

<span data-ttu-id="df018-217">Можно использовать один из следующих вариантов синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="df018-217">You can use one of the following syntax:</span></span>

1. <span data-ttu-id="df018-218">Автоматическая ссылка: `<xref:UID>` или `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="df018-218">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="df018-219">Параметр запроса `displayProperty` создает полный текст ссылки.</span><span class="sxs-lookup"><span data-stu-id="df018-219">The `displayProperty` query    parameter produces a fully qualified link text.</span></span> <span data-ttu-id="df018-220">По умолчанию текст ссылки показывает только имя элемента или типа.</span><span class="sxs-lookup"><span data-stu-id="df018-220">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="df018-221">Ссылка Markdown: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="df018-221">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="df018-222">Используется, если вы хотите настроить отображаемый текст ссылки.</span><span class="sxs-lookup"><span data-stu-id="df018-222">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="df018-223">Примеры</span><span class="sxs-lookup"><span data-stu-id="df018-223">Examples:</span></span>

- <span data-ttu-id="df018-224">`<xref:System.String>` преобразуется как [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="df018-224">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="df018-225">`<xref:System.String?displayProperty=nameWithType>` преобразуется как [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="df018-225">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="df018-226">`[String class](xref:System.String)` преобразуется как [класс String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="df018-226">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="df018-227">Дополнительные сведения об использовании этой нотации см. в разделе [Использование перекрестных ссылок](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span><span class="sxs-lookup"><span data-stu-id="df018-227">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="df018-228">Есть два способа найти уникальный идентификатор:</span><span class="sxs-lookup"><span data-stu-id="df018-228">There are two ways to find the UID:</span></span>

- <span data-ttu-id="df018-229">Просмотрите исходный код для страницы API, на которую вы хотите сослаться, и найдите значение ms.assetid.</span><span class="sxs-lookup"><span data-stu-id="df018-229">View the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="df018-230">Обратите внимание, что отдельные значения перегрузки не показаны в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="df018-230">Note that individual overload values are not shown in the source.</span></span>
- <span data-ttu-id="df018-231">Используйте следующее средство для поиска уникальных идентификаторов: <https://xref.docs.microsoft.com/autocomplete?text=tostring> (замените tostring на части имени API, который вы пытаетесь найти).</span><span class="sxs-lookup"><span data-stu-id="df018-231">Use the following tool to search for UIDs: <https://xref.docs.microsoft.com/autocomplete?text=tostring> (replace tostring with parts of the API name you're trying to find).</span></span> <span data-ttu-id="df018-232">Средство выполняет поиск указанного параметра запроса `text` в любой части уникального идентификатора.</span><span class="sxs-lookup"><span data-stu-id="df018-232">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="df018-233">Например, вы можете искать имя элемента (ToString), частичное имя элемента (ToStri), имя типа и элемента (Double.ToString) и т. д.</span><span class="sxs-lookup"><span data-stu-id="df018-233">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="df018-234">Если уникальный идентификатор содержит специальные символы \`, \# или \*, они должны быть представлены в значении идентификатора в кодировке HTML как `%60`, `%23` и `%2A` соответственно.</span><span class="sxs-lookup"><span data-stu-id="df018-234">When the UID contains the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="df018-235">Иногда круглые скобки кодируются, но это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="df018-235">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="df018-236">Примеры</span><span class="sxs-lookup"><span data-stu-id="df018-236">Examples:</span></span>

- <span data-ttu-id="df018-237">System.Threading.Tasks.Task\`1 преобразуется в `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="df018-237">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="df018-238">System.Exception.\#ctor преобразуется в `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="df018-238">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="df018-239">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) преобразуется в `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="df018-239">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

## <a name="lists"></a><span data-ttu-id="df018-240">Списки</span><span class="sxs-lookup"><span data-stu-id="df018-240">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="df018-241">Упорядоченные списки</span><span class="sxs-lookup"><span data-stu-id="df018-241">Ordered lists</span></span>

1. <span data-ttu-id="df018-242">Это</span><span class="sxs-lookup"><span data-stu-id="df018-242">This</span></span>
1. <span data-ttu-id="df018-243">Пример</span><span class="sxs-lookup"><span data-stu-id="df018-243">Is</span></span>
1. <span data-ttu-id="df018-244">Обычного</span><span class="sxs-lookup"><span data-stu-id="df018-244">An</span></span>
1. <span data-ttu-id="df018-245">Упорядоченного</span><span class="sxs-lookup"><span data-stu-id="df018-245">Ordered</span></span>
1. <span data-ttu-id="df018-246">Списка</span><span class="sxs-lookup"><span data-stu-id="df018-246">List</span></span>

#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="df018-247">Упорядоченный список с внедренным списком.</span><span class="sxs-lookup"><span data-stu-id="df018-247">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="df018-248">А</span><span class="sxs-lookup"><span data-stu-id="df018-248">Here</span></span>
1. <span data-ttu-id="df018-249">это</span><span class="sxs-lookup"><span data-stu-id="df018-249">comes</span></span>
1. <span data-ttu-id="df018-250">пример</span><span class="sxs-lookup"><span data-stu-id="df018-250">an</span></span>
1. <span data-ttu-id="df018-251">внедренного</span><span class="sxs-lookup"><span data-stu-id="df018-251">embedded</span></span>
    1. <span data-ttu-id="df018-252">Мисс Скарлетт</span><span class="sxs-lookup"><span data-stu-id="df018-252">Miss Scarlett</span></span>
    1. <span data-ttu-id="df018-253">Профессор Плам</span><span class="sxs-lookup"><span data-stu-id="df018-253">Professor Plum</span></span>
1. <span data-ttu-id="df018-254">упорядоченного</span><span class="sxs-lookup"><span data-stu-id="df018-254">ordered</span></span>
1. <span data-ttu-id="df018-255">списка</span><span class="sxs-lookup"><span data-stu-id="df018-255">list</span></span>

### <a name="unordered-lists"></a><span data-ttu-id="df018-256">Неупорядоченные списки</span><span class="sxs-lookup"><span data-stu-id="df018-256">Unordered Lists</span></span>

- <span data-ttu-id="df018-257">Вот</span><span class="sxs-lookup"><span data-stu-id="df018-257">This</span></span>
- <span data-ttu-id="df018-258">это</span><span class="sxs-lookup"><span data-stu-id="df018-258">is</span></span>
- <span data-ttu-id="df018-259">пример</span><span class="sxs-lookup"><span data-stu-id="df018-259">a</span></span>
- <span data-ttu-id="df018-260">маркированного</span><span class="sxs-lookup"><span data-stu-id="df018-260">bulleted</span></span>
- <span data-ttu-id="df018-261">списка</span><span class="sxs-lookup"><span data-stu-id="df018-261">list</span></span>

#### <a name="unordered-list-with-an-embedded-list"></a><span data-ttu-id="df018-262">Неупорядоченный список с внедренным списком</span><span class="sxs-lookup"><span data-stu-id="df018-262">Unordered list with an embedded list</span></span>

- <span data-ttu-id="df018-263">Этот</span><span class="sxs-lookup"><span data-stu-id="df018-263">This</span></span>
- <span data-ttu-id="df018-264">маркированный</span><span class="sxs-lookup"><span data-stu-id="df018-264">bulleted</span></span>
- <span data-ttu-id="df018-265">списка</span><span class="sxs-lookup"><span data-stu-id="df018-265">list</span></span>
  - <span data-ttu-id="df018-266">Миссис Пикок</span><span class="sxs-lookup"><span data-stu-id="df018-266">Mrs. Peacock</span></span>
  - <span data-ttu-id="df018-267">Мистер Грин</span><span class="sxs-lookup"><span data-stu-id="df018-267">Mr. Green</span></span>
- <span data-ttu-id="df018-268">содержит</span><span class="sxs-lookup"><span data-stu-id="df018-268">contains</span></span>
- <span data-ttu-id="df018-269">другие</span><span class="sxs-lookup"><span data-stu-id="df018-269">other</span></span>
  1. <span data-ttu-id="df018-270">Полковник Мастард</span><span class="sxs-lookup"><span data-stu-id="df018-270">Colonel Mustard</span></span>
  1. <span data-ttu-id="df018-271">Миссис Уайт</span><span class="sxs-lookup"><span data-stu-id="df018-271">Mrs. White</span></span>
- <span data-ttu-id="df018-272">списки</span><span class="sxs-lookup"><span data-stu-id="df018-272">lists</span></span>

## <a name="horizontal-rule"></a><span data-ttu-id="df018-273">Горизонтальная линия</span><span class="sxs-lookup"><span data-stu-id="df018-273">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="df018-274">Таблицы</span><span class="sxs-lookup"><span data-stu-id="df018-274">Tables</span></span>

| <span data-ttu-id="df018-275">Таблицы</span><span class="sxs-lookup"><span data-stu-id="df018-275">Tables</span></span>        | <span data-ttu-id="df018-276">Это</span><span class="sxs-lookup"><span data-stu-id="df018-276">Are</span></span>           | <span data-ttu-id="df018-277">Здорово</span><span class="sxs-lookup"><span data-stu-id="df018-277">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="df018-278">столбец 3</span><span class="sxs-lookup"><span data-stu-id="df018-278">col 3 is</span></span>      | <span data-ttu-id="df018-279">выровнен по правому краю</span><span class="sxs-lookup"><span data-stu-id="df018-279">right-aligned</span></span> | <span data-ttu-id="df018-280">$1600</span><span class="sxs-lookup"><span data-stu-id="df018-280">$1600</span></span> |
| <span data-ttu-id="df018-281">столбец 2</span><span class="sxs-lookup"><span data-stu-id="df018-281">col 2 is</span></span>      | <span data-ttu-id="df018-282">выровнен по центру</span><span class="sxs-lookup"><span data-stu-id="df018-282">centered</span></span>      |   <span data-ttu-id="df018-283">$12</span><span class="sxs-lookup"><span data-stu-id="df018-283">$12</span></span> |
| <span data-ttu-id="df018-284">столбец 1 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="df018-284">col 1 is default</span></span> | <span data-ttu-id="df018-285">выровнен по левому краю</span><span class="sxs-lookup"><span data-stu-id="df018-285">left-aligned</span></span>     |    <span data-ttu-id="df018-286">$1</span><span class="sxs-lookup"><span data-stu-id="df018-286">$1</span></span> |

<span data-ttu-id="df018-287">Для удобства можно использовать [средство создания таблиц Markdown](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="df018-287">You can use a [Markdown table generator tool](https://www.tablesgenerator.com/markdown_tables) to help creating them more easily.</span></span>

## <a name="code"></a><span data-ttu-id="df018-288">Код</span><span class="sxs-lookup"><span data-stu-id="df018-288">Code</span></span>

<span data-ttu-id="df018-289">Лучший способ добавления кода — включение фрагментов из рабочего образца.</span><span class="sxs-lookup"><span data-stu-id="df018-289">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="df018-290">Создайте образец согласно инструкциям в [руководстве по добавлению кода](../CONTRIBUTING.md#contributing-to-samples).</span><span class="sxs-lookup"><span data-stu-id="df018-290">Create your sample following the instructions in the [contributing guide](../CONTRIBUTING.md#contributing-to-samples).</span></span>

<span data-ttu-id="df018-291">Код можно включить с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="df018-291">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- <span data-ttu-id="df018-292">`-<language>` (*необязательно*, но *рекомендуется*)</span><span class="sxs-lookup"><span data-stu-id="df018-292">`-<language>` (*optional* but *recommended*)</span></span>
  - <span data-ttu-id="df018-293">Язык фрагмента кода, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="df018-293">Language of the code snippet being referenced.</span></span> <span data-ttu-id="df018-294">Список поддерживаемых значений см. в разделе [Поддерживаемые языки ](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="df018-294">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

- <span data-ttu-id="df018-295">`<name>` (*необязательно*)</span><span class="sxs-lookup"><span data-stu-id="df018-295">`<name>` (*optional*)</span></span>
  - <span data-ttu-id="df018-296">Имя фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="df018-296">Name for the code snippet.</span></span> <span data-ttu-id="df018-297">Оно не влияет на выходные данные HTML, но его можно использовать для повышения удобочитаемости источника Markdown.</span><span class="sxs-lookup"><span data-stu-id="df018-297">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

- <span data-ttu-id="df018-298">`<pathToFile>` (*обязательно*)</span><span class="sxs-lookup"><span data-stu-id="df018-298">`<pathToFile>` (*mandatory*)</span></span>
  - <span data-ttu-id="df018-299">Относительный путь в файловой системе, указывающий на файл фрагмента кода для ссылки.</span><span class="sxs-lookup"><span data-stu-id="df018-299">Relative path in the file system that indicates the code snippet file to reference.</span></span>

- <span data-ttu-id="df018-300">`<queryoption>` и `<queryoptionvalue>` (*необязательно*)</span><span class="sxs-lookup"><span data-stu-id="df018-300">`<queryoption>` and `<queryoptionvalue>` (*optional*)</span></span>
  - <span data-ttu-id="df018-301">Используется совместно для указания способа извлечения кода из файла:</span><span class="sxs-lookup"><span data-stu-id="df018-301">Used together to specify how the code should be retrieved from the file:</span></span>
    - <span data-ttu-id="df018-302">`#`: `#L{startlinenumber}-L{endlinenumber}` (диапазон строк) *или* `#{tagname}` (имя тега).</span><span class="sxs-lookup"><span data-stu-id="df018-302">`#`:  `#L{startlinenumber}-L{endlinenumber}` (line range) *or* `#{tagname}` (tag name).</span></span>
    <span data-ttu-id="df018-303">Мы не рекомендуем использовать номера строк, так отдельные строки слишком отрывочны.</span><span class="sxs-lookup"><span data-stu-id="df018-303">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="df018-304">Лучше используйте имя тега для ссылки на фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="df018-304">Tag name is the preferred way of referencing code snippets.</span></span>
    - <span data-ttu-id="df018-305">`range`. `?range=1,3-5` Диапазон строк.</span><span class="sxs-lookup"><span data-stu-id="df018-305">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="df018-306">Этот пример включает строки 1, 3, 4 и 5.</span><span class="sxs-lookup"><span data-stu-id="df018-306">This example includes lines 1, 3, 4, and 5.</span></span>
    - <span data-ttu-id="df018-307">`dedent`. `?dedent=8` Укорачивает строки на число пробелов — в данном случае 8.</span><span class="sxs-lookup"><span data-stu-id="df018-307">`dedent`: `?dedent=8` Dedents the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="df018-308">Это можно сочетать с `range` и другими параметрами запросов, которые выбирают подмножество строк файла.</span><span class="sxs-lookup"><span data-stu-id="df018-308">This can be combined with the `range` and other query options that select a subset of the lines of a file.</span></span>
    - <span data-ttu-id="df018-309">`outdent`. `?outdent=8` Отменяет отступ строк на число пробелов — в данном случае 8.</span><span class="sxs-lookup"><span data-stu-id="df018-309">`outdent`: `?outdent=8` Reverses the indent of the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="df018-310">Это можно сочетать с `range` и другими параметрами запросов, которые выбирают подмножество строк файла.</span><span class="sxs-lookup"><span data-stu-id="df018-310">This can be combined with `range` and other query options that select a subset of the lines of a file.</span></span>

<span data-ttu-id="df018-311">По возможности рекомендуется использовать параметр имени тега.</span><span class="sxs-lookup"><span data-stu-id="df018-311">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="df018-312">Имя тега — это имя региона или комментария к коду в формате `Snippettagname`, присутствующее в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="df018-312">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="df018-313">В приведенном ниже примере показано, как ссылаться на имя тега `1`:</span><span class="sxs-lookup"><span data-stu-id="df018-313">The following example shows how to refer to the tag name `1`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

<span data-ttu-id="df018-314">Вы видите, как фрагменты кода структурированы в [этом исходном файле](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span><span class="sxs-lookup"><span data-stu-id="df018-314">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span></span> <span data-ttu-id="df018-315">Дополнительные сведения о представлении имени тега в исходных файлах фрагментов кода по языку см. в [руководстве по DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span><span class="sxs-lookup"><span data-stu-id="df018-315">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="df018-316">Включение фрагментов из полных программ обеспечивает выполнение всего кода в нашей системе непрерывной интеграции (CI).</span><span class="sxs-lookup"><span data-stu-id="df018-316">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="df018-317">Однако если вам нужно показать фрагмент, который вызывает ошибки во время компиляции или выполнения, вы можете использовать встроенные блоки кода.</span><span class="sxs-lookup"><span data-stu-id="df018-317">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

### <a name="inline-code-blocks-with-language-identifier"></a><span data-ttu-id="df018-318">Встроенные блоки кода с идентификатором языка</span><span class="sxs-lookup"><span data-stu-id="df018-318">Inline code blocks with language identifier</span></span>

<span data-ttu-id="df018-319">Чтобы применить к блоку кода цветовое выделение синтаксиса, характерное для данного языка, используйте три обратных апострофа (\`\`\`) и идентификатор языка.</span><span class="sxs-lookup"><span data-stu-id="df018-319">Use three backticks (\`\`\`) + a language ID to apply language-specific color coding to a code block.</span></span> <span data-ttu-id="df018-320">Ниже приведен список поддерживаемых языков, в которых отображается метка Markdown для каждого идентификатора языка.</span><span class="sxs-lookup"><span data-stu-id="df018-320">Here is the list of supported languages showing the markdown label for each language ID.</span></span>

#### <a name="supported-languages"></a><span data-ttu-id="df018-321">Поддерживаемые языки</span><span class="sxs-lookup"><span data-stu-id="df018-321">Supported languages</span></span>

|<span data-ttu-id="df018-322">name</span><span class="sxs-lookup"><span data-stu-id="df018-322">Name</span></span>|<span data-ttu-id="df018-323">Метка Markdown</span><span class="sxs-lookup"><span data-stu-id="df018-323">Markdown label</span></span>|
|-----|-------|
|<span data-ttu-id="df018-324">Консоль .NET</span><span class="sxs-lookup"><span data-stu-id="df018-324">.NET Console</span></span>|<span data-ttu-id="df018-325">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="df018-325">dotnetcli</span></span>|
|<span data-ttu-id="df018-326">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="df018-326">ASP.NET (C#)</span></span>|<span data-ttu-id="df018-327">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="df018-327">aspx-csharp</span></span>|
|<span data-ttu-id="df018-328">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="df018-328">ASP.NET (VB)</span></span>|<span data-ttu-id="df018-329">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="df018-329">aspx-vb</span></span>|
|<span data-ttu-id="df018-330">Инфраструктура CLI Azure</span><span class="sxs-lookup"><span data-stu-id="df018-330">Azure CLI</span></span>|<span data-ttu-id="df018-331">azurecli</span><span class="sxs-lookup"><span data-stu-id="df018-331">azurecli</span></span>|
|<span data-ttu-id="df018-332">AzCopy</span><span class="sxs-lookup"><span data-stu-id="df018-332">AzCopy</span></span>|<span data-ttu-id="df018-333">azcopy</span><span class="sxs-lookup"><span data-stu-id="df018-333">azcopy</span></span>|
|<span data-ttu-id="df018-334">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="df018-334">Azure PowerShell</span></span>|<span data-ttu-id="df018-335">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="df018-335">azurepowershell</span></span>|
|<span data-ttu-id="df018-336">Bash</span><span class="sxs-lookup"><span data-stu-id="df018-336">Bash</span></span>|<span data-ttu-id="df018-337">bash</span><span class="sxs-lookup"><span data-stu-id="df018-337">bash</span></span>|
|<span data-ttu-id="df018-338">C++</span><span class="sxs-lookup"><span data-stu-id="df018-338">C++</span></span>|<span data-ttu-id="df018-339">cpp</span><span class="sxs-lookup"><span data-stu-id="df018-339">cpp</span></span>|
|<span data-ttu-id="df018-340">C++/CX</span><span class="sxs-lookup"><span data-stu-id="df018-340">C++/CX</span></span>|<span data-ttu-id="df018-341">cppcx</span><span class="sxs-lookup"><span data-stu-id="df018-341">cppcx</span></span>|
|<span data-ttu-id="df018-342">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="df018-342">C++/WinRT</span></span>|<span data-ttu-id="df018-343">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="df018-343">cppwinrt</span></span>|
|<span data-ttu-id="df018-344">C#</span><span class="sxs-lookup"><span data-stu-id="df018-344">C#</span></span>|<span data-ttu-id="df018-345">csharp</span><span class="sxs-lookup"><span data-stu-id="df018-345">csharp</span></span>|
|<span data-ttu-id="df018-346">C# в браузере</span><span class="sxs-lookup"><span data-stu-id="df018-346">C# in browser</span></span>|<span data-ttu-id="df018-347">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="df018-347">csharp-interactive</span></span>|
|<span data-ttu-id="df018-348">Консоль</span><span class="sxs-lookup"><span data-stu-id="df018-348">Console</span></span>|<span data-ttu-id="df018-349">console</span><span class="sxs-lookup"><span data-stu-id="df018-349">console</span></span>|
|<span data-ttu-id="df018-350">CSHTML</span><span class="sxs-lookup"><span data-stu-id="df018-350">CSHTML</span></span>|<span data-ttu-id="df018-351">cshtml</span><span class="sxs-lookup"><span data-stu-id="df018-351">cshtml</span></span>|
|<span data-ttu-id="df018-352">DAX</span><span class="sxs-lookup"><span data-stu-id="df018-352">DAX</span></span>|<span data-ttu-id="df018-353">dax</span><span class="sxs-lookup"><span data-stu-id="df018-353">dax</span></span>|
|<span data-ttu-id="df018-354">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="df018-354">Dockerfile</span></span>|<span data-ttu-id="df018-355">dockerfile</span><span class="sxs-lookup"><span data-stu-id="df018-355">dockerfile</span></span>|
|<span data-ttu-id="df018-356">F#</span><span class="sxs-lookup"><span data-stu-id="df018-356">F#</span></span>|<span data-ttu-id="df018-357">fsharp</span><span class="sxs-lookup"><span data-stu-id="df018-357">fsharp</span></span>|
|<span data-ttu-id="df018-358">Go</span><span class="sxs-lookup"><span data-stu-id="df018-358">Go</span></span>|<span data-ttu-id="df018-359">go</span><span class="sxs-lookup"><span data-stu-id="df018-359">go</span></span>|
|<span data-ttu-id="df018-360">HTML</span><span class="sxs-lookup"><span data-stu-id="df018-360">HTML</span></span>|<span data-ttu-id="df018-361">html</span><span class="sxs-lookup"><span data-stu-id="df018-361">html</span></span>|
|<span data-ttu-id="df018-362">HTTP</span><span class="sxs-lookup"><span data-stu-id="df018-362">HTTP</span></span>|<span data-ttu-id="df018-363">http</span><span class="sxs-lookup"><span data-stu-id="df018-363">http</span></span>|
|<span data-ttu-id="df018-364">Java</span><span class="sxs-lookup"><span data-stu-id="df018-364">Java</span></span>|<span data-ttu-id="df018-365">java</span><span class="sxs-lookup"><span data-stu-id="df018-365">java</span></span>|
|<span data-ttu-id="df018-366">JavaScript</span><span class="sxs-lookup"><span data-stu-id="df018-366">JavaScript</span></span>|<span data-ttu-id="df018-367">javascript</span><span class="sxs-lookup"><span data-stu-id="df018-367">javascript</span></span>|
|<span data-ttu-id="df018-368">JSON</span><span class="sxs-lookup"><span data-stu-id="df018-368">JSON</span></span>|<span data-ttu-id="df018-369">json</span><span class="sxs-lookup"><span data-stu-id="df018-369">json</span></span>|
|<span data-ttu-id="df018-370">Язык запросов Kusto</span><span class="sxs-lookup"><span data-stu-id="df018-370">Kusto Query Language</span></span>|<span data-ttu-id="df018-371">kusto</span><span class="sxs-lookup"><span data-stu-id="df018-371">kusto</span></span>|
|<span data-ttu-id="df018-372">Markdown</span><span class="sxs-lookup"><span data-stu-id="df018-372">Markdown</span></span>|<span data-ttu-id="df018-373">md</span><span class="sxs-lookup"><span data-stu-id="df018-373">md</span></span>|
|<span data-ttu-id="df018-374">Node.js</span><span class="sxs-lookup"><span data-stu-id="df018-374">NodeJS</span></span>|<span data-ttu-id="df018-375">nodejs</span><span class="sxs-lookup"><span data-stu-id="df018-375">nodejs</span></span>|
|<span data-ttu-id="df018-376">Objective-C</span><span class="sxs-lookup"><span data-stu-id="df018-376">Objective-C</span></span>|<span data-ttu-id="df018-377">objc</span><span class="sxs-lookup"><span data-stu-id="df018-377">objc</span></span>|
|<span data-ttu-id="df018-378">OData</span><span class="sxs-lookup"><span data-stu-id="df018-378">OData</span></span>|<span data-ttu-id="df018-379">odata</span><span class="sxs-lookup"><span data-stu-id="df018-379">odata</span></span>|
|<span data-ttu-id="df018-380">PHP</span><span class="sxs-lookup"><span data-stu-id="df018-380">PHP</span></span>|<span data-ttu-id="df018-381">php</span><span class="sxs-lookup"><span data-stu-id="df018-381">php</span></span>|
|<span data-ttu-id="df018-382">protobuf</span><span class="sxs-lookup"><span data-stu-id="df018-382">protobuf</span></span>|<span data-ttu-id="df018-383">protobuf</span><span class="sxs-lookup"><span data-stu-id="df018-383">protobuf</span></span>|
|<span data-ttu-id="df018-384">PowerApps (десятичный разделитель — точка)</span><span class="sxs-lookup"><span data-stu-id="df018-384">PowerApps (dot decimal separator)</span></span>|<span data-ttu-id="df018-385">powerapps-dot</span><span class="sxs-lookup"><span data-stu-id="df018-385">powerapps-dot</span></span>|
|<span data-ttu-id="df018-386">PowerApps (десятичный разделитель — запятая)</span><span class="sxs-lookup"><span data-stu-id="df018-386">PowerApps (comma decimal separator)</span></span>|<span data-ttu-id="df018-387">powerapps-comma</span><span class="sxs-lookup"><span data-stu-id="df018-387">powerapps-comma</span></span>|
|<span data-ttu-id="df018-388">PowerShell</span><span class="sxs-lookup"><span data-stu-id="df018-388">PowerShell</span></span>|<span data-ttu-id="df018-389">powershell</span><span class="sxs-lookup"><span data-stu-id="df018-389">powershell</span></span>|
|<span data-ttu-id="df018-390">Python</span><span class="sxs-lookup"><span data-stu-id="df018-390">Python</span></span>|<span data-ttu-id="df018-391">python</span><span class="sxs-lookup"><span data-stu-id="df018-391">python</span></span>|
|<span data-ttu-id="df018-392">Q#</span><span class="sxs-lookup"><span data-stu-id="df018-392">Q#</span></span>|<span data-ttu-id="df018-393">qsharp</span><span class="sxs-lookup"><span data-stu-id="df018-393">qsharp</span></span>|
|<span data-ttu-id="df018-394">R</span><span class="sxs-lookup"><span data-stu-id="df018-394">R</span></span>|<span data-ttu-id="df018-395">процедура</span><span class="sxs-lookup"><span data-stu-id="df018-395">r</span></span>|
|<span data-ttu-id="df018-396">Ruby</span><span class="sxs-lookup"><span data-stu-id="df018-396">Ruby</span></span>|<span data-ttu-id="df018-397">ruby</span><span class="sxs-lookup"><span data-stu-id="df018-397">ruby</span></span>|
|<span data-ttu-id="df018-398">SQL-код</span><span class="sxs-lookup"><span data-stu-id="df018-398">SQL</span></span>|<span data-ttu-id="df018-399">sql</span><span class="sxs-lookup"><span data-stu-id="df018-399">sql</span></span>|
|<span data-ttu-id="df018-400">Swift</span><span class="sxs-lookup"><span data-stu-id="df018-400">Swift</span></span>|<span data-ttu-id="df018-401">swift</span><span class="sxs-lookup"><span data-stu-id="df018-401">swift</span></span>|
|<span data-ttu-id="df018-402">TypeScript</span><span class="sxs-lookup"><span data-stu-id="df018-402">TypeScript</span></span>|<span data-ttu-id="df018-403">typescript</span><span class="sxs-lookup"><span data-stu-id="df018-403">typescript</span></span>|
|<span data-ttu-id="df018-404">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df018-404">Visual Basic</span></span>|<span data-ttu-id="df018-405">vb</span><span class="sxs-lookup"><span data-stu-id="df018-405">vb</span></span>|
|<span data-ttu-id="df018-406">VBScript</span><span class="sxs-lookup"><span data-stu-id="df018-406">VBScript</span></span>|<span data-ttu-id="df018-407">vbscript</span><span class="sxs-lookup"><span data-stu-id="df018-407">vbscript</span></span>|
|<span data-ttu-id="df018-408">XAML</span><span class="sxs-lookup"><span data-stu-id="df018-408">XAML</span></span>|<span data-ttu-id="df018-409">xaml</span><span class="sxs-lookup"><span data-stu-id="df018-409">xaml</span></span>|
|<span data-ttu-id="df018-410">XML</span><span class="sxs-lookup"><span data-stu-id="df018-410">XML</span></span>|<span data-ttu-id="df018-411">xml</span><span class="sxs-lookup"><span data-stu-id="df018-411">xml</span></span>|
|<span data-ttu-id="df018-412">yml</span><span class="sxs-lookup"><span data-stu-id="df018-412">yml</span></span>|<span data-ttu-id="df018-413">yml</span><span class="sxs-lookup"><span data-stu-id="df018-413">yml</span></span>|

<span data-ttu-id="df018-414">Имя `csharp-interactive` указывает язык C# и возможность запуска примеров из браузера.</span><span class="sxs-lookup"><span data-stu-id="df018-414">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="df018-415">Эти фрагменты кода компилируются и выполняются в контейнере Docker, и результаты выполнения программы отображаются в окне браузера пользователя.</span><span class="sxs-lookup"><span data-stu-id="df018-415">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

<span data-ttu-id="df018-416">Ниже приведены примеры блоков кода с использованием идентификаторов языков для C# (\`\`\`csharp), Python (\`\`\`python) и PowerShell (\`\`\`powershell).</span><span class="sxs-lookup"><span data-stu-id="df018-416">The following are examples of code blocks using the language IDs for C# (\`\`\`csharp), Python (\`\`\`python), and PowerShell (\`\`\`powershell).</span></span>

##### <a name="c"></a><span data-ttu-id="df018-417">C\#</span><span class="sxs-lookup"><span data-stu-id="df018-417">C\#</span></span>

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

#### <a name="python"></a><span data-ttu-id="df018-418">Python</span><span class="sxs-lookup"><span data-stu-id="df018-418">Python</span></span>

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a><span data-ttu-id="df018-419">PowerShell</span><span class="sxs-lookup"><span data-stu-id="df018-419">PowerShell</span></span>

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a><span data-ttu-id="df018-420">Общий блок кода</span><span class="sxs-lookup"><span data-stu-id="df018-420">Generic code block</span></span>

<span data-ttu-id="df018-421">Для общего выделения синтаксиса в блоке кода используйте три обратных апострофа (&#96;&#96;&#96;).</span><span class="sxs-lookup"><span data-stu-id="df018-421">Use three backticks (&#96;&#96;&#96;) for generic code block coding.</span></span>

> <span data-ttu-id="df018-422">Рекомендуемым подходом является использование блоков кода с идентификаторами языков, как описано в предыдущем разделе, для обеспечения правильного выделения синтаксиса на сайте документации.</span><span class="sxs-lookup"><span data-stu-id="df018-422">The recommended approach is to use code blocks with language identifiers as explained in the previous section to ensure the proper syntax highlighting in the documentation site.</span></span> <span data-ttu-id="df018-423">Используйте общие блоки кода только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="df018-423">Use generic code blocks only when necessary.</span></span>

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a><span data-ttu-id="df018-424">Блок цитирования</span><span class="sxs-lookup"><span data-stu-id="df018-424">Blockquotes</span></span>

> <span data-ttu-id="df018-425">Засуха продолжалась десять миллионов лет, и царству ужасных ящеров уже давно пришел конец.</span><span class="sxs-lookup"><span data-stu-id="df018-425">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="df018-426">Здесь, близ экватора, на материке, который позднее назовут Африкой, с новой яростью вспыхнула борьба за существование, и еще не ясно было, кто выйдет из нее победителем.</span><span class="sxs-lookup"><span data-stu-id="df018-426">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="df018-427">На этой бесплодной, иссушенной зноем земле благоденствовать или хотя бы просто выжить могли только маленькие, или ловкие, или свирепые.</span><span class="sxs-lookup"><span data-stu-id="df018-427">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="df018-428">Изображения</span><span class="sxs-lookup"><span data-stu-id="df018-428">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="df018-429">Статическое изображение или анимационный GIF</span><span class="sxs-lookup"><span data-stu-id="df018-429">Static Image or Animated gif</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![это замещающий текст](../images/Logo_DotNet.png)

### <a name="linked-image"></a><span data-ttu-id="df018-431">Связанное изображение</span><span class="sxs-lookup"><span data-stu-id="df018-431">Linked Image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

<span data-ttu-id="df018-432">[![замещающий текст для связанного изображения](../images/Logo_DotNet.png)](https://dot.net)</span><span class="sxs-lookup"><span data-stu-id="df018-432">[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)</span></span>

## <a name="videos"></a><span data-ttu-id="df018-433">Видеоролики</span><span class="sxs-lookup"><span data-stu-id="df018-433">Videos</span></span>

<span data-ttu-id="df018-434">В настоящее время вы можете внедрить видео Channel 9 и YouTube с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="df018-434">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="df018-435">Канал 9</span><span class="sxs-lookup"><span data-stu-id="df018-435">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="df018-436">Чтобы получить правильный URL-адрес видео, выберите вкладку **Внедрить** под видеокадром и скопируйте URL-адрес из элемента `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="df018-436">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="df018-437">Например:</span><span class="sxs-lookup"><span data-stu-id="df018-437">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="df018-438">YouTube</span><span class="sxs-lookup"><span data-stu-id="df018-438">YouTube</span></span>

<span data-ttu-id="df018-439">Чтобы получить правильный URL-адрес видео, щелкните видео правой кнопкой мыши, выберите **Копировать код внедрения** и скопируйте URL-адрес из элемента `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="df018-439">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="df018-440">Например:</span><span class="sxs-lookup"><span data-stu-id="df018-440">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="df018-441">Расширения docs.microsoft</span><span class="sxs-lookup"><span data-stu-id="df018-441">docs.microsoft extensions</span></span>

<span data-ttu-id="df018-442">docs.microsoft предоставляет несколько дополнительных расширений для GitHub Flavored Markdown.</span><span class="sxs-lookup"><span data-stu-id="df018-442">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="alerts"></a><span data-ttu-id="df018-443">Предупреждения</span><span class="sxs-lookup"><span data-stu-id="df018-443">Alerts</span></span>

<span data-ttu-id="df018-444">Необходимо использовать показанные ниже стили оповещений, чтобы они правильно отображались на сайте документации.</span><span class="sxs-lookup"><span data-stu-id="df018-444">It's important to use the following alert styles so they render with the proper style in the documentation site.</span></span> <span data-ttu-id="df018-445">Однако модуль отрисовки GitHub не различает их.</span><span class="sxs-lookup"><span data-stu-id="df018-445">However, the rendering engine on GitHub doesn't differentiate them.</span></span>

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

<span data-ttu-id="df018-446">Отображение будет таким: ![Стили оповещений](../images/alerts.png)</span><span class="sxs-lookup"><span data-stu-id="df018-446">And they'll render like this: ![Alert styles](../images/alerts.png)</span></span>

### <a name="includes"></a><span data-ttu-id="df018-447">Содержит</span><span class="sxs-lookup"><span data-stu-id="df018-447">Includes</span></span>

<span data-ttu-id="df018-448">Вы можете внедрить Markdown одного файла в другой, используя include.</span><span class="sxs-lookup"><span data-stu-id="df018-448">You can embed the Markdown of one file into another using an include.</span></span>

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a><span data-ttu-id="df018-449">Отмеченные списки</span><span class="sxs-lookup"><span data-stu-id="df018-449">Checked lists</span></span>

<span data-ttu-id="df018-450">Пользовательский стиль доступен для списков.</span><span class="sxs-lookup"><span data-stu-id="df018-450">A custom style is available for lists.</span></span> <span data-ttu-id="df018-451">Можно отобразить списки с зелеными галочками.</span><span class="sxs-lookup"><span data-stu-id="df018-451">You can render lists with green check marks.</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="df018-452">как создать приложение .NET Core;</span><span class="sxs-lookup"><span data-stu-id="df018-452">How to create a .NET Core app</span></span>
> - <span data-ttu-id="df018-453">как добавить ссылку на пакет Microsoft.XmlSerializer.Generator;</span><span class="sxs-lookup"><span data-stu-id="df018-453">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="df018-454">как изменить MyApp.csproj для добавления зависимостей;</span><span class="sxs-lookup"><span data-stu-id="df018-454">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="df018-455">как добавить класс и XmlSerializer;</span><span class="sxs-lookup"><span data-stu-id="df018-455">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="df018-456">как собрать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="df018-456">How to build and run the application</span></span>

<span data-ttu-id="df018-457">Пример отмеченных списков в действии см. в [документации по .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span><span class="sxs-lookup"><span data-stu-id="df018-457">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="df018-458">Кнопки</span><span class="sxs-lookup"><span data-stu-id="df018-458">Buttons</span></span>

> [!div class="button"]
> [<span data-ttu-id="df018-459">ссылки кнопок</span><span class="sxs-lookup"><span data-stu-id="df018-459">button links</span></span>](../docs/core/index.md)

<span data-ttu-id="df018-460">Примеры кнопок в действии можно увидеть в [документации по Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="df018-460">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="selectors"></a><span data-ttu-id="df018-461">Селекторы</span><span class="sxs-lookup"><span data-stu-id="df018-461">Selectors</span></span>

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

<span data-ttu-id="df018-464">Примеры селекторов в действии можно увидеть в [документации по Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span><span class="sxs-lookup"><span data-stu-id="df018-464">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="df018-465">Пошаговые инструкции</span><span class="sxs-lookup"><span data-stu-id="df018-465">Step-By-Steps</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="df018-466">[Назад](../docs/csharp/expression-trees-interpreting.md)
>[Вперед](../docs/csharp/expression-trees-translating.md)</span><span class="sxs-lookup"><span data-stu-id="df018-466">[Previous](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)</span></span>

<span data-ttu-id="df018-467">Примеры пошаговых операций можно увидеть в [руководстве по C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span><span class="sxs-lookup"><span data-stu-id="df018-467">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
