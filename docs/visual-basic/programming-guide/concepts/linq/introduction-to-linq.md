---
title: Введение в LINQ (Visual Basic)
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: 8fdfbc0b397db0b3402334c03b6ac4720726d3cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502615"
---
# <a name="introduction-to-linq-visual-basic"></a>Введение в LINQ (Visual Basic)
LINQ (Language-Integrated Query) — это новая возможность, появившаяся в .NET Framework версии 3.5, которая соединяет мир объектов с миром данных.  
  
 Традиционно запросы к данным выражаются в виде простых строк без проверки типов при компиляции или поддержки IntelliSense. Кроме того нужно освоить различные языки запросов для каждого типа источника данных: Базы данных SQL, XML-документов, различных веб-служб и т. д. LINQ делает *запроса* очень удобной языковой конструкцией в Visual Basic. Вы создаете запросы к строго типизированным коллекциям объектов с помощью ключевых слов языка и знакомых операторов.  
  
 Вы можете писать запросы LINQ в Visual Basic для SQL Server базы данных, XML документы, наборы данных ADO.NET и любым коллекциям объектов, который поддерживает <xref:System.Collections.IEnumerable> или универсальный <xref:System.Collections.Generic.IEnumerable%601> интерфейс. Кроме того, сторонние разработчики обеспечивают поддержку LINQ для множества веб-служб и других реализаций баз данных.  
  
 Запросы LINQ можно использовать в новых проектах или параллельно с запросами, не относящимися к LINQ, в существующих проектах. Единственное требование: проект должен разрабатываться для платформы .NET Framework версии 3.5 или более поздней.  
  
 На приведенном ниже рисунке показан частично выполненный запрос LINQ к базе данных SQL Server в C# и Visual Basic с полной проверкой типов и поддержкой IntelliSense.  
  
 ![Запрос LINQ с Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")  
  
## <a name="next-steps"></a>Следующие шаги  
 Чтобы получить дополнительные сведения о LINQ, начните с ознакомления с некоторыми основным понятиями в разделе Приступая к работе [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), а затем ознакомиться с документацией по технологии LINQ, в которой вы являетесь Вы заинтересованы:  
  
-   Базы данных SQL Server: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
-   XML-документов: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
-   Наборы данных ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
-   Коллекции .NET, файлы, строк и т. д.: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a>См. также
- [Синтаксис LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
