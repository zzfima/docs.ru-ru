---
title: '- Деление (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 79fdbebc648daac4f695387d52d2a915383f99ca
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833892"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="40a1d-102">/ (деление) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="40a1d-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="40a1d-103">Делит одно число на другое.</span><span class="sxs-lookup"><span data-stu-id="40a1d-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40a1d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40a1d-104">Syntax</span></span>  
  
```sql  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="40a1d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="40a1d-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="40a1d-106">Делимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="40a1d-106">The numeric expression to divide.</span></span> <span data-ttu-id="40a1d-107">`dividend` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="40a1d-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="40a1d-108">Числовое выражение, на которое делится делимое.</span><span class="sxs-lookup"><span data-stu-id="40a1d-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="40a1d-109">`divisor` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="40a1d-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="40a1d-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="40a1d-110">Result Types</span></span>  
 <span data-ttu-id="40a1d-111">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="40a1d-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="40a1d-112">Дополнительные сведения о неявном повышении типа см. в разделе [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="40a1d-112">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40a1d-113">Пример</span><span class="sxs-lookup"><span data-stu-id="40a1d-113">Example</span></span>  
 <span data-ttu-id="40a1d-114">Следующий Entity SQL запрос использует арифметический оператор/для деления одного числа на другое.</span><span class="sxs-lookup"><span data-stu-id="40a1d-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="40a1d-115">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="40a1d-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="40a1d-116">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="40a1d-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="40a1d-117">Выполните процедуру, описанную в разделе [How: Выполните запрос, возвращающий Структуралтипе Results @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="40a1d-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="40a1d-118">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="40a1d-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#DIVIDE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="40a1d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="40a1d-119">See also</span></span>

- [<span data-ttu-id="40a1d-120">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="40a1d-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
