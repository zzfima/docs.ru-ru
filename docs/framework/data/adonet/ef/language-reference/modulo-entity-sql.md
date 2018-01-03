---
title: "(Остаток от деления) (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a04b2972c80aff654331aeb319390b6f817374bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="35cd1-102">(Остаток от деления) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="35cd1-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="35cd1-103">Возвращает остаток от деления значения одного выражения на другое.</span><span class="sxs-lookup"><span data-stu-id="35cd1-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35cd1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35cd1-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="35cd1-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="35cd1-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="35cd1-106">Делимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="35cd1-106">The numeric expression to divide.</span></span> <span data-ttu-id="35cd1-107">`dividend` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="35cd1-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="35cd1-108">Числовое выражение, на которое делится делимое.</span><span class="sxs-lookup"><span data-stu-id="35cd1-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="35cd1-109">`divisor` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="35cd1-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="35cd1-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="35cd1-110">Result Types</span></span>  
 <span data-ttu-id="35cd1-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="35cd1-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="35cd1-112">Пример</span><span class="sxs-lookup"><span data-stu-id="35cd1-112">Example</span></span>  
 <span data-ttu-id="35cd1-113">В следующем запросе Entity SQL используется арифметический оператор % для получения остатка от деления одного выражения на другое.</span><span class="sxs-lookup"><span data-stu-id="35cd1-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="35cd1-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="35cd1-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="35cd1-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="35cd1-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="35cd1-116">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="35cd1-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="35cd1-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="35cd1-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="35cd1-118">См. также</span><span class="sxs-lookup"><span data-stu-id="35cd1-118">See Also</span></span>  
 [<span data-ttu-id="35cd1-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="35cd1-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
