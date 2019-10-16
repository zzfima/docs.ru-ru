---
title: (Остаток от деления) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: 4bbdbe53403cfec2568cfac320fc7ab1ad2725b0
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319605"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="92811-102">(Остаток от деления) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="92811-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="92811-103">Возвращает остаток от деления значения одного выражения на другое.</span><span class="sxs-lookup"><span data-stu-id="92811-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92811-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92811-104">Syntax</span></span>  
  
```sql  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="92811-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="92811-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="92811-106">Делимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="92811-106">The numeric expression to divide.</span></span> <span data-ttu-id="92811-107">`dividend` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="92811-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="92811-108">Числовое выражение, на которое делится делимое.</span><span class="sxs-lookup"><span data-stu-id="92811-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="92811-109">`divisor` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="92811-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="92811-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="92811-110">Result Types</span></span>  
 <span data-ttu-id="92811-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="92811-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="92811-112">Пример</span><span class="sxs-lookup"><span data-stu-id="92811-112">Example</span></span>  
 <span data-ttu-id="92811-113">В следующем запросе Entity SQL используется арифметический оператор % для получения остатка от деления одного выражения на другое.</span><span class="sxs-lookup"><span data-stu-id="92811-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="92811-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="92811-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="92811-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="92811-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="92811-116">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="92811-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="92811-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="92811-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#MODULO](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="92811-118">См. также</span><span class="sxs-lookup"><span data-stu-id="92811-118">See also</span></span>

- [<span data-ttu-id="92811-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="92811-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
