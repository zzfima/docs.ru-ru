---
title: XSLT-преобразования с помощью класса XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 500335af-f9b5-413b-968a-e6d9a824478c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d534553fcc6ee63d560e731a535d44c3acd1a214
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347894"
---
# <a name="xslt-transformations-with-the-xsltransform-class"></a><span data-ttu-id="23f69-102">XSLT-преобразования с помощью класса XslTransform</span><span class="sxs-lookup"><span data-stu-id="23f69-102">XSLT Transformations with the XslTransform Class</span></span>

> [!NOTE]
> <span data-ttu-id="23f69-103">Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="23f69-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="23f69-104">Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="23f69-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="23f69-105">См. дополнительные сведения об [использовании класса XslCompiledTransform](using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="23f69-105">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>

<span data-ttu-id="23f69-106">Таблицы XSLT применяются для преобразования содержимого исходного XML-документа в другой документ, отличный по формату или структуре (например, чтобы преобразовать XML в HTML для использования в веб-узле или преобразовать его в документ, содержащий только поля, необходимые приложению).</span><span class="sxs-lookup"><span data-stu-id="23f69-106">The goal of the XSLT is to transform the content of a source XML document into another document that is different in format or structure (for example, to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application).</span></span> <span data-ttu-id="23f69-107">Это преобразование описано в [рекомендациях XSLT версии 1.0](https://www.w3.org/TR/1999/REC-xslt-19991116) консорциума W3C.</span><span class="sxs-lookup"><span data-stu-id="23f69-107">This transformation process is specified by the World Wide Web Consortium (W3C)[XSLT version 1.0 recommendation](https://www.w3.org/TR/1999/REC-xslt-19991116).</span></span> <span data-ttu-id="23f69-108">В платформе .NET Framework класс <xref:System.Xml.Xsl.XslTransform>, находящийся в пространстве имен <xref:System.Xml.Xsl>, является обработчиком XSLT, который реализует функциональность этой спецификации.</span><span class="sxs-lookup"><span data-stu-id="23f69-108">In the .NET Framework, the <xref:System.Xml.Xsl.XslTransform> class, found in the <xref:System.Xml.Xsl> namespace, is the XSLT processor that implements the functionality of this specification.</span></span> <span data-ttu-id="23f69-109">Нереализованные функции из рекомендаций XSLT 1.0 консорциума W3C см. руководстве по [выходным данным XslTransform](outputs-from-an-xsltransform.md).</span><span class="sxs-lookup"><span data-stu-id="23f69-109">There are a small number of features that have not been implemented from the W3C XSLT 1.0 recommendation, listed in [Outputs from an XslTransform](outputs-from-an-xsltransform.md).</span></span> <span data-ttu-id="23f69-110">На следующем рисунке показана архитектура преобразования в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="23f69-110">The following figure shows the transformation architecture of the .NET Framework.</span></span>

## <a name="overview"></a><span data-ttu-id="23f69-111">Обзор</span><span class="sxs-lookup"><span data-stu-id="23f69-111">Overview</span></span>

![Схема, показывающая архитектуру преобразования XSLT.](./media/xslt-transformations-with-the-xsltransform-class/xslt-transformation-architecture.gif) 

<span data-ttu-id="23f69-113">В рекомендациях XSLT используется язык XPath для выбора частей XML-документа, XPath - язык запросов, используемый для навигации по узлам дерева документов.</span><span class="sxs-lookup"><span data-stu-id="23f69-113">The XSLT recommendation uses XML Path Language (XPath) to select parts of an XML document, where XPath is a query language used to navigate nodes of a document tree.</span></span> <span data-ttu-id="23f69-114">Как показано на схеме, реализация языка XPath платформы .NET Framework используется для выбора частей XML-документа, сохраненных в нескольких классах, таких как <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument> и <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="23f69-114">As shown in the diagram, the .NET Framework implementation of XPath is used to select parts of XML stored in several classes, such as an <xref:System.Xml.XmlDocument>, an <xref:System.Xml.XmlDataDocument>, and an <xref:System.Xml.XPath.XPathDocument>.</span></span> <span data-ttu-id="23f69-115"><xref:System.Xml.XPath.XPathDocument> - оптимизированное хранилище данных XSLT, которое при использовании с классом <xref:System.Xml.Xsl.XslTransform> обеспечивает хорошую производительность преобразований XSLT.</span><span class="sxs-lookup"><span data-stu-id="23f69-115">An <xref:System.Xml.XPath.XPathDocument> is an optimized XSLT data store, and when used with <xref:System.Xml.Xsl.XslTransform>, it provides XSLT transformations with good performance.</span></span>

<span data-ttu-id="23f69-116">В следующей таблице перечислены классы, широко используемые при работе с классом <xref:System.Xml.Xsl.XslTransform> и XPath, и их функции.</span><span class="sxs-lookup"><span data-stu-id="23f69-116">The following table list commonly uses classes when working with <xref:System.Xml.Xsl.XslTransform> and XPath and their function.</span></span>

|<span data-ttu-id="23f69-117">Класс или интерфейс</span><span class="sxs-lookup"><span data-stu-id="23f69-117">Class or Interface</span></span>|<span data-ttu-id="23f69-118">Функция</span><span class="sxs-lookup"><span data-stu-id="23f69-118">Function</span></span>|
|------------------------|--------------|
|<xref:System.Xml.XPath.XPathNavigator>|<span data-ttu-id="23f69-119">API-интерфейс, который предоставляет модель стиля курсора для навигации по хранилищу, наряду с поддержкой запросов XPath.</span><span class="sxs-lookup"><span data-stu-id="23f69-119">It is an API that provides a cursor style model for navigating over a store, along with XPath query support.</span></span> <span data-ttu-id="23f69-120">Не позволяет вносить изменения в базовое хранилище.</span><span class="sxs-lookup"><span data-stu-id="23f69-120">It does not provide editing of the underlying store.</span></span> <span data-ttu-id="23f69-121">Для изменения используйте класс <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="23f69-121">For editing, use the <xref:System.Xml.XmlDocument> class.</span></span>|
|<xref:System.Xml.XPath.IXPathNavigable>|<span data-ttu-id="23f69-122">Интерфейс, который предоставляет метод `CreateNavigator` классу <xref:System.Xml.XPath.XPathNavigator> для хранилища.</span><span class="sxs-lookup"><span data-stu-id="23f69-122">It is an interface that provides a `CreateNavigator` method to an <xref:System.Xml.XPath.XPathNavigator> for the store.</span></span>|
|<xref:System.Xml.XmlDocument>|<span data-ttu-id="23f69-123">Позволяет изменять документ.</span><span class="sxs-lookup"><span data-stu-id="23f69-123">It enables editing of this document.</span></span> <span data-ttu-id="23f69-124">Реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable>, обеспечивая сценарии изменения документов, в которых требуются преобразования XSLT.</span><span class="sxs-lookup"><span data-stu-id="23f69-124">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing document-editing scenarios where XSLT transformations are subsequently required.</span></span> <span data-ttu-id="23f69-125">См. дополнительные сведения по [использованию XmlDocument в качестве входа для XslTransform](xmldocument-input-to-xsltransform.md).</span><span class="sxs-lookup"><span data-stu-id="23f69-125">For more information, see [XmlDocument Input to XslTransform](xmldocument-input-to-xsltransform.md).</span></span>|
|<xref:System.Xml.XmlDataDocument>|<span data-ttu-id="23f69-126">Производный от <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="23f69-126">It is derived from the <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="23f69-127">Соединяет реляционные и XML-данные с помощью объекта <xref:System.Data.DataSet> для оптимизации хранения структурированных данных в XML-документе в соответствии с сопоставлениями, указанными для объекта <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="23f69-127">It bridges the relational and XML worlds by using a <xref:System.Data.DataSet> to optimize storage of structured data within the XML document according to specified mappings on the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="23f69-128">Реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable>, обеспечивая сценарии, в которых преобразования XSLT могут быть выполнены над реляционными данными, полученными из базы данных.</span><span class="sxs-lookup"><span data-stu-id="23f69-128">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing scenarios where XSLT transformations can be performed over relational data retrieved from a database.</span></span> <span data-ttu-id="23f69-129">См. дополнительные сведения по [интеграции XML с реляционными данными и ADO.NET](xml-integration-with-relational-data-and-adonet.md).</span><span class="sxs-lookup"><span data-stu-id="23f69-129">For more information, see [XML Integration with Relational Data and ADO.NET](xml-integration-with-relational-data-and-adonet.md).</span></span>|
|<xref:System.Xml.XPath.XPathDocument>|<span data-ttu-id="23f69-130">Этот класс оптимизирован для обработки преобразований <xref:System.Xml.Xsl.XslTransform> и запросов XPath, и предоставляет высокопроизводительный кэш только для чтения.</span><span class="sxs-lookup"><span data-stu-id="23f69-130">This class is optimized for <xref:System.Xml.Xsl.XslTransform> processing and XPath queries, and it provides a read-only high performance cache.</span></span> <span data-ttu-id="23f69-131">Реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable> и является предпочтительным хранилищем для преобразований XSLT.</span><span class="sxs-lookup"><span data-stu-id="23f69-131">It implements <xref:System.Xml.XPath.IXPathNavigable> and is the preferred store to use for XSLT transformations.</span></span>|
|<xref:System.Xml.XPath.XPathNodeIterator>|<span data-ttu-id="23f69-132">Обеспечивает навигацию в наборах узлов XPath.</span><span class="sxs-lookup"><span data-stu-id="23f69-132">It provides navigation over XPath node sets.</span></span> <span data-ttu-id="23f69-133">Все методы выбора XPath класса <xref:System.Xml.XPath.XPathNavigator> возвращают объект <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="23f69-133">All XPath selection methods on the <xref:System.Xml.XPath.XPathNavigator> return an <xref:System.Xml.XPath.XPathNodeIterator>.</span></span> <span data-ttu-id="23f69-134">Несколько объектов <xref:System.Xml.XPath.XPathNodeIterator> могут быть созданы для одного хранилища, и каждый может представлять выбранный набор узлов.</span><span class="sxs-lookup"><span data-stu-id="23f69-134">Multiple <xref:System.Xml.XPath.XPathNodeIterator> objects can be created over the same store, each representing a selected set of nodes.</span></span>|

## <a name="msxml-xslt-extensions"></a><span data-ttu-id="23f69-135">Расширения MSXML XSLT</span><span class="sxs-lookup"><span data-stu-id="23f69-135">MSXML XSLT Extensions</span></span>

<span data-ttu-id="23f69-136">Функции `msxsl:script` и `msxsl:node-set` - единственные расширения MSXML XSLT, поддерживаемые классом <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="23f69-136">The `msxsl:script` and `msxsl:node-set` functions are the only Microsoft XML Core Services (MSXML) XSLT extensions supported by the <xref:System.Xml.Xsl.XslTransform> class.</span></span>

## <a name="example"></a><span data-ttu-id="23f69-137">Пример</span><span class="sxs-lookup"><span data-stu-id="23f69-137">Example</span></span>

<span data-ttu-id="23f69-138">Следующий пример кода загружает таблицу стилей XSLT, считывает файл с именем mydata.xml в объект <xref:System.Xml.XPath.XPathDocument> и выполняет преобразование данных из вымышленного файла с именем myStyleSheet.xsl, отправляя форматированные выходные данные на консоль.</span><span class="sxs-lookup"><span data-stu-id="23f69-138">The following code example loads an XSLT style sheet, reads a file called mydata.xml into an <xref:System.Xml.XPath.XPathDocument>, and performs a transformation on the data on a fictitious file called myStyleSheet.xsl, sending the formatted output to the console.</span></span>

```vb
Imports System.IO
Imports System.Xml
Imports System.Xml.XPath
Imports System.Xml.Xsl

Public Class Sample
    Private filename As [String] = "mydata.xml"
    Private stylesheet As [String] = "myStyleSheet.xsl"

    Public Shared Sub Main()
        Dim xslt As New XslTransform()
        xslt.Load(stylesheet)
        Dim xpathdocument As New XPathDocument(filename)
        Dim writer As New XmlTextWriter(Console.Out)
        writer.Formatting = Formatting.Indented

        xslt.Transform(xpathdocument, Nothing, writer, Nothing)
    End Sub 'Main
End Class 'Sample
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.XPath;
using System.Xml.Xsl;

public class Sample 
{
    private const String filename = "mydata.xml";
    private const String stylesheet = "myStyleSheet.xsl";

    public static void Main()
    {
        XslTransform xslt = new XslTransform();
        xslt.Load(stylesheet);
        XPathDocument xpathdocument = new XPathDocument(filename);
        XmlTextWriter writer = new XmlTextWriter(Console.Out);
        writer.Formatting = Formatting.Indented;

        xslt.Transform(xpathdocument, null, writer, null);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="23f69-139">См. также</span><span class="sxs-lookup"><span data-stu-id="23f69-139">See also</span></span>

- <xref:System.Xml.Xsl.XslTransform>
- [<span data-ttu-id="23f69-140">Реализация классом XslTransform XSLT-процессора</span><span class="sxs-lookup"><span data-stu-id="23f69-140">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
- [<span data-ttu-id="23f69-141">Реализация поведения по выбору в классе XslTransform</span><span class="sxs-lookup"><span data-stu-id="23f69-141">Implementation of Discretionary Behaviors in the XslTransform Class</span></span>](implementation-of-discretionary-behaviors-in-the-xsltransform-class.md)
- [<span data-ttu-id="23f69-142">XPathNavigator в преобразованиях</span><span class="sxs-lookup"><span data-stu-id="23f69-142">XPathNavigator in Transformations</span></span>](xpathnavigator-in-transformations.md)
- [<span data-ttu-id="23f69-143">XPathNodeIterator в преобразованиях</span><span class="sxs-lookup"><span data-stu-id="23f69-143">XPathNodeIterator in Transformations</span></span>](xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="23f69-144">Ввод XPathDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="23f69-144">XPathDocument Input to XslTransform</span></span>](xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="23f69-145">Ввод XmlDataDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="23f69-145">XmlDataDocument Input to XslTransform</span></span>](xmldatadocument-input-to-xsltransform.md)
- [<span data-ttu-id="23f69-146">Ввод XmlDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="23f69-146">XmlDocument Input to XslTransform</span></span>](xmldocument-input-to-xsltransform.md)
