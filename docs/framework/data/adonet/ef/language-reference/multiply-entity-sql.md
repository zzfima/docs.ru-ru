---
title: '* (Умножение) (Язык entity SQL)'
ms.date: 03/30/2017
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
ms.openlocfilehash: 68544823d2279b76920e057829fc61a469d39730
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493863"
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="b6300-102">\* (умножение) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b6300-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="b6300-103">Умножает два выражения.</span><span class="sxs-lookup"><span data-stu-id="b6300-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6300-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6300-104">Syntax</span></span>  
  
```  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b6300-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b6300-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b6300-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="b6300-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b6300-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="b6300-107">Result Types</span></span>  
 <span data-ttu-id="b6300-108">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="b6300-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="b6300-109">Дополнительные сведения о неявном повышении уровня типов, см. в разделе [система типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b6300-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6300-110">Пример</span><span class="sxs-lookup"><span data-stu-id="b6300-110">Example</span></span>  
 <span data-ttu-id="b6300-111">В следующем запросе Entity SQL арифметический оператор умножения (\*) используется для умножения двух чисел.</span><span class="sxs-lookup"><span data-stu-id="b6300-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="b6300-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b6300-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b6300-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="b6300-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b6300-114">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b6300-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="b6300-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b6300-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTIPLY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="b6300-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b6300-116">See also</span></span>
- [<span data-ttu-id="b6300-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b6300-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
