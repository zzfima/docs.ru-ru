---
title: Семантика сравнения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 6b4c4177ebd6c45e00a1ac7774e40a43e0c14a74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083339"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="f39d3-102">Семантика сравнения (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f39d3-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="f39d3-103">Выполнение любого следующего оператора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] подразумевает сравнение типов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="f39d3-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="f39d3-104">Явное сравнение</span><span class="sxs-lookup"><span data-stu-id="f39d3-104">Explicit comparison</span></span>  
 <span data-ttu-id="f39d3-105">Операции сравнения:</span><span class="sxs-lookup"><span data-stu-id="f39d3-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="f39d3-106">!=</span><span class="sxs-lookup"><span data-stu-id="f39d3-106">!=</span></span>  
  
 <span data-ttu-id="f39d3-107">Операции упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="f39d3-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="f39d3-108">Операции допустимости значений NULL:</span><span class="sxs-lookup"><span data-stu-id="f39d3-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="f39d3-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="f39d3-109">IS NULL</span></span>  
  
-   <span data-ttu-id="f39d3-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f39d3-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="f39d3-111">Явное отличие</span><span class="sxs-lookup"><span data-stu-id="f39d3-111">Explicit distinction</span></span>  
 <span data-ttu-id="f39d3-112">Отличие равенства:</span><span class="sxs-lookup"><span data-stu-id="f39d3-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="f39d3-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="f39d3-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="f39d3-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="f39d3-114">GROUP BY</span></span>  
  
 <span data-ttu-id="f39d3-115">Отличие упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="f39d3-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="f39d3-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="f39d3-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="f39d3-117">Неявное отличие</span><span class="sxs-lookup"><span data-stu-id="f39d3-117">Implicit distinction</span></span>  
 <span data-ttu-id="f39d3-118">Операция и предикаты для работы с наборами (равенство):</span><span class="sxs-lookup"><span data-stu-id="f39d3-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="f39d3-119">UNION</span><span class="sxs-lookup"><span data-stu-id="f39d3-119">UNION</span></span>  
  
-   <span data-ttu-id="f39d3-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="f39d3-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="f39d3-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="f39d3-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="f39d3-122">SET</span><span class="sxs-lookup"><span data-stu-id="f39d3-122">SET</span></span>  
  
-   <span data-ttu-id="f39d3-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="f39d3-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="f39d3-124">Предикаты элементов (равенство):</span><span class="sxs-lookup"><span data-stu-id="f39d3-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="f39d3-125">IN</span><span class="sxs-lookup"><span data-stu-id="f39d3-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="f39d3-126">Поддерживаемые сочетания</span><span class="sxs-lookup"><span data-stu-id="f39d3-126">Supported Combinations</span></span>  
 <span data-ttu-id="f39d3-127">В следующей таблице приводятся все поддерживаемые сочетания операторов сравнения для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="f39d3-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="f39d3-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="f39d3-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="f39d3-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="f39d3-129">**!=**</span></span>|<span data-ttu-id="f39d3-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="f39d3-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="f39d3-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="f39d3-131">**DISTINCT**</span></span>|<span data-ttu-id="f39d3-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="f39d3-132">**UNION**</span></span><br /><br /> <span data-ttu-id="f39d3-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="f39d3-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="f39d3-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="f39d3-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="f39d3-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="f39d3-135">**SET**</span></span><br /><br /> <span data-ttu-id="f39d3-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="f39d3-136">**OVERLAPS**</span></span>|<span data-ttu-id="f39d3-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="f39d3-137">**IN**</span></span>|<span data-ttu-id="f39d3-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="f39d3-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="f39d3-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="f39d3-139">**>   >=**</span></span>|<span data-ttu-id="f39d3-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="f39d3-140">**ORDER BY**</span></span>|<span data-ttu-id="f39d3-141">**ИМЕЕТ ЗНАЧЕНИЕ NULL**</span><span class="sxs-lookup"><span data-stu-id="f39d3-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="f39d3-142">**НЕ РАВНО NULL**</span><span class="sxs-lookup"><span data-stu-id="f39d3-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="f39d3-143">Тип сущности</span><span class="sxs-lookup"><span data-stu-id="f39d3-143">Entity type</span></span>|<span data-ttu-id="f39d3-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="f39d3-145">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="f39d3-146">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="f39d3-147">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="f39d3-148">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-149">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="f39d3-151">Сложный тип</span><span class="sxs-lookup"><span data-stu-id="f39d3-151">Complex type</span></span>|<span data-ttu-id="f39d3-152">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-153">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-154">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-155">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-156">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-157">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-158">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="f39d3-159">Строка</span><span class="sxs-lookup"><span data-stu-id="f39d3-159">Row</span></span>|<span data-ttu-id="f39d3-160">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="f39d3-161">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="f39d3-162">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="f39d3-163">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-164">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-165">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="f39d3-166">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="f39d3-167">Тип-примитив</span><span class="sxs-lookup"><span data-stu-id="f39d3-167">Primitive type</span></span>|<span data-ttu-id="f39d3-168">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="f39d3-168">Provider-specific</span></span>|<span data-ttu-id="f39d3-169">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="f39d3-169">Provider-specific</span></span>|<span data-ttu-id="f39d3-170">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="f39d3-170">Provider-specific</span></span>|<span data-ttu-id="f39d3-171">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="f39d3-171">Provider-specific</span></span>|<span data-ttu-id="f39d3-172">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="f39d3-172">Provider-specific</span></span>|<span data-ttu-id="f39d3-173">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="f39d3-173">Provider-specific</span></span>|<span data-ttu-id="f39d3-174">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="f39d3-174">Provider-specific</span></span>|  
