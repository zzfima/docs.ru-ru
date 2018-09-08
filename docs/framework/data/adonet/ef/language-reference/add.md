---
title: + (Добавить)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: a3c41ef8cf393a4d1b1deb362d6a3614558a34ba
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44129246"
---
# <a name="-add"></a><span data-ttu-id="cff66-102">+ (сложение)</span><span class="sxs-lookup"><span data-stu-id="cff66-102">+ (Add)</span></span>
<span data-ttu-id="cff66-103">Складывает два числа.</span><span class="sxs-lookup"><span data-stu-id="cff66-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff66-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cff66-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="cff66-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cff66-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="cff66-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="cff66-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="cff66-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="cff66-107">Result Types</span></span>  
 <span data-ttu-id="cff66-108">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="cff66-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="cff66-109">Дополнительные сведения о неявном повышении уровня типов, см. в разделе [система типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="cff66-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cff66-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="cff66-110">Remarks</span></span>  
 <span data-ttu-id="cff66-111">Для типов EDM.String сложение является объединением строк.</span><span class="sxs-lookup"><span data-stu-id="cff66-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cff66-112">Пример</span><span class="sxs-lookup"><span data-stu-id="cff66-112">Example</span></span>  
 <span data-ttu-id="cff66-113">В следующем запросе Entity SQL арифметический оператор сложения (+) используется для сложения двух чисел.</span><span class="sxs-lookup"><span data-stu-id="cff66-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="cff66-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="cff66-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cff66-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="cff66-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="cff66-116">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cff66-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="cff66-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="cff66-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="cff66-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cff66-118">See Also</span></span>  
 [<span data-ttu-id="cff66-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cff66-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="cff66-120">Типы концептуальной модели (CSDL)</span><span class="sxs-lookup"><span data-stu-id="cff66-120">Conceptual Model Types (CSDL)</span></span>](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
