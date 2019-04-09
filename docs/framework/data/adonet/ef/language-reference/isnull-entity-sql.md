---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 894d3ab91623aa4246bf7735fb1b7d04e066825a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072640"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="b46b6-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b46b6-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="b46b6-103">Определяет, имеет ли выражение запроса значение null.</span><span class="sxs-lookup"><span data-stu-id="b46b6-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b46b6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b46b6-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="b46b6-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b46b6-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b46b6-106">Любое допустимое выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="b46b6-106">Any valid query expression.</span></span> <span data-ttu-id="b46b6-107">Не может быть коллекцией, содержать элементы коллекции или тип записи со свойствами типа коллекции.</span><span class="sxs-lookup"><span data-stu-id="b46b6-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="b46b6-108">NOT</span><span class="sxs-lookup"><span data-stu-id="b46b6-108">NOT</span></span>  
 <span data-ttu-id="b46b6-109">Логически инвертирует результат EDM.Boolean для IS NULL.</span><span class="sxs-lookup"><span data-stu-id="b46b6-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b46b6-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b46b6-110">Return Value</span></span>  
 `true` <span data-ttu-id="b46b6-111">Если `expression` возвращает значение null, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="b46b6-111">if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b46b6-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="b46b6-112">Remarks</span></span>  
 <span data-ttu-id="b46b6-113">Ключевое слово `IS NULL` позволяет определить, имеет ли элемент внешнего соединения значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b46b6-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="b46b6-114">Ключевое слово `IS NULL` позволяет определить, имеет ли элемент фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="b46b6-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="b46b6-115">В следующей таблице показан эффект применения оператора `IS NULL` в различных конструкциях.</span><span class="sxs-lookup"><span data-stu-id="b46b6-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="b46b6-116">Все исключения формируются на стороне клиента перед вызовом поставщика.</span><span class="sxs-lookup"><span data-stu-id="b46b6-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="b46b6-117">Шаблон</span><span class="sxs-lookup"><span data-stu-id="b46b6-117">Pattern</span></span>|<span data-ttu-id="b46b6-118">Поведение</span><span class="sxs-lookup"><span data-stu-id="b46b6-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="b46b6-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="b46b6-119">null IS NULL</span></span>|<span data-ttu-id="b46b6-120">Возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="b46b6-120">Returns `true`.</span></span>|  
|<span data-ttu-id="b46b6-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="b46b6-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="b46b6-122">Возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="b46b6-122">Returns `true`.</span></span>|  
|<span data-ttu-id="b46b6-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="b46b6-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="b46b6-124">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="b46b6-124">Throws an error.</span></span>|  
|<span data-ttu-id="b46b6-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="b46b6-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="b46b6-126">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="b46b6-126">Throws an error.</span></span>|  
|<span data-ttu-id="b46b6-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="b46b6-127">EntityType IS NULL</span></span>|<span data-ttu-id="b46b6-128">Возвращает значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="b46b6-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="b46b6-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="b46b6-129">ComplexType IS NULL</span></span>|<span data-ttu-id="b46b6-130">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="b46b6-130">Throws an error.</span></span>|  
|<span data-ttu-id="b46b6-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="b46b6-131">RowType IS NULL</span></span>|<span data-ttu-id="b46b6-132">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="b46b6-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b46b6-133">Пример</span><span class="sxs-lookup"><span data-stu-id="b46b6-133">Example</span></span>  
 <span data-ttu-id="b46b6-134">Следующие [!INCLUDE[esql](../../../../../../includes/esql-md.md)] запросе используется оператор IS NOT NULL, чтобы определить, если выражение запроса не равно null.</span><span class="sxs-lookup"><span data-stu-id="b46b6-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="b46b6-135">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b46b6-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b46b6-136">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="b46b6-136">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b46b6-137">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b46b6-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="b46b6-138">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b46b6-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="b46b6-139">См. также</span><span class="sxs-lookup"><span data-stu-id="b46b6-139">See also</span></span>

- [<span data-ttu-id="b46b6-140">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b46b6-140">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
