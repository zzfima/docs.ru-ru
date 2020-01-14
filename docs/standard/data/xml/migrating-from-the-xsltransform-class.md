---
title: Миграция с класса XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 9404d758-679f-4ffb-995d-3d07d817659e
ms.openlocfilehash: 8383d8cb3e5819c46a0716c59323e492bb9add8e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937994"
---
# <a name="migrating-from-the-xsltransform-class"></a><span data-ttu-id="c8f70-102">Миграция с класса XslTransform</span><span class="sxs-lookup"><span data-stu-id="c8f70-102">Migrating From the XslTransform Class</span></span>

<span data-ttu-id="c8f70-103">Архитектура XLST была переработана в выпуске Visual Studio 2005.</span><span class="sxs-lookup"><span data-stu-id="c8f70-103">The XSLT architecture was redesigned in the Visual Studio 2005 release.</span></span> <span data-ttu-id="c8f70-104">Класс <xref:System.Xml.Xsl.XslTransform> был заменен классом <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-104">The <xref:System.Xml.Xsl.XslTransform> class was replaced by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>

<span data-ttu-id="c8f70-105">В следующих разделах описаны некоторые основные различия между классами <xref:System.Xml.Xsl.XslCompiledTransform> и <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-105">The following sections describe some of the main differences between the <xref:System.Xml.Xsl.XslCompiledTransform> and the <xref:System.Xml.Xsl.XslTransform> classes.</span></span>

## <a name="performance"></a><span data-ttu-id="c8f70-106">Производительность</span><span class="sxs-lookup"><span data-stu-id="c8f70-106">Performance</span></span>

<span data-ttu-id="c8f70-107">Класс <xref:System.Xml.Xsl.XslCompiledTransform> включает многочисленные улучшения производительности.</span><span class="sxs-lookup"><span data-stu-id="c8f70-107">The <xref:System.Xml.Xsl.XslCompiledTransform> class includes many performance improvements.</span></span> <span data-ttu-id="c8f70-108">Новый обработчик XSLT компилирует таблицу стилей XSLT до общего промежуточного формата аналогично среде CLR для других языков программирования.</span><span class="sxs-lookup"><span data-stu-id="c8f70-108">The new XSLT processor compiles the XSLT style sheet down to a common intermediate format, similar to what the common language runtime (CLR) does for other programming languages.</span></span> <span data-ttu-id="c8f70-109">Скомпилированная таблица стилей может быть сохранена в кэше и повторно использована.</span><span class="sxs-lookup"><span data-stu-id="c8f70-109">Once the style sheet is compiled, it can be cached and reused.</span></span>

<span data-ttu-id="c8f70-110">В класс <xref:System.Xml.Xsl.XslCompiledTransform> внесены и другие улучшения, благодаря которым его быстродействие выше, чем у класса <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-110">The <xref:System.Xml.Xsl.XslCompiledTransform> class also includes other optimizations that make it much faster than the <xref:System.Xml.Xsl.XslTransform> class.</span></span>

