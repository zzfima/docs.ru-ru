---
title: Запросы LINQ to SQL
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: 534da029664af0babc3dff6226ff095b7222c34d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915836"
---
# <a name="linq-to-sql-queries"></a>Запросы LINQ to SQL
Запросы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяются с помощью синтаксиса, используемого в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. Единственное отличие заключается в том, что объекты, на которые ссылаются запросы, сопоставляются с элементами базы данных. Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки. В частности, приложение использует API-интерфейс [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для выполнения запроса. Затем поставщик [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запрос в текст SQL и делегирует выполнение поставщику ADO. Поставщик ADO возвращает результаты запроса в виде объекта `DataReader`. Поставщик преобразует результаты ADO <xref:System.Linq.IQueryable> в коллекцию объектов User. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]  
  
> [!NOTE]
> Большинство методов и операторов на .NET Framework встроенных типах имеют прямой перевод в SQL. Те методы и операторы, которые не могут быть преобразованы технологией [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], вызывают исключения во время выполнения. Дополнительные сведения см. в разделе [Сопоставление типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 В следующей таблице показано сходство и различие между элементами запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Элемент|Запрос LINQ|Запрос [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|----------|----------------|----------------------------------------------------------------------|  
|Тип возвращаемого значения для локальной переменной, содержащей запрос (для запросов, которые возвращают последовательности)|Универсальный тип `IEnumerable`|Универсальный тип `IQueryable`|  
|Указание источника данных|Использует предложение `from` (Visual Basic) или (C# `From`|То же|  
|Фильтрация|`Where` Используетпредложение/ `where`|То же|  
|Группирование|`Group…By` Используетпредложение/ `groupby`|То же|  
|Выбор (проецирование)|`Select` Используетпредложение/ `select`|То же|  
|Отложенное или немедленное выполнение|См. статью [Общие сведения оC#LINQ-запросах ()](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) .|То же|  
|Реализация соединений|`Join` Используетпредложение/ `join`|`Join` Может использовать / <xref:System.Data.Linq.Mapping.AssociationAttribute> предложение, но более эффективно использует атрибут. `join` Дополнительные сведения см. в разделе [запросы по связям](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).|  
|Удаленное или локальное выполнение||Дополнительные сведения см. в [разделе Удаленная и Локальное](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md)выполнение.|  
|Потоковое или кэшированное выполнение запросов|Не применяется при использовании локальной памяти||  
  
## <a name="see-also"></a>См. также

- [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Основные операции запроса LINQ](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Связи типов в операциях запроса LINQ](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
