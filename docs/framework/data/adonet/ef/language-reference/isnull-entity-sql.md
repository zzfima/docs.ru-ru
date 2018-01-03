---
title: ISNULL (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 7d880328c1006f418d50c02083e92f97b67627e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="cee7a-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cee7a-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="cee7a-103">Определяет, имеет ли выражение запроса значение null.</span><span class="sxs-lookup"><span data-stu-id="cee7a-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cee7a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cee7a-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="cee7a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cee7a-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="cee7a-106">Любое допустимое выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="cee7a-106">Any valid query expression.</span></span> <span data-ttu-id="cee7a-107">Не может быть коллекцией, содержать элементы коллекции или тип записи со свойствами типа коллекции.</span><span class="sxs-lookup"><span data-stu-id="cee7a-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="cee7a-108">NOT</span><span class="sxs-lookup"><span data-stu-id="cee7a-108">NOT</span></span>  
 <span data-ttu-id="cee7a-109">Логически инвертирует результат EDM.Boolean для IS NULL.</span><span class="sxs-lookup"><span data-stu-id="cee7a-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cee7a-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cee7a-110">Return Value</span></span>  
 <span data-ttu-id="cee7a-111">Значение `true`, если выражение `expression` возвращает значение NULL, либо значение `false` - в противном случае.</span><span class="sxs-lookup"><span data-stu-id="cee7a-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cee7a-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="cee7a-112">Remarks</span></span>  
 <span data-ttu-id="cee7a-113">Ключевое слово `IS NULL` позволяет определить, имеет ли элемент внешнего соединения значение NULL.</span><span class="sxs-lookup"><span data-stu-id="cee7a-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="cee7a-114">Ключевое слово `IS NULL` позволяет определить, имеет ли элемент фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="cee7a-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="cee7a-115">В следующей таблице показан эффект применения оператора `IS NULL` в различных конструкциях.</span><span class="sxs-lookup"><span data-stu-id="cee7a-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="cee7a-116">Все исключения формируются на стороне клиента перед вызовом поставщика.</span><span class="sxs-lookup"><span data-stu-id="cee7a-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="cee7a-117">Шаблон</span><span class="sxs-lookup"><span data-stu-id="cee7a-117">Pattern</span></span>|<span data-ttu-id="cee7a-118">Поведение</span><span class="sxs-lookup"><span data-stu-id="cee7a-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="cee7a-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="cee7a-119">null IS NULL</span></span>|<span data-ttu-id="cee7a-120">Возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="cee7a-120">Returns `true`.</span></span>|  
|<span data-ttu-id="cee7a-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="cee7a-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="cee7a-122">Возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="cee7a-122">Returns `true`.</span></span>|  
|<span data-ttu-id="cee7a-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="cee7a-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="cee7a-124">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="cee7a-124">Throws an error.</span></span>|  
|<span data-ttu-id="cee7a-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="cee7a-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="cee7a-126">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="cee7a-126">Throws an error.</span></span>|  
|<span data-ttu-id="cee7a-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="cee7a-127">EntityType IS NULL</span></span>|<span data-ttu-id="cee7a-128">Возвращает значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="cee7a-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="cee7a-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="cee7a-129">ComplexType IS NULL</span></span>|<span data-ttu-id="cee7a-130">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="cee7a-130">Throws an error.</span></span>|  
|<span data-ttu-id="cee7a-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="cee7a-131">RowType IS NULL</span></span>|<span data-ttu-id="cee7a-132">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="cee7a-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cee7a-133">Пример</span><span class="sxs-lookup"><span data-stu-id="cee7a-133">Example</span></span>  
 <span data-ttu-id="cee7a-134">Следующие [!INCLUDE[esql](../../../../../../includes/esql-md.md)] запроса оператор IS NOT NULL определяет, отличается ли выражение запроса значение null.</span><span class="sxs-lookup"><span data-stu-id="cee7a-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="cee7a-135">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="cee7a-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cee7a-136">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="cee7a-136">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="cee7a-137">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cee7a-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="cee7a-138">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="cee7a-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="cee7a-139">См. также</span><span class="sxs-lookup"><span data-stu-id="cee7a-139">See Also</span></span>  
 [<span data-ttu-id="cee7a-140">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cee7a-140">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
