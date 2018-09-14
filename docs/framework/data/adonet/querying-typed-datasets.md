---
title: Запросы к типизированным наборам данных
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45510004"
---
# <a name="query-typed-datasets"></a>Запрос типизированных наборов данных

Если схема <xref:System.Data.DataSet> известна во время разработки приложения, мы рекомендуем использовать типизированный <xref:System.Data.DataSet> при использовании LINQ to DataSet. Типизированный <xref:System.Data.DataSet> — это класс, производный от <xref:System.Data.DataSet>. Поэтому он наследует все методы, события и свойства класса <xref:System.Data.DataSet>. Кроме того, типизированный <xref:System.Data.DataSet> предоставляет строго типизированные методы, события и свойства. Это означает, что доступ к таблицам и столбцам можно получить по имени, не используя методы на основе коллекций. Это упрощает запросы и повышает их читаемость. Дополнительные сведения см. в разделе [типизированных наборов DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).

LINQ to DataSet также поддерживает запросы к типизированным объектам <xref:System.Data.DataSet>. С типизированным <xref:System.Data.DataSet>, нет необходимости использовать универсальный <xref:System.Data.DataRowExtensions.Field%2A> метод или <xref:System.Data.DataRowExtensions.SetField%2A> метод для доступа к данным столбца. Имена свойств доступны во время компиляции, поскольку сведения о типе в <xref:System.Data.DataSet>. LINQ to DataSet предоставляет доступ к значениям столбцов правильного типа, чтобы ошибки несоответствия типов обнаруживаются в том случае, во время компиляции, а не во время выполнения.

Перед началом при запросе типизированного <xref:System.Data.DataSet>, необходимо создать класс с помощью **конструктор наборов данных** в Visual Studio. Дополнительные сведения см. в разделе [создать и настроить наборы данных](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).

## <a name="example"></a>Пример

В следующем примере показан запрос к типизированному объекту <xref:System.Data.DataSet>:

```csharp
var query = from o in orders
            where o.OnlineOrderFlag == true
            select new { o.SalesOrderID,
                         o.OrderDate,
                         o.SalesOrderNumber };

foreach(var order in query)
{
    Console.WriteLine("{0}\t{1:d}\t{2}",
      order.SalesOrderID,
      order.OrderDate,
      order.SalesOrderNumber);
}
```

```vb
Dim orders = ds.Tables("SalesOrderHeader")

Dim query = _
       From o In orders _
       Where o.OnlineOrderFlag = True _
       Select New {SalesOrderID := o.SalesOrderID, _
                   OrderDate := o.OrderDate, _
                   SalesOrderNumber := o.SalesOrderNumber}

For Each Dim onlineOrder In query
 Console.WriteLine("{0}\t{1:d}\t{2}", _
 onlineOrder.SalesOrderID, _
 onlineOrder.OrderDate, _
 onlineOrder.SalesOrderNumber)
Next
```

## <a name="see-also"></a>См. также

- [Запросы к DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [Запросы между таблицами](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [Запросы к одной таблице](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
