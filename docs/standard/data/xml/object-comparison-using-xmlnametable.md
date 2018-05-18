---
title: Сравнение объектов с помощью XmlNameTable
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09f717cb4c09c1e35b9472b7b549f1d3edf0dd15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
