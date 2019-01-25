---
title: '&gt;= (больше или равно) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: 34326072f4772e74a45e0ffb6ea1e35f1596b206
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697153"
---
# <a name="gt-greater-than-or-equal-to-entity-sql"></a><span data-ttu-id="8f85e-102">&gt;= (больше или равно) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8f85e-102">&gt;= (Greater Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="8f85e-103">Сравнивает два выражения и определяет, имеет ли левое выражение значение, большее или равное значению правого выражения.</span><span class="sxs-lookup"><span data-stu-id="8f85e-103">Compares two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f85e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f85e-104">Syntax</span></span>  
  
```  
expression >= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="8f85e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8f85e-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8f85e-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="8f85e-106">Any valid expression.</span></span> <span data-ttu-id="8f85e-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="8f85e-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8f85e-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="8f85e-108">Result Types</span></span>  
 <span data-ttu-id="8f85e-109">Значение`true` , если левое выражение больше или равно правому. В противном случае - значение `false`.</span><span class="sxs-lookup"><span data-stu-id="8f85e-109">`true` if the left expression has a value greater than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f85e-110">Пример</span><span class="sxs-lookup"><span data-stu-id="8f85e-110">Example</span></span>  
 <span data-ttu-id="8f85e-111">Следующий запрос Entity SQL использует оператор сравнения >= для сравнения двух выражений и определяет, имеет ли левое выражение значение, большее или равное значению правого выражения.</span><span class="sxs-lookup"><span data-stu-id="8f85e-111">The following Entity SQL query uses >= comparison operator to compare two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span> <span data-ttu-id="8f85e-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="8f85e-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8f85e-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="8f85e-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="8f85e-114">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8f85e-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="8f85e-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="8f85e-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="8f85e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8f85e-116">See also</span></span>
- [<span data-ttu-id="8f85e-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8f85e-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
