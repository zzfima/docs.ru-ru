---
title: Сопоставления DataAdapter DataTable и DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: a9c81c8554c0fb393c10ed69f84c8b2d936ec1e6
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040126"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="d973e-102">Сопоставления DataAdapter DataTable и DataColumn</span><span class="sxs-lookup"><span data-stu-id="d973e-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="d973e-103">Объект **DataAdapter** содержит коллекцию из нуля или более <xref:System.Data.Common.DataTableMapping> объектов в своем свойстве **TableMappings** .</span><span class="sxs-lookup"><span data-stu-id="d973e-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="d973e-104">**Экземпляр DataTableMapping** предоставляет основное сопоставление данных, возвращенных запросом к источнику данных, и <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="d973e-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="d973e-105">Имя **экземпляр DataTableMapping** может быть передано вместо имени **DataTable** в метод **Fill** объекта **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="d973e-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="d973e-106">В следующем примере создается **экземпляр DataTableMapping** с именем **Аусорсмаппинг** для таблицы **authors** .</span><span class="sxs-lookup"><span data-stu-id="d973e-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="d973e-107">**Экземпляр DataTableMapping** позволяет использовать имена столбцов в **DataTable** , которые отличаются от имен в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d973e-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="d973e-108">Объект **DataAdapter** использует сопоставление для сопоставления столбцов при обновлении таблицы.</span><span class="sxs-lookup"><span data-stu-id="d973e-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="d973e-109">Если не указать имя **TableName** или **экземпляр DataTableMapping** при вызове метода **Fill** или **Update** объекта **DataAdapter**, то **DataAdapter** ищет **экземпляр DataTableMapping** с именем Table.</span><span class="sxs-lookup"><span data-stu-id="d973e-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="d973e-110">Если этот **экземпляр DataTableMapping** не существует, то **TableName** объекта **DataTable** имеет значение Table.</span><span class="sxs-lookup"><span data-stu-id="d973e-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="d973e-111">Можно указать **экземпляр DataTableMapping** по умолчанию, создав **экземпляр DataTableMapping** с именем "Table".</span><span class="sxs-lookup"><span data-stu-id="d973e-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="d973e-112">Следующий пример кода создает **экземпляр DataTableMapping** (из пространства имен <xref:System.Data.Common>) и делает его сопоставлением по умолчанию для указанного **объекта DataAdapter** , присваивая ему имя "Table".</span><span class="sxs-lookup"><span data-stu-id="d973e-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="d973e-113">Затем в примере сопоставляются столбцы из первой таблицы в результатах запроса (таблица **Customers** базы данных **Northwind** ) с набором более понятных имен пользователей в таблице **"Customers"** в <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="d973e-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d973e-114">Для столбцов, к которым не применяется сопоставление, используются имена столбцов из источника данных.</span><span class="sxs-lookup"><span data-stu-id="d973e-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
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
  
 <span data-ttu-id="d973e-115">В более сложных ситуациях может потребоваться, чтобы один и тот же **DataAdapter** поддерживал загрузку различных таблиц с разными сопоставлениями.</span><span class="sxs-lookup"><span data-stu-id="d973e-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="d973e-116">Для этого просто добавьте дополнительные объекты **экземпляр DataTableMapping** .</span><span class="sxs-lookup"><span data-stu-id="d973e-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="d973e-117">Если методу **Fill** передается экземпляр **набора данных** и имя **экземпляр DataTableMapping** , если сопоставление с таким именем существует, оно используется; в противном случае используется **Таблица** данных с таким именем.</span><span class="sxs-lookup"><span data-stu-id="d973e-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="d973e-118">В следующих примерах создается **экземпляр DataTableMapping** с именем **Customers** и **DataTable** с именем **бизталксчема**.</span><span class="sxs-lookup"><span data-stu-id="d973e-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="d973e-119">Затем в примере сопоставляются строки, возвращенные инструкцией SELECT, с **таблицей**данных **бизталксчема** .</span><span class="sxs-lookup"><span data-stu-id="d973e-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
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
> <span data-ttu-id="d973e-120">Если имя исходного столбца не задано для сопоставления столбцов, или имя исходной таблицы не задано для сопоставления таблиц, то автоматически создаются имена, применяемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d973e-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="d973e-121">Если для сопоставления столбцов не указан исходный столбец, сопоставлению столбцов присваивается добавочное имя по умолчанию **SourceColumn** *N,* начиная с **SourceColumn1**.</span><span class="sxs-lookup"><span data-stu-id="d973e-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="d973e-122">Если для сопоставления таблицы не указано имя исходной таблицы, сопоставлению таблицы присваивается добавочное имя по умолчанию **SourceTable** *N*, начиная с **SourceTable1**.</span><span class="sxs-lookup"><span data-stu-id="d973e-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d973e-123">Мы рекомендуем не использовать соглашение об именовании **SourceColumn** *N* для сопоставления столбцов или **SourceTable** *N* для сопоставления таблиц, так как указываемое имя может конфликтовать с существующим именем сопоставления столбцов по умолчанию в  **Колумнмаппингколлектион** или имя сопоставления таблицы в **дататаблемаппингколлектион**.</span><span class="sxs-lookup"><span data-stu-id="d973e-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="d973e-124">Если указанное имя уже существует, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="d973e-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="d973e-125">Обработка нескольких результирующих наборов</span><span class="sxs-lookup"><span data-stu-id="d973e-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="d973e-126">Если **SelectCommand** возвращает несколько таблиц, функция **Fill** автоматически создает имена таблиц с добавочными значениями для таблиц в **наборе данных**, начиная с указанного имени таблицы и продолжая в форме **TableName** . *N*, начиная с **TableName1**.</span><span class="sxs-lookup"><span data-stu-id="d973e-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="d973e-127">Сопоставления таблиц можно использовать для сопоставления автоматически создаваемого имени таблицы с именем, которое необходимо указать для таблицы в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="d973e-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="d973e-128">Например, для **SelectCommand** , возвращающего две таблицы, **Customers** и **Orders**, выполните следующий вызов функции **Fill**.</span><span class="sxs-lookup"><span data-stu-id="d973e-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 <span data-ttu-id="d973e-129">В **наборе данных**создаются две таблицы: **Customers** и **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="d973e-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="d973e-130">Можно использовать сопоставления таблиц, чтобы гарантировать, что вторая таблица будет называться **Orders** вместо **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="d973e-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="d973e-131">Для этого сопоставьте исходную таблицу **Customers1** со столбцами таблицы **набора данных** ,как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d973e-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a><span data-ttu-id="d973e-132">См. также</span><span class="sxs-lookup"><span data-stu-id="d973e-132">See also</span></span>

- [<span data-ttu-id="d973e-133">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="d973e-133">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="d973e-134">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d973e-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="d973e-135">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d973e-135">ADO.NET Overview</span></span>](ado-net-overview.md)
