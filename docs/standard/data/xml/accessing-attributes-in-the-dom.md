---
title: "Доступ к атрибутам в модели DOM | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Доступ к атрибутам в модели DOM
Атрибуты \- свойства элемента, а не его дочерние элементы.  Это различие очень важно из\-за методов, используемых для перемещения по дочерним, родительским и одноуровневым узлам модели XML DOM.  Например, методы **PreviousSibling** и **NextSibling** не используются для перемещения с элемента на атрибут или с одного атрибута на другой.  Вместо этого атрибут является свойством элемента и принадлежит ему. У атрибута есть свойство **OwnerElement** вместо свойства **parentNode**. Для атрибутов существуют специальные методы навигации.  
  
 Если текущий узел является элементом, можно узнать, есть ли у него атрибуты, с помощью метода **HasAttribute**.  Если у элемента есть атрибуты, к ним можно получить доступ различными методами.  Можно воспользоваться методами **GetAttribute** и **GetAttributeNode** класса **XmlElement** для получения единичного атрибута элемента, или получить все атрибуты сразу в виде коллекции.  Получение коллекции удобно, если предполагается ее обзор.  Если нужно получить все атрибуты данного элемента, следует воспользоваться его свойством **Attributes** для получения всех атрибутов в виде коллекции.  
  
## Получение всех атрибутов в виде коллекции  
 Если нужно поместить все атрибуты узла элемента в коллекцию, это можно сделать с помощью свойства **XmlElement.Attributes**.  Таким образом можно получить коллекцию **XmlAttributeCollection**, содержащую все атрибуты элемента.  Класс **XmlAttributeCollection** является производным от карты **XmlNamedNode**.  Поэтому свойства и методы, доступные для данной коллекции, включают в себя те, что доступны для карты именованного узла, в дополнение к методам и свойствам, специфичным для класса **XmlAttributeCollection** \- таким, как свойство **ItemOf** или метод **Append**.  Каждый элемент коллекции атрибутов представляет собой узел **XmlAttribute**.  Чтобы выяснить число атрибутов данного элемента, нужно получить объект **XmlAttributeCollection** и воспользоваться его свойством **Count**, чтобы узнать, сколько узлов **XmlAttribute** содержится в коллекции.  
  
 В следующем примере кода показано, как получить коллекцию атрибутов и пройти по ней, используя метод **Count** для индекса цикла.  Затем в примере демонстрируется получение одного атрибута из коллекции и вывод его значения.  
  
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
  
 Информация из коллекции атрибутов может быть получена по имени или по значению индекса.  В примере показано получение данных по имени.  В следующем примере показано получение данных по значению индекса.  
  
 Поскольку **XmlAttributeCollection** \- коллекция, и ее можно обходить по имени или индексу, в данном примере показан выбор из коллекции первого атрибута на основе индекса \(с отсчетом от 0\). В качестве ввода используется файл **baseuri.xml**.  
  
### Ввод  
  
```  
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
  
## Получение единичного узла атрибута  
 Для получения из элемента одного узла атрибута используется метод <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=fullName>.  Он возвращает объект типа **XmlAttribute**.  Для полученного объекта **XmlAttribute** доступны все методы и свойства класса [XmlAttribute Members](frlrfsystemxmlxmlattributeclasstopic) \- например, можно найти значение **OwnerElement**.  
  
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
  
 Можно также поступить как в предыдущем примере, где единичный узел атрибута был получен из коллекции атрибутов.  Следующий пример демонстрирует, как с помощью одной строки кода можно получить единичный атрибут по значению индекса из корневого элемента дерева XML\-документа, известного также как свойство **DocumentElement**.  
  
```  
XmlAttribute attr = doc.DocumentElement.Attributes[0];  
```  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)