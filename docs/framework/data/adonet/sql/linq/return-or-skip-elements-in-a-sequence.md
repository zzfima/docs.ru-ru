---
title: "Возвращение или пропуск элементов последовательности | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81a31acd-e0f1-4bca-9a12-fa1ad5752374
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Возвращение или пропуск элементов последовательности
Для возвращения заданного числа элементов последовательности и пропуска оставшихся используется оператор <xref:System.Linq.Queryable.Take%2A>.  
  
 Для пропуска заданного числа элементов последовательности и возвращения оставшихся используется оператор <xref:System.Linq.Queryable.Skip%2A>.  
  
> [!NOTE]
>  На методы <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> накладываются некоторые ограничения при их использовании в запросах для SQL Server 2000.  Дополнительные сведения см. в подразделе «Исключения операторов "Skip" и "Take" в SQL Server 2000» раздела [Устранение неполадок](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует <xref:System.Linq.Queryable.Skip%2A> с помощью вложенного запроса с предложением `NOT EXISTS` SQL.  Это преобразование имеет следующие ограничения.  
  
-   Необходимо задать значение аргумента.  Не поддерживаются множественные наборы, даже упорядоченные.  
  
-   Созданный запрос может быть сложнее, чем запрос, созданный для основного запроса, к которому применен <xref:System.Linq.Queryable.Skip%2A>.  Это может стать причиной снижения производительности или даже привести к превышению времени ожидания.  
  
## Пример  
 В следующем примере для выбора первых пяти принятых на работу `Employees` используется метод `Take`.  Обратите внимание, что коллекция сначала сортируется по `HireDate`.  
  
 [!code-csharp[DLinqQueryExamples#16](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#16)]
 [!code-vb[DLinqQueryExamples#16](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#16)]  
  
## Пример  
 В следующем примере для выбора всех `Products`, за исключением 10 самых дорогих, используется метод <xref:System.Linq.Queryable.Skip%2A>.  
  
 [!code-csharp[DLinqQueryExamples#17](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#17)]
 [!code-vb[DLinqQueryExamples#17](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#17)]  
  
## Пример  
 В следующем примере для пропуска первых 50 и возвращения следующих за ними 10 записей методы <xref:System.Linq.Queryable.Skip%2A> и <xref:System.Linq.Queryable.Take%2A> объединяются.  
  
 [!code-csharp[DLinqQueryExamples#18](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#18)]
 [!code-vb[DLinqQueryExamples#18](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#18)]  
  
 Методы <xref:System.Linq.Queryable.Take%2A> и <xref:System.Linq.Queryable.Skip%2A> правильно определяются только для упорядоченных наборов.  Семантика для неупорядоченных наборов или множественных наборов не определена.  
  
 Из\-за ограничений, накладываемых на упорядочение в SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предпринимает попытку переместить упорядочение аргументов оператора <xref:System.Linq.Queryable.Take%2A> или <xref:System.Linq.Queryable.Skip%2A>в результат оператора.  
  
> [!NOTE]
>  Преобразование для [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] отличается от преобразования [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].  Если планируется применять метод <xref:System.Linq.Queryable.Skip%2A> в запросах любой сложности, используйте [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].  
  
 Рассмотрим следующий запрос [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].  
  
 [!code-csharp[DLinqQueryExamples#19](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#19)]
 [!code-vb[DLinqQueryExamples#19](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#19)]  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] перемещает упорядочение в конец кода SQL, как показано далее.  
  
```  
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],  
FROM [Customers] AS [t0]  
WHERE (NOT (EXISTS(  
    SELECT NULL AS [EMPTY]  
    FROM (  
        SELECT TOP 1 [t1].[CustomerID]  
        FROM [Customers] AS [t1]  
        WHERE [t1].[City] = @p0  
        ORDER BY [t1].[CustomerID]  
        ) AS [t2]  
    WHERE [t0].[CustomerID] = [t2].[CustomerID]  
    ))) AND ([t0].[City] = @p1)  
ORDER BY [t0].[CustomerID]  
```  
  
 При связывании методов <xref:System.Linq.Queryable.Take%2A> и <xref:System.Linq.Queryable.Skip%2A> друг с другом все указанные операции упорядочения должны быть согласованы.  В противном случае результаты не определены.  
  
 Методы <xref:System.Linq.Queryable.Take%2A> и <xref:System.Linq.Queryable.Skip%2A> правильно определяются для неотрицательных постоянных целочисленных аргументов, соответствующих спецификации SQL.  
  
## См. также  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)   
 [Преобразование стандартных операторов запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)