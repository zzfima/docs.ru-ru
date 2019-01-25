---
title: Просмотр данных в таблице данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: 6c6f5f277689ba43590b106f3c78826e07911e87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602667"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="06530-102">Просмотр данных в таблице данных</span><span class="sxs-lookup"><span data-stu-id="06530-102">Viewing Data in a DataTable</span></span>
<span data-ttu-id="06530-103">Можно получить содержимое из <xref:System.Data.DataTable> с помощью **строк** и **столбцы** коллекции **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="06530-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="06530-104">Можно также использовать <xref:System.Data.DataTable.Select%2A> метод для возврата подмножества данных в **DataTable** в соответствии с условиями поиска, порядок сортировки и состоянием строк.</span><span class="sxs-lookup"><span data-stu-id="06530-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="06530-105">Кроме того, можно использовать <xref:System.Data.DataRowCollection.Find%2A> метод **DataRowCollection** при поиске конкретной строки, используя значение первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="06530-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>  
  
 <span data-ttu-id="06530-106">**Выберите** метод **DataTable** объект возвращает набор <xref:System.Data.DataRow> объектов, соответствующих указанным критериям.</span><span class="sxs-lookup"><span data-stu-id="06530-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="06530-107">**Выберите** принимает необязательные аргументы критерия фильтра, выражение сортировки, и **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="06530-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="06530-108">Критерий фильтра определяет возвращаемые на основе строки **DataColumn** значения, такие как `LastName = 'Smith'`.</span><span class="sxs-lookup"><span data-stu-id="06530-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="06530-109">Выражение сортировки следует стандартным соглашениям SQL об упорядочивании столбцов, например по `LastName ASC, FirstName ASC`.</span><span class="sxs-lookup"><span data-stu-id="06530-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="06530-110">Правила написания выражений, см. в разделе <xref:System.Data.DataColumn.Expression%2A> свойство **DataColumn** класса.</span><span class="sxs-lookup"><span data-stu-id="06530-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="06530-111">Если выполняется несколько вызовов **выберите** метод **DataTable**, можно повысить производительность, сначала создавая <xref:System.Data.DataView> для **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="06530-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="06530-112">Создание **DataView** индексируются строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="06530-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="06530-113">**Выберите** метод, а затем использует этот индекс, значительно сокращает время для создания результата запроса.</span><span class="sxs-lookup"><span data-stu-id="06530-113">The **Select** method then usees that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="06530-114">Сведения о создании **DataView** для **DataTable**, см. в разделе [объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span><span class="sxs-lookup"><span data-stu-id="06530-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>  
  
 <span data-ttu-id="06530-115">**Выберите** метод определяет, какую версию строк нужно просмотреть или обработать, на основе <xref:System.Data.DataViewRowState>.</span><span class="sxs-lookup"><span data-stu-id="06530-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="06530-116">В следующей таблице описаны возможные **DataViewRowState** значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="06530-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>  
  
|<span data-ttu-id="06530-117">Значение DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="06530-117">DataViewRowState value</span></span>|<span data-ttu-id="06530-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="06530-118">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="06530-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="06530-119">**CurrentRows**</span></span>|<span data-ttu-id="06530-120">Текущие строки, включая не изменившиеся, добавленные и измененные.</span><span class="sxs-lookup"><span data-stu-id="06530-120">Current rows including unchanged, added, and modified rows.</span></span>|  
|<span data-ttu-id="06530-121">**Удален**</span><span class="sxs-lookup"><span data-stu-id="06530-121">**Deleted**</span></span>|<span data-ttu-id="06530-122">Удаленная строка.</span><span class="sxs-lookup"><span data-stu-id="06530-122">A deleted row.</span></span>|  
|<span data-ttu-id="06530-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="06530-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="06530-124">Текущая версия, которая является измененной версией исходных данных.</span><span class="sxs-lookup"><span data-stu-id="06530-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="06530-125">(См. в разделе **ModifiedOriginal**.)</span><span class="sxs-lookup"><span data-stu-id="06530-125">(See **ModifiedOriginal**.)</span></span>|  
|<span data-ttu-id="06530-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="06530-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="06530-127">Исходная версия всех измененных строк.</span><span class="sxs-lookup"><span data-stu-id="06530-127">The original version of all modified rows.</span></span> <span data-ttu-id="06530-128">Текущая версия — доступно при использовании **ModifiedCurrent**.</span><span class="sxs-lookup"><span data-stu-id="06530-128">The current version is available using **ModifiedCurrent**.</span></span>|  
|<span data-ttu-id="06530-129">**Добавлен**</span><span class="sxs-lookup"><span data-stu-id="06530-129">**Added**</span></span>|<span data-ttu-id="06530-130">Новая строка.</span><span class="sxs-lookup"><span data-stu-id="06530-130">A new row.</span></span>|  
|<span data-ttu-id="06530-131">**None**</span><span class="sxs-lookup"><span data-stu-id="06530-131">**None**</span></span>|<span data-ttu-id="06530-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="06530-132">None.</span></span>|  
|<span data-ttu-id="06530-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="06530-133">**OriginalRows**</span></span>|<span data-ttu-id="06530-134">Исходные строки, включая неизменившиеся и удаленные.</span><span class="sxs-lookup"><span data-stu-id="06530-134">Original rows, including unchanged and deleted rows.</span></span>|  
|<span data-ttu-id="06530-135">**без изменений**</span><span class="sxs-lookup"><span data-stu-id="06530-135">**Unchanged**</span></span>|<span data-ttu-id="06530-136">Неизменившаяся строка.</span><span class="sxs-lookup"><span data-stu-id="06530-136">An unchanged row.</span></span>|  
  
 <span data-ttu-id="06530-137">В следующем примере **набора данных** фильтруется таким образом, необходимо работать только со строками, **DataViewRowState** присваивается **CurrentRows**.</span><span class="sxs-lookup"><span data-stu-id="06530-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>  
  
