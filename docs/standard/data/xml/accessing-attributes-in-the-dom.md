---
title: "Доступ к атрибутам в модели DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a433ec5f83a50aa4fe4b2017a0dac3d2a5e5710c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-attributes-in-the-dom"></a>Доступ к атрибутам в модели DOM
Атрибуты - свойства элемента, а не его дочерние элементы. Это различие очень важно из-за методов, используемых для перемещения по дочерним, родительским и одноуровневым узлам модели XML DOM. Например **PreviousSibling** и **NextSibling** методы не используются для перемещения с элемента на атрибут или между атрибутами. Вместо этого атрибут является свойством элемента и принадлежит элемент, имеет **OwnerElement** свойство и не **parentNode** свойство, и имеет собственные методы навигации.  
  
 Если текущий узел является элементом, используйте **HasAttribute** метод, если есть какие-либо атрибуты, связанные с элементом. Если у элемента есть атрибуты, к ним можно получить доступ различными методами. Для получения одного атрибута элемента, можно использовать **GetAttribute** и **GetAttributeNode** методы **XmlElement** или получить все атрибуты в коллекцию. Получение коллекции удобно, если предполагается ее обзор. Если требуется, чтобы все атрибуты данного элемента, используйте **атрибуты** свойство элемента для получения всех атрибутов в коллекцию.  
  
## <a name="retrieving-all-attributes-into-a-collection"></a>Получение всех атрибутов в виде коллекции  
 Если требуется поместить все атрибуты узла элемента в коллекцию, вызовите **XmlElement.Attributes** свойство. Это возвращает **XmlAttributeCollection** , содержащий все атрибуты элемента. **XmlAttributeCollection** класс наследует от **XmlNamedNode** карты. Таким образом, методы и свойства, доступные для данной коллекции включают в себя те, которые доступны для карты именованного узла в дополнение к методам и свойствам, специфичным для **XmlAttributeCollection** класса, такие как **ItemOf**  свойство или **Append** метод. Каждый элемент в коллекции атрибутов представляет **XmlAttribute** узла. Чтобы выяснить число атрибутов данного элемента, получить **XmlAttributeCollection**и использовать **число** свойство, чтобы просмотреть сколько **XmlAttribute** узлы находятся в коллекции.  
  
 В следующем примере кода показано, как получить атрибут коллекции и, используя **число** для индекса цикла, пройти по ней. Затем в примере демонстрируется получение одного атрибута из коллекции и вывод его значения.  
  
```vb  
Imports System  
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
  
```  
genre = novel  
ISBN = 1-861001-57-5  
misc = sale item  
Display the attribute information.  
sale item  
```  
  
 Информация из коллекции атрибутов может быть получена по имени или по значению индекса. В примере показано получение данных по имени. В следующем примере показано получение данных по значению индекса.  
  
 Поскольку **XmlAttributeCollection** является коллекцией и ее можно обходить по имени или индексу, в этом примере показан выбор из коллекции, используя отсчитываемый от нуля индекс и следующий файл первого атрибута **baseuri.xml**качестве входных данных.  
  
### <a name="input"></a>Ввод  
  
```xml  
<!-- XML fragment -->  
<book genre="novel">  
  <title>Pride And Prejudice</title>  
</book>  
```  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
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
        Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText)  
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
    Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText);  
  }  
}  
```  
  
## <a name="retrieving-an-individual-attribute-node"></a>Получение единичного узла атрибута  
 Для получения из элемента одного узла атрибута используется метод <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType>. Возвращает объект типа **XmlAttribute**. После получения **XmlAttribute**, все методы и свойства, доступные в <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> класса доступны для этого объекта, например, можно найти **OwnerElement**.  
  
```vb  
Imports System  
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
  
 Можно также поступить как в предыдущем примере, где единичный узел атрибута был получен из коллекции атрибутов. В следующем примере кода показано как с одной строки кода можно получить единичный атрибут по номеру индекса из корневого элемента XML-документа дерева, также известного как **DocumentElement** свойство.  
  
```  
XmlAttribute attr = doc.DocumentElement.Attributes[0];  
```  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
