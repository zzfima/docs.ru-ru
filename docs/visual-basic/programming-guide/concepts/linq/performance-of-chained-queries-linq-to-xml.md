---
title: "Производительность цепочек запросов (LINQ to XML) (Visual Basic) | Документы Microsoft"
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
ms.assetid: 589f2adc-69f9-404d-b9d6-4c28dabea7f7
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dd5b63f255107c5864108cfbb87bef6e53a971a0
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017


---
# <a name="performance-of-chained-queries-linq-to-xml-visual-basic"></a>Производительность цепочек запросов (LINQ to XML) (Visual Basic)
Одним из наиболее важных преимуществ LINQ (и LINQ to XML) является возможность эффективного выполнения цепочек запросов наряду с одиночными большими и более сложными запросами.  
  
 Цепочкой запросов называется запрос, использующий в качестве источника другой запрос. Например, в следующем простом коде запрос `query2` в качестве источника включает в себя запрос `query1`.  
  
```vb  
Dim root As New XElement("Root", New XElement("Child", 1), New XElement("Child", 2), New XElement("Child", 3), New XElement("Child", 4))  
  
Dim query1 = From x In root.Elements("Child") Where CInt(x) >= 3x  
  
Dim query2 = From e In query1 Where CInt(e) Mod 2 = 0e  
  
For Each i As var In query2  
    Console.WriteLine("{0}", CInt(i))  
Next  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
4  
```  
  
 Эта цепочка запросов по своим показателям производительности аналогична выполнению итераций по связанному списку.  
  
-   <xref:System.Xml.Linq.XContainer.Elements%2A>Ось имеет по сути такую же производительность итераций по связанному списку.</xref:System.Xml.Linq.XContainer.Elements%2A> <xref:System.Xml.Linq.XContainer.Elements%2A>реализуется как итератор с отложенным выполнением.</xref:System.Xml.Linq.XContainer.Elements%2A> Это означает, что помимо итераций по связанному списку выполняется и другая работа, например, выделяется память для объекта итератора и отслеживается состояние выполнения. Эта работа делится на две категории: работа, выполняемая при настройке итератора, и работа, выполняемая при каждой итерации. Настройка требует небольшого фиксированного объема работы, тогда как объем работы, выполняемой при каждой итерации, пропорционален количеству элементов в исходной коллекции.  
  
-   В `query1`, `Where` вызывает предложения запроса для вызова <xref:System.Linq.Enumerable.Where%2A>метод.</xref:System.Linq.Enumerable.Where%2A> Этот метод так же реализован в виде итератора. Работа по настройке состоит в создании экземпляра выражения-делегата, которое будет ссылаться на лямбда-выражение, и в выполнении обычной настройки итератора. Выражение-делегат вызывается в каждой итерации для выполнения предиката. Работа по настройке и работа, выполняемая при каждой итерации, аналогична работе, выполняемой при итерациях по оси.  
  
-   В `query1`, предложение select вызывает запрос для вызова <xref:System.Linq.Enumerable.Select%2A>метод.</xref:System.Linq.Enumerable.Select%2A> Этот метод имеет те же показатели производительности, как <xref:System.Linq.Enumerable.Where%2A>метод.</xref:System.Linq.Enumerable.Where%2A>  
  
-   В запросе `query2` предложения `Where` и `Select` имеют такие же показатели производительности, как и в запросе `query1`.  
  
 Таким образом, работа итерации по запросу `query2` прямо пропорциональна количеству элементов в источнике первого запроса, то есть имеет линейную зависимость.  
  
## <a name="see-also"></a>См. также  
 [Производительность (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

