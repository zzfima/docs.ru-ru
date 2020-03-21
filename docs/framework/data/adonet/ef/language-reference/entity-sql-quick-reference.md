---
title: Краткий справочник по Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: fc7cf8f8f692f9dc4230569d5f575b6d5fad19fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150354"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="c43c0-102">Краткий справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c43c0-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="c43c0-103">В этом разделе содержится краткий справочник по запросам [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c43c0-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="c43c0-104">Запросы, описанные в этом разделе, основаны на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="c43c0-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="c43c0-105">Литералы</span><span class="sxs-lookup"><span data-stu-id="c43c0-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="c43c0-106">Строка</span><span class="sxs-lookup"><span data-stu-id="c43c0-106">String</span></span>  
 <span data-ttu-id="c43c0-107">Существуют строковые литералы в Юникоде и не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="c43c0-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="c43c0-108">Строки Unicode готовятся с помощью N. Например, `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="c43c0-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="c43c0-109">Ниже приведен пример строкового литерала не в Юникоде:</span><span class="sxs-lookup"><span data-stu-id="c43c0-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="c43c0-110">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-110">Output:</span></span>  
  
|<span data-ttu-id="c43c0-111">Значение</span><span class="sxs-lookup"><span data-stu-id="c43c0-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c43c0-112">hello</span><span class="sxs-lookup"><span data-stu-id="c43c0-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="c43c0-113">Дата и время</span><span class="sxs-lookup"><span data-stu-id="c43c0-113">DateTime</span></span>  
 <span data-ttu-id="c43c0-114">В литералах DateTime обязательными являются и часть даты, и часть времени.</span><span class="sxs-lookup"><span data-stu-id="c43c0-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="c43c0-115">Значения по умолчанию отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="c43c0-115">There are no default values.</span></span>  
  
 <span data-ttu-id="c43c0-116">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="c43c0-117">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-117">Output:</span></span>  
  
|<span data-ttu-id="c43c0-118">Значение</span><span class="sxs-lookup"><span data-stu-id="c43c0-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c43c0-119">Понедельник, 25.12.06, 01:01:00</span><span class="sxs-lookup"><span data-stu-id="c43c0-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="c43c0-120">Целое число</span><span class="sxs-lookup"><span data-stu-id="c43c0-120">Integer</span></span>  
 <span data-ttu-id="c43c0-121">Целочисленные литералы могут иметь тип Int32 (123), UInt32 (123U), Int64 (123L) и UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="c43c0-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="c43c0-122">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="c43c0-123">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-123">Output:</span></span>  
  
|<span data-ttu-id="c43c0-124">Значение</span><span class="sxs-lookup"><span data-stu-id="c43c0-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c43c0-125">1</span><span class="sxs-lookup"><span data-stu-id="c43c0-125">1</span></span>|  
|<span data-ttu-id="c43c0-126">2</span><span class="sxs-lookup"><span data-stu-id="c43c0-126">2</span></span>|  
|<span data-ttu-id="c43c0-127">3</span><span class="sxs-lookup"><span data-stu-id="c43c0-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="c43c0-128">Другие</span><span class="sxs-lookup"><span data-stu-id="c43c0-128">Other</span></span>  
 <span data-ttu-id="c43c0-129">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает и другие типы литералов - Guid, Binary, Float/Double, Decimal и `null`.</span><span class="sxs-lookup"><span data-stu-id="c43c0-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="c43c0-130">Литералы NULL в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] считаются совместимыми с любым из других типов в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="c43c0-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="c43c0-131">Конструкторы типов</span><span class="sxs-lookup"><span data-stu-id="c43c0-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="c43c0-132">ROW</span><span class="sxs-lookup"><span data-stu-id="c43c0-132">ROW</span></span>  
 <span data-ttu-id="c43c0-133">[ROW](row-entity-sql.md) строит анонимное, структурно набраное (запись) значение, как в:`ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="c43c0-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="c43c0-134">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="c43c0-135">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-135">Output:</span></span>  
  
|<span data-ttu-id="c43c0-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="c43c0-136">ProductID</span></span>|<span data-ttu-id="c43c0-137">Имя</span><span class="sxs-lookup"><span data-stu-id="c43c0-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="c43c0-138">1</span><span class="sxs-lookup"><span data-stu-id="c43c0-138">1</span></span>|<span data-ttu-id="c43c0-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="c43c0-139">Adjustable Race</span></span>|  
|<span data-ttu-id="c43c0-140">879</span><span class="sxs-lookup"><span data-stu-id="c43c0-140">879</span></span>|<span data-ttu-id="c43c0-141">Универсальная подставка для велосипеда</span><span class="sxs-lookup"><span data-stu-id="c43c0-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="c43c0-142">712</span><span class="sxs-lookup"><span data-stu-id="c43c0-142">712</span></span>|<span data-ttu-id="c43c0-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="c43c0-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="c43c0-144">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-144">...</span></span>|<span data-ttu-id="c43c0-145">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="c43c0-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="c43c0-146">MULTISET</span></span>  
 <span data-ttu-id="c43c0-147">[MULTISET](multiset-entity-sql.md) конструирует коллекции, такие как:</span><span class="sxs-lookup"><span data-stu-id="c43c0-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="c43c0-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="c43c0-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="c43c0-149">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="c43c0-150">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-150">Output:</span></span>  
  
|<span data-ttu-id="c43c0-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="c43c0-151">ProductID</span></span>|<span data-ttu-id="c43c0-152">Имя</span><span class="sxs-lookup"><span data-stu-id="c43c0-152">Name</span></span>|<span data-ttu-id="c43c0-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="c43c0-153">ProductNumber</span></span>|<span data-ttu-id="c43c0-154">…</span><span class="sxs-lookup"><span data-stu-id="c43c0-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="c43c0-155">842</span><span class="sxs-lookup"><span data-stu-id="c43c0-155">842</span></span>|<span data-ttu-id="c43c0-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="c43c0-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="c43c0-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="c43c0-157">PA-T100</span></span>|<span data-ttu-id="c43c0-158">…</span><span class="sxs-lookup"><span data-stu-id="c43c0-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="c43c0-159">Объект</span><span class="sxs-lookup"><span data-stu-id="c43c0-159">Object</span></span>  
 <span data-ttu-id="c43c0-160">[Названный тип конструктора](named-type-constructor-entity-sql.md) строит (названные) пользовательские объекты, такие как `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="c43c0-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="c43c0-161">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 <span data-ttu-id="c43c0-162">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-162">Output:</span></span>  
  
