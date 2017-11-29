---
title: "Общие сведения об Entity SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 301a934cad59b14d1a65a1e98247490d578e6866
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="entity-sql-overview"></a><span data-ttu-id="15d85-102">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="15d85-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="15d85-103"> представляет собой язык, подобный языку SQL, который позволяет выполнять запросы к концептуальным моделям в [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15d85-103"> is a SQL-like language that enables you to query conceptual models in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="15d85-104">Концептуальные модели представляют данные в виде сущностей и связей, и [!INCLUDE[esql](../../../../../../includes/esql-md.md)] позволяет выполнять запросы этим сущностям и связям в формате, который хорошо знаком тем, кто использовал SQL.</span><span class="sxs-lookup"><span data-stu-id="15d85-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  
  
 <span data-ttu-id="15d85-105">Платформа [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] работает с зависящими от хранилища поставщиками данных в целях преобразования общих конструкций языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] в специфичные для хранилища запросы.</span><span class="sxs-lookup"><span data-stu-id="15d85-105">The [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="15d85-106">Поставщик EntityClient предоставляет способ выполнения команды языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] на модели сущностей и получения разнообразных типов данных, в том числе скалярных результатов, результирующих наборов и графов объектов.</span><span class="sxs-lookup"><span data-stu-id="15d85-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="15d85-107">При создании объекта <xref:System.Data.EntityClient.EntityCommand> можно указать имя хранимой процедуры или текст запроса, присвоив строку запроса на языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] его свойству <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="15d85-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="15d85-108"><xref:System.Data.EntityClient.EntityDataReader> предоставляет доступ к результатам выполнения <xref:System.Data.EntityClient.EntityCommand> к модели EDM.</span><span class="sxs-lookup"><span data-stu-id="15d85-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="15d85-109">Для выполнения команды, возвращающей значение <xref:System.Data.EntityClient.EntityDataReader>, нужно вызвать метод <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="15d85-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="15d85-110">Помимо поставщика EntityClient, платформа [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] обеспечивает выполнение запросов [!INCLUDE[esql](../../../../../../includes/esql-md.md)] к концептуальной модели и возврат данных в виде строго типизированных объектов среды CLR, которые являются экземплярами типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="15d85-110">In addition to the EntityClient provider, the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="15d85-111">Дополнительные сведения см. в разделе [работа с объектами](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="15d85-111">For more information, see [Working with Objects](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span></span>  
  
 <span data-ttu-id="15d85-112">В этом разделе приведены основные сведения о языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15d85-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15d85-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="15d85-113">In This Section</span></span>  
 [<span data-ttu-id="15d85-114">Отличия Entity SQL от Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15d85-114">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="15d85-115">Краткий справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="15d85-115">Entity SQL Quick Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="15d85-116">Система типов</span><span class="sxs-lookup"><span data-stu-id="15d85-116">Type System</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)  
  
 [<span data-ttu-id="15d85-117">Определения типов</span><span class="sxs-lookup"><span data-stu-id="15d85-117">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="15d85-118">Сборка типов</span><span class="sxs-lookup"><span data-stu-id="15d85-118">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="15d85-119">Кэширование планов запросов</span><span class="sxs-lookup"><span data-stu-id="15d85-119">Query Plan Caching</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="15d85-120">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="15d85-120">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
  
 [<span data-ttu-id="15d85-121">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="15d85-121">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 [<span data-ttu-id="15d85-122">Параметры</span><span class="sxs-lookup"><span data-stu-id="15d85-122">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
  
 [<span data-ttu-id="15d85-123">Переменные</span><span class="sxs-lookup"><span data-stu-id="15d85-123">Variables</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md)  
  
 [<span data-ttu-id="15d85-124">Неподдерживаемые выражения</span><span class="sxs-lookup"><span data-stu-id="15d85-124">Unsupported Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="15d85-125">Литералы</span><span class="sxs-lookup"><span data-stu-id="15d85-125">Literals</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md)  
  
 [<span data-ttu-id="15d85-126">Литералы NULL и определение типов</span><span class="sxs-lookup"><span data-stu-id="15d85-126">Null Literals and Type Inference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="15d85-127">Набор символов ввода</span><span class="sxs-lookup"><span data-stu-id="15d85-127">Input Character Set</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="15d85-128">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="15d85-128">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="15d85-129">Функции</span><span class="sxs-lookup"><span data-stu-id="15d85-129">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)  
  
 [<span data-ttu-id="15d85-130">Приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="15d85-130">Operator Precedence</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="15d85-131">Разбивка на страницы</span><span class="sxs-lookup"><span data-stu-id="15d85-131">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
  
 [<span data-ttu-id="15d85-132">Семантика сравнения</span><span class="sxs-lookup"><span data-stu-id="15d85-132">Comparison Semantics</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="15d85-133">Составление вложенных запросов Entity SQL</span><span class="sxs-lookup"><span data-stu-id="15d85-133">Composing Nested Entity SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="15d85-134">Структурированные типы, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="15d85-134">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="15d85-135">См. также</span><span class="sxs-lookup"><span data-stu-id="15d85-135">See Also</span></span>  
 [<span data-ttu-id="15d85-136">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="15d85-136">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="15d85-137">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="15d85-137">Entity SQL Language</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [<span data-ttu-id="15d85-138">Спецификации CSDL, SSDL и MSL</span><span class="sxs-lookup"><span data-stu-id="15d85-138">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
