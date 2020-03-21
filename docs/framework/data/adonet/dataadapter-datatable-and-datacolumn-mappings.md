---
title: Сопоставления DataAdapter DataTable и DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6380dd0512bd7834f50b87f90f445cb01b7a8b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151563"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="4adeb-102">Сопоставления DataAdapter DataTable и DataColumn</span><span class="sxs-lookup"><span data-stu-id="4adeb-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="4adeb-103">**DataAdapter** содержит коллекцию объектов <xref:System.Data.Common.DataTableMapping> с нулевым или большим количеством объектов в **свойстве TableMappings.**</span><span class="sxs-lookup"><span data-stu-id="4adeb-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="4adeb-104">**DataTableMapping** предоставляет мастер-картографирование между данными, возвращенными из <xref:System.Data.DataTable>запроса, против источника данных и .</span><span class="sxs-lookup"><span data-stu-id="4adeb-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="4adeb-105">Имя **DataTableMapping** может быть передано вместо имени **DataTable** методу **заполнения** **DataAdapter.**</span><span class="sxs-lookup"><span data-stu-id="4adeb-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="4adeb-106">Следующий пример создает **таблицу DataTableMapping** под названием **AuthorsMapping** для **авторов** таблицы.</span><span class="sxs-lookup"><span data-stu-id="4adeb-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="4adeb-107">**DataTableMapping** позволяет использовать имена столбцов в **DataTable,** которые отличаются от тех, которые находятся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4adeb-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="4adeb-108">**DataAdapter** использует отображение для соответствия столбцов при обновлении таблицы.</span><span class="sxs-lookup"><span data-stu-id="4adeb-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="4adeb-109">Если при вызове метода **Заполнения** или **обновления** **DataAdapter**вы не указали **имя TableName** или **имя DataTableMapping,** **DataAdapter** ищет **DataTableMapping** под названием "Таблица".</span><span class="sxs-lookup"><span data-stu-id="4adeb-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="4adeb-110">Если этого **DataTableMapping** не существует, **таблицаНазвание** **dataTable** — это «Таблица».</span><span class="sxs-lookup"><span data-stu-id="4adeb-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="4adeb-111">Можно указать **данные** по умолчанию, создав **DataTableMapping** с именем "Таблица".</span><span class="sxs-lookup"><span data-stu-id="4adeb-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="4adeb-112">Следующий пример кода создает **DataTableMapping** (из пространства <xref:System.Data.Common> имен) и делает его отображением по умолчанию для указанного **DataAdapter,** назвав его "Таблица".</span><span class="sxs-lookup"><span data-stu-id="4adeb-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="4adeb-113">Затем в примере отображается столбцы из первой таблицы в результате запроса (таблица **клиентов** базы данных **Northwind)** <xref:System.Data.DataSet>с набором более удобных имен в таблице **клиентов Northwind** в таблице .</span><span class="sxs-lookup"><span data-stu-id="4adeb-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="4adeb-114">Для столбцов, к которым не применяется сопоставление, используются имена столбцов из источника данных.</span><span class="sxs-lookup"><span data-stu-id="4adeb-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
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
  
 <span data-ttu-id="4adeb-115">В более продвинутых ситуациях вы можете решить, что вам нужно, чтобы тот же **DataAdapter** поддерживал загрузку различных таблиц с различными отображениями.</span><span class="sxs-lookup"><span data-stu-id="4adeb-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="4adeb-116">Для этого просто добавьте дополнительные объекты **DataTableMapping.**</span><span class="sxs-lookup"><span data-stu-id="4adeb-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="4adeb-117">При переводе метода **заполнения** **экземплярА DataSet** и имени **DataTableMapping,** если существует отображение с этим именем, оно используется; в противном случае используется **DataTable** с таким именем.</span><span class="sxs-lookup"><span data-stu-id="4adeb-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="4adeb-118">Следующие примеры создают **DataTableMapping** с именем **Клиентов** и именем **DataTable** **BizTalkSchema**.</span><span class="sxs-lookup"><span data-stu-id="4adeb-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="4adeb-119">Пример затем отображает строки, возвращенные выпиской SELECT, в **BizTalkSchema** **DataTable.**</span><span class="sxs-lookup"><span data-stu-id="4adeb-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
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
> <span data-ttu-id="4adeb-120">Если имя исходного столбца не задано для сопоставления столбцов, или имя исходной таблицы не задано для сопоставления таблиц, то автоматически создаются имена, применяемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4adeb-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="4adeb-121">Если столбец исходного кода не поставляется для отображения столбца, отображению столбца дается дополнительное имя по умолчанию **SourceColumn** *N,* начиная с **SourceColumn1.**</span><span class="sxs-lookup"><span data-stu-id="4adeb-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="4adeb-122">Если имя исходной таблицы не поставляется для отображения таблицы, отображение таблицы получает дополнительное значение значения по умолчанию **SourceTable** *N,* начиная с **SourceTable1.**</span><span class="sxs-lookup"><span data-stu-id="4adeb-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4adeb-123">Мы рекомендуем вам избегать именования конвенции **SourceColumn** *N* для отображения столбцов или **SourceTable** *N* для отображения таблицы, поскольку имя, которое вы поставляете, может противоречить существующему имени столбца по умолчанию в названии **columnMappingCollection** или имя отображения таблицы в **DataTableMappingCollection.**</span><span class="sxs-lookup"><span data-stu-id="4adeb-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="4adeb-124">Если указанное имя уже существует, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="4adeb-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="4adeb-125">Обработка нескольких результирующих наборов</span><span class="sxs-lookup"><span data-stu-id="4adeb-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="4adeb-126">Если **SelectCommand** возвращает несколько таблиц, **Fill** автоматически генерирует имена таблиц с дополнительными значениями для таблиц в **DataSet,** начиная с указанного имени таблицы и продолжая в форме **TableName** *N,* начиная с **TableName1.**</span><span class="sxs-lookup"><span data-stu-id="4adeb-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="4adeb-127">Можно использовать таблицы для отображения автоматически генерируемого имени таблицы с именем, которое вы хотите указать для таблицы **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="4adeb-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="4adeb-128">Например, для **SelectCommand,** который возвращает две таблицы, **Клиенты** и **Заказы,** выдать следующий вызов **для заполнения.**</span><span class="sxs-lookup"><span data-stu-id="4adeb-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 <span data-ttu-id="4adeb-129">В **DataSet**создаются две таблицы: **Клиенты** и **клиенты1**.</span><span class="sxs-lookup"><span data-stu-id="4adeb-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="4adeb-130">Можно использовать таблицы для картирования, чтобы убедиться, что вторая таблица называется **Заказы** вместо **Customers1.**</span><span class="sxs-lookup"><span data-stu-id="4adeb-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="4adeb-131">Для этого нанесите карту исходной таблицы **Customers1** в таблицу **DataSet** **Orders,** как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4adeb-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a><span data-ttu-id="4adeb-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4adeb-132">See also</span></span>

- [<span data-ttu-id="4adeb-133">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="4adeb-133">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="4adeb-134">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4adeb-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="4adeb-135">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4adeb-135">ADO.NET Overview</span></span>](ado-net-overview.md)
