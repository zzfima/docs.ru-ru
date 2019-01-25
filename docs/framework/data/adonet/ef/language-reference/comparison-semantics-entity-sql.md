---
title: Семантика сравнения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 371999df0fb3177ecc90f9b1fa43d457a51bfd7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492498"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="b219d-102">Семантика сравнения (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b219d-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="b219d-103">Выполнение любого следующего оператора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] подразумевает сравнение типов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b219d-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="b219d-104">Явное сравнение</span><span class="sxs-lookup"><span data-stu-id="b219d-104">Explicit comparison</span></span>  
 <span data-ttu-id="b219d-105">Операции сравнения:</span><span class="sxs-lookup"><span data-stu-id="b219d-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="b219d-106">!=</span><span class="sxs-lookup"><span data-stu-id="b219d-106">!=</span></span>  
  
 <span data-ttu-id="b219d-107">Операции упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="b219d-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="b219d-108">Операции допустимости значений NULL:</span><span class="sxs-lookup"><span data-stu-id="b219d-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="b219d-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="b219d-109">IS NULL</span></span>  
  
-   <span data-ttu-id="b219d-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b219d-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="b219d-111">Явное отличие</span><span class="sxs-lookup"><span data-stu-id="b219d-111">Explicit distinction</span></span>  
 <span data-ttu-id="b219d-112">Отличие равенства:</span><span class="sxs-lookup"><span data-stu-id="b219d-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="b219d-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="b219d-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="b219d-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="b219d-114">GROUP BY</span></span>  
  
 <span data-ttu-id="b219d-115">Отличие упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="b219d-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="b219d-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="b219d-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="b219d-117">Неявное отличие</span><span class="sxs-lookup"><span data-stu-id="b219d-117">Implicit distinction</span></span>  
 <span data-ttu-id="b219d-118">Операция и предикаты для работы с наборами (равенство):</span><span class="sxs-lookup"><span data-stu-id="b219d-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="b219d-119">UNION</span><span class="sxs-lookup"><span data-stu-id="b219d-119">UNION</span></span>  
  
-   <span data-ttu-id="b219d-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="b219d-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="b219d-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="b219d-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="b219d-122">SET</span><span class="sxs-lookup"><span data-stu-id="b219d-122">SET</span></span>  
  
-   <span data-ttu-id="b219d-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="b219d-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="b219d-124">Предикаты элементов (равенство):</span><span class="sxs-lookup"><span data-stu-id="b219d-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="b219d-125">IN</span><span class="sxs-lookup"><span data-stu-id="b219d-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="b219d-126">Поддерживаемые сочетания</span><span class="sxs-lookup"><span data-stu-id="b219d-126">Supported Combinations</span></span>  
 <span data-ttu-id="b219d-127">В следующей таблице приводятся все поддерживаемые сочетания операторов сравнения для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="b219d-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="b219d-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="b219d-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="b219d-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="b219d-129">**!=**</span></span>|<span data-ttu-id="b219d-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="b219d-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="b219d-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="b219d-131">**DISTINCT**</span></span>|<span data-ttu-id="b219d-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="b219d-132">**UNION**</span></span><br /><br /> <span data-ttu-id="b219d-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="b219d-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="b219d-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="b219d-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="b219d-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="b219d-135">**SET**</span></span><br /><br /> <span data-ttu-id="b219d-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="b219d-136">**OVERLAPS**</span></span>|<span data-ttu-id="b219d-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="b219d-137">**IN**</span></span>|<span data-ttu-id="b219d-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="b219d-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="b219d-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="b219d-139">**>   >=**</span></span>|<span data-ttu-id="b219d-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="b219d-140">**ORDER BY**</span></span>|<span data-ttu-id="b219d-141">**ИМЕЕТ ЗНАЧЕНИЕ NULL**</span><span class="sxs-lookup"><span data-stu-id="b219d-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="b219d-142">**НЕ РАВНО NULL**</span><span class="sxs-lookup"><span data-stu-id="b219d-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="b219d-143">Тип сущности</span><span class="sxs-lookup"><span data-stu-id="b219d-143">Entity type</span></span>|<span data-ttu-id="b219d-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="b219d-145">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="b219d-146">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="b219d-147">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="b219d-148">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-149">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="b219d-151">Сложный тип</span><span class="sxs-lookup"><span data-stu-id="b219d-151">Complex type</span></span>|<span data-ttu-id="b219d-152">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-153">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-154">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-155">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-156">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-157">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-158">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="b219d-159">Строка</span><span class="sxs-lookup"><span data-stu-id="b219d-159">Row</span></span>|<span data-ttu-id="b219d-160">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="b219d-161">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="b219d-162">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="b219d-163">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-164">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-165">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="b219d-166">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="b219d-167">Тип-примитив</span><span class="sxs-lookup"><span data-stu-id="b219d-167">Primitive type</span></span>|<span data-ttu-id="b219d-168">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="b219d-168">Provider-specific</span></span>|<span data-ttu-id="b219d-169">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="b219d-169">Provider-specific</span></span>|<span data-ttu-id="b219d-170">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="b219d-170">Provider-specific</span></span>|<span data-ttu-id="b219d-171">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="b219d-171">Provider-specific</span></span>|<span data-ttu-id="b219d-172">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="b219d-172">Provider-specific</span></span>|<span data-ttu-id="b219d-173">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="b219d-173">Provider-specific</span></span>|<span data-ttu-id="b219d-174">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="b219d-174">Provider-specific</span></span>|  
