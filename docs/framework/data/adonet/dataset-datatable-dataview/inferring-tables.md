---
title: Определение таблиц
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 2c2a93d413f301dc3006b701e4bc7979a3fa7a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034259"
---
# <a name="inferring-tables"></a><span data-ttu-id="a801d-102">Определение таблиц</span><span class="sxs-lookup"><span data-stu-id="a801d-102">Inferring Tables</span></span>
<span data-ttu-id="a801d-103">При выведении схемы для <xref:System.Data.DataSet> из XML-документа ADO.NET сначала определяет, какой из XML-элементов представляет таблицы.</span><span class="sxs-lookup"><span data-stu-id="a801d-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="a801d-104">Следующие структуры XML приводятся в таблице для **набора данных** схемы:</span><span class="sxs-lookup"><span data-stu-id="a801d-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="a801d-105">Элементы с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="a801d-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="a801d-106">Элементы с дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="a801d-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="a801d-107">Повторяющиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="a801d-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="a801d-108">Элементы с атрибутами</span><span class="sxs-lookup"><span data-stu-id="a801d-108">Elements with Attributes</span></span>  
 <span data-ttu-id="a801d-109">Элементы с заданными атрибутами приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="a801d-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="a801d-110">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="a801d-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a801d-111">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="a801d-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="a801d-112">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a801d-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a801d-113">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="a801d-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a801d-114">attr1</span><span class="sxs-lookup"><span data-stu-id="a801d-114">attr1</span></span>|<span data-ttu-id="a801d-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="a801d-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="a801d-116">value1</span><span class="sxs-lookup"><span data-stu-id="a801d-116">value1</span></span>||  
|<span data-ttu-id="a801d-117">value2</span><span class="sxs-lookup"><span data-stu-id="a801d-117">value2</span></span>|<span data-ttu-id="a801d-118">Text1</span><span class="sxs-lookup"><span data-stu-id="a801d-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="a801d-119">Элементы с дочерними элементами</span><span class="sxs-lookup"><span data-stu-id="a801d-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="a801d-120">Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="a801d-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="a801d-121">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="a801d-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a801d-122">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="a801d-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="a801d-123">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a801d-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a801d-124">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="a801d-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a801d-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="a801d-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="a801d-126">Text1</span><span class="sxs-lookup"><span data-stu-id="a801d-126">Text1</span></span>|  
  
 <span data-ttu-id="a801d-127">Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="a801d-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="a801d-128">Если элемент документа не имеет атрибутов и дочерних элементов, которые выводились бы как столбцы, то элемент выводится как **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="a801d-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="a801d-129">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="a801d-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a801d-130">В процессе вывода создается таблица с именем DocumentElement.</span><span class="sxs-lookup"><span data-stu-id="a801d-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="a801d-131">**Набор данных:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="a801d-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="a801d-132">**Таблица:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a801d-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="a801d-133">Element1</span><span class="sxs-lookup"><span data-stu-id="a801d-133">Element1</span></span>|<span data-ttu-id="a801d-134">Element2</span><span class="sxs-lookup"><span data-stu-id="a801d-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="a801d-135">Text1</span><span class="sxs-lookup"><span data-stu-id="a801d-135">Text1</span></span>|<span data-ttu-id="a801d-136">Text2</span><span class="sxs-lookup"><span data-stu-id="a801d-136">Text2</span></span>|  
  
 <span data-ttu-id="a801d-137">В качестве альтернативы рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="a801d-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a801d-138">В процессе вывода создается **набора данных** с именем «DocumentElement», который содержит таблицу с именем «Элемент1».</span><span class="sxs-lookup"><span data-stu-id="a801d-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="a801d-139">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a801d-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a801d-140">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="a801d-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a801d-141">attr1</span><span class="sxs-lookup"><span data-stu-id="a801d-141">attr1</span></span>|<span data-ttu-id="a801d-142">attr2</span><span class="sxs-lookup"><span data-stu-id="a801d-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="a801d-143">value1</span><span class="sxs-lookup"><span data-stu-id="a801d-143">value1</span></span>|<span data-ttu-id="a801d-144">value2</span><span class="sxs-lookup"><span data-stu-id="a801d-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="a801d-145">Повторяющиеся элементы</span><span class="sxs-lookup"><span data-stu-id="a801d-145">Repeating Elements</span></span>  
 <span data-ttu-id="a801d-146">Повторяющиеся элементы приводятся в выведенной таблице.</span><span class="sxs-lookup"><span data-stu-id="a801d-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="a801d-147">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="a801d-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a801d-148">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="a801d-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="a801d-149">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a801d-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a801d-150">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="a801d-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a801d-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="a801d-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="a801d-152">Text1</span><span class="sxs-lookup"><span data-stu-id="a801d-152">Text1</span></span>|  
|<span data-ttu-id="a801d-153">Text2</span><span class="sxs-lookup"><span data-stu-id="a801d-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a801d-154">См. также</span><span class="sxs-lookup"><span data-stu-id="a801d-154">See also</span></span>

- [<span data-ttu-id="a801d-155">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="a801d-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="a801d-156">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="a801d-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="a801d-157">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="a801d-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="a801d-158">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="a801d-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="a801d-159">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="a801d-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="a801d-160">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a801d-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
