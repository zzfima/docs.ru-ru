---
title: CASE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: 58b21d3be8e13a0a2204a4fd6d355f734207c509
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150471"
---
# <a name="case-entity-sql"></a><span data-ttu-id="4fc99-102">CASE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc99-102">CASE (Entity SQL)</span></span>
<span data-ttu-id="4fc99-103">Вычисляет набор выражений типа `Boolean` для определения результата.</span><span class="sxs-lookup"><span data-stu-id="4fc99-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc99-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fc99-104">Syntax</span></span>  
  
```csharp  
CASE  
     WHEN Boolean_expression THEN result_expression
    [ ...n ]
     [
    ELSE else_result_expression
     ]
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="4fc99-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4fc99-105">Arguments</span></span>  
 `n`  
 <span data-ttu-id="4fc99-106">Заполнитель, который показывает, что можно использовать несколько предложений WHEN `Boolean_expression` THEN `result_expression` .</span><span class="sxs-lookup"><span data-stu-id="4fc99-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="4fc99-107">THEN `result_expression`</span><span class="sxs-lookup"><span data-stu-id="4fc99-107">THEN `result_expression`</span></span>  
 <span data-ttu-id="4fc99-108">Выражение, возвращаемое, если результатом выражения `Boolean_expression` является значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4fc99-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> <span data-ttu-id="4fc99-109">`result expression` - любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="4fc99-109">`result expression` is any valid expression.</span></span>  
  
 <span data-ttu-id="4fc99-110">ELSE `else_result_expression`</span><span class="sxs-lookup"><span data-stu-id="4fc99-110">ELSE `else_result_expression`</span></span>  
 <span data-ttu-id="4fc99-111">Это выражение, возвращаемое, если ни одна из операций сравнения не дает в результате `true`.</span><span class="sxs-lookup"><span data-stu-id="4fc99-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="4fc99-112">Если этот аргумент опущен и ни одна из операций сравнения не дает в результате `true`, функция CASE возвращает NULL.</span><span class="sxs-lookup"><span data-stu-id="4fc99-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> <span data-ttu-id="4fc99-113">`else_result_expression` - любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="4fc99-113">`else_result_expression` is any valid expression.</span></span> <span data-ttu-id="4fc99-114">Типы данных аргумента `else_result_expression` и любого из аргументов `result_expression` должны быть одинаковыми или неявно приводимыми друг к другу.</span><span class="sxs-lookup"><span data-stu-id="4fc99-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="4fc99-115">WHEN `Boolean_expression`</span><span class="sxs-lookup"><span data-stu-id="4fc99-115">WHEN `Boolean_expression`</span></span>  
 <span data-ttu-id="4fc99-116">Выражение типа `Boolean` , вычисляемое при использовании поискового формата оператора CASE.</span><span class="sxs-lookup"><span data-stu-id="4fc99-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> <span data-ttu-id="4fc99-117">`Boolean_expression` - любое допустимое выражение типа `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="4fc99-117">`Boolean_expression` is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fc99-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4fc99-118">Return Value</span></span>  
 <span data-ttu-id="4fc99-119">Возвращает тип с наивысшим приоритетом из набора типов в выражении `result_expression` и необязательном выражении `else_result_expression`.</span><span class="sxs-lookup"><span data-stu-id="4fc99-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fc99-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="4fc99-120">Remarks</span></span>  
 <span data-ttu-id="4fc99-121">Выражение [!INCLUDE[esql](../../../../../../includes/esql-md.md)] случая напоминает выражение корпуса «Трансакт-СЗЛ».</span><span class="sxs-lookup"><span data-stu-id="4fc99-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the Transact-SQL case expression.</span></span> <span data-ttu-id="4fc99-122">Выражение CASE применяется для выполнения ряда проверок условий в целях определения того, вычисление какого выражения приведет к получению приемлемого результата.</span><span class="sxs-lookup"><span data-stu-id="4fc99-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="4fc99-123">В этой форме выражение CASE применяется к ряду, состоящему из одного или нескольких выражений типа `Boolean` , для определения правильного результирующего выражения.</span><span class="sxs-lookup"><span data-stu-id="4fc99-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="4fc99-124">Функция CASE находит значение `Boolean_expression` для каждого предложения WHEN в указанном порядке и возвращает значение `result_expression` первого выражения `Boolean_expression` , которое определяется как `true`.</span><span class="sxs-lookup"><span data-stu-id="4fc99-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="4fc99-125">Остальные выражения оцениваться не будут.</span><span class="sxs-lookup"><span data-stu-id="4fc99-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="4fc99-126">Если ни одно выражение `Boolean_expression` не вычисляется в `true`, компонент Database Engine возвращает выражение `else_result_expression` , если указано предложение ELSE, или значение NULL, если предложение ELSE не указано.</span><span class="sxs-lookup"><span data-stu-id="4fc99-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="4fc99-127">Инструкция CASE не может возвращать мультинабор.</span><span class="sxs-lookup"><span data-stu-id="4fc99-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fc99-128">Пример</span><span class="sxs-lookup"><span data-stu-id="4fc99-128">Example</span></span>  
 <span data-ttu-id="4fc99-129">Следующий запрос Entity SQL с помощью выражения CASE оценивает набор выражений типа `Boolean` , чтобы определить результат.</span><span class="sxs-lookup"><span data-stu-id="4fc99-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="4fc99-130">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="4fc99-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4fc99-131">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="4fc99-131">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="4fc99-132">Следуйте процедуре в [Как: Выполнить запрос, который возвращает результаты PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="4fc99-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="4fc99-133">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="4fc99-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="4fc99-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4fc99-134">See also</span></span>

- [<span data-ttu-id="4fc99-135">Затем</span><span class="sxs-lookup"><span data-stu-id="4fc99-135">THEN</span></span>](then-entity-sql.md)
- [<span data-ttu-id="4fc99-136">Выберите</span><span class="sxs-lookup"><span data-stu-id="4fc99-136">SELECT</span></span>](select-entity-sql.md)
- [<span data-ttu-id="4fc99-137">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="4fc99-137">Entity SQL Reference</span></span>](entity-sql-reference.md)
