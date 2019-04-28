---
title: '!= (не равно) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: f5fdbbf2892781ce44dfe73e8cd80fbe0f74cf1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760341"
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="6d56d-102">!= (не равно) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6d56d-102">!= (Not Equal To) (Entity SQL)</span></span>
<span data-ttu-id="6d56d-103">Сравнивает два выражения, чтобы определить, является ли значение левого выражения не равным значению правого выражения.</span><span class="sxs-lookup"><span data-stu-id="6d56d-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="6d56d-104">Действие оператора != (не равно) эквивалентно действию оператора <>.</span><span class="sxs-lookup"><span data-stu-id="6d56d-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d56d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d56d-105">Syntax</span></span>  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="6d56d-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6d56d-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6d56d-107">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="6d56d-107">Any valid expression.</span></span> <span data-ttu-id="6d56d-108">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="6d56d-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6d56d-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="6d56d-109">Result Types</span></span>  
 <span data-ttu-id="6d56d-110">`true` , если значение левого выражения не равно значению правого; в противном случае - `false`.</span><span class="sxs-lookup"><span data-stu-id="6d56d-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d56d-111">Пример</span><span class="sxs-lookup"><span data-stu-id="6d56d-111">Example</span></span>  
 <span data-ttu-id="6d56d-112">В следующем запросе Entity SQL оператор != используется для сравнения двух выражений, чтобы определить, отличается ли значение левого выражения от значения правого.</span><span class="sxs-lookup"><span data-stu-id="6d56d-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="6d56d-113">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="6d56d-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6d56d-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="6d56d-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6d56d-115">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6d56d-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6d56d-116">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6d56d-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="6d56d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6d56d-117">See also</span></span>

- [<span data-ttu-id="6d56d-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6d56d-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
