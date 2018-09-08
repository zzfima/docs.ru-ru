---
title: Ограничения определения
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: d113df98cdd339300b3e75ceda49a56d4f346d3c
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44137230"
---
# <a name="inference-limitations"></a><span data-ttu-id="ebf59-102">Ограничения определения</span><span class="sxs-lookup"><span data-stu-id="ebf59-102">Inference Limitations</span></span>
<span data-ttu-id="ebf59-103">Процесс вывода схемы <xref:System.Data.DataSet> из XML-кода может приводиться в различных схемах в зависимости от XML-элементов в каждом документе.</span><span class="sxs-lookup"><span data-stu-id="ebf59-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="ebf59-104">Например, рассмотрим следующие XML-документы.</span><span class="sxs-lookup"><span data-stu-id="ebf59-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="ebf59-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="ebf59-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="ebf59-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="ebf59-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="ebf59-107">Для «Документ1», в процессе вывода создается **набора данных** с именем «DocumentElement» и таблица с именем «Элемент1», так как «Элемент1» является повторяющимся элементом.</span><span class="sxs-lookup"><span data-stu-id="ebf59-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="ebf59-108">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="ebf59-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="ebf59-109">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="ebf59-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="ebf59-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="ebf59-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="ebf59-111">Text1</span><span class="sxs-lookup"><span data-stu-id="ebf59-111">Text1</span></span>|  
|<span data-ttu-id="ebf59-112">Text2</span><span class="sxs-lookup"><span data-stu-id="ebf59-112">Text2</span></span>|  
  
 <span data-ttu-id="ebf59-113">Тем не менее, для «Document2», в процессе вывода создается **набора данных** с именем «NewDataSet» и таблица с именем «DocumentElement.»</span><span class="sxs-lookup"><span data-stu-id="ebf59-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="ebf59-114">Element1 выводится в виде столбца, потому что не имеет атрибутов и дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="ebf59-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="ebf59-115">**Набор данных:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="ebf59-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="ebf59-116">**Таблица:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="ebf59-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="ebf59-117">Element1</span><span class="sxs-lookup"><span data-stu-id="ebf59-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="ebf59-118">Text1</span><span class="sxs-lookup"><span data-stu-id="ebf59-118">Text1</span></span>|  
  
 <span data-ttu-id="ebf59-119">Эти два XML-документа, возможно, должны были выдавать одну и ту же схему, но процесс вывода дает значительно различающиеся результаты в зависимости от элементов, содержащихся в каждом документе.</span><span class="sxs-lookup"><span data-stu-id="ebf59-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="ebf59-120">Чтобы избежать несоответствий, которые могут произойти при создании схемы из XML-документа, рекомендуется явно задавать схему с помощью языка определения схемы XML (XSD) или XML-Data Reduced (XDR), при загрузке **набора данных** из XML-ФАЙЛ.</span><span class="sxs-lookup"><span data-stu-id="ebf59-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="ebf59-121">Дополнительные сведения о явном задании **набора данных** схему со схемой XML, см. в разделе [наследование реляционной структуры DataSet из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="ebf59-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf59-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ebf59-122">See Also</span></span>  
 [<span data-ttu-id="ebf59-123">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="ebf59-123">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="ebf59-124">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="ebf59-124">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="ebf59-125">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="ebf59-125">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="ebf59-126">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="ebf59-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="ebf59-127">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="ebf59-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="ebf59-128">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ebf59-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
