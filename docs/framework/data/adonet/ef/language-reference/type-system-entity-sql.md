---
title: Система типов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: d86c97834b9cc6698da8664ff2a09ceda7cc0043
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64641235"
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="456f5-102">Система типов (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="456f5-102">Type System (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="456f5-103">поддерживает несколько типов:</span><span class="sxs-lookup"><span data-stu-id="456f5-103">supports a number of types:</span></span>  
  
- <span data-ttu-id="456f5-104">Типы-примитивы (простые типы), такие как `Int32` и `String.`</span><span class="sxs-lookup"><span data-stu-id="456f5-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
- <span data-ttu-id="456f5-105">Номинальные типы, которые определяются в схеме, например <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> и <xref:System.Data.Metadata.Edm.RelationshipType>.</span><span class="sxs-lookup"><span data-stu-id="456f5-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
- <span data-ttu-id="456f5-106">Анонимные типы, которые явно не определяются в схеме: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> и <xref:System.Data.Metadata.Edm.RefType>.</span><span class="sxs-lookup"><span data-stu-id="456f5-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="456f5-107">В этом разделе рассматриваются анонимные типы, которые не определены в схеме явно, но поддерживаются языком Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="456f5-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by Entity SQL.</span></span> <span data-ttu-id="456f5-108">Сведения о типах-примитивах и номинальных см. в разделе [типов концептуальной модели (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span><span class="sxs-lookup"><span data-stu-id="456f5-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="456f5-109">Строки</span><span class="sxs-lookup"><span data-stu-id="456f5-109">Rows</span></span>  
 <span data-ttu-id="456f5-110">Структура строки зависит от последовательности типизированных и именованных элементов, из которых состоит строка.</span><span class="sxs-lookup"><span data-stu-id="456f5-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="456f5-111">Тип строки не имеет идентификатора и не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="456f5-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="456f5-112">Экземпляры строк одинакового типа считаются равными, если равны соответствующие элементы этих строк.</span><span class="sxs-lookup"><span data-stu-id="456f5-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="456f5-113">Со строками не связаны операции, отличные от проверки равнозначности их структуры, к тому же они не имеют эквивалентов в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="456f5-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="456f5-114">Запросы могут возвращать структуры, содержащие строки или коллекции строк.</span><span class="sxs-lookup"><span data-stu-id="456f5-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="456f5-115">API определения привязки между запросами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] и базовым языком определяет способ реализации строк в запросе, вырабатывающем этот результат.</span><span class="sxs-lookup"><span data-stu-id="456f5-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="456f5-116">Сведения о создании экземпляра строки, см. в разделе [типов, создав](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="456f5-116">For information on how to construct a row instance, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="456f5-117">Коллекции</span><span class="sxs-lookup"><span data-stu-id="456f5-117">Collections</span></span>  
 <span data-ttu-id="456f5-118">Типы коллекций представляют ноль и более экземпляров других объектов.</span><span class="sxs-lookup"><span data-stu-id="456f5-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="456f5-119">Сведения о способах создания коллекции, см. в разделе [типов, создав](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="456f5-119">For information on how to construct collection, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="456f5-120">Ссылки</span><span class="sxs-lookup"><span data-stu-id="456f5-120">References</span></span>  
 <span data-ttu-id="456f5-121">Ссылка - это логический указатель на отдельную сущность в определенном наборе сущностей.</span><span class="sxs-lookup"><span data-stu-id="456f5-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 <span data-ttu-id="456f5-122">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает следующие операторы для конструирования, деконструирования и перехода по ссылкам.</span><span class="sxs-lookup"><span data-stu-id="456f5-122">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
- [<span data-ttu-id="456f5-123">REF</span><span class="sxs-lookup"><span data-stu-id="456f5-123">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
  
- [<span data-ttu-id="456f5-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="456f5-124">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
  
- [<span data-ttu-id="456f5-125">KEY</span><span class="sxs-lookup"><span data-stu-id="456f5-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
  
- [<span data-ttu-id="456f5-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="456f5-126">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
  
 <span data-ttu-id="456f5-127">По ссылке можно переходить с помощью оператора доступа к элементам «точка» (`.`).</span><span class="sxs-lookup"><span data-stu-id="456f5-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="456f5-128">В следующем фрагменте извлекается свойство Id (объекта Order) путем перехода по свойству r (сокращение от reference).</span><span class="sxs-lookup"><span data-stu-id="456f5-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 <span data-ttu-id="456f5-129">Если ссылка имеет значение NULL или цель ссылки не существует, результатом становится NULL.</span><span class="sxs-lookup"><span data-stu-id="456f5-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="456f5-130">См. также</span><span class="sxs-lookup"><span data-stu-id="456f5-130">See also</span></span>

- [<span data-ttu-id="456f5-131">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="456f5-131">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="456f5-132">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="456f5-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="456f5-133">CAST</span><span class="sxs-lookup"><span data-stu-id="456f5-133">CAST</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)
- [<span data-ttu-id="456f5-134">Спецификации CSDL, SSDL и MSL</span><span class="sxs-lookup"><span data-stu-id="456f5-134">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
