---
title: '> (Больше) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: 0b57f36681575ccbe3239220e89804c804f13f39
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250886"
---
# <a name="-greater-than-entity-sql"></a><span data-ttu-id="ade33-102">> (Больше) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ade33-102">> (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="ade33-103">Сравнивает два выражения и определяет, имеет ли левое выражение значение больше значения правого выражения.</span><span class="sxs-lookup"><span data-stu-id="ade33-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ade33-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ade33-104">Syntax</span></span>  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ade33-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ade33-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ade33-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="ade33-106">Any valid expression.</span></span> <span data-ttu-id="ade33-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="ade33-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ade33-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="ade33-108">Result Types</span></span>  
 <span data-ttu-id="ade33-109">Значение`true` , если левое выражение больше правого. В противном случае - значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ade33-109">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ade33-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ade33-110">Example</span></span>  
 <span data-ttu-id="ade33-111">Следующий запрос Entity SQL использует оператор сравнения > для сравнения двух выражений и определяет, имеет ли левое выражение значение, большее значения правого выражения.</span><span class="sxs-lookup"><span data-stu-id="ade33-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="ade33-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="ade33-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ade33-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="ade33-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ade33-114">Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.</span><span class="sxs-lookup"><span data-stu-id="ade33-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ade33-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ade33-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="ade33-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ade33-116">See also</span></span>

- [<span data-ttu-id="ade33-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ade33-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