|<span data-ttu-id="c43c0-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="c43c0-163">SalesOrderDetailID</span></span>|<span data-ttu-id="c43c0-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="c43c0-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="c43c0-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="c43c0-165">OrderQty</span></span>|<span data-ttu-id="c43c0-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="c43c0-166">ProductID</span></span>|<span data-ttu-id="c43c0-167">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="c43c0-168">1</span><span class="sxs-lookup"><span data-stu-id="c43c0-168">1</span></span>|<span data-ttu-id="c43c0-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="c43c0-169">4911-403C-98</span></span>|<span data-ttu-id="c43c0-170">1</span><span class="sxs-lookup"><span data-stu-id="c43c0-170">1</span></span>|<span data-ttu-id="c43c0-171">776</span><span class="sxs-lookup"><span data-stu-id="c43c0-171">776</span></span>|<span data-ttu-id="c43c0-172">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-172">...</span></span>|  
|<span data-ttu-id="c43c0-173">2</span><span class="sxs-lookup"><span data-stu-id="c43c0-173">2</span></span>|<span data-ttu-id="c43c0-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="c43c0-174">4911-403C-98</span></span>|<span data-ttu-id="c43c0-175">3</span><span class="sxs-lookup"><span data-stu-id="c43c0-175">3</span></span>|<span data-ttu-id="c43c0-176">777</span><span class="sxs-lookup"><span data-stu-id="c43c0-176">777</span></span>|<span data-ttu-id="c43c0-177">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-177">...</span></span>|  
|<span data-ttu-id="c43c0-178">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-178">...</span></span>|<span data-ttu-id="c43c0-179">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-179">...</span></span>|<span data-ttu-id="c43c0-180">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-180">...</span></span>|<span data-ttu-id="c43c0-181">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-181">...</span></span>|<span data-ttu-id="c43c0-182">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="c43c0-183">Ссылки</span><span class="sxs-lookup"><span data-stu-id="c43c0-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="c43c0-184">REF</span><span class="sxs-lookup"><span data-stu-id="c43c0-184">REF</span></span>  
 <span data-ttu-id="c43c0-185">[REF](ref-entity-sql.md) создает ссылку на экземпляр типа сущности.</span><span class="sxs-lookup"><span data-stu-id="c43c0-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="c43c0-186">Например, следующий запрос возвращает ссылки на каждую сущность Order в наборе сущностей Orders:</span><span class="sxs-lookup"><span data-stu-id="c43c0-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="c43c0-187">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-187">Output:</span></span>  
  
