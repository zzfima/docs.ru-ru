---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: 16be25336bac386c993eae7527c9377be1073d1e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319277"
---
# <a name="top-entity-sql"></a><span data-ttu-id="48163-102">TOP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="48163-102">TOP (Entity SQL)</span></span>

<span data-ttu-id="48163-103">Предложение SELECT может иметь необязательное вложенное предложение TOP, которое следует за необязательным модификатором ALL/DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="48163-103">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="48163-104">Предложение TOP указывает, что в результатах запроса возвращается только набор первых строк.</span><span class="sxs-lookup"><span data-stu-id="48163-104">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span>

## <a name="syntax"></a><span data-ttu-id="48163-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48163-105">Syntax</span></span>

```sql
[ TOP (n) ]
```

## <a name="arguments"></a><span data-ttu-id="48163-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="48163-106">Arguments</span></span>

<span data-ttu-id="48163-107">`n` числовое выражение, задающее количество возвращаемых строк.</span><span class="sxs-lookup"><span data-stu-id="48163-107">`n` The numeric expression that specifies the number of rows to be returned.</span></span> <span data-ttu-id="48163-108">`n` может быть одним числовым литералом или одним параметром.</span><span class="sxs-lookup"><span data-stu-id="48163-108">`n` could be a single numeric literal or a single parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="48163-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="48163-109">Remarks</span></span>

<span data-ttu-id="48163-110">Выражение TOP должно быть одним числовым литералом или одним параметром.</span><span class="sxs-lookup"><span data-stu-id="48163-110">The TOP expression must be either a single numeric literal or a single parameter.</span></span> <span data-ttu-id="48163-111">При использовании постоянного литерала он должен поддерживать неявное повышение до Edm.Int64 (byte, int16, int32 и int64 или любой тип поставщика, который сопоставляется с типом, поддерживающим повышение до Edm.Int64), а его значение должно быть больше или равно нулю.</span><span class="sxs-lookup"><span data-stu-id="48163-111">If a constant literal is used, the literal type must be implicitly promotable to Edm.Int64 (byte, int16, int32 or int64 or any provider type that maps to a type that is promotable to Edm.Int64) and its value must be greater than or equal to zero.</span></span> <span data-ttu-id="48163-112">В противном случае возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="48163-112">Otherwise an exception will be raised.</span></span> <span data-ttu-id="48163-113">Если в качестве выражения используется параметр, то тип параметра также должен поддерживать неявное повышение до Edm.Int64, однако проверка фактического значения параметра во время компиляции проводиться не будет, поскольку значения параметров связываются в режиме позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="48163-113">If a parameter is used as an expression, the parameter type must also be implicitly promotable to Edm.Int64, but there will be no validation of the actual parameter value during compilation because the parameter values are late bounded.</span></span>

<span data-ttu-id="48163-114">Ниже приведен пример постоянного выражения TOP:</span><span class="sxs-lookup"><span data-stu-id="48163-114">The following is an example of constant TOP expression:</span></span>

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

<span data-ttu-id="48163-115">Ниже приведен пример параметризованного выражения TOP:</span><span class="sxs-lookup"><span data-stu-id="48163-115">The following is an example of parameterized TOP expression:</span></span>

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

<span data-ttu-id="48163-116">Выражение TOP является недетерминированным, если запрос не отсортирован.</span><span class="sxs-lookup"><span data-stu-id="48163-116">TOP is non-deterministic unless the query is sorted.</span></span> <span data-ttu-id="48163-117">При необходимости в детерминированном результате используйте вложенные предложения [SKIP](skip-entity-sql.md) и [LIMIT](limit-entity-sql.md) в предложении [ORDER BY](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="48163-117">If you require a deterministic result, use the [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses in the [ORDER BY](order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="48163-118">Предложения TOP и SKIP/LIMIT являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="48163-118">The TOP and SKIP/LIMIT are mutually exclusive.</span></span>

## <a name="example"></a><span data-ttu-id="48163-119">Пример</span><span class="sxs-lookup"><span data-stu-id="48163-119">Example</span></span>

<span data-ttu-id="48163-120">В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] для указания верхней строки, которую следует вернуть из результата запроса, используется выражение TOP.</span><span class="sxs-lookup"><span data-stu-id="48163-120">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TOP to specify the top one row to be returned from the query result.</span></span> <span data-ttu-id="48163-121">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="48163-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="48163-122">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="48163-122">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="48163-123">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="48163-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="48163-124">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="48163-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

    [!code-sql[DP EntityServices Concepts#TOP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#top)]

## <a name="see-also"></a><span data-ttu-id="48163-125">См. также</span><span class="sxs-lookup"><span data-stu-id="48163-125">See also</span></span>

- [<span data-ttu-id="48163-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="48163-126">SELECT</span></span>](select-entity-sql.md)
- [<span data-ttu-id="48163-127">SKIP</span><span class="sxs-lookup"><span data-stu-id="48163-127">SKIP</span></span>](skip-entity-sql.md)
- [<span data-ttu-id="48163-128">LIMIT</span><span class="sxs-lookup"><span data-stu-id="48163-128">LIMIT</span></span>](limit-entity-sql.md)
- [<span data-ttu-id="48163-129">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="48163-129">ORDER BY</span></span>](order-by-entity-sql.md)
- [<span data-ttu-id="48163-130">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="48163-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
