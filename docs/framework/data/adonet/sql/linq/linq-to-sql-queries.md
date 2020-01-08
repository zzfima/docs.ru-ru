---
title: Запросы LINQ to SQL
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: 478138d26d6cdf656b2487c637a5eb13784126e9
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634384"
---
# <a name="linq-to-sql-queries"></a>Запросы LINQ to SQL
Запросы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяются с использованием того же синтаксиса, что и в LINQ. Единственное отличие заключается в том, что объекты, на которые ссылаются запросы, сопоставляются с элементами базы данных. Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки. В частности, приложение использует API-интерфейс [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для выполнения запроса. Затем поставщик [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запрос в текст SQL и делегирует выполнение поставщику ADO. Поставщик ADO возвращает результаты запроса в виде объекта `DataReader`. Поставщик [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует результаты ADO в коллекцию <xref:System.Linq.IQueryable> объектов User.  
  
> [!NOTE]
> Большинство методов и операторов на .NET Framework встроенных типах имеют прямой перевод в SQL. Те, которые LINQ не может преобразовать, создают исключения времени выполнения. Дополнительные сведения см. в разделе [Сопоставление типов SQL-CLR](sql-clr-type-mapping.md).  
  
 В следующей таблице показаны сходства и различия между элементами запроса LINQ и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Элемент|Запрос LINQ|Запрос [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|----------|----------------|----------------------------------------------------------------------|  
|Тип возвращаемого значения для локальной переменной, содержащей запрос (для запросов, которые возвращают последовательности)|Универсальный тип `IEnumerable`|Универсальный тип `IQueryable`|  
|Указание источника данных|Использует предложение `From` (Visual Basic) или `from` (C#)|То же самое|  
|Фильтрация|Использует предложение `where` /`Where`|То же самое|  
|Группирование|Использует предложение `groupby` /`Group…By`|То же самое|  
|Выбор (проецирование)|Использует предложение `select` /`Select`|То же самое|  
|Отложенное или немедленное выполнение|См. статью [Общие сведения оC#LINQ-запросах ()](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) .|То же самое|  
|Реализация соединений|Использует предложение `join` /`Join`|Может использовать предложение `Join`/`join`, но более эффективно использует атрибут <xref:System.Data.Linq.Mapping.AssociationAttribute>. Дополнительные сведения см. в разделе [запросы по связям](querying-across-relationships.md).|  
|Удаленное или локальное выполнение||Дополнительные сведения см. в разделе [удаленное и локальное выполнение](remote-vs-local-execution.md).|  
|Потоковое или кэшированное выполнение запросов|Не применяется при использовании локальной памяти||  
  
## <a name="see-also"></a>См. также:

- [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Основные операции запроса LINQ](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Связи типов в операциях запроса LINQ](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Основные принципы запросов](query-concepts.md)
