---
title: = (равно) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: bda314208a25426be321ba307be96067b1df2ac8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="a4023-102">= (равно) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a4023-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="a4023-103">Проверяет равенство двух выражений.</span><span class="sxs-lookup"><span data-stu-id="a4023-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4023-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4023-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a4023-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a4023-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a4023-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="a4023-106">Any valid expression.</span></span> <span data-ttu-id="a4023-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="a4023-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a4023-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="a4023-108">Result Types</span></span>  
 <span data-ttu-id="a4023-109">Имеет значение`true` , если левое выражение равно правому выражению. В противном случае имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="a4023-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4023-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="a4023-110">Remarks</span></span>  
 <span data-ttu-id="a4023-111">Оператор == эквивалентен оператору =.</span><span class="sxs-lookup"><span data-stu-id="a4023-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4023-112">Пример</span><span class="sxs-lookup"><span data-stu-id="a4023-112">Example</span></span>  
 <span data-ttu-id="a4023-113">В следующем запросе Entity SQL оператор сравнения = используется для сравнения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="a4023-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="a4023-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="a4023-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a4023-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="a4023-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a4023-116">Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a4023-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="a4023-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a4023-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="a4023-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a4023-118">See Also</span></span>  
 [<span data-ttu-id="a4023-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a4023-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