> [!NOTE]
> <span data-ttu-id="c8f70-111">Хотя класс <xref:System.Xml.Xsl.XslCompiledTransform> имеет более высокий общий уровень производительности, чем класс <xref:System.Xml.Xsl.XslTransform>, метод <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> класса <xref:System.Xml.Xsl.XslCompiledTransform> может выполняться медленнее, чем метод <xref:System.Xml.Xsl.XslTransform.Load%2A> класса <xref:System.Xml.Xsl.XslTransform> при первом вызове преобразования.</span><span class="sxs-lookup"><span data-stu-id="c8f70-111">Although the overall performance of the <xref:System.Xml.Xsl.XslCompiledTransform> class is better than the <xref:System.Xml.Xsl.XslTransform> class, the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslCompiledTransform> class might perform more slowly than the <xref:System.Xml.Xsl.XslTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslTransform> class the first time it is called on a transformation.</span></span> <span data-ttu-id="c8f70-112">Причина этого заключается в необходимости компиляции XSLT-файла перед его загрузкой.</span><span class="sxs-lookup"><span data-stu-id="c8f70-112">This is because the XSLT file must be compiled before it is loaded.</span></span> <span data-ttu-id="c8f70-113">См. дополнительные сведения о [сравнении XslCompiledTransform и XslTransform](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span><span class="sxs-lookup"><span data-stu-id="c8f70-113">For more information, see the following blog post: [XslCompiledTransform Slower than XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span></span>

## <a name="security"></a><span data-ttu-id="c8f70-114">по безопасности</span><span class="sxs-lookup"><span data-stu-id="c8f70-114">Security</span></span>

<span data-ttu-id="c8f70-115">По умолчанию класс <xref:System.Xml.Xsl.XslCompiledTransform> отключает поддержку функции XSLT `document()` и внедренных скриптов.</span><span class="sxs-lookup"><span data-stu-id="c8f70-115">By default, the <xref:System.Xml.Xsl.XslCompiledTransform> class disables support for the XSLT `document()` function and embedded scripting.</span></span> <span data-ttu-id="c8f70-116">Эти возможности можно включить, создав объект <xref:System.Xml.Xsl.XsltSettings> с включенными возможностями и передав его в метод <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-116">These features can be enabled by creating an <xref:System.Xml.Xsl.XsltSettings> object that has the features enabled and passing it to the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span> <span data-ttu-id="c8f70-117">В следующем примере показаны способы включения скриптов и выполнения XSLT-преобразования.</span><span class="sxs-lookup"><span data-stu-id="c8f70-117">The following example shows how to enable scripting and perform an XSLT transformation.</span></span>

[!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
[!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]

<span data-ttu-id="c8f70-118">Дополнительные сведения см. в статье [Рекомендации по безопасности XSLT](../../../../docs/standard/data/xml/xslt-security-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="c8f70-118">For more information, see [XSLT Security Considerations](../../../../docs/standard/data/xml/xslt-security-considerations.md).</span></span>

## <a name="new-features"></a><span data-ttu-id="c8f70-119">Новые функции</span><span class="sxs-lookup"><span data-stu-id="c8f70-119">New Features</span></span>

### <a name="temporary-files"></a><span data-ttu-id="c8f70-120">Временные файлы</span><span class="sxs-lookup"><span data-stu-id="c8f70-120">Temporary Files</span></span>

<span data-ttu-id="c8f70-121">Временные файлы иногда формируются при обработке XSLT.</span><span class="sxs-lookup"><span data-stu-id="c8f70-121">Temporary files are sometimes generated during XSLT processing.</span></span> <span data-ttu-id="c8f70-122">Если в таблице стилей содержатся блоки скриптов или если она скомпилирована с параметром отладки, установленным в значение true, в папке %TEMP% могут быть созданы временные файлы.</span><span class="sxs-lookup"><span data-stu-id="c8f70-122">If a style sheet contains script blocks, or if it is compiled with the debug setting set to true, temporary files may be created in the %TEMP% folder.</span></span> <span data-ttu-id="c8f70-123">В некоторых случаях часть временных файлов не удаляется из-за рассогласований во времени.</span><span class="sxs-lookup"><span data-stu-id="c8f70-123">There may be instances when some temporary files are not deleted due to timing issues.</span></span> <span data-ttu-id="c8f70-124">Например, если файлы используются текущим доменом приложений или отладчиком, они не могут быть удалены с помощью метода завершения объекта <xref:System.CodeDom.Compiler.TempFileCollection>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-124">For example, if the files are in use by the current AppDomain or by the debugger, the finalizer of the <xref:System.CodeDom.Compiler.TempFileCollection> object will not be able to remove them.</span></span>

<span data-ttu-id="c8f70-125">Свойство <xref:System.Xml.Xsl.XslCompiledTransform.TemporaryFiles%2A> может быть использовано для дополнительной очистки, чтобы убедиться, что все временные файлы удалены из клиента.</span><span class="sxs-lookup"><span data-stu-id="c8f70-125">The <xref:System.Xml.Xsl.XslCompiledTransform.TemporaryFiles%2A> property can be used for additional cleanup to make sure that all temporary files are removed from the client.</span></span>

### <a name="support-for-the-xsloutput-element-and-xmlwriter"></a><span data-ttu-id="c8f70-126">Поддержка элемента xsl:output и объекта XmlWriter</span><span class="sxs-lookup"><span data-stu-id="c8f70-126">Support for the xsl:output Element and XmlWriter</span></span>

<span data-ttu-id="c8f70-127">Класс <xref:System.Xml.Xsl.XslTransform> не учитывает настройки `xsl:output`, если выходные данные преобразования были переданы в объект <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-127">The <xref:System.Xml.Xsl.XslTransform> class ignored `xsl:output` settings when the transform output was sent to an <xref:System.Xml.XmlWriter> object.</span></span> <span data-ttu-id="c8f70-128">Класс <xref:System.Xml.Xsl.XslCompiledTransform> содержит свойство <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A>, которое возвращает объект <xref:System.Xml.XmlWriterSettings>, содержащий выходные сведения, производные от элемента `xsl:output` таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="c8f70-128">The <xref:System.Xml.Xsl.XslCompiledTransform> class has an <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A> property that returns an <xref:System.Xml.XmlWriterSettings> object containing the output information derived from the `xsl:output` element of the style sheet.</span></span> <span data-ttu-id="c8f70-129">Объект <xref:System.Xml.XmlWriterSettings> используется для создания объекта <xref:System.Xml.XmlWriter> с правильными настройками, которые могут быть переданы методу <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> .</span><span class="sxs-lookup"><span data-stu-id="c8f70-129">The <xref:System.Xml.XmlWriterSettings> object is used to create an <xref:System.Xml.XmlWriter> object with the correct settings that can be passed to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span> <span data-ttu-id="c8f70-130">Это поведение иллюстрируется следующим кодом C#:</span><span class="sxs-lookup"><span data-stu-id="c8f70-130">The following C# code illustrates this behavior:</span></span>

```csharp
// Create the XslTransform object and load the style sheet.
XslCompiledTransform xslt = new XslCompiledTransform();
xslt.Load(stylesheet);

// Load the file to transform.
XPathDocument doc = new XPathDocument(filename);

// Create the writer.
XmlWriter writer = XmlWriter.Create(Console.Out, xslt.OutputSettings);

// Transform the file and send the output to the console.
xslt.Transform(doc, writer);
writer.Close();
```

### <a name="debug-option"></a><span data-ttu-id="c8f70-131">Параметр отладки</span><span class="sxs-lookup"><span data-stu-id="c8f70-131">Debug Option</span></span>

<span data-ttu-id="c8f70-132">Класс <xref:System.Xml.Xsl.XslCompiledTransform> может формировать отладочные данные, что позволяет выполнить отладку таблицы стилей с помощью отладчика среды Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c8f70-132">The <xref:System.Xml.Xsl.XslCompiledTransform> class can generate debug information, which enables you to debug the style sheet with the Microsoft Visual Studio Debugger.</span></span> <span data-ttu-id="c8f70-133">Дополнительные сведения см. в разделе <xref:System.Xml.Xsl.XslCompiledTransform.%23ctor%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-133">See <xref:System.Xml.Xsl.XslCompiledTransform.%23ctor%28System.Boolean%29> for more information.</span></span>

## <a name="behavioral-differences"></a><span data-ttu-id="c8f70-134">Различия в поведении</span><span class="sxs-lookup"><span data-stu-id="c8f70-134">Behavioral Differences</span></span>

### <a name="transforming-to-an-xmlreader"></a><span data-ttu-id="c8f70-135">Преобразование в объект XmlReader</span><span class="sxs-lookup"><span data-stu-id="c8f70-135">Transforming to an XmlReader</span></span>

<span data-ttu-id="c8f70-136">Класс <xref:System.Xml.Xsl.XslTransform> содержит несколько перегруженных методов Transform, которые возвращают результаты преобразования как объект <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-136">The <xref:System.Xml.Xsl.XslTransform> class has several Transform overloads that return transformation results as an <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="c8f70-137">Эти перегруженные методы можно использовать для загрузки результатов преобразования в представление в памяти (такое как <xref:System.Xml.XmlDocument> или <xref:System.Xml.XPath.XPathDocument>) без дополнительной нагрузки, связанной с сериализацией и десериализацией полученного в результате XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="c8f70-137">These overloads can be used to load the transformation results into an in-memory representation (such as <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument>) without incurring the overhead of serialization and deserialization of the resulting XML tree.</span></span> <span data-ttu-id="c8f70-138">Следующий код C# показывает, как загрузить результаты преобразования в объект <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-138">The following C# code shows how to load the transformation results into an <xref:System.Xml.XmlDocument> object.</span></span>

```csharp
// Load the style sheet
XslTransform xslt = new XslTransform();
xslt.Load("MyStylesheet.xsl");

// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
doc.Load(xslt.Transform(input, (XsltArgumentList)null));
```

<span data-ttu-id="c8f70-139">Класс <xref:System.Xml.Xsl.XslCompiledTransform> не поддерживает преобразование в объект <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-139">The <xref:System.Xml.Xsl.XslCompiledTransform> class does not support transforming to an <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="c8f70-140">Однако можно выполнить аналогичное действие с помощью метода <xref:System.Xml.XPath.XPathNavigator.CreateNavigator%2A> для загрузки результирующего XML-дерева непосредственно из объекта <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-140">However, you can do something similar by using the <xref:System.Xml.XPath.XPathNavigator.CreateNavigator%2A> method to load the resulting XML tree directly from an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="c8f70-141">Следующий код C# показывает, как выполнить ту же задачу с помощью класса <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-141">The following C# code shows how to accomplish the same task using <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>

```csharp
// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
using (XmlWriter writer = doc.CreateNavigator().AppendChild()) {
    xslt.Transform(input, (XsltArgumentList)null, writer);
}
```

### <a name="discretionary-behavior"></a><span data-ttu-id="c8f70-142">Поведение, реализуемое по усмотрению разработчика</span><span class="sxs-lookup"><span data-stu-id="c8f70-142">Discretionary Behavior</span></span>

<span data-ttu-id="c8f70-143">Рекомендация W3C по XSL-преобразованиям (XSLT) версии 1.0 включает в себя такие области, в которых поставщик реализации может решать, как обрабатывать ситуацию.</span><span class="sxs-lookup"><span data-stu-id="c8f70-143">The W3C XSL Transformations (XSLT) Version 1.0 Recommendation includes areas in which the implementation provider may decide how to handle a situation.</span></span> <span data-ttu-id="c8f70-144">Эти области считаются предоставленными на усмотрение поставщика.</span><span class="sxs-lookup"><span data-stu-id="c8f70-144">These areas are considered to be discretionary behavior.</span></span> <span data-ttu-id="c8f70-145">Существует несколько областей, в которых поведение класса <xref:System.Xml.Xsl.XslCompiledTransform> отличается от класса <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-145">There are several areas where the <xref:System.Xml.Xsl.XslCompiledTransform> behaves differently than the <xref:System.Xml.Xsl.XslTransform> class.</span></span> <span data-ttu-id="c8f70-146">Дополнительные сведения см. в статье [Устранимые ошибки XSLT](../../../../docs/standard/data/xml/recoverable-xslt-errors.md).</span><span class="sxs-lookup"><span data-stu-id="c8f70-146">For more information, see [Recoverable XSLT Errors](../../../../docs/standard/data/xml/recoverable-xslt-errors.md).</span></span>

### <a name="extension-objects-and-script-functions"></a><span data-ttu-id="c8f70-147">Объекты расширения и функции скриптов</span><span class="sxs-lookup"><span data-stu-id="c8f70-147">Extension Objects and Script Functions</span></span>

<span data-ttu-id="c8f70-148">Класс <xref:System.Xml.Xsl.XslCompiledTransform> вводит два новых ограничения на использование функций скриптов.</span><span class="sxs-lookup"><span data-stu-id="c8f70-148"><xref:System.Xml.Xsl.XslCompiledTransform> introduces two new restrictions on the use of script functions:</span></span>

- <span data-ttu-id="c8f70-149">Только общие методы могут быть вызваны из выражений XPath.</span><span class="sxs-lookup"><span data-stu-id="c8f70-149">Only public methods may be called from XPath expressions.</span></span>

- <span data-ttu-id="c8f70-150">Перегруженные методы неотличимы друг от друга по количеству аргументов.</span><span class="sxs-lookup"><span data-stu-id="c8f70-150">Overloads are distinguishable from each other based on the number of arguments.</span></span> <span data-ttu-id="c8f70-151">Если более одного перегруженного метода имеет одинаковое количество аргументов, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="c8f70-151">If more than one overload has the same number of arguments, an exception will be raised.</span></span>

<span data-ttu-id="c8f70-152">В классе <xref:System.Xml.Xsl.XslCompiledTransform> привязка (поиск имени метода) к функциям скриптов выполняется во время компиляции, и таблицы стилей, работающие с объектом XslTransform, могут вызвать исключение при загрузке с классом <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-152">In <xref:System.Xml.Xsl.XslCompiledTransform>, a binding (method name lookup) to script functions occurs at compile time, and style sheets that worked with XslTransform may cause an exception when they are loaded with <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>

<span data-ttu-id="c8f70-153">Класс <xref:System.Xml.Xsl.XslCompiledTransform> поддерживает дочерние элементы `msxsl:using` и `msxsl:assembly` внутри элемента `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="c8f70-153"><xref:System.Xml.Xsl.XslCompiledTransform> supports having `msxsl:using` and `msxsl:assembly` child elements within the `msxsl:script` element.</span></span> <span data-ttu-id="c8f70-154">Чтобы декларировать дополнительные пространства имен и сборок для использования в блоке скриптов, используются элементы `msxsl:using` и `msxsl:assembly`.</span><span class="sxs-lookup"><span data-stu-id="c8f70-154">The `msxsl:using` and `msxsl:assembly` elements are used to declare additional namespaces and assemblies for use in the script block.</span></span> <span data-ttu-id="c8f70-155">В статье [Блоки скриптов с использованием msxsl:script](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md) вы найдете дополнительную информацию об этом.</span><span class="sxs-lookup"><span data-stu-id="c8f70-155">See [Script Blocks Using msxsl:script](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md) for more information.</span></span>

<span data-ttu-id="c8f70-156">Класс <xref:System.Xml.Xsl.XslCompiledTransform> запрещает объекты расширения, которые имеют несколько перегруженных методов с одинаковым количеством аргументов.</span><span class="sxs-lookup"><span data-stu-id="c8f70-156"><xref:System.Xml.Xsl.XslCompiledTransform> prohibits extension objects that have multiple overloads with the same number of arguments.</span></span>

### <a name="msxml-functions"></a><span data-ttu-id="c8f70-157">Функции MSXML</span><span class="sxs-lookup"><span data-stu-id="c8f70-157">MSXML Functions</span></span>

<span data-ttu-id="c8f70-158">Класс <xref:System.Xml.Xsl.XslCompiledTransform> дополнен функциями MSXML.</span><span class="sxs-lookup"><span data-stu-id="c8f70-158">Support for additional MSXML functions have been added to the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="c8f70-159">Новые и улучшенные функции описываются в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="c8f70-159">The following list describes new or improved functionality:</span></span>

- <span data-ttu-id="c8f70-160">msxsl:node-set: класс <xref:System.Xml.Xsl.XslTransform> требует, чтобы аргумент [функции node-set](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256197(v=vs.100)) являлся фрагментом результирующего дерева.</span><span class="sxs-lookup"><span data-stu-id="c8f70-160">msxsl:node-set: <xref:System.Xml.Xsl.XslTransform> required the argument of the [node-set Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256197(v=vs.100)) function to be a result tree fragment.</span></span> <span data-ttu-id="c8f70-161">Такое требование отсутствует у класса <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-161">The <xref:System.Xml.Xsl.XslCompiledTransform> class does not have this requirement.</span></span>

- <span data-ttu-id="c8f70-162">msxsl:version: эта функция поддерживается в классе <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="c8f70-162">msxsl:version: This function is supported in <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>

- <span data-ttu-id="c8f70-163">Функции расширения XPath: теперь поддерживаются функции [ms:string-compare](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256114(v=vs.100)), [ms:utc](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256474(v=vs.100)), [ms:namespace-uri](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256231(v=vs.100)), [ms:local-name](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256055(v=vs.100)), [ms:number](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256155(v=vs.100)), [ms:format-date](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256099(v=vs.100)) и [ms:format-time](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256467(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c8f70-163">XPath extension functions: The [ms:string-compare Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256114(v=vs.100)), [ms:utc Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256474(v=vs.100)), [ms:namespace-uri Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256231(v=vs.100)), [ms:local-name Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256055(v=vs.100)), [ms:number Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256155(v=vs.100)), [ms:format-date Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256099(v=vs.100)), and [ms:format-time Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256467(v=vs.100)) functions are now supported.</span></span>

- <span data-ttu-id="c8f70-164">Функции расширения XPath, связанные со схемой: <xref:System.Xml.Xsl.XslCompiledTransform> не обеспечивает встроенную поддержку этих функций.</span><span class="sxs-lookup"><span data-stu-id="c8f70-164">Schema-related XPath extension functions: These functions are not supported natively by <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span> <span data-ttu-id="c8f70-165">Однако их можно реализовать как функции расширения.</span><span class="sxs-lookup"><span data-stu-id="c8f70-165">However, they can be implemented as extension functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8f70-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="c8f70-166">See also</span></span>

- [<span data-ttu-id="c8f70-167">Преобразования XSLT</span><span class="sxs-lookup"><span data-stu-id="c8f70-167">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
- [<span data-ttu-id="c8f70-168">Использование класса XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="c8f70-168">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