|<span data-ttu-id="c43c0-188">Значение</span><span class="sxs-lookup"><span data-stu-id="c43c0-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c43c0-189">1</span><span class="sxs-lookup"><span data-stu-id="c43c0-189">1</span></span>|  
|<span data-ttu-id="c43c0-190">2</span><span class="sxs-lookup"><span data-stu-id="c43c0-190">2</span></span>|  
|<span data-ttu-id="c43c0-191">3</span><span class="sxs-lookup"><span data-stu-id="c43c0-191">3</span></span>|  
|<span data-ttu-id="c43c0-192">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-192">...</span></span>|  
  
 <span data-ttu-id="c43c0-193">В следующем примере оператор извлечения свойства (.) используется для доступа к свойству сущности.</span><span class="sxs-lookup"><span data-stu-id="c43c0-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="c43c0-194">При использовании этого оператора автоматически выполняется разыменование ссылки.</span><span class="sxs-lookup"><span data-stu-id="c43c0-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="c43c0-195">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="c43c0-196">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-196">Output:</span></span>  
  
|<span data-ttu-id="c43c0-197">Значение</span><span class="sxs-lookup"><span data-stu-id="c43c0-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c43c0-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="c43c0-198">Adjustable Race</span></span>|  
|<span data-ttu-id="c43c0-199">Универсальная подставка для велосипеда</span><span class="sxs-lookup"><span data-stu-id="c43c0-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="c43c0-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="c43c0-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="c43c0-201">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="c43c0-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="c43c0-202">DEREF</span></span>  
 <span data-ttu-id="c43c0-203">[DEREF](deref-entity-sql.md) ссылается на эталонное значение и дает результат этого упоминания.</span><span class="sxs-lookup"><span data-stu-id="c43c0-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="c43c0-204">Например, следующий запрос возвращает сущности Order для каждой из записей Order в наборе сущностей Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="c43c0-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="c43c0-205">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="c43c0-206">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-206">Output:</span></span>  
  
|<span data-ttu-id="c43c0-207">Значение</span><span class="sxs-lookup"><span data-stu-id="c43c0-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c43c0-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="c43c0-208">Adjustable Race</span></span>|  
|<span data-ttu-id="c43c0-209">Универсальная подставка для велосипеда</span><span class="sxs-lookup"><span data-stu-id="c43c0-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="c43c0-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="c43c0-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="c43c0-211">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="c43c0-212">CREATEREF и KEY</span><span class="sxs-lookup"><span data-stu-id="c43c0-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="c43c0-213">[CREATEREF](createref-entity-sql.md) создает ссылку, передающая ключ.</span><span class="sxs-lookup"><span data-stu-id="c43c0-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="c43c0-214">[KEY](key-entity-sql.md) извлекает ключевую часть выражения с помощью ссылки типа.</span><span class="sxs-lookup"><span data-stu-id="c43c0-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="c43c0-215">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="c43c0-216">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-216">Output:</span></span>  
  
|<span data-ttu-id="c43c0-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="c43c0-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="c43c0-218">980</span><span class="sxs-lookup"><span data-stu-id="c43c0-218">980</span></span>|  
|<span data-ttu-id="c43c0-219">365</span><span class="sxs-lookup"><span data-stu-id="c43c0-219">365</span></span>|  
|<span data-ttu-id="c43c0-220">771</span><span class="sxs-lookup"><span data-stu-id="c43c0-220">771</span></span>|  
|<span data-ttu-id="c43c0-221">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="c43c0-222">Функции</span><span class="sxs-lookup"><span data-stu-id="c43c0-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="c43c0-223">Canonical</span><span class="sxs-lookup"><span data-stu-id="c43c0-223">Canonical</span></span>  
 <span data-ttu-id="c43c0-224">Пространство имен для [канонических функций](canonical-functions.md) Является `Edm.Length("string")`Edm, как и в .</span><span class="sxs-lookup"><span data-stu-id="c43c0-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="c43c0-225">Если не импортировано другое пространство имен, содержащее функцию, имя которой совпадает с именем канонической функции, то указывать пространство имен не обязательно.</span><span class="sxs-lookup"><span data-stu-id="c43c0-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="c43c0-226">Если в двух пространствах имен имеется функция с тем же именем, то пользователь должен указать полное имя функции.</span><span class="sxs-lookup"><span data-stu-id="c43c0-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="c43c0-227">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="c43c0-228">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-228">Output:</span></span>  
  