```vb  
Dim column As DataColumn  
Dim row As DataRow  
  
Dim currentRows() As DataRow = _  
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)  
  
If (currentRows.Length < 1 ) Then  
  Console.WriteLine("No Current Rows Found")  
Else  
  For Each column in workTable.Columns  
    Console.Write(vbTab & column.ColumnName)  
  Next  
  
  Console.WriteLine(vbTab & "RowState")  
  
  For Each row In currentRows  
    For Each column In workTable.Columns  
      Console.Write(vbTab & row(column).ToString())  
    Next  
  
    Dim rowState As String = _  
        System.Enum.GetName(row.RowState.GetType(), row.RowState)  
    Console.WriteLine(vbTab & rowState)  
  Next  
End If  
```  
  
```csharp  
DataRow[] currentRows = workTable.Select(  
    null, null, DataViewRowState.CurrentRows);  
  
if (currentRows.Length < 1 )  
  Console.WriteLine("No Current Rows Found");  
else  
{  
  foreach (DataColumn column in workTable.Columns)  
    Console.Write("\t{0}", column.ColumnName);  
  
  Console.WriteLine("\tRowState");  
  
  foreach (DataRow row in currentRows)  
  {  
    foreach (DataColumn column in workTable.Columns)  
      Console.Write("\t{0}", row[column]);  
  
    Console.WriteLine("\t" + row.RowState);  
  }  
}  
```  
  
 <span data-ttu-id="06530-138">**Выберите** метод может использоваться для возвращения строк с разными **RowState** или значениями полей.</span><span class="sxs-lookup"><span data-stu-id="06530-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="06530-139">В следующем примере возвращается **DataRow** массив, который ссылается на все строки, которые были удалены и возвращает другой **DataRow** массив, который ссылается на все строки, упорядоченные по **CustLName**, где **CustID** столбца больше, чем 5.</span><span class="sxs-lookup"><span data-stu-id="06530-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="06530-140">Сведения о том, как просмотреть сведения в **Deleted** строк, см. в разделе [строки состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="06530-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
```vb  
' Retrieve all deleted rows.  
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
' Retrieve rows where CustID > 5, and order by CustLName.  
Dim custRows() As DataRow = workTable.Select( _  
    "CustID > 5", "CustLName ASC")  
```  
  
```csharp  
// Retrieve all deleted rows.  
DataRow[] deletedRows = workTable.Select(  
    null, null, DataViewRowState.Deleted);  
  
// Retrieve rows where CustID > 5, and order by CustLName.  
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");  
```  
  
## <a name="see-also"></a><span data-ttu-id="06530-141">См. также</span><span class="sxs-lookup"><span data-stu-id="06530-141">See also</span></span>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [<span data-ttu-id="06530-142">Управление данными в DataTable</span><span class="sxs-lookup"><span data-stu-id="06530-142">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="06530-143">Состояния и версии строк</span><span class="sxs-lookup"><span data-stu-id="06530-143">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)
- [<span data-ttu-id="06530-144">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="06530-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
