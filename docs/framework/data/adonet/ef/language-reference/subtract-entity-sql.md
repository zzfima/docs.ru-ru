---
title: '- (Вычитание) (Язык entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: 2e4c08788ea57000e189c8371f0494641931184b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316691"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="d45cc-102">- (вычитание) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d45cc-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="d45cc-103">Вычитает одно число из другого.</span><span class="sxs-lookup"><span data-stu-id="d45cc-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d45cc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d45cc-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d45cc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d45cc-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d45cc-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="d45cc-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d45cc-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="d45cc-107">Result Types</span></span>  
 <span data-ttu-id="d45cc-108">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="d45cc-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="d45cc-109">Дополнительные сведения о неявном повышении уровня типов, см. в разделе [система типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d45cc-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d45cc-110">Пример</span><span class="sxs-lookup"><span data-stu-id="d45cc-110">Example</span></span>  
 <span data-ttu-id="d45cc-111">Следующий запрос Entity SQL использует арифметический оператор вычитания (-) для вычитания одного числа из другого.</span><span class="sxs-lookup"><span data-stu-id="d45cc-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="d45cc-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="d45cc-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d45cc-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="d45cc-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d45cc-114">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d45cc-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d45cc-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d45cc-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="d45cc-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d45cc-116">See also</span></span>

- [<span data-ttu-id="d45cc-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d45cc-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
