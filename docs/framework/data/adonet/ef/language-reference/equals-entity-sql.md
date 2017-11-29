---
title: "= (равно) (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 12de808403ee6714d2bcfd15da4e67a8596e1ff1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="18cbc-102">= (равно) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="18cbc-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="18cbc-103">Проверяет равенство двух выражений.</span><span class="sxs-lookup"><span data-stu-id="18cbc-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18cbc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18cbc-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="18cbc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="18cbc-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="18cbc-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="18cbc-106">Any valid expression.</span></span> <span data-ttu-id="18cbc-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="18cbc-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="18cbc-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="18cbc-108">Result Types</span></span>  
 <span data-ttu-id="18cbc-109">Имеет значение`true` , если левое выражение равно правому выражению. В противном случае имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="18cbc-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18cbc-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="18cbc-110">Remarks</span></span>  
 <span data-ttu-id="18cbc-111">Оператор == эквивалентен оператору =.</span><span class="sxs-lookup"><span data-stu-id="18cbc-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18cbc-112">Пример</span><span class="sxs-lookup"><span data-stu-id="18cbc-112">Example</span></span>  
 <span data-ttu-id="18cbc-113">В следующем запросе Entity SQL оператор сравнения = используется для сравнения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="18cbc-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="18cbc-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="18cbc-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="18cbc-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="18cbc-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="18cbc-116">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="18cbc-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="18cbc-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="18cbc-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="18cbc-118">См. также</span><span class="sxs-lookup"><span data-stu-id="18cbc-118">See Also</span></span>  
 [<span data-ttu-id="18cbc-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="18cbc-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
