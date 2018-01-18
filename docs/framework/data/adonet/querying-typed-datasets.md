---
title: "Запросы к типизированным наборам данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fff678a54416e72f4be8c3fdfdcacec5a7d90af7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="querying-typed-datasets"></a><span data-ttu-id="6b124-102">Запросы к типизированным наборам данных</span><span class="sxs-lookup"><span data-stu-id="6b124-102">Querying Typed DataSets</span></span>
<span data-ttu-id="6b124-103">Если схема объекта <xref:System.Data.DataSet> известна во время разработки приложения, при создании запроса <xref:System.Data.DataSet> рекомендуется использовать типизированный объект [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b124-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="6b124-104">Типизированный <xref:System.Data.DataSet> — это класс, производный от <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6b124-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6b124-105">Поэтому он наследует все методы, события и свойства класса <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6b124-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6b124-106">Кроме того, типизированный <xref:System.Data.DataSet> предоставляет строго типизированные методы, события и свойства.</span><span class="sxs-lookup"><span data-stu-id="6b124-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="6b124-107">Это означает, что доступ к таблицам и столбцам можно получить по имени, не используя методы на основе коллекций.</span><span class="sxs-lookup"><span data-stu-id="6b124-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="6b124-108">Это упрощает запросы и повышает их читаемость.</span><span class="sxs-lookup"><span data-stu-id="6b124-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="6b124-109">Дополнительные сведения см. в разделе [типизированных наборов данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="6b124-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="6b124-110">также поддерживает запросы к типизированным объектам <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6b124-110"> also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6b124-111">С типизированным <xref:System.Data.DataSet>, нет необходимости использовать универсальный <xref:System.Data.DataRowExtensions.Field%2A> метода или <xref:System.Data.DataRowExtensions.SetField%2A> метод для доступа к данным столбца.</span><span class="sxs-lookup"><span data-stu-id="6b124-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span>  <span data-ttu-id="6b124-112">Имена свойств доступны во время компиляции, так как сведения о типе включаются в <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6b124-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="6b124-113">предоставляет доступ к значениям столбцов правильного типа, поэтому ошибки несоответствия типов выявляются при компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6b124-113"> provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>  
  
 <span data-ttu-id="6b124-114">Прежде чем направлять запросы к типизированному объекту <xref:System.Data.DataSet>, необходимо создать класс с помощью конструктора DataSet в среде [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b124-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the DataSet Designer in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].</span></span>  <span data-ttu-id="6b124-115">Дополнительные сведения см. в разделе, посвященном [созданию и настройке наборов данных](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="6b124-115">For more information, see [Create and configure datasets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b124-116">Пример</span><span class="sxs-lookup"><span data-stu-id="6b124-116">Example</span></span>  
 <span data-ttu-id="6b124-117">В следующем примере показан запрос к типизированному объекту <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="6b124-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6b124-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6b124-118">See Also</span></span>  
 [<span data-ttu-id="6b124-119">Запросы к DataSet</span><span class="sxs-lookup"><span data-stu-id="6b124-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="6b124-120">Запросы между таблицами</span><span class="sxs-lookup"><span data-stu-id="6b124-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [<span data-ttu-id="6b124-121">Запросы к одной таблице</span><span class="sxs-lookup"><span data-stu-id="6b124-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
