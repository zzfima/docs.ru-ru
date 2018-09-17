---
title: Запросы к типизированным наборам данных
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45963748"
---
# <a name="query-typed-datasets"></a><span data-ttu-id="b2bb4-102">Запрос типизированных наборов данных</span><span class="sxs-lookup"><span data-stu-id="b2bb4-102">Query typed DataSets</span></span>

<span data-ttu-id="b2bb4-103">Если схема <xref:System.Data.DataSet> известна во время разработки приложения, мы рекомендуем использовать типизированный <xref:System.Data.DataSet> при использовании LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="b2bb4-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using LINQ to DataSet.</span></span> <span data-ttu-id="b2bb4-104">Типизированный <xref:System.Data.DataSet> — это класс, производный от <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b2bb4-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b2bb4-105">Поэтому он наследует все методы, события и свойства класса <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b2bb4-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b2bb4-106">Кроме того, типизированный <xref:System.Data.DataSet> предоставляет строго типизированные методы, события и свойства.</span><span class="sxs-lookup"><span data-stu-id="b2bb4-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="b2bb4-107">Это означает, что доступ к таблицам и столбцам можно получить по имени, не используя методы на основе коллекций.</span><span class="sxs-lookup"><span data-stu-id="b2bb4-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="b2bb4-108">Это упрощает запросы и повышает их читаемость.</span><span class="sxs-lookup"><span data-stu-id="b2bb4-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="b2bb4-109">Дополнительные сведения см. в разделе [типизированных наборов DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="b2bb4-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>

<span data-ttu-id="b2bb4-110">LINQ to DataSet также поддерживает запросы к типизированным объектам <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b2bb4-110">LINQ to DataSet also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b2bb4-111">С типизированным <xref:System.Data.DataSet>, нет необходимости использовать универсальный <xref:System.Data.DataRowExtensions.Field%2A> метод или <xref:System.Data.DataRowExtensions.SetField%2A> метод для доступа к данным столбца.</span><span class="sxs-lookup"><span data-stu-id="b2bb4-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span> <span data-ttu-id="b2bb4-112">Имена свойств доступны во время компиляции, поскольку сведения о типе в <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b2bb4-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b2bb4-113">LINQ to DataSet предоставляет доступ к значениям столбцов правильного типа, чтобы ошибки несоответствия типов обнаруживаются в том случае, во время компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b2bb4-113">LINQ to DataSet provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>

<span data-ttu-id="b2bb4-114">Перед началом при запросе типизированного <xref:System.Data.DataSet>, необходимо создать класс с помощью **конструктор наборов данных** в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b2bb4-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the **DataSet Designer** in Visual Studio.</span></span> <span data-ttu-id="b2bb4-115">Дополнительные сведения см. в разделе [создать и настроить наборы данных](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="b2bb4-115">For more information, see [Create and configure DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>

## <a name="example"></a><span data-ttu-id="b2bb4-116">Пример</span><span class="sxs-lookup"><span data-stu-id="b2bb4-116">Example</span></span>

<span data-ttu-id="b2bb4-117">В следующем примере показан запрос к типизированному объекту <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="b2bb4-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b2bb4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b2bb4-118">See also</span></span>

- [<span data-ttu-id="b2bb4-119">Запросы к DataSet</span><span class="sxs-lookup"><span data-stu-id="b2bb4-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="b2bb4-120">Запросы между таблицами</span><span class="sxs-lookup"><span data-stu-id="b2bb4-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="b2bb4-121">Запросы к одной таблице</span><span class="sxs-lookup"><span data-stu-id="b2bb4-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
