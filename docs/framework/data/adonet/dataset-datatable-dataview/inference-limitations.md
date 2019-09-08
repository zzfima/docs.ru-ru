---
title: Ограничения определения
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 10347abc5b01edb4ec6fbf97221d44f4bfb88f54
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784578"
---
# <a name="inference-limitations"></a><span data-ttu-id="aa179-102">Ограничения определения</span><span class="sxs-lookup"><span data-stu-id="aa179-102">Inference Limitations</span></span>
<span data-ttu-id="aa179-103">Процесс вывода схемы <xref:System.Data.DataSet> из XML-кода может приводиться в различных схемах в зависимости от XML-элементов в каждом документе.</span><span class="sxs-lookup"><span data-stu-id="aa179-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="aa179-104">Например, рассмотрим следующие XML-документы.</span><span class="sxs-lookup"><span data-stu-id="aa179-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="aa179-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="aa179-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="aa179-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="aa179-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="aa179-107">Для "document1" процесс вывода создает **набор данных** с именем "documentElement" и таблицу с именем "Element1", так как "Element1" является повторяющимся элементом.</span><span class="sxs-lookup"><span data-stu-id="aa179-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="aa179-108">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="aa179-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="aa179-109">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="aa179-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="aa179-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="aa179-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="aa179-111">Text1</span><span class="sxs-lookup"><span data-stu-id="aa179-111">Text1</span></span>|  
|<span data-ttu-id="aa179-112">Text2</span><span class="sxs-lookup"><span data-stu-id="aa179-112">Text2</span></span>|  
  
 <span data-ttu-id="aa179-113">Однако для "Document2" процесс вывода создает **набор данных** с именем "невдатасет" и таблицу с именем "documentElement".</span><span class="sxs-lookup"><span data-stu-id="aa179-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="aa179-114">Element1 выводится в виде столбца, потому что не имеет атрибутов и дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="aa179-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="aa179-115">**Объекте** невдатасет</span><span class="sxs-lookup"><span data-stu-id="aa179-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="aa179-116">**Таблица** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="aa179-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="aa179-117">Element1</span><span class="sxs-lookup"><span data-stu-id="aa179-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="aa179-118">Text1</span><span class="sxs-lookup"><span data-stu-id="aa179-118">Text1</span></span>|  
  
 <span data-ttu-id="aa179-119">Эти два XML-документа, возможно, должны были выдавать одну и ту же схему, но процесс вывода дает значительно различающиеся результаты в зависимости от элементов, содержащихся в каждом документе.</span><span class="sxs-lookup"><span data-stu-id="aa179-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="aa179-120">Чтобы избежать расхождений, которые могут возникнуть при формировании схемы из XML-документа, рекомендуется явно указать схему с помощью языка определения схемы XML (XSD) или сокращенных данных XML (XDR) при загрузке **набора данных** из XML.</span><span class="sxs-lookup"><span data-stu-id="aa179-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="aa179-121">Дополнительные сведения о явном указании схемы **набора данных** с XML-схемой см. [в разделе Наследование реляционной структуры набора данных из схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="aa179-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa179-122">См. также</span><span class="sxs-lookup"><span data-stu-id="aa179-122">See also</span></span>

- [<span data-ttu-id="aa179-123">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="aa179-123">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="aa179-124">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="aa179-124">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="aa179-125">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="aa179-125">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="aa179-126">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="aa179-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="aa179-127">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="aa179-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="aa179-128">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aa179-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
