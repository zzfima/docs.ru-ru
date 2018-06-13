---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 70ec49fd4643c67c6ad08fdda9166eeb8a64d254
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763245"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="3354e-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3354e-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="3354e-103">Определяет, имеет ли выражение запроса значение null.</span><span class="sxs-lookup"><span data-stu-id="3354e-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3354e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3354e-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="3354e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3354e-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3354e-106">Любое допустимое выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="3354e-106">Any valid query expression.</span></span> <span data-ttu-id="3354e-107">Не может быть коллекцией, содержать элементы коллекции или тип записи со свойствами типа коллекции.</span><span class="sxs-lookup"><span data-stu-id="3354e-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="3354e-108">NOT</span><span class="sxs-lookup"><span data-stu-id="3354e-108">NOT</span></span>  
 <span data-ttu-id="3354e-109">Логически инвертирует результат EDM.Boolean для IS NULL.</span><span class="sxs-lookup"><span data-stu-id="3354e-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3354e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3354e-110">Return Value</span></span>  
 <span data-ttu-id="3354e-111">Значение `true`, если выражение `expression` возвращает значение NULL, либо значение `false` - в противном случае.</span><span class="sxs-lookup"><span data-stu-id="3354e-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3354e-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="3354e-112">Remarks</span></span>  
 <span data-ttu-id="3354e-113">Ключевое слово `IS NULL` позволяет определить, имеет ли элемент внешнего соединения значение NULL.</span><span class="sxs-lookup"><span data-stu-id="3354e-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="3354e-114">Ключевое слово `IS NULL` позволяет определить, имеет ли элемент фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="3354e-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="3354e-115">В следующей таблице показан эффект применения оператора `IS NULL` в различных конструкциях.</span><span class="sxs-lookup"><span data-stu-id="3354e-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="3354e-116">Все исключения формируются на стороне клиента перед вызовом поставщика.</span><span class="sxs-lookup"><span data-stu-id="3354e-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="3354e-117">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3354e-117">Pattern</span></span>|<span data-ttu-id="3354e-118">Поведение</span><span class="sxs-lookup"><span data-stu-id="3354e-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="3354e-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="3354e-119">null IS NULL</span></span>|<span data-ttu-id="3354e-120">Возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="3354e-120">Returns `true`.</span></span>|  
|<span data-ttu-id="3354e-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="3354e-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="3354e-122">Возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="3354e-122">Returns `true`.</span></span>|  
|<span data-ttu-id="3354e-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="3354e-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="3354e-124">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="3354e-124">Throws an error.</span></span>|  
|<span data-ttu-id="3354e-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="3354e-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="3354e-126">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="3354e-126">Throws an error.</span></span>|  
|<span data-ttu-id="3354e-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="3354e-127">EntityType IS NULL</span></span>|<span data-ttu-id="3354e-128">Возвращает значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="3354e-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="3354e-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="3354e-129">ComplexType IS NULL</span></span>|<span data-ttu-id="3354e-130">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="3354e-130">Throws an error.</span></span>|  
|<span data-ttu-id="3354e-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="3354e-131">RowType IS NULL</span></span>|<span data-ttu-id="3354e-132">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="3354e-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3354e-133">Пример</span><span class="sxs-lookup"><span data-stu-id="3354e-133">Example</span></span>  
 <span data-ttu-id="3354e-134">Следующие [!INCLUDE[esql](../../../../../../includes/esql-md.md)] запроса оператор IS NOT NULL определяет, отличается ли выражение запроса значение null.</span><span class="sxs-lookup"><span data-stu-id="3354e-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="3354e-135">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="3354e-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3354e-136">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="3354e-136">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3354e-137">Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3354e-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="3354e-138">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3354e-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="3354e-139">См. также</span><span class="sxs-lookup"><span data-stu-id="3354e-139">See Also</span></span>  
 [<span data-ttu-id="3354e-140">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3354e-140">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
