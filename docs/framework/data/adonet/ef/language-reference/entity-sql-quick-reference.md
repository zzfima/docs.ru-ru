---
title: Краткий справочник по Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: 9ccfc461d394af8804c960ebf460e7fbfb025b64
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833878"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="84e9d-102">Краткий справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="84e9d-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="84e9d-103">В этом разделе содержится краткий справочник по запросам [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84e9d-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="84e9d-104">Запросы в этом разделе основаны на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="84e9d-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="84e9d-105">Литералы</span><span class="sxs-lookup"><span data-stu-id="84e9d-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="84e9d-106">Строка</span><span class="sxs-lookup"><span data-stu-id="84e9d-106">String</span></span>  
 <span data-ttu-id="84e9d-107">Существуют строковые литералы в Юникоде и не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="84e9d-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="84e9d-108">Строки в Юникоде добавляются в начало с префиксом N. Например, `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="84e9d-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="84e9d-109">Ниже приведен пример строкового литерала не в Юникоде:</span><span class="sxs-lookup"><span data-stu-id="84e9d-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="84e9d-110">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-110">Output:</span></span>  
  
|<span data-ttu-id="84e9d-111">Значение</span><span class="sxs-lookup"><span data-stu-id="84e9d-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="84e9d-112">hello</span><span class="sxs-lookup"><span data-stu-id="84e9d-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="84e9d-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="84e9d-113">DateTime</span></span>  
 <span data-ttu-id="84e9d-114">В литералах DateTime обязательными являются и часть даты, и часть времени.</span><span class="sxs-lookup"><span data-stu-id="84e9d-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="84e9d-115">Значения по умолчанию отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="84e9d-115">There are no default values.</span></span>  
  
 <span data-ttu-id="84e9d-116">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="84e9d-117">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-117">Output:</span></span>  
  
|<span data-ttu-id="84e9d-118">Значение</span><span class="sxs-lookup"><span data-stu-id="84e9d-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="84e9d-119">Понедельник, 25.12.06, 01:01:00</span><span class="sxs-lookup"><span data-stu-id="84e9d-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="84e9d-120">Целое число</span><span class="sxs-lookup"><span data-stu-id="84e9d-120">Integer</span></span>  
 <span data-ttu-id="84e9d-121">Целочисленные литералы могут иметь тип Int32 (123), UInt32 (123U), Int64 (123L) и UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="84e9d-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="84e9d-122">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="84e9d-123">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-123">Output:</span></span>  
  
|<span data-ttu-id="84e9d-124">Значение</span><span class="sxs-lookup"><span data-stu-id="84e9d-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="84e9d-125">1</span><span class="sxs-lookup"><span data-stu-id="84e9d-125">1</span></span>|  
|<span data-ttu-id="84e9d-126">2</span><span class="sxs-lookup"><span data-stu-id="84e9d-126">2</span></span>|  
|<span data-ttu-id="84e9d-127">3</span><span class="sxs-lookup"><span data-stu-id="84e9d-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="84e9d-128">Прочее</span><span class="sxs-lookup"><span data-stu-id="84e9d-128">Other</span></span>  
 <span data-ttu-id="84e9d-129">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает и другие типы литералов - Guid, Binary, Float/Double, Decimal и `null`.</span><span class="sxs-lookup"><span data-stu-id="84e9d-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="84e9d-130">Литералы NULL в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] считаются совместимыми с любым из других типов в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="84e9d-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="84e9d-131">Конструкторы типов</span><span class="sxs-lookup"><span data-stu-id="84e9d-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="84e9d-132">ROW</span><span class="sxs-lookup"><span data-stu-id="84e9d-132">ROW</span></span>  
 <span data-ttu-id="84e9d-133">[Строка](row-entity-sql.md) конструирует анонимное, структурно типизированное значение (запись), как в: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="84e9d-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="84e9d-134">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="84e9d-135">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-135">Output:</span></span>  
  
|<span data-ttu-id="84e9d-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="84e9d-136">ProductID</span></span>|<span data-ttu-id="84e9d-137">Имя</span><span class="sxs-lookup"><span data-stu-id="84e9d-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="84e9d-138">1</span><span class="sxs-lookup"><span data-stu-id="84e9d-138">1</span></span>|<span data-ttu-id="84e9d-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="84e9d-139">Adjustable Race</span></span>|  
|<span data-ttu-id="84e9d-140">879</span><span class="sxs-lookup"><span data-stu-id="84e9d-140">879</span></span>|<span data-ttu-id="84e9d-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="84e9d-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="84e9d-142">712</span><span class="sxs-lookup"><span data-stu-id="84e9d-142">712</span></span>|<span data-ttu-id="84e9d-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="84e9d-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="84e9d-144">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-144">...</span></span>|<span data-ttu-id="84e9d-145">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="84e9d-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="84e9d-146">MULTISET</span></span>  
 <span data-ttu-id="84e9d-147">Коллекции [мультинаборов](multiset-entity-sql.md) , например:</span><span class="sxs-lookup"><span data-stu-id="84e9d-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="84e9d-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="84e9d-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="84e9d-149">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="84e9d-150">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-150">Output:</span></span>  
  
|<span data-ttu-id="84e9d-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="84e9d-151">ProductID</span></span>|<span data-ttu-id="84e9d-152">Имя</span><span class="sxs-lookup"><span data-stu-id="84e9d-152">Name</span></span>|<span data-ttu-id="84e9d-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="84e9d-153">ProductNumber</span></span>|<span data-ttu-id="84e9d-154">…</span><span class="sxs-lookup"><span data-stu-id="84e9d-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="84e9d-155">842</span><span class="sxs-lookup"><span data-stu-id="84e9d-155">842</span></span>|<span data-ttu-id="84e9d-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="84e9d-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="84e9d-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="84e9d-157">PA-T100</span></span>|<span data-ttu-id="84e9d-158">…</span><span class="sxs-lookup"><span data-stu-id="84e9d-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="84e9d-159">Object</span><span class="sxs-lookup"><span data-stu-id="84e9d-159">Object</span></span>  
 <span data-ttu-id="84e9d-160">[Конструктор именованного типа](named-type-constructor-entity-sql.md) конструирует (именованные) определяемые пользователем объекты, такие как `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="84e9d-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="84e9d-161">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="84e9d-162">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-162">Output:</span></span>  
  
|<span data-ttu-id="84e9d-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="84e9d-163">SalesOrderDetailID</span></span>|<span data-ttu-id="84e9d-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="84e9d-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="84e9d-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="84e9d-165">OrderQty</span></span>|<span data-ttu-id="84e9d-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="84e9d-166">ProductID</span></span>|<span data-ttu-id="84e9d-167">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="84e9d-168">1</span><span class="sxs-lookup"><span data-stu-id="84e9d-168">1</span></span>|<span data-ttu-id="84e9d-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="84e9d-169">4911-403C-98</span></span>|<span data-ttu-id="84e9d-170">1</span><span class="sxs-lookup"><span data-stu-id="84e9d-170">1</span></span>|<span data-ttu-id="84e9d-171">776</span><span class="sxs-lookup"><span data-stu-id="84e9d-171">776</span></span>|<span data-ttu-id="84e9d-172">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-172">...</span></span>|  
|<span data-ttu-id="84e9d-173">2</span><span class="sxs-lookup"><span data-stu-id="84e9d-173">2</span></span>|<span data-ttu-id="84e9d-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="84e9d-174">4911-403C-98</span></span>|<span data-ttu-id="84e9d-175">3</span><span class="sxs-lookup"><span data-stu-id="84e9d-175">3</span></span>|<span data-ttu-id="84e9d-176">777</span><span class="sxs-lookup"><span data-stu-id="84e9d-176">777</span></span>|<span data-ttu-id="84e9d-177">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-177">...</span></span>|  
|<span data-ttu-id="84e9d-178">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-178">...</span></span>|<span data-ttu-id="84e9d-179">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-179">...</span></span>|<span data-ttu-id="84e9d-180">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-180">...</span></span>|<span data-ttu-id="84e9d-181">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-181">...</span></span>|<span data-ttu-id="84e9d-182">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="84e9d-183">Ссылки</span><span class="sxs-lookup"><span data-stu-id="84e9d-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="84e9d-184">REF</span><span class="sxs-lookup"><span data-stu-id="84e9d-184">REF</span></span>  
 <span data-ttu-id="84e9d-185">[Ref](ref-entity-sql.md) создает ссылку на экземпляр типа сущности.</span><span class="sxs-lookup"><span data-stu-id="84e9d-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="84e9d-186">Например, следующий запрос возвращает ссылки на каждую сущность Order в наборе сущностей Orders:</span><span class="sxs-lookup"><span data-stu-id="84e9d-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="84e9d-187">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-187">Output:</span></span>  
  
|<span data-ttu-id="84e9d-188">Значение</span><span class="sxs-lookup"><span data-stu-id="84e9d-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="84e9d-189">1</span><span class="sxs-lookup"><span data-stu-id="84e9d-189">1</span></span>|  
|<span data-ttu-id="84e9d-190">2</span><span class="sxs-lookup"><span data-stu-id="84e9d-190">2</span></span>|  
|<span data-ttu-id="84e9d-191">3</span><span class="sxs-lookup"><span data-stu-id="84e9d-191">3</span></span>|  
|<span data-ttu-id="84e9d-192">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-192">...</span></span>|  
  
 <span data-ttu-id="84e9d-193">В следующем примере оператор извлечения свойства (.) используется для доступа к свойству сущности.</span><span class="sxs-lookup"><span data-stu-id="84e9d-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="84e9d-194">При использовании этого оператора автоматически выполняется разыменование ссылки.</span><span class="sxs-lookup"><span data-stu-id="84e9d-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="84e9d-195">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="84e9d-196">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-196">Output:</span></span>  
  
|<span data-ttu-id="84e9d-197">Значение</span><span class="sxs-lookup"><span data-stu-id="84e9d-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="84e9d-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="84e9d-198">Adjustable Race</span></span>|  
|<span data-ttu-id="84e9d-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="84e9d-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="84e9d-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="84e9d-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="84e9d-201">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="84e9d-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="84e9d-202">DEREF</span></span>  
 <span data-ttu-id="84e9d-203">[DEREF](deref-entity-sql.md) разыменование ссылочного значения и выдает результат разыменования.</span><span class="sxs-lookup"><span data-stu-id="84e9d-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="84e9d-204">Например, следующий запрос возвращает сущности Order для каждой из записей Order в наборе сущностей Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="84e9d-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="84e9d-205">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="84e9d-206">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-206">Output:</span></span>  
  
|<span data-ttu-id="84e9d-207">Значение</span><span class="sxs-lookup"><span data-stu-id="84e9d-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="84e9d-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="84e9d-208">Adjustable Race</span></span>|  
|<span data-ttu-id="84e9d-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="84e9d-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="84e9d-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="84e9d-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="84e9d-211">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="84e9d-212">CREATEREF и KEY</span><span class="sxs-lookup"><span data-stu-id="84e9d-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="84e9d-213">[CREATEREF](createref-entity-sql.md) создает ссылку, передавая ключ.</span><span class="sxs-lookup"><span data-stu-id="84e9d-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="84e9d-214">[Key](key-entity-sql.md) извлекает ключевую часть выражения со ссылкой на тип.</span><span class="sxs-lookup"><span data-stu-id="84e9d-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="84e9d-215">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="84e9d-216">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-216">Output:</span></span>  
  
|<span data-ttu-id="84e9d-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="84e9d-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="84e9d-218">980</span><span class="sxs-lookup"><span data-stu-id="84e9d-218">980</span></span>|  
|<span data-ttu-id="84e9d-219">365</span><span class="sxs-lookup"><span data-stu-id="84e9d-219">365</span></span>|  
|<span data-ttu-id="84e9d-220">771</span><span class="sxs-lookup"><span data-stu-id="84e9d-220">771</span></span>|  
|<span data-ttu-id="84e9d-221">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="84e9d-222">Функции</span><span class="sxs-lookup"><span data-stu-id="84e9d-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="84e9d-223">Канонические</span><span class="sxs-lookup"><span data-stu-id="84e9d-223">Canonical</span></span>  
 <span data-ttu-id="84e9d-224">Пространство имен для [канонических функций](canonical-functions.md) — EDM, как в `Edm.Length("string")`.</span><span class="sxs-lookup"><span data-stu-id="84e9d-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="84e9d-225">Если не импортировано другое пространство имен, содержащее функцию, имя которой совпадает с именем канонической функции, то указывать пространство имен не обязательно.</span><span class="sxs-lookup"><span data-stu-id="84e9d-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="84e9d-226">Если в двух пространствах имен имеется функция с тем же именем, то пользователь должен указать полное имя функции.</span><span class="sxs-lookup"><span data-stu-id="84e9d-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="84e9d-227">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="84e9d-228">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-228">Output:</span></span>  
  
|<span data-ttu-id="84e9d-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="84e9d-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="84e9d-230">6</span><span class="sxs-lookup"><span data-stu-id="84e9d-230">6</span></span>|  
|<span data-ttu-id="84e9d-231">6</span><span class="sxs-lookup"><span data-stu-id="84e9d-231">6</span></span>|  
|<span data-ttu-id="84e9d-232">5</span><span class="sxs-lookup"><span data-stu-id="84e9d-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="84e9d-233">Функции поставщиков данных (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="84e9d-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="84e9d-234">[Функции, относящиеся к поставщику (Майкрософт)](../sqlclient-for-ef-functions.md) , находятся в пространстве имен `SqlServer`.</span><span class="sxs-lookup"><span data-stu-id="84e9d-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="84e9d-235">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="84e9d-236">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-236">Output:</span></span>  
  
|<span data-ttu-id="84e9d-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="84e9d-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="84e9d-238">27</span><span class="sxs-lookup"><span data-stu-id="84e9d-238">27</span></span>|  
|<span data-ttu-id="84e9d-239">27</span><span class="sxs-lookup"><span data-stu-id="84e9d-239">27</span></span>|  
|<span data-ttu-id="84e9d-240">26</span><span class="sxs-lookup"><span data-stu-id="84e9d-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="84e9d-241">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="84e9d-241">Namespaces</span></span>  
 <span data-ttu-id="84e9d-242">[Использование](using-entity-sql.md) задает пространства имен, используемые в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="84e9d-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="84e9d-243">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="84e9d-244">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-244">Output:</span></span>  
  
|<span data-ttu-id="84e9d-245">Значение</span><span class="sxs-lookup"><span data-stu-id="84e9d-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="84e9d-246">aa</span><span class="sxs-lookup"><span data-stu-id="84e9d-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="84e9d-247">Подкачка</span><span class="sxs-lookup"><span data-stu-id="84e9d-247">Paging</span></span>  
 <span data-ttu-id="84e9d-248">Разбиение на страницы может быть выражено путем объявления вложенных предложений [Skip](skip-entity-sql.md) и [Limit](limit-entity-sql.md) в предложении [ORDER BY](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="84e9d-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="84e9d-249">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="84e9d-250">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-250">Output:</span></span>  
  
|<span data-ttu-id="84e9d-251">ИДЕНТИФИКАТОР</span><span class="sxs-lookup"><span data-stu-id="84e9d-251">ID</span></span>|<span data-ttu-id="84e9d-252">Имя</span><span class="sxs-lookup"><span data-stu-id="84e9d-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="84e9d-253">10</span><span class="sxs-lookup"><span data-stu-id="84e9d-253">10</span></span>|<span data-ttu-id="84e9d-254">Adina</span><span class="sxs-lookup"><span data-stu-id="84e9d-254">Adina</span></span>|  
|<span data-ttu-id="84e9d-255">11</span><span class="sxs-lookup"><span data-stu-id="84e9d-255">11</span></span>|<span data-ttu-id="84e9d-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="84e9d-256">Agcaoili</span></span>|  
|<span data-ttu-id="84e9d-257">12</span><span class="sxs-lookup"><span data-stu-id="84e9d-257">12</span></span>|<span data-ttu-id="84e9d-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="84e9d-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="84e9d-259">Группирование</span><span class="sxs-lookup"><span data-stu-id="84e9d-259">Grouping</span></span>  
 <span data-ttu-id="84e9d-260">[Группирование по](group-by-entity-sql.md) задает группы, в которые должны быть помещены объекты, возвращаемые выражением запроса ([SELECT](select-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="84e9d-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="84e9d-261">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="84e9d-262">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-262">Output:</span></span>  
  
|<span data-ttu-id="84e9d-263">name</span><span class="sxs-lookup"><span data-stu-id="84e9d-263">name</span></span>|  
|----------|  
|<span data-ttu-id="84e9d-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="84e9d-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="84e9d-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="84e9d-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="84e9d-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="84e9d-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="84e9d-267">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="84e9d-268">Навигация</span><span class="sxs-lookup"><span data-stu-id="84e9d-268">Navigation</span></span>  
 <span data-ttu-id="84e9d-269">Оператор навигации по связям позволяет переходить по связям от одной сущности (исходный элемент) к другой (конечный элемент).</span><span class="sxs-lookup"><span data-stu-id="84e9d-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="84e9d-270">[Переход](navigate-entity-sql.md) принимает тип отношения, который определен как \<> пространства имен. > имя типа отношения\<.</span><span class="sxs-lookup"><span data-stu-id="84e9d-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="84e9d-271">Функция Navigate возвращает ref\<T > Если количество элементов с начала до конца равно 1.</span><span class="sxs-lookup"><span data-stu-id="84e9d-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="84e9d-272">Если число элементов в конец равно n, будет возвращена коллекция < ref\<T > >.</span><span class="sxs-lookup"><span data-stu-id="84e9d-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="84e9d-273">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="84e9d-274">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-274">Output:</span></span>  
  
|<span data-ttu-id="84e9d-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="84e9d-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="84e9d-276">1</span><span class="sxs-lookup"><span data-stu-id="84e9d-276">1</span></span>|  
|<span data-ttu-id="84e9d-277">2</span><span class="sxs-lookup"><span data-stu-id="84e9d-277">2</span></span>|  
|<span data-ttu-id="84e9d-278">3</span><span class="sxs-lookup"><span data-stu-id="84e9d-278">3</span></span>|  
|<span data-ttu-id="84e9d-279">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="84e9d-280">SELECT VALUE и SELECT</span><span class="sxs-lookup"><span data-stu-id="84e9d-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="84e9d-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="84e9d-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="84e9d-282">предоставляет предложение SELECT VALUE для пропуска неявной конструкции строки.</span><span class="sxs-lookup"><span data-stu-id="84e9d-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="84e9d-283">В предложении SELECT VALUE может быть указан только один элемент.</span><span class="sxs-lookup"><span data-stu-id="84e9d-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="84e9d-284">При использовании такого предложения оболочка строк не создается вокруг элементов в предложении SELECT и может быть создана коллекция требуемой формы, например: `SELECT VALUE a`.</span><span class="sxs-lookup"><span data-stu-id="84e9d-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="84e9d-285">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="84e9d-286">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-286">Output:</span></span>  
  
|<span data-ttu-id="84e9d-287">Имя</span><span class="sxs-lookup"><span data-stu-id="84e9d-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="84e9d-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="84e9d-288">Adjustable Race</span></span>|  
|<span data-ttu-id="84e9d-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="84e9d-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="84e9d-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="84e9d-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="84e9d-291">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="84e9d-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="84e9d-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="84e9d-293">также предоставляет конструктор строк для создания произвольных строк.</span><span class="sxs-lookup"><span data-stu-id="84e9d-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="84e9d-294">Предложение SELECT принимает один или несколько элементов в проекции и возвращает запись данных с полями, например: `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="84e9d-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="84e9d-295">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-295">Example:</span></span>  
  
 <span data-ttu-id="84e9d-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="84e9d-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="84e9d-297">Имя</span><span class="sxs-lookup"><span data-stu-id="84e9d-297">Name</span></span>|<span data-ttu-id="84e9d-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="84e9d-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="84e9d-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="84e9d-299">Adjustable Race</span></span>|<span data-ttu-id="84e9d-300">1</span><span class="sxs-lookup"><span data-stu-id="84e9d-300">1</span></span>|  
|<span data-ttu-id="84e9d-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="84e9d-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="84e9d-302">879</span><span class="sxs-lookup"><span data-stu-id="84e9d-302">879</span></span>|  
|<span data-ttu-id="84e9d-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="84e9d-303">AWC Logo Cap</span></span>|<span data-ttu-id="84e9d-304">712</span><span class="sxs-lookup"><span data-stu-id="84e9d-304">712</span></span>|  
|<span data-ttu-id="84e9d-305">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-305">...</span></span>|<span data-ttu-id="84e9d-306">...</span><span class="sxs-lookup"><span data-stu-id="84e9d-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="84e9d-307">Выражение варианта выбора</span><span class="sxs-lookup"><span data-stu-id="84e9d-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="84e9d-308">[Выражение CASE](case-entity-sql.md) вычисляет набор логических выражений для определения результата.</span><span class="sxs-lookup"><span data-stu-id="84e9d-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="84e9d-309">Пример.</span><span class="sxs-lookup"><span data-stu-id="84e9d-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="84e9d-310">Результат</span><span class="sxs-lookup"><span data-stu-id="84e9d-310">Output:</span></span>  
  
|<span data-ttu-id="84e9d-311">Значение</span><span class="sxs-lookup"><span data-stu-id="84e9d-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="84e9d-312">TRUE</span><span class="sxs-lookup"><span data-stu-id="84e9d-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84e9d-313">См. также:</span><span class="sxs-lookup"><span data-stu-id="84e9d-313">See also</span></span>

- [<span data-ttu-id="84e9d-314">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="84e9d-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="84e9d-315">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="84e9d-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
