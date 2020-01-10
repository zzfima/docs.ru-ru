---
title: Реализация классом XslTransform XSLT-процессора
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 88373fe2-4a6b-44f9-8a62-8a3e348e3a46
ms.openlocfilehash: 73a432db9a3fcb6587184e27e6dfe9ba49010e92
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709612"
---
# <a name="xsltransform-class-implements-the-xslt-processor"></a>Реализация классом XslTransform XSLT-процессора

> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).

Класс <xref:System.Xml.Xsl.XslTransform> является XSLT-процессором, реализующим рекомендации по XSL-преобразованиям (XSLT) версии 1.0. Метод <xref:System.Xml.Xsl.XslTransform.Load%2A> находит и считывает таблицы стилей, а метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> преобразует исходный документ. В качестве исходного документа для метода <xref:System.Xml.XPath.IXPathNavigable> может служить любое хранилище, реализующее интерфейс <xref:System.Xml.Xsl.XslTransform>. Платформа .NET Framework в настоящее время реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable> в классах <xref:System.Xml.XmlDocument><xref:System.Xml.XmlDataDocument> и <xref:System.Xml.XPath.XPathDocument>, поэтому все они могут использоваться в качестве источника документов для преобразования.

Объект <xref:System.Xml.Xsl.XslTransform> в платформе .NET Framework поддерживает только спецификацию XSLT 1.0, определенную со следующим пространством имен:

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
```

Загрузить таблицу стилей можно, вызвав метод <xref:System.Xml.Xsl.XslTransform.Load%2A> из одного из следующих классов:

- XPathNavigator

- XmlReader

- Строка, представляющая URL-адрес

Существует другой метод <xref:System.Xml.Xsl.XslTransform.Load%2A> для каждого из приведенных выше входных классов. Некоторые методы принимают в качестве аргументов сочетание одного из этих классов и класса <xref:System.Xml.XmlResolver>. Класс <xref:System.Xml.XmlResolver> находит ресурсы, на которые ссылаются элементы `<xsl:import>` или `<xsl:include>` в таблице стилей. Следующие методы в качестве входного значения принимают строку: <xref:System.Xml.XmlReader> и <xref:System.Xml.XPath.XPathNavigator>.

```vb
Overloads Public Sub Load(String)
```

```csharp
public void Load(string);
```

```vb
Overloads Public Sub Load(String, XmlResolver)
```

```csharp
public void Load(string, XmlResolver);
```

```vb
Overloads Public Sub Load(XmlReader, XmlResolver, Evidence)
```

```csharp
public void Load(XmlReader, XmlResolver, Evidence);
```

```vb
Overloads Public Sub Load(XPathNavigator, XmlResolver, Evidence)
```

```csharp
public void Load(XPathNavigator, XmlResolver, Evidence);
```

Большая часть приведенных выше методов <xref:System.Xml.Xsl.XslTransform.Load%2A> принимает в качестве параметра объект <xref:System.Xml.XmlResolver>. Объект <xref:System.Xml.XmlResolver> используется для загрузки таблицы стилей и всех таблиц стилей, на которые имеются ссылки в элементах xsl:import и xsl:include.

Большинство методов <xref:System.Xml.Xsl.XslTransform.Load%2A> также принимает свидетельство в качестве параметра. Параметр-свидетельство является объектом <xref:System.Security.Policy.Evidence>, связанным с таблицей стилей. Уровень безопасности таблицы стилей влияет на уровень безопасности всех последующих ресурсов, на которые она ссылается, например содержащийся в ней скрипт, все вызываемые функции `document()` и все объекты расширения, используемые объектом <xref:System.Xml.Xsl.XsltArgumentList>.

Если таблица стилей загружается с помощью метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, содержащего параметр URL-адреса и не содержащего свидетельства, свидетельство таблицы стилей вычисляется путем объединения этого URL-адреса с его веб-узлом и зоной.

Если URI или свидетельство отсутствуют, то свидетельство таблицы стилей считается полностью доверенным. Не загружайте таблицы стилей из ненадежных источников и не добавляйте ненадежные объекты расширения в объект <xref:System.Xml.Xsl.XsltArgumentList>.

Дополнительные сведения об уровнях безопасности и свидетельстве, а также об их влиянии на работу со скриптами, вы найдете в статье [о скриптах для таблиц стилей XSLT с использованием \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md). Сведения об уровнях безопасности и свидетельстве, а также об их влиянии на объекты расширения см. в статье [XsltArgumentList для параметров таблицы стилей и объектов расширения](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md).

Сведения об уровнях безопасности и свидетельстве, а также об их влиянии на функцию `document()` см. в статье [Разрешение внешних таблиц стилей XSLT и документов](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md).

Таблицу стилей можно предоставить с рядом входных параметров. Таблица стилей может также вызывать функции в объектах расширения. Как параметры, так и объекты расширения предоставляются таблице стилей с помощью объекта <xref:System.Xml.Xsl.XsltArgumentList>. Дополнительные сведения о <xref:System.Xml.Xsl.XsltArgumentList> см. в разделе <xref:System.Xml.Xsl.XsltArgumentList>.

## <a name="recommended-secure-use-of-xsltransform-class"></a>Рекомендованное безопасное использование класса XslTransform

Права доступа таблицы стилей зависят от предоставленного свидетельства. В следующей таблице представлено расположение таблицы стилей и объясняется соответствующий тип свидетельства.

- Таблица стилей XSLT не имеет внешних ссылок или поступает из доверенного кода.

  - Предоставьте свидетельство из собственной сборки:

    ```vb
    Dim xslt = New XslTransform() xslt.Load(stylesheet, resolver, Me.GetType().Assembly.Evidence)

    XsltTransform xslt = new XslTransform();  xslt.Load(stylesheet, resolver, this.GetType().Assembly.Evidence);
    ```

- Таблица стилей XSLT поступает из внешнего источника. Происхождение источника известно, существует поддающийся проверке URI.

  - Создайте свидетельство с помощью этого URI.

    ```vb
    Dim xslt As New XslTransform() Dim ev As Evidence = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri) xslt.Load(stylesheet, resolver, evidence)

    XslTransform xslt = new XslTransform(); Evidence ev = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri); xslt.Load(stylesheet, resolver, evidence);
    ```

- Таблица стилей XSLT поступает из внешнего источника. Происхождение источника неизвестно.

  - Присвойте свидетельству значение `null`. Блоки скриптов не обрабатываются, функция XSLT `document()` не поддерживается, привилегированные объекты расширения запрещены.

    Кроме того, можно также присвоить параметру `resolver` значение `null`. Это гарантирует, что элементы `xsl:import` и `xsl:include` не будут обрабатываться.

- Таблица стилей XSLT поступает из внешнего источника. Происхождение источника неизвестно, но необходима поддержка скриптов.

  - Запросите свидетельство у вызывающего.

## <a name="transformation-of-xml-data"></a>Преобразование XML-данных

После загрузки таблицы стилей преобразование начинается с вызова методов <xref:System.Xml.Xsl.XslTransform.Transform%2A> и предоставления исходного документа источника. Метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> перегружен, чтобы обеспечить разные выходные данные преобразования. Преобразование может завершиться следующими выходными форматами:

- <xref:System.Xml.XmlReader>

- <xref:System.Xml.XmlWriter>

- <xref:System.IO.TextWriter>

- <xref:System.IO.Stream>

- Строковый URL-адрес файла

Последний формат, строковый URL-адрес файла, является наиболее распространенной ситуацией при преобразовании исходного документа, находящегося по определенному URL-адресу, и записи этого документа в выходной URL-адрес. Метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> является самым удобным для загрузки XML-документа из файла, выполнения XSLT-преобразования и записи выходных данных в файл. При этом не нужно создавать и загружать исходный документ с последующей записью в файловый поток. В следующем образце кода показано применение метода <xref:System.Xml.Xsl.XslTransform.Transform%2A> при использовании строкового URL-адреса в качестве входных и выходных данных:

```vb
Dim xsltransform As XslTransform = New XslTransform()
xsltransform.Load("favorite.xsl")
xsltransform.Transform("MyDocument.Xml", "TransformResult.xml", Nothing)
```

```csharp
XslTransform xsltransform = new XslTransform();
xsltransform.Load("favorite.xsl");
xsltransform.Transform("MyDocument.xml", "TransformResult.xml", null);
```

## <a name="transforming-a-section-of-an-xml-document"></a>Преобразование раздела XML-документа

Преобразования применяются к документу в целом. Иными словами, если передать узел, отличный от корневого узла документа, это не помешает процессу преобразования обратиться ко всем узлам загружаемого документа. Чтобы преобразовать фрагмент результирующего дерева, необходимо создать объект <xref:System.Xml.XmlDocument>, содержащий только фрагмент результирующего дерева, и передать этот объект <xref:System.Xml.XmlDocument> методу <xref:System.Xml.Xsl.XslTransform.Transform%2A>. В следующем примере выполняется преобразование фрагмента результирующего дерева.

```vb
Dim xslt As New XslTransform()
xslt.Load("print_root.xsl")
Dim doc As New XmlDocument()
doc.Load("library.xml")
' Create a new document containing just the result tree fragment.
Dim testNode As XmlNode = doc.DocumentElement.FirstChild
Dim tmpDoc As New XmlDocument()
tmpDoc.LoadXml(testNode.OuterXml)
' Pass the document containing the result tree fragment
' to the Transform method.
Console.WriteLine(("Passing " + tmpDoc.OuterXml + " to print_root.xsl"))
xslt.Transform(tmpDoc, Nothing, Console.Out, Nothing)
```

```csharp
XslTransform xslt = new XslTransform();
xslt.Load("print_root.xsl");
XmlDocument doc = new XmlDocument();
doc.Load("library.xml");
// Create a new document containing just the result tree fragment.
XmlNode testNode = doc.DocumentElement.FirstChild;
XmlDocument tmpDoc = new XmlDocument();
tmpDoc.LoadXml(testNode.OuterXml);
// Pass the document containing the result tree fragment
// to the Transform method.
Console.WriteLine("Passing " + tmpDoc.OuterXml + " to print_root.xsl");
xslt.Transform(tmpDoc, null, Console.Out, null);
```

В этом примере в качестве входных данных используются файлы Library. XML и print_root. xsl. в консоль выводится следующее:

```console
Passing <book genre="novel" ISBN="1-861001-57-5"><title>Pride And Prejudice</title></book> to print_root.xsl
Root node is book.
```

library.xml

```xml
<library>
  <book genre='novel' ISBN='1-861001-57-5'>
     <title>Pride And Prejudice</title>
  </book>
  <book genre='novel' ISBN='1-81920-21-2'>
     <title>Hook</title>
  </book>
