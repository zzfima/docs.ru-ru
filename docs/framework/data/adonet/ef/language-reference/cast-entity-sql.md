---
title: CAST (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
ms.openlocfilehash: c16270babe4daa8e703b24b27211c6fd6f53677d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039917"
---
# <a name="cast-entity-sql"></a><span data-ttu-id="096c4-102">CAST (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="096c4-102">CAST (Entity SQL)</span></span>
<span data-ttu-id="096c4-103">Преобразует выражение одного типа данных в другой.</span><span class="sxs-lookup"><span data-stu-id="096c4-103">Converts an expression of one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="096c4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="096c4-104">Syntax</span></span>  
  
```csharp
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="096c4-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="096c4-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="096c4-106">Любое допустимое выражение, которое можно преобразовать в `data_type`.</span><span class="sxs-lookup"><span data-stu-id="096c4-106">Any valid expression that is convertible to `data_type`.</span></span>  
  
 `data_type`  
 <span data-ttu-id="096c4-107">Целевой тип данных, предоставляемый системой.</span><span class="sxs-lookup"><span data-stu-id="096c4-107">The target system-supplied data type.</span></span> <span data-ttu-id="096c4-108">Это должен быть (скалярный) тип-примитив.</span><span class="sxs-lookup"><span data-stu-id="096c4-108">It must be a primitive (scalar) type.</span></span> <span data-ttu-id="096c4-109">Какой тип `data_type` будет использован, зависит от области запроса.</span><span class="sxs-lookup"><span data-stu-id="096c4-109">The `data_type` used depends on the query space.</span></span> <span data-ttu-id="096c4-110">Если запрос выполняется с командой <xref:System.Data.EntityClient.EntityCommand>, то типом данных будет тип, определенный в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="096c4-110">If a query is executed with the <xref:System.Data.EntityClient.EntityCommand>, the data type is a type defined in the conceptual model.</span></span> <span data-ttu-id="096c4-111">Для получения дополнительной информации см. [CSDL Specification](csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="096c4-111">For more information, see [CSDL Specification](csdl-specification.md).</span></span> <span data-ttu-id="096c4-112">Если запрос выполняется командой <xref:System.Data.Objects.ObjectQuery%601>, то этим типом данных будет тип CLR.</span><span class="sxs-lookup"><span data-stu-id="096c4-112">If a query is executed with <xref:System.Data.Objects.ObjectQuery%601>, the data type is a common language runtime (CLR) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="096c4-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="096c4-113">Return Value</span></span>  
 <span data-ttu-id="096c4-114">Возвращает значение такого же типа, что и аргумент `data_type`.</span><span class="sxs-lookup"><span data-stu-id="096c4-114">Returns the same value as `data_type`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="096c4-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="096c4-115">Remarks</span></span>  
 <span data-ttu-id="096c4-116">Выражение приведения имеет аналогичную семантику выражения Transact-SQL CONVERT.</span><span class="sxs-lookup"><span data-stu-id="096c4-116">The cast expression has similar semantics to the Transact-SQL CONVERT expression.</span></span> <span data-ttu-id="096c4-117">Выражение явного приведения используется для преобразования значения одного типа в значение другого типа.</span><span class="sxs-lookup"><span data-stu-id="096c4-117">The cast expression is used to convert a value of one type into a value of another type.</span></span>  
  
```csharp
CAST( e as T )  
```  
  
 <span data-ttu-id="096c4-118">Если «e» имеет некий тип S, а S можно преобразовать в T, то приведенное выше выражение является допустимым выражением явного приведения.</span><span class="sxs-lookup"><span data-stu-id="096c4-118">If e is of some type S, and S is convertible to T, then the above expression is a valid cast expression.</span></span> <span data-ttu-id="096c4-119">Т должно иметь (скалярный) тип-примитив.</span><span class="sxs-lookup"><span data-stu-id="096c4-119">T must be a primitive (scalar) type.</span></span>  
  
 <span data-ttu-id="096c4-120">При явном приведении к `Edm.Decimal`можно дополнительно указать значения аспектов точности и масштаба.</span><span class="sxs-lookup"><span data-stu-id="096c4-120">Values for the precision and scale facets may optionally be provided when casting to `Edm.Decimal`.</span></span> <span data-ttu-id="096c4-121">Если они не заданы явным образом, принимаются значения по умолчанию для точности и масштаба 18 и 0 соответственно.</span><span class="sxs-lookup"><span data-stu-id="096c4-121">If not explicitly provided, the default values for precision and scale are 18 and 0, respectively.</span></span> <span data-ttu-id="096c4-122">В частности, для `Decimal`поддерживаются следующие перегрузки:</span><span class="sxs-lookup"><span data-stu-id="096c4-122">Specifically, the following overloads are supported for `Decimal`:</span></span>  
  
- `CAST( d as Edm.Decimal );`  
  
- `CAST( d as Edm.Decimal(precision) );`  
  
- `CAST( d as Edm.Decimal(precision, scale) );`  
  
 <span data-ttu-id="096c4-123">Использование выражения явного приведения считается явным преобразованием.</span><span class="sxs-lookup"><span data-stu-id="096c4-123">The use of a cast expression is considered an explicit conversion.</span></span> <span data-ttu-id="096c4-124">При явном преобразовании возможно усечение данных и потеря точности.</span><span class="sxs-lookup"><span data-stu-id="096c4-124">Explicit conversions might truncate data or lose precision.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="096c4-125">Операция CAST может выполняться только над типами-примитивами и типами элементов перечисления.</span><span class="sxs-lookup"><span data-stu-id="096c4-125">CAST is only supported over primitive types and enumeration member types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="096c4-126">Пример</span><span class="sxs-lookup"><span data-stu-id="096c4-126">Example</span></span>  
 <span data-ttu-id="096c4-127">В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор CAST используется для явного приведения выражения одного типа данных к другому.</span><span class="sxs-lookup"><span data-stu-id="096c4-127">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the CAST operator to cast an expression of one data type to another.</span></span> <span data-ttu-id="096c4-128">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="096c4-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="096c4-129">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="096c4-129">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="096c4-130">Выполните процедуру, описанную в разделе [инструкции. выполнение запроса, возвращающего тип PrimitiveType результаты](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="096c4-130">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="096c4-131">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="096c4-131">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a><span data-ttu-id="096c4-132">См. также</span><span class="sxs-lookup"><span data-stu-id="096c4-132">See also</span></span>

- [<span data-ttu-id="096c4-133">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="096c4-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
