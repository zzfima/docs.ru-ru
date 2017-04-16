---
title: "Запросы LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Запросы LINQ to SQL
Запросы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяются с помощью синтаксиса, используемого в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  Единственное отличие заключается в том, что объекты, на которые ссылаются запросы, сопоставляются с элементами базы данных.  Дополнительные сведения см. в разделе [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md).  
  
 Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки. В частности, приложение использует API\-интерфейс [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для выполнения запроса.  Поставщик [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запрос в текст SQL и делегирует выполнение поставщику ADO. Поставщик ADO возвращает результаты запроса в виде объекта `DataReader`.  Поставщик [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует результаты ADO в коллекцию <xref:System.Linq.IQueryable> пользовательских объектов.  
  
> [!NOTE]
>  Для большинства методов и операторов, основанных на встроенных типах [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], предусмотрены непосредственные преобразования в команды SQL.  Те методы и операторы, которые не могут быть преобразованы технологией [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], вызывают исключения во время выполнения.  Дополнительные сведения см. в разделе [Сопоставление типов SQL и CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 В следующей таблице показано сходство и различие между элементами запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Элемент|Запрос LINQ|Запрос [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|-------------|-----------------|-----------------------------------------------------------------------|  
|Тип возвращаемых данных для локальной переменной, содержащей запрос \(для запросов, которые возвращают последовательности\)|Универсальный тип `IEnumerable`|Универсальный тип `IQueryable`|  
|Указание источника данных|Используется предложение `From` \([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\) или `from` \(C\#\)|То же|  
|Фильтрация|Используется предложение `Where`\/`where`|То же|  
|Группирование|Используется предложение `Group…By`\/`groupby`|То же|  
|Выбор \(проецирование\)|Используется предложение `Select`\/`select`|То же|  
|Отложенное или немедленное выполнение|См. раздел [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)|То же|  
|Реализация соединений|Используется предложение `Join`\/`join`|Можно использовать предложение `Join`\/`join`, однако более эффективно использовать атрибут <xref:System.Data.Linq.Mapping.AssociationAttribute>.  Подробнее: [Выполнение запросов в связях](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).|  
|Удаленное или локальное выполнение||Подробнее: [Сравнение удаленного и локального выполнения](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md).|  
|Потоковое или кэшированное выполнение запросов|Не применяется при использовании локальной памяти||  
  
## См. также  
 [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)   
 [Basic LINQ Query Operations](../Topic/Basic%20LINQ%20Query%20Operations%20\(C%23\).md)   
 [Type Relationships in LINQ Query Operations](../Topic/Type%20Relationships%20in%20LINQ%20Query%20Operations%20\(C%23\).md)   
 [Основные понятия о запросах](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)