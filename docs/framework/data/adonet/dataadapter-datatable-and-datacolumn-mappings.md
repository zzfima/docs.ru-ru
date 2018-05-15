---
title: Сопоставления DataAdapter DataTable и DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 1b426dbcdc78ecfddeac003616993849ce60b89c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="b39b9-102">Сопоставления DataAdapter DataTable и DataColumn</span><span class="sxs-lookup"><span data-stu-id="b39b9-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="b39b9-103">Объект **DataAdapter** содержит коллекцию из нуля или более <xref:System.Data.Common.DataTableMapping> объекты в его **TableMappings** свойство.</span><span class="sxs-lookup"><span data-stu-id="b39b9-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="b39b9-104">Объект **DataTableMapping** обеспечивает основное сопоставление между данными, возвращаемыми из запроса к источнику данных и <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="b39b9-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="b39b9-105">**DataTableMapping** может быть передано вместо **DataTable** в **заполнения** метод **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="b39b9-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="b39b9-106">В следующем примере создается **DataTableMapping** с именем **AuthorsMapping** для **авторы** таблицы.</span><span class="sxs-lookup"><span data-stu-id="b39b9-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="b39b9-107">Объект **DataTableMapping** позволяет использовать имена столбцов в **DataTable** , отличаются от таковых в базе данных.</span><span class="sxs-lookup"><span data-stu-id="b39b9-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="b39b9-108">**DataAdapter** это сопоставление используется для согласования столбцов при обновлении таблицы.</span><span class="sxs-lookup"><span data-stu-id="b39b9-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="b39b9-109">Если вы не укажете **TableName** или **DataTableMapping** при вызове **заполнения** или **обновление** метод  **DataAdapter**, **DataAdapter** ищет **DataTableMapping** с именем «Table».</span><span class="sxs-lookup"><span data-stu-id="b39b9-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="b39b9-110">Если данный **DataTableMapping** не существует, **TableName** из **DataTable** является «Table».</span><span class="sxs-lookup"><span data-stu-id="b39b9-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="b39b9-111">Можно задать значение по умолчанию **DataTableMapping** путем создания **DataTableMapping** с именем «Table».</span><span class="sxs-lookup"><span data-stu-id="b39b9-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="b39b9-112">В следующем примере кода создается **DataTableMapping** (из <xref:System.Data.Common> пространство имен) и делает его сопоставление по умолчанию для указанного **DataAdapter** путем присваивания ему имени «Table».</span><span class="sxs-lookup"><span data-stu-id="b39b9-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="b39b9-113">Этом примере производится сопоставление столбцов из первой таблицы, в результате запроса ( **клиентов** таблицу **Northwind** базы данных) в набор более понятные имена в **Northwind Customers**  в таблицу <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b39b9-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b39b9-114">Для столбцов, к которым не применяется сопоставление, используются имена столбцов из источника данных.</span><span class="sxs-lookup"><span data-stu-id="b39b9-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 <span data-ttu-id="b39b9-115">В более сложных ситуациях может быть принято решение, то же **DataAdapter** должен поддерживать загрузку разных таблиц с различными сопоставлениями.</span><span class="sxs-lookup"><span data-stu-id="b39b9-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="b39b9-116">Чтобы сделать это, просто добавьте дополнительные **DataTableMapping** объектов.</span><span class="sxs-lookup"><span data-stu-id="b39b9-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="b39b9-117">Когда **заполнения** методу передается экземпляр **набора данных** и **DataTableMapping** имя, если сопоставление с таким именем существует, он используется, в противном случае —  **DataTable** с, используется имя.</span><span class="sxs-lookup"><span data-stu-id="b39b9-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="b39b9-118">В следующих примерах создаются **DataTableMapping** с именем **клиентов** и **DataTable** имя **BizTalkSchema**.</span><span class="sxs-lookup"><span data-stu-id="b39b9-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="b39b9-119">Пример сопоставляет строк, возвращаемых инструкцией SELECT для **BizTalkSchema** **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="b39b9-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
>  <span data-ttu-id="b39b9-120">Если имя исходного столбца не задано для сопоставления столбцов, или имя исходной таблицы не задано для сопоставления таблиц, то автоматически создаются имена, применяемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b39b9-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="b39b9-121">Если ни один исходный столбец предоставляется для сопоставления столбцов, сопоставлению столбцов присваивается имя по умолчанию **SourceColumn** *N,* начиная с **Исходныйстолбец1**.</span><span class="sxs-lookup"><span data-stu-id="b39b9-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="b39b9-122">Если для сопоставления таблиц не указано имя таблицы источника, сопоставлению таблиц присваивается имя по умолчанию **SourceTable** *N*, начиная с **Исходнаятаблица1**.</span><span class="sxs-lookup"><span data-stu-id="b39b9-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b39b9-123">Мы рекомендуем избегать именования **SourceColumn** *N* для сопоставления столбцов, или **SourceTable** *N* для таблицы сопоставление, поскольку указывается имя может конфликтовать с существующим именем столбца сопоставление по умолчанию в **ColumnMappingCollection** или имя таблицы сопоставления в **DataTableMappingCollection** .</span><span class="sxs-lookup"><span data-stu-id="b39b9-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="b39b9-124">Если указанное имя уже существует, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="b39b9-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="b39b9-125">Обработка нескольких результирующих наборов</span><span class="sxs-lookup"><span data-stu-id="b39b9-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="b39b9-126">Если ваш **SelectCommand** возвращает несколько таблиц **заполнения** автоматически формирует имена таблиц с добавочные значения для таблиц в **набора данных**, начиная с Указанное имя таблицы и продолжение на в форме **TableName** *N*, начиная с **TableName1**.</span><span class="sxs-lookup"><span data-stu-id="b39b9-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="b39b9-127">Можно использовать сопоставления таблиц для сопоставления автоматически создаваемого имени таблицы с именем, которое требуется задать для таблицы в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="b39b9-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="b39b9-128">Например, для **SelectCommand** , возвращает две таблицы **клиентов** и **заказов**, выполните следующий вызов **заполнения**.</span><span class="sxs-lookup"><span data-stu-id="b39b9-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 <span data-ttu-id="b39b9-129">Будут созданы две таблицы в **DataSet**: **клиентов** и **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="b39b9-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="b39b9-130">Можно использовать сопоставления таблиц, чтобы убедиться, что вторая таблица называется **заказов** вместо **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="b39b9-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="b39b9-131">Чтобы сделать это, сопоставить исходную таблицу из **Customers1** для **набора данных** таблицы **заказов**, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b39b9-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a><span data-ttu-id="b39b9-132">См. также</span><span class="sxs-lookup"><span data-stu-id="b39b9-132">See Also</span></span>  
 [<span data-ttu-id="b39b9-133">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="b39b9-133">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="b39b9-134">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b39b9-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="b39b9-135">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b39b9-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
