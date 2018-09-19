---
title: Определение отношений
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 7dc3fb0c6098d636e640aaf52b72a404c1486492
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46288200"
---
# <a name="inferring-relationships"></a><span data-ttu-id="1ca28-102">Определение отношений</span><span class="sxs-lookup"><span data-stu-id="1ca28-102">Inferring Relationships</span></span>
<span data-ttu-id="1ca28-103">Если элемент, выводимый в виде таблицы, имеет дочерний элемент, который также выводится в виде таблицы, между двумя этими таблицами будет создана связь <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="1ca28-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="1ca28-104">Новый столбец с именем **ParentTableName_Id** будут добавлены как таблицы, созданной для родительского элемента, так и таблицу, созданную для дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="1ca28-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="1ca28-105">**ColumnMapping** данного столбца идентификаторов будет установлено **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="1ca28-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="1ca28-106">Столбец будет заданы с автоматическим приращением первичным ключом для родительской таблицы, а также будет использоваться для **DataRelation** между двумя таблицами.</span><span class="sxs-lookup"><span data-stu-id="1ca28-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="1ca28-107">Тип данных добавленный столбец идентификаторов будет **System.Int32**, в отличие от всех остальных выведенных столбцов типа данных, который является **System.String**.</span><span class="sxs-lookup"><span data-stu-id="1ca28-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="1ca28-108">Объект <xref:System.Data.ForeignKeyConstraint> с **DeleteRule** = **Cascade** также будет создаваться с помощью нового столбца в родительской и дочерней таблицами.</span><span class="sxs-lookup"><span data-stu-id="1ca28-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="1ca28-109">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="1ca28-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="1ca28-110">Процесс вывода создаст две таблицы: **Element1** и **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="1ca28-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="1ca28-111">**Element1** таблица будет содержать два столбца: **Element1_Id** и **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="1ca28-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="1ca28-112">**ColumnMapping** свойство **Element1_Id** столбца будет присвоено **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="1ca28-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="1ca28-113">**ColumnMapping** свойство **ChildElement2** столбца будет присвоено **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="1ca28-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="1ca28-114">**Element1_Id** столбца будет установлено в качестве первичного ключа **Element1** таблицы.</span><span class="sxs-lookup"><span data-stu-id="1ca28-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="1ca28-115">**ChildElement1** таблица будет иметь три столбца: **attr1**, **attr2** и **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="1ca28-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="1ca28-116">**ColumnMapping** свойство для **attr1** и **attr2** столбцов будет присвоено **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="1ca28-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="1ca28-117">**ColumnMapping** свойство **Element1_Id** столбца будет присвоено **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="1ca28-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="1ca28-118">Объект **DataRelation** и **ForeignKeyConstraint** будет создан с помощью **Element1_Id** столбцы из обеих таблиц.</span><span class="sxs-lookup"><span data-stu-id="1ca28-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="1ca28-119">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="1ca28-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="1ca28-120">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="1ca28-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="1ca28-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="1ca28-121">Element1_Id</span></span>|<span data-ttu-id="1ca28-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="1ca28-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="1ca28-123">0</span><span class="sxs-lookup"><span data-stu-id="1ca28-123">0</span></span>|<span data-ttu-id="1ca28-124">Text2</span><span class="sxs-lookup"><span data-stu-id="1ca28-124">Text2</span></span>|  
  
 <span data-ttu-id="1ca28-125">**Таблица:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="1ca28-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="1ca28-126">attr1</span><span class="sxs-lookup"><span data-stu-id="1ca28-126">attr1</span></span>|<span data-ttu-id="1ca28-127">attr2</span><span class="sxs-lookup"><span data-stu-id="1ca28-127">attr2</span></span>|<span data-ttu-id="1ca28-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="1ca28-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="1ca28-129">value1</span><span class="sxs-lookup"><span data-stu-id="1ca28-129">value1</span></span>|<span data-ttu-id="1ca28-130">value2</span><span class="sxs-lookup"><span data-stu-id="1ca28-130">value2</span></span>|<span data-ttu-id="1ca28-131">0</span><span class="sxs-lookup"><span data-stu-id="1ca28-131">0</span></span>|  
  
 <span data-ttu-id="1ca28-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="1ca28-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="1ca28-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="1ca28-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="1ca28-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="1ca28-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="1ca28-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="1ca28-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="1ca28-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="1ca28-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="1ca28-137">**Вложенные:** True</span><span class="sxs-lookup"><span data-stu-id="1ca28-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="1ca28-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="1ca28-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="1ca28-139">**Столбец:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="1ca28-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="1ca28-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="1ca28-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="1ca28-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="1ca28-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="1ca28-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="1ca28-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="1ca28-143">**AcceptRejectRule:** None</span><span class="sxs-lookup"><span data-stu-id="1ca28-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ca28-144">См. также</span><span class="sxs-lookup"><span data-stu-id="1ca28-144">See Also</span></span>  
 [<span data-ttu-id="1ca28-145">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="1ca28-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="1ca28-146">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="1ca28-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="1ca28-147">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="1ca28-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="1ca28-148">Вложенность объектов DataRelation</span><span class="sxs-lookup"><span data-stu-id="1ca28-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [<span data-ttu-id="1ca28-149">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="1ca28-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="1ca28-150">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="1ca28-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="1ca28-151">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1ca28-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
