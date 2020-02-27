---
title: Неупорядоченное извлечение узлов по имени или индексу
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
ms.openlocfilehash: 577de6b60e579b37eb54ea69de72f3534f1d23ac
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628908"
---
# <a name="unordered-node-retrieval-by-name-or-index"></a>Неупорядоченное извлечение узлов по имени или индексу
Класс **XmlNamedNodeMap** описан в спецификации консорциума W3C как NamedNodeMap. Он нужен для обработки неупорядоченного набора узлов с возможностью ссылаться на узлы по их именам и индексам. Единственный способ доступа к классу **XmlNamedNodeMap** — возврат **XmlNamedNodeMap** через метод или свойство. Есть три метода или свойства, возвращающих класс **XmlNamedNodeMap**:  
  
- XmlElement.Attributes;  
  
- XmlDocumentType.Entities;  
  
- XmlDocumentType.Notations.  
  
 Например, свойство **XmlDocumentType.Entities** получает коллекцию узлов **XmlEntity**, указанных в декларации типа документа. Эта коллекция возвращается как **XmlNamedNodeMap**. Можно выполнить итерацию по коллекции с помощью свойства **Count** и отобразить данные о сущности. Пример выполнения итерации по **XmlNamedNodeMap** см. в описании <xref:System.Xml.XmlDocumentType.Entities%2A>.  
  
 Коллекция **XmlAttributeCollection** является производной от **XmlNamedNodeMap**. Изменять можно только атрибуты, а нотации и сущности доступны только для чтения. С помощью коллекции **XmlNamedNodeMap** для атрибутов можно получить узлы на основе их XML-имен. Это дает простой метод управления коллекцией атрибутов на узле элемента. Этот метод можно противопоставить напрямую коллекции **XmlNodeList**, в которой также реализован интерфейс **IEnumerable**, но с использованием метода доступа по индексу, а не по строке. Методы **RemoveNamedItem** и **SetNamedItem** используются только с коллекцией **XmlAttributeCollection**. Добавление или удаление из коллекции атрибутов, как с помощью реализации **AttributeCollection**, так и с помощью **XmlNamedNodeMap**, изменяет коллекцию атрибутов в элементе. В следующем примере кода показан способ перемещения атрибута и создания атрибута.  
  
```vb  
Imports System  
Imports System.Xml  
  
Class test  
  
    Public Shared Sub Main()  
        Dim doc As New XmlDocument()  
        doc.LoadXml("<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> ")  
  
        ' Get the attributes of node "child2 "  
        Dim ac As XmlAttributeCollection = doc.DocumentElement.ChildNodes(1).Attributes  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
        Dim i As Integer  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Get the 'attr1' from child1.  
        Dim attr As XmlAttribute = doc.DocumentElement.ChildNodes(0).Attributes(0)  
  
        ' Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem(attr)  
  
        ''attr1' will be removed from 'child1' and added to 'child2'.  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Create a new attribute and add to the collection.  
        Dim attr2 As XmlAttribute = doc.CreateAttribute("attr4")  
        attr2.Value = "val4"  
        ac.SetNamedItem(attr2)  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
    End Sub 'Main  
End Class 'test  
```  
  
```csharp  
using System;  
using System.Xml;  
class test {  
    public static void Main() {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml( "<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> " );  
  
        // Get the attributes of node "child2"  
        XmlAttributeCollection ac = doc.DocumentElement.ChildNodes[1].Attributes;  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );  
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Get the 'attr1' from child1.  
        XmlAttribute attr = doc.DocumentElement.ChildNodes[0].Attributes[0];  
  
        // Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem( attr );  
  
        // 'attr1' will be removed from 'child1' and added to 'child2'.  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Create a new attribute and add to the collection.  
        XmlAttribute attr2 = doc.CreateAttribute( "attr4" );  
        attr2.Value = "val4";  
        ac.SetNamedItem( attr2 );  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );           
  
    }  
}  
```  
  
 Дополнительный пример кода, в котором показано перемещение атрибута из коллекции **AttributeCollection**, см. в описании [XmlNamedNodeMap.RemoveNamedItem Method](xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A). Дополнительные сведения о доступных методах и свойствах см. в описании [XmlNamedNodeMap Members](xref:System.Xml.XmlNamedNodeMap).  
  
## <a name="see-also"></a>См. также раздел

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
