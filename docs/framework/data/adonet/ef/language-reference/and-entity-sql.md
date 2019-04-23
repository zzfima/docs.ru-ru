---
title: '&amp;&amp; (И) (Язык entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: eab05f7454f8ebc88ed29030503bfa96d0c70756
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308436"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="f58e2-102">&amp;&amp; (И) (Язык entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f58e2-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="f58e2-103">Возвращает значение `true` если оба выражения `true`; в противном случае возвращает значение `false` или `NULL`.</span><span class="sxs-lookup"><span data-stu-id="f58e2-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f58e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f58e2-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="f58e2-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f58e2-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="f58e2-106">Любое допустимое выражение, возвращающее значение типа Boolean.</span><span class="sxs-lookup"><span data-stu-id="f58e2-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f58e2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f58e2-107">Remarks</span></span>  
 <span data-ttu-id="f58e2-108">Два амперсанда (&&) действуют так же, как оператор AND.</span><span class="sxs-lookup"><span data-stu-id="f58e2-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="f58e2-109">В следующей таблице указаны возможные входные значения и возвращаемые типы.</span><span class="sxs-lookup"><span data-stu-id="f58e2-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="f58e2-110">true</span><span class="sxs-lookup"><span data-stu-id="f58e2-110">TRUE</span></span>|<span data-ttu-id="f58e2-111">false</span><span class="sxs-lookup"><span data-stu-id="f58e2-111">FALSE</span></span>|<span data-ttu-id="f58e2-112">NULL</span><span class="sxs-lookup"><span data-stu-id="f58e2-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="f58e2-113">false</span><span class="sxs-lookup"><span data-stu-id="f58e2-113">FALSE</span></span>|<span data-ttu-id="f58e2-114">false</span><span class="sxs-lookup"><span data-stu-id="f58e2-114">FALSE</span></span>|<span data-ttu-id="f58e2-115">false</span><span class="sxs-lookup"><span data-stu-id="f58e2-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="f58e2-116">NULL</span><span class="sxs-lookup"><span data-stu-id="f58e2-116">NULL</span></span>|<span data-ttu-id="f58e2-117">false</span><span class="sxs-lookup"><span data-stu-id="f58e2-117">FALSE</span></span>|<span data-ttu-id="f58e2-118">NULL</span><span class="sxs-lookup"><span data-stu-id="f58e2-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f58e2-119">Пример</span><span class="sxs-lookup"><span data-stu-id="f58e2-119">Example</span></span>  
 <span data-ttu-id="f58e2-120">Следующий запрос Entity SQL демонстрирует, как использовать оператор AND.</span><span class="sxs-lookup"><span data-stu-id="f58e2-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="f58e2-121">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="f58e2-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f58e2-122">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="f58e2-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f58e2-123">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f58e2-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="f58e2-124">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f58e2-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="f58e2-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f58e2-125">See also</span></span>

- [<span data-ttu-id="f58e2-126">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f58e2-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
