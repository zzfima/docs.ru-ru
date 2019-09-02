---
title: Сортировка и фильтрация данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 0907aa2a66e1bf51fefc7bed8ea2612cc0c830fa
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203228"
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="5930c-102">Сортировка и фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="5930c-102">Sorting and Filtering Data</span></span>
<span data-ttu-id="5930c-103"><xref:System.Data.DataView> предоставляет несколько способов сортировки и фильтрации данных в <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="5930c-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
- <span data-ttu-id="5930c-104">Можно использовать свойство <xref:System.Data.DataView.Sort%2A> для задания одного или нескольких порядков сортировки столбцов и включить параметры ASC (по возрастанию) и DESC (по убыванию).</span><span class="sxs-lookup"><span data-stu-id="5930c-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
- <span data-ttu-id="5930c-105">Свойство <xref:System.Data.DataView.ApplyDefaultSort%2A> служит для автоматического создания порядка сортировки по возрастанию на основании столбца или столбцов первичного ключа таблицы.</span><span class="sxs-lookup"><span data-stu-id="5930c-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="5930c-106"><xref:System.Data.DataView.ApplyDefaultSort%2A>применяется только в том случае, если свойство **Sort** является нулевой ссылкой или пустой строкой и если в таблице определен первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5930c-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
- <span data-ttu-id="5930c-107">Свойство <xref:System.Data.DataView.RowFilter%2A> можно использовать для задания подмножеств строк на основании значений их столбцов.</span><span class="sxs-lookup"><span data-stu-id="5930c-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="5930c-108">Дополнительные сведения о допустимых выражениях для свойства **RowFilter** см. в справочных сведениях по <xref:System.Data.DataColumn.Expression%2A> свойству <xref:System.Data.DataColumn> класса.</span><span class="sxs-lookup"><span data-stu-id="5930c-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="5930c-109">Если требуется возвратить результаты определенного запроса к данным, а не предоставить динамическое представление подмножества данных, используйте <xref:System.Data.DataView.Find%2A> методы или <xref:System.Data.DataView.FindRows%2A> объекта **DataView** для достижения оптимальной производительности, а не задав  **Свойство RowFilter** .</span><span class="sxs-lookup"><span data-stu-id="5930c-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="5930c-110">При установке свойства **RowFilter** перестраивается индекс данных, добавляются дополнительные затраты на приложение и снижается производительность.</span><span class="sxs-lookup"><span data-stu-id="5930c-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="5930c-111">Свойство **RowFilter** лучше использовать в приложении с привязкой к данным, в котором привязанный элемент управления отображает отфильтрованные результаты.</span><span class="sxs-lookup"><span data-stu-id="5930c-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="5930c-112">Методы **Find** и **FindRows** используют текущий индекс без необходимости перестроения индекса.</span><span class="sxs-lookup"><span data-stu-id="5930c-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="5930c-113">Дополнительные сведения о методах **Find** и **FindRows** см. в разделе [Поиск строк](finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="5930c-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](finding-rows.md).</span></span>  
  
- <span data-ttu-id="5930c-114">Свойство <xref:System.Data.DataView.RowStateFilter%2A> можно использовать для определения, какие версии строк следует просматривать.</span><span class="sxs-lookup"><span data-stu-id="5930c-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="5930c-115">Объект **DataView** неявно определяет, какая версия строки должна быть предоставлена в зависимости от **RowState** базовой строки.</span><span class="sxs-lookup"><span data-stu-id="5930c-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="5930c-116">Например, если для **RowStateFilter** задано значение **DataViewRowState. Deleted**, **DataView** отображает исходную версию строк всех **удаленных** строк, так как **Текущая** версия строки отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5930c-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="5930c-117">Вы можете определить, какая версия строки предоставляется с помощью свойства **rowversion** **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="5930c-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="5930c-118">В следующей таблице показаны параметры для **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="5930c-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="5930c-119">Параметры DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="5930c-119">DataViewRowState options</span></span>|<span data-ttu-id="5930c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5930c-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="5930c-121">**куррентровс**</span><span class="sxs-lookup"><span data-stu-id="5930c-121">**CurrentRows**</span></span>|<span data-ttu-id="5930c-122">**Текущая** версия строки всех неизмененных, добавленныхи измененных строк.</span><span class="sxs-lookup"><span data-stu-id="5930c-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="5930c-123">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5930c-123">This is the default.</span></span>|  
    |<span data-ttu-id="5930c-124">**Добавлен**</span><span class="sxs-lookup"><span data-stu-id="5930c-124">**Added**</span></span>|<span data-ttu-id="5930c-125">Версия **текущей** строки всех добавленных строк.</span><span class="sxs-lookup"><span data-stu-id="5930c-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="5930c-126">**Удаленной**</span><span class="sxs-lookup"><span data-stu-id="5930c-126">**Deleted**</span></span>|<span data-ttu-id="5930c-127">Версия **исходной** строки всех **удаленных** строк.</span><span class="sxs-lookup"><span data-stu-id="5930c-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="5930c-128">**модифиедкуррент**</span><span class="sxs-lookup"><span data-stu-id="5930c-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="5930c-129">Версия **текущей** строки для всех **измененных** строк.</span><span class="sxs-lookup"><span data-stu-id="5930c-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="5930c-130">**модифиедоригинал**</span><span class="sxs-lookup"><span data-stu-id="5930c-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="5930c-131">Версия **исходной** строки всех измененных строк.</span><span class="sxs-lookup"><span data-stu-id="5930c-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="5930c-132">**None**</span><span class="sxs-lookup"><span data-stu-id="5930c-132">**None**</span></span>|<span data-ttu-id="5930c-133">Нет строк.</span><span class="sxs-lookup"><span data-stu-id="5930c-133">No rows.</span></span>|  
    |<span data-ttu-id="5930c-134">**оригиналровс**</span><span class="sxs-lookup"><span data-stu-id="5930c-134">**OriginalRows**</span></span>|<span data-ttu-id="5930c-135">Версия **исходной** строки всех неизмененных, измененныхи **удаленных** строк.</span><span class="sxs-lookup"><span data-stu-id="5930c-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="5930c-136">**Без изменений**</span><span class="sxs-lookup"><span data-stu-id="5930c-136">**Unchanged**</span></span>|<span data-ttu-id="5930c-137">Версия **текущей** строки всех неизмененных строк.</span><span class="sxs-lookup"><span data-stu-id="5930c-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="5930c-138">Дополнительные сведения о состояниях строк и версиях строк см. в разделе [состояния строк и версии](row-states-and-row-versions.md)строк.</span><span class="sxs-lookup"><span data-stu-id="5930c-138">For more information about row states and row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="5930c-139">В следующем примере кода создается представление, которое показывает все продукты, где число элементов на складе меньше или равно уровню переупорядочения, отсортированного вначале по идентификаторам поставщиков, а затем по названиям продуктов.</span><span class="sxs-lookup"><span data-stu-id="5930c-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5930c-140">См. также</span><span class="sxs-lookup"><span data-stu-id="5930c-140">See also</span></span>

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="5930c-141">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="5930c-141">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="5930c-142">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5930c-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
