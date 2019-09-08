---
title: Запросы к типизированным наборам данных
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: 55714c4dae73cd17a849cc35681797dfa4266e3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782950"
---
# <a name="query-typed-datasets"></a>Запрос типизированных наборов данных

Если схема объекта <xref:System.Data.DataSet> известна во время разработки приложения, рекомендуется использовать типизированный <xref:System.Data.DataSet> при использовании LINQ to DataSet. Типизированный <xref:System.Data.DataSet> — это класс, производный <xref:System.Data.DataSet>от класса. Поэтому он наследует все методы, события и свойства класса <xref:System.Data.DataSet>. Кроме того, типизированный <xref:System.Data.DataSet> объект предоставляет строго типизированные методы, события и свойства. Это означает, что доступ к таблицам и столбцам можно получить по имени, не используя методы на основе коллекций. Это упрощает запросы и повышает их читаемость. Дополнительные сведения см. в разделе [типизированные наборы данных](./dataset-datatable-dataview/typed-datasets.md).

LINQ to DataSet также поддерживает запросы к типизированным <xref:System.Data.DataSet>. В типизированном <xref:System.Data.DataSet>виде нет необходимости использовать универсальный <xref:System.Data.DataRowExtensions.Field%2A> метод или <xref:System.Data.DataRowExtensions.SetField%2A> метод для доступа к данным столбца. Имена свойств доступны во время компиляции, <xref:System.Data.DataSet>так как сведения о типе включены в. LINQ to DataSet предоставляет доступ к значениям столбцов в качестве правильного типа, поэтому ошибки несоответствия типов перехватываются при компиляции кода, а не во время выполнения.

Прежде чем начать запрос к типизированному типу <xref:System.Data.DataSet>, необходимо создать класс с помощью **конструктора наборов данных** в Visual Studio. Дополнительные сведения см. в разделе [Создание и Настройка наборов данных](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).

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

- [Запросы к DataSet](querying-datasets-linq-to-dataset.md)
- [Запросы между таблицами](cross-table-queries-linq-to-dataset.md)
- [Запросы к одной таблице](single-table-queries-linq-to-dataset.md)
