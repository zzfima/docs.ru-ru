---
title: Семантика сравнения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 8d7868b0166f0a18824ec25e6cdf639deec665ac
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833935"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="37d9b-102">Семантика сравнения (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="37d9b-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="37d9b-103">Выполнение любого следующего оператора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] подразумевает сравнение типов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="37d9b-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="37d9b-104">Явное сравнение</span><span class="sxs-lookup"><span data-stu-id="37d9b-104">Explicit comparison</span></span>  
 <span data-ttu-id="37d9b-105">Операции сравнения:</span><span class="sxs-lookup"><span data-stu-id="37d9b-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="37d9b-106">!=</span><span class="sxs-lookup"><span data-stu-id="37d9b-106">!=</span></span>  
  
 <span data-ttu-id="37d9b-107">Операции упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="37d9b-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="37d9b-108">Операции допустимости значений NULL:</span><span class="sxs-lookup"><span data-stu-id="37d9b-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="37d9b-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="37d9b-109">IS NULL</span></span>  
  
- <span data-ttu-id="37d9b-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="37d9b-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="37d9b-111">Явное отличие</span><span class="sxs-lookup"><span data-stu-id="37d9b-111">Explicit distinction</span></span>  
 <span data-ttu-id="37d9b-112">Отличие равенства:</span><span class="sxs-lookup"><span data-stu-id="37d9b-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="37d9b-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="37d9b-113">DISTINCT</span></span>  
  
- <span data-ttu-id="37d9b-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="37d9b-114">GROUP BY</span></span>  
  
 <span data-ttu-id="37d9b-115">Отличие упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="37d9b-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="37d9b-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="37d9b-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="37d9b-117">Неявное отличие</span><span class="sxs-lookup"><span data-stu-id="37d9b-117">Implicit distinction</span></span>  
 <span data-ttu-id="37d9b-118">Операция и предикаты для работы с наборами (равенство):</span><span class="sxs-lookup"><span data-stu-id="37d9b-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="37d9b-119">UNION</span><span class="sxs-lookup"><span data-stu-id="37d9b-119">UNION</span></span>  
  
- <span data-ttu-id="37d9b-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="37d9b-120">INTERSECT</span></span>  
  
- <span data-ttu-id="37d9b-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="37d9b-121">EXCEPT</span></span>  
  
- <span data-ttu-id="37d9b-122">SET</span><span class="sxs-lookup"><span data-stu-id="37d9b-122">SET</span></span>  
  
- <span data-ttu-id="37d9b-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="37d9b-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="37d9b-124">Предикаты элементов (равенство):</span><span class="sxs-lookup"><span data-stu-id="37d9b-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="37d9b-125">IN</span><span class="sxs-lookup"><span data-stu-id="37d9b-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="37d9b-126">Поддерживаемые сочетания</span><span class="sxs-lookup"><span data-stu-id="37d9b-126">Supported Combinations</span></span>  
 <span data-ttu-id="37d9b-127">В следующей таблице приводятся все поддерживаемые сочетания операторов сравнения для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="37d9b-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="37d9b-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="37d9b-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="37d9b-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="37d9b-129">**!=**</span></span>|<span data-ttu-id="37d9b-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="37d9b-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="37d9b-131">**ИНДИВИДУАЛЬНО**</span><span class="sxs-lookup"><span data-stu-id="37d9b-131">**DISTINCT**</span></span>|<span data-ttu-id="37d9b-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="37d9b-132">**UNION**</span></span><br /><br /> <span data-ttu-id="37d9b-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="37d9b-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="37d9b-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="37d9b-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="37d9b-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="37d9b-135">**SET**</span></span><br /><br /> <span data-ttu-id="37d9b-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="37d9b-136">**OVERLAPS**</span></span>|<span data-ttu-id="37d9b-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="37d9b-137">**IN**</span></span>|<span data-ttu-id="37d9b-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="37d9b-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="37d9b-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="37d9b-139">**>   >=**</span></span>|<span data-ttu-id="37d9b-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="37d9b-140">**ORDER BY**</span></span>|<span data-ttu-id="37d9b-141">**ИМЕЕТ ЗНАЧЕНИЕ NULL**</span><span class="sxs-lookup"><span data-stu-id="37d9b-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="37d9b-142">**НЕ РАВНО NULL**</span><span class="sxs-lookup"><span data-stu-id="37d9b-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="37d9b-143">Тип сущности</span><span class="sxs-lookup"><span data-stu-id="37d9b-143">Entity type</span></span>|<span data-ttu-id="37d9b-144">Ссылка<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="37d9b-145">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="37d9b-146">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="37d9b-147">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="37d9b-148">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-149">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-150">Ссылка<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="37d9b-151">Сложный тип</span><span class="sxs-lookup"><span data-stu-id="37d9b-151">Complex type</span></span>|<span data-ttu-id="37d9b-152">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-153">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-154">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-155">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-156">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-157">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-158">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="37d9b-159">Строка</span><span class="sxs-lookup"><span data-stu-id="37d9b-159">Row</span></span>|<span data-ttu-id="37d9b-160">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="37d9b-161">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="37d9b-162">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="37d9b-163">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-164">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-165">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="37d9b-166">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="37d9b-167">Тип-примитив</span><span class="sxs-lookup"><span data-stu-id="37d9b-167">Primitive type</span></span>|<span data-ttu-id="37d9b-168">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="37d9b-168">Provider-specific</span></span>|<span data-ttu-id="37d9b-169">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="37d9b-169">Provider-specific</span></span>|<span data-ttu-id="37d9b-170">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="37d9b-170">Provider-specific</span></span>|<span data-ttu-id="37d9b-171">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="37d9b-171">Provider-specific</span></span>|<span data-ttu-id="37d9b-172">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="37d9b-172">Provider-specific</span></span>|<span data-ttu-id="37d9b-173">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="37d9b-173">Provider-specific</span></span>|<span data-ttu-id="37d9b-174">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="37d9b-174">Provider-specific</span></span>|  
