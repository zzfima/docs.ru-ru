---
title: Краткий справочник по Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: b4e3eaf8abd82b63fa2663b47f878ecfa9584897
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207075"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="247d6-102">Краткий справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="247d6-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="247d6-103">В этом разделе содержится краткий справочник по запросам [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="247d6-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="247d6-104">Запросы в этом разделе основаны на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="247d6-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="247d6-105">Литералы</span><span class="sxs-lookup"><span data-stu-id="247d6-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="247d6-106">String</span><span class="sxs-lookup"><span data-stu-id="247d6-106">String</span></span>  
 <span data-ttu-id="247d6-107">Существуют строковые литералы в Юникоде и не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="247d6-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="247d6-108">Строки в Юникоде предваряются символом N. Например `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="247d6-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="247d6-109">Ниже приведен пример строкового литерала не в Юникоде:</span><span class="sxs-lookup"><span data-stu-id="247d6-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="247d6-110">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-110">Output:</span></span>  
  
|<span data-ttu-id="247d6-111">Значение</span><span class="sxs-lookup"><span data-stu-id="247d6-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="247d6-112">hello</span><span class="sxs-lookup"><span data-stu-id="247d6-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="247d6-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="247d6-113">DateTime</span></span>  
 <span data-ttu-id="247d6-114">В литералах DateTime обязательными являются и часть даты, и часть времени.</span><span class="sxs-lookup"><span data-stu-id="247d6-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="247d6-115">Значения по умолчанию отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="247d6-115">There are no default values.</span></span>  
  
 <span data-ttu-id="247d6-116">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="247d6-117">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-117">Output:</span></span>  
  
|<span data-ttu-id="247d6-118">Значение</span><span class="sxs-lookup"><span data-stu-id="247d6-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="247d6-119">Понедельник, 25.12.06, 01:01:00</span><span class="sxs-lookup"><span data-stu-id="247d6-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="247d6-120">Целое число</span><span class="sxs-lookup"><span data-stu-id="247d6-120">Integer</span></span>  
 <span data-ttu-id="247d6-121">Целочисленные литералы могут иметь тип Int32 (123), UInt32 (123U), Int64 (123L) и UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="247d6-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="247d6-122">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="247d6-123">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-123">Output:</span></span>  
  
|<span data-ttu-id="247d6-124">Значение</span><span class="sxs-lookup"><span data-stu-id="247d6-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="247d6-125">1</span><span class="sxs-lookup"><span data-stu-id="247d6-125">1</span></span>|  
|<span data-ttu-id="247d6-126">2</span><span class="sxs-lookup"><span data-stu-id="247d6-126">2</span></span>|  
|<span data-ttu-id="247d6-127">3</span><span class="sxs-lookup"><span data-stu-id="247d6-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="247d6-128">Другое</span><span class="sxs-lookup"><span data-stu-id="247d6-128">Other</span></span>  
 <span data-ttu-id="247d6-129">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает и другие типы литералов - Guid, Binary, Float/Double, Decimal и `null`.</span><span class="sxs-lookup"><span data-stu-id="247d6-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="247d6-130">Литералы NULL в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] считаются совместимыми с любым из других типов в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="247d6-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="247d6-131">Конструкторы типов</span><span class="sxs-lookup"><span data-stu-id="247d6-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="247d6-132">ROW</span><span class="sxs-lookup"><span data-stu-id="247d6-132">ROW</span></span>  
 <span data-ttu-id="247d6-133">[СТРОКИ](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) создает анонимные структурно типизированные (значение запись), как в:</span><span class="sxs-lookup"><span data-stu-id="247d6-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in:</span></span> `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 <span data-ttu-id="247d6-134">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="247d6-135">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-135">Output:</span></span>  
  
|<span data-ttu-id="247d6-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="247d6-136">ProductID</span></span>|<span data-ttu-id="247d6-137">name</span><span class="sxs-lookup"><span data-stu-id="247d6-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="247d6-138">1</span><span class="sxs-lookup"><span data-stu-id="247d6-138">1</span></span>|<span data-ttu-id="247d6-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="247d6-139">Adjustable Race</span></span>|  
|<span data-ttu-id="247d6-140">879</span><span class="sxs-lookup"><span data-stu-id="247d6-140">879</span></span>|<span data-ttu-id="247d6-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="247d6-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="247d6-142">712</span><span class="sxs-lookup"><span data-stu-id="247d6-142">712</span></span>|<span data-ttu-id="247d6-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="247d6-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="247d6-144">...</span><span class="sxs-lookup"><span data-stu-id="247d6-144">...</span></span>|<span data-ttu-id="247d6-145">...</span><span class="sxs-lookup"><span data-stu-id="247d6-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="247d6-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="247d6-146">MULTISET</span></span>  
 <span data-ttu-id="247d6-147">[МУЛЬТИНАБОР](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) создает коллекции, такие как:</span><span class="sxs-lookup"><span data-stu-id="247d6-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 <span data-ttu-id="247d6-148">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-148">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="247d6-149">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-149">Output:</span></span>  
  
|<span data-ttu-id="247d6-150">ProductID</span><span class="sxs-lookup"><span data-stu-id="247d6-150">ProductID</span></span>|<span data-ttu-id="247d6-151">name</span><span class="sxs-lookup"><span data-stu-id="247d6-151">Name</span></span>|<span data-ttu-id="247d6-152">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="247d6-152">ProductNumber</span></span>|<span data-ttu-id="247d6-153">…</span><span class="sxs-lookup"><span data-stu-id="247d6-153">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="247d6-154">842</span><span class="sxs-lookup"><span data-stu-id="247d6-154">842</span></span>|<span data-ttu-id="247d6-155">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="247d6-155">Touring-Panniers, Large</span></span>|<span data-ttu-id="247d6-156">PA-T100</span><span class="sxs-lookup"><span data-stu-id="247d6-156">PA-T100</span></span>|<span data-ttu-id="247d6-157">…</span><span class="sxs-lookup"><span data-stu-id="247d6-157">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="247d6-158">Object</span><span class="sxs-lookup"><span data-stu-id="247d6-158">Object</span></span>  
 <span data-ttu-id="247d6-159">[С именем конструктор типа](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) конструкции (именованные) объекты, определяемые пользователем, такие как `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="247d6-159">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="247d6-160">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-160">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="247d6-161">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-161">Output:</span></span>  
  
|<span data-ttu-id="247d6-162">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="247d6-162">SalesOrderDetailID</span></span>|<span data-ttu-id="247d6-163">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="247d6-163">CarrierTrackingNumber</span></span>|<span data-ttu-id="247d6-164">OrderQty</span><span class="sxs-lookup"><span data-stu-id="247d6-164">OrderQty</span></span>|<span data-ttu-id="247d6-165">ProductID</span><span class="sxs-lookup"><span data-stu-id="247d6-165">ProductID</span></span>|<span data-ttu-id="247d6-166">...</span><span class="sxs-lookup"><span data-stu-id="247d6-166">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="247d6-167">1</span><span class="sxs-lookup"><span data-stu-id="247d6-167">1</span></span>|<span data-ttu-id="247d6-168">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="247d6-168">4911-403C-98</span></span>|<span data-ttu-id="247d6-169">1</span><span class="sxs-lookup"><span data-stu-id="247d6-169">1</span></span>|<span data-ttu-id="247d6-170">776</span><span class="sxs-lookup"><span data-stu-id="247d6-170">776</span></span>|<span data-ttu-id="247d6-171">...</span><span class="sxs-lookup"><span data-stu-id="247d6-171">...</span></span>|  
|<span data-ttu-id="247d6-172">2</span><span class="sxs-lookup"><span data-stu-id="247d6-172">2</span></span>|<span data-ttu-id="247d6-173">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="247d6-173">4911-403C-98</span></span>|<span data-ttu-id="247d6-174">3</span><span class="sxs-lookup"><span data-stu-id="247d6-174">3</span></span>|<span data-ttu-id="247d6-175">777</span><span class="sxs-lookup"><span data-stu-id="247d6-175">777</span></span>|<span data-ttu-id="247d6-176">...</span><span class="sxs-lookup"><span data-stu-id="247d6-176">...</span></span>|  
|<span data-ttu-id="247d6-177">...</span><span class="sxs-lookup"><span data-stu-id="247d6-177">...</span></span>|<span data-ttu-id="247d6-178">...</span><span class="sxs-lookup"><span data-stu-id="247d6-178">...</span></span>|<span data-ttu-id="247d6-179">...</span><span class="sxs-lookup"><span data-stu-id="247d6-179">...</span></span>|<span data-ttu-id="247d6-180">...</span><span class="sxs-lookup"><span data-stu-id="247d6-180">...</span></span>|<span data-ttu-id="247d6-181">...</span><span class="sxs-lookup"><span data-stu-id="247d6-181">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="247d6-182">Ссылки</span><span class="sxs-lookup"><span data-stu-id="247d6-182">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="247d6-183">REF</span><span class="sxs-lookup"><span data-stu-id="247d6-183">REF</span></span>  
 <span data-ttu-id="247d6-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) создает ссылку на экземпляр типа сущности.</span><span class="sxs-lookup"><span data-stu-id="247d6-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="247d6-185">Например, следующий запрос возвращает ссылки на каждую сущность Order в наборе сущностей Orders:</span><span class="sxs-lookup"><span data-stu-id="247d6-185">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="247d6-186">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-186">Output:</span></span>  
  
|<span data-ttu-id="247d6-187">Значение</span><span class="sxs-lookup"><span data-stu-id="247d6-187">Value</span></span>|  
|-----------|  
|<span data-ttu-id="247d6-188">1</span><span class="sxs-lookup"><span data-stu-id="247d6-188">1</span></span>|  
|<span data-ttu-id="247d6-189">2</span><span class="sxs-lookup"><span data-stu-id="247d6-189">2</span></span>|  
|<span data-ttu-id="247d6-190">3</span><span class="sxs-lookup"><span data-stu-id="247d6-190">3</span></span>|  
|<span data-ttu-id="247d6-191">...</span><span class="sxs-lookup"><span data-stu-id="247d6-191">...</span></span>|  
  
 <span data-ttu-id="247d6-192">В следующем примере оператор извлечения свойства (.) используется для доступа к свойству сущности.</span><span class="sxs-lookup"><span data-stu-id="247d6-192">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="247d6-193">При использовании этого оператора автоматически выполняется разыменование ссылки.</span><span class="sxs-lookup"><span data-stu-id="247d6-193">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="247d6-194">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-194">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="247d6-195">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-195">Output:</span></span>  
  
|<span data-ttu-id="247d6-196">Значение</span><span class="sxs-lookup"><span data-stu-id="247d6-196">Value</span></span>|  
|-----------|  
|<span data-ttu-id="247d6-197">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="247d6-197">Adjustable Race</span></span>|  
|<span data-ttu-id="247d6-198">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="247d6-198">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="247d6-199">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="247d6-199">AWC Logo Cap</span></span>|  
|<span data-ttu-id="247d6-200">...</span><span class="sxs-lookup"><span data-stu-id="247d6-200">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="247d6-201">DEREF</span><span class="sxs-lookup"><span data-stu-id="247d6-201">DEREF</span></span>  
 <span data-ttu-id="247d6-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) разыменовывает значение ссылки и выдает результат разыменования.</span><span class="sxs-lookup"><span data-stu-id="247d6-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="247d6-203">Например, следующий запрос возвращает сущности Order для каждой из записей Order в наборе сущностей Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="247d6-203">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="247d6-204">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-204">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="247d6-205">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-205">Output:</span></span>  
  
|<span data-ttu-id="247d6-206">Значение</span><span class="sxs-lookup"><span data-stu-id="247d6-206">Value</span></span>|  
|-----------|  
|<span data-ttu-id="247d6-207">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="247d6-207">Adjustable Race</span></span>|  
|<span data-ttu-id="247d6-208">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="247d6-208">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="247d6-209">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="247d6-209">AWC Logo Cap</span></span>|  
|<span data-ttu-id="247d6-210">...</span><span class="sxs-lookup"><span data-stu-id="247d6-210">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="247d6-211">CREATEREF и KEY</span><span class="sxs-lookup"><span data-stu-id="247d6-211">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="247d6-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) создает ссылку, передавая ключ.</span><span class="sxs-lookup"><span data-stu-id="247d6-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="247d6-213">[КЛЮЧ](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) извлекает ключевую часть выражения со ссылкой на тип.</span><span class="sxs-lookup"><span data-stu-id="247d6-213">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="247d6-214">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-214">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="247d6-215">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-215">Output:</span></span>  
  
|<span data-ttu-id="247d6-216">ProductID</span><span class="sxs-lookup"><span data-stu-id="247d6-216">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="247d6-217">980</span><span class="sxs-lookup"><span data-stu-id="247d6-217">980</span></span>|  
|<span data-ttu-id="247d6-218">365</span><span class="sxs-lookup"><span data-stu-id="247d6-218">365</span></span>|  
|<span data-ttu-id="247d6-219">771</span><span class="sxs-lookup"><span data-stu-id="247d6-219">771</span></span>|  
|<span data-ttu-id="247d6-220">...</span><span class="sxs-lookup"><span data-stu-id="247d6-220">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="247d6-221">Функции</span><span class="sxs-lookup"><span data-stu-id="247d6-221">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="247d6-222">Канонические</span><span class="sxs-lookup"><span data-stu-id="247d6-222">Canonical</span></span>  
 <span data-ttu-id="247d6-223">Пространство имен для [канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) является модель Edm, как показано на `Edm.Length("string")`.</span><span class="sxs-lookup"><span data-stu-id="247d6-223">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="247d6-224">Если не импортировано другое пространство имен, содержащее функцию, имя которой совпадает с именем канонической функции, то указывать пространство имен не обязательно.</span><span class="sxs-lookup"><span data-stu-id="247d6-224">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="247d6-225">Если в двух пространствах имен имеется функция с тем же именем, то пользователь должен указать полное имя функции.</span><span class="sxs-lookup"><span data-stu-id="247d6-225">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="247d6-226">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-226">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="247d6-227">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-227">Output:</span></span>  
  
|<span data-ttu-id="247d6-228">NameLen</span><span class="sxs-lookup"><span data-stu-id="247d6-228">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="247d6-229">6</span><span class="sxs-lookup"><span data-stu-id="247d6-229">6</span></span>|  
|<span data-ttu-id="247d6-230">6</span><span class="sxs-lookup"><span data-stu-id="247d6-230">6</span></span>|  
|<span data-ttu-id="247d6-231">5</span><span class="sxs-lookup"><span data-stu-id="247d6-231">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="247d6-232">Функции поставщиков данных (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="247d6-232">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="247d6-233">[Функции поставщика Microsoft](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) в `SqlServer` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="247d6-233">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="247d6-234">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-234">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="247d6-235">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-235">Output:</span></span>  
  
|<span data-ttu-id="247d6-236">EmailLen</span><span class="sxs-lookup"><span data-stu-id="247d6-236">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="247d6-237">27</span><span class="sxs-lookup"><span data-stu-id="247d6-237">27</span></span>|  
|<span data-ttu-id="247d6-238">27</span><span class="sxs-lookup"><span data-stu-id="247d6-238">27</span></span>|  
|<span data-ttu-id="247d6-239">26</span><span class="sxs-lookup"><span data-stu-id="247d6-239">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="247d6-240">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="247d6-240">Namespaces</span></span>  
 <span data-ttu-id="247d6-241">[С помощью](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) задает пространства имен, используемые в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="247d6-241">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="247d6-242">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-242">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="247d6-243">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-243">Output:</span></span>  
  
|<span data-ttu-id="247d6-244">Значение</span><span class="sxs-lookup"><span data-stu-id="247d6-244">Value</span></span>|  
|-----------|  
|<span data-ttu-id="247d6-245">aa</span><span class="sxs-lookup"><span data-stu-id="247d6-245">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="247d6-246">Разбивка на страницы</span><span class="sxs-lookup"><span data-stu-id="247d6-246">Paging</span></span>  
 <span data-ttu-id="247d6-247">Разбиение на страницы можно выразить, задав объявления [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) и [ограничение](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) вложенными предложениями для [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) предложение.</span><span class="sxs-lookup"><span data-stu-id="247d6-247">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="247d6-248">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-248">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="247d6-249">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-249">Output:</span></span>  
  
|<span data-ttu-id="247d6-250">ID</span><span class="sxs-lookup"><span data-stu-id="247d6-250">ID</span></span>|<span data-ttu-id="247d6-251">name</span><span class="sxs-lookup"><span data-stu-id="247d6-251">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="247d6-252">10</span><span class="sxs-lookup"><span data-stu-id="247d6-252">10</span></span>|<span data-ttu-id="247d6-253">Adina</span><span class="sxs-lookup"><span data-stu-id="247d6-253">Adina</span></span>|  
|<span data-ttu-id="247d6-254">11</span><span class="sxs-lookup"><span data-stu-id="247d6-254">11</span></span>|<span data-ttu-id="247d6-255">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="247d6-255">Agcaoili</span></span>|  
|<span data-ttu-id="247d6-256">12</span><span class="sxs-lookup"><span data-stu-id="247d6-256">12</span></span>|<span data-ttu-id="247d6-257">Aguilar</span><span class="sxs-lookup"><span data-stu-id="247d6-257">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="247d6-258">Группирование</span><span class="sxs-lookup"><span data-stu-id="247d6-258">Grouping</span></span>  
 <span data-ttu-id="247d6-259">[ГРУППИРОВАНИЕ по](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) определяет группы, в объекты, возвращаемые запросом ([ВЫБЕРИТЕ](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) выражения должны быть помещены.</span><span class="sxs-lookup"><span data-stu-id="247d6-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="247d6-260">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-260">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="247d6-261">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-261">Output:</span></span>  
  
|<span data-ttu-id="247d6-262">имя</span><span class="sxs-lookup"><span data-stu-id="247d6-262">name</span></span>|  
|----------|  
|<span data-ttu-id="247d6-263">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="247d6-263">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="247d6-264">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="247d6-264">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="247d6-265">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="247d6-265">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="247d6-266">...</span><span class="sxs-lookup"><span data-stu-id="247d6-266">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="247d6-267">Навигация</span><span class="sxs-lookup"><span data-stu-id="247d6-267">Navigation</span></span>  
 <span data-ttu-id="247d6-268">Оператор навигации по связям позволяет переходить по связям от одной сущности (исходный элемент) к другой (конечный элемент).</span><span class="sxs-lookup"><span data-stu-id="247d6-268">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="247d6-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) принимает тип связи, заданный как \<пространства имен >.\< имя_типа_связи >.</span><span class="sxs-lookup"><span data-stu-id="247d6-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="247d6-270">Перейдите возвращает значение Ref\<T > Если количество элементов равно 1.</span><span class="sxs-lookup"><span data-stu-id="247d6-270">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="247d6-271">Если количество элементов равно n, коллекции < Ref\<T >> будут возвращены.</span><span class="sxs-lookup"><span data-stu-id="247d6-271">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="247d6-272">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-272">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="247d6-273">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-273">Output:</span></span>  
  
|<span data-ttu-id="247d6-274">AddressID</span><span class="sxs-lookup"><span data-stu-id="247d6-274">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="247d6-275">1</span><span class="sxs-lookup"><span data-stu-id="247d6-275">1</span></span>|  
|<span data-ttu-id="247d6-276">2</span><span class="sxs-lookup"><span data-stu-id="247d6-276">2</span></span>|  
|<span data-ttu-id="247d6-277">3</span><span class="sxs-lookup"><span data-stu-id="247d6-277">3</span></span>|  
|<span data-ttu-id="247d6-278">...</span><span class="sxs-lookup"><span data-stu-id="247d6-278">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="247d6-279">SELECT VALUE и SELECT</span><span class="sxs-lookup"><span data-stu-id="247d6-279">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="247d6-280">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="247d6-280">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="247d6-281">предоставляет в предложении SELECT VALUE, чтобы пропустить неявное построение строки.</span><span class="sxs-lookup"><span data-stu-id="247d6-281">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="247d6-282">В предложении SELECT VALUE может быть указан только один элемент.</span><span class="sxs-lookup"><span data-stu-id="247d6-282">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="247d6-283">При использовании такого предложения для элементов, в предложении SELECT оболочка строк не создается и коллекцию необходимой формы могут быть созданы, например: `SELECT VALUE a`.</span><span class="sxs-lookup"><span data-stu-id="247d6-283">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="247d6-284">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-284">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="247d6-285">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-285">Output:</span></span>  
  
|<span data-ttu-id="247d6-286">name</span><span class="sxs-lookup"><span data-stu-id="247d6-286">Name</span></span>|  
|----------|  
|<span data-ttu-id="247d6-287">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="247d6-287">Adjustable Race</span></span>|  
|<span data-ttu-id="247d6-288">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="247d6-288">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="247d6-289">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="247d6-289">AWC Logo Cap</span></span>|  
|<span data-ttu-id="247d6-290">...</span><span class="sxs-lookup"><span data-stu-id="247d6-290">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="247d6-291">SELECT</span><span class="sxs-lookup"><span data-stu-id="247d6-291">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="247d6-292">также предоставляет конструктор строк для построения произвольных строк.</span><span class="sxs-lookup"><span data-stu-id="247d6-292">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="247d6-293">Предложение SELECT принимает один или несколько элементов в проекции и возвращает запись данных с полями, например: `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="247d6-293">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="247d6-294">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-294">Example:</span></span>  
  
 <span data-ttu-id="247d6-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="247d6-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="247d6-296">name</span><span class="sxs-lookup"><span data-stu-id="247d6-296">Name</span></span>|<span data-ttu-id="247d6-297">ProductID</span><span class="sxs-lookup"><span data-stu-id="247d6-297">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="247d6-298">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="247d6-298">Adjustable Race</span></span>|<span data-ttu-id="247d6-299">1</span><span class="sxs-lookup"><span data-stu-id="247d6-299">1</span></span>|  
|<span data-ttu-id="247d6-300">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="247d6-300">All-Purpose Bike Stand</span></span>|<span data-ttu-id="247d6-301">879</span><span class="sxs-lookup"><span data-stu-id="247d6-301">879</span></span>|  
|<span data-ttu-id="247d6-302">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="247d6-302">AWC Logo Cap</span></span>|<span data-ttu-id="247d6-303">712</span><span class="sxs-lookup"><span data-stu-id="247d6-303">712</span></span>|  
|<span data-ttu-id="247d6-304">...</span><span class="sxs-lookup"><span data-stu-id="247d6-304">...</span></span>|<span data-ttu-id="247d6-305">...</span><span class="sxs-lookup"><span data-stu-id="247d6-305">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="247d6-306">Выражение варианта выбора</span><span class="sxs-lookup"><span data-stu-id="247d6-306">CASE EXPRESSION</span></span>  
 <span data-ttu-id="247d6-307">[Выражение case](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) вычисляет набор логических выражений для определения результата.</span><span class="sxs-lookup"><span data-stu-id="247d6-307">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="247d6-308">Пример</span><span class="sxs-lookup"><span data-stu-id="247d6-308">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="247d6-309">Результат</span><span class="sxs-lookup"><span data-stu-id="247d6-309">Output:</span></span>  
  
|<span data-ttu-id="247d6-310">Значение</span><span class="sxs-lookup"><span data-stu-id="247d6-310">Value</span></span>|  
|-----------|  
|<span data-ttu-id="247d6-311">true</span><span class="sxs-lookup"><span data-stu-id="247d6-311">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="247d6-312">См. также</span><span class="sxs-lookup"><span data-stu-id="247d6-312">See also</span></span>

- [<span data-ttu-id="247d6-313">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="247d6-313">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="247d6-314">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="247d6-314">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
