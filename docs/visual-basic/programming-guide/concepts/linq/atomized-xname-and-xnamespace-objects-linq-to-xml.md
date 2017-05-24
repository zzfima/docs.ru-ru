---
title: "Атомизация объекты XName и XNamespace (LINQ to XML) (Visual Basic) | Документы Microsoft"
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
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b08f3116f5acb404cf2c33072ec31fbaada4e7cb
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017


---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a>Атомизация объекты XName и XNamespace (LINQ to XML) (Visual Basic)
<xref:System.Xml.Linq.XName>и <xref:System.Xml.Linq.XNamespace>объекты *атомизация*; то есть, если они имеют идентичное полное имя, они ссылаются на один объект.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName> Это способствует повышению производительности при выполнении запросов: при сравнении двух атомарных имен для проверки их равенства соответствующий промежуточный язык должен определить, ссылаются ли они на один и тот же объект. Эта операция используется в промежуточном коде вместо более длительной операции сравнения строк.  
  
## <a name="atomization-semantics"></a>Семантика атомизации  
 Атомизация означает, что если два <xref:System.Xml.Linq.XName>объекты имеют одинаковое локальное имя и они находятся в том же пространстве имен, они совместно используют тот же экземпляр.</xref:System.Xml.Linq.XName> Таким же образом, если два <xref:System.Xml.Linq.XNamespace>объекты имеют то же пространство имен URI, совместно используют тот же экземпляр.</xref:System.Xml.Linq.XNamespace>  
  
 Чтобы разрешить создание атомарных объектов класса, необходимо, чтобы конструктор класса был закрытым, а не открытым. Это требование основано на том, что если бы конструктор был открытым, можно было бы создавать неатомарные объекты. <xref:System.Xml.Linq.XName>И <xref:System.Xml.Linq.XNamespace>классы реализуют неявный оператор преобразования для преобразования строки в <xref:System.Xml.Linq.XName>или <xref:System.Xml.Linq.XNamespace>.</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName> Экземпляры этих объектов могут быть получены только таким способом. Создание экземпляров с помощью конструктора невозможно, так как конструктор недоступен.  
  
 <xref:System.Xml.Linq.XName>и <xref:System.Xml.Linq.XNamespace>также реализуют операторы равенства и неравенства, определяющие ли два сравниваемых являются ссылками на том же экземпляре.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName>  
  
## <a name="example"></a>Пример  
 Следующий код создает <xref:System.Xml.Linq.XElement>объектов и демонстрирует, что идентичные имена совместно используют тот же экземпляр.</xref:System.Xml.Linq.XElement>  
  
```vb  
Dim r1 As New XElement("Root", "data1")  
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")  
  
If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
  
Dim n As XName = "Root"  
  
If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 Как упоминалось выше, преимущество атомарных объектов заключается в, при использовании одного из методов оси, принимающих <xref:System.Xml.Linq.XName>как параметр метода оси должен определить, что два имени ссылки один и тот же экземпляр для выбора необходимых элементов.</xref:System.Xml.Linq.XName>  
  
 В следующем примере передается <xref:System.Xml.Linq.XName>для <xref:System.Xml.Linq.XContainer.Descendants%2A>вызова метода, для которого производительность за счет атомизации.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XName>  
  
```vb  
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))  
  
Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e  
  
For Each z As var In query  
    Console.WriteLine(z)  
Next  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
<C1>1</C1>  
<C1>1</C1>  
```  
  
## <a name="see-also"></a>См. также  
 [Производительность (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

