---
title: Создание новых атрибутов для элементов в модели DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fb1a337c2795627b82125c8c29335c52b5fb332c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a>Создание новых атрибутов для элементов в модели DOM
Создание новых атрибутов отличается от создания других типов узлов, поскольку атрибуты являются не узлами, а свойствами узла элемента, и содержатся в связанной с этим элементом коллекции **XmlAttributeCollection**. Есть несколько способов создания атрибута и присоединения его к элементу:  
  
-   Получите узел элемента и примените метод **SetAttribute**, чтобы добавить атрибут в коллекцию атрибутов этого элемента.  
  
-   Создайте узел **XmlAttribute** с помощью метода **CreateAttribute**, получите узел элемента и примените метод **SetAttributeNode**, чтобы добавить узел в коллекцию атрибутов этого элемента.  
  
 Следующий пример демонстрирует, как добавить атрибут к элементу с помощью метода **SetAttribute**.  
  
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
  
 Следующий пример демонстрирует, как создать новый атрибут с помощью метода **CreateAttribute**. Созданный атрибут он добавляет в коллекцию атрибутов элемента **book** с помощью метода **SetAttributeNode**.  
  
 Заданы следующие XML-данные:  
  
```xml  
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
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 Полный код для этого примера вы найдете на странице <xref:System.Xml.XmlDocument.CreateAttribute%2A>.  
  
 Также можно создать узел **XmlAttribute** и вызвать метод **InsertBefore** или **InsertAfter**, чтобы поместить его в подходящее место коллекции. Если в коллекции атрибутов уже существует атрибут с таким именем, эти методы удаляют существующий узел **XmlAttribute** и добавляют вместо него новый узел **XmlAttribute**. Алгоритм выполнения здесь такой же, как у метода **SetAttribute**. Эти методы принимают в качестве параметра существующий узел, который будет считаться базовой точкой для методов **InsertBefore** и **InsertAfter**. Если не задан базовый узел, рядом с которым нужно вставить новый узел, метод **InsertAfter** по умолчанию вставляет новый узел в начало коллекции, а метод **InsertBefore** — в конец коллекции.  
  
 Если вы создали для атрибутов коллекцию **XmlNamedNodeMap**, можете добавить именованный атрибут с помощью метода <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>. Дополнительные сведения см. в статье [Коллекции узлов в NamedNodeMap и NodeList](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).  
  
## <a name="default-attributes"></a>Атрибуты по умолчанию  
 При создании элемента, для которого декларирован атрибут по умолчанию, модель XML DOM создаст новый атрибут по умолчанию со значением по умолчанию и присоединит его к элементу. Одновременно будут созданы дочерние узлы атрибута по умолчанию.  
  
## <a name="attribute-child-nodes"></a>Дочерние узлы атрибута  
 Значение узла атрибута становится его дочерними узлами. Существует всего два допустимых типа дочерних узлов: **XmlText** и **XmlEntityReference**. Они являются дочерними узлами в том смысле, что такие методы, как **FirstChild** и **LastChild**, обрабатывают их как дочерние узлы. Это отличие атрибута, имеющего дочерние узлы, становится важным во время удаления атрибута или его дочерних узлов. Дополнительные сведения см. в статье [Удаление атрибутов из узла элемента в модели DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
