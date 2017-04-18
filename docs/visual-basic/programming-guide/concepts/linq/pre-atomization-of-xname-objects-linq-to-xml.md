---
title: "Предварительная атомизация объектов XName (LINQ to XML) (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 519b64a96e03e098d7325cfb779bcd5d53db3741
ms.lasthandoff: 03/13/2017


---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a>Предварительная атомизация объектов XName (LINQ to XML) (Visual Basic)
Одним из способов повышения производительности в LINQ to XML является предварительная атомизация <xref:System.Xml.Linq.XName>объектов.</xref:System.Xml.Linq.XName> Предварительная атомизация присвоения строки для <xref:System.Xml.Linq.XName>Прежде чем создавать XML-дерево с помощью конструкторы <xref:System.Xml.Linq.XElement>и <xref:System.Xml.Linq.XAttribute>классы.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XName> Затем, вместо передачи строки конструктору, где будет выполнено ее неявное преобразование из строки в <xref:System.Xml.Linq.XName>, можно передать инициализированный <xref:System.Xml.Linq.XName>объекта.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName>  
  
 Таким способом можно повысить производительность при создании большого XML-дерева с рядом повторяющихся имен. Чтобы сделать это, необходимо объявить и инициализировать <xref:System.Xml.Linq.XName>объектов, прежде чем создавать XML-дерева, а затем используйте <xref:System.Xml.Linq.XName>объектов вместо строк имен элементов и атрибутов.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName> Эта техника может дать существенный рост производительности, когда создается большое количество элементов (или атрибутов) с одним и тем же именем.  
  
 Чтобы принять решение об использовании предварительной атомизации, протестируйте этот прием в вашем конкретном случае.  
  
## <a name="example"></a>Пример  
 В следующем примере это показано.  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 Следующий пример демонстрирует ту же технику, когда XML-документ находится в пространстве имен.  
  
```vb  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim Root__1 As XName = aw + "Root"  
Dim Data As XName = aw + "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XAttribute(XNamespace.Xmlns + "aw", aw), New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 Следующий пример наиболее приближен к реальной ситуации. В этом примере содержимое элементов предоставляется запросом.  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim t1 As DateTime = DateTime.Now  
Dim root__2 As New XElement(Root__1, From i In System.Linq.Enumerable.Range(1, 100000)New XElement(Data, New XAttribute(ID, i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
 Производительность кода в предыдущем примере выше, чем в следующем, где не выполняется предварительная атомизация имен.  
  
```vb  
Dim t1 As DateTime = DateTime.Now  
Dim root As New XElement("Root", From i In System.Linq.Enumerable.Range(1, 100000)New XElement("Data", New XAttribute("ID", i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
## <a name="see-also"></a>См. также  
 [Производительность (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)   
 [Атомизация объекты XName и XNamespace (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)
