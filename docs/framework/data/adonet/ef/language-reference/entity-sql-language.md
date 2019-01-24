---
title: Язык Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 0c698f04c3b95ffb204a20d41e91ef3f6210c5d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494104"
---
# <a name="entity-sql-language"></a><span data-ttu-id="bd5e1-102">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bd5e1-102">Entity SQL Language</span></span>
<span data-ttu-id="bd5e1-103">Entity SQL представляет собой независимый от хранилища язык запросов, аналогичный языку SQL.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="bd5e1-104">Entity SQL позволяет выполнять запросы к данным сущности, представленным либо в виде объектов, либо в табличной форме.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="bd5e1-105">Возможность использования Entity SQL необходимо рассматривать в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="bd5e1-105">You should consider using Entity SQL in the following cases:</span></span>  
  
-   <span data-ttu-id="bd5e1-106">Если запрос должен создаваться динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="bd5e1-107">В этом случае следует также рассмотреть возможность использования методов построителя запросов <xref:System.Data.Objects.ObjectQuery%601> вместо создания строки запроса Entity SQL во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
-   <span data-ttu-id="bd5e1-108">Если требуется определить запрос как часть определения модели.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="bd5e1-109">В модели данных поддерживается только Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="bd5e1-110">Дополнительные сведения см. в разделе [элемент QueryView (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span><span class="sxs-lookup"><span data-stu-id="bd5e1-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
-   <span data-ttu-id="bd5e1-111">Если EntityClient применяется для возврата допускающих только для чтения данных сущности в виде наборов строк с использованием <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="bd5e1-112">Дополнительные сведения см. в разделе [поставщик EntityClient для Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="bd5e1-112">For more information, see [EntityClient Provider for the Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>  
  
-   <span data-ttu-id="bd5e1-113">Для специалиста по языкам запросов на основе SQL язык Entity SQL может оказаться самым естественным выбором.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="bd5e1-114">Использование Entity SQL с поставщиком EntityClient</span><span class="sxs-lookup"><span data-stu-id="bd5e1-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="bd5e1-115">Если требуется использовать Entity SQL с поставщиком EntityClient, см. дополнительные сведения в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="bd5e1-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="bd5e1-116">Поставщик EntityClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="bd5e1-116">EntityClient Provider for the Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="bd5e1-117">Практическое руководство. Построить строку соединения EntityConnection</span><span class="sxs-lookup"><span data-stu-id="bd5e1-117">How to: Build an EntityConnection Connection String</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="bd5e1-118">Практическое руководство. Выполнение запроса, возвращающего результаты PrimitiveType</span><span class="sxs-lookup"><span data-stu-id="bd5e1-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="bd5e1-119">Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType</span><span class="sxs-lookup"><span data-stu-id="bd5e1-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="bd5e1-120">Практическое руководство. Выполнение запроса, возвращающего результаты RefType</span><span class="sxs-lookup"><span data-stu-id="bd5e1-120">How to: Execute a Query that Returns RefType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="bd5e1-121">Практическое руководство. Выполнение запроса, возвращающего сложные типы</span><span class="sxs-lookup"><span data-stu-id="bd5e1-121">How to: Execute a Query that Returns Complex Types</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="bd5e1-122">Практическое руководство. Выполнение запроса, возвращающего вложенные коллекции</span><span class="sxs-lookup"><span data-stu-id="bd5e1-122">How to: Execute a Query that Returns Nested Collections</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="bd5e1-123">Практическое руководство. Выполнение параметризованного запроса Entity SQL с использованием EntityCommand</span><span class="sxs-lookup"><span data-stu-id="bd5e1-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="bd5e1-124">Практическое руководство. Выполнить параметризированную хранимую процедуру с использованием EntityCommand</span><span class="sxs-lookup"><span data-stu-id="bd5e1-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="bd5e1-125">Практическое руководство. Выполнить полиморфный запрос</span><span class="sxs-lookup"><span data-stu-id="bd5e1-125">How to: Execute a Polymorphic Query</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="bd5e1-126">Практическое руководство. Переход по отношениям с помощью оператора Navigate</span><span class="sxs-lookup"><span data-stu-id="bd5e1-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="bd5e1-127">Использование Entity SQL с запросами объектов</span><span class="sxs-lookup"><span data-stu-id="bd5e1-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="bd5e1-128">Если требуется использовать Entity SQL с запросами объектов, см. дополнительные сведения в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="bd5e1-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="bd5e1-129">Практическое руководство. Выполнение запроса, возвращающего объекты типа сущностей</span><span class="sxs-lookup"><span data-stu-id="bd5e1-129">How to: Execute a Query that Returns Entity Type Objects</span></span>](https://msdn.microsoft.com/library/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [<span data-ttu-id="bd5e1-130">Практическое руководство. Выполнение параметризованного запроса</span><span class="sxs-lookup"><span data-stu-id="bd5e1-130">How to: Execute a Parameterized Query</span></span>](https://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [<span data-ttu-id="bd5e1-131">Практическое руководство. Переход по отношениям с помощью свойств навигации</span><span class="sxs-lookup"><span data-stu-id="bd5e1-131">How to: Navigate Relationships Using Navigation Properties</span></span>](https://msdn.microsoft.com/library/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [<span data-ttu-id="bd5e1-132">Практическое руководство. Вызов определяемой пользователем функции</span><span class="sxs-lookup"><span data-stu-id="bd5e1-132">How to: Call a User-Defined Function</span></span>](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [<span data-ttu-id="bd5e1-133">Практическое руководство. Фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="bd5e1-133">How to: Filter Data</span></span>](https://msdn.microsoft.com/library/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [<span data-ttu-id="bd5e1-134">Практическое руководство. Сортировка данных</span><span class="sxs-lookup"><span data-stu-id="bd5e1-134">How to: Sort Data</span></span>](https://msdn.microsoft.com/library/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [<span data-ttu-id="bd5e1-135">Практическое руководство. Группы данных</span><span class="sxs-lookup"><span data-stu-id="bd5e1-135">How to: Group Data</span></span>](https://msdn.microsoft.com/library/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [<span data-ttu-id="bd5e1-136">Практическое руководство. Сводные данные</span><span class="sxs-lookup"><span data-stu-id="bd5e1-136">How to: Aggregate Data</span></span>](https://msdn.microsoft.com/library/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [<span data-ttu-id="bd5e1-137">Практическое руководство. Выполнение запроса, возвращающего объекты анонимного типа</span><span class="sxs-lookup"><span data-stu-id="bd5e1-137">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](https://msdn.microsoft.com/library/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [<span data-ttu-id="bd5e1-138">Практическое руководство. Выполнение запроса, возвращающего коллекцию примитивных типов</span><span class="sxs-lookup"><span data-stu-id="bd5e1-138">How to: Execute a Query that Returns a Collection of Primitive Types</span></span>](https://msdn.microsoft.com/library/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [<span data-ttu-id="bd5e1-139">Практическое руководство. Запрос связанных объектов в EntityCollection</span><span class="sxs-lookup"><span data-stu-id="bd5e1-139">How to: Query Related Objects in an EntityCollection</span></span>](https://msdn.microsoft.com/library/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [<span data-ttu-id="bd5e1-140">Практическое руководство. Порядок объединения двух запросов</span><span class="sxs-lookup"><span data-stu-id="bd5e1-140">How to: Order the Union of Two Queries</span></span>](https://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313)  
  
 [<span data-ttu-id="bd5e1-141">Практическое руководство. Постранично просмотреть результаты запроса</span><span class="sxs-lookup"><span data-stu-id="bd5e1-141">How to: Page Through Query Results</span></span>](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a><span data-ttu-id="bd5e1-142">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="bd5e1-142">In This Section</span></span>  
 [<span data-ttu-id="bd5e1-143">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bd5e1-143">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [<span data-ttu-id="bd5e1-144">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bd5e1-144">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="bd5e1-145">См. также</span><span class="sxs-lookup"><span data-stu-id="bd5e1-145">See also</span></span>
- [<span data-ttu-id="bd5e1-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="bd5e1-146">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
- [<span data-ttu-id="bd5e1-147">Справочник по языку</span><span class="sxs-lookup"><span data-stu-id="bd5e1-147">Language Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
