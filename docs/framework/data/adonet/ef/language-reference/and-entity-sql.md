---
title: '&amp;&amp; (И) (Язык entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 6ee7987f2801a35fb9669472ce7b237e684f64e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579671"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="c633c-102">&amp;&amp; (И) (Язык entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c633c-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="c633c-103">Возвращает значение `true` если оба выражения `true`; в противном случае возвращает значение `false` или `NULL`.</span><span class="sxs-lookup"><span data-stu-id="c633c-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c633c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c633c-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="c633c-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c633c-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="c633c-106">Любое допустимое выражение, возвращающее значение типа Boolean.</span><span class="sxs-lookup"><span data-stu-id="c633c-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c633c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c633c-107">Remarks</span></span>  
 <span data-ttu-id="c633c-108">Два амперсанда (&&) действуют так же, как оператор AND.</span><span class="sxs-lookup"><span data-stu-id="c633c-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="c633c-109">В следующей таблице указаны возможные входные значения и возвращаемые типы.</span><span class="sxs-lookup"><span data-stu-id="c633c-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="c633c-110">TRUE</span><span class="sxs-lookup"><span data-stu-id="c633c-110">TRUE</span></span>|<span data-ttu-id="c633c-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="c633c-111">FALSE</span></span>|<span data-ttu-id="c633c-112">NULL</span><span class="sxs-lookup"><span data-stu-id="c633c-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="c633c-113">FALSE</span><span class="sxs-lookup"><span data-stu-id="c633c-113">FALSE</span></span>|<span data-ttu-id="c633c-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="c633c-114">FALSE</span></span>|<span data-ttu-id="c633c-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="c633c-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="c633c-116">NULL</span><span class="sxs-lookup"><span data-stu-id="c633c-116">NULL</span></span>|<span data-ttu-id="c633c-117">false</span><span class="sxs-lookup"><span data-stu-id="c633c-117">FALSE</span></span>|<span data-ttu-id="c633c-118">NULL</span><span class="sxs-lookup"><span data-stu-id="c633c-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c633c-119">Пример</span><span class="sxs-lookup"><span data-stu-id="c633c-119">Example</span></span>  
 <span data-ttu-id="c633c-120">Следующий запрос Entity SQL демонстрирует, как использовать оператор AND.</span><span class="sxs-lookup"><span data-stu-id="c633c-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="c633c-121">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="c633c-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c633c-122">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="c633c-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c633c-123">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c633c-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="c633c-124">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c633c-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="c633c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c633c-125">See also</span></span>
- [<span data-ttu-id="c633c-126">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c633c-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
