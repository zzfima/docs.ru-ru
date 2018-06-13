---
title: Определение таблиц
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: b14cbc39b02136ac7f226faf2636a69ac072f529
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757831"
---
# <a name="inferring-tables"></a><span data-ttu-id="06409-102">Определение таблиц</span><span class="sxs-lookup"><span data-stu-id="06409-102">Inferring Tables</span></span>
<span data-ttu-id="06409-103">При выведении схемы для <xref:System.Data.DataSet> из XML-документа ADO.NET сначала определяет, какой из XML-элементов представляет таблицы.</span><span class="sxs-lookup"><span data-stu-id="06409-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="06409-104">Следующие структуры XML приводятся в таблице для **DataSet** схемы:</span><span class="sxs-lookup"><span data-stu-id="06409-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="06409-105">Элементы с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="06409-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="06409-106">Элементы с дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="06409-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="06409-107">Повторяющиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="06409-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="06409-108">Элементы с атрибутами</span><span class="sxs-lookup"><span data-stu-id="06409-108">Elements with Attributes</span></span>  
 <span data-ttu-id="06409-109">Элементы с заданными атрибутами приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="06409-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="06409-110">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="06409-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="06409-111">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="06409-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="06409-112">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="06409-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="06409-113">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="06409-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="06409-114">attr1</span><span class="sxs-lookup"><span data-stu-id="06409-114">attr1</span></span>|<span data-ttu-id="06409-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="06409-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="06409-116">value1</span><span class="sxs-lookup"><span data-stu-id="06409-116">value1</span></span>||  
|<span data-ttu-id="06409-117">value2</span><span class="sxs-lookup"><span data-stu-id="06409-117">value2</span></span>|<span data-ttu-id="06409-118">Text1</span><span class="sxs-lookup"><span data-stu-id="06409-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="06409-119">Элементы с дочерними элементами</span><span class="sxs-lookup"><span data-stu-id="06409-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="06409-120">Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="06409-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="06409-121">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="06409-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="06409-122">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="06409-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="06409-123">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="06409-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="06409-124">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="06409-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="06409-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="06409-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="06409-126">Text1</span><span class="sxs-lookup"><span data-stu-id="06409-126">Text1</span></span>|  
  
 <span data-ttu-id="06409-127">Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="06409-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="06409-128">Если элемент документа не имеет атрибутов и дочерних элементов, которые можно вывести в виде столбцов, то элемент выводится как **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="06409-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="06409-129">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="06409-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="06409-130">В процессе вывода создается таблица с именем DocumentElement.</span><span class="sxs-lookup"><span data-stu-id="06409-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="06409-131">**Набор данных:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="06409-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="06409-132">**Таблица:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="06409-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="06409-133">Element1</span><span class="sxs-lookup"><span data-stu-id="06409-133">Element1</span></span>|<span data-ttu-id="06409-134">Element2</span><span class="sxs-lookup"><span data-stu-id="06409-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="06409-135">Text1</span><span class="sxs-lookup"><span data-stu-id="06409-135">Text1</span></span>|<span data-ttu-id="06409-136">Text2</span><span class="sxs-lookup"><span data-stu-id="06409-136">Text2</span></span>|  
  
 <span data-ttu-id="06409-137">В качестве альтернативы рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="06409-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="06409-138">Процесс вывода дает **набора данных** с именем «DocumentElement», содержащий таблицу с именем «Элемент1».</span><span class="sxs-lookup"><span data-stu-id="06409-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="06409-139">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="06409-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="06409-140">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="06409-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="06409-141">attr1</span><span class="sxs-lookup"><span data-stu-id="06409-141">attr1</span></span>|<span data-ttu-id="06409-142">attr2</span><span class="sxs-lookup"><span data-stu-id="06409-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="06409-143">value1</span><span class="sxs-lookup"><span data-stu-id="06409-143">value1</span></span>|<span data-ttu-id="06409-144">value2</span><span class="sxs-lookup"><span data-stu-id="06409-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="06409-145">Повторяющиеся элементы</span><span class="sxs-lookup"><span data-stu-id="06409-145">Repeating Elements</span></span>  
 <span data-ttu-id="06409-146">Повторяющиеся элементы приводятся в выведенной таблице.</span><span class="sxs-lookup"><span data-stu-id="06409-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="06409-147">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="06409-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="06409-148">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="06409-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="06409-149">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="06409-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="06409-150">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="06409-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="06409-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="06409-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="06409-152">Text1</span><span class="sxs-lookup"><span data-stu-id="06409-152">Text1</span></span>|  
|<span data-ttu-id="06409-153">Text2</span><span class="sxs-lookup"><span data-stu-id="06409-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06409-154">См. также</span><span class="sxs-lookup"><span data-stu-id="06409-154">See Also</span></span>  
 [<span data-ttu-id="06409-155">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="06409-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="06409-156">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="06409-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="06409-157">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="06409-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="06409-158">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="06409-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="06409-159">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="06409-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="06409-160">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="06409-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
