---
title: Просмотр данных в таблице данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: ea92b8a5e46bdaa8e94756cd28a3fbcb2789d7b3
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204392"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="f17c3-102">Просмотр данных в таблице данных</span><span class="sxs-lookup"><span data-stu-id="f17c3-102">Viewing Data in a DataTable</span></span>

<span data-ttu-id="f17c3-103">Доступ <xref:System.Data.DataTable> к содержимому объекта можно получить с помощью коллекций **Rows** и **Columns** **таблицы DataTable**.</span><span class="sxs-lookup"><span data-stu-id="f17c3-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="f17c3-104">Также можно использовать <xref:System.Data.DataTable.Select%2A> метод, чтобы возвращать подмножества данных в **DataTable** в соответствии с критериями, в том числе критериями поиска, порядком сортировки и состоянием строк.</span><span class="sxs-lookup"><span data-stu-id="f17c3-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="f17c3-105">Кроме того, можно использовать <xref:System.Data.DataRowCollection.Find%2A> метод **датаровколлектион** при поиске определенной строки с помощью значения первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="f17c3-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>

<span data-ttu-id="f17c3-106">Метод **SELECT** объекта **DataTable** возвращает набор <xref:System.Data.DataRow> объектов, соответствующих указанным критериям.</span><span class="sxs-lookup"><span data-stu-id="f17c3-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="f17c3-107">**SELECT** принимает необязательные аргументы критерия фильтра, выражения сортировки и **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="f17c3-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="f17c3-108">Выражение фильтра определяет, какие строки должны возвращаться на основе значений **DataColumn** , таких как `LastName = 'Smith'`.</span><span class="sxs-lookup"><span data-stu-id="f17c3-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="f17c3-109">Выражение сортировки следует стандартным соглашениям SQL об упорядочивании столбцов, например по `LastName ASC, FirstName ASC`.</span><span class="sxs-lookup"><span data-stu-id="f17c3-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="f17c3-110">Правила написания выражений см. в <xref:System.Data.DataColumn.Expression%2A> описании свойства класса **DataColumn** .</span><span class="sxs-lookup"><span data-stu-id="f17c3-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>

> [!TIP]
> <span data-ttu-id="f17c3-111">При выполнении нескольких вызовов к методу **SELECT** объекта **DataTable**можно повысить производительность, создавая <xref:System.Data.DataView> для **таблицы DataTable**.</span><span class="sxs-lookup"><span data-stu-id="f17c3-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="f17c3-112">При создании объект **DataView** индексирует строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="f17c3-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="f17c3-113">Затем метод **SELECT** использует этот индекс, что значительно сокращает время создания результата запроса.</span><span class="sxs-lookup"><span data-stu-id="f17c3-113">The **Select** method then uses that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="f17c3-114">Дополнительные сведения о создании **DataView** для **DataTable**см. в разделе « [представления](dataviews.md)данных».</span><span class="sxs-lookup"><span data-stu-id="f17c3-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](dataviews.md).</span></span>

<span data-ttu-id="f17c3-115">Метод **SELECT** определяет версию строк для просмотра или управления на основе <xref:System.Data.DataViewRowState>.</span><span class="sxs-lookup"><span data-stu-id="f17c3-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="f17c3-116">В следующей таблице описаны возможные значения перечисления **DataViewRowState** .</span><span class="sxs-lookup"><span data-stu-id="f17c3-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>

