---
title: "Запросы LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 533786ffe1fa39928f90d94bbb0d80584bf85b8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-sql-queries"></a>Запросы LINQ to SQL
Запросы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяются с помощью синтаксиса, используемого в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. Единственное отличие заключается в том, что объекты, на которые ссылаются запросы, сопоставляются с элементами базы данных. Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки. В частности, приложение использует API-интерфейс [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для выполнения запроса. Затем поставщик [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запрос в текст SQL и делегирует выполнение поставщику ADO. Поставщик ADO возвращает результаты запроса в виде объекта `DataReader`. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Поставщик преобразует результаты ADO в <xref:System.Linq.IQueryable> коллекции пользовательских объектов.  
  
> [!NOTE]
>  Для большинства методов и операторов, основанных на встроенных типах [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], предусмотрены непосредственные преобразования в команды SQL. Те методы и операторы, которые не могут быть преобразованы технологией [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], вызывают исключения во время выполнения. Дополнительные сведения см. в разделе [сопоставление типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 В следующей таблице показано сходство и различие между элементами запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Элемент|Запрос LINQ|Запрос [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|----------|----------------|----------------------------------------------------------------------|  
|Тип возвращаемых данных для локальной переменной, содержащей запрос (для запросов, которые возвращают последовательности)|Универсальный тип `IEnumerable`|Универсальный тип `IQueryable`|  
|Указание источника данных|Использует `From` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) или `from` предложение (C#)|То же|  
|Фильтрация|Использует `Where` / `where` предложения|То же|  
|Группирование|Использует `Group…By` / `groupby` предложения|То же|  
|Выбор (проецирование)|Использует `Select` / `select` предложения|То же|  
|Отложенное или немедленное выполнение|В разделе [введение в запросы LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|То же|  
|Реализация соединений|Использует `Join` / `join` предложения|Можно использовать `Join` / `join` предложение, однако более эффективно использовать <xref:System.Data.Linq.Mapping.AssociationAttribute> атрибута. Дополнительные сведения см. в разделе [выполнение запросов в связях](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).|  
|Удаленное или локальное выполнение||Дополнительные сведения см. в разделе [удаленного vs. Локальное выполнение](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md).|  
|Потоковое или кэшированное выполнение запросов|Не применяется при использовании локальной памяти||  
  
## <a name="see-also"></a>См. также  
 [Введение в запросы LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 [Основные операции запроса LINQ](~/docs/csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)  
 [Связи типов в операциях запроса LINQ](~/docs/csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)  
 [Основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
