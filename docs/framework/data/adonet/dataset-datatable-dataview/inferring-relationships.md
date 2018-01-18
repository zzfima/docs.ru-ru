---
title: "Определение отношений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 79f79c1dbc74b98cff10de81c2bd7bd32d7d286b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-relationships"></a><span data-ttu-id="25637-102">Определение отношений</span><span class="sxs-lookup"><span data-stu-id="25637-102">Inferring Relationships</span></span>
<span data-ttu-id="25637-103">Если элемент, выводимый в виде таблицы, имеет дочерний элемент, который также выводится в виде таблицы, между двумя этими таблицами будет создана связь <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="25637-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="25637-104">Новый столбец с именем **ParentTableName_Id** будут добавлены в таблицу, созданную для родительского элемента и в таблицу, созданную для дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="25637-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="25637-105">**ColumnMapping** будет присвоено свойству данного столбца идентификаторов **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="25637-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="25637-106">Столбец будет с автоматическим приращением первичного ключа для родительской таблицы и будет использоваться для **DataRelation** между двумя таблицами.</span><span class="sxs-lookup"><span data-stu-id="25637-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="25637-107">Тип данных добавленный столбец идентификаторов будет **System.Int32**, в отличие от типа данных всех остальных выведенных столбцов, который является **System.String**.</span><span class="sxs-lookup"><span data-stu-id="25637-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="25637-108">Объект <xref:System.Data.ForeignKeyConstraint> с **DeleteRule** = **Cascade** также будет создан с помощью нового столбца в родительской и дочерней таблицами.</span><span class="sxs-lookup"><span data-stu-id="25637-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="25637-109">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="25637-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="25637-110">Процесс вывода создаст две таблицы: **Element1** и **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="25637-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="25637-111">**Element1** будет содержать два столбца: **Element1_Id** и **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="25637-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="25637-112">**ColumnMapping** свойство **Element1_Id** столбца будет присвоено **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="25637-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="25637-113">**ColumnMapping** свойство **ChildElement2** столбца будет присвоено **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="25637-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="25637-114">**Element1_Id** столбца будет установлено в качестве первичного ключа **Element1** таблицы.</span><span class="sxs-lookup"><span data-stu-id="25637-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="25637-115">**ChildElement1** будет содержать три столбца: **attr1**, **attr2** и **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="25637-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="25637-116">**ColumnMapping** свойство **attr1** и **attr2** столбцов будет присвоено **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="25637-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="25637-117">**ColumnMapping** свойство **Element1_Id** столбца будет присвоено **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="25637-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="25637-118">Объект **DataRelation** и **ForeignKeyConstraint** будут созданы с использованием **Element1_Id** столбцы из обеих таблиц.</span><span class="sxs-lookup"><span data-stu-id="25637-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="25637-119">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="25637-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="25637-120">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="25637-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="25637-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="25637-121">Element1_Id</span></span>|<span data-ttu-id="25637-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="25637-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="25637-123">0</span><span class="sxs-lookup"><span data-stu-id="25637-123">0</span></span>|<span data-ttu-id="25637-124">Text2</span><span class="sxs-lookup"><span data-stu-id="25637-124">Text2</span></span>|  
  
 <span data-ttu-id="25637-125">**Таблица:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="25637-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="25637-126">attr1</span><span class="sxs-lookup"><span data-stu-id="25637-126">attr1</span></span>|<span data-ttu-id="25637-127">attr2</span><span class="sxs-lookup"><span data-stu-id="25637-127">attr2</span></span>|<span data-ttu-id="25637-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="25637-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="25637-129">value1</span><span class="sxs-lookup"><span data-stu-id="25637-129">value1</span></span>|<span data-ttu-id="25637-130">value2</span><span class="sxs-lookup"><span data-stu-id="25637-130">value2</span></span>|<span data-ttu-id="25637-131">0</span><span class="sxs-lookup"><span data-stu-id="25637-131">0</span></span>|  
  
 <span data-ttu-id="25637-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="25637-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="25637-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="25637-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="25637-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="25637-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="25637-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="25637-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="25637-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="25637-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="25637-137">**Вложенные:** True</span><span class="sxs-lookup"><span data-stu-id="25637-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="25637-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="25637-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="25637-139">**Column:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="25637-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="25637-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="25637-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="25637-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="25637-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="25637-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="25637-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="25637-143">**AcceptRejectRule:** None</span><span class="sxs-lookup"><span data-stu-id="25637-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25637-144">См. также</span><span class="sxs-lookup"><span data-stu-id="25637-144">See Also</span></span>  
 [<span data-ttu-id="25637-145">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="25637-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="25637-146">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="25637-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="25637-147">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="25637-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="25637-148">Вложенность объектов DataRelation</span><span class="sxs-lookup"><span data-stu-id="25637-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [<span data-ttu-id="25637-149">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="25637-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="25637-150">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="25637-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="25637-151">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="25637-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
