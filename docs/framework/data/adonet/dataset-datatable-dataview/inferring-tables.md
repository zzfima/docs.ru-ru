---
title: Определение таблиц
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 84cee828f2d3c918a12e449da5b01a3d72d86333
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203514"
---
# <a name="inferring-tables"></a><span data-ttu-id="a8841-102">Определение таблиц</span><span class="sxs-lookup"><span data-stu-id="a8841-102">Inferring Tables</span></span>
<span data-ttu-id="a8841-103">При выведении схемы для <xref:System.Data.DataSet> из XML-документа ADO.NET сначала определяет, какой из XML-элементов представляет таблицы.</span><span class="sxs-lookup"><span data-stu-id="a8841-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="a8841-104">Следующие XML-структуры приводят к созданию таблицы для схемы **набора данных** :</span><span class="sxs-lookup"><span data-stu-id="a8841-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="a8841-105">Элементы с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="a8841-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="a8841-106">Элементы с дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="a8841-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="a8841-107">Повторяющиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="a8841-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="a8841-108">Элементы с атрибутами</span><span class="sxs-lookup"><span data-stu-id="a8841-108">Elements with Attributes</span></span>  
 <span data-ttu-id="a8841-109">Элементы с заданными атрибутами приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="a8841-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="a8841-110">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="a8841-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a8841-111">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="a8841-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="a8841-112">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a8841-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a8841-113">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="a8841-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a8841-114">attr1</span><span class="sxs-lookup"><span data-stu-id="a8841-114">attr1</span></span>|<span data-ttu-id="a8841-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="a8841-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="a8841-116">value1</span><span class="sxs-lookup"><span data-stu-id="a8841-116">value1</span></span>||  
|<span data-ttu-id="a8841-117">value2</span><span class="sxs-lookup"><span data-stu-id="a8841-117">value2</span></span>|<span data-ttu-id="a8841-118">Text1</span><span class="sxs-lookup"><span data-stu-id="a8841-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="a8841-119">Элементы с дочерними элементами</span><span class="sxs-lookup"><span data-stu-id="a8841-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="a8841-120">Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="a8841-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="a8841-121">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="a8841-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a8841-122">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="a8841-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="a8841-123">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a8841-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a8841-124">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="a8841-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a8841-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="a8841-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="a8841-126">Text1</span><span class="sxs-lookup"><span data-stu-id="a8841-126">Text1</span></span>|  
  
 <span data-ttu-id="a8841-127">Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="a8841-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="a8841-128">Если элемент документа не имеет атрибутов и не содержит дочерних элементов, которые будут выводиться как столбцы, то элемент выводится как **набор данных**.</span><span class="sxs-lookup"><span data-stu-id="a8841-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="a8841-129">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="a8841-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a8841-130">В процессе вывода создается таблица с именем DocumentElement.</span><span class="sxs-lookup"><span data-stu-id="a8841-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="a8841-131">**Объекте** невдатасет</span><span class="sxs-lookup"><span data-stu-id="a8841-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="a8841-132">**Таблица** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a8841-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="a8841-133">Element1</span><span class="sxs-lookup"><span data-stu-id="a8841-133">Element1</span></span>|<span data-ttu-id="a8841-134">Element2</span><span class="sxs-lookup"><span data-stu-id="a8841-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="a8841-135">Text1</span><span class="sxs-lookup"><span data-stu-id="a8841-135">Text1</span></span>|<span data-ttu-id="a8841-136">Text2</span><span class="sxs-lookup"><span data-stu-id="a8841-136">Text2</span></span>|  
  
 <span data-ttu-id="a8841-137">В качестве альтернативы рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="a8841-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a8841-138">Процесс вывода создает **набор данных** с именем «documentElement», содержащий таблицу с именем «Element1».</span><span class="sxs-lookup"><span data-stu-id="a8841-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="a8841-139">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a8841-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a8841-140">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="a8841-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a8841-141">attr1</span><span class="sxs-lookup"><span data-stu-id="a8841-141">attr1</span></span>|<span data-ttu-id="a8841-142">attr2</span><span class="sxs-lookup"><span data-stu-id="a8841-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="a8841-143">value1</span><span class="sxs-lookup"><span data-stu-id="a8841-143">value1</span></span>|<span data-ttu-id="a8841-144">value2</span><span class="sxs-lookup"><span data-stu-id="a8841-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="a8841-145">Повторяющиеся элементы</span><span class="sxs-lookup"><span data-stu-id="a8841-145">Repeating Elements</span></span>  
 <span data-ttu-id="a8841-146">Повторяющиеся элементы приводятся в выведенной таблице.</span><span class="sxs-lookup"><span data-stu-id="a8841-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="a8841-147">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="a8841-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a8841-148">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="a8841-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="a8841-149">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a8841-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a8841-150">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="a8841-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a8841-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="a8841-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="a8841-152">Text1</span><span class="sxs-lookup"><span data-stu-id="a8841-152">Text1</span></span>|  
|<span data-ttu-id="a8841-153">Text2</span><span class="sxs-lookup"><span data-stu-id="a8841-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8841-154">См. также</span><span class="sxs-lookup"><span data-stu-id="a8841-154">See also</span></span>

- [<span data-ttu-id="a8841-155">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="a8841-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="a8841-156">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="a8841-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="a8841-157">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="a8841-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="a8841-158">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="a8841-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="a8841-159">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="a8841-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="a8841-160">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8841-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
