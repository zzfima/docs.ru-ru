---
title: '>= (Больше или равно) (язык Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: b5a8a834c325cca38e2c106ca3f8ee829dd699b2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317146"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a><span data-ttu-id="7ddf7-102">> = (больше или равно) (язык Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7ddf7-102">>= (Greater Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="7ddf7-103">Сравнивает два выражения и определяет, имеет ли левое выражение значение, большее или равное значению правого выражения.</span><span class="sxs-lookup"><span data-stu-id="7ddf7-103">Compares two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ddf7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ddf7-104">Syntax</span></span>  
  
```  
expression >= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="7ddf7-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7ddf7-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="7ddf7-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="7ddf7-106">Any valid expression.</span></span> <span data-ttu-id="7ddf7-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="7ddf7-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7ddf7-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="7ddf7-108">Result Types</span></span>  
 `true` <span data-ttu-id="7ddf7-109">Если левое выражение значение больше или равно правому выражению. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="7ddf7-109">if the left expression has a value greater than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ddf7-110">Пример</span><span class="sxs-lookup"><span data-stu-id="7ddf7-110">Example</span></span>  
 <span data-ttu-id="7ddf7-111">Следующий запрос Entity SQL использует оператор сравнения >= для сравнения двух выражений и определяет, имеет ли левое выражение значение, большее или равное значению правого выражения.</span><span class="sxs-lookup"><span data-stu-id="7ddf7-111">The following Entity SQL query uses >= comparison operator to compare two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span> <span data-ttu-id="7ddf7-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="7ddf7-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7ddf7-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="7ddf7-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7ddf7-114">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="7ddf7-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="7ddf7-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="7ddf7-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="7ddf7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7ddf7-116">See also</span></span>

- [<span data-ttu-id="7ddf7-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="7ddf7-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
