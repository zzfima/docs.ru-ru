---
title: '&amp;&amp; (и) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: be6e7120e6c19714f151aa38a8b9a1355de29d1a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039952"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="5f977-102">&amp;&amp; (и) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5f977-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="5f977-103">Возвращает значение `true` если оба выражения `true`; в противном случае возвращает значение `false` или `NULL`.</span><span class="sxs-lookup"><span data-stu-id="5f977-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f977-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f977-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```
 
<span data-ttu-id="5f977-105">или</span><span class="sxs-lookup"><span data-stu-id="5f977-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="5f977-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5f977-106">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="5f977-107">Любое допустимое выражение, возвращающее значение типа Boolean.</span><span class="sxs-lookup"><span data-stu-id="5f977-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f977-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="5f977-108">Remarks</span></span>  
 <span data-ttu-id="5f977-109">Два амперсанда (&&) действуют так же, как оператор AND.</span><span class="sxs-lookup"><span data-stu-id="5f977-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="5f977-110">В следующей таблице указаны возможные входные значения и возвращаемые типы.</span><span class="sxs-lookup"><span data-stu-id="5f977-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="5f977-111">true</span><span class="sxs-lookup"><span data-stu-id="5f977-111">TRUE</span></span>|<span data-ttu-id="5f977-112">false</span><span class="sxs-lookup"><span data-stu-id="5f977-112">FALSE</span></span>|<span data-ttu-id="5f977-113">NULL</span><span class="sxs-lookup"><span data-stu-id="5f977-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="5f977-114">false</span><span class="sxs-lookup"><span data-stu-id="5f977-114">FALSE</span></span>|<span data-ttu-id="5f977-115">false</span><span class="sxs-lookup"><span data-stu-id="5f977-115">FALSE</span></span>|<span data-ttu-id="5f977-116">false</span><span class="sxs-lookup"><span data-stu-id="5f977-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="5f977-117">NULL</span><span class="sxs-lookup"><span data-stu-id="5f977-117">NULL</span></span>|<span data-ttu-id="5f977-118">false</span><span class="sxs-lookup"><span data-stu-id="5f977-118">FALSE</span></span>|<span data-ttu-id="5f977-119">NULL</span><span class="sxs-lookup"><span data-stu-id="5f977-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5f977-120">Пример</span><span class="sxs-lookup"><span data-stu-id="5f977-120">Example</span></span>  
 <span data-ttu-id="5f977-121">Следующий запрос Entity SQL демонстрирует, как использовать оператор AND.</span><span class="sxs-lookup"><span data-stu-id="5f977-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="5f977-122">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="5f977-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5f977-123">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="5f977-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="5f977-124">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5f977-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="5f977-125">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5f977-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="5f977-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5f977-126">See also</span></span>

- [<span data-ttu-id="5f977-127">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5f977-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
