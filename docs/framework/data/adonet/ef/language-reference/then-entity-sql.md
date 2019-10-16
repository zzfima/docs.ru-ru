---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: ba01a978c53b58f7e6c1ac9bc42a97277ac64bbc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319286"
---
# <a name="then-entity-sql"></a><span data-ttu-id="ac946-102">THEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ac946-102">THEN (Entity SQL)</span></span>
<span data-ttu-id="ac946-103">Результат предложения WHEN, если оно оценивается как значение `true`.</span><span class="sxs-lookup"><span data-stu-id="ac946-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac946-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac946-104">Syntax</span></span>  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac946-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ac946-105">Arguments</span></span>  
 `when_expression`  
 <span data-ttu-id="ac946-106">Любое допустимое выражение типа Boolean.</span><span class="sxs-lookup"><span data-stu-id="ac946-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="ac946-107">Любое допустимое выражение запроса, возвращающее коллекцию.</span><span class="sxs-lookup"><span data-stu-id="ac946-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac946-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="ac946-108">Remarks</span></span>  
 <span data-ttu-id="ac946-109">Если аргумент `when_expression` оценивается как значение `true`, результатом является соответствующее значение `then-expression`.</span><span class="sxs-lookup"><span data-stu-id="ac946-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="ac946-110">Если не выполнено ни одно из условий предложения WHEN, оценивается выражение `else-expression` .</span><span class="sxs-lookup"><span data-stu-id="ac946-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="ac946-111">Однако, если выражение `else-expression`отсутствует, результат равен NULL.</span><span class="sxs-lookup"><span data-stu-id="ac946-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="ac946-112">Пример см. в разделе [case](case-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ac946-112">For an example, see [CASE](case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac946-113">Пример</span><span class="sxs-lookup"><span data-stu-id="ac946-113">Example</span></span>  
 <span data-ttu-id="ac946-114">В следующем запросе Entity SQL с помощью выражения CASE оценивается набор выражений типа `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="ac946-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="ac946-115">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="ac946-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ac946-116">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="ac946-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ac946-117">Выполните процедуру, описанную в разделе [инструкции. выполнение запроса, возвращающего тип PrimitiveType результаты](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ac946-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="ac946-118">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ac946-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="ac946-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ac946-119">See also</span></span>

- [<span data-ttu-id="ac946-120">CASE</span><span class="sxs-lookup"><span data-stu-id="ac946-120">CASE</span></span>](case-entity-sql.md)
- [<span data-ttu-id="ac946-121">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ac946-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
