---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: aaecce3ff74d64b8e07b31329ced5b5e581fca5b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295098"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="9110d-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9110d-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="9110d-103">Определяет, имеет ли выражение запроса значение null.</span><span class="sxs-lookup"><span data-stu-id="9110d-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9110d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9110d-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="9110d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9110d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9110d-106">Любое допустимое выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="9110d-106">Any valid query expression.</span></span> <span data-ttu-id="9110d-107">Не может быть коллекцией, содержать элементы коллекции или тип записи со свойствами типа коллекции.</span><span class="sxs-lookup"><span data-stu-id="9110d-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="9110d-108">NOT</span><span class="sxs-lookup"><span data-stu-id="9110d-108">NOT</span></span>  
 <span data-ttu-id="9110d-109">Логически инвертирует результат EDM.Boolean для IS NULL.</span><span class="sxs-lookup"><span data-stu-id="9110d-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9110d-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9110d-110">Return Value</span></span>  
 `true` <span data-ttu-id="9110d-111">Если `expression` возвращает значение null, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="9110d-111">if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9110d-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="9110d-112">Remarks</span></span>  
 <span data-ttu-id="9110d-113">Ключевое слово `IS NULL` позволяет определить, имеет ли элемент внешнего соединения значение NULL.</span><span class="sxs-lookup"><span data-stu-id="9110d-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="9110d-114">Ключевое слово `IS NULL` позволяет определить, имеет ли элемент фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="9110d-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="9110d-115">В следующей таблице показан эффект применения оператора `IS NULL` в различных конструкциях.</span><span class="sxs-lookup"><span data-stu-id="9110d-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="9110d-116">Все исключения формируются на стороне клиента перед вызовом поставщика.</span><span class="sxs-lookup"><span data-stu-id="9110d-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="9110d-117">Шаблон</span><span class="sxs-lookup"><span data-stu-id="9110d-117">Pattern</span></span>|<span data-ttu-id="9110d-118">Поведение</span><span class="sxs-lookup"><span data-stu-id="9110d-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="9110d-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="9110d-119">null IS NULL</span></span>|<span data-ttu-id="9110d-120">Возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="9110d-120">Returns `true`.</span></span>|  
|<span data-ttu-id="9110d-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="9110d-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="9110d-122">Возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="9110d-122">Returns `true`.</span></span>|  
|<span data-ttu-id="9110d-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="9110d-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="9110d-124">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="9110d-124">Throws an error.</span></span>|  
|<span data-ttu-id="9110d-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="9110d-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="9110d-126">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="9110d-126">Throws an error.</span></span>|  
|<span data-ttu-id="9110d-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="9110d-127">EntityType IS NULL</span></span>|<span data-ttu-id="9110d-128">Возвращает значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="9110d-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="9110d-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="9110d-129">ComplexType IS NULL</span></span>|<span data-ttu-id="9110d-130">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="9110d-130">Throws an error.</span></span>|  
|<span data-ttu-id="9110d-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="9110d-131">RowType IS NULL</span></span>|<span data-ttu-id="9110d-132">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="9110d-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9110d-133">Пример</span><span class="sxs-lookup"><span data-stu-id="9110d-133">Example</span></span>  
 <span data-ttu-id="9110d-134">Следующие [!INCLUDE[esql](../../../../../../includes/esql-md.md)] запросе используется оператор IS NOT NULL, чтобы определить, если выражение запроса не равно null.</span><span class="sxs-lookup"><span data-stu-id="9110d-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="9110d-135">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="9110d-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9110d-136">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="9110d-136">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="9110d-137">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="9110d-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="9110d-138">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="9110d-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="9110d-139">См. также</span><span class="sxs-lookup"><span data-stu-id="9110d-139">See also</span></span>

- [<span data-ttu-id="9110d-140">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9110d-140">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
