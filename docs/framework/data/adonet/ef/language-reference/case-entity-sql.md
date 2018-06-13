---
title: CASE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: ee878409e7698300b7bebbdac760422013f3b7de
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761468"
---
# <a name="case-entity-sql"></a><span data-ttu-id="584b1-102">CASE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="584b1-102">CASE (Entity SQL)</span></span>
<span data-ttu-id="584b1-103">Вычисляет набор выражений типа `Boolean` для определения результата.</span><span class="sxs-lookup"><span data-stu-id="584b1-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="584b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="584b1-104">Syntax</span></span>  
  
```  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="584b1-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="584b1-105">Arguments</span></span>  
 `n`  
 <span data-ttu-id="584b1-106">Заполнитель, который показывает, что можно использовать несколько предложений WHEN `Boolean_expression` THEN `result_expression` .</span><span class="sxs-lookup"><span data-stu-id="584b1-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="584b1-107">THEN `result_expression`</span><span class="sxs-lookup"><span data-stu-id="584b1-107">THEN `result_expression`</span></span>  
 <span data-ttu-id="584b1-108">Выражение, возвращаемое, если результатом выражения `Boolean_expression` является значение `true`.</span><span class="sxs-lookup"><span data-stu-id="584b1-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> <span data-ttu-id="584b1-109">`result expression` - любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="584b1-109">`result expression` is any valid expression.</span></span>  
  
 <span data-ttu-id="584b1-110">ELSE `else_result_expression`</span><span class="sxs-lookup"><span data-stu-id="584b1-110">ELSE `else_result_expression`</span></span>  
 <span data-ttu-id="584b1-111">Это выражение, возвращаемое, если ни одна из операций сравнения не дает в результате `true`.</span><span class="sxs-lookup"><span data-stu-id="584b1-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="584b1-112">Если этот аргумент опущен и ни одна из операций сравнения не дает в результате `true`, функция CASE возвращает NULL.</span><span class="sxs-lookup"><span data-stu-id="584b1-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> <span data-ttu-id="584b1-113">`else_result_expression` - любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="584b1-113">`else_result_expression` is any valid expression.</span></span> <span data-ttu-id="584b1-114">Типы данных аргумента `else_result_expression` и любого из аргументов `result_expression` должны быть одинаковыми или неявно приводимыми друг к другу.</span><span class="sxs-lookup"><span data-stu-id="584b1-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="584b1-115">WHEN `Boolean_expression`</span><span class="sxs-lookup"><span data-stu-id="584b1-115">WHEN `Boolean_expression`</span></span>  
 <span data-ttu-id="584b1-116">Выражение типа `Boolean` , вычисляемое при использовании поискового формата оператора CASE.</span><span class="sxs-lookup"><span data-stu-id="584b1-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> <span data-ttu-id="584b1-117">`Boolean_expression` - любое допустимое выражение типа `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="584b1-117">`Boolean_expression` is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="584b1-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="584b1-118">Return Value</span></span>  
 <span data-ttu-id="584b1-119">Возвращает тип с наивысшим приоритетом из набора типов в выражении `result_expression` и необязательном выражении `else_result_expression`.</span><span class="sxs-lookup"><span data-stu-id="584b1-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="584b1-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="584b1-120">Remarks</span></span>  
 <span data-ttu-id="584b1-121">Выражение CASE языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] во многом подобно выражению CASE языка [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="584b1-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] case expression.</span></span> <span data-ttu-id="584b1-122">Выражение CASE применяется для выполнения ряда проверок условий в целях определения того, вычисление какого выражения приведет к получению приемлемого результата.</span><span class="sxs-lookup"><span data-stu-id="584b1-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="584b1-123">В этой форме выражение CASE применяется к ряду, состоящему из одного или нескольких выражений типа `Boolean` , для определения правильного результирующего выражения.</span><span class="sxs-lookup"><span data-stu-id="584b1-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="584b1-124">Функция CASE находит значение `Boolean_expression` для каждого предложения WHEN в указанном порядке и возвращает значение `result_expression` первого выражения `Boolean_expression` , которое определяется как `true`.</span><span class="sxs-lookup"><span data-stu-id="584b1-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="584b1-125">Остальные выражения оцениваться не будут.</span><span class="sxs-lookup"><span data-stu-id="584b1-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="584b1-126">Если ни одно выражение `Boolean_expression` не вычисляется в `true`, компонент Database Engine возвращает выражение `else_result_expression` , если указано предложение ELSE, или значение NULL, если предложение ELSE не указано.</span><span class="sxs-lookup"><span data-stu-id="584b1-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="584b1-127">Инструкция CASE не может возвращать мультинабор.</span><span class="sxs-lookup"><span data-stu-id="584b1-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="584b1-128">Пример</span><span class="sxs-lookup"><span data-stu-id="584b1-128">Example</span></span>  
 <span data-ttu-id="584b1-129">Следующий запрос Entity SQL с помощью выражения CASE оценивает набор выражений типа `Boolean` , чтобы определить результат.</span><span class="sxs-lookup"><span data-stu-id="584b1-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="584b1-130">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="584b1-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="584b1-131">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="584b1-131">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="584b1-132">Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="584b1-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="584b1-133">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="584b1-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="584b1-134">См. также</span><span class="sxs-lookup"><span data-stu-id="584b1-134">See Also</span></span>  
 [<span data-ttu-id="584b1-135">THEN</span><span class="sxs-lookup"><span data-stu-id="584b1-135">THEN</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)  
 [<span data-ttu-id="584b1-136">SELECT</span><span class="sxs-lookup"><span data-stu-id="584b1-136">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [<span data-ttu-id="584b1-137">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="584b1-137">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
