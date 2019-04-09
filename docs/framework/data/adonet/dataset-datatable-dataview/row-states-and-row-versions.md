---
title: Состояния и версии строк
ms.date: 07/19/2018
dev_langs:
- csharp
- vb
ms.assetid: 2e6642c9-bfc6-425c-b3a7-e4912ffa6c1f
ms.openlocfilehash: 83147c3f9d70434f5c8dd34e2e56f44f71adc53d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092907"
---
# <a name="row-states-and-row-versions"></a><span data-ttu-id="01cc2-102">Состояния и версии строк</span><span class="sxs-lookup"><span data-stu-id="01cc2-102">Row States and Row Versions</span></span>
<span data-ttu-id="01cc2-103">ADO.NET управляет строками таблиц с помощью состояний и версий строк.</span><span class="sxs-lookup"><span data-stu-id="01cc2-103">ADO.NET manages rows in tables using row states and versions.</span></span> <span data-ttu-id="01cc2-104">Состояние строки указывает на статус строки, а версии строк хранят значения изменения строки, включая текущее, исходное и применяемое по умолчанию значения.</span><span class="sxs-lookup"><span data-stu-id="01cc2-104">A row state indicates the status of a row; row versions maintain the values stored in a row as it is modified, including current, original, and default values.</span></span> <span data-ttu-id="01cc2-105">Например, после внесения изменения в столбец строки эта строка будет иметь состояние `Modified` и две версии: `Current`, содержащую текущие значения, и `Original`, содержащую значения этой строки до изменения столбца.</span><span class="sxs-lookup"><span data-stu-id="01cc2-105">For example, after you have made a modification to a column in a row, the row will have a row state of `Modified`, and two row versions: `Current`, which contains the current row values, and `Original`, which contains the row values before the column was modified.</span></span>  
  
 <span data-ttu-id="01cc2-106">Каждый объект <xref:System.Data.DataRow> имеет свойство <xref:System.Data.DataRow.RowState%2A>, которое отображает текущее состояние строки.</span><span class="sxs-lookup"><span data-stu-id="01cc2-106">Each <xref:System.Data.DataRow> object has a <xref:System.Data.DataRow.RowState%2A> property that you can examine to determine the current state of the row.</span></span> <span data-ttu-id="01cc2-107">В следующей таблице кратко описано каждое из значений перечисления `RowState`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-107">The following table gives a brief description of each `RowState` enumeration value.</span></span>  
  
