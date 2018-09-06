---
title: Копирование содержимого набора данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: b85fb6ebf56b110330be121c87d2492b0cfac536
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43804073"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="1d2b0-102">Копирование содержимого набора данных</span><span class="sxs-lookup"><span data-stu-id="1d2b0-102">Copying DataSet Contents</span></span>
<span data-ttu-id="1d2b0-103">Можно создать копию <xref:System.Data.DataSet> таким образом, можно работать с данными, не затрагивая исходные данные или работать с подмножеством данных из **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="1d2b0-104">При копировании **набора данных**, вы можете:</span><span class="sxs-lookup"><span data-stu-id="1d2b0-104">When copying a **DataSet**, you can:</span></span>  
  
-   <span data-ttu-id="1d2b0-105">Создать точную копию объекта **набора данных**, включая схему, данные, информацию о состоянии строк и версии строк.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
-   <span data-ttu-id="1d2b0-106">Создание **набора данных** , содержащий схему существующей **набора данных**, но только те строки, которые были изменены.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="1d2b0-107">Возвращает все строки, которые были изменены, также можно указать конкретный **DataRowState**.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="1d2b0-108">Дополнительные сведения о состояниях строк см. в разделе [строки состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="1d2b0-108">For more information about row states, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
-   <span data-ttu-id="1d2b0-109">Копирование схемы или реляционной структуры **набора данных** , не копируя никаких строк.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="1d2b0-110">Строки могут быть импортированы в существующий объект <xref:System.Data.DataTable> с использованием <xref:System.Data.DataTable.ImportRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="1d2b0-111">Чтобы создать точную копию объекта **набора данных** , включает в себя схему и данные, используйте <xref:System.Data.DataSet.Copy%2A> метод **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="1d2b0-112">В следующем примере кода показано, как создать точную копию объекта **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="1d2b0-113">Чтобы создать копию **набора данных** , включает в себя схему и только данные, представляющие **Added**, **Modified**, или **Deleted** строк, используйте <xref:System.Data.DataSet.GetChanges%2A> метод **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="1d2b0-114">Можно также использовать **GetChanges** для возврата только строк с указанным состоянием строки, передав **DataRowState** значение при вызове **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="1d2b0-115">В следующем примере кода показано, как передать **DataRowState** при вызове **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="1d2b0-116">Чтобы создать копию **набора данных** , включает только схему, используйте <xref:System.Data.DataSet.Clone%2A> метод **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="1d2b0-117">Можно также добавить существующие строки на клонированный **набора данных** с помощью **ImportRow** метод **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="1d2b0-118">**ImportRow** добавляет к указанной таблице данных, состояние и сведения о версии строки.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="1d2b0-119">Значения столбца добавляются только в тех случаях, если имена столбцов согласуются, а типы данных являются совместимыми.</span><span class="sxs-lookup"><span data-stu-id="1d2b0-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="1d2b0-120">В следующем примере кода создается клон **набора данных** и затем добавляет строки из исходного **набора данных** для **клиентов** в таблицу **набора данных**  клона для клиентов, где **CountryRegion** столбец имеет значение «Germany».</span><span class="sxs-lookup"><span data-stu-id="1d2b0-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1d2b0-121">См. также</span><span class="sxs-lookup"><span data-stu-id="1d2b0-121">See Also</span></span>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="1d2b0-122">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="1d2b0-122">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="1d2b0-123">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1d2b0-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
