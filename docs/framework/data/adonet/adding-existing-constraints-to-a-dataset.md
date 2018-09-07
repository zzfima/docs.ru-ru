---
title: Добавление существующих ограничений к набору данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 90aa1e5dceb3cac87d330837496b9dc467dc1876
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44064206"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="4c087-102">Добавление существующих ограничений к набору данных</span><span class="sxs-lookup"><span data-stu-id="4c087-102">Adding Existing Constraints to a DataSet</span></span>
<span data-ttu-id="4c087-103">**Заполнения** метод **DataAdapter** заполняет <xref:System.Data.DataSet> только со столбцами таблицы и строки из источника данных; Однако обычно устанавливают ограничения источником данных, **заполнения** метод не добавляет эти данные схемы к **набора данных** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4c087-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="4c087-104">Для заполнения **набора данных** сведениями о существующие ограничения первичного ключа из источника данных, можно вызвать метод **FillSchema** метод **DataAdapter**, или задать **MissingSchemaAction** свойство **DataAdapter** для **AddWithKey** перед вызовом **заполнения**.</span><span class="sxs-lookup"><span data-stu-id="4c087-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="4c087-105">Это позволит гарантировать, что первичный ключ ограничения в **набора данных** отражаются в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="4c087-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="4c087-106">Ограничение внешнего ключа сведения не включается и нужно создавать явно, как показано в [ограничения таблиц данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="4c087-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="4c087-107">Добавление сведений о схеме для **набора данных** прежде, чем заполнение данных гарантирует, что ограничения первичного ключа входят в состав <xref:System.Data.DataTable> объекты в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="4c087-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="4c087-108">В результате при дополнительных вызовах для заполнения **набора данных** вносятся основной сведения о ключевом столбце используется для проверки соответствия новых строк из источника данных текущим строкам в каждом **DataTable**и текущие данные в таблиц перезаписываются данными из источника данных.</span><span class="sxs-lookup"><span data-stu-id="4c087-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="4c087-109">Без данных схемы новые строки из источника данных, добавляются к **набора данных**, полученный в повторяющихся строк.</span><span class="sxs-lookup"><span data-stu-id="4c087-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c087-110">Если столбец в источнике данных определен как заданы с автоматическим приращением, **FillSchema** метод, или **заполнения** метод с **MissingSchemaAction** из  **AddWithKey**, создает **DataColumn** с **AutoIncrement** свойство значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4c087-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="4c087-111">Тем не менее, вам потребуется задать **AutoIncrementStep** и **AutoIncrementSeed** значения самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="4c087-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="4c087-112">Дополнительные сведения о столбцах автоприращения см. в разделе [Создание столбцов AutoIncrement](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span><span class="sxs-lookup"><span data-stu-id="4c087-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
 <span data-ttu-id="4c087-113">С помощью **FillSchema** или параметр **MissingSchemaAction** для **AddWithKey** требует дополнительной обработки в источнике данных, чтобы определить столбец первичного ключа сведения.</span><span class="sxs-lookup"><span data-stu-id="4c087-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="4c087-114">Такая дополнительная обработка может снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="4c087-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="4c087-115">Если сведения о столбцах первичного ключа известны во время разработки, рекомендуется явно задавать столбец или столбцы первичного ключа, чтобы добиться оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="4c087-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="4c087-116">Сведения о явном задании сведения о первичном ключе таблицы, см. в разделе [Определение первичных ключей](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="4c087-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="4c087-117">В следующем примере кода показано, как добавить сведения о схеме для **набора данных** с помощью **FillSchema**.</span><span class="sxs-lookup"><span data-stu-id="4c087-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**.</span></span>  
  
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
  
 <span data-ttu-id="4c087-118">В следующем примере кода показано, как добавить сведения о схеме для **набора данных** с помощью **MissingSchemaAction.AddWithKey** свойство **заполнения** метод.</span><span class="sxs-lookup"><span data-stu-id="4c087-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method.</span></span>  
  
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
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="4c087-119">Обработка нескольких результирующих наборов</span><span class="sxs-lookup"><span data-stu-id="4c087-119">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="4c087-120">Если **DataAdapter** обнаруживает несколько результирующих наборов, возвращенных **SelectCommand**, он создаст несколько таблиц в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="4c087-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="4c087-121">Таблицы, получает имя по умолчанию **таблицы** *N*, начиная с **таблицы** вместо «Table0».</span><span class="sxs-lookup"><span data-stu-id="4c087-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="4c087-122">Если имя таблицы передается в качестве аргумента для **FillSchema** метода таблиц Получает отсчитываемый от нуля добавочное имя **TableName** *N*, начиная с **TableName** вместо «TableName0».</span><span class="sxs-lookup"><span data-stu-id="4c087-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c087-123">Если **FillSchema** метод **OleDbDataAdapter** объекта вызывается для команды, которая возвращает несколько результирующих наборов, возвращаются только сведения о схеме из первого результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="4c087-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="4c087-124">Если данные схемы возвращаются для нескольких результирующих наборов с помощью **OleDbDataAdapter**, рекомендуется указывать **MissingSchemaAction** из **AddWithKey** и получить сведения о схеме, при вызове **заполнения** метод.</span><span class="sxs-lookup"><span data-stu-id="4c087-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c087-125">См. также</span><span class="sxs-lookup"><span data-stu-id="4c087-125">See Also</span></span>  
 [<span data-ttu-id="4c087-126">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="4c087-126">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="4c087-127">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="4c087-127">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="4c087-128">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4c087-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="4c087-129">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4c087-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
