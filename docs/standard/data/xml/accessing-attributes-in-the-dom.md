---
title: Доступ к атрибутам в модели DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
ms.openlocfilehash: dd3292620cafc4e5d2494b3b5e18e04691910dc4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711198"
---
# <a name="accessing-attributes-in-the-dom"></a>Доступ к атрибутам в модели DOM

Атрибуты - свойства элемента, а не его дочерние элементы. Это различие очень важно из-за методов, используемых для перемещения по дочерним, родительским и одноуровневым узлам модели XML DOM. Например, методы **PreviousSibling** и **NextSibling** не позволяют перемещаться с элемента на атрибут или с одного атрибута на другой. Вместо этого атрибут является свойством элемента и принадлежит ему. У атрибута есть специальные методы навигации и свойство **OwnerElement**, но нет свойства **parentNode**.

Если текущий узел является элементом, метод **HasAttribute** позволяет узнать, есть ли у него атрибуты. Если у элемента есть атрибуты, к ним можно получить доступ различными методами. Чтобы получить отдельный атрибут элементв, используйте методы **GetAttribute** и **GetAttributeNode** класса **XmlElement**. Также есть возможность получить все атрибуты сразу в виде коллекции. Получение коллекции удобно, если предполагается ее обзор. Если нужно получить все атрибуты конкретного элемента, воспользуйтесь его свойством **Attributes** для получения всех атрибутов в виде коллекции.

## <a name="retrieving-all-attributes-into-a-collection"></a>Получение всех атрибутов в виде коллекции

Если нужно поместить все атрибуты узла элемента в коллекцию, вызовите свойство **XmlElement.Attributes**. Оно возвращает коллекцию **XmlAttributeCollection** со всеми атрибутами элемента. Класс **XmlAttributeCollection** наследует от карты **XmlNamedNode**. Таким образом, для этой коллекции доступны все свойства и методы, что и для карты именованного узла, а также все методы и свойства класса **XmlAttributeCollection**, например свойство **ItemOf** и метод **Append**. Каждый элемент коллекции атрибутов представляет узел **XmlAttribute**. Чтобы выяснить число атрибутов некоторого элемента, получите коллекцию **XmlAttributeCollection** и вызовите ее свойство **Count**, которое содержит число узлов **XmlAttribute** в коллекции.

В следующем примере кода показано, как получить коллекцию атрибутов и последовательно перебрать ее элементы, используя метод **Count** в роли индекса цикла. Затем в примере демонстрируется получение одного атрибута из коллекции и вывод его значения.

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As XmlDocument = New XmlDocument()
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _
               "<title>The Handmaid's Tale</title>" & _
               "<price>14.95</price>" & _
               "</book>")

        ' Move to an element.
        Dim myElement As XmlElement = doc.DocumentElement

        ' Create an attribute collection from the element.
        Dim attrColl As XmlAttributeCollection = myElement.Attributes

        ' Show the collection by iterating over it.
        Console.WriteLine("Display all the attributes in the collection...")
        Dim i As Integer
        For i = 0 To attrColl.Count - 1
            Console.Write("{0} = ", attrColl.ItemOf(i).Name)
            Console.Write("{0}", attrColl.ItemOf(i).Value)
            Console.WriteLine()
        Next

        ' Retrieve a single attribute from the collection; specifically, the
        ' attribute with the name "misc".
        Dim attr As XmlAttribute = attrColl("misc")

        ' Retrieve the value from that attribute.
        Dim miscValue As String = attr.InnerXml

        Console.WriteLine("Display the attribute information.")
        Console.WriteLine(miscValue)

    End Sub
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;

public class Sample
{

    public static void Main()
    {
        XmlDocument doc = new XmlDocument();
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" +
                      "<title>The Handmaid's Tale</title>" +
                      "<price>14.95</price>" +
                      "</book>");

        // Move to an element.
        XmlElement myElement = doc.DocumentElement;

        // Create an attribute collection from the element.
        XmlAttributeCollection attrColl = myElement.Attributes;

        // Show the collection by iterating over it.
        Console.WriteLine("Display all the attributes in the collection...");
        for (int i = 0; i < attrColl.Count; i++)
        {
            Console.Write("{0} = ", attrColl[i].Name);
            Console.Write("{0}", attrColl[i].Value);
            Console.WriteLine();
        }

