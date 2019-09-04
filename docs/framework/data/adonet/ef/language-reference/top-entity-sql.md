---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: 8b55519b7f95deb6463af4c0a6a2a53975e5b5a2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248976"
---
# <a name="top-entity-sql"></a><span data-ttu-id="49fdc-102">TOP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="49fdc-102">TOP (Entity SQL)</span></span>

<span data-ttu-id="49fdc-103">Предложение SELECT может иметь необязательное вложенное предложение TOP, которое следует за необязательным модификатором ALL/DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="49fdc-103">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="49fdc-104">Предложение TOP указывает, что в результатах запроса возвращается только набор первых строк.</span><span class="sxs-lookup"><span data-stu-id="49fdc-104">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span>

## <a name="syntax"></a><span data-ttu-id="49fdc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49fdc-105">Syntax</span></span>

```
[ TOP (n) ]
```

## <a name="arguments"></a><span data-ttu-id="49fdc-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="49fdc-106">Arguments</span></span>

<span data-ttu-id="49fdc-107">`n`Числовое выражение, задающее количество возвращаемых строк.</span><span class="sxs-lookup"><span data-stu-id="49fdc-107">`n` The numeric expression that specifies the number of rows to be returned.</span></span> <span data-ttu-id="49fdc-108">`n` может быть одним числовым литералом или одним параметром.</span><span class="sxs-lookup"><span data-stu-id="49fdc-108">`n` could be a single numeric literal or a single parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="49fdc-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="49fdc-109">Remarks</span></span>

<span data-ttu-id="49fdc-110">Выражение TOP должно быть одним числовым литералом или одним параметром.</span><span class="sxs-lookup"><span data-stu-id="49fdc-110">The TOP expression must be either a single numeric literal or a single parameter.</span></span> <span data-ttu-id="49fdc-111">При использовании постоянного литерала он должен поддерживать неявное повышение до Edm.Int64 (byte, int16, int32 и int64 или любой тип поставщика, который сопоставляется с типом, поддерживающим повышение до Edm.Int64), а его значение должно быть больше или равно нулю.</span><span class="sxs-lookup"><span data-stu-id="49fdc-111">If a constant literal is used, the literal type must be implicitly promotable to Edm.Int64 (byte, int16, int32 or int64 or any provider type that maps to a type that is promotable to Edm.Int64) and its value must be greater than or equal to zero.</span></span> <span data-ttu-id="49fdc-112">В противном случае возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="49fdc-112">Otherwise an exception will be raised.</span></span> <span data-ttu-id="49fdc-113">Если в качестве выражения используется параметр, то тип параметра также должен поддерживать неявное повышение до Edm.Int64, однако проверка фактического значения параметра во время компиляции проводиться не будет, поскольку значения параметров связываются в режиме позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="49fdc-113">If a parameter is used as an expression, the parameter type must also be implicitly promotable to Edm.Int64, but there will be no validation of the actual parameter value during compilation because the parameter values are late bounded.</span></span>

<span data-ttu-id="49fdc-114">Ниже приведен пример постоянного выражения TOP:</span><span class="sxs-lookup"><span data-stu-id="49fdc-114">The following is an example of constant TOP expression:</span></span>

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

<span data-ttu-id="49fdc-115">Ниже приведен пример параметризованного выражения TOP:</span><span class="sxs-lookup"><span data-stu-id="49fdc-115">The following is an example of parameterized TOP expression:</span></span>

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

<span data-ttu-id="49fdc-116">Выражение TOP является недетерминированным, если запрос не отсортирован.</span><span class="sxs-lookup"><span data-stu-id="49fdc-116">TOP is non-deterministic unless the query is sorted.</span></span> <span data-ttu-id="49fdc-117">При необходимости в детерминированном результате используйте вложенные предложения [SKIP](skip-entity-sql.md) и [LIMIT](limit-entity-sql.md) в предложении [ORDER BY](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="49fdc-117">If you require a deterministic result, use the [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses in the [ORDER BY](order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="49fdc-118">Предложения TOP и SKIP/LIMIT являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="49fdc-118">The TOP and SKIP/LIMIT are mutually exclusive.</span></span>

## <a name="example"></a><span data-ttu-id="49fdc-119">Пример</span><span class="sxs-lookup"><span data-stu-id="49fdc-119">Example</span></span>

<span data-ttu-id="49fdc-120">В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] для указания верхней строки, которую следует вернуть из результата запроса, используется выражение TOP.</span><span class="sxs-lookup"><span data-stu-id="49fdc-120">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TOP to specify the top one row to be returned from the query result.</span></span> <span data-ttu-id="49fdc-121">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="49fdc-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="49fdc-122">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="49fdc-122">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="49fdc-123">Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.</span><span class="sxs-lookup"><span data-stu-id="49fdc-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="49fdc-124">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="49fdc-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

    [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]

## <a name="see-also"></a><span data-ttu-id="49fdc-125">См. также</span><span class="sxs-lookup"><span data-stu-id="49fdc-125">See also</span></span>

- [<span data-ttu-id="49fdc-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="49fdc-126">SELECT</span></span>](select-entity-sql.md)
- [<span data-ttu-id="49fdc-127">SKIP</span><span class="sxs-lookup"><span data-stu-id="49fdc-127">SKIP</span></span>](skip-entity-sql.md)
- [<span data-ttu-id="49fdc-128">LIMIT</span><span class="sxs-lookup"><span data-stu-id="49fdc-128">LIMIT</span></span>](limit-entity-sql.md)
- [<span data-ttu-id="49fdc-129">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="49fdc-129">ORDER BY</span></span>](order-by-entity-sql.md)
- [<span data-ttu-id="49fdc-130">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="49fdc-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
