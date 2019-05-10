---
title: Семантика сравнения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 2ca91861d4830321168e96fb200c4889dc33b04b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64631714"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="04bd0-102">Семантика сравнения (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="04bd0-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="04bd0-103">Выполнение любого следующего оператора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] подразумевает сравнение типов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="04bd0-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="04bd0-104">Явное сравнение</span><span class="sxs-lookup"><span data-stu-id="04bd0-104">Explicit comparison</span></span>  
 <span data-ttu-id="04bd0-105">Операции сравнения:</span><span class="sxs-lookup"><span data-stu-id="04bd0-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="04bd0-106">!=</span><span class="sxs-lookup"><span data-stu-id="04bd0-106">!=</span></span>  
  
 <span data-ttu-id="04bd0-107">Операции упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="04bd0-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="04bd0-108">Операции допустимости значений NULL:</span><span class="sxs-lookup"><span data-stu-id="04bd0-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="04bd0-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="04bd0-109">IS NULL</span></span>  
  
- <span data-ttu-id="04bd0-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="04bd0-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="04bd0-111">Явное отличие</span><span class="sxs-lookup"><span data-stu-id="04bd0-111">Explicit distinction</span></span>  
 <span data-ttu-id="04bd0-112">Отличие равенства:</span><span class="sxs-lookup"><span data-stu-id="04bd0-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="04bd0-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="04bd0-113">DISTINCT</span></span>  
  
- <span data-ttu-id="04bd0-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="04bd0-114">GROUP BY</span></span>  
  
 <span data-ttu-id="04bd0-115">Отличие упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="04bd0-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="04bd0-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="04bd0-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="04bd0-117">Неявное отличие</span><span class="sxs-lookup"><span data-stu-id="04bd0-117">Implicit distinction</span></span>  
 <span data-ttu-id="04bd0-118">Операция и предикаты для работы с наборами (равенство):</span><span class="sxs-lookup"><span data-stu-id="04bd0-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="04bd0-119">UNION</span><span class="sxs-lookup"><span data-stu-id="04bd0-119">UNION</span></span>  
  
- <span data-ttu-id="04bd0-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="04bd0-120">INTERSECT</span></span>  
  
- <span data-ttu-id="04bd0-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="04bd0-121">EXCEPT</span></span>  
  
- <span data-ttu-id="04bd0-122">SET</span><span class="sxs-lookup"><span data-stu-id="04bd0-122">SET</span></span>  
  
- <span data-ttu-id="04bd0-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="04bd0-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="04bd0-124">Предикаты элементов (равенство):</span><span class="sxs-lookup"><span data-stu-id="04bd0-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="04bd0-125">IN</span><span class="sxs-lookup"><span data-stu-id="04bd0-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="04bd0-126">Поддерживаемые сочетания</span><span class="sxs-lookup"><span data-stu-id="04bd0-126">Supported Combinations</span></span>  
 <span data-ttu-id="04bd0-127">В следующей таблице приводятся все поддерживаемые сочетания операторов сравнения для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="04bd0-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="04bd0-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="04bd0-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="04bd0-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="04bd0-129">**!=**</span></span>|<span data-ttu-id="04bd0-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="04bd0-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="04bd0-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="04bd0-131">**DISTINCT**</span></span>|<span data-ttu-id="04bd0-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="04bd0-132">**UNION**</span></span><br /><br /> <span data-ttu-id="04bd0-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="04bd0-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="04bd0-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="04bd0-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="04bd0-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="04bd0-135">**SET**</span></span><br /><br /> <span data-ttu-id="04bd0-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="04bd0-136">**OVERLAPS**</span></span>|<span data-ttu-id="04bd0-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="04bd0-137">**IN**</span></span>|<span data-ttu-id="04bd0-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="04bd0-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="04bd0-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="04bd0-139">**>   >=**</span></span>|<span data-ttu-id="04bd0-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="04bd0-140">**ORDER BY**</span></span>|<span data-ttu-id="04bd0-141">**ИМЕЕТ ЗНАЧЕНИЕ NULL**</span><span class="sxs-lookup"><span data-stu-id="04bd0-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="04bd0-142">**НЕ РАВНО NULL**</span><span class="sxs-lookup"><span data-stu-id="04bd0-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="04bd0-143">Тип сущности</span><span class="sxs-lookup"><span data-stu-id="04bd0-143">Entity type</span></span>|<span data-ttu-id="04bd0-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="04bd0-145">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="04bd0-146">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="04bd0-147">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="04bd0-148">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-149">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="04bd0-151">Сложный тип</span><span class="sxs-lookup"><span data-stu-id="04bd0-151">Complex type</span></span>|<span data-ttu-id="04bd0-152">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-153">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-154">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-155">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-156">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-157">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-158">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="04bd0-159">Строка</span><span class="sxs-lookup"><span data-stu-id="04bd0-159">Row</span></span>|<span data-ttu-id="04bd0-160">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="04bd0-161">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="04bd0-162">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="04bd0-163">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-164">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-165">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="04bd0-166">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="04bd0-167">Тип-примитив</span><span class="sxs-lookup"><span data-stu-id="04bd0-167">Primitive type</span></span>|<span data-ttu-id="04bd0-168">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="04bd0-168">Provider-specific</span></span>|<span data-ttu-id="04bd0-169">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="04bd0-169">Provider-specific</span></span>|<span data-ttu-id="04bd0-170">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="04bd0-170">Provider-specific</span></span>|<span data-ttu-id="04bd0-171">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="04bd0-171">Provider-specific</span></span>|<span data-ttu-id="04bd0-172">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="04bd0-172">Provider-specific</span></span>|<span data-ttu-id="04bd0-173">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="04bd0-173">Provider-specific</span></span>|<span data-ttu-id="04bd0-174">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="04bd0-174">Provider-specific</span></span>|  