|<span data-ttu-id="f39d3-175">Мультинабор</span><span class="sxs-lookup"><span data-stu-id="f39d3-175">Multiset</span></span>|<span data-ttu-id="f39d3-176">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-177">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-178">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-179">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-180">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-181">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-182">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="f39d3-183">Ссылочный</span><span class="sxs-lookup"><span data-stu-id="f39d3-183">Ref</span></span>|<span data-ttu-id="f39d3-184">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="f39d3-185">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="f39d3-186">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="f39d3-187">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="f39d3-188">Throw</span><span class="sxs-lookup"><span data-stu-id="f39d3-188">Throw</span></span>|<span data-ttu-id="f39d3-189">Throw</span><span class="sxs-lookup"><span data-stu-id="f39d3-189">Throw</span></span>|<span data-ttu-id="f39d3-190">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="f39d3-191">Ассоциация</span><span class="sxs-lookup"><span data-stu-id="f39d3-191">Association</span></span><br /><br /> <span data-ttu-id="f39d3-192">type</span><span class="sxs-lookup"><span data-stu-id="f39d3-192">type</span></span>|<span data-ttu-id="f39d3-193">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-194">Throw</span><span class="sxs-lookup"><span data-stu-id="f39d3-194">Throw</span></span>|<span data-ttu-id="f39d3-195">Throw</span><span class="sxs-lookup"><span data-stu-id="f39d3-195">Throw</span></span>|<span data-ttu-id="f39d3-196">Throw</span><span class="sxs-lookup"><span data-stu-id="f39d3-196">Throw</span></span>|<span data-ttu-id="f39d3-197">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-198">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="f39d3-199">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="f39d3-200"><sup>1</sup>ссылки экземпляров типа сущности неявно сравниваются, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f39d3-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="f39d3-201">Экземпляр сущности нельзя сравнивать с явной ссылкой.</span><span class="sxs-lookup"><span data-stu-id="f39d3-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="f39d3-202">При попытке такого сравнения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="f39d3-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="f39d3-203">Например, следующий запрос вызовет исключение:</span><span class="sxs-lookup"><span data-stu-id="f39d3-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="f39d3-204"><sup>2</sup>свойства сложных типов выравниваются перед отправкой в хранилище, поэтому их можно сравнивать (при условии, что сравнимы их свойства).</span><span class="sxs-lookup"><span data-stu-id="f39d3-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="f39d3-205">Также см. в разделе <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="f39d3-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="f39d3-206"><sup>3</sup>среды выполнения платформы Entity Framework обнаруживает неподдерживаемый вариант и вызывает значимое исключение, не вовлекая поставщик или хранилище.</span><span class="sxs-lookup"><span data-stu-id="f39d3-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="f39d3-207"><sup>4</sup>сделана попытка сравнить все свойства.</span><span class="sxs-lookup"><span data-stu-id="f39d3-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="f39d3-208">Если имеется свойство несравнимого типа, например text, ntext или image, может возникнуть серверное исключение.</span><span class="sxs-lookup"><span data-stu-id="f39d3-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="f39d3-209"><sup>5</sup>сравниваются все отдельные элементы ссылок (включая имя набора сущностей и все ключевые свойства типа сущности).</span><span class="sxs-lookup"><span data-stu-id="f39d3-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f39d3-210">См. также</span><span class="sxs-lookup"><span data-stu-id="f39d3-210">See also</span></span>

- [<span data-ttu-id="f39d3-211">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f39d3-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
