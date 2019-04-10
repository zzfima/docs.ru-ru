---
title: '- (Деление) (Язык entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: c3b477a63adf3c3d51f28449e94c2b716422296c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59330861"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="85c05-102">/ (деление) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="85c05-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="85c05-103">Делит одно число на другое.</span><span class="sxs-lookup"><span data-stu-id="85c05-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85c05-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="85c05-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="85c05-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="85c05-106">Делимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="85c05-106">The numeric expression to divide.</span></span> `dividend` <span data-ttu-id="85c05-107">— любое допустимое выражение любого из числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="85c05-107">is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="85c05-108">Числовое выражение, на которое делится делимое.</span><span class="sxs-lookup"><span data-stu-id="85c05-108">The numeric expression to divide the dividend by.</span></span> `divisor` <span data-ttu-id="85c05-109">— любое допустимое выражение любого из числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="85c05-109">is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="85c05-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="85c05-110">Result Types</span></span>  
 <span data-ttu-id="85c05-111">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="85c05-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="85c05-112">Дополнительные сведения о неявном повышении уровня типов, см. в разделе [система типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="85c05-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85c05-113">Пример</span><span class="sxs-lookup"><span data-stu-id="85c05-113">Example</span></span>  
 <span data-ttu-id="85c05-114">В следующем запросе Entity SQL используется арифметический оператор деления для деления одного числа на другое.</span><span class="sxs-lookup"><span data-stu-id="85c05-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="85c05-115">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="85c05-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="85c05-116">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="85c05-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="85c05-117">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="85c05-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="85c05-118">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="85c05-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="85c05-119">См. также</span><span class="sxs-lookup"><span data-stu-id="85c05-119">See also</span></span>

- [<span data-ttu-id="85c05-120">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="85c05-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
