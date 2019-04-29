---
title: Семантика сравнения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 6b4c4177ebd6c45e00a1ac7774e40a43e0c14a74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61605975"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="d53da-102">Семантика сравнения (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d53da-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="d53da-103">Выполнение любого следующего оператора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] подразумевает сравнение типов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="d53da-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="d53da-104">Явное сравнение</span><span class="sxs-lookup"><span data-stu-id="d53da-104">Explicit comparison</span></span>  
 <span data-ttu-id="d53da-105">Операции сравнения:</span><span class="sxs-lookup"><span data-stu-id="d53da-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="d53da-106">!=</span><span class="sxs-lookup"><span data-stu-id="d53da-106">!=</span></span>  
  
 <span data-ttu-id="d53da-107">Операции упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="d53da-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="d53da-108">Операции допустимости значений NULL:</span><span class="sxs-lookup"><span data-stu-id="d53da-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="d53da-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="d53da-109">IS NULL</span></span>  
  
- <span data-ttu-id="d53da-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="d53da-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="d53da-111">Явное отличие</span><span class="sxs-lookup"><span data-stu-id="d53da-111">Explicit distinction</span></span>  
 <span data-ttu-id="d53da-112">Отличие равенства:</span><span class="sxs-lookup"><span data-stu-id="d53da-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="d53da-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="d53da-113">DISTINCT</span></span>  
  
- <span data-ttu-id="d53da-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="d53da-114">GROUP BY</span></span>  
  
 <span data-ttu-id="d53da-115">Отличие упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="d53da-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="d53da-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="d53da-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="d53da-117">Неявное отличие</span><span class="sxs-lookup"><span data-stu-id="d53da-117">Implicit distinction</span></span>  
 <span data-ttu-id="d53da-118">Операция и предикаты для работы с наборами (равенство):</span><span class="sxs-lookup"><span data-stu-id="d53da-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="d53da-119">UNION</span><span class="sxs-lookup"><span data-stu-id="d53da-119">UNION</span></span>  
  
- <span data-ttu-id="d53da-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="d53da-120">INTERSECT</span></span>  
  
- <span data-ttu-id="d53da-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="d53da-121">EXCEPT</span></span>  
  
- <span data-ttu-id="d53da-122">SET</span><span class="sxs-lookup"><span data-stu-id="d53da-122">SET</span></span>  
  
- <span data-ttu-id="d53da-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="d53da-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="d53da-124">Предикаты элементов (равенство):</span><span class="sxs-lookup"><span data-stu-id="d53da-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="d53da-125">IN</span><span class="sxs-lookup"><span data-stu-id="d53da-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="d53da-126">Поддерживаемые сочетания</span><span class="sxs-lookup"><span data-stu-id="d53da-126">Supported Combinations</span></span>  
 <span data-ttu-id="d53da-127">В следующей таблице приводятся все поддерживаемые сочетания операторов сравнения для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="d53da-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="d53da-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="d53da-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="d53da-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="d53da-129">**!=**</span></span>|<span data-ttu-id="d53da-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="d53da-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="d53da-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="d53da-131">**DISTINCT**</span></span>|<span data-ttu-id="d53da-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="d53da-132">**UNION**</span></span><br /><br /> <span data-ttu-id="d53da-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="d53da-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="d53da-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="d53da-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="d53da-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="d53da-135">**SET**</span></span><br /><br /> <span data-ttu-id="d53da-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="d53da-136">**OVERLAPS**</span></span>|<span data-ttu-id="d53da-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="d53da-137">**IN**</span></span>|<span data-ttu-id="d53da-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="d53da-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="d53da-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="d53da-139">**>   >=**</span></span>|<span data-ttu-id="d53da-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="d53da-140">**ORDER BY**</span></span>|<span data-ttu-id="d53da-141">**ИМЕЕТ ЗНАЧЕНИЕ NULL**</span><span class="sxs-lookup"><span data-stu-id="d53da-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="d53da-142">**НЕ РАВНО NULL**</span><span class="sxs-lookup"><span data-stu-id="d53da-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="d53da-143">Тип сущности</span><span class="sxs-lookup"><span data-stu-id="d53da-143">Entity type</span></span>|<span data-ttu-id="d53da-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="d53da-145">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="d53da-146">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="d53da-147">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="d53da-148">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-149">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="d53da-151">Сложный тип</span><span class="sxs-lookup"><span data-stu-id="d53da-151">Complex type</span></span>|<span data-ttu-id="d53da-152">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-153">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-154">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-155">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-156">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-157">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-158">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d53da-159">Строка</span><span class="sxs-lookup"><span data-stu-id="d53da-159">Row</span></span>|<span data-ttu-id="d53da-160">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="d53da-161">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="d53da-162">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="d53da-163">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-164">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-165">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="d53da-166">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d53da-167">Тип-примитив</span><span class="sxs-lookup"><span data-stu-id="d53da-167">Primitive type</span></span>|<span data-ttu-id="d53da-168">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d53da-168">Provider-specific</span></span>|<span data-ttu-id="d53da-169">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d53da-169">Provider-specific</span></span>|<span data-ttu-id="d53da-170">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d53da-170">Provider-specific</span></span>|<span data-ttu-id="d53da-171">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d53da-171">Provider-specific</span></span>|<span data-ttu-id="d53da-172">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d53da-172">Provider-specific</span></span>|<span data-ttu-id="d53da-173">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d53da-173">Provider-specific</span></span>|<span data-ttu-id="d53da-174">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d53da-174">Provider-specific</span></span>|  
