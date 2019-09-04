---
title: = (равно) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: ec87ec682e1773c001c225567a35b3cedc9c5aba
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251004"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="fb768-102">= (равно) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fb768-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="fb768-103">Проверяет равенство двух выражений.</span><span class="sxs-lookup"><span data-stu-id="fb768-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb768-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb768-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="fb768-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fb768-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="fb768-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="fb768-106">Any valid expression.</span></span> <span data-ttu-id="fb768-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="fb768-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="fb768-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="fb768-108">Result Types</span></span>  
 <span data-ttu-id="fb768-109">Имеет значение`true` , если левое выражение равно правому выражению. В противном случае имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="fb768-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb768-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb768-110">Remarks</span></span>  
 <span data-ttu-id="fb768-111">Оператор == эквивалентен оператору =.</span><span class="sxs-lookup"><span data-stu-id="fb768-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb768-112">Пример</span><span class="sxs-lookup"><span data-stu-id="fb768-112">Example</span></span>  
 <span data-ttu-id="fb768-113">В следующем запросе Entity SQL оператор сравнения = используется для сравнения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="fb768-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="fb768-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="fb768-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="fb768-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="fb768-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="fb768-116">Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.</span><span class="sxs-lookup"><span data-stu-id="fb768-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="fb768-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="fb768-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="fb768-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fb768-118">See also</span></span>

- [<span data-ttu-id="fb768-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fb768-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
