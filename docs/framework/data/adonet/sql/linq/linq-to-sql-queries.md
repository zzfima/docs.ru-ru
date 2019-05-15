---
title: Запросы LINQ to SQL
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: 6142a1c4713010a75ed8413b935678fce92e40be
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583658"
---
# <a name="linq-to-sql-queries"></a>Запросы LINQ to SQL
Запросы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяются с помощью синтаксиса, используемого в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. Единственное отличие заключается в том, что объекты, на которые ссылаются запросы, сопоставляются с элементами базы данных. Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки. В частности, приложение использует API-интерфейс [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для выполнения запроса. Затем поставщик [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запрос в текст SQL и делегирует выполнение поставщику ADO. Поставщик ADO возвращает результаты запроса в виде объекта `DataReader`. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Поставщик преобразует результаты ADO <xref:System.Linq.IQueryable> коллекции объектов-пользователей.  
  
> [!NOTE]
>  Большинство методов и операторы для встроенных типов .NET Framework предусмотрены непосредственные преобразования в SQL. Те методы и операторы, которые не могут быть преобразованы технологией [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], вызывают исключения во время выполнения. Дополнительные сведения см. в разделе [сопоставления типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 В следующей таблице показано сходство и различие между элементами запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Элемент|Запрос LINQ|Запрос [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|----------|----------------|----------------------------------------------------------------------|  
|Тип возвращаемого значения для локальной переменной, содержащей запрос (для запросов, которые возвращают последовательности)|Универсальный тип `IEnumerable`|Универсальный тип `IQueryable`|  
|Указание источника данных|Использует `From` (Visual Basic) или `from` (C#) предложение|То же|  
|Фильтрация|Использует `Where` / `where` предложение|То же|  
|Группирование|Использует `Group…By` / `groupby` предложение|То же|  
|Выбор (проецирование)|Использует `Select` / `select` предложение|То же|  
|Отложенное или немедленное выполнение|См. в разделе [введение в запросы LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|То же|  
|Реализация соединений|Использует `Join` / `join` предложение|Можно использовать `Join` / `join` предложение, однако более эффективно использовать <xref:System.Data.Linq.Mapping.AssociationAttribute> атрибута. Дополнительные сведения см. в разделе [выполнение запросов в связях](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).|  
|Удаленное или локальное выполнение||Дополнительные сведения см. в разделе [удаленного vs. Локальное выполнение](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md).|  
|Потоковое или кэшированное выполнение запросов|Не применяется при использовании локальной памяти||  
  
## <a name="see-also"></a>См. также

- [Введение в запросы LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Основные операции запроса LINQ](~/docs/csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Связи типов в операциях запроса LINQ](~/docs/csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
