---
title: Навигация по отношениям DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: f4dfccad23bf5d15f5cbd0a33e76a136417e13ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607268"
---
# <a name="navigating-datarelations"></a><span data-ttu-id="0be39-102">Навигация по отношениям DataRelation</span><span class="sxs-lookup"><span data-stu-id="0be39-102">Navigating DataRelations</span></span>
<span data-ttu-id="0be39-103">Одно из основных назначений объекта <xref:System.Data.DataRelation> состоит в обеспечении переходов от одного объекта <xref:System.Data.DataTable> к другому в пределах <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0be39-103">One of the primary functions of a <xref:System.Data.DataRelation> is to allow navigation from one <xref:System.Data.DataTable> to another within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0be39-104">Это позволяет получить все связанные <xref:System.Data.DataRow> объектов в одном **DataTable** при указании единственного **DataRow** из связанной **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="0be39-104">This allows you to retrieve all the related <xref:System.Data.DataRow> objects in one **DataTable** when given a single **DataRow** from a related **DataTable**.</span></span> <span data-ttu-id="0be39-105">Например, после установки **DataRelation** между таблицей заказчиков и таблицей заказов, можно получить все строки заказов для конкретного клиента строки с помощью **GetChildRows**.</span><span class="sxs-lookup"><span data-stu-id="0be39-105">For example, after establishing a **DataRelation** between a table of customers and a table of orders, you can retrieve all the order rows for a particular customer row using **GetChildRows**.</span></span>  
  
 <span data-ttu-id="0be39-106">В следующем примере кода создается **DataRelation** между **клиентов** таблицы и **заказы** таблицы **набора данных** и возвращает все заказы для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="0be39-106">The following code example creates a **DataRelation** between the **Customers** table and the **Orders** table of a **DataSet** and returns all the orders for each customer.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 <span data-ttu-id="0be39-107">Следующий пример основан на предыдущем примере; в нем четыре таблицы связываются друг с другом и происходит переход по этим связям.</span><span class="sxs-lookup"><span data-stu-id="0be39-107">The next example builds on the preceding example, relating four tables together and navigating those relationships.</span></span> <span data-ttu-id="0be39-108">Как показано в предыдущем примере **CustomerID** относится **клиентов** таблицы **заказы** таблицы.</span><span class="sxs-lookup"><span data-stu-id="0be39-108">As in the previous example, **CustomerID** relates the **Customers** table to the **Orders** table.</span></span> <span data-ttu-id="0be39-109">Для каждого клиента в **клиентов** таблицы, все дочерние строки в **заказы** определяются таблицы, для возврата числа заказов конкретного заказчика и их **OrderID** значения.</span><span class="sxs-lookup"><span data-stu-id="0be39-109">For each customer in the **Customers** table, all the child rows in the **Orders** table are determined, in order to return the number of orders a particular customer has and their **OrderID** values.</span></span>  
  
 <span data-ttu-id="0be39-110">Расширенный пример возвращает значения из **OrderDetails** и **продуктов** таблиц.</span><span class="sxs-lookup"><span data-stu-id="0be39-110">The expanded example also returns the values from the **OrderDetails** and **Products** tables.</span></span> <span data-ttu-id="0be39-111">**Заказы** таблица связана с **OrderDetails** таблицу с помощью **OrderID** чтобы определить, для каждого клиентского заказа, какие товары и количества были заказаны.</span><span class="sxs-lookup"><span data-stu-id="0be39-111">The **Orders** table is related to the **OrderDetails** table using **OrderID** to determine, for each customer order, what products and quantities were ordered.</span></span> <span data-ttu-id="0be39-112">Так как **OrderDetails** таблицы содержит только **ProductID** каждого заказанного продукта, **OrderDetails** связана с **продуктов** с помощью **ProductID** для возвращения **ProductName**.</span><span class="sxs-lookup"><span data-stu-id="0be39-112">Because the **OrderDetails** table only contains the **ProductID** of an ordered product, **OrderDetails** is related to **Products** using **ProductID** in order to return the **ProductName**.</span></span> <span data-ttu-id="0be39-113">В этой связи **продуктов** таблицы является родительским и **Order Details** таблицы является дочерним элементом.</span><span class="sxs-lookup"><span data-stu-id="0be39-113">In this relation, the **Products** table is the parent and the **Order Details** table is the child.</span></span> <span data-ttu-id="0be39-114">В результате во время итерации внутри **OrderDetails** таблицы, **GetParentRow** вызывается для получения связанного **ProductName** значение.</span><span class="sxs-lookup"><span data-stu-id="0be39-114">As a result, when iterating through the **OrderDetails** table, **GetParentRow** is called to retrieve the related **ProductName** value.</span></span>  
  
 <span data-ttu-id="0be39-115">Обратите внимание, что при **DataRelation** создается для **клиентов** и **заказы** таблицы, значение не указано для **createConstraints**флаг (по умолчанию используется **true**).</span><span class="sxs-lookup"><span data-stu-id="0be39-115">Notice that when the **DataRelation** is created for the **Customers** and **Orders** tables, no value is specified for the **createConstraints** flag (the default is **true**).</span></span> <span data-ttu-id="0be39-116">Это предполагает, что все строки в **заказы** таблица имеет **CustomerID** значение, которое существует в родительском объекте **клиентов** таблицы.</span><span class="sxs-lookup"><span data-stu-id="0be39-116">This assumes that all the rows in the **Orders** table have a **CustomerID** value that exists in the parent **Customers** table.</span></span> <span data-ttu-id="0be39-117">Если **CustomerID** существует в **заказы** таблицу, которая не существует в **клиентов** таблицы, <xref:System.Data.ForeignKeyConstraint> приводит к возникновению исключения, исключение.</span><span class="sxs-lookup"><span data-stu-id="0be39-117">If a **CustomerID** exists in the **Orders** table that does not exist in the **Customers** table, a <xref:System.Data.ForeignKeyConstraint> causes an exception to be thrown.</span></span>  
  
 <span data-ttu-id="0be39-118">Когда дочерний столбец может содержать значения, которые не содержит родительский столбец, задайте **createConstraints** флаг **false** при добавлении **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="0be39-118">When the child column might contain values that the parent column does not contain, set the **createConstraints** flag to **false** when adding the **DataRelation**.</span></span> <span data-ttu-id="0be39-119">В примере **createConstraints** флаг имеет значение **false** для **DataRelation** между **заказы** таблицы и  **OrderDetails** таблицы.</span><span class="sxs-lookup"><span data-stu-id="0be39-119">In the example, the **createConstraints** flag is set to **false** for the **DataRelation** between the **Orders** table and the **OrderDetails** table.</span></span> <span data-ttu-id="0be39-120">Это позволяет приложению вернуть все записи из **OrderDetails** таблицы и только подмножество записей из **заказы** таблицы без формирования исключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0be39-120">This enables the application to return all the records from the **OrderDetails** table and only a subset of records from the **Orders** table without generating a run-time exception.</span></span> <span data-ttu-id="0be39-121">В этом расширенном образце вывод формируется в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="0be39-121">The expanded sample generates output in the following format.</span></span>  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 <span data-ttu-id="0be39-122">В следующем примере кода представляет собой расширенный образец где значения из **OrderDetails** и **продуктов** возвращаются таблицы с набором записей в **заказы**таблицы.</span><span class="sxs-lookup"><span data-stu-id="0be39-122">The following code example is an expanded sample where the values from the **OrderDetails** and **Products** tables are returned, with only a subset of the records in the **Orders** table being returned.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0be39-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0be39-123">See also</span></span>

- [<span data-ttu-id="0be39-124">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="0be39-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="0be39-125">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0be39-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