|<span data-ttu-id="37d9b-175">Мультинабор</span><span class="sxs-lookup"><span data-stu-id="37d9b-175">Multiset</span></span>|<span data-ttu-id="37d9b-176">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-177">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-178">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-179">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-180">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-181">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-182">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="37d9b-183">Ссылочный</span><span class="sxs-lookup"><span data-stu-id="37d9b-183">Ref</span></span>|<span data-ttu-id="37d9b-184">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="37d9b-185">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="37d9b-186">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="37d9b-187">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="37d9b-188">Throw</span><span class="sxs-lookup"><span data-stu-id="37d9b-188">Throw</span></span>|<span data-ttu-id="37d9b-189">Throw</span><span class="sxs-lookup"><span data-stu-id="37d9b-189">Throw</span></span>|<span data-ttu-id="37d9b-190">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="37d9b-191">Ассоциация</span><span class="sxs-lookup"><span data-stu-id="37d9b-191">Association</span></span><br /><br /> <span data-ttu-id="37d9b-192">type</span><span class="sxs-lookup"><span data-stu-id="37d9b-192">type</span></span>|<span data-ttu-id="37d9b-193">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-194">Throw</span><span class="sxs-lookup"><span data-stu-id="37d9b-194">Throw</span></span>|<span data-ttu-id="37d9b-195">Throw</span><span class="sxs-lookup"><span data-stu-id="37d9b-195">Throw</span></span>|<span data-ttu-id="37d9b-196">Throw</span><span class="sxs-lookup"><span data-stu-id="37d9b-196">Throw</span></span>|<span data-ttu-id="37d9b-197">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-198">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="37d9b-199">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="37d9b-200"><sup>1</sup> Ссылки на заданные экземпляры типа сущности неявно сравниваются, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="37d9b-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="37d9b-201">Экземпляр сущности нельзя сравнивать с явной ссылкой.</span><span class="sxs-lookup"><span data-stu-id="37d9b-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="37d9b-202">При попытке такого сравнения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="37d9b-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="37d9b-203">Например, следующий запрос вызовет исключение:</span><span class="sxs-lookup"><span data-stu-id="37d9b-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="37d9b-204"><sup>2</sup> Свойства сложных типов выравниваются перед отправкой в хранилище, поэтому они становятся сравнимыми (при условии, что все их свойства сравнимы).</span><span class="sxs-lookup"><span data-stu-id="37d9b-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="37d9b-205">См <sup>. также 4.</sup></span><span class="sxs-lookup"><span data-stu-id="37d9b-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="37d9b-206"><sup>3</sup> Среда выполнения Entity Framework обнаруживает неподдерживаемый вариант и создает осмысленное исключение без привлечения поставщика или хранилища.</span><span class="sxs-lookup"><span data-stu-id="37d9b-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="37d9b-207"><sup>4</sup> Выполняется попытка сравнить все свойства.</span><span class="sxs-lookup"><span data-stu-id="37d9b-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="37d9b-208">Если имеется свойство несравнимого типа, например text, ntext или image, может возникнуть серверное исключение.</span><span class="sxs-lookup"><span data-stu-id="37d9b-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="37d9b-209"><sup>5</sup> Сравниваются все отдельные элементы ссылок (в том числе имя набора сущностей и все ключевые свойства типа сущности).</span><span class="sxs-lookup"><span data-stu-id="37d9b-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37d9b-210">См. также</span><span class="sxs-lookup"><span data-stu-id="37d9b-210">See also</span></span>

- [<span data-ttu-id="37d9b-211">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="37d9b-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
