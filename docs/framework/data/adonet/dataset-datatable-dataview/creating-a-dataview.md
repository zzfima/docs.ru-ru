---
title: Создание DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: b88df66ef2e065d1db8d4033eb1fb0e47ebdd189
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45994008"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="19546-102">Создание DataView</span><span class="sxs-lookup"><span data-stu-id="19546-102">Creating a DataView</span></span>
<span data-ttu-id="19546-103">Есть два способа создания представления данных <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="19546-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="19546-104">Можно использовать **DataView** конструктор, или можно создать ссылку на <xref:System.Data.DataTable.DefaultView%2A> свойство <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="19546-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="19546-105">**DataView** конструктор может быть пустым или может принимать **DataTable** как один аргумент, или **DataTable** вместе с критерии фильтрации, сортировки и строки фильтр состояния.</span><span class="sxs-lookup"><span data-stu-id="19546-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="19546-106">Дополнительные сведения о других аргументах, доступных для использования с **DataView**, см. в разделе [Сортировка и фильтрация данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="19546-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="19546-107">Так как индекс для **DataView** формируется как при **DataView** создается, а также при любой из **сортировки**, **RowFilter**, или  **RowStateFilter** изменяются свойства, для обеспечения лучшей производительности, указав любой исходный порядок сортировки или критерии фильтрации как аргументы конструктора, при создании **DataView**.</span><span class="sxs-lookup"><span data-stu-id="19546-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="19546-108">Создание **DataView** без указания критериев сортировки или фильтрации, а затем установив **сортировки**, **RowFilter**, или **RowStateFilter** свойства позже приводит к менее двукратному построению индекса: после при **DataView** создается, и еще раз при изменении каких-либо свойств сортировки или фильтрации.</span><span class="sxs-lookup"><span data-stu-id="19546-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="19546-109">Обратите внимание, что при создании **DataView** с помощью конструктора, не принимающий никаких аргументов, нельзя будет использовать **DataView** пока **таблицы** свойство .</span><span class="sxs-lookup"><span data-stu-id="19546-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="19546-110">В следующем примере кода демонстрируется создание **DataView** с помощью **DataView** конструктор.</span><span class="sxs-lookup"><span data-stu-id="19546-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="19546-111">Объект **RowFilter**, **сортировки** столбца, и **DataViewRowState** передаются вместе с **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="19546-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="19546-112">В следующем примере кода показано, как получить ссылку на значение по умолчанию **DataView** из **DataTable** с помощью **DefaultView** свойство таблицы.</span><span class="sxs-lookup"><span data-stu-id="19546-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="19546-113">См. также</span><span class="sxs-lookup"><span data-stu-id="19546-113">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="19546-114">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="19546-114">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="19546-115">Сортировка и фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="19546-115">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [<span data-ttu-id="19546-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="19546-116">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="19546-117">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="19546-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
