---
title: Копирование содержимого набора данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: d8a7762c4ec5d650295ca0626180285723549051
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786516"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="30402-102">Копирование содержимого набора данных</span><span class="sxs-lookup"><span data-stu-id="30402-102">Copying DataSet Contents</span></span>
<span data-ttu-id="30402-103">Можно создать копию, <xref:System.Data.DataSet> чтобы можно было работать с данными, не затрагивая исходные данные, или работать с подмножеством данных из **набора**данных.</span><span class="sxs-lookup"><span data-stu-id="30402-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="30402-104">При копировании **набора данных**можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="30402-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="30402-105">Создайте точную копию **набора данных**, включая схему, данные, сведения о состоянии строки и версии строк.</span><span class="sxs-lookup"><span data-stu-id="30402-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="30402-106">Создайте **набор данных** , содержащий схему существующего **набора данных**, но только измененные строки.</span><span class="sxs-lookup"><span data-stu-id="30402-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="30402-107">Можно вернуть все измененные строки или указать конкретный **датаровстате**.</span><span class="sxs-lookup"><span data-stu-id="30402-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="30402-108">Дополнительные сведения о состояниях строк см. в разделе [состояния строк и версии строк](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="30402-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="30402-109">Скопируйте схему или реляционную структуру только **набора данных** без копирования каких бы то ни было строк.</span><span class="sxs-lookup"><span data-stu-id="30402-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="30402-110">Строки могут быть импортированы в существующий объект <xref:System.Data.DataTable> с использованием <xref:System.Data.DataTable.ImportRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="30402-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="30402-111">Чтобы создать точную копию **набора данных** , включающего как схему, так и данные, используйте <xref:System.Data.DataSet.Copy%2A> метод **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="30402-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="30402-112">В следующем примере кода показано, как создать точную копию **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="30402-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="30402-113">Чтобы создать копию **набора данных** , включающего схему, и только данные, представляющие **добавленные**, **измененные**или **Удаленные** строки, <xref:System.Data.DataSet.GetChanges%2A> используйте метод **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="30402-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="30402-114">Можно **также использовать функции GetRows, чтобы** возвратить только строки с указанным состоянием строки, передав значение **датаровстате** **при вызове**метода GetRows.</span><span class="sxs-lookup"><span data-stu-id="30402-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="30402-115">В следующем примере кода показано, как передать **датаровстате** при вызове методаического **изменения**.</span><span class="sxs-lookup"><span data-stu-id="30402-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="30402-116">Чтобы создать копию **набора данных** , включающего только схему, используйте <xref:System.Data.DataSet.Clone%2A> метод **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="30402-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="30402-117">Можно также добавить существующие строки в клонированный **набор данных** с помощью метода **импортров** объекта **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="30402-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="30402-118">**Импортров** добавляет данные, состояние строки и сведения о версии строки в указанную таблицу.</span><span class="sxs-lookup"><span data-stu-id="30402-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="30402-119">Значения столбца добавляются только в тех случаях, если имена столбцов согласуются, а типы данных являются совместимыми.</span><span class="sxs-lookup"><span data-stu-id="30402-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="30402-120">В следующем примере кода создается клон **набора данных** , а затем строки из исходного **набора данных** добавляются в таблицу **Customers** в клоне **набора данных** для клиентов, где столбец **страна** имеет значение "Германия ".</span><span class="sxs-lookup"><span data-stu-id="30402-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="30402-121">См. также</span><span class="sxs-lookup"><span data-stu-id="30402-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="30402-122">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="30402-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="30402-123">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="30402-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
