---
title: "Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9ac8e64c02d96450d41233cfbe65e1db839df9e7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="534b9-102">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="534b9-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="534b9-103">Язык XSD позволяет задавать ограничения применительно к элементам и атрибутам, которые он определяет.</span><span class="sxs-lookup"><span data-stu-id="534b9-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="534b9-104">При сопоставлении XML-схемы с реляционной схемой в <xref:System.Data.DataSet>, ограничения XML-схемы сопоставляются с соответствующими реляционными ограничениями таблиц и столбцов в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="534b9-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="534b9-105">В этом разделе рассматривается сопоставление следующих ограничений схемы XML:</span><span class="sxs-lookup"><span data-stu-id="534b9-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
-   <span data-ttu-id="534b9-106">Ограничение уникальности, заданное с помощью **уникальный** элемента.</span><span class="sxs-lookup"><span data-stu-id="534b9-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
-   <span data-ttu-id="534b9-107">Ограничение ключа, заданное с помощью **ключ** элемента.</span><span class="sxs-lookup"><span data-stu-id="534b9-107">The key constraint specified using the **key** element.</span></span>  
  
-   <span data-ttu-id="534b9-108">Ограничение keyref, заданное с помощью **keyref** элемента.</span><span class="sxs-lookup"><span data-stu-id="534b9-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="534b9-109">С помощью ограничения элемента или атрибута задаются определенные ограничения значений элемента в любом экземпляре документа.</span><span class="sxs-lookup"><span data-stu-id="534b9-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="534b9-110">Например, ограничение по ключу **CustomerID** дочерний элемент элемента **клиента** элемента в схеме указывает, что значения **CustomerID** дочерний элемент должен быть Уникальный в любом экземпляре документа и не допускаются значения null.</span><span class="sxs-lookup"><span data-stu-id="534b9-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="534b9-111">Ограничения также можно указывать между элементами и атрибутами документа для установления связи внутри документа.</span><span class="sxs-lookup"><span data-stu-id="534b9-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="534b9-112">Ограничения key и keyref используются в схеме для указания ограничения внутри документа, что приводит к созданию связи между элементами и атрибутами документа.</span><span class="sxs-lookup"><span data-stu-id="534b9-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="534b9-113">Процесс сопоставления преобразует ограничения схемы в соответствующие ограничения таблицы, созданные в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="534b9-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="534b9-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="534b9-114">In This Section</span></span>  
 [<span data-ttu-id="534b9-115">Сопоставление уникальных ограничений XML-схемы (XSD) набора данных</span><span class="sxs-lookup"><span data-stu-id="534b9-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="534b9-116">Описывает элементы схемы XML, используемые для создания ограничений unique в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="534b9-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="534b9-117">Сопоставление ключевых ограничений XML-схемы (XSD) для ограничения набора данных</span><span class="sxs-lookup"><span data-stu-id="534b9-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="534b9-118">Описывает элементы схемы XML, используемые для создания ключа ограничений (ограничения unique, где недопустимы значения null) в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="534b9-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="534b9-119">Сопоставление ограничений схемы XML (XSD) keyref набора данных</span><span class="sxs-lookup"><span data-stu-id="534b9-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="534b9-120">Описывает элементы схемы XML, используемые для создания keyref ограничений (внешний ключ) в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="534b9-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="534b9-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="534b9-121">Related Sections</span></span>  
 [<span data-ttu-id="534b9-122">Наследование реляционной структуры набора данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="534b9-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="534b9-123">Описывает реляционную структуру или схему, из **набора данных** , созданную из схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="534b9-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="534b9-124">Создание отношений наборов данных из XML-схемы (XSD)</span><span class="sxs-lookup"><span data-stu-id="534b9-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="534b9-125">Описывает элементы схемы XML, используемых для создания связей между столбцами таблиц в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="534b9-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534b9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="534b9-126">See Also</span></span>  
 [<span data-ttu-id="534b9-127">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="534b9-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