</library>
```

print_root.xsl

```xml
<stylesheet version="1.0" xmlns="http://www.w3.org/1999/XSL/Transform" >
  <output method="text" />
  <template match="/">
     Root node is  <value-of select="local-name(//*[position() = 1])" />
  </template>
</stylesheet>
```

## <a name="migration-of-xslt-from-net-framework-version-10-to-net-framework-version-11"></a>Миграция XSLT с платформы .NET Framework версии 1.0 на платформу .NET Framework версии 1.1

В следующей таблице показаны устаревшие методы платформы .NET Framework версии 1.0 и новые методы платформы .NET Framework версии 1.1 для метода <xref:System.Xml.Xsl.XslTransform.Load%2A>. Новые методы позволяют ограничить разрешения таблицы стилей, указывая свидетельство.

|Устаревшие методы Load платформы .NET Framework версии 1.0|Заменяющие их методы Load платформы .NET Framework версии 1.1|
|------------------------------------------------------|---------------------------------------------------------|
|Load(XPathNavigator input);<br /><br /> Load(XPathNavigator input, XmlResolver resolver);|Load(XPathNavigator stylesheet, XmlResolver resolver, Evidence evidence);|
|Load(IXPathNavigable stylesheet);<br /><br /> Load(IXPathNavigable stylesheet, XmlResolver resolver);|Load(IXPathNavigable stylesheet, XmlResolver resolver, Evidence evidence);|
|Load(XmlReader stylesheet);<br /><br /> Load(XmlReader stylesheet, XmlResolver resolver);|Load(XmlReader stylesheet, XmlResolver resolver, Evidence evidence);|

В следующей таблице показаны устаревшие и новые методы для метода <xref:System.Xml.Xsl.XslTransform.Transform%2A>. Новые методы принимают объект <xref:System.Xml.XmlResolver>.

|Устаревшие методы Transform платформы .NET Framework версии 1.0|Заменяющие их методы Transform платформы .NET Framework версии 1.1|
|-----------------------------------------------------------|--------------------------------------------------------------|
|XmlReader Transform(XPathNavigator input, XsltArgumentList args)|XmlReader Transform(XPathNavigator  input, XsltArgumentList args, XmlResolver resolver)|
|XmlReader Transform(IXPathNavigable input, XsltArgumentList args)|XmlReader Transform(IXPathNavigable input, XsltArgumentList args, XmlResolver resolver)|
|Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output)|Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)|
|Void Transform(IXPathNavigable input, XsltArgumentList args, XmlWriter output)|Void Transform(IXpathNavigable input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)|
|Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output)|Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output, XmlResolver resolver)|
|Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output)|Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output, XmlResolver resolver)|
|Void Transform(XPathNavigator input, XsltArgumentList args, Stream output)|Void Transform(XPathNavigator input, XsltArgumentList args, Stream output, XmlResolver resolver)|
|Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output)|Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output, XmlResolver resolver)|
|Void Transform(String input, String output);|Void Transform(String input, String output, XmlResolver resolver);|

Свойство <xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType> в платформе .NET Framework версии 1.1 является устаревшим. Используйте вместо него новые перегрузки <xref:System.Xml.Xsl.XslTransform.Transform%2A>, принимающие объект <xref:System.Xml.XmlResolver>.

## <a name="see-also"></a>См. также:

- <xref:System.Xml.Xsl.XslTransform>
- [XSLT-преобразования с помощью класса XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [XPathNavigator в преобразованиях](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [XPathNodeIterator в преобразованиях](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [Ввод XPathDocument в XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [Ввод XmlDataDocument в XslTransform](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
- [Ввод XmlDocument в XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