|<span data-ttu-id="c43c0-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="c43c0-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="c43c0-230">6</span><span class="sxs-lookup"><span data-stu-id="c43c0-230">6</span></span>|  
|<span data-ttu-id="c43c0-231">6</span><span class="sxs-lookup"><span data-stu-id="c43c0-231">6</span></span>|  
|<span data-ttu-id="c43c0-232">5</span><span class="sxs-lookup"><span data-stu-id="c43c0-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="c43c0-233">Функции поставщиков данных (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c43c0-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="c43c0-234">[Функции, связанные с поставщиком Майкрософт,](../sqlclient-for-ef-functions.md) находятся в пространстве `SqlServer` имен.</span><span class="sxs-lookup"><span data-stu-id="c43c0-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="c43c0-235">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="c43c0-236">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-236">Output:</span></span>  
  
|<span data-ttu-id="c43c0-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="c43c0-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="c43c0-238">27</span><span class="sxs-lookup"><span data-stu-id="c43c0-238">27</span></span>|  
|<span data-ttu-id="c43c0-239">27</span><span class="sxs-lookup"><span data-stu-id="c43c0-239">27</span></span>|  
|<span data-ttu-id="c43c0-240">26</span><span class="sxs-lookup"><span data-stu-id="c43c0-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="c43c0-241">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="c43c0-241">Namespaces</span></span>  
 <span data-ttu-id="c43c0-242">[USING](using-entity-sql.md) определяет пространства имен, используемые в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="c43c0-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="c43c0-243">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="c43c0-244">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-244">Output:</span></span>  
  
