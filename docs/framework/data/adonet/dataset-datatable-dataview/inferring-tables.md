---
title: Определение таблиц
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 52ffd3fe90eb491dd01acf8538276cc828fdb309
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784495"
---
# <a name="inferring-tables"></a><span data-ttu-id="652d4-102">Определение таблиц</span><span class="sxs-lookup"><span data-stu-id="652d4-102">Inferring Tables</span></span>
<span data-ttu-id="652d4-103">При выведении схемы для <xref:System.Data.DataSet> из XML-документа ADO.NET сначала определяет, какой из XML-элементов представляет таблицы.</span><span class="sxs-lookup"><span data-stu-id="652d4-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="652d4-104">Следующие XML-структуры приводят к созданию таблицы для схемы **набора данных** :</span><span class="sxs-lookup"><span data-stu-id="652d4-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="652d4-105">Элементы с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="652d4-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="652d4-106">Элементы с дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="652d4-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="652d4-107">Повторяющиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="652d4-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="652d4-108">Элементы с атрибутами</span><span class="sxs-lookup"><span data-stu-id="652d4-108">Elements with Attributes</span></span>  
 <span data-ttu-id="652d4-109">Элементы с заданными атрибутами приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="652d4-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="652d4-110">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="652d4-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="652d4-111">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="652d4-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="652d4-112">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="652d4-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="652d4-113">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="652d4-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="652d4-114">attr1</span><span class="sxs-lookup"><span data-stu-id="652d4-114">attr1</span></span>|<span data-ttu-id="652d4-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="652d4-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="652d4-116">value1</span><span class="sxs-lookup"><span data-stu-id="652d4-116">value1</span></span>||  
|<span data-ttu-id="652d4-117">value2</span><span class="sxs-lookup"><span data-stu-id="652d4-117">value2</span></span>|<span data-ttu-id="652d4-118">Text1</span><span class="sxs-lookup"><span data-stu-id="652d4-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="652d4-119">Элементы с дочерними элементами</span><span class="sxs-lookup"><span data-stu-id="652d4-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="652d4-120">Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="652d4-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="652d4-121">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="652d4-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="652d4-122">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="652d4-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="652d4-123">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="652d4-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="652d4-124">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="652d4-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="652d4-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="652d4-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="652d4-126">Text1</span><span class="sxs-lookup"><span data-stu-id="652d4-126">Text1</span></span>|  
  
 <span data-ttu-id="652d4-127">Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="652d4-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="652d4-128">Если элемент документа не имеет атрибутов и не содержит дочерних элементов, которые будут выводиться как столбцы, то элемент выводится как **набор данных**.</span><span class="sxs-lookup"><span data-stu-id="652d4-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="652d4-129">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="652d4-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="652d4-130">В процессе вывода создается таблица с именем DocumentElement.</span><span class="sxs-lookup"><span data-stu-id="652d4-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="652d4-131">**Объекте** невдатасет</span><span class="sxs-lookup"><span data-stu-id="652d4-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="652d4-132">**Таблица** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="652d4-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="652d4-133">Element1</span><span class="sxs-lookup"><span data-stu-id="652d4-133">Element1</span></span>|<span data-ttu-id="652d4-134">Element2</span><span class="sxs-lookup"><span data-stu-id="652d4-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="652d4-135">Text1</span><span class="sxs-lookup"><span data-stu-id="652d4-135">Text1</span></span>|<span data-ttu-id="652d4-136">Text2</span><span class="sxs-lookup"><span data-stu-id="652d4-136">Text2</span></span>|  
  
 <span data-ttu-id="652d4-137">В качестве альтернативы рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="652d4-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="652d4-138">Процесс вывода создает **набор данных** с именем «documentElement», содержащий таблицу с именем «Element1».</span><span class="sxs-lookup"><span data-stu-id="652d4-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="652d4-139">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="652d4-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="652d4-140">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="652d4-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="652d4-141">attr1</span><span class="sxs-lookup"><span data-stu-id="652d4-141">attr1</span></span>|<span data-ttu-id="652d4-142">attr2</span><span class="sxs-lookup"><span data-stu-id="652d4-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="652d4-143">value1</span><span class="sxs-lookup"><span data-stu-id="652d4-143">value1</span></span>|<span data-ttu-id="652d4-144">value2</span><span class="sxs-lookup"><span data-stu-id="652d4-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="652d4-145">Повторяющиеся элементы</span><span class="sxs-lookup"><span data-stu-id="652d4-145">Repeating Elements</span></span>  
 <span data-ttu-id="652d4-146">Повторяющиеся элементы приводятся в выведенной таблице.</span><span class="sxs-lookup"><span data-stu-id="652d4-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="652d4-147">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="652d4-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="652d4-148">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="652d4-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="652d4-149">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="652d4-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="652d4-150">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="652d4-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="652d4-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="652d4-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="652d4-152">Text1</span><span class="sxs-lookup"><span data-stu-id="652d4-152">Text1</span></span>|  
|<span data-ttu-id="652d4-153">Text2</span><span class="sxs-lookup"><span data-stu-id="652d4-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="652d4-154">См. также</span><span class="sxs-lookup"><span data-stu-id="652d4-154">See also</span></span>

- [<span data-ttu-id="652d4-155">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="652d4-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="652d4-156">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="652d4-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="652d4-157">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="652d4-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="652d4-158">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="652d4-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="652d4-159">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="652d4-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="652d4-160">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="652d4-160">ADO.NET Overview</span></span>](../ado-net-overview.md)
