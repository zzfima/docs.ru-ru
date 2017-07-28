---
title: "Создание новых атрибутов для элементов в модели DOM | Microsoft Docs"
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
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Создание новых атрибутов для элементов в модели DOM
Создание новых атрибутов отличается от создания других типов узлов, поскольку атрибуты являются не узлами, а свойствами узла элемента и содержатся в коллекции **XmlAttributeCollection**, связанной с элементом.  Есть несколько способов создания атрибута и присоединения его к элементу:  
  
-   вернуть узел элемента и использовать метод **SetAttribute**, чтобы добавить атрибут в коллекцию атрибутов этого элемента;  
  
-   создать узел **XmlAttribute** с помощью метода **CreateAttribute**, вернуть узел элемента и использовать метод **SetAttributeNode**, чтобы добавить узел в коллекцию атрибутов этого элемента.  
  
 В следующем примере показано, как добавить атрибут к элементу с помощью метода **SetAttribute**.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
public class Sample  
  
  public shared sub Main()  
  
  Dim doc as XmlDocument = new XmlDocument()  
  doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _  
              "<title>Pride And Prejudice</title>" & _  
              "</book>")  
  Dim root as XmlElement = doc.DocumentElement  
  
  'Add a new attribute.  
  root.SetAttribute("genre", "urn:samples", "novel")  
  
  Console.WriteLine("Display the modified XML...")  
  Console.WriteLine(doc.InnerXml)  
  
  end sub  
end class  
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
    doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +  
                "<title>Pride And Prejudice</title>" +  
                "</book>");  
    XmlElement root = doc.DocumentElement;  
  
    // Add a new attribute.  
    root.SetAttribute("genre", "urn:samples", "novel");  
  
    Console.WriteLine("Display the modified XML...");  
    Console.WriteLine(doc.InnerXml);  
  }  
```  
  
 В следующем примере показано, как создать новый атрибут с помощью метода **CreateAttribute**.  Затем показано, как атрибут добавляется в коллекцию атрибутов элемента **book** с помощью метода **SetAttributeNode**.  
  
 Заданы следующие XML\-данные:  
  
```  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 Создается новый атрибут, и ему присваивается значение:  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 Атрибут присоединяется к его элементу:  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 **Вывод**  
  
```  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 Полный образец кода см. в разделе [Метод XmlDocument.CreateAttribute](frlrfSystemXmlXmlDocumentClassCreateAttributeTopic).  
  
 Также можно создать узел **XmlAttribute** и использовать метод **InsertBefore** или **InsertAfter**, чтобы поместить его в соответствующее место коллекции.  Если в коллекции атрибутов уже существует атрибут с таким именем, существующий узел **XmlAttribute** будет удален из коллекции и вместо него будет вставлен новый узел **XmlAttribute**.  Это происходит так же, как с помощью метода **SetAttribute**.  Эти методы принимают в качестве параметра существующий узел, используемый как точка ссылки для методов **InsertBefore** и **InsertAfter**.  Если не задан эталонный узел, относительно которого вставляется новый узел, по умолчанию метод **InsertAfter** вставляет новый узел в начало коллекции,  а метод **InsertBefore** \- в конец коллекции.  
  
 Если создана коллекция **XmlNamedNodeMap** атрибутов, можно добавить атрибут по имени с помощью метода [SetNamedItem](frlrfSystemXmlXmlNamedNodeMapClassSetNamedItemTopic).  Дополнительные сведения см. в разделе [Коллекции узлов в NamedNodeMaps и NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).  
  
## Атрибуты по умолчанию  
 При создании элемента, для которого декларирован атрибут по умолчанию, модель XML DOM создаст новый атрибут по умолчанию со значением по умолчанию и присоединит его к элементу.  Одновременно будут созданы дочерние узлы атрибута по умолчанию.  
  
## Дочерние узлы атрибута  
 Значение узла атрибута становится его дочерними узлами.  Существует вcего два допустимых типа дочерних узлов: **XmlText** и **XmlEntityReference**.  Они являются дочерними узлами в том смысле, что методы, подобные **FirstChild** и **LastChild**, обрабатывают их как дочерние узлы.  Это отличие атрибута, имеющего дочерние узлы, становится важным во время удаления атрибута или его дочерних узлов.  Дополнительные сведения см. в разделе [Удаление атрибутов из узла элемента в модели DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)