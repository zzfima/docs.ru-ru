---
title: "Введение в LINQ (Visual Basic) | Документы Microsoft"
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
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 41964e2fcbb079b7650c3132c9035fc2f754f3de
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-linq-visual-basic"></a>Введение в LINQ (Visual Basic)
Новая возможность, появившаяся в .NET Framework версии 3.5, мосты вовлеченности мир объектов с миром данных является Language Integrated Query (LINQ).  
  
 Традиционно запросы к данным выражаются в виде простых строк без проверки типов при компиляции или поддержки IntelliSense. Кроме того, необходимо узнать различные языки запросов для каждого типа источника данных: SQL базы данных, документы XML, различных веб-служб и т. д. LINQ позволяет *запроса* конструкцию полноправный язык в Visual Basic. Писать запросы к строго типизированным коллекциям объектов с помощью ключевых слов языка и знакомых операторов.  
  
 Можно писать запросы LINQ в Visual Basic для SQL Server базы данных, XML документы, наборы данных ADO.NET и коллекцию объектов, которая поддерживает <xref:System.Collections.IEnumerable>или универсальный <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable> Поддержка LINQ также предоставляется сторонними производителями для многих веб-служб и других реализаций базы данных.  
  
 Запросы LINQ можно использовать в новых проектах или параллельно с не использующего LINQ запросы в существующих проектах. Единственным требованием является то, что проект предназначены для .NET Framework 3.5 или более поздней версии.  
  
 На следующем из Visual Studio рисунке частично завершенной LINQ-запрос для базы данных SQL Server в C# и Visual Basic с полной проверкой типов и поддержку технологии IntelliSense.  
  
 ![Запрос LINQ с Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")  
  
## <a name="next-steps"></a>Дальнейшие действия  
 Чтобы получить дополнительные сведения о LINQ, начните с ознакомления с некоторыми основными понятиями в разделе Приступая к работе [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), а затем прочитайте документацию по технологии LINQ, который вас интересует:  
  
-   Базы данных SQL Server: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
  
-   XML-документы: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
-   Наборы данных ADO.NET: [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)  
  
-   Коллекции .NET, файлы, строк и т. д: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a>См. также  
 [Интегрированный в язык запрос (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
