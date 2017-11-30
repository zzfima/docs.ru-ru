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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ae6f7827b7206544ff7547cc04f44b7cda34bef8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-tables"></a><span data-ttu-id="6a105-102">Определение таблиц</span><span class="sxs-lookup"><span data-stu-id="6a105-102">Inferring Tables</span></span>
<span data-ttu-id="6a105-103">При выведении схемы для <xref:System.Data.DataSet> из XML-документа ADO.NET сначала определяет, какой из XML-элементов представляет таблицы.</span><span class="sxs-lookup"><span data-stu-id="6a105-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="6a105-104">Следующие структуры XML приводятся в таблице для **DataSet** схемы:</span><span class="sxs-lookup"><span data-stu-id="6a105-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="6a105-105">Элементы с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="6a105-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="6a105-106">Элементы с дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="6a105-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="6a105-107">Повторяющиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="6a105-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="6a105-108">Элементы с атрибутами</span><span class="sxs-lookup"><span data-stu-id="6a105-108">Elements with Attributes</span></span>  
 <span data-ttu-id="6a105-109">Элементы с заданными атрибутами приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="6a105-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="6a105-110">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="6a105-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="6a105-111">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="6a105-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="6a105-112">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="6a105-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="6a105-113">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="6a105-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="6a105-114">attr1</span><span class="sxs-lookup"><span data-stu-id="6a105-114">attr1</span></span>|<span data-ttu-id="6a105-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="6a105-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="6a105-116">value1</span><span class="sxs-lookup"><span data-stu-id="6a105-116">value1</span></span>||  
|<span data-ttu-id="6a105-117">value2</span><span class="sxs-lookup"><span data-stu-id="6a105-117">value2</span></span>|<span data-ttu-id="6a105-118">Text1</span><span class="sxs-lookup"><span data-stu-id="6a105-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="6a105-119">Элементы с дочерними элементами</span><span class="sxs-lookup"><span data-stu-id="6a105-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="6a105-120">Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="6a105-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="6a105-121">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="6a105-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="6a105-122">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="6a105-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="6a105-123">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="6a105-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="6a105-124">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="6a105-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="6a105-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="6a105-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="6a105-126">Text1</span><span class="sxs-lookup"><span data-stu-id="6a105-126">Text1</span></span>|  
  
 <span data-ttu-id="6a105-127">Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="6a105-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="6a105-128">Если элемент документа не имеет атрибутов и дочерних элементов, которые можно вывести в виде столбцов, то элемент выводится как **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="6a105-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="6a105-129">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="6a105-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="6a105-130">В процессе вывода создается таблица с именем DocumentElement.</span><span class="sxs-lookup"><span data-stu-id="6a105-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="6a105-131">**Набор данных:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="6a105-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="6a105-132">**Таблица:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="6a105-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="6a105-133">Element1</span><span class="sxs-lookup"><span data-stu-id="6a105-133">Element1</span></span>|<span data-ttu-id="6a105-134">Element2</span><span class="sxs-lookup"><span data-stu-id="6a105-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="6a105-135">Text1</span><span class="sxs-lookup"><span data-stu-id="6a105-135">Text1</span></span>|<span data-ttu-id="6a105-136">Text2</span><span class="sxs-lookup"><span data-stu-id="6a105-136">Text2</span></span>|  
  
 <span data-ttu-id="6a105-137">В качестве альтернативы рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="6a105-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="6a105-138">Процесс вывода дает **набора данных** с именем «DocumentElement», содержащий таблицу с именем «Элемент1».</span><span class="sxs-lookup"><span data-stu-id="6a105-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="6a105-139">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="6a105-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="6a105-140">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="6a105-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="6a105-141">attr1</span><span class="sxs-lookup"><span data-stu-id="6a105-141">attr1</span></span>|<span data-ttu-id="6a105-142">attr2</span><span class="sxs-lookup"><span data-stu-id="6a105-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="6a105-143">value1</span><span class="sxs-lookup"><span data-stu-id="6a105-143">value1</span></span>|<span data-ttu-id="6a105-144">value2</span><span class="sxs-lookup"><span data-stu-id="6a105-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="6a105-145">Повторяющиеся элементы</span><span class="sxs-lookup"><span data-stu-id="6a105-145">Repeating Elements</span></span>  
 <span data-ttu-id="6a105-146">Повторяющиеся элементы приводятся в выведенной таблице.</span><span class="sxs-lookup"><span data-stu-id="6a105-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="6a105-147">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="6a105-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="6a105-148">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="6a105-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="6a105-149">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="6a105-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="6a105-150">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="6a105-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="6a105-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="6a105-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="6a105-152">Text1</span><span class="sxs-lookup"><span data-stu-id="6a105-152">Text1</span></span>|  
|<span data-ttu-id="6a105-153">Text2</span><span class="sxs-lookup"><span data-stu-id="6a105-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a105-154">См. также</span><span class="sxs-lookup"><span data-stu-id="6a105-154">See Also</span></span>  
 [<span data-ttu-id="6a105-155">Определение реляционной структуры набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="6a105-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="6a105-156">Загрузка набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="6a105-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="6a105-157">Загрузка сведений о схеме набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="6a105-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="6a105-158">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="6a105-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="6a105-159">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="6a105-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="6a105-160">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6a105-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
