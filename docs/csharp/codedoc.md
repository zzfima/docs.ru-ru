---
title: Документирование кода с помощью XML-комментариев
description: Сведения о том, как документировать код с использованием комментариев XML-документации и создавать XML-файл документации во время компиляции.
ms.date: 02/14/2017
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.openlocfilehash: 048546407dbf94f274dd8c9c39e83c103efd75e1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521168"
---
# <a name="documenting-your-code-with-xml-comments"></a><span data-ttu-id="51104-103">Документирование кода с помощью XML-комментариев</span><span class="sxs-lookup"><span data-stu-id="51104-103">Documenting your code with XML comments</span></span>

<span data-ttu-id="51104-104">Комментарии к XML-документации — это особый тип комментария, добавляемого перед определением определяемого пользователем типа или члена.</span><span class="sxs-lookup"><span data-stu-id="51104-104">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span>
<span data-ttu-id="51104-105">Их особенность в том, что компилятор может обрабатывать их для создания XML-файла документации во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="51104-105">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="51104-106">Созданный компилятором XML-файл можно распространять вместе со сборкой .NET, чтобы Visual Studio и другие интегрированные среды разработки могли использовать IntelliSense для отображения кратких сведений о типах или членах.</span><span class="sxs-lookup"><span data-stu-id="51104-106">The compiler generated XML file can be distributed alongside your .NET assembly so that Visual Studio and other IDEs can use IntelliSense to show quick information about types or members.</span></span> <span data-ttu-id="51104-107">Кроме того, XML-файл можно запускать с помощью таких средств, как [DocFX](https://dotnet.github.io/docfx/) и [Sandcastle](https://github.com/EWSoftware/SHFB), и создавать веб-сайты со справочными сведениями по API.</span><span class="sxs-lookup"><span data-stu-id="51104-107">Additionally, the XML file can be run through tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to generate API reference websites.</span></span>

<span data-ttu-id="51104-108">Комментарии к XML-документации, как и все другие комментарии, пропускаются компилятором.</span><span class="sxs-lookup"><span data-stu-id="51104-108">XML documentation comments, like all other comments, are ignored by the compiler.</span></span>

<span data-ttu-id="51104-109">Можно создать XML-файл во время компиляции, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="51104-109">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="51104-110">Если вы разрабатываете приложение с использованием .NET Core из командной строки, добавьте [элемент DocumentationFile](/visualstudio/msbuild/common-msbuild-project-properties) в раздел `<PropertyGroup>` CSPROJ-файла проекта.</span><span class="sxs-lookup"><span data-stu-id="51104-110">If you are developing an application with .NET Core from the command line, you can add a [DocumentationFile element](/visualstudio/msbuild/common-msbuild-project-properties) to the `<PropertyGroup>` section of your .csproj project file.</span></span> <span data-ttu-id="51104-111">В следующем примере создается XML-файл в каталоге проекта с тем же именем корневого файла, что и у сборки:</span><span class="sxs-lookup"><span data-stu-id="51104-111">The following example generates an XML file in the project directory with the same root filename as the assembly:</span></span>

   ```xml
   <DocumentationFile>bin\$(Configuration)\$(TargetFramework)\$(AssemblyName).xml</DocumentationFile>
   ```

   <span data-ttu-id="51104-112">Также можно указать точный абсолютный или относительный путь и имя XML-файла.</span><span class="sxs-lookup"><span data-stu-id="51104-112">You can also specify the exact absolute or relative path and name of the XML file.</span></span> <span data-ttu-id="51104-113">В следующем примере создается XML-файла в одном каталоге с отладочной версией приложения:</span><span class="sxs-lookup"><span data-stu-id="51104-113">The following example generates the XML file in the same directory as the debug version of an application:</span></span>

   ```xml
   <DocumentationFile>bin\Debug\netcoreapp2.1\App.xml</DocumentationFile>
   ```

- <span data-ttu-id="51104-114">Если вы разрабатываете приложение с помощью Visual Studio, щелкните правой кнопкой мыши проект и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="51104-114">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="51104-115">В диалоговом окне свойств откройте вкладку **Сборка** и выберите **XML-файл документации**.</span><span class="sxs-lookup"><span data-stu-id="51104-115">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="51104-116">Можно также изменить расположение, в котором компилятор записывает файл.</span><span class="sxs-lookup"><span data-stu-id="51104-116">You can also change the location to which the compiler writes the file.</span></span>

- <span data-ttu-id="51104-117">Если вы компилируете приложение .NET Framework из командной строки, добавьте [параметр компилятора -doc](language-reference/compiler-options/doc-compiler-option.md) во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="51104-117">If you are compiling a .NET Framework application from the command line, add the [-doc compiler option](language-reference/compiler-options/doc-compiler-option.md) when compiling.</span></span>  

<span data-ttu-id="51104-118">Для вставки комментария к XML-документации используются три символа косой черты (`///`) и текст комментария в формате XML.</span><span class="sxs-lookup"><span data-stu-id="51104-118">XML documentation comments use triple forward slashes (`///`) and an XML formatted comment body.</span></span> <span data-ttu-id="51104-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="51104-119">For example:</span></span>

[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]

## <a name="walkthrough"></a><span data-ttu-id="51104-120">Пошаговое руководство</span><span class="sxs-lookup"><span data-stu-id="51104-120">Walkthrough</span></span>

<span data-ttu-id="51104-121">Давайте разберем документирование простейшей математической библиотеки, чтобы новые разработчики могли без труда понимать и дополнять ее, а сторонние разработчики — легко использовать ее.</span><span class="sxs-lookup"><span data-stu-id="51104-121">Let's walk through documenting a very basic math library to make it easy for new developers to understand/contribute and for third party developers to use.</span></span>

<span data-ttu-id="51104-122">Ниже приведен код для простой математической библиотеки.</span><span class="sxs-lookup"><span data-stu-id="51104-122">Here's code for the simple math library:</span></span>

[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]

<span data-ttu-id="51104-123">Пример библиотеки поддерживает четыре основные арифметические операции `add`, `subtract`, `multiply` и `divide` с типами данных `int` и `double`.</span><span class="sxs-lookup"><span data-stu-id="51104-123">The sample library supports four major arithmetic operations `add`, `subtract`, `multiply` and `divide` on `int` and `double` data types.</span></span>

<span data-ttu-id="51104-124">Теперь вам нужна возможность создания справочного документа по API из кода для сторонних разработчиков, которые используют библиотеку, но не имеют доступа к исходному коду.</span><span class="sxs-lookup"><span data-stu-id="51104-124">Now you want to be able to create an API reference document from your code for third party developers who use your library but don't have access to the source code.</span></span>
<span data-ttu-id="51104-125">Как упоминалось ранее, это можно сделать с помощью тегов XML-документации.</span><span class="sxs-lookup"><span data-stu-id="51104-125">As mentioned earlier XML documentation tags can be used to achieve this.</span></span> <span data-ttu-id="51104-126">Сейчас вы познакомитесь со стандартными XML-тегами, которые поддерживает компилятор C#.</span><span class="sxs-lookup"><span data-stu-id="51104-126">You will now be introduced to the standard XML tags the C# compiler supports.</span></span>

## <a name="summary"></a><span data-ttu-id="51104-127">\<summary></span><span class="sxs-lookup"><span data-stu-id="51104-127">\<summary></span></span>

<span data-ttu-id="51104-128">Тег `<summary>` добавляет краткие сведения о типе или члене.</span><span class="sxs-lookup"><span data-stu-id="51104-128">The `<summary>` tag adds brief information about a type or member.</span></span>
<span data-ttu-id="51104-129">Я продемонстрирую использование тега путем его добавления в определение класса `Math` и первый метод `Add`.</span><span class="sxs-lookup"><span data-stu-id="51104-129">I'll demonstrate its use by adding it to the `Math` class definition and the first `Add` method.</span></span> <span data-ttu-id="51104-130">Кроме того, его можно применить к остальной части кода.</span><span class="sxs-lookup"><span data-stu-id="51104-130">Feel free to apply it to the rest of your code.</span></span>

[!code-csharp[Summary Tag](../../samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]

<span data-ttu-id="51104-131">Тег `<summary>` имеет очень важное значение, и его рекомендуется включать, так как его содержимое является основным источником информации о типе или члене в IntelliSense или справочном документе по API.</span><span class="sxs-lookup"><span data-stu-id="51104-131">The `<summary>` tag is very important, and we recommend that you include it because its content is the primary source of type or member information in IntelliSense or an API reference document.</span></span>

## <a name="remarks"></a><span data-ttu-id="51104-132">\<remarks></span><span class="sxs-lookup"><span data-stu-id="51104-132">\<remarks></span></span>

<span data-ttu-id="51104-133">Тег `<remarks>` дополняет сведения о типах или членах, предоставляемые тегом `<summary>`.</span><span class="sxs-lookup"><span data-stu-id="51104-133">The `<remarks>` tag supplements the information about types or members that the `<summary>` tag provides.</span></span> <span data-ttu-id="51104-134">В этом примере вы просто добавите его в класс.</span><span class="sxs-lookup"><span data-stu-id="51104-134">In this example, you'll just add it to the class.</span></span>

[!code-csharp[Remarks Tag](../../samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]

## <a name="returns"></a><span data-ttu-id="51104-135">\<returns></span><span class="sxs-lookup"><span data-stu-id="51104-135">\<returns></span></span>

<span data-ttu-id="51104-136">Тег `<returns>` описывает возвращаемое значение объявления метода.</span><span class="sxs-lookup"><span data-stu-id="51104-136">The `<returns>` tag describes the return value of a method declaration.</span></span>
<span data-ttu-id="51104-137">Как и ранее, в следующем примере демонстрируется тег `<returns>` в первом методе `Add`.</span><span class="sxs-lookup"><span data-stu-id="51104-137">As before, the following example illustrates the `<returns>` tag on the first `Add` method.</span></span> <span data-ttu-id="51104-138">То же самое можно сделать и с другими методами.</span><span class="sxs-lookup"><span data-stu-id="51104-138">You can do the same on other methods.</span></span>

[!code-csharp[Returns Tag](../../samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]

## <a name="value"></a><span data-ttu-id="51104-139">\<value></span><span class="sxs-lookup"><span data-stu-id="51104-139">\<value></span></span>

<span data-ttu-id="51104-140">Тег `<value>` аналогичен тегу `<returns>`, за исключением того, что он используется для свойств.</span><span class="sxs-lookup"><span data-stu-id="51104-140">The `<value>` tag is similar to the `<returns>` tag, except that you use it for properties.</span></span>
<span data-ttu-id="51104-141">Если бы в библиотеке `Math` было статическое свойство `PI`, вы использовали бы этот тег следующим образом:</span><span class="sxs-lookup"><span data-stu-id="51104-141">Assuming your `Math` library had a static property called `PI`, here's how you'd use this tag:</span></span>

[!code-csharp[Value Tag](../../samples/snippets/csharp/concepts/codedoc/value-tag.cs)]

## <a name="example"></a><span data-ttu-id="51104-142">\<example></span><span class="sxs-lookup"><span data-stu-id="51104-142">\<example></span></span>

<span data-ttu-id="51104-143">Тег `<example>` применяется для включения примера в XML-документацию.</span><span class="sxs-lookup"><span data-stu-id="51104-143">You use the `<example>` tag to include an example in your XML documentation.</span></span>
<span data-ttu-id="51104-144">В этом случае нужно использовать дочерний тег `<code>`.</span><span class="sxs-lookup"><span data-stu-id="51104-144">This involves using the child `<code>` tag.</span></span>

[!code-csharp[Example Tag](../../samples/snippets/csharp/concepts/codedoc/example-tag.cs)]

<span data-ttu-id="51104-145">Тег `code` сохраняет разрывы строк и отступы для более длинных примеров.</span><span class="sxs-lookup"><span data-stu-id="51104-145">The `code` tag preserves line breaks and indentation for longer examples.</span></span>

## <a name="para"></a><span data-ttu-id="51104-146">\<para></span><span class="sxs-lookup"><span data-stu-id="51104-146">\<para></span></span>

<span data-ttu-id="51104-147">Тег `<para>` используется для форматирования содержимого в его родительском теге.</span><span class="sxs-lookup"><span data-stu-id="51104-147">You use the `<para>` tag to format the content within its parent tag.</span></span> <span data-ttu-id="51104-148">`<para>` обычно используется внутри тега, такого как `<remarks>` или `<returns>`, чтобы разделить текст на абзацы.</span><span class="sxs-lookup"><span data-stu-id="51104-148">`<para>` is usually used inside a tag, such as `<remarks>` or `<returns>`, to divide text into paragraphs.</span></span>
<span data-ttu-id="51104-149">Содержимое тега `<remarks>` для определения класса можно отформатировать.</span><span class="sxs-lookup"><span data-stu-id="51104-149">You can format the contents of the `<remarks>` tag for your class definition.</span></span>

[!code-csharp[Para Tag](../../samples/snippets/csharp/concepts/codedoc/para-tag.cs)]

## <a name="c"></a><span data-ttu-id="51104-150">\<c></span><span class="sxs-lookup"><span data-stu-id="51104-150">\<c></span></span>

<span data-ttu-id="51104-151">Что касается форматирования, можно использовать тег `<c>` для пометки части текста в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="51104-151">Still on the topic of formatting, you use the `<c>` tag for marking part of text as code.</span></span>
<span data-ttu-id="51104-152">Он подобен тегу `<code>`, но является встроенным.</span><span class="sxs-lookup"><span data-stu-id="51104-152">It's like the `<code>` tag but inline.</span></span> <span data-ttu-id="51104-153">Он полезен, если требуется показать пример кода как часть содержимого тега.</span><span class="sxs-lookup"><span data-stu-id="51104-153">It's useful when you want to show a quick code example as part of a tag's content.</span></span>
<span data-ttu-id="51104-154">Давайте обновим в документацию для класса `Math`.</span><span class="sxs-lookup"><span data-stu-id="51104-154">Let's update the documentation for the `Math` class.</span></span>

[!code-csharp[C Tag](../../samples/snippets/csharp/concepts/codedoc/c-tag.cs)]

## <a name="exception"></a><span data-ttu-id="51104-155">\<exception></span><span class="sxs-lookup"><span data-stu-id="51104-155">\<exception></span></span>

<span data-ttu-id="51104-156">С помощью тега `<exception>` можно сообщить разработчикам, что метод может генерировать определенные исключения.</span><span class="sxs-lookup"><span data-stu-id="51104-156">By using the `<exception>` tag, you let your developers know that a method can throw specific exceptions.</span></span>
<span data-ttu-id="51104-157">Если взглянуть на библиотеку `Math`, можно увидеть, что оба метода `Add` создают исключение при выполнении определенного условия.</span><span class="sxs-lookup"><span data-stu-id="51104-157">Looking at your `Math` library, you can see that both `Add` methods throw an exception if a certain condition is met.</span></span> <span data-ttu-id="51104-158">Метод `Divide` с типом integer также создает исключение (хотя и не столь очевидно), если параметр `b` равен нулю.</span><span class="sxs-lookup"><span data-stu-id="51104-158">Not so obvious, though, is that integer `Divide` method throws as well if the `b` parameter is zero.</span></span> <span data-ttu-id="51104-159">Теперь добавьте в этот метод документацию по исключению.</span><span class="sxs-lookup"><span data-stu-id="51104-159">Now add exception documentation to this method.</span></span>

[!code-csharp[Exception Tag](../../samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]

<span data-ttu-id="51104-160">Атрибут `cref` представляет ссылку на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="51104-160">The `cref` attribute represents a reference to an exception that is available from the current compilation environment.</span></span>
<span data-ttu-id="51104-161">Это может быть любой тип, определенный в проекте или ссылочной сборке.</span><span class="sxs-lookup"><span data-stu-id="51104-161">This can be any type defined in the project or a referenced assembly.</span></span> <span data-ttu-id="51104-162">Компилятор выдаст предупреждение, если его значение не может быть разрешено.</span><span class="sxs-lookup"><span data-stu-id="51104-162">The compiler will issue a warning if its value cannot be resolved.</span></span>

## <a name="see"></a><span data-ttu-id="51104-163">\<see></span><span class="sxs-lookup"><span data-stu-id="51104-163">\<see></span></span>

<span data-ttu-id="51104-164">Тег `<see>` позволяет создать активную ссылку на страницу документации по другому элементу кода.</span><span class="sxs-lookup"><span data-stu-id="51104-164">The `<see>` tag lets you create a clickable link to a documentation page for another code element.</span></span> <span data-ttu-id="51104-165">В следующем примере будет создана активная ссылка между двумя методами `Add`.</span><span class="sxs-lookup"><span data-stu-id="51104-165">In our next example, we'll create a clickable link between the two `Add` methods.</span></span>

[!code-csharp[See Tag](../../samples/snippets/csharp/concepts/codedoc/see-tag.cs)]

<span data-ttu-id="51104-166">Атрибут `cref` является **обязательным** и представляет ссылку на тип или его член, который доступен из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="51104-166">The `cref` is a **required** attribute that represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="51104-167">Это может быть любой тип, определенный в проекте или ссылочной сборке.</span><span class="sxs-lookup"><span data-stu-id="51104-167">This can be any type defined in the project or a referenced assembly.</span></span>

## <a name="seealso"></a><span data-ttu-id="51104-168">\<seealso></span><span class="sxs-lookup"><span data-stu-id="51104-168">\<seealso></span></span>

<span data-ttu-id="51104-169">Тег `<seealso>` используется так же, как тег `<see>`.</span><span class="sxs-lookup"><span data-stu-id="51104-169">You use the `<seealso>` tag in the same way you do the `<see>` tag.</span></span> <span data-ttu-id="51104-170">Единственное различие заключается в том, что его содержимое обычно помещается в раздел "См. также".</span><span class="sxs-lookup"><span data-stu-id="51104-170">The only difference is that its content is typically placed in a "See Also" section.</span></span> <span data-ttu-id="51104-171">Мы добавим тег `seealso` в метод `Add` с типом integer для ссылки на другие методы в классе, принимающие параметры с типом integer:</span><span class="sxs-lookup"><span data-stu-id="51104-171">Here we'll add a `seealso` tag on the integer `Add` method to reference other methods in the class that accept integer parameters:</span></span>

[!code-csharp[Seealso Tag](../../samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]

<span data-ttu-id="51104-172">Атрибут `cref` представляет ссылку на тип или его член, который доступен из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="51104-172">The `cref` attribute represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="51104-173">Это может быть любой тип, определенный в проекте или ссылочной сборке.</span><span class="sxs-lookup"><span data-stu-id="51104-173">This can be any type defined in the project or a referenced assembly.</span></span>

## <a name="param"></a><span data-ttu-id="51104-174">\<param></span><span class="sxs-lookup"><span data-stu-id="51104-174">\<param></span></span>

<span data-ttu-id="51104-175">Тег `<param>` используется для описания параметров метода.</span><span class="sxs-lookup"><span data-stu-id="51104-175">You use the `<param>` tag to describe a method's parameters.</span></span> <span data-ttu-id="51104-176">Ниже приведен пример метода double `Add`: Параметр, описываемый тегом, указан в **обязательном** атрибуте `name`.</span><span class="sxs-lookup"><span data-stu-id="51104-176">Here's an example on the double `Add` method: The parameter the tag describes is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Param Tag](../../samples/snippets/csharp/concepts/codedoc/param-tag.cs)]

## <a name="typeparam"></a><span data-ttu-id="51104-177">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="51104-177">\<typeparam></span></span>

<span data-ttu-id="51104-178">Тег `<typeparam>` используется так же, как тег `<param>`, но для объявлений универсального типа или метода он служит для описания универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="51104-178">You use `<typeparam>` tag just like the `<param>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="51104-179">Добавьте в класс `Math` быстрый универсальный метод, чтобы проверить, что одно количество больше другого.</span><span class="sxs-lookup"><span data-stu-id="51104-179">Add a quick generic method to your `Math` class to check if one quantity is greater than another.</span></span>

[!code-csharp[Typeparam Tag](../../samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]

## <a name="paramref"></a><span data-ttu-id="51104-180">\<paramref></span><span class="sxs-lookup"><span data-stu-id="51104-180">\<paramref></span></span>

<span data-ttu-id="51104-181">Иногда в процессе описания выполнения метода в теге `<summary>` может потребоваться создание ссылки на параметр.</span><span class="sxs-lookup"><span data-stu-id="51104-181">Sometimes you might be in the middle of describing what a method does in what could be a `<summary>` tag, and you might want to make a reference to a parameter.</span></span> <span data-ttu-id="51104-182">Для этого отлично подойдет тег `<paramref>`.</span><span class="sxs-lookup"><span data-stu-id="51104-182">The `<paramref>` tag is great for just this.</span></span> <span data-ttu-id="51104-183">Обновим сводку по методу `Add` с типом double.</span><span class="sxs-lookup"><span data-stu-id="51104-183">Let's update the summary of our double based `Add` method.</span></span> <span data-ttu-id="51104-184">Как и для тега `<param>`, имя параметра указано в **обязательном** атрибуте `name`.</span><span class="sxs-lookup"><span data-stu-id="51104-184">Like the `<param>` tag the parameter name is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Paramref Tag](../../samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]

## <a name="typeparamref"></a><span data-ttu-id="51104-185">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="51104-185">\<typeparamref></span></span>

<span data-ttu-id="51104-186">Тег `<typeparamref>` используется так же, как тег `<paramref>`, но для объявлений универсального типа или метода он служит для описания универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="51104-186">You use `<typeparamref>` tag just like the `<paramref>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="51104-187">Можно использовать созданные ранее универсальный метод.</span><span class="sxs-lookup"><span data-stu-id="51104-187">You can use the same generic method you previously created.</span></span>

[!code-csharp[Typeparamref Tag](../../samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]

## <a name="list"></a><span data-ttu-id="51104-188">\<list></span><span class="sxs-lookup"><span data-stu-id="51104-188">\<list></span></span>

<span data-ttu-id="51104-189">Тег `<list>` используется для форматирования сведений о документации в виде упорядоченного списка, неупорядоченного списка или таблицы.</span><span class="sxs-lookup"><span data-stu-id="51104-189">You use the `<list>` tag to format documentation information as an ordered list, unordered list or table.</span></span>
<span data-ttu-id="51104-190">Создайте неупорядоченный список для каждой математической операции, поддерживаемой библиотекой `Math`.</span><span class="sxs-lookup"><span data-stu-id="51104-190">Make an unordered list of every math operation your `Math` library supports.</span></span>

[!code-csharp[List Tag](../../samples/snippets/csharp/concepts/codedoc/list-tag.cs)]

<span data-ttu-id="51104-191">Упорядоченный список или таблицу можно сформировать, изменив атрибут `type` на `number` или `table` соответственно.</span><span class="sxs-lookup"><span data-stu-id="51104-191">You can make an ordered list or table by changing the `type` attribute to `number` or `table`, respectively.</span></span>

### <a name="putting-it-all-together"></a><span data-ttu-id="51104-192">Заключение</span><span class="sxs-lookup"><span data-stu-id="51104-192">Putting it all together</span></span>

<span data-ttu-id="51104-193">Вы выполнили инструкции в этом учебнике и включили теги в код там, где необходимо. Теперь ваш код должен иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="51104-193">If you've followed this tutorial and applied the tags to your code where necessary, your code should now look similar to the following:</span></span>

[!code-csharp[Tagged Library](../../samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]

<span data-ttu-id="51104-194">В коде можно создать подробную документацию к веб-сайту, содержащую интерактивные перекрестные ссылки.</span><span class="sxs-lookup"><span data-stu-id="51104-194">From your code, you can generate a detailed documentation website complete with clickable cross-references.</span></span> <span data-ttu-id="51104-195">При этом вы можете столкнуться с другой проблемой — такой код очень трудно читать.</span><span class="sxs-lookup"><span data-stu-id="51104-195">But you're faced with another problem: your code has become hard to read.</span></span>
<span data-ttu-id="51104-196">Для любого разработчика, который хочет вносить дополнения в этот код, необходимость обработки большого количества данных становится настоящим кошмаром.</span><span class="sxs-lookup"><span data-stu-id="51104-196">There's so much information to sift through that this is going to be a nightmare for any developer who wants to contribute to this code.</span></span>
<span data-ttu-id="51104-197">К счастью, есть XML-тег, который поможет справиться с этой задачей:</span><span class="sxs-lookup"><span data-stu-id="51104-197">Thankfully there's an XML tag that can help you deal with this:</span></span>

## <a name="include"></a><span data-ttu-id="51104-198">\<include></span><span class="sxs-lookup"><span data-stu-id="51104-198">\<include></span></span>

<span data-ttu-id="51104-199">Тег `<include>` позволяет обращаться к комментариям в отдельном XML-файле, описывающем типы и члены в исходном коде, а не размещать комментарии к документации непосредственно в файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="51104-199">The `<include>` tag lets you refer to comments in a separate XML file that describe the types and members in your source code, as opposed to placing documentation comments directly in your source code file.</span></span>

<span data-ttu-id="51104-200">Переместим все XML-теги в отдельный файл XML с именем `docs.xml`.</span><span class="sxs-lookup"><span data-stu-id="51104-200">Now you're going to move all your XML tags into a separate XML file named `docs.xml`.</span></span> <span data-ttu-id="51104-201">Файлу можно задать любое имя.</span><span class="sxs-lookup"><span data-stu-id="51104-201">Feel free to name the file whatever you want.</span></span>

[!code-xml[Sample XML](../../samples/snippets/csharp/concepts/codedoc/include.xml)]

<span data-ttu-id="51104-202">В приведенном выше XML комментарии к документации по каждому члену отображаются непосредственно внутри тега с именем, соответствующим его назначению.</span><span class="sxs-lookup"><span data-stu-id="51104-202">In the above XML, each member's documentation comments appear directly inside a tag named after what they do.</span></span> <span data-ttu-id="51104-203">Можно выбрать собственную стратегию.</span><span class="sxs-lookup"><span data-stu-id="51104-203">You can choose your own strategy.</span></span>
<span data-ttu-id="51104-204">Теперь, когда комментарии XML находятся в отдельном файле, давайте посмотрим, как можно улучшить удобочитаемость кода с помощью тега `<include>`.</span><span class="sxs-lookup"><span data-stu-id="51104-204">Now that you have your XML comments in a separate file, let's see how your code can be made more readable by using the `<include>` tag:</span></span>

[!code-csharp[Include Tag](../../samples/snippets/csharp/concepts/codedoc/include-tag.cs)]

<span data-ttu-id="51104-205">Сейчас чтение кода снова не вызывает сложностей, и никакие сведения не были потеряны.</span><span class="sxs-lookup"><span data-stu-id="51104-205">And there you have it: our code is back to being readable, and no documentation information has been lost.</span></span>

<span data-ttu-id="51104-206">Атрибут `file` представляет имя XML-файла, содержащего документацию.</span><span class="sxs-lookup"><span data-stu-id="51104-206">The `file` attribute represents the name of the XML file containing the documentation.</span></span>

<span data-ttu-id="51104-207">Атрибут `path` представляет запрос [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) к `tag name`, находящемуся в указанном `file`.</span><span class="sxs-lookup"><span data-stu-id="51104-207">The `path` attribute represents an [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) query to the `tag name` present in the specified `file`.</span></span>

<span data-ttu-id="51104-208">Атрибут `name` представляет спецификатор имени в теге, который предшествует комментариям.</span><span class="sxs-lookup"><span data-stu-id="51104-208">The `name` attribute represents the name specifier in the tag that precedes the comments.</span></span>

<span data-ttu-id="51104-209">Атрибут `id`, который может использоваться вместо `name`, представляет идентификатор для тега, предшествующего комментариям.</span><span class="sxs-lookup"><span data-stu-id="51104-209">The `id` attribute which can be used in place of `name` represents the ID for the tag that precedes the comments.</span></span>

### <a name="user-defined-tags"></a><span data-ttu-id="51104-210">Определяемые пользователем теги</span><span class="sxs-lookup"><span data-stu-id="51104-210">User Defined Tags</span></span>

<span data-ttu-id="51104-211">Все описанные выше теги распознаются компилятором C#.</span><span class="sxs-lookup"><span data-stu-id="51104-211">All the tags outlined above represent those that are recognized by the C# compiler.</span></span> <span data-ttu-id="51104-212">Тем не менее пользователь может определять собственные теги.</span><span class="sxs-lookup"><span data-stu-id="51104-212">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="51104-213">Инструменты, такие как Sandcastle, обеспечивают поддержку дополнительных тегов, например [`<event>`](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [`<note>`](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm), и даже поддержку [пространств имен документирования](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span><span class="sxs-lookup"><span data-stu-id="51104-213">Tools like Sandcastle bring support for extra tags like [`<event>`](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [`<note>`](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) and even support [documenting namespaces](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span></span>
<span data-ttu-id="51104-214">Средства создания пользовательской или внутренней документации также можно использовать со стандартными тегами. Кроме того, поддерживается несколько выходных форматов — от HTML до PDF.</span><span class="sxs-lookup"><span data-stu-id="51104-214">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="recommendations"></a><span data-ttu-id="51104-215">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="51104-215">Recommendations</span></span>

<span data-ttu-id="51104-216">Документирование кода рекомендуется по многим причинам.</span><span class="sxs-lookup"><span data-stu-id="51104-216">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="51104-217">Далее приводится ряд рекомендаций, распространенные сценарии использования и вопросы, которые нужно иметь в виду при работе с тегами XML-документации в коде C#.</span><span class="sxs-lookup"><span data-stu-id="51104-217">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your C# code.</span></span>

- <span data-ttu-id="51104-218">Для обеспечения согласованности все открытые типы и их члены должны быть задокументированы.</span><span class="sxs-lookup"><span data-stu-id="51104-218">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="51104-219">Если это необходимо, задокументируйте их все.</span><span class="sxs-lookup"><span data-stu-id="51104-219">If you must do it, do it all.</span></span>
- <span data-ttu-id="51104-220">Закрытые члены можно также задокументировать с помощью XML-комментариев.</span><span class="sxs-lookup"><span data-stu-id="51104-220">Private members can also be documented using XML comments.</span></span> <span data-ttu-id="51104-221">Однако это приводит к раскрытию внутренних (возможно, конфиденциальных) процессов библиотеки.</span><span class="sxs-lookup"><span data-stu-id="51104-221">However, this exposes the inner (potentially confidential) workings of your library.</span></span>
- <span data-ttu-id="51104-222">Как минимум, типы и их члены должен иметь тег `<summary>`, так как его содержимое требуется для IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="51104-222">At a bare minimum, types and their members should have a `<summary>` tag because its content is needed for IntelliSense.</span></span>
- <span data-ttu-id="51104-223">Текст документации должны быть написан с использованием законченных предложений, в конце которых ставится точка.</span><span class="sxs-lookup"><span data-stu-id="51104-223">Documentation text should be written using complete sentences ending with full stops.</span></span>
- <span data-ttu-id="51104-224">Разделяемые классы полностью поддерживаются, и данные о документации объединяются в одну запись для этого типа.</span><span class="sxs-lookup"><span data-stu-id="51104-224">Partial classes are fully supported, and documentation information will be concatenated into a single entry for that type.</span></span>
- <span data-ttu-id="51104-225">Компилятор проверяет синтаксис тегов `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` и `<typeparam>`.</span><span class="sxs-lookup"><span data-stu-id="51104-225">The compiler verifies the syntax of the `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` and `<typeparam>` tags.</span></span>
- <span data-ttu-id="51104-226">Компилятор проверяет параметры, которые содержат пути к файлам и ссылки на другие части кода.</span><span class="sxs-lookup"><span data-stu-id="51104-226">The compiler validates the parameters that contain file paths and references to other parts of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="51104-227">См. также</span><span class="sxs-lookup"><span data-stu-id="51104-227">See also</span></span>

- [<span data-ttu-id="51104-228">Комментарии к XML-документации (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="51104-228">XML Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/index.md)
- [<span data-ttu-id="51104-229">Рекомендуемые теги для комментариев документации (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="51104-229">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
