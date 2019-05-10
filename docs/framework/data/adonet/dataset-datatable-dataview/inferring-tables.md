---
title: Определение таблиц
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 174d305688c7090c163df60a11e233aea24b8f79
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587363"
---
# <a name="inferring-tables"></a><span data-ttu-id="2a0bf-102">Определение таблиц</span><span class="sxs-lookup"><span data-stu-id="2a0bf-102">Inferring Tables</span></span>
<span data-ttu-id="2a0bf-103">При выведении схемы для <xref:System.Data.DataSet> из XML-документа ADO.NET сначала определяет, какой из XML-элементов представляет таблицы.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="2a0bf-104">Следующие структуры XML приводятся в таблице для **набора данных** схемы:</span><span class="sxs-lookup"><span data-stu-id="2a0bf-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="2a0bf-105">Элементы с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="2a0bf-106">Элементы с дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="2a0bf-107">Повторяющиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="2a0bf-108">Элементы с атрибутами</span><span class="sxs-lookup"><span data-stu-id="2a0bf-108">Elements with Attributes</span></span>  
 <span data-ttu-id="2a0bf-109">Элементы с заданными атрибутами приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="2a0bf-110">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="2a0bf-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2a0bf-111">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="2a0bf-112">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2a0bf-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2a0bf-113">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2a0bf-114">attr1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-114">attr1</span></span>|<span data-ttu-id="2a0bf-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="2a0bf-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="2a0bf-116">value1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-116">value1</span></span>||  
|<span data-ttu-id="2a0bf-117">value2</span><span class="sxs-lookup"><span data-stu-id="2a0bf-117">value2</span></span>|<span data-ttu-id="2a0bf-118">Text1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="2a0bf-119">Элементы с дочерними элементами</span><span class="sxs-lookup"><span data-stu-id="2a0bf-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="2a0bf-120">Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="2a0bf-121">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="2a0bf-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2a0bf-122">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="2a0bf-123">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2a0bf-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2a0bf-124">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2a0bf-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="2a0bf-126">Text1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-126">Text1</span></span>|  
  
 <span data-ttu-id="2a0bf-127">Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="2a0bf-128">Если элемент документа не имеет атрибутов и дочерних элементов, которые выводились бы как столбцы, то элемент выводится как **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="2a0bf-129">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="2a0bf-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2a0bf-130">В процессе вывода создается таблица с именем DocumentElement.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="2a0bf-131">**Набор данных:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="2a0bf-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="2a0bf-132">**Таблица:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2a0bf-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="2a0bf-133">Element1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-133">Element1</span></span>|<span data-ttu-id="2a0bf-134">Element2</span><span class="sxs-lookup"><span data-stu-id="2a0bf-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="2a0bf-135">Text1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-135">Text1</span></span>|<span data-ttu-id="2a0bf-136">Text2</span><span class="sxs-lookup"><span data-stu-id="2a0bf-136">Text2</span></span>|  
  
 <span data-ttu-id="2a0bf-137">В качестве альтернативы рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="2a0bf-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2a0bf-138">В процессе вывода создается **набора данных** с именем «DocumentElement», который содержит таблицу с именем «Элемент1».</span><span class="sxs-lookup"><span data-stu-id="2a0bf-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="2a0bf-139">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2a0bf-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2a0bf-140">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2a0bf-141">attr1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-141">attr1</span></span>|<span data-ttu-id="2a0bf-142">attr2</span><span class="sxs-lookup"><span data-stu-id="2a0bf-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="2a0bf-143">value1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-143">value1</span></span>|<span data-ttu-id="2a0bf-144">value2</span><span class="sxs-lookup"><span data-stu-id="2a0bf-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="2a0bf-145">Повторяющиеся элементы</span><span class="sxs-lookup"><span data-stu-id="2a0bf-145">Repeating Elements</span></span>  
 <span data-ttu-id="2a0bf-146">Повторяющиеся элементы приводятся в выведенной таблице.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="2a0bf-147">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="2a0bf-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2a0bf-148">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="2a0bf-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="2a0bf-149">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2a0bf-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2a0bf-150">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2a0bf-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="2a0bf-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="2a0bf-152">Text1</span><span class="sxs-lookup"><span data-stu-id="2a0bf-152">Text1</span></span>|  
|<span data-ttu-id="2a0bf-153">Text2</span><span class="sxs-lookup"><span data-stu-id="2a0bf-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a0bf-154">См. также</span><span class="sxs-lookup"><span data-stu-id="2a0bf-154">See also</span></span>

- [<span data-ttu-id="2a0bf-155">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="2a0bf-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="2a0bf-156">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="2a0bf-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="2a0bf-157">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="2a0bf-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="2a0bf-158">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="2a0bf-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="2a0bf-159">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="2a0bf-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="2a0bf-160">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2a0bf-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
