---
title: "Сортировка и фильтрация данных"
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
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f514095e551967928d610451cfcaa9a829c0989f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="14fe8-102">Сортировка и фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="14fe8-102">Sorting and Filtering Data</span></span>
<span data-ttu-id="14fe8-103"><xref:System.Data.DataView> предоставляет несколько способов сортировки и фильтрации данных в <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="14fe8-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
-   <span data-ttu-id="14fe8-104">Можно использовать свойство <xref:System.Data.DataView.Sort%2A> для задания одного или нескольких порядков сортировки столбцов и включить параметры ASC (по возрастанию) и DESC (по убыванию).</span><span class="sxs-lookup"><span data-stu-id="14fe8-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
-   <span data-ttu-id="14fe8-105">Свойство <xref:System.Data.DataView.ApplyDefaultSort%2A> служит для автоматического создания порядка сортировки по возрастанию на основании столбца или столбцов первичного ключа таблицы.</span><span class="sxs-lookup"><span data-stu-id="14fe8-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="14fe8-106"><xref:System.Data.DataView.ApplyDefaultSort%2A>применяется, только если **сортировки** свойство является пустой ссылкой или пустой строкой, и если таблица имеет первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="14fe8-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
-   <span data-ttu-id="14fe8-107">Свойство <xref:System.Data.DataView.RowFilter%2A> можно использовать для задания подмножеств строк на основании значений их столбцов.</span><span class="sxs-lookup"><span data-stu-id="14fe8-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="14fe8-108">Дополнительные сведения о допустимых выражениях для **RowFilter** свойства, см. Справочные сведения по <xref:System.Data.DataColumn.Expression%2A> свойство <xref:System.Data.DataColumn> класса.</span><span class="sxs-lookup"><span data-stu-id="14fe8-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="14fe8-109">Если вы хотите вернуть результаты определенного запроса данных, а не динамическое представление подмножества данных, используйте <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> методы **DataView** для достижения наилучшей производительности вместо Установка **RowFilter** свойство.</span><span class="sxs-lookup"><span data-stu-id="14fe8-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="14fe8-110">Установка **RowFilter** перестраивается индекс данных, что добавляет нагрузку на приложение и снижает производительность.</span><span class="sxs-lookup"><span data-stu-id="14fe8-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="14fe8-111">**RowFilter** свойство лучше всего использовать в приложении с привязкой к данным где элемент связывания отображает отфильтрованные результаты.</span><span class="sxs-lookup"><span data-stu-id="14fe8-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="14fe8-112">**Найти** и **FindRows** методы используют текущий индекс, не требуя его перестроения.</span><span class="sxs-lookup"><span data-stu-id="14fe8-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="14fe8-113">Дополнительные сведения о **найти** и **FindRows** методов, см. [поиск строки](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="14fe8-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span></span>  
  
-   <span data-ttu-id="14fe8-114">Свойство <xref:System.Data.DataView.RowStateFilter%2A> можно использовать для определения, какие версии строк следует просматривать.</span><span class="sxs-lookup"><span data-stu-id="14fe8-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="14fe8-115">**DataView** неявно регулирует Выбор версии строк для предоставления зависимости **RowState** базовой строки.</span><span class="sxs-lookup"><span data-stu-id="14fe8-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="14fe8-116">Например если **RowStateFilter** равно **DataViewRowState.Deleted**, **DataView** предоставляет **исходного** версии строк все **Deleted** строк, так как отсутствует не **текущей** версию строки.</span><span class="sxs-lookup"><span data-stu-id="14fe8-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="14fe8-117">Можно определить, какие версии строки предоставляется с использованием **RowVersion** свойство **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="14fe8-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="14fe8-118">В следующей таблице показаны параметры для **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="14fe8-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="14fe8-119">Параметры DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="14fe8-119">DataViewRowState options</span></span>|<span data-ttu-id="14fe8-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="14fe8-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="14fe8-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="14fe8-121">**CurrentRows**</span></span>|<span data-ttu-id="14fe8-122">**Текущей** из всех **Unchanged**, **Added**, и **Modified** строк.</span><span class="sxs-lookup"><span data-stu-id="14fe8-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="14fe8-123">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="14fe8-123">This is the default.</span></span>|  
    |<span data-ttu-id="14fe8-124">**Добавить**</span><span class="sxs-lookup"><span data-stu-id="14fe8-124">**Added**</span></span>|<span data-ttu-id="14fe8-125">**Текущей** из всех **Added** строк.</span><span class="sxs-lookup"><span data-stu-id="14fe8-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="14fe8-126">**Удален**</span><span class="sxs-lookup"><span data-stu-id="14fe8-126">**Deleted**</span></span>|<span data-ttu-id="14fe8-127">**Исходного** из всех **Deleted** строк.</span><span class="sxs-lookup"><span data-stu-id="14fe8-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="14fe8-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="14fe8-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="14fe8-129">**Текущей** из всех **Modified** строк.</span><span class="sxs-lookup"><span data-stu-id="14fe8-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="14fe8-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="14fe8-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="14fe8-131">**Исходного** из всех **Modified** строк.</span><span class="sxs-lookup"><span data-stu-id="14fe8-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="14fe8-132">**None**</span><span class="sxs-lookup"><span data-stu-id="14fe8-132">**None**</span></span>|<span data-ttu-id="14fe8-133">Нет строк.</span><span class="sxs-lookup"><span data-stu-id="14fe8-133">No rows.</span></span>|  
    |<span data-ttu-id="14fe8-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="14fe8-134">**OriginalRows**</span></span>|<span data-ttu-id="14fe8-135">**Исходного** из всех **Unchanged**, **Modified**, и **Deleted** строк.</span><span class="sxs-lookup"><span data-stu-id="14fe8-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="14fe8-136">**Без изменений**</span><span class="sxs-lookup"><span data-stu-id="14fe8-136">**Unchanged**</span></span>|<span data-ttu-id="14fe8-137">**Текущей** из всех **Unchanged** строк.</span><span class="sxs-lookup"><span data-stu-id="14fe8-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="14fe8-138">Дополнительные сведения о состояниях и версиях строк см. в разделе [состояния строк и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="14fe8-138">For more information about row states and row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="14fe8-139">В следующем примере кода создается представление, которое показывает все продукты, где число элементов на складе меньше или равно уровню переупорядочения, отсортированного вначале по идентификаторам поставщиков, а затем по названиям продуктов.</span><span class="sxs-lookup"><span data-stu-id="14fe8-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a><span data-ttu-id="14fe8-140">См. также</span><span class="sxs-lookup"><span data-stu-id="14fe8-140">See Also</span></span>  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="14fe8-141">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="14fe8-141">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="14fe8-142">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="14fe8-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