|<span data-ttu-id="c43c0-245">Значение</span><span class="sxs-lookup"><span data-stu-id="c43c0-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c43c0-246">aa</span><span class="sxs-lookup"><span data-stu-id="c43c0-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="c43c0-247">Разбиение по страницам</span><span class="sxs-lookup"><span data-stu-id="c43c0-247">Paging</span></span>  
 <span data-ttu-id="c43c0-248">Paging может быть выражено путем объявления [подклавов SKIP](skip-entity-sql.md) и [LIMIT](limit-entity-sql.md) к оговорке [ORDER BY.](order-by-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="c43c0-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="c43c0-249">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="c43c0-250">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-250">Output:</span></span>  
  
|<span data-ttu-id="c43c0-251">ID</span><span class="sxs-lookup"><span data-stu-id="c43c0-251">ID</span></span>|<span data-ttu-id="c43c0-252">Имя</span><span class="sxs-lookup"><span data-stu-id="c43c0-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="c43c0-253">10</span><span class="sxs-lookup"><span data-stu-id="c43c0-253">10</span></span>|<span data-ttu-id="c43c0-254">Adina</span><span class="sxs-lookup"><span data-stu-id="c43c0-254">Adina</span></span>|  
|<span data-ttu-id="c43c0-255">11</span><span class="sxs-lookup"><span data-stu-id="c43c0-255">11</span></span>|<span data-ttu-id="c43c0-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="c43c0-256">Agcaoili</span></span>|  
|<span data-ttu-id="c43c0-257">12</span><span class="sxs-lookup"><span data-stu-id="c43c0-257">12</span></span>|<span data-ttu-id="c43c0-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="c43c0-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="c43c0-259">Группирование</span><span class="sxs-lookup"><span data-stu-id="c43c0-259">Grouping</span></span>  
 <span data-ttu-id="c43c0-260">[GROUPING BY](group-by-entity-sql.md) определяет группы, в которые должны быть размещены объекты, возвращенные экспрессом[(SELECT](select-entity-sql.md)) expression.</span><span class="sxs-lookup"><span data-stu-id="c43c0-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="c43c0-261">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="c43c0-262">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-262">Output:</span></span>  
  
|<span data-ttu-id="c43c0-263">name</span><span class="sxs-lookup"><span data-stu-id="c43c0-263">name</span></span>|  
|----------|  
|<span data-ttu-id="c43c0-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="c43c0-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="c43c0-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="c43c0-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="c43c0-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="c43c0-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="c43c0-267">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="c43c0-268">Навигации</span><span class="sxs-lookup"><span data-stu-id="c43c0-268">Navigation</span></span>  
 <span data-ttu-id="c43c0-269">Оператор навигации по связям позволяет переходить по связям от одной сущности (исходный элемент) к другой (конечный элемент).</span><span class="sxs-lookup"><span data-stu-id="c43c0-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="c43c0-270">[NAVIGATE](navigate-entity-sql.md) принимает тип отношений, квалифицированный как \<> пространства имен. \<имя типа отношения>.</span><span class="sxs-lookup"><span data-stu-id="c43c0-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="c43c0-271">Навигация возвращает\<Ref T> если кардинальность до конца 1.</span><span class="sxs-lookup"><span data-stu-id="c43c0-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="c43c0-272">Если кардинальность до конца n, коллекция<\<Ref T>> будут возвращены.</span><span class="sxs-lookup"><span data-stu-id="c43c0-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="c43c0-273">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="c43c0-274">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-274">Output:</span></span>  
  
|<span data-ttu-id="c43c0-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="c43c0-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="c43c0-276">1</span><span class="sxs-lookup"><span data-stu-id="c43c0-276">1</span></span>|  
|<span data-ttu-id="c43c0-277">2</span><span class="sxs-lookup"><span data-stu-id="c43c0-277">2</span></span>|  
|<span data-ttu-id="c43c0-278">3</span><span class="sxs-lookup"><span data-stu-id="c43c0-278">3</span></span>|  
|<span data-ttu-id="c43c0-279">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="c43c0-280">SELECT VALUE и SELECT</span><span class="sxs-lookup"><span data-stu-id="c43c0-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="c43c0-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="c43c0-281">SELECT VALUE</span></span>  
 <span data-ttu-id="c43c0-282">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает предложение SELECT VALUE, позволяющее пропустить неявное построение строки.</span><span class="sxs-lookup"><span data-stu-id="c43c0-282">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="c43c0-283">В предложении SELECT VALUE может быть указан только один элемент.</span><span class="sxs-lookup"><span data-stu-id="c43c0-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="c43c0-284">При использовании такого положения вокруг элементов в пункте SELECT не строится обертка строки, и, например, может быть произведена коллекция желаемой формы, например: `SELECT VALUE a`.</span><span class="sxs-lookup"><span data-stu-id="c43c0-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="c43c0-285">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="c43c0-286">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-286">Output:</span></span>  
  
|<span data-ttu-id="c43c0-287">Имя</span><span class="sxs-lookup"><span data-stu-id="c43c0-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="c43c0-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="c43c0-288">Adjustable Race</span></span>|  
|<span data-ttu-id="c43c0-289">Универсальная подставка для велосипеда</span><span class="sxs-lookup"><span data-stu-id="c43c0-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="c43c0-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="c43c0-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="c43c0-291">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="c43c0-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="c43c0-292">SELECT</span></span>  
 <span data-ttu-id="c43c0-293">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает также конструктор строк, позволяющий создавать произвольные строки.</span><span class="sxs-lookup"><span data-stu-id="c43c0-293">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="c43c0-294">Предложение SELECT принимает один или несколько элементов в проекции и возвращает запись данных с полями, например: `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="c43c0-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="c43c0-295">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-295">Example:</span></span>  
  
 <span data-ttu-id="c43c0-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="c43c0-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="c43c0-297">Имя</span><span class="sxs-lookup"><span data-stu-id="c43c0-297">Name</span></span>|<span data-ttu-id="c43c0-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="c43c0-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="c43c0-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="c43c0-299">Adjustable Race</span></span>|<span data-ttu-id="c43c0-300">1</span><span class="sxs-lookup"><span data-stu-id="c43c0-300">1</span></span>|  
|<span data-ttu-id="c43c0-301">Универсальная подставка для велосипеда</span><span class="sxs-lookup"><span data-stu-id="c43c0-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="c43c0-302">879</span><span class="sxs-lookup"><span data-stu-id="c43c0-302">879</span></span>|  
|<span data-ttu-id="c43c0-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="c43c0-303">AWC Logo Cap</span></span>|<span data-ttu-id="c43c0-304">712</span><span class="sxs-lookup"><span data-stu-id="c43c0-304">712</span></span>|  
|<span data-ttu-id="c43c0-305">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-305">...</span></span>|<span data-ttu-id="c43c0-306">...</span><span class="sxs-lookup"><span data-stu-id="c43c0-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="c43c0-307">Выражение варианта выбора</span><span class="sxs-lookup"><span data-stu-id="c43c0-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="c43c0-308">[Выражение случая](case-entity-sql.md) оценивает набор выражений Boolean для определения результата.</span><span class="sxs-lookup"><span data-stu-id="c43c0-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="c43c0-309">Пример</span><span class="sxs-lookup"><span data-stu-id="c43c0-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="c43c0-310">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c43c0-310">Output:</span></span>  
  
|<span data-ttu-id="c43c0-311">Значение</span><span class="sxs-lookup"><span data-stu-id="c43c0-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c43c0-312">TRUE</span><span class="sxs-lookup"><span data-stu-id="c43c0-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c43c0-313">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c43c0-313">See also</span></span>

- [<span data-ttu-id="c43c0-314">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c43c0-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="c43c0-315">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c43c0-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
