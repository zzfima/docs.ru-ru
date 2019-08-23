---
title: Добавление существующих ограничений к набору данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 05f95a9c4f250100ca97e3ab52e4073d027df1b8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932194"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="4789b-102">Добавление существующих ограничений к набору данных</span><span class="sxs-lookup"><span data-stu-id="4789b-102">Adding Existing Constraints to a DataSet</span></span>
<span data-ttu-id="4789b-103">Метод **Fill** объекта **DataAdapter** заполняет объект <xref:System.Data.DataSet> только столбцами таблицы и строками из источника данных. Хотя ограничения обычно задаются источником данных, метод **Fill** не добавляет эти сведения о схеме в элемент  **Набор данных** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4789b-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="4789b-104">Чтобы заполнить **набор** данных существующими сведениями об ограничениях первичного ключа из источника данных, можно либо вызвать метод **FillSchema** объекта **DataAdapter**, либо задать свойство **миссингсчемаактион** объекта **DataAdapter** . до **аддвискэй** перед вызовом **Fill**.</span><span class="sxs-lookup"><span data-stu-id="4789b-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="4789b-105">Это обеспечит, чтобы ограничения первичного ключа в **наборе** данных отражали значения в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="4789b-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="4789b-106">Сведения об ограничениях внешнего ключа не включаются и должны создаваться явным образом, как показано в разделе [ограничения DataTable](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="4789b-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="4789b-107">Добавление сведений о схеме в **набор** данных перед их заполнением данными гарантирует, что ограничения первичного ключа будут <xref:System.Data.DataTable> включены в объекты в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="4789b-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="4789b-108">В результате, когда создаются дополнительные вызовы для заполнения **набора** данных, сведения о первичном ключевом столбце используются для сопоставления новых строк из источника данных с текущими строками в каждой **таблице DataTable**, а текущие данные в таблицах перезаписываются данными из Источник данных.</span><span class="sxs-lookup"><span data-stu-id="4789b-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="4789b-109">Без сведений о схеме новые строки из источника данных добавляются к набору данных, чтоприводит к дублированию строк.</span><span class="sxs-lookup"><span data-stu-id="4789b-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4789b-110">Если столбец в источнике данных определен как автоматически увеличивающийся, метод **FillSchema** или метод **Fill** с **миссингсчемаактион** **Аддвискэй**, создает **DataColumn** со свойством **AutoIncrement** . Задайте для `true`значение.</span><span class="sxs-lookup"><span data-stu-id="4789b-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="4789b-111">Тем не менее, необходимо задать значения **аутоинкрементстеп** и **аутоинкрементсид** самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="4789b-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="4789b-112">Дополнительные сведения о столбцах с автоматическим приращением см. в разделе [Создание столбцов](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)с автоувеличением.</span><span class="sxs-lookup"><span data-stu-id="4789b-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
 <span data-ttu-id="4789b-113">Использование **FillSchema** или присвоение параметру **миссингсчемаактион** значения **аддвискэй** требует дополнительной обработки в источнике данных для определения сведений о первичном ключевом столбце.</span><span class="sxs-lookup"><span data-stu-id="4789b-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="4789b-114">Такая дополнительная обработка может снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="4789b-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="4789b-115">Если сведения о столбцах первичного ключа известны во время разработки, рекомендуется явно задавать столбец или столбцы первичного ключа, чтобы добиться оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="4789b-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="4789b-116">Сведения о явном задании сведений о первичном ключе для таблицы см. в разделе [Определение первичных ключей](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="4789b-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="4789b-117">В следующем примере кода показано, как добавить сведения о схеме в **набор данных** с помощью **FillSchema**.</span><span class="sxs-lookup"><span data-stu-id="4789b-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**.</span></span>  
  
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
  
 <span data-ttu-id="4789b-118">В следующем примере кода показано, как добавить сведения о схеме в **набор данных** с помощью свойства **миссингсчемаактион. аддвискэй** метода **Fill** .</span><span class="sxs-lookup"><span data-stu-id="4789b-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method.</span></span>  
  
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
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="4789b-119">Обработка нескольких результирующих наборов</span><span class="sxs-lookup"><span data-stu-id="4789b-119">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="4789b-120">Если объект **DataAdapter** обнаруживает несколько результирующих наборов, возвращенных из **SelectCommand**, он создает несколько таблиц в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="4789b-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="4789b-121">Таблицам будет присвоено отсчитываемое от нуля имя по умолчанию **таблицы** *N*, начинающееся с **Table** вместо «Table0».</span><span class="sxs-lookup"><span data-stu-id="4789b-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="4789b-122">Если имя таблицы передается в качестве аргумента в метод **FillSchema** , то таблицам будет присвоено отсчитываемое от нуля имя **TableName** *N*, начинающееся с **TableName** вместо "TableName0".</span><span class="sxs-lookup"><span data-stu-id="4789b-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4789b-123">Если метод **FillSchema** объекта **OleDbDataAdapter** вызывается для команды, возвращающей несколько результирующих наборов, возвращается только информация о схеме из первого результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="4789b-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="4789b-124">При возврате сведений о схеме для нескольких результирующих наборов с помощью **OleDbDataAdapter**рекомендуется указать **миссингсчемаактион** **аддвискэй** и получить сведения о схеме при вызове **Fill** . Method.</span><span class="sxs-lookup"><span data-stu-id="4789b-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4789b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="4789b-125">See also</span></span>

- [<span data-ttu-id="4789b-126">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="4789b-126">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="4789b-127">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="4789b-127">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="4789b-128">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4789b-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="4789b-129">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4789b-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