|<span data-ttu-id="01cc2-108">Значение перечисления RowState</span><span class="sxs-lookup"><span data-stu-id="01cc2-108">RowState value</span></span>|<span data-ttu-id="01cc2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="01cc2-109">Description</span></span>|  
|--------------------|-----------------|  
|<xref:System.Data.DataRowState.Unchanged>|<span data-ttu-id="01cc2-110">Не было выполнено никаких изменений с момента последнего вызова метода `AcceptChanges` или с момента создания строки методом `DataAdapter.Fill`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-110">No changes have been made since the last call to `AcceptChanges` or since the row was created by `DataAdapter.Fill`.</span></span>|  
|<xref:System.Data.DataRowState.Added>|<span data-ttu-id="01cc2-111">Строка добавлена к таблице, но метод `AcceptChanges` не вызывался.</span><span class="sxs-lookup"><span data-stu-id="01cc2-111">The row has been added to the table, but `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Modified>|<span data-ttu-id="01cc2-112">Изменены некоторые элементы строки.</span><span class="sxs-lookup"><span data-stu-id="01cc2-112">Some element of the row has been changed.</span></span>|  
|<xref:System.Data.DataRowState.Deleted>|<span data-ttu-id="01cc2-113">Строка удалена из таблицы, но метод `AcceptChanges` не вызывался.</span><span class="sxs-lookup"><span data-stu-id="01cc2-113">The row has been deleted from a table, and `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Detached>|<span data-ttu-id="01cc2-114">Строка не принадлежит ни к одной коллекции `DataRowCollection`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-114">The row is not part of any `DataRowCollection`.</span></span> <span data-ttu-id="01cc2-115">Свойство `RowState` только что созданной строки имеет значение `Detached`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-115">The `RowState` of a newly created row is set to `Detached`.</span></span> <span data-ttu-id="01cc2-116">После добавления новой строки `DataRow` к коллекции `DataRowCollection` с помощью вызова метода `Add` свойству `RowState` присваивается значение `Added`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-116">After the new `DataRow` is added to the `DataRowCollection` by calling the `Add` method, the value of the `RowState` property is set to `Added`.</span></span><br /><br /> `Detached` <span data-ttu-id="01cc2-117">также имеет значение для строки, который был удален из `DataRowCollection` с помощью `Remove` метод, или с помощью `Delete` метода, за которым следует `AcceptChanges` метод.</span><span class="sxs-lookup"><span data-stu-id="01cc2-117">is also set for a row that has been removed from a `DataRowCollection` using the `Remove` method, or by the `Delete` method followed by the `AcceptChanges` method.</span></span>|  
  
 <span data-ttu-id="01cc2-118">Если метод `AcceptChanges` вызывается для <xref:System.Data.DataSet>, <xref:System.Data.DataTable> или <xref:System.Data.DataRow>, удаляются все строки со значением состояния `Deleted`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-118">When `AcceptChanges` is called on a <xref:System.Data.DataSet>, <xref:System.Data.DataTable> , or <xref:System.Data.DataRow>, all rows with a row state of `Deleted` are removed.</span></span> <span data-ttu-id="01cc2-119">Оставшимся строкам присваивается состояние `Unchanged`, а значения в версии строки `Original` перезаписываются значениями версии строки `Current`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-119">The remaining rows are given a row state of `Unchanged`, and the values in the `Original` row version are overwritten with the `Current` row version values.</span></span> <span data-ttu-id="01cc2-120">Если вызывается метод `RejectChanges`, удаляются все строки со значением состояния `Added`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-120">When `RejectChanges` is called, all rows with a row state of `Added` are removed.</span></span> <span data-ttu-id="01cc2-121">Оставшимся строкам присваивается состояние `Unchanged`, а значения в версии строки `Current` перезаписываются значениями версии строки `Original`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-121">The remaining rows are given a row state of `Unchanged`, and the values in the `Current` row version are overwritten with the `Original` row version values.</span></span>  
  
 <span data-ttu-id="01cc2-122">Можно просматривать разные версии строки, передавая параметр <xref:System.Data.DataRowVersion> со ссылкой на столбец, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="01cc2-122">You can view the different row versions of a row by passing a <xref:System.Data.DataRowVersion> parameter with the column reference, as shown in the following example.</span></span>  
  
```vb  
Dim custRow As DataRow = custTable.Rows(0)  
Dim custID As String = custRow("CustomerID", DataRowVersion.Original).ToString()  
```  
  
```csharp  
DataRow custRow = custTable.Rows[0];  
string custID = custRow["CustomerID", DataRowVersion.Original].ToString();  
```  
  
 <span data-ttu-id="01cc2-123">В следующей таблице кратко описано каждое из значений перечисления `DataRowVersion`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-123">The following table gives a brief description of each `DataRowVersion` enumeration value.</span></span>  
  
