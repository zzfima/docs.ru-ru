---
title: "Создание новых атрибутов для элементов в модели DOM"
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
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6970ffc38e900c9b47c58c8ae4b81b9551f5589b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a>Создание новых атрибутов для элементов в модели DOM
Создание новых атрибутов отличается от создания других типов узлов, поскольку атрибуты являются не узлами, но свойства узла элемента и содержатся в **XmlAttributeCollection** связанных с элементом. Есть несколько способов создания атрибута и присоединения его к элементу:  
  
-   Вернуть узел элемента и использовать **SetAttribute** Чтобы добавить атрибут в коллекцию атрибутов этого элемента.  
  
-   Создание **XmlAttribute** узла с помощью **CreateAttribute** , вернуть узел элемента и использовать **SetAttributeNode** для добавления в коллекцию атрибутов этого узла элемент.  
  
 Следующий пример демонстрирует добавление атрибута к элементу с помощью **SetAttribute** метод.  
  
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
  
 В следующем примере показано новый атрибут с помощью **CreateAttribute** метод. Затем показано, как атрибут добавляется в коллекцию атрибутов этого **книги** элемента с помощью **SetAttributeNode** метод.  
  
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
  
 Полный образец кода можно найти на <xref:System.Xml.XmlDocument.CreateAttribute%2A>.  
  
 Можно также создать **XmlAttribute** узел и использование **InsertBefore** или **InsertAfter** чтобы поместить его в соответствующее место в коллекции. Если атрибут с таким именем уже существует в коллекции атрибутов существующих **XmlAttribute** узел удаляется из коллекции, а новый **XmlAttribute** вставки узла. В этом случае выполняется так же, как **SetAttribute** метод. Эти методы принимают в качестве параметра существующий узел как отправную точку для выполнения **InsertBefore** и **InsertAfter**. Если эталонный узел, куда необходимо добавить новый узел, по умолчанию не имеют **InsertAfter** вставляет новый узел в начало коллекции. Значение по умолчанию положения **InsertBefore**, если ни один узел ссылки, в конец коллекции.  
  
 Если вы создали **XmlNamedNodeMap** атрибутов, можно добавить атрибут по имени с помощью <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>. Дополнительные сведения см. в разделе [коллекции узлов в NamedNodeMap и nodelist](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).  
  
## <a name="default-attributes"></a>Атрибуты по умолчанию  
 При создании элемента, для которого декларирован атрибут по умолчанию, модель XML DOM создаст новый атрибут по умолчанию со значением по умолчанию и присоединит его к элементу. Одновременно будут созданы дочерние узлы атрибута по умолчанию.  
  
## <a name="attribute-child-nodes"></a>Дочерние узлы атрибута  
 Значение узла атрибута становится его дочерними узлами. Существует только два типа допустимым дочерних узлов: **XmlText** узлов, и **XmlEntityReference** узлов. Они являются дочерними узлами в том смысле, что методы, такие как **FirstChild** и **LastChild** обрабатывают их как дочерние узлы. Это отличие атрибута, имеющего дочерние узлы, становится важным во время удаления атрибута или его дочерних узлов. Дополнительные сведения см. в разделе [удаление атрибутов из узла элемента в DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
