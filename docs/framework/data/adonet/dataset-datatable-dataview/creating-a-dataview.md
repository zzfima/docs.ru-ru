---
title: "Создание DataView"
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
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 53cbfc5097c28c0677a164f817cfe14927814d75
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-dataview"></a><span data-ttu-id="70055-102">Создание DataView</span><span class="sxs-lookup"><span data-stu-id="70055-102">Creating a DataView</span></span>
<span data-ttu-id="70055-103">Есть два способа создания представления данных <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="70055-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="70055-104">Можно использовать **DataView** конструктору, или вы можете создать ссылку на <xref:System.Data.DataTable.DefaultView%2A> свойство <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="70055-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="70055-105">**DataView** конструктор может быть пустым либо может принимать **DataTable** как один аргумент или **DataTable** вместе с критериями фильтрации, сортировки и строки фильтр состояния.</span><span class="sxs-lookup"><span data-stu-id="70055-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="70055-106">Дополнительные сведения о дополнительных аргументов для использования с **DataView**, в разделе [Сортировка и фильтрация данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="70055-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="70055-107">Так как индекс для **DataView** формируется как при **DataView** создается и если какие-либо **сортировки**, **RowFilter**, или  **RowStateFilter** свойства изменяются, добиться лучшей производительности, указав любой исходный порядок сортировки или критерии фильтрации как аргументы конструктора, при создании **DataView**.</span><span class="sxs-lookup"><span data-stu-id="70055-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="70055-108">Создание **DataView** без указания критериев сортировки и фильтрации, а затем установить **сортировки**, **RowFilter**, или **RowStateFilter** свойства позже приводит индекса для создания по крайней мере дважды: после при **DataView** создается, и снова при любого из свойств сортировки или фильтрации, будут изменены.</span><span class="sxs-lookup"><span data-stu-id="70055-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="70055-109">Обратите внимание, что при создании **DataView** с помощью конструктора, который не принимает никаких аргументов, нельзя будет использовать **DataView** пока **таблицы** свойство .</span><span class="sxs-lookup"><span data-stu-id="70055-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="70055-110">В следующем примере кода показано, как создать **DataView** с помощью **DataView** конструктор.</span><span class="sxs-lookup"><span data-stu-id="70055-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="70055-111">Объект **RowFilter**, **сортировки** столбца, и **DataViewRowState** передаются вместе с **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="70055-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 <span data-ttu-id="70055-112">В следующем примере кода показано, как получить ссылку на значение по умолчанию **DataView** из **DataTable** с помощью **DefaultView** свойство таблицы.</span><span class="sxs-lookup"><span data-stu-id="70055-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="70055-113">См. также</span><span class="sxs-lookup"><span data-stu-id="70055-113">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="70055-114">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="70055-114">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="70055-115">Сортировка и фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="70055-115">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [<span data-ttu-id="70055-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="70055-116">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="70055-117">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="70055-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
