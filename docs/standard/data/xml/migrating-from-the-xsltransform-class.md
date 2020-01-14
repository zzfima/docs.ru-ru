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
# <a name="migrating-from-the-xsltransform-class"></a>Миграция с класса XslTransform

Архитектура XLST была переработана в выпуске Visual Studio 2005. Класс <xref:System.Xml.Xsl.XslTransform> был заменен классом <xref:System.Xml.Xsl.XslCompiledTransform>.

В следующих разделах описаны некоторые основные различия между классами <xref:System.Xml.Xsl.XslCompiledTransform> и <xref:System.Xml.Xsl.XslTransform>.

## <a name="performance"></a>Производительность

Класс <xref:System.Xml.Xsl.XslCompiledTransform> включает многочисленные улучшения производительности. Новый обработчик XSLT компилирует таблицу стилей XSLT до общего промежуточного формата аналогично среде CLR для других языков программирования. Скомпилированная таблица стилей может быть сохранена в кэше и повторно использована.

В класс <xref:System.Xml.Xsl.XslCompiledTransform> внесены и другие улучшения, благодаря которым его быстродействие выше, чем у класса <xref:System.Xml.Xsl.XslTransform>.

> [!NOTE]
> Хотя класс <xref:System.Xml.Xsl.XslCompiledTransform> имеет более высокий общий уровень производительности, чем класс <xref:System.Xml.Xsl.XslTransform>, метод <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> класса <xref:System.Xml.Xsl.XslCompiledTransform> может выполняться медленнее, чем метод <xref:System.Xml.Xsl.XslTransform.Load%2A> класса <xref:System.Xml.Xsl.XslTransform> при первом вызове преобразования. Причина этого заключается в необходимости компиляции XSLT-файла перед его загрузкой. См. дополнительные сведения о [сравнении XslCompiledTransform и XslTransform](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)

## <a name="security"></a>по безопасности

По умолчанию класс <xref:System.Xml.Xsl.XslCompiledTransform> отключает поддержку функции XSLT `document()` и внедренных скриптов. Эти возможности можно включить, создав объект <xref:System.Xml.Xsl.XsltSettings> с включенными возможностями и передав его в метод <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>. В следующем примере показаны способы включения скриптов и выполнения XSLT-преобразования.