|<span data-ttu-id="01cc2-124">Значение DataRowVersion</span><span class="sxs-lookup"><span data-stu-id="01cc2-124">DataRowVersion value</span></span>|<span data-ttu-id="01cc2-125">Описание</span><span class="sxs-lookup"><span data-stu-id="01cc2-125">Description</span></span>|  
|--------------------------|-----------------|  
|<xref:System.Data.DataRowVersion.Current>|<span data-ttu-id="01cc2-126">Текущие значения строки.</span><span class="sxs-lookup"><span data-stu-id="01cc2-126">The current values for the row.</span></span> <span data-ttu-id="01cc2-127">Эта версия не существует для строк, у которых `RowState` равно `Deleted`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-127">This row version does not exist for rows with a `RowState` of `Deleted`.</span></span>|  
|<xref:System.Data.DataRowVersion.Default>|<span data-ttu-id="01cc2-128">Версия по умолчанию для конкретной строки.</span><span class="sxs-lookup"><span data-stu-id="01cc2-128">The default row version for a particular row.</span></span> <span data-ttu-id="01cc2-129">Версия по умолчанию для строки `Added`, `Modified` и `Deleted` представляет собой `Current`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-129">The default row version for an `Added`, `Modified`, or `Deleted` row is `Current`.</span></span> <span data-ttu-id="01cc2-130">Версия по умолчанию для строки `Detached` - `Proposed`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-130">The default row version for a `Detached` row is `Proposed`.</span></span>|  
|<xref:System.Data.DataRowVersion.Original>|<span data-ttu-id="01cc2-131">Исходные значения строки.</span><span class="sxs-lookup"><span data-stu-id="01cc2-131">The original values for the row.</span></span> <span data-ttu-id="01cc2-132">Эта версия не существует для строк, у которых `RowState` равно `Added`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-132">This row version does not exist for rows with a `RowState` of `Added`.</span></span>|  
|<xref:System.Data.DataRowVersion.Proposed>|<span data-ttu-id="01cc2-133">Предложенные значения строки.</span><span class="sxs-lookup"><span data-stu-id="01cc2-133">The proposed values for the row.</span></span> <span data-ttu-id="01cc2-134">Эта версия строки существует в течение операции изменения строки или для строки, не содержащейся в коллекции `DataRowCollection`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-134">This row version exists during an edit operation on a row, or for a row that is not part of a `DataRowCollection`.</span></span>|  
  
 <span data-ttu-id="01cc2-135">Можно проверить, имеет ли `DataRow` конкретную версию строки, вызвав метод <xref:System.Data.DataRow.HasVersion%2A> и передав ему `DataRowVersion` в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="01cc2-135">You can test whether a `DataRow` has a particular row version by calling the <xref:System.Data.DataRow.HasVersion%2A> method and passing a `DataRowVersion` as an argument.</span></span> <span data-ttu-id="01cc2-136">Например, `DataRow.HasVersion(DataRowVersion.Original)` возвратит значение `false` для только что добавленных строк перед тем, как был вызван метод `AcceptChanges`.</span><span class="sxs-lookup"><span data-stu-id="01cc2-136">For example, `DataRow.HasVersion(DataRowVersion.Original)` will return `false` for newly added rows before `AcceptChanges` has been called.</span></span>  
  
 <span data-ttu-id="01cc2-137">В следующем примере кода показаны значения во всех удаленных строках таблицы.</span><span class="sxs-lookup"><span data-stu-id="01cc2-137">The following code example displays the values in all the deleted rows of a table.</span></span> `Deleted` <span data-ttu-id="01cc2-138">Нет строк `Current` версию строки, поэтому необходимо передать `DataRowVersion.Original` при доступе к значениям столбцов.</span><span class="sxs-lookup"><span data-stu-id="01cc2-138">rows do not have a `Current` row version, so you must pass `DataRowVersion.Original` when accessing the column values.</span></span>  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
  
Dim delRows() As DataRow = catTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
Console.WriteLine("Deleted rows:" & vbCrLf)  
  
Dim catCol As DataColumn  
Dim delRow As DataRow  
  
For Each catCol In catTable.Columns  
  Console.Write(catCol.ColumnName & vbTab)  
Next  
Console.WriteLine()  
  
For Each delRow In delRows  
  For Each catCol In catTable.Columns  
    Console.Write(delRow(catCol, DataRowVersion.Original) & vbTab)  
  Next  
  Console.WriteLine()  
Next  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
  
DataRow[] delRows = catTable.Select(null, null, DataViewRowState.Deleted);  
  
Console.WriteLine("Deleted rows:\n");  
  
foreach (DataColumn catCol in catTable.Columns)  
  Console.Write(catCol.ColumnName + "\t");  
Console.WriteLine();  
  
foreach (DataRow delRow in delRows)  
{  
  foreach (DataColumn catCol in catTable.Columns)  
    Console.Write(delRow[catCol, DataRowVersion.Original] + "\t");  
  Console.WriteLine();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="01cc2-139">См. также</span><span class="sxs-lookup"><span data-stu-id="01cc2-139">See also</span></span>

- [<span data-ttu-id="01cc2-140">Управление данными в таблице данных</span><span class="sxs-lookup"><span data-stu-id="01cc2-140">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="01cc2-141">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="01cc2-141">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="01cc2-142">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="01cc2-142">DataAdapters and DataReaders</span></span>](../../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="01cc2-143">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="01cc2-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
