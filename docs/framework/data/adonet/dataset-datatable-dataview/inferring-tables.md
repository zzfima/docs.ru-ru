---
title: Определение таблиц
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 38709f91e01c7f85d9e8482bdd49bc0892121f09
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2018
ms.locfileid: "43332857"
---
# <a name="inferring-tables"></a><span data-ttu-id="c38ec-102">Определение таблиц</span><span class="sxs-lookup"><span data-stu-id="c38ec-102">Inferring Tables</span></span>
<span data-ttu-id="c38ec-103">При выведении схемы для <xref:System.Data.DataSet> из XML-документа ADO.NET сначала определяет, какой из XML-элементов представляет таблицы.</span><span class="sxs-lookup"><span data-stu-id="c38ec-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="c38ec-104">Следующие структуры XML приводятся в таблице для **набора данных** схемы:</span><span class="sxs-lookup"><span data-stu-id="c38ec-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="c38ec-105">Элементы с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="c38ec-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="c38ec-106">Элементы с дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="c38ec-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="c38ec-107">Повторяющиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="c38ec-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="c38ec-108">Элементы с атрибутами</span><span class="sxs-lookup"><span data-stu-id="c38ec-108">Elements with Attributes</span></span>  
 <span data-ttu-id="c38ec-109">Элементы с заданными атрибутами приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="c38ec-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="c38ec-110">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="c38ec-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c38ec-111">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="c38ec-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="c38ec-112">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c38ec-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c38ec-113">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="c38ec-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c38ec-114">attr1</span><span class="sxs-lookup"><span data-stu-id="c38ec-114">attr1</span></span>|<span data-ttu-id="c38ec-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="c38ec-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="c38ec-116">value1</span><span class="sxs-lookup"><span data-stu-id="c38ec-116">value1</span></span>||  
|<span data-ttu-id="c38ec-117">value2</span><span class="sxs-lookup"><span data-stu-id="c38ec-117">value2</span></span>|<span data-ttu-id="c38ec-118">Text1</span><span class="sxs-lookup"><span data-stu-id="c38ec-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="c38ec-119">Элементы с дочерними элементами</span><span class="sxs-lookup"><span data-stu-id="c38ec-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="c38ec-120">Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="c38ec-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="c38ec-121">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="c38ec-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c38ec-122">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="c38ec-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="c38ec-123">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c38ec-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c38ec-124">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="c38ec-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c38ec-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="c38ec-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="c38ec-126">Text1</span><span class="sxs-lookup"><span data-stu-id="c38ec-126">Text1</span></span>|  
  
 <span data-ttu-id="c38ec-127">Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="c38ec-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="c38ec-128">Если элемент документа не имеет атрибутов и дочерних элементов, которые выводились бы как столбцы, то элемент выводится как **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="c38ec-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="c38ec-129">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="c38ec-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c38ec-130">В процессе вывода создается таблица с именем DocumentElement.</span><span class="sxs-lookup"><span data-stu-id="c38ec-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="c38ec-131">**Набор данных:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="c38ec-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="c38ec-132">**Таблица:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c38ec-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="c38ec-133">Element1</span><span class="sxs-lookup"><span data-stu-id="c38ec-133">Element1</span></span>|<span data-ttu-id="c38ec-134">Element2</span><span class="sxs-lookup"><span data-stu-id="c38ec-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="c38ec-135">Text1</span><span class="sxs-lookup"><span data-stu-id="c38ec-135">Text1</span></span>|<span data-ttu-id="c38ec-136">Text2</span><span class="sxs-lookup"><span data-stu-id="c38ec-136">Text2</span></span>|  
  
 <span data-ttu-id="c38ec-137">В качестве альтернативы рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="c38ec-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c38ec-138">В процессе вывода создается **набора данных** с именем «DocumentElement», который содержит таблицу с именем «Элемент1».</span><span class="sxs-lookup"><span data-stu-id="c38ec-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="c38ec-139">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c38ec-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c38ec-140">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="c38ec-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c38ec-141">attr1</span><span class="sxs-lookup"><span data-stu-id="c38ec-141">attr1</span></span>|<span data-ttu-id="c38ec-142">attr2</span><span class="sxs-lookup"><span data-stu-id="c38ec-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="c38ec-143">value1</span><span class="sxs-lookup"><span data-stu-id="c38ec-143">value1</span></span>|<span data-ttu-id="c38ec-144">value2</span><span class="sxs-lookup"><span data-stu-id="c38ec-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="c38ec-145">Повторяющиеся элементы</span><span class="sxs-lookup"><span data-stu-id="c38ec-145">Repeating Elements</span></span>  
 <span data-ttu-id="c38ec-146">Повторяющиеся элементы приводятся в выведенной таблице.</span><span class="sxs-lookup"><span data-stu-id="c38ec-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="c38ec-147">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="c38ec-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c38ec-148">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="c38ec-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="c38ec-149">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c38ec-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c38ec-150">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="c38ec-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c38ec-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="c38ec-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="c38ec-152">Text1</span><span class="sxs-lookup"><span data-stu-id="c38ec-152">Text1</span></span>|  
|<span data-ttu-id="c38ec-153">Text2</span><span class="sxs-lookup"><span data-stu-id="c38ec-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c38ec-154">См. также</span><span class="sxs-lookup"><span data-stu-id="c38ec-154">See Also</span></span>  
 [<span data-ttu-id="c38ec-155">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="c38ec-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="c38ec-156">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="c38ec-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="c38ec-157">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="c38ec-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="c38ec-158">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="c38ec-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="c38ec-159">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="c38ec-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="c38ec-160">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c38ec-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