|<span data-ttu-id="b219d-175">Мультинабор</span><span class="sxs-lookup"><span data-stu-id="b219d-175">Multiset</span></span>|<span data-ttu-id="b219d-176">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-177">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-178">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-179">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-180">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-181">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-182">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="b219d-183">Ссылочный</span><span class="sxs-lookup"><span data-stu-id="b219d-183">Ref</span></span>|<span data-ttu-id="b219d-184">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="b219d-185">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="b219d-186">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="b219d-187">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="b219d-188">Throw</span><span class="sxs-lookup"><span data-stu-id="b219d-188">Throw</span></span>|<span data-ttu-id="b219d-189">Throw</span><span class="sxs-lookup"><span data-stu-id="b219d-189">Throw</span></span>|<span data-ttu-id="b219d-190">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="b219d-191">Ассоциация</span><span class="sxs-lookup"><span data-stu-id="b219d-191">Association</span></span><br /><br /> <span data-ttu-id="b219d-192">type</span><span class="sxs-lookup"><span data-stu-id="b219d-192">type</span></span>|<span data-ttu-id="b219d-193">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-194">Throw</span><span class="sxs-lookup"><span data-stu-id="b219d-194">Throw</span></span>|<span data-ttu-id="b219d-195">Throw</span><span class="sxs-lookup"><span data-stu-id="b219d-195">Throw</span></span>|<span data-ttu-id="b219d-196">Throw</span><span class="sxs-lookup"><span data-stu-id="b219d-196">Throw</span></span>|<span data-ttu-id="b219d-197">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-198">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="b219d-199">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="b219d-200"><sup>1</sup>ссылки экземпляров типа сущности неявно сравниваются, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b219d-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="b219d-201">Экземпляр сущности нельзя сравнивать с явной ссылкой.</span><span class="sxs-lookup"><span data-stu-id="b219d-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="b219d-202">При попытке такого сравнения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="b219d-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="b219d-203">Например, следующий запрос вызовет исключение:</span><span class="sxs-lookup"><span data-stu-id="b219d-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="b219d-204"><sup>2</sup>свойства сложных типов выравниваются перед отправкой в хранилище, поэтому их можно сравнивать (при условии, что сравнимы их свойства).</span><span class="sxs-lookup"><span data-stu-id="b219d-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="b219d-205">Также см. в разделе <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="b219d-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="b219d-206"><sup>3</sup>среды выполнения платформы Entity Framework обнаруживает неподдерживаемый вариант и вызывает значимое исключение, не вовлекая поставщик или хранилище.</span><span class="sxs-lookup"><span data-stu-id="b219d-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="b219d-207"><sup>4</sup>сделана попытка сравнить все свойства.</span><span class="sxs-lookup"><span data-stu-id="b219d-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="b219d-208">Если имеется свойство несравнимого типа, например text, ntext или image, может возникнуть серверное исключение.</span><span class="sxs-lookup"><span data-stu-id="b219d-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="b219d-209"><sup>5</sup>сравниваются все отдельные элементы ссылок (включая имя набора сущностей и все ключевые свойства типа сущности).</span><span class="sxs-lookup"><span data-stu-id="b219d-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b219d-210">См. также</span><span class="sxs-lookup"><span data-stu-id="b219d-210">See also</span></span>
- [<span data-ttu-id="b219d-211">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b219d-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
