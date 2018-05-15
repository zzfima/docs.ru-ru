---
title: TREAT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: 932f335bf6a502b031dcf09b8050e278a0bbe9f8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="treat-entity-sql"></a><span data-ttu-id="5355e-102">TREAT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5355e-102">TREAT (Entity SQL)</span></span>
<span data-ttu-id="5355e-103">Обрабатывает объект некоторого базового типа, как объект указанного производного типа.</span><span class="sxs-lookup"><span data-stu-id="5355e-103">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5355e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5355e-104">Syntax</span></span>  
  
```  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="5355e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5355e-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="5355e-106">Любое допустимое выражение запроса, возвращающее сущность.</span><span class="sxs-lookup"><span data-stu-id="5355e-106">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5355e-107">Тип указанного выражения должен быть подтипом указанного типа данных, либо тип данных должен быть подтипом типа выражения.</span><span class="sxs-lookup"><span data-stu-id="5355e-107">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="5355e-108">Тип сущности.</span><span class="sxs-lookup"><span data-stu-id="5355e-108">An entity type.</span></span> <span data-ttu-id="5355e-109">Для типа должно быть указано пространство имен.</span><span class="sxs-lookup"><span data-stu-id="5355e-109">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5355e-110">Указанное выражение должно быть подтипом указанного типа данных, либо тип данных должен быть подтипом данного выражения.</span><span class="sxs-lookup"><span data-stu-id="5355e-110">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5355e-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5355e-111">Return Value</span></span>  
 <span data-ttu-id="5355e-112">Значение указанного типа данных.</span><span class="sxs-lookup"><span data-stu-id="5355e-112">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5355e-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="5355e-113">Remarks</span></span>  
 <span data-ttu-id="5355e-114">Оператор TREAT предназначен для приведения связанных классов к базовому типу.</span><span class="sxs-lookup"><span data-stu-id="5355e-114">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="5355e-115">Например, если тип `Employee` является производным от типа `Person` , а «p» относится к типу `Person`, то выражение `TREAT(p AS NamespaceName.Employee)` приводит общий экземпляр типа `Person` к типу `Employee`. Иными словами, он позволяет обрабатывать «p» как тип `Employee`.</span><span class="sxs-lookup"><span data-stu-id="5355e-115">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="5355e-116">Оператор TREAT используется в сценариях наследования, в которых можно выполнить запрос наподобие следующего.</span><span class="sxs-lookup"><span data-stu-id="5355e-116">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 <span data-ttu-id="5355e-117">Этот запрос приводит сущности `Person` к типу `Employee` .</span><span class="sxs-lookup"><span data-stu-id="5355e-117">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="5355e-118">Если значение «p» фактически не относится к типу `Employee`, то выражение имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="5355e-118">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5355e-119">Указанное выражение `Employee` должен быть подтипом указанного типа данных `Person`, либо тип данных должен быть подтипом данного выражения.</span><span class="sxs-lookup"><span data-stu-id="5355e-119">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="5355e-120">В противном случае это выражение вызовет ошибку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="5355e-120">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="5355e-121">Следующая таблица показывает, каким образом оператор TREAT работает с некоторыми стандартными и не очень часто используемыми конструкциями.</span><span class="sxs-lookup"><span data-stu-id="5355e-121">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="5355e-122">Все исключения формируются на стороне клиента перед вызовом поставщика.</span><span class="sxs-lookup"><span data-stu-id="5355e-122">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="5355e-123">Шаблон</span><span class="sxs-lookup"><span data-stu-id="5355e-123">Pattern</span></span>|<span data-ttu-id="5355e-124">Поведение</span><span class="sxs-lookup"><span data-stu-id="5355e-124">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="5355e-125">Возвращает `DbNull`.</span><span class="sxs-lookup"><span data-stu-id="5355e-125">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="5355e-126">Создает исключение.</span><span class="sxs-lookup"><span data-stu-id="5355e-126">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="5355e-127">Создает исключение/</span><span class="sxs-lookup"><span data-stu-id="5355e-127">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="5355e-128">Возвращает значение `EntityType` или `null`.</span><span class="sxs-lookup"><span data-stu-id="5355e-128">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="5355e-129">Создает исключение.</span><span class="sxs-lookup"><span data-stu-id="5355e-129">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="5355e-130">Создает исключение.</span><span class="sxs-lookup"><span data-stu-id="5355e-130">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5355e-131">Пример</span><span class="sxs-lookup"><span data-stu-id="5355e-131">Example</span></span>  
 <span data-ttu-id="5355e-132">В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор TREAT используется для преобразования объекта типа Course в коллекцию объектов типа OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="5355e-132">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="5355e-133">Запрос основан на [модели School](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span><span class="sxs-lookup"><span data-stu-id="5355e-133">The query is based on the [School Model](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="5355e-134">См. также</span><span class="sxs-lookup"><span data-stu-id="5355e-134">See Also</span></span>  
 [<span data-ttu-id="5355e-135">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5355e-135">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="5355e-136">Допускающие значения NULL структурированные типы</span><span class="sxs-lookup"><span data-stu-id="5355e-136">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
