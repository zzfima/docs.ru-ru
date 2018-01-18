---
title: TOP (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 10967ac87fa8f8504dc9a6a29be99401e620085e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="top-entity-sql"></a><span data-ttu-id="d3984-102">TOP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d3984-102">TOP (Entity SQL)</span></span>
<span data-ttu-id="d3984-103">Предложение SELECT может иметь необязательное вложенное предложение TOP, которое следует за необязательным модификатором ALL/DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="d3984-103">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="d3984-104">Предложение TOP указывает, что в результатах запроса возвращается только набор первых строк.</span><span class="sxs-lookup"><span data-stu-id="d3984-104">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3984-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3984-105">Syntax</span></span>  
  
```  
[ TOP (n) ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d3984-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d3984-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="d3984-107">Числовое выражение, указывающее количество строк, которые необходимо вернуть.</span><span class="sxs-lookup"><span data-stu-id="d3984-107">The numeric expression that specifies the number of rows to be returned.</span></span> <span data-ttu-id="d3984-108">`n` может быть одним числовым литералом или одним параметром.</span><span class="sxs-lookup"><span data-stu-id="d3984-108">`n` could be a single numeric literal or a single parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3984-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3984-109">Remarks</span></span>  
 <span data-ttu-id="d3984-110">Выражение TOP должно быть одним числовым литералом или одним параметром.</span><span class="sxs-lookup"><span data-stu-id="d3984-110">The TOP expression must be either a single numeric literal or a single parameter.</span></span> <span data-ttu-id="d3984-111">При использовании постоянного литерала он должен поддерживать неявное повышение до Edm.Int64 (byte, int16, int32 и int64 или любой тип поставщика, который сопоставляется с типом, поддерживающим повышение до Edm.Int64), а его значение должно быть больше или равно нулю.</span><span class="sxs-lookup"><span data-stu-id="d3984-111">If a constant literal is used, the literal type must be implicitly promotable to Edm.Int64 (byte, int16, int32 or int64 or any provider type that maps to a type that is promotable to Edm.Int64) and its value must be greater than or equal to zero.</span></span> <span data-ttu-id="d3984-112">В противном случае возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="d3984-112">Otherwise an exception will be raised.</span></span> <span data-ttu-id="d3984-113">Если в качестве выражения используется параметр, то тип параметра также должен поддерживать неявное повышение до Edm.Int64, однако проверка фактического значения параметра во время компиляции проводиться не будет, поскольку значения параметров связываются в режиме позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="d3984-113">If a parameter is used as an expression, the parameter type must also be implicitly promotable to Edm.Int64, but there will be no validation of the actual parameter value during compilation because the parameter values are late bounded.</span></span>  
  
 <span data-ttu-id="d3984-114">Ниже приведен пример постоянного выражения TOP:</span><span class="sxs-lookup"><span data-stu-id="d3984-114">The following is an example of constant TOP expression:</span></span>  
  
 `select distinct top(10) c.a1, c.a2 from T as a`  
  
 <span data-ttu-id="d3984-115">Ниже приведен пример параметризованного выражения TOP:</span><span class="sxs-lookup"><span data-stu-id="d3984-115">The following is an example of parametrized TOP expression:</span></span>  
  
 `select distinct top(@topParam) c.a1, c.a2 from T as a`  
  
 <span data-ttu-id="d3984-116">Выражение TOP является недетерминированным, если запрос не отсортирован.</span><span class="sxs-lookup"><span data-stu-id="d3984-116">TOP is non-deterministic unless the query is sorted.</span></span> <span data-ttu-id="d3984-117">При необходимости в детерминированном результате используйте вложенные предложения [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) и [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) в предложении [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="d3984-117">If you require a deterministic result, use the [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses in the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="d3984-118">Предложения TOP и SKIP/LIMIT являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="d3984-118">The TOP and SKIP/LIMIT are mutually exclusive.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3984-119">Пример</span><span class="sxs-lookup"><span data-stu-id="d3984-119">Example</span></span>  
 <span data-ttu-id="d3984-120">В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] для указания верхней строки, которую следует вернуть из результата запроса, используется выражение TOP.</span><span class="sxs-lookup"><span data-stu-id="d3984-120">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TOP to specify the top one row to be returned from the query result.</span></span> <span data-ttu-id="d3984-121">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="d3984-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d3984-122">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="d3984-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d3984-123">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d3984-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="d3984-124">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d3984-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]  
  
## <a name="see-also"></a><span data-ttu-id="d3984-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d3984-125">See Also</span></span>  
 [<span data-ttu-id="d3984-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="d3984-126">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [<span data-ttu-id="d3984-127">SKIP</span><span class="sxs-lookup"><span data-stu-id="d3984-127">SKIP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
 [<span data-ttu-id="d3984-128">LIMIT</span><span class="sxs-lookup"><span data-stu-id="d3984-128">LIMIT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
 [<span data-ttu-id="d3984-129">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="d3984-129">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [<span data-ttu-id="d3984-130">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d3984-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