[!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
[!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]

Дополнительные сведения см. в статье [Рекомендации по безопасности XSLT](../../../../docs/standard/data/xml/xslt-security-considerations.md).

## <a name="new-features"></a>Новые функции

### <a name="temporary-files"></a>Временные файлы

Временные файлы иногда формируются при обработке XSLT. Если в таблице стилей содержатся блоки скриптов или если она скомпилирована с параметром отладки, установленным в значение true, в папке %TEMP% могут быть созданы временные файлы. В некоторых случаях часть временных файлов не удаляется из-за рассогласований во времени. Например, если файлы используются текущим доменом приложений или отладчиком, они не могут быть удалены с помощью метода завершения объекта <xref:System.CodeDom.Compiler.TempFileCollection>.

Свойство <xref:System.Xml.Xsl.XslCompiledTransform.TemporaryFiles%2A> может быть использовано для дополнительной очистки, чтобы убедиться, что все временные файлы удалены из клиента.

### <a name="support-for-the-xsloutput-element-and-xmlwriter"></a>Поддержка элемента xsl:output и объекта XmlWriter

Класс <xref:System.Xml.Xsl.XslTransform> не учитывает настройки `xsl:output`, если выходные данные преобразования были переданы в объект <xref:System.Xml.XmlWriter>. Класс <xref:System.Xml.Xsl.XslCompiledTransform> содержит свойство <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A>, которое возвращает объект <xref:System.Xml.XmlWriterSettings>, содержащий выходные сведения, производные от элемента `xsl:output` таблицы стилей. Объект <xref:System.Xml.XmlWriterSettings> используется для создания объекта <xref:System.Xml.XmlWriter> с правильными настройками, которые могут быть переданы методу <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> . Это поведение иллюстрируется следующим кодом C#:

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

### <a name="debug-option"></a>Параметр отладки

Класс <xref:System.Xml.Xsl.XslCompiledTransform> может формировать отладочные данные, что позволяет выполнить отладку таблицы стилей с помощью отладчика среды Microsoft Visual Studio. Дополнительные сведения см. в разделе <xref:System.Xml.Xsl.XslCompiledTransform.%23ctor%28System.Boolean%29>.

## <a name="behavioral-differences"></a>Различия в поведении

### <a name="transforming-to-an-xmlreader"></a>Преобразование в объект XmlReader

Класс <xref:System.Xml.Xsl.XslTransform> содержит несколько перегруженных методов Transform, которые возвращают результаты преобразования как объект <xref:System.Xml.XmlReader>. Эти перегруженные методы можно использовать для загрузки результатов преобразования в представление в памяти (такое как <xref:System.Xml.XmlDocument> или <xref:System.Xml.XPath.XPathDocument>) без дополнительной нагрузки, связанной с сериализацией и десериализацией полученного в результате XML-дерева. Следующий код C# показывает, как загрузить результаты преобразования в объект <xref:System.Xml.XmlDocument>.

```csharp
// Load the style sheet
XslTransform xslt = new XslTransform();
xslt.Load("MyStylesheet.xsl");

// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
doc.Load(xslt.Transform(input, (XsltArgumentList)null));
```

Класс <xref:System.Xml.Xsl.XslCompiledTransform> не поддерживает преобразование в объект <xref:System.Xml.XmlReader>. Однако можно выполнить аналогичное действие с помощью метода <xref:System.Xml.XPath.XPathNavigator.CreateNavigator%2A> для загрузки результирующего XML-дерева непосредственно из объекта <xref:System.Xml.XmlWriter>. Следующий код C# показывает, как выполнить ту же задачу с помощью класса <xref:System.Xml.Xsl.XslCompiledTransform>.

```csharp
// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
using (XmlWriter writer = doc.CreateNavigator().AppendChild()) {
    xslt.Transform(input, (XsltArgumentList)null, writer);
}
```

### <a name="discretionary-behavior"></a>Поведение, реализуемое по усмотрению разработчика

Рекомендация W3C по XSL-преобразованиям (XSLT) версии 1.0 включает в себя такие области, в которых поставщик реализации может решать, как обрабатывать ситуацию. Эти области считаются предоставленными на усмотрение поставщика. Существует несколько областей, в которых поведение класса <xref:System.Xml.Xsl.XslCompiledTransform> отличается от класса <xref:System.Xml.Xsl.XslTransform>. Дополнительные сведения см. в статье [Устранимые ошибки XSLT](../../../../docs/standard/data/xml/recoverable-xslt-errors.md).

### <a name="extension-objects-and-script-functions"></a>Объекты расширения и функции скриптов

Класс <xref:System.Xml.Xsl.XslCompiledTransform> вводит два новых ограничения на использование функций скриптов.

- Только общие методы могут быть вызваны из выражений XPath.

- Перегруженные методы неотличимы друг от друга по количеству аргументов. Если более одного перегруженного метода имеет одинаковое количество аргументов, возникает исключение.

В классе <xref:System.Xml.Xsl.XslCompiledTransform> привязка (поиск имени метода) к функциям скриптов выполняется во время компиляции, и таблицы стилей, работающие с объектом XslTransform, могут вызвать исключение при загрузке с классом <xref:System.Xml.Xsl.XslCompiledTransform>.

Класс <xref:System.Xml.Xsl.XslCompiledTransform> поддерживает дочерние элементы `msxsl:using` и `msxsl:assembly` внутри элемента `msxsl:script`. Чтобы декларировать дополнительные пространства имен и сборок для использования в блоке скриптов, используются элементы `msxsl:using` и `msxsl:assembly`. В статье [Блоки скриптов с использованием msxsl:script](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md) вы найдете дополнительную информацию об этом.

Класс <xref:System.Xml.Xsl.XslCompiledTransform> запрещает объекты расширения, которые имеют несколько перегруженных методов с одинаковым количеством аргументов.

### <a name="msxml-functions"></a>Функции MSXML

Класс <xref:System.Xml.Xsl.XslCompiledTransform> дополнен функциями MSXML. Новые и улучшенные функции описываются в следующем списке.

- msxsl:node-set: класс <xref:System.Xml.Xsl.XslTransform> требует, чтобы аргумент [функции node-set](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256197(v=vs.100)) являлся фрагментом результирующего дерева. Такое требование отсутствует у класса <xref:System.Xml.Xsl.XslCompiledTransform>.

- msxsl:version: эта функция поддерживается в классе <xref:System.Xml.Xsl.XslCompiledTransform>.

- Функции расширения XPath: теперь поддерживаются функции [ms:string-compare](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256114(v=vs.100)), [ms:utc](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256474(v=vs.100)), [ms:namespace-uri](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256231(v=vs.100)), [ms:local-name](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256055(v=vs.100)), [ms:number](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256155(v=vs.100)), [ms:format-date](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256099(v=vs.100)) и [ms:format-time](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256467(v=vs.100)).

- Функции расширения XPath, связанные со схемой: <xref:System.Xml.Xsl.XslCompiledTransform> не обеспечивает встроенную поддержку этих функций. Однако их можно реализовать как функции расширения.

## <a name="see-also"></a>См. также:

- [Преобразования XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
- [Использование класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
