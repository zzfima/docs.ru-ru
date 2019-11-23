---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: e46db63600b6baa03697615a2f5eb9240f55d15e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833697"
---
# <a name="in-entity-sql"></a><span data-ttu-id="fc7f7-102">IN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fc7f7-102">IN (Entity SQL)</span></span>
<span data-ttu-id="fc7f7-103">Определяет, совпадает ли значение с каким-либо значением в коллекции.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-103">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc7f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc7f7-104">Syntax</span></span>  
  
```sql  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="fc7f7-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fc7f7-105">Arguments</span></span>  
 `value`  
 <span data-ttu-id="fc7f7-106">Любое допустимое выражение, возвращающее значение для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-106">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="fc7f7-107">[ NOT ]</span><span class="sxs-lookup"><span data-stu-id="fc7f7-107">[ NOT ]</span></span>  
 <span data-ttu-id="fc7f7-108">Указывает, что значение `Boolean` оператора IN следует инвертировать.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-108">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="fc7f7-109">Любое допустимое выражение, возвращающее коллекцию для проверки соответствия.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-109">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="fc7f7-110">Все выражения должны иметь тот же тип, что и аргумент `value`, или принадлежать к базовому или производному типу для типа этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-110">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc7f7-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fc7f7-111">Return Value</span></span>  
 <span data-ttu-id="fc7f7-112">`true`, если значение найдено в коллекции; значение null, если значение равно null или коллекция имеет значение null; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-112">`true` if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="fc7f7-113">Использование NOT IN логически инвертирует результат IN.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-113">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc7f7-114">Пример</span><span class="sxs-lookup"><span data-stu-id="fc7f7-114">Example</span></span>  
 <span data-ttu-id="fc7f7-115">В следующем запросе на языке Entity SQL оператор IN используется для определения, совпадает ли значение с каким-либо значением в коллекции.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-115">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="fc7f7-116">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="fc7f7-117">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="fc7f7-118">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="fc7f7-119">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="fc7f7-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a><span data-ttu-id="fc7f7-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc7f7-120">See also</span></span>

- [<span data-ttu-id="fc7f7-121">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fc7f7-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
