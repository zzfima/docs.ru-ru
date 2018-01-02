---
title: ORDER BY (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e4ef6edfc56fe73cd509d466fcc26cdb24069c9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="order-by-entity-sql"></a><span data-ttu-id="90add-102">ORDER BY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="90add-102">ORDER BY (Entity SQL)</span></span>
<span data-ttu-id="90add-103">Указывает порядок сортировки для объектов, возвращаемых инструкцией SELECT.</span><span class="sxs-lookup"><span data-stu-id="90add-103">Specifies the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90add-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90add-104">Syntax</span></span>  
  
```  
[ ORDER BY   
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]   
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="90add-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="90add-105">Arguments</span></span>  
 `order_by_expression`  
 <span data-ttu-id="90add-106">Любое допустимое выражение запроса, задающее свойство, по которому выполняется сортировка.</span><span class="sxs-lookup"><span data-stu-id="90add-106">Any valid query expression specifying a property on which to sort.</span></span> <span data-ttu-id="90add-107">Может быть указано несколько выражений сортировки.</span><span class="sxs-lookup"><span data-stu-id="90add-107">Multiple sort expressions can be specified.</span></span> <span data-ttu-id="90add-108">Последовательность выражений сортировки в предложении ORDER BY определяет порядок сортировки результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="90add-108">The sequence of the sort expressions in the ORDER BY clause defines the organization of the sorted result set.</span></span>  
  
 <span data-ttu-id="90add-109">COLLATE {collation_name}</span><span class="sxs-lookup"><span data-stu-id="90add-109">COLLATE {collation_name}</span></span>  
 <span data-ttu-id="90add-110">Указывает, что операция ORDER BY должна выполняться в соответствии с параметрами сортировки, заданными в аргументе `collation_name`.</span><span class="sxs-lookup"><span data-stu-id="90add-110">Specifies that the ORDER BY operation should be performed according to the collation specified in `collation_name`.</span></span> <span data-ttu-id="90add-111">COLLATE применяется только для строковых выражений.</span><span class="sxs-lookup"><span data-stu-id="90add-111">COLLATE is applicable only for string expressions.</span></span>  
  
 <span data-ttu-id="90add-112">ASC</span><span class="sxs-lookup"><span data-stu-id="90add-112">ASC</span></span>  
 <span data-ttu-id="90add-113">Указывает, что значения в указанном свойстве должны быть отсортированы в порядке возрастания, от меньшего к большему.</span><span class="sxs-lookup"><span data-stu-id="90add-113">Specifies that the values in the specified property should be sorted in ascending order, from lowest value to highest value.</span></span> <span data-ttu-id="90add-114">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90add-114">This is the default.</span></span>  
  
 <span data-ttu-id="90add-115">DESC</span><span class="sxs-lookup"><span data-stu-id="90add-115">DESC</span></span>  
 <span data-ttu-id="90add-116">Указывает, что значения в указанном свойстве должны быть отсортированы в порядке убывания, от большего к меньшему.</span><span class="sxs-lookup"><span data-stu-id="90add-116">Specifies that the values in the specified property should be sorted in descending order, from highest value to lowest value.</span></span>  
  
 <span data-ttu-id="90add-117">LIMIT `n`</span><span class="sxs-lookup"><span data-stu-id="90add-117">LIMIT `n`</span></span>  
 <span data-ttu-id="90add-118">Будут выбраны только первые `n` элементов.</span><span class="sxs-lookup"><span data-stu-id="90add-118">Only the first `n` items will be selected.</span></span>  
  
 <span data-ttu-id="90add-119">SKIP `n`</span><span class="sxs-lookup"><span data-stu-id="90add-119">SKIP `n`</span></span>  
 <span data-ttu-id="90add-120">Пропускает первые `n` элементов.</span><span class="sxs-lookup"><span data-stu-id="90add-120">Skips the first `n` items.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90add-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="90add-121">Remarks</span></span>  
 <span data-ttu-id="90add-122">Предложение ORDER BY логически применяется к результату предложения SELECT.</span><span class="sxs-lookup"><span data-stu-id="90add-122">The ORDER BY clause is logically applied to the result of the SELECT clause.</span></span> <span data-ttu-id="90add-123">Предложение ORDER BY может ссылаться на элементы списка выбора по их псевдонимам.</span><span class="sxs-lookup"><span data-stu-id="90add-123">The ORDER BY clause can reference items in the select list by using their aliases.</span></span> <span data-ttu-id="90add-124">Предложение ORDER BY может также ссылаться на другие переменные, находящиеся в области видимости.</span><span class="sxs-lookup"><span data-stu-id="90add-124">The ORDER BY clause can also reference other variables that are currently in-scope.</span></span> <span data-ttu-id="90add-125">Однако если предложение SELECT указано с модификатором DISTINCT, то предложение ORDER BY может ссылаться только на псевдонимы из предложения SELECT.</span><span class="sxs-lookup"><span data-stu-id="90add-125">However, if the SELECT clause has been specified with a DISTINCT modifier, the ORDER BY clause can only reference aliases from the SELECT clause.</span></span>  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 <span data-ttu-id="90add-126">Выражения в предложении ORDER BY должны иметь сравнимый тип, поскольку для упорядочивания производится сравнение элементов (меньше, больше и т. д.).</span><span class="sxs-lookup"><span data-stu-id="90add-126">Each expression in the ORDER BY clause must evaluate to some type that can be compared for ordered inequality (less than or greater than, and so on).</span></span> <span data-ttu-id="90add-127">Такими типами обычно являются скалярные примитивы - числа, строки и даты.</span><span class="sxs-lookup"><span data-stu-id="90add-127">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="90add-128">Типы RowType для сравнимых типов также являются сравнимыми для упорядочивания.</span><span class="sxs-lookup"><span data-stu-id="90add-128">RowTypes of comparable types are also order comparable.</span></span>  
  
 <span data-ttu-id="90add-129">Если код проходит по упорядоченному набору, отличному от проекции верхнего уровня, то сохранение порядка в выходных данных не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="90add-129">If your code iterates over an ordered set, other than for a top-level projection, the output is not guaranteed to have its order preserved.</span></span>  
  
```  
-- In the following sample, order is guaranteed to be preserved:  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 <span data-ttu-id="90add-130">Получить упорядоченный результат выполнения операции UNION, UNION ALL, EXCEPT или INTERSECT можно следующим образом.</span><span class="sxs-lookup"><span data-stu-id="90add-130">To have an ordered UNION, UNION ALL, EXCEPT, or INTERSECT operation, use the following pattern:</span></span>  
  
```  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a><span data-ttu-id="90add-131">Служебные ключевые слова</span><span class="sxs-lookup"><span data-stu-id="90add-131">Restricted keywords</span></span>  
 <span data-ttu-id="90add-132">Следующие ключевые слова при использовании в предложении `ORDER BY` необходимо заключать в кавычки.</span><span class="sxs-lookup"><span data-stu-id="90add-132">The following keywords must be enclosed in quotation marks when used in an `ORDER BY` clause:</span></span>  
  
-   <span data-ttu-id="90add-133">CROSS</span><span class="sxs-lookup"><span data-stu-id="90add-133">CROSS</span></span>  
  
-   <span data-ttu-id="90add-134">FULL</span><span class="sxs-lookup"><span data-stu-id="90add-134">FULL</span></span>  
  
-   <span data-ttu-id="90add-135">KEY</span><span class="sxs-lookup"><span data-stu-id="90add-135">KEY</span></span>  
  
-   <span data-ttu-id="90add-136">LEFT</span><span class="sxs-lookup"><span data-stu-id="90add-136">LEFT</span></span>  
  
-   <span data-ttu-id="90add-137">ORDER</span><span class="sxs-lookup"><span data-stu-id="90add-137">ORDER</span></span>  
  
-   <span data-ttu-id="90add-138">OUTER</span><span class="sxs-lookup"><span data-stu-id="90add-138">OUTER</span></span>  
  
-   <span data-ttu-id="90add-139">RIGHT</span><span class="sxs-lookup"><span data-stu-id="90add-139">RIGHT</span></span>  
  
-   <span data-ttu-id="90add-140">ROW</span><span class="sxs-lookup"><span data-stu-id="90add-140">ROW</span></span>  
  
-   <span data-ttu-id="90add-141">VALUE</span><span class="sxs-lookup"><span data-stu-id="90add-141">VALUE</span></span>  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="90add-142">Упорядочение вложенных запросов</span><span class="sxs-lookup"><span data-stu-id="90add-142">Ordering Nested Queries</span></span>  
 <span data-ttu-id="90add-143">Платформа Entity Framework позволяет разместить вложенное выражение в любом месте запроса. Порядок вложенного запроса не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="90add-143">In the Entity Framework, a nested expression can be placed anywhere in the query; the order of a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by the last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a><span data-ttu-id="90add-144">Пример</span><span class="sxs-lookup"><span data-stu-id="90add-144">Example</span></span>  
 <span data-ttu-id="90add-145">В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор ORDER BY задает порядок сортировки для объектов, возвращаемых инструкцией SELECT.</span><span class="sxs-lookup"><span data-stu-id="90add-145">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ORDER BY operator to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="90add-146">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="90add-146">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="90add-147">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="90add-147">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="90add-148">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="90add-148">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="90add-149">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="90add-149">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ORDERBY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#orderby)]  
  
## <a name="see-also"></a><span data-ttu-id="90add-150">См. также</span><span class="sxs-lookup"><span data-stu-id="90add-150">See Also</span></span>  
 [<span data-ttu-id="90add-151">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="90add-151">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [<span data-ttu-id="90add-152">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="90add-152">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="90add-153">SKIP</span><span class="sxs-lookup"><span data-stu-id="90add-153">SKIP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
 [<span data-ttu-id="90add-154">LIMIT</span><span class="sxs-lookup"><span data-stu-id="90add-154">LIMIT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
 [<span data-ttu-id="90add-155">TOP</span><span class="sxs-lookup"><span data-stu-id="90add-155">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
