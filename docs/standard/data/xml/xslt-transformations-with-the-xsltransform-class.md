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
# <a name="xslt-transformations-with-the-xsltransform-class"></a>XSLT-преобразования с помощью класса XslTransform

> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](migrating-from-the-xsltransform-class.md).

Таблицы XSLT применяются для преобразования содержимого исходного XML-документа в другой документ, отличный по формату или структуре (например, чтобы преобразовать XML в HTML для использования в веб-узле или преобразовать его в документ, содержащий только поля, необходимые приложению). Это преобразование описано в [рекомендациях XSLT версии 1.0](https://www.w3.org/TR/1999/REC-xslt-19991116) консорциума W3C. В платформе .NET Framework класс <xref:System.Xml.Xsl.XslTransform>, находящийся в пространстве имен <xref:System.Xml.Xsl>, является обработчиком XSLT, который реализует функциональность этой спецификации. Нереализованные функции из рекомендаций XSLT 1.0 консорциума W3C см. руководстве по [выходным данным XslTransform](outputs-from-an-xsltransform.md). На следующем рисунке показана архитектура преобразования в платформе .NET Framework.

## <a name="overview"></a>Обзор

![Схема, показывающая архитектуру преобразования XSLT.](./media/xslt-transformations-with-the-xsltransform-class/xslt-transformation-architecture.gif) 

В рекомендациях XSLT используется язык XPath для выбора частей XML-документа, XPath - язык запросов, используемый для навигации по узлам дерева документов. Как показано на схеме, реализация языка XPath платформы .NET Framework используется для выбора частей XML-документа, сохраненных в нескольких классах, таких как <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument> и <xref:System.Xml.XPath.XPathDocument>. <xref:System.Xml.XPath.XPathDocument> - оптимизированное хранилище данных XSLT, которое при использовании с классом <xref:System.Xml.Xsl.XslTransform> обеспечивает хорошую производительность преобразований XSLT.

В следующей таблице перечислены классы, широко используемые при работе с классом <xref:System.Xml.Xsl.XslTransform> и XPath, и их функции.

|Класс или интерфейс|Функция|
|------------------------|--------------|
|<xref:System.Xml.XPath.XPathNavigator>|API-интерфейс, который предоставляет модель стиля курсора для навигации по хранилищу, наряду с поддержкой запросов XPath. Не позволяет вносить изменения в базовое хранилище. Для изменения используйте класс <xref:System.Xml.XmlDocument>.|
|<xref:System.Xml.XPath.IXPathNavigable>|Интерфейс, который предоставляет метод `CreateNavigator` классу <xref:System.Xml.XPath.XPathNavigator> для хранилища.|
|<xref:System.Xml.XmlDocument>|Позволяет изменять документ. Реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable>, обеспечивая сценарии изменения документов, в которых требуются преобразования XSLT. См. дополнительные сведения по [использованию XmlDocument в качестве входа для XslTransform](xmldocument-input-to-xsltransform.md).|
|<xref:System.Xml.XmlDataDocument>|Производный от <xref:System.Xml.XmlDocument>. Соединяет реляционные и XML-данные с помощью объекта <xref:System.Data.DataSet> для оптимизации хранения структурированных данных в XML-документе в соответствии с сопоставлениями, указанными для объекта <xref:System.Data.DataSet>. Реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable>, обеспечивая сценарии, в которых преобразования XSLT могут быть выполнены над реляционными данными, полученными из базы данных. См. дополнительные сведения по [интеграции XML с реляционными данными и ADO.NET](xml-integration-with-relational-data-and-adonet.md).|
|<xref:System.Xml.XPath.XPathDocument>|Этот класс оптимизирован для обработки преобразований <xref:System.Xml.Xsl.XslTransform> и запросов XPath, и предоставляет высокопроизводительный кэш только для чтения. Реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable> и является предпочтительным хранилищем для преобразований XSLT.|
|<xref:System.Xml.XPath.XPathNodeIterator>|Обеспечивает навигацию в наборах узлов XPath. Все методы выбора XPath класса <xref:System.Xml.XPath.XPathNavigator> возвращают объект <xref:System.Xml.XPath.XPathNodeIterator>. Несколько объектов <xref:System.Xml.XPath.XPathNodeIterator> могут быть созданы для одного хранилища, и каждый может представлять выбранный набор узлов.|

## <a name="msxml-xslt-extensions"></a>Расширения MSXML XSLT

Функции `msxsl:script` и `msxsl:node-set` - единственные расширения MSXML XSLT, поддерживаемые классом <xref:System.Xml.Xsl.XslTransform>.

## <a name="example"></a>Пример

Следующий пример кода загружает таблицу стилей XSLT, считывает файл с именем mydata.xml в объект <xref:System.Xml.XPath.XPathDocument> и выполняет преобразование данных из вымышленного файла с именем myStyleSheet.xsl, отправляя форматированные выходные данные на консоль.

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

## <a name="see-also"></a>См. также

- <xref:System.Xml.Xsl.XslTransform>
- [Реализация классом XslTransform XSLT-процессора](xsltransform-class-implements-the-xslt-processor.md)
- [Реализация поведения по выбору в классе XslTransform](implementation-of-discretionary-behaviors-in-the-xsltransform-class.md)
- [XPathNavigator в преобразованиях](xpathnavigator-in-transformations.md)
- [XPathNodeIterator в преобразованиях](xpathnodeiterator-in-transformations.md)
- [Ввод XPathDocument в XslTransform](xpathdocument-input-to-xsltransform.md)
- [Ввод XmlDataDocument в XslTransform](xmldatadocument-input-to-xsltransform.md)
- [Ввод XmlDocument в XslTransform](xmldocument-input-to-xsltransform.md)
