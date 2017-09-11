---
title: "Документирование кода с помощью XML-комментариев"
description: "Сведения о том, как документировать код с использованием комментариев XML-документации и создавать XML-файл документации во время компиляции."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 02/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0cb5725a70d94173c8596f818dcaa6eb2de13bcc
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="documenting-your-code-with-xml-comments"></a><span data-ttu-id="060ab-104">Документирование кода с помощью XML-комментариев</span><span class="sxs-lookup"><span data-stu-id="060ab-104">Documenting your code with XML comments</span></span>

<span data-ttu-id="060ab-105">Комментарии к XML-документации — это особый тип комментария, добавляемого перед определением определяемого пользователем типа или члена.</span><span class="sxs-lookup"><span data-stu-id="060ab-105">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span> <span data-ttu-id="060ab-106">Их особенность в том, что компилятор может обрабатывать их для создания XML-файла документации во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="060ab-106">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="060ab-107">Созданный компилятором XML-файл можно распространять вместе со сборкой .NET, чтобы Visual Studio и другие интегрированные среды разработки могли использовать IntelliSense для отображения кратких сведений о типах или членах.</span><span class="sxs-lookup"><span data-stu-id="060ab-107">The compiler generated XML file can be distributed alongside your .NET assembly so that Visual Studio and other IDEs can use IntelliSense to show quick information about types or members.</span></span> <span data-ttu-id="060ab-108">Кроме того, XML-файл можно запускать с помощью таких средств, как [DocFX](https://dotnet.github.io/docfx/) и [Sandcastle](https://github.com/EWSoftware/SHFB), и создавать веб-сайты со справочными сведениями по API.</span><span class="sxs-lookup"><span data-stu-id="060ab-108">Additionally, the XML file can be run through tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to generate API reference websites.</span></span>

<span data-ttu-id="060ab-109">Комментарии к XML-документации, как и все другие комментарии, пропускаются компилятором.</span><span class="sxs-lookup"><span data-stu-id="060ab-109">XML documentation comments, like all other comments, are ignored by the compiler.</span></span>

<span data-ttu-id="060ab-110">Можно создать XML-файл во время компиляции, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="060ab-110">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="060ab-111">Если вы разрабатываете приложение с использованием .NET Core из командной строки, добавьте [элемент DocumentationFile](http://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties) в раздел `<PropertyGroup>` CSPROJ-файла проекта.</span><span class="sxs-lookup"><span data-stu-id="060ab-111">If you are developing an application with .NET Core from the command line, you can add a [DocumentationFile element](http://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties) to the `<PropertyGroup>` section of your .csproj project file.</span></span> <span data-ttu-id="060ab-112">В следующем примере создается XML-файл в каталоге проекта с тем же именем корневого файла проекта:</span><span class="sxs-lookup"><span data-stu-id="060ab-112">The following example generates an XML file in the project directory with the same root filename as the project:</span></span>

   ```xml
   <DocumentationFile>$(MSBuildProjectName).xml</DocumentationFile>
   ```

   <span data-ttu-id="060ab-113">Также можно указать точный абсолютный или относительный путь и имя XML-файла.</span><span class="sxs-lookup"><span data-stu-id="060ab-113">You can also specify the exact absolute or relative path and name of the XML file.</span></span> <span data-ttu-id="060ab-114">В следующем примере создается XML-файла в одном каталоге с отладочной версией приложения:</span><span class="sxs-lookup"><span data-stu-id="060ab-114">The following example generates the XML file in the same directory as the debug version of an application:</span></span>

    ```xml
   <DocumentationFile>bin\Debug\netcoreapp1.0\App.xml</DocumentationFile>
   ```

- <span data-ttu-id="060ab-115">Если вы разрабатываете приложение с помощью Visual Studio, щелкните правой кнопкой мыши проект и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="060ab-115">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="060ab-116">В диалоговом окне свойств откройте вкладку **Сборка** и выберите **XML-файл документации**.</span><span class="sxs-lookup"><span data-stu-id="060ab-116">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="060ab-117">Можно также изменить расположение, в котором компилятор записывает файл.</span><span class="sxs-lookup"><span data-stu-id="060ab-117">You can also change the location to which the compiler writes the file.</span></span> 

- <span data-ttu-id="060ab-118">Если вы компилируете приложение .NET Framework из командной строки, добавьте [параметр компилятора /doc](language-reference/compiler-options/doc-compiler-option.md) во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="060ab-118">If you are compiling a .NET Framework application from the command line, add the [/doc compiler option](language-reference/compiler-options/doc-compiler-option.md) when compiling.</span></span>  

<span data-ttu-id="060ab-119">Для вставки комментария к XML-документации используются три символа косой черты (`///`) и текст комментария в формате XML.</span><span class="sxs-lookup"><span data-stu-id="060ab-119">XML documentation comments use triple forward slashes (`///`) and an XML formatted comment body.</span></span> <span data-ttu-id="060ab-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="060ab-120">For example:</span></span>

<span data-ttu-id="060ab-121">[!code-csharp[Комментарии XML-документации](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-121">[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]</span></span>

## <a name="walkthrough"></a><span data-ttu-id="060ab-122">Пошаговое руководство</span><span class="sxs-lookup"><span data-stu-id="060ab-122">Walkthrough</span></span>

<span data-ttu-id="060ab-123">Давайте разберем документирование простейшей математической библиотеки, чтобы новые разработчики могли без труда понимать и дополнять ее, а сторонние разработчики — легко использовать ее.</span><span class="sxs-lookup"><span data-stu-id="060ab-123">Let's walk through documenting a very basic math library to make it easy for new developers to understand/contribute and for third party developers to use.</span></span>

<span data-ttu-id="060ab-124">Ниже приведен код для простой математической библиотеки.</span><span class="sxs-lookup"><span data-stu-id="060ab-124">Here's code for the simple math library:</span></span>

<span data-ttu-id="060ab-125">[!code-csharp[Пример библиотеки](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-125">[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]</span></span>

<span data-ttu-id="060ab-126">Пример библиотеки поддерживает четыре основные арифметические операции `add`, `subtract`, `multiply` и `divide` с типами данных `int` и `double`.</span><span class="sxs-lookup"><span data-stu-id="060ab-126">The sample library supports four major arithmetic operations `add`, `subtract`, `multiply` and `divide` on `int` and `double` data types.</span></span>

<span data-ttu-id="060ab-127">Теперь вам нужна возможность создания справочного документа по API из кода для сторонних разработчиков, которые используют библиотеку, но не имеют доступа к исходному коду.</span><span class="sxs-lookup"><span data-stu-id="060ab-127">Now you want to be able to create an API reference document from your code for third party developers who use your library but don't have access to the source code.</span></span>
<span data-ttu-id="060ab-128">Как упоминалось ранее, это можно сделать с помощью тегов XML-документации. Сейчас вы познакомитесь со стандартными XML-тегами, поддерживаемыми компилятором C#.</span><span class="sxs-lookup"><span data-stu-id="060ab-128">As mentioned earlier XML documentation tags can be used to achieve this, You will now be introduced to the standard XML tags the C# compiler supports.</span></span>

### <a name="ltsummarygt"></a><span data-ttu-id="060ab-129">&lt;summary&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-129">&lt;summary&gt;</span></span>

<span data-ttu-id="060ab-130">Тег `<summary>` добавляет краткие сведения о типе или члене.</span><span class="sxs-lookup"><span data-stu-id="060ab-130">The `<summary>` tag adds brief information about a type or member.</span></span>
<span data-ttu-id="060ab-131">Я продемонстрирую использование тега путем его добавления в определение класса `Math` и первый метод `Add`.</span><span class="sxs-lookup"><span data-stu-id="060ab-131">I'll demonstrate its use by adding it to the `Math` class definition and the first `Add` method.</span></span> <span data-ttu-id="060ab-132">Кроме того, его можно применить к остальной части кода.</span><span class="sxs-lookup"><span data-stu-id="060ab-132">Feel free to apply it to the rest of your code.</span></span>

<span data-ttu-id="060ab-133">[!code-csharp[Тег Summary](../../samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-133">[!code-csharp[Summary Tag](../../samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]</span></span>

<span data-ttu-id="060ab-134">Тег `<summary>` имеет очень важное значение, и его рекомендуется включать, так как его содержимое является основным источником информации о типе или члене в IntelliSense или справочном документе по API.</span><span class="sxs-lookup"><span data-stu-id="060ab-134">The `<summary>` tag is very important, and we recommend that you include it because its content is the primary source of type or member information in IntelliSense or an API reference document.</span></span>

### <a name="ltremarksgt"></a><span data-ttu-id="060ab-135">&lt;remarks&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-135">&lt;remarks&gt;</span></span>

<span data-ttu-id="060ab-136">Тег `<remarks>` дополняет сведения о типах или членах, предоставляемые тегом `<summary>`.</span><span class="sxs-lookup"><span data-stu-id="060ab-136">The `<remarks>` tag supplements the information about types or members that the `<summary>` tag provides.</span></span> <span data-ttu-id="060ab-137">В этом примере вы просто добавите его в класс.</span><span class="sxs-lookup"><span data-stu-id="060ab-137">In this example, you'll just add it to the class.</span></span>

<span data-ttu-id="060ab-138">[!code-csharp[Тег Remarks](../../samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-138">[!code-csharp[Remarks Tag](../../samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]</span></span>

### <a name="ltreturnsgt"></a><span data-ttu-id="060ab-139">&lt;returns&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-139">&lt;returns&gt;</span></span>

<span data-ttu-id="060ab-140">Тег `<returns>` описывает возвращаемое значение объявления метода.</span><span class="sxs-lookup"><span data-stu-id="060ab-140">The `<returns>` tag describes the return value of a method declaration.</span></span>
<span data-ttu-id="060ab-141">Как и ранее, в следующем примере демонстрируется тег `<returns>` в первом методе `Add`.</span><span class="sxs-lookup"><span data-stu-id="060ab-141">As before, the following example illustrates the `<returns>` tag on the first `Add` method.</span></span> <span data-ttu-id="060ab-142">То же самое можно сделать и с другими методами.</span><span class="sxs-lookup"><span data-stu-id="060ab-142">You can do the same on other methods.</span></span>

<span data-ttu-id="060ab-143">[!code-csharp[Тег Returns](../../samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-143">[!code-csharp[Returns Tag](../../samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]</span></span>

### <a name="ltvaluegt"></a><span data-ttu-id="060ab-144">&lt;value&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-144">&lt;value&gt;</span></span>

<span data-ttu-id="060ab-145">Тег `<value>` аналогичен тегу `<returns>`, за исключением того, что он используется для свойств.</span><span class="sxs-lookup"><span data-stu-id="060ab-145">The `<value>` tag is similar to the `<returns>` tag, except that you use it for properties.</span></span>
<span data-ttu-id="060ab-146">Если бы в библиотеке `Math` было статическое свойство `PI`, вы использовали бы этот тег следующим образом:</span><span class="sxs-lookup"><span data-stu-id="060ab-146">Assuming your `Math` library had a static property called `PI`, here's how you'd use this tag:</span></span>

<span data-ttu-id="060ab-147">[!code-csharp[Тег Value](../../samples/snippets/csharp/concepts/codedoc/value-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-147">[!code-csharp[Value Tag](../../samples/snippets/csharp/concepts/codedoc/value-tag.cs)]</span></span>

### <a name="ltexamplegt"></a><span data-ttu-id="060ab-148">&lt;example&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-148">&lt;example&gt;</span></span>

<span data-ttu-id="060ab-149">Тег `<example>` применяется для включения примера в XML-документацию.</span><span class="sxs-lookup"><span data-stu-id="060ab-149">You use the `<example>` tag to include an example in your XML documentation.</span></span>
<span data-ttu-id="060ab-150">В этом случае нужно использовать дочерний тег `<code>`.</span><span class="sxs-lookup"><span data-stu-id="060ab-150">This involves using the child `<code>` tag.</span></span>

<span data-ttu-id="060ab-151">[!code-csharp[Тег Example](../../samples/snippets/csharp/concepts/codedoc/example-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-151">[!code-csharp[Example Tag](../../samples/snippets/csharp/concepts/codedoc/example-tag.cs)]</span></span>

<span data-ttu-id="060ab-152">Тег `code` сохраняет разрывы строк и отступы для более длинных примеров.</span><span class="sxs-lookup"><span data-stu-id="060ab-152">The `code` tag preserves line breaks and indentation for longer examples.</span></span>

### <a name="ltparagt"></a><span data-ttu-id="060ab-153">&lt;para&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-153">&lt;para&gt;</span></span>

<span data-ttu-id="060ab-154">Тег `<para>` используется для форматирования содержимого в его родительском теге.</span><span class="sxs-lookup"><span data-stu-id="060ab-154">You use the `<para>` tag to format the content within its parent tag.</span></span> <span data-ttu-id="060ab-155">`<para>` обычно используется внутри тега, такого как `<remarks>` или `<returns>`, чтобы разделить текст на абзацы.</span><span class="sxs-lookup"><span data-stu-id="060ab-155">`<para>` is usually used inside a tag, such as `<remarks>` or `<returns>`, to divide text into paragraphs.</span></span>
<span data-ttu-id="060ab-156">Содержимое тега `<remarks>` для определения класса можно отформатировать.</span><span class="sxs-lookup"><span data-stu-id="060ab-156">You can format the contents of the `<remarks>` tag for your class definition.</span></span>

<span data-ttu-id="060ab-157">[!code-csharp[Тег Para](../../samples/snippets/csharp/concepts/codedoc/para-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-157">[!code-csharp[Para Tag](../../samples/snippets/csharp/concepts/codedoc/para-tag.cs)]</span></span>

### <a name="ltcgt"></a><span data-ttu-id="060ab-158">&lt;c&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-158">&lt;c&gt;</span></span>

<span data-ttu-id="060ab-159">Что касается форматирования, можно использовать тег `<c>` для пометки части текста в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="060ab-159">Still on the topic of formatting, you use the `<c>` tag for marking part of text as code.</span></span>
<span data-ttu-id="060ab-160">Он подобен тегу `<code>`, но является встроенным.</span><span class="sxs-lookup"><span data-stu-id="060ab-160">It's like the `<code>` tag but inline.</span></span> <span data-ttu-id="060ab-161">Он полезен, если требуется показать пример кода как часть содержимого тега.</span><span class="sxs-lookup"><span data-stu-id="060ab-161">It's useful when you want to show a quick code example as part of a tag's content.</span></span>
<span data-ttu-id="060ab-162">Давайте обновим в документацию для класса `Math`.</span><span class="sxs-lookup"><span data-stu-id="060ab-162">Let's update the documentation for the `Math` class.</span></span>

<span data-ttu-id="060ab-163">[!code-csharp[Тег C](../../samples/snippets/csharp/concepts/codedoc/c-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-163">[!code-csharp[C Tag](../../samples/snippets/csharp/concepts/codedoc/c-tag.cs)]</span></span>

### <a name="ltexceptiongt"></a><span data-ttu-id="060ab-164">&lt;exception&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-164">&lt;exception&gt;</span></span>

<span data-ttu-id="060ab-165">С помощью тега `<exception>` можно сообщить разработчикам, что метод может генерировать определенные исключения.</span><span class="sxs-lookup"><span data-stu-id="060ab-165">By using the `<exception>` tag, you let your developers know that a method can throw specific exceptions.</span></span>
<span data-ttu-id="060ab-166">Если взглянуть на библиотеку `Math`, можно увидеть, что оба метода `Add` создают исключение при выполнении определенного условия.</span><span class="sxs-lookup"><span data-stu-id="060ab-166">Looking at your `Math` library, you can see that both `Add` methods throw an exception if a certain condition is met.</span></span> <span data-ttu-id="060ab-167">Метод `Divide` с типом integer также создает исключение (хотя и не столь очевидно), если параметр `b` равен нулю.</span><span class="sxs-lookup"><span data-stu-id="060ab-167">Not so obvious, though, is that integer `Divide` method throws as well if the `b` parameter is zero.</span></span> <span data-ttu-id="060ab-168">Теперь добавьте в этот метод документацию по исключению.</span><span class="sxs-lookup"><span data-stu-id="060ab-168">Now add exception documentation to this method.</span></span>

<span data-ttu-id="060ab-169">[!code-csharp[Тег Exception](../../samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-169">[!code-csharp[Exception Tag](../../samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]</span></span>

<span data-ttu-id="060ab-170">Атрибут `cref` представляет ссылку на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="060ab-170">The `cref` attribute represents a reference to an exception that is available from the current compilation environment.</span></span>
<span data-ttu-id="060ab-171">Это может быть любой тип, определенный в проекте или ссылочной сборке.</span><span class="sxs-lookup"><span data-stu-id="060ab-171">This can be any type defined in the project or a referenced assembly.</span></span> <span data-ttu-id="060ab-172">Компилятор выдаст предупреждение, если его значение не может быть разрешено.</span><span class="sxs-lookup"><span data-stu-id="060ab-172">The compiler will issue a warning if its value cannot be resolved.</span></span>

### <a name="ltseegt"></a><span data-ttu-id="060ab-173">&lt;see&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-173">&lt;see&gt;</span></span>

<span data-ttu-id="060ab-174">Тег `<see>` позволяет создать активную ссылку на страницу документации по другому элементу кода.</span><span class="sxs-lookup"><span data-stu-id="060ab-174">The `<see>` tag lets you create a clickable link to a documentation page for another code element.</span></span> <span data-ttu-id="060ab-175">В следующем примере будет создана активная ссылка между двумя методами `Add`.</span><span class="sxs-lookup"><span data-stu-id="060ab-175">In our next example, we'll create a clickable link between the two `Add` methods.</span></span>

<span data-ttu-id="060ab-176">[!code-csharp[Тег See](../../samples/snippets/csharp/concepts/codedoc/see-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-176">[!code-csharp[See Tag](../../samples/snippets/csharp/concepts/codedoc/see-tag.cs)]</span></span>

<span data-ttu-id="060ab-177">Атрибут `cref` является **обязательным** и представляет ссылку на тип или его член, который доступен из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="060ab-177">The `cref` is a **required** attribute that represents a reference to a type or its member that is available from the current compilation environment.</span></span> <span data-ttu-id="060ab-178">Это может быть любой тип, определенный в проекте или ссылочной сборке.</span><span class="sxs-lookup"><span data-stu-id="060ab-178">This can be any type defined in the project or a referenced assembly.</span></span>

### <a name="ltseealsogt"></a><span data-ttu-id="060ab-179">&lt;seealso&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-179">&lt;seealso&gt;</span></span>

<span data-ttu-id="060ab-180">Тег `<seealso>` используется так же, как тег `<see>`.</span><span class="sxs-lookup"><span data-stu-id="060ab-180">You use the `<seealso>` tag in the same way you do the `<see>` tag.</span></span> <span data-ttu-id="060ab-181">Единственное различие заключается в том, что его содержимое обычно помещается в раздел "См. также".</span><span class="sxs-lookup"><span data-stu-id="060ab-181">The only difference is that its content is typically placed in a "See Also" section.</span></span> <span data-ttu-id="060ab-182">Мы добавим тег `seealso` в метод `Add` с типом integer для ссылки на другие методы в классе, принимающие параметры с типом integer:</span><span class="sxs-lookup"><span data-stu-id="060ab-182">Here we'll add a `seealso` tag on the integer `Add` method to reference other methods in the class that accept integer parameters:</span></span>

<span data-ttu-id="060ab-183">[!code-csharp[Тег Seealso](../../samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-183">[!code-csharp[Seealso Tag](../../samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]</span></span>

<span data-ttu-id="060ab-184">Атрибут `cref` представляет ссылку на тип или его член, который доступен из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="060ab-184">The `cref` attribute represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="060ab-185">Это может быть любой тип, определенный в проекте или ссылочной сборке.</span><span class="sxs-lookup"><span data-stu-id="060ab-185">This can be any type defined in the project or a referenced assembly.</span></span>

### <a name="ltparamgt"></a><span data-ttu-id="060ab-186">&lt;param&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-186">&lt;param&gt;</span></span>

<span data-ttu-id="060ab-187">Тег `<param>` используется для описания параметров метода.</span><span class="sxs-lookup"><span data-stu-id="060ab-187">You use the `<param>` tag to describe a method's parameters.</span></span> <span data-ttu-id="060ab-188">Ниже приведен пример для метода `Add` с типом double: параметр, описываемый тегом, указан в **обязательном** атрибуте `name`.</span><span class="sxs-lookup"><span data-stu-id="060ab-188">Here's an example on the double `Add` method: The parameter the tag describes is specified in the **required** `name` attribute.</span></span>

<span data-ttu-id="060ab-189">[!code-csharp[Тег Param](../../samples/snippets/csharp/concepts/codedoc/param-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-189">[!code-csharp[Param Tag](../../samples/snippets/csharp/concepts/codedoc/param-tag.cs)]</span></span>

### <a name="lttypeparamgt"></a><span data-ttu-id="060ab-190">&lt;typeparam&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-190">&lt;typeparam&gt;</span></span>

<span data-ttu-id="060ab-191">Тег `<typeparam>` используется так же, как тег `<param>`, но для объявлений универсального типа или метода он служит для описания универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="060ab-191">You use `<typeparam>` tag just like the `<param>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="060ab-192">Добавьте в класс `Math` быстрый универсальный метод, чтобы проверить, что одно количество больше другого.</span><span class="sxs-lookup"><span data-stu-id="060ab-192">Add a quick generic method to your `Math` class to check if one quantity is greater than another.</span></span>

<span data-ttu-id="060ab-193">[!code-csharp[Тег Typeparam](../../samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-193">[!code-csharp[Typeparam Tag](../../samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]</span></span>

### <a name="ltparamrefgt"></a><span data-ttu-id="060ab-194">&lt;paramref&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-194">&lt;paramref&gt;</span></span>

<span data-ttu-id="060ab-195">Иногда в процессе описания выполнения метода в теге `<summary>` может потребоваться создание ссылки на параметр.</span><span class="sxs-lookup"><span data-stu-id="060ab-195">Sometimes you might be in the middle of describing what a method does in what could be a `<summary>` tag, and you might want to make a reference to a parameter.</span></span> <span data-ttu-id="060ab-196">Для этого отлично подойдет тег `<paramref>`.</span><span class="sxs-lookup"><span data-stu-id="060ab-196">The `<paramref>` tag is great for just this.</span></span> <span data-ttu-id="060ab-197">Обновим сводку по методу `Add` с типом double.</span><span class="sxs-lookup"><span data-stu-id="060ab-197">Let's update the summary of our double based `Add` method.</span></span> <span data-ttu-id="060ab-198">Как и для тега `<param>`, имя параметра указано в **обязательном** атрибуте `name`.</span><span class="sxs-lookup"><span data-stu-id="060ab-198">Like the `<param>` tag the parameter name is specified in the **required** `name` attribute.</span></span>

<span data-ttu-id="060ab-199">[!code-csharp[Тег Paramref](../../samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-199">[!code-csharp[Paramref Tag](../../samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]</span></span>

### <a name="lttypeparamrefgt"></a><span data-ttu-id="060ab-200">&lt;typeparamref&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-200">&lt;typeparamref&gt;</span></span>

<span data-ttu-id="060ab-201">Тег `<typeparamref>` используется так же, как тег `<paramref>`, но для объявлений универсального типа или метода он служит для описания универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="060ab-201">You use `<typeparamref>` tag just like the `<paramref>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="060ab-202">Можно использовать созданные ранее универсальный метод.</span><span class="sxs-lookup"><span data-stu-id="060ab-202">You can use the same generic method you previously created.</span></span>

<span data-ttu-id="060ab-203">[!code-csharp[Тег Typeparamref](../../samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-203">[!code-csharp[Typeparamref Tag](../../samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]</span></span>

### <a name="ltlistgt"></a><span data-ttu-id="060ab-204">&lt;list&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-204">&lt;list&gt;</span></span>

<span data-ttu-id="060ab-205">Тег `<list>` используется для форматирования сведений о документации в виде упорядоченного списка, неупорядоченного списка или таблицы.</span><span class="sxs-lookup"><span data-stu-id="060ab-205">You use the `<list>` tag to format documentation information as an ordered list, unordered list or table.</span></span>
<span data-ttu-id="060ab-206">Создайте неупорядоченный список для каждой математической операции, поддерживаемой библиотекой `Math`.</span><span class="sxs-lookup"><span data-stu-id="060ab-206">Make an unordered list of every math operation your `Math` library supports.</span></span>

<span data-ttu-id="060ab-207">[!code-csharp[Тег List](../../samples/snippets/csharp/concepts/codedoc/list-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-207">[!code-csharp[List Tag](../../samples/snippets/csharp/concepts/codedoc/list-tag.cs)]</span></span>

<span data-ttu-id="060ab-208">Упорядоченный список или таблицу можно сформировать, изменив атрибут `type` на `number` или `table` соответственно.</span><span class="sxs-lookup"><span data-stu-id="060ab-208">You can make an ordered list or table by changing the `type` attribute to `number` or `table`, respectively.</span></span>

### <a name="putting-it-all-together"></a><span data-ttu-id="060ab-209">Заключение</span><span class="sxs-lookup"><span data-stu-id="060ab-209">Putting it all together</span></span>

<span data-ttu-id="060ab-210">Вы выполнили инструкции в этом учебнике и включили теги в код там, где необходимо. Теперь ваш код должен иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="060ab-210">If you've followed this tutorial and applied the tags to your code where necessary, your code should now look similar to the following:</span></span>

<span data-ttu-id="060ab-211">[!code-csharp[Библиотека с тегами](../../samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-211">[!code-csharp[Tagged Library](../../samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]</span></span>

<span data-ttu-id="060ab-212">В коде можно создать подробную документацию к веб-сайту, содержащую интерактивные перекрестные ссылки.</span><span class="sxs-lookup"><span data-stu-id="060ab-212">From your code, you can generate a detailed documentation website complete with clickable cross-references.</span></span> <span data-ttu-id="060ab-213">При этом вы можете столкнуться с другой проблемой — такой код очень трудно читать.</span><span class="sxs-lookup"><span data-stu-id="060ab-213">But you're faced with another problem: your code has become hard to read.</span></span>
<span data-ttu-id="060ab-214">Для любого разработчика, который хочет вносить дополнения в этот код, необходимость обработки большого количества данных становится настоящим кошмаром.</span><span class="sxs-lookup"><span data-stu-id="060ab-214">There's so much information to sift through that this is going to be a nightmare for any developer who wants to contribute to this code.</span></span> <span data-ttu-id="060ab-215">К счастью, есть XML-тег, который поможет справиться с этой задачей:</span><span class="sxs-lookup"><span data-stu-id="060ab-215">Thankfully there's an XML tag that can help you deal with this:</span></span>

### <a name="ltincludegt"></a><span data-ttu-id="060ab-216">&lt;include&gt;</span><span class="sxs-lookup"><span data-stu-id="060ab-216">&lt;include&gt;</span></span>

<span data-ttu-id="060ab-217">Тег `<include>` позволяет обращаться к комментариям в отдельном XML-файле, описывающем типы и члены в исходном коде, а не размещать комментарии к документации непосредственно в файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="060ab-217">The `<include>` tag lets you refer to comments in a separate XML file that describe the types and members in your source code, as opposed to placing documentation comments directly in your source code file.</span></span>

<span data-ttu-id="060ab-218">Переместим все XML-теги в отдельный файл XML с именем `docs.xml`.</span><span class="sxs-lookup"><span data-stu-id="060ab-218">Now you're going to move all your XML tags into a separate XML file named `docs.xml`.</span></span> <span data-ttu-id="060ab-219">Файлу можно задать любое имя.</span><span class="sxs-lookup"><span data-stu-id="060ab-219">Feel free to name the file whatever you want.</span></span>

<span data-ttu-id="060ab-220">[!code-xml[Образец XML](../../samples/snippets/csharp/concepts/codedoc/include.xml)]</span><span class="sxs-lookup"><span data-stu-id="060ab-220">[!code-xml[Sample XML](../../samples/snippets/csharp/concepts/codedoc/include.xml)]</span></span>

<span data-ttu-id="060ab-221">В приведенном выше XML комментарии к документации по каждому члену отображаются непосредственно внутри тега с именем, соответствующим его назначению.</span><span class="sxs-lookup"><span data-stu-id="060ab-221">In the above XML, each member's documentation comments appear directly inside a tag named after what they do.</span></span> <span data-ttu-id="060ab-222">Можно выбрать собственную стратегию.</span><span class="sxs-lookup"><span data-stu-id="060ab-222">You can choose your own strategy.</span></span> <span data-ttu-id="060ab-223">Теперь, когда комментарии XML находятся в отдельном файле, давайте посмотрим, как можно улучшить удобочитаемость кода с помощью тега `<include>`.</span><span class="sxs-lookup"><span data-stu-id="060ab-223">Now that you have your XML comments in a separate file, let's see how your code can be made more readable by using the `<include>` tag:</span></span>

<span data-ttu-id="060ab-224">[!code-csharp[Тег Include](../../samples/snippets/csharp/concepts/codedoc/include-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="060ab-224">[!code-csharp[Include Tag](../../samples/snippets/csharp/concepts/codedoc/include-tag.cs)]</span></span>

<span data-ttu-id="060ab-225">Сейчас чтение кода снова не вызывает сложностей, и никакие сведения не были потеряны.</span><span class="sxs-lookup"><span data-stu-id="060ab-225">And there you have it: our code is back to being readable, and no documentation information has been lost.</span></span> 

<span data-ttu-id="060ab-226">Атрибут `filename` представляет имя XML-файла, содержащего документацию.</span><span class="sxs-lookup"><span data-stu-id="060ab-226">The `filename` attribute represents the name of the XML file containing the documentation.</span></span>

<span data-ttu-id="060ab-227">Атрибут `path` представляет запрос [XPath](https://msdn.microsoft.com/library/ms256115.aspx) к `tag name`, находящемуся в указанном `filename`.</span><span class="sxs-lookup"><span data-stu-id="060ab-227">The `path` attribute represents an [XPath](https://msdn.microsoft.com/library/ms256115.aspx) query to the `tag name` present in the specified `filename`.</span></span>

<span data-ttu-id="060ab-228">Атрибут `name` представляет спецификатор имени в теге, который предшествует комментариям.</span><span class="sxs-lookup"><span data-stu-id="060ab-228">The `name` attribute represents the name specifier in the tag that precedes the comments.</span></span>

<span data-ttu-id="060ab-229">Атрибут `id`, который может использоваться вместо `name`, представляет идентификатор для тега, предшествующего комментариям.</span><span class="sxs-lookup"><span data-stu-id="060ab-229">The `id` attribute which can be used in place of `name` represents the ID for the tag that precedes the comments.</span></span>

### <a name="user-defined-tags"></a><span data-ttu-id="060ab-230">Определяемые пользователем теги</span><span class="sxs-lookup"><span data-stu-id="060ab-230">User Defined Tags</span></span>

<span data-ttu-id="060ab-231">Все описанные выше теги распознаются компилятором C#.</span><span class="sxs-lookup"><span data-stu-id="060ab-231">All the tags outlined above represent those that are recognized by the C# compiler.</span></span> <span data-ttu-id="060ab-232">Тем не менее пользователь может определять собственные теги.</span><span class="sxs-lookup"><span data-stu-id="060ab-232">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="060ab-233">Инструменты, такие как Sandcastle, обеспечивают поддержку дополнительных тегов, например [`<event>`](http://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [`<note>`](http://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm), и даже поддержку [пространств имен документирования](http://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span><span class="sxs-lookup"><span data-stu-id="060ab-233">Tools like Sandcastle bring support for extra tags like [`<event>`](http://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [`<note>`](http://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) and even support [documenting namespaces](http://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span></span>
<span data-ttu-id="060ab-234">Средства создания пользовательской или внутренней документации также можно использовать со стандартными тегами. Кроме того, поддерживается несколько выходных форматов — от HTML до PDF.</span><span class="sxs-lookup"><span data-stu-id="060ab-234">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="recommendations"></a><span data-ttu-id="060ab-235">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="060ab-235">Recommendations</span></span>

<span data-ttu-id="060ab-236">Документирование кода рекомендуется по многим причинам.</span><span class="sxs-lookup"><span data-stu-id="060ab-236">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="060ab-237">Далее приводится ряд рекомендаций, распространенные сценарии использования и вопросы, которые нужно иметь в виду при работе с тегами XML-документации в коде C#.</span><span class="sxs-lookup"><span data-stu-id="060ab-237">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your C# code.</span></span>

* <span data-ttu-id="060ab-238">Для обеспечения согласованности все открытые типы и их члены должны быть задокументированы.</span><span class="sxs-lookup"><span data-stu-id="060ab-238">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="060ab-239">Если это необходимо, задокументируйте их все.</span><span class="sxs-lookup"><span data-stu-id="060ab-239">If you must do it, do it all.</span></span>
* <span data-ttu-id="060ab-240">Закрытые члены можно также задокументировать с помощью XML-комментариев.</span><span class="sxs-lookup"><span data-stu-id="060ab-240">Private members can also be documented using XML comments.</span></span> <span data-ttu-id="060ab-241">Однако это приводит к раскрытию внутренних (возможно, конфиденциальных) процессов библиотеки.</span><span class="sxs-lookup"><span data-stu-id="060ab-241">However, this exposes the inner (potentially confidential) workings of your library.</span></span>
* <span data-ttu-id="060ab-242">Как минимум, типы и их члены должен иметь тег `<summary>`, так как его содержимое требуется для IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="060ab-242">At a bare minimum, types and their members should have a `<summary>` tag because its content is needed for IntelliSense.</span></span>
* <span data-ttu-id="060ab-243">Текст документации должны быть написан с использованием законченных предложений, в конце которых ставится точка.</span><span class="sxs-lookup"><span data-stu-id="060ab-243">Documentation text should be written using complete sentences ending with full stops.</span></span>
* <span data-ttu-id="060ab-244">Разделяемые классы полностью поддерживаются, и данные о документации объединяются в одну запись для этого типа.</span><span class="sxs-lookup"><span data-stu-id="060ab-244">Partial classes are fully supported, and documentation information will be concatenated into a single entry for that type.</span></span>
* <span data-ttu-id="060ab-245">Компилятор проверяет синтаксис тегов `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` и `<typeparam>`.</span><span class="sxs-lookup"><span data-stu-id="060ab-245">The compiler verifies the syntax of the `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` and `<typeparam>` tags.</span></span>
- <span data-ttu-id="060ab-246">Компилятор проверяет параметры, которые содержат пути к файлам и ссылки на другие части кода.</span><span class="sxs-lookup"><span data-stu-id="060ab-246">The compiler validates the parameters that contain file paths and references to other parts of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="060ab-247">См. также</span><span class="sxs-lookup"><span data-stu-id="060ab-247">See also</span></span>
[<span data-ttu-id="060ab-248">Комментарии к XML-документации (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="060ab-248">XML Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/xml-documentation-comments.md)

[<span data-ttu-id="060ab-249">Рекомендуемые теги для комментариев документации (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="060ab-249">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