|<span data-ttu-id="f17c3-117">Значение DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="f17c3-117">DataViewRowState value</span></span>|<span data-ttu-id="f17c3-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f17c3-118">Description</span></span>|
|----------------------------|-----------------|
|<span data-ttu-id="f17c3-119">**куррентровс**</span><span class="sxs-lookup"><span data-stu-id="f17c3-119">**CurrentRows**</span></span>|<span data-ttu-id="f17c3-120">Текущие строки, включая не изменившиеся, добавленные и измененные.</span><span class="sxs-lookup"><span data-stu-id="f17c3-120">Current rows including unchanged, added, and modified rows.</span></span>|
|<span data-ttu-id="f17c3-121">**Удаленной**</span><span class="sxs-lookup"><span data-stu-id="f17c3-121">**Deleted**</span></span>|<span data-ttu-id="f17c3-122">Удаленная строка.</span><span class="sxs-lookup"><span data-stu-id="f17c3-122">A deleted row.</span></span>|
|<span data-ttu-id="f17c3-123">**модифиедкуррент**</span><span class="sxs-lookup"><span data-stu-id="f17c3-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="f17c3-124">Текущая версия, которая является измененной версией исходных данных.</span><span class="sxs-lookup"><span data-stu-id="f17c3-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="f17c3-125">(См. **модифиедоригинал**.)</span><span class="sxs-lookup"><span data-stu-id="f17c3-125">(See **ModifiedOriginal**.)</span></span>|
|<span data-ttu-id="f17c3-126">**модифиедоригинал**</span><span class="sxs-lookup"><span data-stu-id="f17c3-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="f17c3-127">Исходная версия всех измененных строк.</span><span class="sxs-lookup"><span data-stu-id="f17c3-127">The original version of all modified rows.</span></span> <span data-ttu-id="f17c3-128">Текущая версия доступна с помощью **модифиедкуррент**.</span><span class="sxs-lookup"><span data-stu-id="f17c3-128">The current version is available using **ModifiedCurrent**.</span></span>|
|<span data-ttu-id="f17c3-129">**Добавлен**</span><span class="sxs-lookup"><span data-stu-id="f17c3-129">**Added**</span></span>|<span data-ttu-id="f17c3-130">Новая строка.</span><span class="sxs-lookup"><span data-stu-id="f17c3-130">A new row.</span></span>|
|<span data-ttu-id="f17c3-131">**None**</span><span class="sxs-lookup"><span data-stu-id="f17c3-131">**None**</span></span>|<span data-ttu-id="f17c3-132">Нет.</span><span class="sxs-lookup"><span data-stu-id="f17c3-132">None.</span></span>|
|<span data-ttu-id="f17c3-133">**оригиналровс**</span><span class="sxs-lookup"><span data-stu-id="f17c3-133">**OriginalRows**</span></span>|<span data-ttu-id="f17c3-134">Исходные строки, включая неизменившиеся и удаленные.</span><span class="sxs-lookup"><span data-stu-id="f17c3-134">Original rows, including unchanged and deleted rows.</span></span>|
|<span data-ttu-id="f17c3-135">**Без изменений**</span><span class="sxs-lookup"><span data-stu-id="f17c3-135">**Unchanged**</span></span>|<span data-ttu-id="f17c3-136">Неизменившаяся строка.</span><span class="sxs-lookup"><span data-stu-id="f17c3-136">An unchanged row.</span></span>|

<span data-ttu-id="f17c3-137">В следующем примере объект **DataSet** фильтруется так, что вы работаете только со строками, для которых для **DataViewRowState** задано значение **куррентровс**.</span><span class="sxs-lookup"><span data-stu-id="f17c3-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>

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

<span data-ttu-id="f17c3-138">Метод **SELECT** можно использовать для возврата строк с разными значениями **RowState** или значениями полей.</span><span class="sxs-lookup"><span data-stu-id="f17c3-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="f17c3-139">В следующем примере возвращается массив **DataRow** , который ссылается на все удаленные строки, и возвращается другой массив **DataRow** , который ссылается на все строки, упорядоченные по **кустлнаме**, где столбец **CustID** больше 5.</span><span class="sxs-lookup"><span data-stu-id="f17c3-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="f17c3-140">Сведения о просмотре сведений в **удаленной** строке см. в разделе [состояния строк и версии строк](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="f17c3-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f17c3-141">См. также</span><span class="sxs-lookup"><span data-stu-id="f17c3-141">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [<span data-ttu-id="f17c3-142">Управление данными в DataTable</span><span class="sxs-lookup"><span data-stu-id="f17c3-142">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="f17c3-143">Состояния и версии строк</span><span class="sxs-lookup"><span data-stu-id="f17c3-143">Row States and Row Versions</span></span>](row-states-and-row-versions.md)
- [<span data-ttu-id="f17c3-144">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f17c3-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
