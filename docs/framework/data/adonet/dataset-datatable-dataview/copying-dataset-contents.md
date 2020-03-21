---
title: Копирование содержимого набора данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: de13e07eb5c19b8beffa724fec4a128c418a4fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151368"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="bef88-102">Копирование содержимого набора данных</span><span class="sxs-lookup"><span data-stu-id="bef88-102">Copying DataSet Contents</span></span>
<span data-ttu-id="bef88-103">Можно создать копию, <xref:System.Data.DataSet> чтобы работать с данными, не влияя на исходные данные, или работать с подмножеством данных из **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="bef88-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="bef88-104">При копировании **набора данных**можно:</span><span class="sxs-lookup"><span data-stu-id="bef88-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="bef88-105">Создайте точную копию **DataSet,** включая схему, данные, сведения о состоянии строк и версии строк.</span><span class="sxs-lookup"><span data-stu-id="bef88-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="bef88-106">Создайте **DataSet,** содержащий схему существующего **DataSet,** но только строки, которые были изменены.</span><span class="sxs-lookup"><span data-stu-id="bef88-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="bef88-107">Вы можете вернуть все строки, которые были изменены, или указать конкретные **DataRowState.**</span><span class="sxs-lookup"><span data-stu-id="bef88-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="bef88-108">Для получения дополнительной информации [Row States and Row Versions](row-states-and-row-versions.md)о состояниях строк см.</span><span class="sxs-lookup"><span data-stu-id="bef88-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="bef88-109">Копируйте схему, или реляционную структуру, только **DataSet,** не копируя строки.</span><span class="sxs-lookup"><span data-stu-id="bef88-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="bef88-110">Строки могут быть импортированы в существующий объект <xref:System.Data.DataTable> с использованием <xref:System.Data.DataTable.ImportRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="bef88-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="bef88-111">Чтобы создать точную копию **DataSet,** которая включает в <xref:System.Data.DataSet.Copy%2A> себя как схему, так и данные, используйте метод **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="bef88-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="bef88-112">Следующий пример кода показывает, как создать точную копию **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="bef88-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="bef88-113">Для создания копии **DataSet,** включающей схему и только данные, представляющие **добавленные,** **измененные**или **удаленные** строки, используйте <xref:System.Data.DataSet.GetChanges%2A> метод **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="bef88-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="bef88-114">Вы также можете использовать **GetChanges** для возврата только строк с указанным состоянием строки, передавая значение **DataRowState** при вызове **GetChanges.**</span><span class="sxs-lookup"><span data-stu-id="bef88-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="bef88-115">Следующий пример кода показывает, как пройти **DataRowState** при вызове **GetChanges.**</span><span class="sxs-lookup"><span data-stu-id="bef88-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 <span data-ttu-id="bef88-116">Чтобы создать копию **DataSet,** которая включает только <xref:System.Data.DataSet.Clone%2A> схему, используйте метод **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="bef88-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="bef88-117">Можно также добавить существующие строки в клонированный **DataSet** с помощью метода **ImportRow** **DataTable.**</span><span class="sxs-lookup"><span data-stu-id="bef88-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="bef88-118">**ImportRow** добавляет данные, состояние строки и информацию о строке версии в указанную таблицу.</span><span class="sxs-lookup"><span data-stu-id="bef88-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="bef88-119">Значения столбца добавляются только в тех случаях, если имена столбцов согласуются, а типы данных являются совместимыми.</span><span class="sxs-lookup"><span data-stu-id="bef88-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="bef88-120">Следующий пример кода создает клон **DataSet,** а затем добавляет строки из исходного **Набора данных** в таблицу **клиентов** в клоне **DataSet** для клиентов, где столбец **CountryRegion** имеет значение "Германия".</span><span class="sxs-lookup"><span data-stu-id="bef88-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a><span data-ttu-id="bef88-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bef88-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="bef88-122">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="bef88-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="bef88-123">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bef88-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
