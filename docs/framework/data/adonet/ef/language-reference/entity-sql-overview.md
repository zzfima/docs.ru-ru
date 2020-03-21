---
title: Общие сведения об Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 880b81f2b6d4c4b893d28c919490f88dfb2a42e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150380"
---
# <a name="entity-sql-overview"></a><span data-ttu-id="5944d-102">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5944d-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5944d-103">— это язык, похожий на S'L, который позволяет заставить заставить заранее о концептуальных моделях в рамочной системе entity.</span><span class="sxs-lookup"><span data-stu-id="5944d-103">is a SQL-like language that enables you to query conceptual models in the Entity Framework.</span></span> <span data-ttu-id="5944d-104">Концептуальные модели представляют данные как сущности и отношения и [!INCLUDE[esql](../../../../../../includes/esql-md.md)] позволяют заставить заинтересовать эти сущности и отношения в формате, знакомом тем, кто использовал S'L.</span><span class="sxs-lookup"><span data-stu-id="5944d-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  

 <span data-ttu-id="5944d-105">Рамочная система сущности работает с поставщиками данных для хранения данных для перевода генерических [!INCLUDE[esql](../../../../../../includes/esql-md.md)] в запросы, касающиеся данных.</span><span class="sxs-lookup"><span data-stu-id="5944d-105">The Entity Framework works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="5944d-106">Поставщик EntityClient предоставляет способ выполнения команды языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] на модели сущностей и получения разнообразных типов данных, в том числе скалярных результатов, результирующих наборов и графов объектов.</span><span class="sxs-lookup"><span data-stu-id="5944d-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="5944d-107">При создании объекта <xref:System.Data.EntityClient.EntityCommand> можно указать имя хранимой процедуры или текст запроса, присвоив строку запроса на языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] его свойству <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5944d-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="5944d-108"><xref:System.Data.EntityClient.EntityDataReader> предоставляет доступ к результатам выполнения <xref:System.Data.EntityClient.EntityCommand> к модели EDM.</span><span class="sxs-lookup"><span data-stu-id="5944d-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="5944d-109">Для выполнения команды, возвращающей значение <xref:System.Data.EntityClient.EntityDataReader>, нужно вызвать метод <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="5944d-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="5944d-110">Помимо поставщика EntityClient, рамочная система [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Entity Framework позволяет использовать для выполнения запросов в отношении концептуальной модели и возврата данных в качестве сильно набранных объектов CLR, которые являются экземплярами типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="5944d-110">In addition to the EntityClient provider, the Entity Framework enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="5944d-111">Для получения дополнительной информации [см.](../working-with-objects.md)</span><span class="sxs-lookup"><span data-stu-id="5944d-111">For more information, see [Working with Objects](../working-with-objects.md).</span></span>  
  
 <span data-ttu-id="5944d-112">В этом разделе приведены основные сведения о языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5944d-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5944d-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="5944d-113">In This Section</span></span>  
 [<span data-ttu-id="5944d-114">Отличия Entity SQL от Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5944d-114">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="5944d-115">Краткий справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5944d-115">Entity SQL Quick Reference</span></span>](entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="5944d-116">Система типов</span><span class="sxs-lookup"><span data-stu-id="5944d-116">Type System</span></span>](type-system-entity-sql.md)  
  
 [<span data-ttu-id="5944d-117">Определения типов</span><span class="sxs-lookup"><span data-stu-id="5944d-117">Type Definitions</span></span>](type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="5944d-118">Сборка типов</span><span class="sxs-lookup"><span data-stu-id="5944d-118">Constructing Types</span></span>](constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="5944d-119">Кэширование плана запроса</span><span class="sxs-lookup"><span data-stu-id="5944d-119">Query Plan Caching</span></span>](query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="5944d-120">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="5944d-120">Namespaces</span></span>](namespaces-entity-sql.md)  
  
 [<span data-ttu-id="5944d-121">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="5944d-121">Identifiers</span></span>](identifiers-entity-sql.md)  
  
 [<span data-ttu-id="5944d-122">Параметры</span><span class="sxs-lookup"><span data-stu-id="5944d-122">Parameters</span></span>](parameters-entity-sql.md)  
  
 [<span data-ttu-id="5944d-123">Переменные</span><span class="sxs-lookup"><span data-stu-id="5944d-123">Variables</span></span>](variables-entity-sql.md)  
  
 [<span data-ttu-id="5944d-124">Неподдерживаемые выражения</span><span class="sxs-lookup"><span data-stu-id="5944d-124">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="5944d-125">Литералы</span><span class="sxs-lookup"><span data-stu-id="5944d-125">Literals</span></span>](literals-entity-sql.md)  
  
 [<span data-ttu-id="5944d-126">Литералы NULL и вывод типов</span><span class="sxs-lookup"><span data-stu-id="5944d-126">Null Literals and Type Inference</span></span>](null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="5944d-127">Набор символов ввода</span><span class="sxs-lookup"><span data-stu-id="5944d-127">Input Character Set</span></span>](input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="5944d-128">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="5944d-128">Query Expressions</span></span>](query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="5944d-129">Функции</span><span class="sxs-lookup"><span data-stu-id="5944d-129">Functions</span></span>](functions-entity-sql.md)  
  
 [<span data-ttu-id="5944d-130">Приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="5944d-130">Operator Precedence</span></span>](operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="5944d-131">Разбиение по страницам</span><span class="sxs-lookup"><span data-stu-id="5944d-131">Paging</span></span>](paging-entity-sql.md)  
  
 [<span data-ttu-id="5944d-132">Семантика сравнения</span><span class="sxs-lookup"><span data-stu-id="5944d-132">Comparison Semantics</span></span>](comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="5944d-133">Составление вложенных запросов Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5944d-133">Composing Nested Entity SQL Queries</span></span>](composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="5944d-134">Допускающие значения NULL структурированные типы</span><span class="sxs-lookup"><span data-stu-id="5944d-134">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="5944d-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5944d-135">See also</span></span>

- [<span data-ttu-id="5944d-136">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5944d-136">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="5944d-137">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5944d-137">Entity SQL Language</span></span>](entity-sql-language.md)
- [<span data-ttu-id="5944d-138">Спецификации CSDL, SSDL и MSL</span><span class="sxs-lookup"><span data-stu-id="5944d-138">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
