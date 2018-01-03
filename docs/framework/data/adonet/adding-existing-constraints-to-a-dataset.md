---
title: "Добавление существующих ограничений к набору данных"
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
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: fd760cf51aa0f3e89e49831b1aa165e62b321d20
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="ee8af-102">Добавление существующих ограничений к набору данных</span><span class="sxs-lookup"><span data-stu-id="ee8af-102">Adding Existing Constraints to a DataSet</span></span>
<span data-ttu-id="ee8af-103">**Заполнения** метод **DataAdapter** заполняет <xref:System.Data.DataSet> только со столбцами таблицы и строки из источника данных; Однако обычно устанавливают ограничения по источнику данных **заполнения** метод не добавляет эти данные схемы к **DataSet** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ee8af-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="ee8af-104">Для заполнения **DataSet** с существующие ограничения первичного ключа сведения из источника данных, можно вызвать **FillSchema** метод **DataAdapter**, или задать **MissingSchemaAction** свойство **DataAdapter** для **AddWithKey** перед вызовом **заполнения**.</span><span class="sxs-lookup"><span data-stu-id="ee8af-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="ee8af-105">Это позволит гарантировать, что первичный ключ ограничений в **DataSet** отражаются в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="ee8af-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="ee8af-106">Ограничение внешнего ключа сведения не включено и должны создаваться явно, как показано в [ограничения таблиц данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="ee8af-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="ee8af-107">Добавление сведений о схеме для **DataSet** перед заполнение данных гарантирует, что ограничений primary key включаются с <xref:System.Data.DataTable> объекты в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="ee8af-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="ee8af-108">В результате при дополнительных вызовах для заполнения **набора данных** вносятся первичном сведений о столбце ключей используется для сопоставления новых строк из источника данных с текущим строкам в каждой **DataTable**и текущие данные в таблиц перезаписываются данными из источника данных.</span><span class="sxs-lookup"><span data-stu-id="ee8af-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="ee8af-109">Без данных схемы новые строки из источника данных добавляются к **набора данных**, полученный в повторяющихся строк.</span><span class="sxs-lookup"><span data-stu-id="ee8af-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee8af-110">Если столбец в источнике данных определен как заданы с автоматическим приращением, **FillSchema** метод, или **заполнения** метод с **MissingSchemaAction** из  **AddWithKey**, создает **DataColumn** с **AutoIncrement** свойство `true`.</span><span class="sxs-lookup"><span data-stu-id="ee8af-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="ee8af-111">Тем не менее, необходимо задать **AutoIncrementStep** и **AutoIncrementSeed** значения самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="ee8af-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="ee8af-112">Дополнительные сведения о столбцах с автоматическим приращением см. в разделе [Создание столбцов AutoIncrement](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span><span class="sxs-lookup"><span data-stu-id="ee8af-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
 <span data-ttu-id="ee8af-113">С помощью **FillSchema** или параметр **MissingSchemaAction** для **AddWithKey** требует дополнительной обработки в источнике данных, чтобы определить столбец первичного ключа сведения.</span><span class="sxs-lookup"><span data-stu-id="ee8af-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="ee8af-114">Такая дополнительная обработка может снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="ee8af-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="ee8af-115">Если сведения о столбцах первичного ключа известны во время разработки, рекомендуется явно задавать столбец или столбцы первичного ключа, чтобы добиться оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="ee8af-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="ee8af-116">Сведения о явном данные первичного ключа для таблицы см. в разделе [Определение первичных ключей](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="ee8af-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="ee8af-117">В следующем примере кода показано, как добавить сведения о схеме для **DataSet** с помощью **FillSchema**.</span><span class="sxs-lookup"><span data-stu-id="ee8af-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 <span data-ttu-id="ee8af-118">В следующем примере кода показано, как добавить сведения о схеме для **DataSet** с помощью **MissingSchemaAction.AddWithKey** свойство **заполнения** метод.</span><span class="sxs-lookup"><span data-stu-id="ee8af-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="ee8af-119">Обработка нескольких результирующих наборов</span><span class="sxs-lookup"><span data-stu-id="ee8af-119">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="ee8af-120">Если **DataAdapter** обнаруживает несколько результирующих наборов, возвращенных **SelectCommand**, он создает несколько таблиц в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="ee8af-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="ee8af-121">Таблицы присваивается имя по умолчанию **таблицы** *N*, начиная с **таблицы** вместо «Table0».</span><span class="sxs-lookup"><span data-stu-id="ee8af-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="ee8af-122">Если имя таблицы передается в качестве аргумента для **FillSchema** метод, таблицам будут присваиваться с нуля добавочное имя **TableName** *N*, начиная с **TableName** вместо «TableName0».</span><span class="sxs-lookup"><span data-stu-id="ee8af-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee8af-123">Если **FillSchema** метод **OleDbDataAdapter** вызывается для команды, которая возвращает несколько результирующих наборов, возвращаются только сведения о схеме из первого результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="ee8af-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="ee8af-124">Когда данные схемы возвращаются для нескольких результирующих задает использование **OleDbDataAdapter**, рекомендуется указывать **MissingSchemaAction** из **AddWithKey** и получить сведения о схеме, при вызове **заполнения** метод.</span><span class="sxs-lookup"><span data-stu-id="ee8af-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee8af-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ee8af-125">See Also</span></span>  
 [<span data-ttu-id="ee8af-126">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="ee8af-126">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="ee8af-127">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="ee8af-127">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="ee8af-128">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ee8af-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="ee8af-129">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ee8af-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
