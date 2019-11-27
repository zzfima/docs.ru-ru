---
title: Введение в LINQ
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: add442583bd81665533b704c0c9721b111cddd78
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74338908"
---
# <a name="introduction-to-linq-visual-basic"></a>Введение в LINQ (Visual Basic)
LINQ (Language-Integrated Query) — это новая возможность, появившаяся в .NET Framework версии 3.5, которая соединяет мир объектов с миром данных.  
  
 Традиционно запросы к данным выражаются в виде простых строк без проверки типов при компиляции или поддержки IntelliSense. Кроме того, разработчику приходится изучать различные языки запросов для каждого из типов источников данных: баз данных SQL, XML-документов, различных веб-служб и т. д. LINQ делает *запрос* к конструкции языка первого класса в Visual Basic. Вы создаете запросы к строго типизированным коллекциям объектов с помощью ключевых слов языка и знакомых операторов.  
  
 Можно писать запросы LINQ в Visual Basic для SQL Server баз данных, XML-документов, наборов данных ADO.NET и любой коллекции объектов, поддерживающей <xref:System.Collections.IEnumerable> или универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>. Кроме того, сторонние разработчики обеспечивают поддержку LINQ для множества веб-служб и других реализаций баз данных.  
  
 Запросы LINQ можно использовать в новых проектах или параллельно с запросами, не относящимися к LINQ, в существующих проектах. Единственное требование: проект должен разрабатываться для платформы .NET Framework версии 3.5 или более поздней.  
  
 На приведенном ниже рисунке показан частично выполненный запрос LINQ к базе данных SQL Server в C# и Visual Basic с полной проверкой типов и поддержкой IntelliSense.  
  
 ![Схема, показывающая запрос LINQ с Intellisense.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a>Следующие шаги  
 Чтобы получить дополнительные сведения о LINQ, начните с ознакомления с некоторыми основными понятиями в начало работы разделе [Начало работы с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), а затем прочитайте документацию по интересующей вас технологии LINQ:  
  
- Базы данных SQL Server: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
- XML-документы: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
- Наборы данных ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
- Коллекции .NET, файлы, строки и т. д. [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a>См. также:

- [Синтаксис LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
