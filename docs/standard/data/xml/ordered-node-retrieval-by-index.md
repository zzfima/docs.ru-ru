---
title: Упорядоченное извлечение узлов по индексу
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 5412c90f-2703-4aa8-a9c4-1b8a35183c37
ms.openlocfilehash: 72e866e43b556d8534024a219d924b1f372ed073
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710522"
---
# <a name="ordered-node-retrieval-by-index"></a>Упорядоченное извлечение узлов по индексу
Модель DOM XML-документа консорциума W3C описывает класс NodeList, который позволяет обрабатывать упорядоченные списки узлов, в отличие от неупорядоченного набора, обрабатываемого с помощью класса **XmlNamedNodeMap**. Класс NodeList в платформе Microsoft .NET Framework называется **XmlNodeList**. Методы и свойства, которые возвращают класс **XmlNodeList**:  
  
- XmlNode.ChildNodes  
  
- XmlDocument.GetElementsByTagName  
  
- XmlElement.GetElementsByTagName;  
  
- XmlNode.SelectNodes  
  
 Класс **XmlNodeList** имеет свойство **Count**, с помощью которого можно создавать циклы для выполнения итерации по узлам объекта **XmlNodeList**, как показано в следующем примере кода:  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
   doc.Load("books.xml")  
  
    ' Retrieve all book titles.  
    Dim root as XmlElement = doc.DocumentElement  
    Dim elemList as XmlNodeList = root.GetElementsByTagName("title")  
    Dim i as integer  
    for i=0  to elemList.Count-1  
        ' Display all book titles in the Node List.  
        Console.WriteLine(elemList.ItemOf(i).InnerXml)  
    next  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
// Retrieve all book titles.  
XmlElement root = doc.DocumentElement;  
XmlNodeList elemList = root.GetElementsByTagName("title");  
for (int i=0; i < elemList.Count; i++)  
{     
   // Display all book titles in the Node List.  
   Console.WriteLine(elemList[i].InnerXml);  
}   
```  
  
 В дополнение к свойству **Count**, доступен метод **GetEnumerator**, который обеспечивает итерацию в стиле `foreach` по коллекции узлов в объекте **XmlNodeList**. В следующем примере кода показано использование инструкции `foreach`.  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("books.xml")  
  
' Get book titles.  
Dim root As XmlElement = doc.DocumentElement  
Dim elemList As XmlNodeList = root.GetElementsByTagName("title")  
Dim ienum As IEnumerator = elemList.GetEnumerator()  
' Loop over the XmlNodeList using the enumerator ienum          
While ienum.MoveNext()  
    ' Display the book title.  
    Dim title As XmlNode = CType(ienum.Current, XmlNode)  
    Console.WriteLine(title.InnerText)  
End While  
```  
  
```csharp  
{  
     XmlDocument doc = new XmlDocument();  
     doc.Load("books.xml");  
  
     // Get book titles.  
     XmlElement root = doc.DocumentElement;  
     XmlNodeList elemList = root.GetElementsByTagName("title");  
     IEnumerator ienum = elemList.GetEnumerator();    
     // Loop over the XmlNodeList using the enumerator ienum          
     while (ienum.MoveNext())  
     {  
          // Display the book title.  
           XmlNode title = (XmlNode) ienum.Current;  
           Console.WriteLine(title.InnerText);  
     }  
  }  
```  
  
 Дополнительные сведения о доступных методах и свойствах класса **XmlNodeList** см. в описании <xref:System.Xml.XmlNodeList>.  
  
## <a name="see-also"></a>См. также:

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