|<span data-ttu-id="d53da-175">Мультинабор</span><span class="sxs-lookup"><span data-stu-id="d53da-175">Multiset</span></span>|<span data-ttu-id="d53da-176">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-177">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-178">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-179">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-180">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-181">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-182">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d53da-183">Ссылочный</span><span class="sxs-lookup"><span data-stu-id="d53da-183">Ref</span></span>|<span data-ttu-id="d53da-184">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="d53da-185">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="d53da-186">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="d53da-187">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="d53da-188">Throw</span><span class="sxs-lookup"><span data-stu-id="d53da-188">Throw</span></span>|<span data-ttu-id="d53da-189">Throw</span><span class="sxs-lookup"><span data-stu-id="d53da-189">Throw</span></span>|<span data-ttu-id="d53da-190">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="d53da-191">Ассоциация</span><span class="sxs-lookup"><span data-stu-id="d53da-191">Association</span></span><br /><br /> <span data-ttu-id="d53da-192">type</span><span class="sxs-lookup"><span data-stu-id="d53da-192">type</span></span>|<span data-ttu-id="d53da-193">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-194">Throw</span><span class="sxs-lookup"><span data-stu-id="d53da-194">Throw</span></span>|<span data-ttu-id="d53da-195">Throw</span><span class="sxs-lookup"><span data-stu-id="d53da-195">Throw</span></span>|<span data-ttu-id="d53da-196">Throw</span><span class="sxs-lookup"><span data-stu-id="d53da-196">Throw</span></span>|<span data-ttu-id="d53da-197">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-198">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="d53da-199">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="d53da-200"><sup>1</sup>ссылки экземпляров типа сущности неявно сравниваются, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d53da-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="d53da-201">Экземпляр сущности нельзя сравнивать с явной ссылкой.</span><span class="sxs-lookup"><span data-stu-id="d53da-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="d53da-202">При попытке такого сравнения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="d53da-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="d53da-203">Например, следующий запрос вызовет исключение:</span><span class="sxs-lookup"><span data-stu-id="d53da-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="d53da-204"><sup>2</sup>свойства сложных типов выравниваются перед отправкой в хранилище, поэтому их можно сравнивать (при условии, что сравнимы их свойства).</span><span class="sxs-lookup"><span data-stu-id="d53da-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="d53da-205">Также см. в разделе <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="d53da-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="d53da-206"><sup>3</sup>среды выполнения платформы Entity Framework обнаруживает неподдерживаемый вариант и вызывает значимое исключение, не вовлекая поставщик или хранилище.</span><span class="sxs-lookup"><span data-stu-id="d53da-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="d53da-207"><sup>4</sup>сделана попытка сравнить все свойства.</span><span class="sxs-lookup"><span data-stu-id="d53da-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="d53da-208">Если имеется свойство несравнимого типа, например text, ntext или image, может возникнуть серверное исключение.</span><span class="sxs-lookup"><span data-stu-id="d53da-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="d53da-209"><sup>5</sup>сравниваются все отдельные элементы ссылок (включая имя набора сущностей и все ключевые свойства типа сущности).</span><span class="sxs-lookup"><span data-stu-id="d53da-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53da-210">См. также</span><span class="sxs-lookup"><span data-stu-id="d53da-210">See also</span></span>

- [<span data-ttu-id="d53da-211">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d53da-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
