---
title: "Определение таблиц"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2c00dd11d4d93e5d3b0e2f1c3b75765056a10cab
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-tables"></a><span data-ttu-id="2cd4d-102">Определение таблиц</span><span class="sxs-lookup"><span data-stu-id="2cd4d-102">Inferring Tables</span></span>
<span data-ttu-id="2cd4d-103">При выведении схемы для <xref:System.Data.DataSet> из XML-документа ADO.NET сначала определяет, какой из XML-элементов представляет таблицы.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="2cd4d-104">Следующие структуры XML приводятся в таблице для **DataSet** схемы:</span><span class="sxs-lookup"><span data-stu-id="2cd4d-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="2cd4d-105">Элементы с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="2cd4d-106">Элементы с дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="2cd4d-107">Повторяющиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="2cd4d-108">Элементы с атрибутами</span><span class="sxs-lookup"><span data-stu-id="2cd4d-108">Elements with Attributes</span></span>  
 <span data-ttu-id="2cd4d-109">Элементы с заданными атрибутами приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="2cd4d-110">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="2cd4d-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2cd4d-111">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="2cd4d-112">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2cd4d-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2cd4d-113">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2cd4d-114">attr1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-114">attr1</span></span>|<span data-ttu-id="2cd4d-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="2cd4d-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="2cd4d-116">value1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-116">value1</span></span>||  
|<span data-ttu-id="2cd4d-117">value2</span><span class="sxs-lookup"><span data-stu-id="2cd4d-117">value2</span></span>|<span data-ttu-id="2cd4d-118">Text1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="2cd4d-119">Элементы с дочерними элементами</span><span class="sxs-lookup"><span data-stu-id="2cd4d-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="2cd4d-120">Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="2cd4d-121">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="2cd4d-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2cd4d-122">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="2cd4d-123">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2cd4d-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2cd4d-124">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2cd4d-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="2cd4d-126">Text1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-126">Text1</span></span>|  
  
 <span data-ttu-id="2cd4d-127">Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="2cd4d-128">Если элемент документа не имеет атрибутов и дочерних элементов, которые можно вывести в виде столбцов, то элемент выводится как **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="2cd4d-129">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="2cd4d-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2cd4d-130">В процессе вывода создается таблица с именем DocumentElement.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="2cd4d-131">**Набор данных:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="2cd4d-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="2cd4d-132">**Таблица:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2cd4d-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="2cd4d-133">Element1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-133">Element1</span></span>|<span data-ttu-id="2cd4d-134">Element2</span><span class="sxs-lookup"><span data-stu-id="2cd4d-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="2cd4d-135">Text1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-135">Text1</span></span>|<span data-ttu-id="2cd4d-136">Text2</span><span class="sxs-lookup"><span data-stu-id="2cd4d-136">Text2</span></span>|  
  
 <span data-ttu-id="2cd4d-137">В качестве альтернативы рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="2cd4d-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2cd4d-138">Процесс вывода дает **набора данных** с именем «DocumentElement», содержащий таблицу с именем «Элемент1».</span><span class="sxs-lookup"><span data-stu-id="2cd4d-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="2cd4d-139">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2cd4d-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2cd4d-140">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2cd4d-141">attr1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-141">attr1</span></span>|<span data-ttu-id="2cd4d-142">attr2</span><span class="sxs-lookup"><span data-stu-id="2cd4d-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="2cd4d-143">value1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-143">value1</span></span>|<span data-ttu-id="2cd4d-144">value2</span><span class="sxs-lookup"><span data-stu-id="2cd4d-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="2cd4d-145">Повторяющиеся элементы</span><span class="sxs-lookup"><span data-stu-id="2cd4d-145">Repeating Elements</span></span>  
 <span data-ttu-id="2cd4d-146">Повторяющиеся элементы приводятся в выведенной таблице.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="2cd4d-147">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="2cd4d-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2cd4d-148">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="2cd4d-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="2cd4d-149">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2cd4d-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2cd4d-150">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2cd4d-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="2cd4d-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="2cd4d-152">Text1</span><span class="sxs-lookup"><span data-stu-id="2cd4d-152">Text1</span></span>|  
|<span data-ttu-id="2cd4d-153">Text2</span><span class="sxs-lookup"><span data-stu-id="2cd4d-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2cd4d-154">См. также</span><span class="sxs-lookup"><span data-stu-id="2cd4d-154">See Also</span></span>  
 [<span data-ttu-id="2cd4d-155">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="2cd4d-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="2cd4d-156">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="2cd4d-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="2cd4d-157">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="2cd4d-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="2cd4d-158">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="2cd4d-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="2cd4d-159">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="2cd4d-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="2cd4d-160">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2cd4d-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
