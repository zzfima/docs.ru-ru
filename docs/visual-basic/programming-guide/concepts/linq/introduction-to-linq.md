---
title: Введение в LINQ (Visual Basic)
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: 371801e1730c578b039adb6a88bd0bcdfd186db7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="introduction-to-linq-visual-basic"></a>Введение в LINQ (Visual Basic)
LINQ (Language-Integrated Query) — это новая возможность, появившаяся в .NET Framework версии 3.5, которая соединяет мир объектов с миром данных.  
  
 Традиционно запросы к данным выражаются в виде простых строк без проверки типов при компиляции или поддержки IntelliSense. Кроме того, разработчику приходится изучать различные языки запросов для каждого типа источников данных: баз данных SQL, XML-документов, различных веб-служб и т. д. LINQ позволяет *запроса* конструкцию полноправный язык в Visual Basic. Вы создаете запросы к строго типизированным коллекциям объектов с помощью ключевых слов языка и знакомых операторов.  
  
 Можно написать запросы LINQ в Visual Basic для SQL Server базы данных, XML документы, наборы данных ADO.NET и коллекция объектов, которая поддерживает <xref:System.Collections.IEnumerable> или универсальный <xref:System.Collections.Generic.IEnumerable%601> интерфейса. Кроме того, сторонние разработчики обеспечивают поддержку LINQ для множества веб-служб и других реализаций баз данных.  
  
 Запросы LINQ можно использовать в новых проектах или параллельно с запросами, не относящимися к LINQ, в существующих проектах. Единственное требование: проект должен разрабатываться для платформы .NET Framework версии 3.5 или более поздней.  
  
 На приведенном ниже рисунке показан частично выполненный запрос LINQ к базе данных SQL Server в C# и Visual Basic с полной проверкой типов и поддержкой IntelliSense.  
  
 ![Запрос LINQ с Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")  
  
## <a name="next-steps"></a>Следующие шаги  
 Чтобы получить дополнительные сведения о технологии LINQ, начните с ознакомления с некоторыми основными понятиями в разделе "Приступая к работе" [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), а затем ознакомиться с документацией по технологии LINQ, в которой вы являетесь нужны:  
  
-   Базы данных SQL Server: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
-   XML-документы: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
-   Наборы данных ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
-   Коллекции .NET, файлы, строк и т. п: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a>См. также  
 [Синтаксис LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
