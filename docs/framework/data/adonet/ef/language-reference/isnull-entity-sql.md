---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 9066f9fb68ce2c50e9523881cfa0dd930cd0b52e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319734"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="59bcb-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="59bcb-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="59bcb-103">Определяет, имеет ли выражение запроса значение null.</span><span class="sxs-lookup"><span data-stu-id="59bcb-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59bcb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59bcb-104">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="59bcb-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="59bcb-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="59bcb-106">Любое допустимое выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="59bcb-106">Any valid query expression.</span></span> <span data-ttu-id="59bcb-107">Не может быть коллекцией, содержать элементы коллекции или тип записи со свойствами типа коллекции.</span><span class="sxs-lookup"><span data-stu-id="59bcb-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="59bcb-108">NOT</span><span class="sxs-lookup"><span data-stu-id="59bcb-108">NOT</span></span>  
 <span data-ttu-id="59bcb-109">Логически инвертирует результат EDM.Boolean для IS NULL.</span><span class="sxs-lookup"><span data-stu-id="59bcb-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59bcb-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="59bcb-110">Return Value</span></span>  
 <span data-ttu-id="59bcb-111">Значение `true`, если выражение `expression` возвращает значение NULL, либо значение `false` - в противном случае.</span><span class="sxs-lookup"><span data-stu-id="59bcb-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59bcb-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="59bcb-112">Remarks</span></span>  
 <span data-ttu-id="59bcb-113">Ключевое слово `IS NULL` позволяет определить, имеет ли элемент внешнего соединения значение NULL.</span><span class="sxs-lookup"><span data-stu-id="59bcb-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```sql  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="59bcb-114">Ключевое слово `IS NULL` позволяет определить, имеет ли элемент фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="59bcb-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="59bcb-115">В следующей таблице показан эффект применения оператора `IS NULL` в различных конструкциях.</span><span class="sxs-lookup"><span data-stu-id="59bcb-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="59bcb-116">Все исключения формируются на стороне клиента перед вызовом поставщика.</span><span class="sxs-lookup"><span data-stu-id="59bcb-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="59bcb-117">Шаблон</span><span class="sxs-lookup"><span data-stu-id="59bcb-117">Pattern</span></span>|<span data-ttu-id="59bcb-118">Поведение</span><span class="sxs-lookup"><span data-stu-id="59bcb-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="59bcb-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="59bcb-119">null IS NULL</span></span>|<span data-ttu-id="59bcb-120">Возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="59bcb-120">Returns `true`.</span></span>|  
|<span data-ttu-id="59bcb-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="59bcb-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="59bcb-122">Возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="59bcb-122">Returns `true`.</span></span>|  
|<span data-ttu-id="59bcb-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="59bcb-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="59bcb-124">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="59bcb-124">Throws an error.</span></span>|  
|<span data-ttu-id="59bcb-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="59bcb-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="59bcb-126">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="59bcb-126">Throws an error.</span></span>|  
|<span data-ttu-id="59bcb-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="59bcb-127">EntityType IS NULL</span></span>|<span data-ttu-id="59bcb-128">Возвращает значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="59bcb-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="59bcb-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="59bcb-129">ComplexType IS NULL</span></span>|<span data-ttu-id="59bcb-130">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="59bcb-130">Throws an error.</span></span>|  
|<span data-ttu-id="59bcb-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="59bcb-131">RowType IS NULL</span></span>|<span data-ttu-id="59bcb-132">Вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="59bcb-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="59bcb-133">Пример</span><span class="sxs-lookup"><span data-stu-id="59bcb-133">Example</span></span>  
 <span data-ttu-id="59bcb-134">Следующий запрос [!INCLUDE[esql](../../../../../../includes/esql-md.md)] использует оператор IS NOT NULL, чтобы определить, имеет ли выражение запроса значение, не равное NULL.</span><span class="sxs-lookup"><span data-stu-id="59bcb-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="59bcb-135">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="59bcb-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="59bcb-136">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="59bcb-136">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="59bcb-137">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="59bcb-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="59bcb-138">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="59bcb-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="59bcb-139">См. также</span><span class="sxs-lookup"><span data-stu-id="59bcb-139">See also</span></span>

- [<span data-ttu-id="59bcb-140">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="59bcb-140">Entity SQL Reference</span></span>](entity-sql-reference.md)
