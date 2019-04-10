---
title: = (равно) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: d50ede1964f6d6b9025a7214efe90e878aa55a0c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333162"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="0c37f-102">= (равно) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0c37f-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="0c37f-103">Проверяет равенство двух выражений.</span><span class="sxs-lookup"><span data-stu-id="0c37f-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c37f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c37f-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="0c37f-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0c37f-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="0c37f-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="0c37f-106">Any valid expression.</span></span> <span data-ttu-id="0c37f-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="0c37f-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0c37f-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="0c37f-108">Result Types</span></span>  
 `true` <span data-ttu-id="0c37f-109">Если левое выражение равно правому выражению. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="0c37f-109">if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c37f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c37f-110">Remarks</span></span>  
 <span data-ttu-id="0c37f-111">Оператор == эквивалентен оператору =.</span><span class="sxs-lookup"><span data-stu-id="0c37f-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c37f-112">Пример</span><span class="sxs-lookup"><span data-stu-id="0c37f-112">Example</span></span>  
 <span data-ttu-id="0c37f-113">В следующем запросе Entity SQL оператор сравнения = используется для сравнения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="0c37f-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="0c37f-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="0c37f-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0c37f-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="0c37f-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="0c37f-116">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="0c37f-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="0c37f-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="0c37f-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="0c37f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0c37f-118">See also</span></span>

- [<span data-ttu-id="0c37f-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0c37f-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
