---
title: Создание DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151342"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="ede64-102">Создание DataView</span><span class="sxs-lookup"><span data-stu-id="ede64-102">Creating a DataView</span></span>
<span data-ttu-id="ede64-103">Есть два способа создания представления данных <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="ede64-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="ede64-104">Вы можете использовать конструктор **DataView,** или вы можете <xref:System.Data.DataTable.DefaultView%2A> создать <xref:System.Data.DataTable>ссылку на свойство .</span><span class="sxs-lookup"><span data-stu-id="ede64-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="ede64-105">Конструктор **DataView** может быть пустым, или он может принять либо **DataTable** в качестве одного аргумента, либо **DataTable** вместе с критериями фильтра, критериями сортировки и фильтром состояния строки.</span><span class="sxs-lookup"><span data-stu-id="ede64-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="ede64-106">Для получения дополнительной информации о дополнительных аргументах, доступных для использования в **DataView,** [см.](sorting-and-filtering-data.md)</span><span class="sxs-lookup"><span data-stu-id="ede64-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="ede64-107">Поскольку индекс **DataView** создается как при создании **DataView,** так и при изменении свойств **Sort,** **RowFilter**или **RowStateFilter,** вы достигаете наилучшей производительности, предоставляя какой-либо первоначальный порядок сортировки или критерии фильтрации в качестве аргументов конструктора при создании **DataView.**</span><span class="sxs-lookup"><span data-stu-id="ede64-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="ede64-108">Создание **DataView** без указания критериев сортировки или фильтра, а затем настройки свойств **Sort,** **RowFilter**или **RowStateFilter** позже приводит к тому, что индекс будет построен по крайней мере дважды: один раз при создании **DataView** и снова, когда какие-либо свойства сортировки или фильтра изменяются.</span><span class="sxs-lookup"><span data-stu-id="ede64-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="ede64-109">Обратите внимание, что если вы создаете **DataView** с помощью конструктора, который не принимает никаких аргументов, вы не сможете использовать **DataView,** пока не установите свойство **таблицы.**</span><span class="sxs-lookup"><span data-stu-id="ede64-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="ede64-110">Следующий пример кода показывает, как создать **DataView** с помощью конструктора **DataView.**</span><span class="sxs-lookup"><span data-stu-id="ede64-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="ede64-111">**СтрокаФильтр,** **Колонка сортировки** и **DataViewRowState** поставляются вместе с **DataTable.**</span><span class="sxs-lookup"><span data-stu-id="ede64-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="ede64-112">Следующий пример кода показывает, как получить ссылку на **DataView DataView** **DataTable** с помощью свойства **таблицы DefaultView.**</span><span class="sxs-lookup"><span data-stu-id="ede64-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="ede64-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ede64-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="ede64-114">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="ede64-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="ede64-115">Сортировка и фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="ede64-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="ede64-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="ede64-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="ede64-117">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ede64-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
