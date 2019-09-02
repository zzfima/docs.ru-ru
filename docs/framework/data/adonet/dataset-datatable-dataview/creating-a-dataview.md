---
title: Создание DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 391c071f19149e9690c9121b1094aef5bfa605cd
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203841"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="c9d0a-102">Создание DataView</span><span class="sxs-lookup"><span data-stu-id="c9d0a-102">Creating a DataView</span></span>
<span data-ttu-id="c9d0a-103">Есть два способа создания представления данных <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="c9d0a-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="c9d0a-104">Можно использовать конструктор **DataView** или можно создать ссылку на <xref:System.Data.DataTable.DefaultView%2A> свойство объекта. <xref:System.Data.DataTable></span><span class="sxs-lookup"><span data-stu-id="c9d0a-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="c9d0a-105">Конструктор **DataView** может быть пустым или может принимать либо **DataTable** в виде одного аргумента, либо **DataTable** вместе с условиями фильтра, критерием сортировки и фильтром состояния строки.</span><span class="sxs-lookup"><span data-stu-id="c9d0a-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="c9d0a-106">Дополнительные сведения о дополнительных аргументах, доступных для использования с **DataView**, см. в разделе [Сортировка и фильтрация данных](sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="c9d0a-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="c9d0a-107">Поскольку индекс для **объекта DataView** строится как при создании **DataView** , так и при изменении любого из свойств **Sort**, **RowFilter**или **RowStateFilter** , достижение лучшей производительности достигается за счет предоставления всех начальных порядок сортировки или критерий фильтрации в качестве аргументов конструктора при создании **DataView**.</span><span class="sxs-lookup"><span data-stu-id="c9d0a-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="c9d0a-108">Создание **объекта DataView** без указания условия сортировки или фильтра, а затем Установка **свойств Sort**, **RowFilter**или **RowStateFilter** в дальнейшем приводит к тому, что индекс будет построен по крайней мере дважды: один раз, когда **DataView** создаются и снова при изменении любого свойства сортировки или фильтрации.</span><span class="sxs-lookup"><span data-stu-id="c9d0a-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="c9d0a-109">Обратите внимание, что при создании **DataView** с помощью конструктора, который не принимает никаких аргументов, вы не сможете использовать **DataView** до тех пор, пока не будет задано свойство **Table** .</span><span class="sxs-lookup"><span data-stu-id="c9d0a-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="c9d0a-110">В следующем примере кода показано, как создать объект **DataView** с помощью конструктора **DataView** .</span><span class="sxs-lookup"><span data-stu-id="c9d0a-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="c9d0a-111">**RowFilter**, столбец **сортировки** и **DataViewRowState** предоставляются вместе с таблицей данных.</span><span class="sxs-lookup"><span data-stu-id="c9d0a-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="c9d0a-112">В следующем примере кода показано, как получить ссылку на **представление DataView** по умолчанию объекта **DataTable** с помощью свойства **DefaultView** таблицы.</span><span class="sxs-lookup"><span data-stu-id="c9d0a-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9d0a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c9d0a-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="c9d0a-114">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="c9d0a-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="c9d0a-115">Сортировка и фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="c9d0a-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="c9d0a-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="c9d0a-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="c9d0a-117">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9d0a-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
