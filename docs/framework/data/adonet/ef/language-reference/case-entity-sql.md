---
title: CASE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: df86e69684a111effc29a2663d18310b276f4b83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="case-entity-sql"></a><span data-ttu-id="0ab74-102">CASE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0ab74-102">CASE (Entity SQL)</span></span>
<span data-ttu-id="0ab74-103">Вычисляет набор выражений типа `Boolean` для определения результата.</span><span class="sxs-lookup"><span data-stu-id="0ab74-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ab74-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ab74-104">Syntax</span></span>  
  
```  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="0ab74-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0ab74-105">Arguments</span></span>  
 `n`  
 <span data-ttu-id="0ab74-106">Заполнитель, который показывает, что можно использовать несколько предложений WHEN `Boolean_expression` THEN `result_expression` .</span><span class="sxs-lookup"><span data-stu-id="0ab74-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="0ab74-107">THEN `result_expression`</span><span class="sxs-lookup"><span data-stu-id="0ab74-107">THEN `result_expression`</span></span>  
 <span data-ttu-id="0ab74-108">Выражение, возвращаемое, если результатом выражения `Boolean_expression` является значение `true`.</span><span class="sxs-lookup"><span data-stu-id="0ab74-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> <span data-ttu-id="0ab74-109">`result expression` - любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="0ab74-109">`result expression` is any valid expression.</span></span>  
  
 <span data-ttu-id="0ab74-110">ELSE `else_result_expression`</span><span class="sxs-lookup"><span data-stu-id="0ab74-110">ELSE `else_result_expression`</span></span>  
 <span data-ttu-id="0ab74-111">Это выражение, возвращаемое, если ни одна из операций сравнения не дает в результате `true`.</span><span class="sxs-lookup"><span data-stu-id="0ab74-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="0ab74-112">Если этот аргумент опущен и ни одна из операций сравнения не дает в результате `true`, функция CASE возвращает NULL.</span><span class="sxs-lookup"><span data-stu-id="0ab74-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> <span data-ttu-id="0ab74-113">`else_result_expression` - любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="0ab74-113">`else_result_expression` is any valid expression.</span></span> <span data-ttu-id="0ab74-114">Типы данных аргумента `else_result_expression` и любого из аргументов `result_expression` должны быть одинаковыми или неявно приводимыми друг к другу.</span><span class="sxs-lookup"><span data-stu-id="0ab74-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="0ab74-115">WHEN `Boolean_expression`</span><span class="sxs-lookup"><span data-stu-id="0ab74-115">WHEN `Boolean_expression`</span></span>  
 <span data-ttu-id="0ab74-116">Выражение типа `Boolean` , вычисляемое при использовании поискового формата оператора CASE.</span><span class="sxs-lookup"><span data-stu-id="0ab74-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> <span data-ttu-id="0ab74-117">`Boolean_expression` - любое допустимое выражение типа `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="0ab74-117">`Boolean_expression` is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ab74-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0ab74-118">Return Value</span></span>  
 <span data-ttu-id="0ab74-119">Возвращает тип с наивысшим приоритетом из набора типов в выражении `result_expression` и необязательном выражении `else_result_expression`.</span><span class="sxs-lookup"><span data-stu-id="0ab74-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ab74-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ab74-120">Remarks</span></span>  
 <span data-ttu-id="0ab74-121">Выражение CASE языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] во многом подобно выражению CASE языка [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ab74-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] case expression.</span></span> <span data-ttu-id="0ab74-122">Выражение CASE применяется для выполнения ряда проверок условий в целях определения того, вычисление какого выражения приведет к получению приемлемого результата.</span><span class="sxs-lookup"><span data-stu-id="0ab74-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="0ab74-123">В этой форме выражение CASE применяется к ряду, состоящему из одного или нескольких выражений типа `Boolean` , для определения правильного результирующего выражения.</span><span class="sxs-lookup"><span data-stu-id="0ab74-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="0ab74-124">Функция CASE находит значение `Boolean_expression` для каждого предложения WHEN в указанном порядке и возвращает значение `result_expression` первого выражения `Boolean_expression` , которое определяется как `true`.</span><span class="sxs-lookup"><span data-stu-id="0ab74-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="0ab74-125">Остальные выражения оцениваться не будут.</span><span class="sxs-lookup"><span data-stu-id="0ab74-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="0ab74-126">Если ни одно выражение `Boolean_expression` не вычисляется в `true`, компонент Database Engine возвращает выражение `else_result_expression` , если указано предложение ELSE, или значение NULL, если предложение ELSE не указано.</span><span class="sxs-lookup"><span data-stu-id="0ab74-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="0ab74-127">Инструкция CASE не может возвращать мультинабор.</span><span class="sxs-lookup"><span data-stu-id="0ab74-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ab74-128">Пример</span><span class="sxs-lookup"><span data-stu-id="0ab74-128">Example</span></span>  
 <span data-ttu-id="0ab74-129">Следующий запрос Entity SQL с помощью выражения CASE оценивает набор выражений типа `Boolean` , чтобы определить результат.</span><span class="sxs-lookup"><span data-stu-id="0ab74-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="0ab74-130">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="0ab74-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0ab74-131">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="0ab74-131">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0ab74-132">Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="0ab74-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="0ab74-133">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="0ab74-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="0ab74-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0ab74-134">See Also</span></span>  
 [<span data-ttu-id="0ab74-135">THEN</span><span class="sxs-lookup"><span data-stu-id="0ab74-135">THEN</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)  
 [<span data-ttu-id="0ab74-136">SELECT</span><span class="sxs-lookup"><span data-stu-id="0ab74-136">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [<span data-ttu-id="0ab74-137">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0ab74-137">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