|<span data-ttu-id="04bd0-175">Мультинабор</span><span class="sxs-lookup"><span data-stu-id="04bd0-175">Multiset</span></span>|<span data-ttu-id="04bd0-176">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-177">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-178">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-179">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-180">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-181">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-182">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="04bd0-183">Ссылочный</span><span class="sxs-lookup"><span data-stu-id="04bd0-183">Ref</span></span>|<span data-ttu-id="04bd0-184">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="04bd0-185">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="04bd0-186">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="04bd0-187">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="04bd0-188">Throw</span><span class="sxs-lookup"><span data-stu-id="04bd0-188">Throw</span></span>|<span data-ttu-id="04bd0-189">Throw</span><span class="sxs-lookup"><span data-stu-id="04bd0-189">Throw</span></span>|<span data-ttu-id="04bd0-190">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="04bd0-191">Ассоциация</span><span class="sxs-lookup"><span data-stu-id="04bd0-191">Association</span></span><br /><br /> <span data-ttu-id="04bd0-192">type</span><span class="sxs-lookup"><span data-stu-id="04bd0-192">type</span></span>|<span data-ttu-id="04bd0-193">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-194">Throw</span><span class="sxs-lookup"><span data-stu-id="04bd0-194">Throw</span></span>|<span data-ttu-id="04bd0-195">Throw</span><span class="sxs-lookup"><span data-stu-id="04bd0-195">Throw</span></span>|<span data-ttu-id="04bd0-196">Throw</span><span class="sxs-lookup"><span data-stu-id="04bd0-196">Throw</span></span>|<span data-ttu-id="04bd0-197">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-198">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="04bd0-199">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="04bd0-200"><sup>1</sup>ссылки экземпляров типа сущности неявно сравниваются, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="04bd0-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="04bd0-201">Экземпляр сущности нельзя сравнивать с явной ссылкой.</span><span class="sxs-lookup"><span data-stu-id="04bd0-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="04bd0-202">При попытке такого сравнения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="04bd0-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="04bd0-203">Например, следующий запрос вызовет исключение:</span><span class="sxs-lookup"><span data-stu-id="04bd0-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="04bd0-204"><sup>2</sup>свойства сложных типов выравниваются перед отправкой в хранилище, поэтому их можно сравнивать (при условии, что сравнимы их свойства).</span><span class="sxs-lookup"><span data-stu-id="04bd0-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="04bd0-205">Также см. в разделе <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="04bd0-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="04bd0-206"><sup>3</sup>среды выполнения платформы Entity Framework обнаруживает неподдерживаемый вариант и вызывает значимое исключение, не вовлекая поставщик или хранилище.</span><span class="sxs-lookup"><span data-stu-id="04bd0-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="04bd0-207"><sup>4</sup>сделана попытка сравнить все свойства.</span><span class="sxs-lookup"><span data-stu-id="04bd0-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="04bd0-208">Если имеется свойство несравнимого типа, например text, ntext или image, может возникнуть серверное исключение.</span><span class="sxs-lookup"><span data-stu-id="04bd0-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="04bd0-209"><sup>5</sup>сравниваются все отдельные элементы ссылок (включая имя набора сущностей и все ключевые свойства типа сущности).</span><span class="sxs-lookup"><span data-stu-id="04bd0-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04bd0-210">См. также</span><span class="sxs-lookup"><span data-stu-id="04bd0-210">See also</span></span>

- [<span data-ttu-id="04bd0-211">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="04bd0-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
