---
title: '* Перемножаемых (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
ms.openlocfilehash: 7006f5143e8cc18156f748ae7664f3787c9ff5c9
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319611"
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="5d35c-102">\* (умножение) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5d35c-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="5d35c-103">Умножает два выражения.</span><span class="sxs-lookup"><span data-stu-id="5d35c-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d35c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d35c-104">Syntax</span></span>  
  
```sql  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="5d35c-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5d35c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="5d35c-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="5d35c-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5d35c-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="5d35c-107">Result Types</span></span>  
 <span data-ttu-id="5d35c-108">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="5d35c-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="5d35c-109">Дополнительные сведения о неявном повышении типа см. в разделе [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5d35c-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d35c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="5d35c-110">Example</span></span>  
 <span data-ttu-id="5d35c-111">В следующем запросе Entity SQL арифметический оператор умножения (\*) используется для умножения двух чисел.</span><span class="sxs-lookup"><span data-stu-id="5d35c-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="5d35c-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="5d35c-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5d35c-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="5d35c-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="5d35c-114">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5d35c-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="5d35c-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5d35c-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#MULTIPLY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="5d35c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5d35c-116">See also</span></span>

- [<span data-ttu-id="5d35c-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5d35c-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
