---
title: "Сравнение объектов с помощью XmlNameTable"
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
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f6c65581437bfb22cf771d66716b3dbb62dbafae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="object-comparison-using-xmlnametable"></a>Сравнение объектов с помощью XmlNameTable
При создании **XmlDocuments** создается таблица имен специально для этого документа. Когда XML загружается в документ или создаются новые элементы и атрибуты, все имена элементов и атрибутов помещаются в **XmlNameTable**. Также объект **XmlDocument** можно создать с помощью существующего объекта **NameTable** из другого документа. Если **XmlDocuments** создается с помощью конструктора, который принимает параметр **XmlNameTable**, этот документ получает доступ к именам узлов, пространствам имен и префиксам, хранящимся в объекте **XmlNameTable**. Независимо от того, насколько таблица имен загружена именами, после сохранения их в таблице эти имена можно быстро сравнить, используя сравнение объектов вместо сравнения строк. Еще вы можете добавлять строки в таблицу имен с помощью <xref:System.Xml.NameTable.Add%2A>. Следующий пример кода демонстрирует создание таблицы имен и добавление к ней строки **MyString**. После этого на основе этой таблицы создается объект **XmlDocument**, и к существующей таблице имен добавляются имена элементов и атрибутов из файла **Myfile.xml**.  
  
```vb  
Dim nt As New NameTable()  
nt.Add("MyString")  
Dim doc As New XmlDocument(nt)  
doc.Load("Myfile.xml")  
```  
  
```csharp  
NameTable nt = new NameTable();  
nt.Add("MyString");  
XmlDocument doc = new XmlDocument(nt);  
doc.Load("Myfile.xml");  
```  
  
 В следующем примере кода показано создание документа, добавление к нему двух новых элементов, имена которых добавляются в таблицу имен, а также сравнение объектов по именам.  
  
```vb  
Dim doc1 As XmlDocument = imp.CreateDocument()  
Dim node1 As XmlElement = doc.CreateElement("node1")  
Dim doc2 As XmlDocument = imp.CreateDocument()  
Dim node2 As XmlElement = doc.CreateElement("node2")  
if (CType(node1.Name, object) = CType(node2.Name, object))  
```  
  
```csharp  
XmlDocument doc1 = imp.CreateDocument();  
node1 = doc1.CreateElement ("node1");  
XmlDocument doc2 = imp.CreateDocument();  
node2 = doc2.CreateElement ("node1");  
if (((object)node1.Name) == ((object)node2.Name))  
{ ...  
```  
  
 Приведенный выше сценарий передачи таблицы имен между двумя документами является типичным для многократной обработки документа некоторого типа, совместимого со схемой XSD или определением DTD, в котором многократно повторяются некоторые строки, например, при обработке заказов на веб-узле электронной торговли. Применение таблицы имен повышает производительность, поскольку одинаковое имя элемента встречается в нескольких документах.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
