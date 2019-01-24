---
title: '- (Деление) (Язык entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 42fc5e2a9f9f159a8a60973dbed6540b3188fba6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745239"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="2e5fd-102">/ (деление) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2e5fd-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="2e5fd-103">Делит одно число на другое.</span><span class="sxs-lookup"><span data-stu-id="2e5fd-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e5fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e5fd-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="2e5fd-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2e5fd-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="2e5fd-106">Делимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="2e5fd-106">The numeric expression to divide.</span></span> <span data-ttu-id="2e5fd-107">`dividend` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="2e5fd-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="2e5fd-108">Числовое выражение, на которое делится делимое.</span><span class="sxs-lookup"><span data-stu-id="2e5fd-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="2e5fd-109">`divisor` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="2e5fd-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2e5fd-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="2e5fd-110">Result Types</span></span>  
 <span data-ttu-id="2e5fd-111">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="2e5fd-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="2e5fd-112">Дополнительные сведения о неявном повышении уровня типов, см. в разделе [система типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2e5fd-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e5fd-113">Пример</span><span class="sxs-lookup"><span data-stu-id="2e5fd-113">Example</span></span>  
 <span data-ttu-id="2e5fd-114">В следующем запросе Entity SQL используется арифметический оператор деления для деления одного числа на другое.</span><span class="sxs-lookup"><span data-stu-id="2e5fd-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="2e5fd-115">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="2e5fd-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2e5fd-116">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="2e5fd-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="2e5fd-117">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2e5fd-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="2e5fd-118">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="2e5fd-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="2e5fd-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2e5fd-119">See also</span></span>
- [<span data-ttu-id="2e5fd-120">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2e5fd-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
