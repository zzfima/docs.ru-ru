---
title: Определение столбцов
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 2718cbcf29799f99c8648b129fdb6079a6f6d344
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786175"
---
# <a name="inferring-columns"></a><span data-ttu-id="84f78-102">Определение столбцов</span><span class="sxs-lookup"><span data-stu-id="84f78-102">Inferring Columns</span></span>
<span data-ttu-id="84f78-103">ADO.NET определяет по XML-документу, какие элементы выводятся как таблицы для <xref:System.Data.DataSet>, а затем выводятся столбцы для этих таблиц.</span><span class="sxs-lookup"><span data-stu-id="84f78-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="84f78-104">В ADO.NET 2,0 появился новый механизм вывода схемы, который выводит строго типизированный тип данных для каждого элемента **simpleType** .</span><span class="sxs-lookup"><span data-stu-id="84f78-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="84f78-105">В предыдущих версиях тип данных выводимого элемента **simpleType** всегда имеет значение **xsd: String**.</span><span class="sxs-lookup"><span data-stu-id="84f78-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="84f78-106">Миграция и обратная совместимость</span><span class="sxs-lookup"><span data-stu-id="84f78-106">Migration and Backward Compatibility</span></span>  
 <span data-ttu-id="84f78-107">Метод **ReadXml** принимает аргумент типа **инферсчема**.</span><span class="sxs-lookup"><span data-stu-id="84f78-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="84f78-108">Этот аргумент позволяет задать поведение, совместимое с предыдущими версиями.</span><span class="sxs-lookup"><span data-stu-id="84f78-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="84f78-109">Доступные значения перечисления **инферсчема** показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="84f78-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="84f78-110">Обеспечивает обратную совместимость, выводя в качестве простого типа всегда тип <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="84f78-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="84f78-111">Выводит строго типизированный тип данных.</span><span class="sxs-lookup"><span data-stu-id="84f78-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="84f78-112">Вызывает исключение при использовании с <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="84f78-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="84f78-113">Пропускает любую встроенную схему и считывает данные в существующую схему <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="84f78-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="84f78-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="84f78-114">Attributes</span></span>  
 <span data-ttu-id="84f78-115">Как определено в [выведение таблиц](inferring-tables.md), элемент с атрибутами будет выведен как таблица.</span><span class="sxs-lookup"><span data-stu-id="84f78-115">As defined in [Inferring Tables](inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="84f78-116">Атрибуты этого элемента будут выведены как столбцы для таблицы.</span><span class="sxs-lookup"><span data-stu-id="84f78-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="84f78-117">Свойству **ColumnMapping** столбцов будет присвоено значение **MappingType. Attribute**, чтобы гарантировать, что имена столбцов будут записаны как атрибуты, если схема записывается обратно в XML.</span><span class="sxs-lookup"><span data-stu-id="84f78-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="84f78-118">Значения атрибутов хранятся в строке в таблице.</span><span class="sxs-lookup"><span data-stu-id="84f78-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="84f78-119">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="84f78-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="84f78-120">В процессе вывода создается таблица с именем **Element1** с двумя столбцами, **attr1** и **attr2**.</span><span class="sxs-lookup"><span data-stu-id="84f78-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="84f78-121">Свойство **ColumnMapping** обоих столбцов будет иметь значение **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="84f78-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="84f78-122">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="84f78-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="84f78-123">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="84f78-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="84f78-124">attr1</span><span class="sxs-lookup"><span data-stu-id="84f78-124">attr1</span></span>|<span data-ttu-id="84f78-125">attr2</span><span class="sxs-lookup"><span data-stu-id="84f78-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="84f78-126">value1</span><span class="sxs-lookup"><span data-stu-id="84f78-126">value1</span></span>|<span data-ttu-id="84f78-127">value2</span><span class="sxs-lookup"><span data-stu-id="84f78-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="84f78-128">Элементы без атрибутов или дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="84f78-128">Elements Without Attributes or Child Elements</span></span>  
 <span data-ttu-id="84f78-129">Если элемент не имеет дочерних элементов или атрибутов, то он будет выведен как столбец.</span><span class="sxs-lookup"><span data-stu-id="84f78-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="84f78-130">Свойству **ColumnMapping** столбца будет присвоено значение **MappingType. element**.</span><span class="sxs-lookup"><span data-stu-id="84f78-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="84f78-131">Текст для дочерних элементов хранится в строке в таблице.</span><span class="sxs-lookup"><span data-stu-id="84f78-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="84f78-132">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="84f78-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="84f78-133">В процессе вывода создается таблица с именем **Element1** с двумя столбцами, **ChildElement1** и **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="84f78-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="84f78-134">Свойство **ColumnMapping** обоих столбцов будет иметь значение **MappingType. element**.</span><span class="sxs-lookup"><span data-stu-id="84f78-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="84f78-135">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="84f78-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="84f78-136">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="84f78-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="84f78-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="84f78-137">ChildElement1</span></span>|<span data-ttu-id="84f78-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="84f78-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="84f78-139">Text1</span><span class="sxs-lookup"><span data-stu-id="84f78-139">Text1</span></span>|<span data-ttu-id="84f78-140">Text2</span><span class="sxs-lookup"><span data-stu-id="84f78-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84f78-141">См. также</span><span class="sxs-lookup"><span data-stu-id="84f78-141">See also</span></span>

- [<span data-ttu-id="84f78-142">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="84f78-142">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="84f78-143">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="84f78-143">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="84f78-144">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="84f78-144">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="84f78-145">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="84f78-145">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="84f78-146">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="84f78-146">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="84f78-147">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="84f78-147">ADO.NET Overview</span></span>](../ado-net-overview.md)