        // Retrieve a single attribute from the collection; specifically, the
        // attribute with the name "misc".
        XmlAttribute attr = attrColl["misc"];

        // Retrieve the value from that attribute.
        String miscValue = attr.InnerXml;

        Console.WriteLine("Display the attribute information.");
        Console.WriteLine(miscValue);

    }
}
```

Этот пример выводит следующие данные:

**Вывод**

Отображает все атрибуты из коллекции.

```console
genre = novel
ISBN = 1-861001-57-5
misc = sale item
Display the attribute information.
sale item
```

Информация из коллекции атрибутов может быть получена по имени или по значению индекса. В примере показано получение данных по имени. В следующем примере показано получение данных по значению индекса.

**XmlAttributeCollection** является коллекцией, которую можно обходить по имени или индексу. В этом примере мы выбираем из коллекции первый атрибут по индексу (нумерация начинается с нуля) и применяем файл **baseuri.xml** в качестве источника входных данных.

### <a name="input"></a>Input

```xml
<!-- XML fragment -->
<book genre="novel">
  <title>Pride And Prejudice</title>
</book>
```

```vb
Option Explicit On
Option Strict On

Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()
        ' Create the XmlDocument.
        Dim doc As New XmlDocument()
        doc.Load("http://localhost/baseuri.xml")

        ' Display information on the attribute node. The value
        ' returned for BaseURI is 'http://localhost/baseuri.xml'.
        Dim attr As XmlAttribute = doc.DocumentElement.Attributes(0)
        Console.WriteLine("Name of the attribute:  {0}", attr.Name)
        Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI)
        Console.WriteLine("The value of the attribute:  {0}", attr.InnerText)
    End Sub 'Main
End Class 'Sample
```

```csharp
using System;
using System.IO;
using System.Xml;

public class Sample
{
  public static void Main()
  {
    // Create the XmlDocument.
    XmlDocument doc = new XmlDocument();

    doc.Load("http://localhost/baseuri.xml");

    // Display information on the attribute node. The value
    // returned for BaseURI is 'http://localhost/baseuri.xml'.
    XmlAttribute attr = doc.DocumentElement.Attributes[0];
    Console.WriteLine("Name of the attribute:  {0}", attr.Name);
    Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI);
    Console.WriteLine("The value of the attribute:  {0}", attr.InnerText);
  }
}
```

## <a name="retrieving-an-individual-attribute-node"></a>Получение единичного узла атрибута

Для получения из элемента одного узла атрибута используется метод <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType>. Он возвращает объект типа **XmlAttribute**. Для полученного объекта **XmlAttribute** доступны все методы и свойства класса <xref:System.Xml.XmlAttribute?displayProperty=nameWithType>, например, значение **OwnerElement**.

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As XmlDocument = New XmlDocument()
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _
               "<title>The Handmaid's Tale</title>" & _
               "<price>14.95</price>" & _
               "</book>")

        ' Move to an element.
        Dim root As XmlElement
        root = doc.DocumentElement

        ' Get an attribute.
        Dim attr As XmlAttribute
        attr = root.GetAttributeNode("ISBN")

        ' Display the value of the attribute.
        Dim attrValue As String
        attrValue = attr.InnerXml
        Console.WriteLine(attrValue)

    End Sub
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;

 public class Sample
 {
      public static void Main()
      {
    XmlDocument doc = new XmlDocument();
     doc.LoadXml("<book genre='novel' ISBN='1-861003-78' misc='sale item'>" +
                   "<title>The Handmaid's Tale</title>" +
                   "<price>14.95</price>" +
                   "</book>");

    // Move to an element.
     XmlElement root = doc.DocumentElement;

    // Get an attribute.
     XmlAttribute attr = root.GetAttributeNode("ISBN");

    // Display the value of the attribute.
     String attrValue = attr.InnerXml;
     Console.WriteLine(attrValue);

    }
}
```

Можно также поступить как в предыдущем примере, где единичный узел атрибута был получен из коллекции атрибутов. Следующий пример демонстрирует, как с помощью одной строки кода получить по значению индекса один атрибут из корневого элемента дерева XML-документа, существующего в виде свойства **DocumentElement**.

```csharp
XmlAttribute attr = doc.DocumentElement.Attributes[0];
```

## <a name="see-also"></a>См. также:

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
