---
title: CAST (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
ms.openlocfilehash: afa92cc46aba9def65dddd490a2df3350c163af9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143166"
---
# <a name="cast-entity-sql"></a><span data-ttu-id="3af12-102">CAST (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3af12-102">CAST (Entity SQL)</span></span>
<span data-ttu-id="3af12-103">Преобразует выражение одного типа данных в другой.</span><span class="sxs-lookup"><span data-stu-id="3af12-103">Converts an expression of one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3af12-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3af12-104">Syntax</span></span>  
  
```  
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="3af12-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3af12-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3af12-106">Любое допустимое выражение, которое можно преобразовать в `data_type`.</span><span class="sxs-lookup"><span data-stu-id="3af12-106">Any valid expression that is convertible to `data_type`.</span></span>  
  
 `data_type`  
 <span data-ttu-id="3af12-107">Целевой тип данных, предоставляемый системой.</span><span class="sxs-lookup"><span data-stu-id="3af12-107">The target system-supplied data type.</span></span> <span data-ttu-id="3af12-108">Это должен быть (скалярный) тип-примитив.</span><span class="sxs-lookup"><span data-stu-id="3af12-108">It must be a primitive (scalar) type.</span></span> <span data-ttu-id="3af12-109">Какой тип `data_type` будет использован, зависит от области запроса.</span><span class="sxs-lookup"><span data-stu-id="3af12-109">The `data_type` used depends on the query space.</span></span> <span data-ttu-id="3af12-110">Если запрос выполняется с командой <xref:System.Data.EntityClient.EntityCommand>, то типом данных будет тип, определенный в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="3af12-110">If a query is executed with the <xref:System.Data.EntityClient.EntityCommand>, the data type is a type defined in the conceptual model.</span></span> <span data-ttu-id="3af12-111">Для получения дополнительной информации см. [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="3af12-111">For more information, see [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span> <span data-ttu-id="3af12-112">Если запрос выполняется командой <xref:System.Data.Objects.ObjectQuery%601>, то этим типом данных будет тип CLR.</span><span class="sxs-lookup"><span data-stu-id="3af12-112">If a query is executed with <xref:System.Data.Objects.ObjectQuery%601>, the data type is a common language runtime (CLR) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3af12-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3af12-113">Return Value</span></span>  
 <span data-ttu-id="3af12-114">Возвращает значение такого же типа, что и аргумент `data_type`.</span><span class="sxs-lookup"><span data-stu-id="3af12-114">Returns the same value as `data_type`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3af12-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="3af12-115">Remarks</span></span>  
 <span data-ttu-id="3af12-116">Семантика выражения явного приведения такая же, как у выражения [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT.</span><span class="sxs-lookup"><span data-stu-id="3af12-116">The cast expression has similar semantics to the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT expression.</span></span> <span data-ttu-id="3af12-117">Выражение явного приведения используется для преобразования значения одного типа в значение другого типа.</span><span class="sxs-lookup"><span data-stu-id="3af12-117">The cast expression is used to convert a value of one type into a value of another type.</span></span>  
  
```  
CAST( e as T )  
```  
  
 <span data-ttu-id="3af12-118">Если «e» имеет некий тип S, а S можно преобразовать в T, то приведенное выше выражение является допустимым выражением явного приведения.</span><span class="sxs-lookup"><span data-stu-id="3af12-118">If e is of some type S, and S is convertible to T, then the above expression is a valid cast expression.</span></span> <span data-ttu-id="3af12-119">Т должно иметь (скалярный) тип-примитив.</span><span class="sxs-lookup"><span data-stu-id="3af12-119">T must be a primitive (scalar) type.</span></span>  
  
 <span data-ttu-id="3af12-120">При явном приведении к `Edm.Decimal`можно дополнительно указать значения аспектов точности и масштаба.</span><span class="sxs-lookup"><span data-stu-id="3af12-120">Values for the precision and scale facets may optionally be provided when casting to `Edm.Decimal`.</span></span> <span data-ttu-id="3af12-121">Если они не заданы явным образом, принимаются значения по умолчанию для точности и масштаба 18 и 0 соответственно.</span><span class="sxs-lookup"><span data-stu-id="3af12-121">If not explicitly provided, the default values for precision and scale are 18 and 0, respectively.</span></span> <span data-ttu-id="3af12-122">В частности, для `Decimal`поддерживаются следующие перегрузки:</span><span class="sxs-lookup"><span data-stu-id="3af12-122">Specifically, the following overloads are supported for `Decimal`:</span></span>  
  
-   `CAST( d as Edm.Decimal );`  
  
-   `CAST( d as Edm.Decimal(precision) );`  
  
-   `CAST( d as Edm.Decimal(precision, scale) );`  
  
 <span data-ttu-id="3af12-123">Использование выражения явного приведения считается явным преобразованием.</span><span class="sxs-lookup"><span data-stu-id="3af12-123">The use of a cast expression is considered an explicit conversion.</span></span> <span data-ttu-id="3af12-124">При явном преобразовании возможно усечение данных и потеря точности.</span><span class="sxs-lookup"><span data-stu-id="3af12-124">Explicit conversions might truncate data or lose precision.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3af12-125">Операция CAST может выполняться только над типами-примитивами и типами элементов перечисления.</span><span class="sxs-lookup"><span data-stu-id="3af12-125">CAST is only supported over primitive types and enumeration member types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3af12-126">Пример</span><span class="sxs-lookup"><span data-stu-id="3af12-126">Example</span></span>  
 <span data-ttu-id="3af12-127">В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор CAST используется для явного приведения выражения одного типа данных к другому.</span><span class="sxs-lookup"><span data-stu-id="3af12-127">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the CAST operator to cast an expression of one data type to another.</span></span> <span data-ttu-id="3af12-128">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="3af12-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3af12-129">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="3af12-129">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3af12-130">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3af12-130">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="3af12-131">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3af12-131">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a><span data-ttu-id="3af12-132">См. также</span><span class="sxs-lookup"><span data-stu-id="3af12-132">See also</span></span>

- [<span data-ttu-id="3af12-133">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3af12-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
