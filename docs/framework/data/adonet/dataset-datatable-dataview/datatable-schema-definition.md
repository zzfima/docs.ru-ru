---
title: "Определение схемы таблицы данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e848a0fac5d41628d4d39f1771019eb870e6395b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="datatable-schema-definition"></a><span data-ttu-id="1e913-102">Определение схемы таблицы данных</span><span class="sxs-lookup"><span data-stu-id="1e913-102">DataTable Schema Definition</span></span>
<span data-ttu-id="1e913-103">Схема, или структура, таблицы представляется столбцами и ограничениями.</span><span class="sxs-lookup"><span data-stu-id="1e913-103">The schema, or structure, of a table is represented by columns and constraints.</span></span> <span data-ttu-id="1e913-104">Схема <xref:System.Data.DataTable> определяется с использованием объектов <xref:System.Data.DataColumn>, а также объектов <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint>.</span><span class="sxs-lookup"><span data-stu-id="1e913-104">You define the schema of a <xref:System.Data.DataTable> using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="1e913-105">Столбцы таблицы могут сопоставляться со столбцами источника данных, содержать вычисляемые значения выражений, автоматически увеличивать значения или содержать значения первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="1e913-105">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="1e913-106">В ссылках по имени на столбцы, связи и ограничения таблицы учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="1e913-106">References by name to columns, relations, and constraints in a table are case-sensitive.</span></span> <span data-ttu-id="1e913-107">Поэтому в таблице могут существовать столбцы, связи и ограничения, имеющие одинаковое имя, но отличающиеся регистром.</span><span class="sxs-lookup"><span data-stu-id="1e913-107">Two or more columns, relations, or constraints can therefore exist in a table that have the same name, but that differ in case.</span></span> <span data-ttu-id="1e913-108">Например, можно иметь **Col1** и **col1**.</span><span class="sxs-lookup"><span data-stu-id="1e913-108">For example, you can have **Col1** and **col1**.</span></span> <span data-ttu-id="1e913-109">В таком случае ссылка на один из столбцов по имени должна точно соответствовать регистру столбца; в противном случае возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="1e913-109">In such as case, a reference to one of the columns by name must match the case of the column name exactly; otherwise an exception is thrown.</span></span> <span data-ttu-id="1e913-110">Например если таблица **myTable** содержит столбцы **Col1** и **col1**, необходимо предоставить ссылки, **Col1** по имени как  **myTable.Columns["Col1"]**, и **col1** как **myTable.Columns["col1"]**.</span><span class="sxs-lookup"><span data-stu-id="1e913-110">For example, if the table **myTable** contains the columns **Col1** and **col1**, you would reference **Col1** by name as **myTable.Columns["Col1"]**, and **col1** as **myTable.Columns["col1"]**.</span></span> <span data-ttu-id="1e913-111">Попытка сослаться на любую из столбцов, **myTable.Columns["COL1"]** создается исключение.</span><span class="sxs-lookup"><span data-stu-id="1e913-111">Attempting to reference either of the columns as **myTable.Columns["COL1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="1e913-112">Правило учета регистра не применяется, если существует только один столбец, одна связь или ограничение с конкретным именем.</span><span class="sxs-lookup"><span data-stu-id="1e913-112">The case-sensitivity rule does not apply if only one column, relation, or constraint  with a particular name exists.</span></span> <span data-ttu-id="1e913-113">Это означает, что если в таблице нет другого объекта столбца, связи или ограничения, имя которого совпадает с именем этого конкретного объекта столбца, связи или ограничения, то на объект можно ссылаться по имени, используя любой регистр, и исключение в этом случае не возникает.</span><span class="sxs-lookup"><span data-stu-id="1e913-113">That is, if no other column, relation, or constraint object in the table matches the name of that particular column, relation, or constraint object, you may reference the object by name using any case, and no exception is thrown.</span></span> <span data-ttu-id="1e913-114">Например, если таблица имеет только **Col1**, можно ссылаться с использованием **my. Столбцы [«COL1»]**.</span><span class="sxs-lookup"><span data-stu-id="1e913-114">For example, if the table has only **Col1**, you can reference it using **my.Columns["COL1"]**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e913-115"><xref:System.Data.DataTable.CaseSensitive%2A> Свойство **DataTable** не влияет на это поведение.</span><span class="sxs-lookup"><span data-stu-id="1e913-115">The <xref:System.Data.DataTable.CaseSensitive%2A> property of the **DataTable** does not affect this behavior.</span></span> <span data-ttu-id="1e913-116">**CaseSensitive** свойство применяется, данные в таблице и влияет на сортировку, поиск, фильтрацию, соблюдение ограничений и т. д., но не ссылки на столбцы, связи и ограничения.</span><span class="sxs-lookup"><span data-stu-id="1e913-116">The **CaseSensitive** property applies to the data in a table and affects sorting, searching, filtering, enforcing constraints, and so on, but not to references to the columns, relations, and constraints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e913-117">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="1e913-117">In This Section</span></span>  
 [<span data-ttu-id="1e913-118">Добавление столбцов в DataTable</span><span class="sxs-lookup"><span data-stu-id="1e913-118">Adding Columns to a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-columns-to-a-datatable.md)  
 <span data-ttu-id="1e913-119">Описывает, как определить столбцы таблицы с использованием **DataColumn** объектов.</span><span class="sxs-lookup"><span data-stu-id="1e913-119">Describes how to define the columns of a table using **DataColumn** objects.</span></span>  
  
 [<span data-ttu-id="1e913-120">Создание столбцов выражений</span><span class="sxs-lookup"><span data-stu-id="1e913-120">Creating Expression Columns</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-expression-columns.md)  
 <span data-ttu-id="1e913-121">Объясняет, как **выражение** свойство столбца может использоваться для расчета значений на основе значений из других столбцов в строке.</span><span class="sxs-lookup"><span data-stu-id="1e913-121">Explains how the **Expression** property of a column can be used to calculate values based on the values from other columns in the row.</span></span>  
  
 [<span data-ttu-id="1e913-122">Создание столбцов AutoIncrement</span><span class="sxs-lookup"><span data-stu-id="1e913-122">Creating AutoIncrement Columns</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)  
 <span data-ttu-id="1e913-123">Описывает, как для столбца может быть установлено автоматическое увеличение числовых значений для обеспечения уникального значения столбца в строке.</span><span class="sxs-lookup"><span data-stu-id="1e913-123">Describes how a column can be set to automatically increment numerical values to ensure a unique column value per row.</span></span>  
  
 [<span data-ttu-id="1e913-124">Определение первичных ключей</span><span class="sxs-lookup"><span data-stu-id="1e913-124">Defining Primary Keys</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)  
 <span data-ttu-id="1e913-125">Описывает, как задать первичный ключ таблицы из одного или нескольких **DataColumn** объектов.</span><span class="sxs-lookup"><span data-stu-id="1e913-125">Describes how to specify the primary key of a table from one or more **DataColumn** objects.</span></span>  
  
 [<span data-ttu-id="1e913-126">Ограничения DataTable</span><span class="sxs-lookup"><span data-stu-id="1e913-126">DataTable Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)  
 <span data-ttu-id="1e913-127">Описывает, как определить внешний ключ и ограничения уникальности для столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="1e913-127">Describes how to define foreign key and unique constraints for columns in a table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e913-128">См. также</span><span class="sxs-lookup"><span data-stu-id="1e913-128">See Also</span></span>  
 [<span data-ttu-id="1e913-129">DataTables</span><span class="sxs-lookup"><span data-stu-id="1e913-129">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="1e913-130">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1e913-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
