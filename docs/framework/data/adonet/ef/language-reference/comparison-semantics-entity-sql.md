---
title: Семантика сравнения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 57d81d4b581df76a4382ad5e1d72fe8250b10d43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150458"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="8ee0f-102">Семантика сравнения (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8ee0f-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="8ee0f-103">Выполнение любого следующего оператора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] подразумевает сравнение типов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="8ee0f-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="8ee0f-104">Явное сравнение</span><span class="sxs-lookup"><span data-stu-id="8ee0f-104">Explicit comparison</span></span>  
 <span data-ttu-id="8ee0f-105">Операции сравнения:</span><span class="sxs-lookup"><span data-stu-id="8ee0f-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="8ee0f-106">!=</span><span class="sxs-lookup"><span data-stu-id="8ee0f-106">!=</span></span>  
  
 <span data-ttu-id="8ee0f-107">Операции упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="8ee0f-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="8ee0f-108">Операции допустимости значений NULL:</span><span class="sxs-lookup"><span data-stu-id="8ee0f-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="8ee0f-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="8ee0f-109">IS NULL</span></span>  
  
- <span data-ttu-id="8ee0f-110">IS NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="8ee0f-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="8ee0f-111">Явное отличие</span><span class="sxs-lookup"><span data-stu-id="8ee0f-111">Explicit distinction</span></span>  
 <span data-ttu-id="8ee0f-112">Отличие равенства:</span><span class="sxs-lookup"><span data-stu-id="8ee0f-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="8ee0f-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="8ee0f-113">DISTINCT</span></span>  
  
- <span data-ttu-id="8ee0f-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="8ee0f-114">GROUP BY</span></span>  
  
 <span data-ttu-id="8ee0f-115">Отличие упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="8ee0f-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="8ee0f-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="8ee0f-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="8ee0f-117">Неявное отличие</span><span class="sxs-lookup"><span data-stu-id="8ee0f-117">Implicit distinction</span></span>  
 <span data-ttu-id="8ee0f-118">Операция и предикаты для работы с наборами (равенство):</span><span class="sxs-lookup"><span data-stu-id="8ee0f-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="8ee0f-119">UNION</span><span class="sxs-lookup"><span data-stu-id="8ee0f-119">UNION</span></span>  
  
- <span data-ttu-id="8ee0f-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="8ee0f-120">INTERSECT</span></span>  
  
- <span data-ttu-id="8ee0f-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="8ee0f-121">EXCEPT</span></span>  
  
- <span data-ttu-id="8ee0f-122">SET</span><span class="sxs-lookup"><span data-stu-id="8ee0f-122">SET</span></span>  
  
- <span data-ttu-id="8ee0f-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="8ee0f-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="8ee0f-124">Предикаты элементов (равенство):</span><span class="sxs-lookup"><span data-stu-id="8ee0f-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="8ee0f-125">IN</span><span class="sxs-lookup"><span data-stu-id="8ee0f-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="8ee0f-126">Поддерживаемые сочетания</span><span class="sxs-lookup"><span data-stu-id="8ee0f-126">Supported Combinations</span></span>  
 <span data-ttu-id="8ee0f-127">В следующей таблице приводятся все поддерживаемые сочетания операторов сравнения для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="8ee0f-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="8ee0f-128">**Тип**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="8ee0f-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-129">**!=**</span></span>|<span data-ttu-id="8ee0f-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="8ee0f-131">**Различных**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-131">**DISTINCT**</span></span>|<span data-ttu-id="8ee0f-132">**Союза**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-132">**UNION**</span></span><br /><br /> <span data-ttu-id="8ee0f-133">**Пересекаются**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="8ee0f-134">**Кроме**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="8ee0f-135">**Установить**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-135">**SET**</span></span><br /><br /> <span data-ttu-id="8ee0f-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-136">**OVERLAPS**</span></span>|<span data-ttu-id="8ee0f-137">**В**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-137">**IN**</span></span>|<span data-ttu-id="8ee0f-138">**< <**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="8ee0f-139">**> >**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-139">**>   >=**</span></span>|<span data-ttu-id="8ee0f-140">**ЗАКАЗ BY**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-140">**ORDER BY**</span></span>|<span data-ttu-id="8ee0f-141">**ЯВЛЯЕТСЯ НЕДЕЙСТВИТЕЛЬНЫМ**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="8ee0f-142">**НЕ ЯВЛЯЕТСЯ НЕДЕЙСТВИТЕЛЬНЫМ**</span><span class="sxs-lookup"><span data-stu-id="8ee0f-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="8ee0f-143">Тип сущности</span><span class="sxs-lookup"><span data-stu-id="8ee0f-143">Entity type</span></span>|<span data-ttu-id="8ee0f-144">Рефери<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="8ee0f-145">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="8ee0f-146">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="8ee0f-147">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="8ee0f-148">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-149">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-150">Рефери<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="8ee0f-151">Сложный тип</span><span class="sxs-lookup"><span data-stu-id="8ee0f-151">Complex type</span></span>|<span data-ttu-id="8ee0f-152">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-153">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-154">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-155">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-156">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-157">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-158">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="8ee0f-159">Строка</span><span class="sxs-lookup"><span data-stu-id="8ee0f-159">Row</span></span>|<span data-ttu-id="8ee0f-160">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="8ee0f-161">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="8ee0f-162">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="8ee0f-163">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-164">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-165">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="8ee0f-166">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="8ee0f-167">Тип-примитив</span><span class="sxs-lookup"><span data-stu-id="8ee0f-167">Primitive type</span></span>|<span data-ttu-id="8ee0f-168">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="8ee0f-168">Provider-specific</span></span>|<span data-ttu-id="8ee0f-169">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="8ee0f-169">Provider-specific</span></span>|<span data-ttu-id="8ee0f-170">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="8ee0f-170">Provider-specific</span></span>|<span data-ttu-id="8ee0f-171">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="8ee0f-171">Provider-specific</span></span>|<span data-ttu-id="8ee0f-172">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="8ee0f-172">Provider-specific</span></span>|<span data-ttu-id="8ee0f-173">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="8ee0f-173">Provider-specific</span></span>|<span data-ttu-id="8ee0f-174">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="8ee0f-174">Provider-specific</span></span>|  
|<span data-ttu-id="8ee0f-175">Мультинабор</span><span class="sxs-lookup"><span data-stu-id="8ee0f-175">Multiset</span></span>|<span data-ttu-id="8ee0f-176">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-177">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-178">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-179">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-180">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-181">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-182">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="8ee0f-183">Ссылочный</span><span class="sxs-lookup"><span data-stu-id="8ee0f-183">Ref</span></span>|<span data-ttu-id="8ee0f-184">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="8ee0f-185">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="8ee0f-186">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="8ee0f-187">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="8ee0f-188">Throw</span><span class="sxs-lookup"><span data-stu-id="8ee0f-188">Throw</span></span>|<span data-ttu-id="8ee0f-189">Throw</span><span class="sxs-lookup"><span data-stu-id="8ee0f-189">Throw</span></span>|<span data-ttu-id="8ee0f-190">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="8ee0f-191">Взаимосвязь</span><span class="sxs-lookup"><span data-stu-id="8ee0f-191">Association</span></span><br /><br /> <span data-ttu-id="8ee0f-192">type</span><span class="sxs-lookup"><span data-stu-id="8ee0f-192">type</span></span>|<span data-ttu-id="8ee0f-193">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-194">Throw</span><span class="sxs-lookup"><span data-stu-id="8ee0f-194">Throw</span></span>|<span data-ttu-id="8ee0f-195">Throw</span><span class="sxs-lookup"><span data-stu-id="8ee0f-195">Throw</span></span>|<span data-ttu-id="8ee0f-196">Throw</span><span class="sxs-lookup"><span data-stu-id="8ee0f-196">Throw</span></span>|<span data-ttu-id="8ee0f-197">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-198">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="8ee0f-199">Бросок<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="8ee0f-200"><sup>1</sup> Ссылки на экземпляры данного типа сущности неявно сравниваются, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8ee0f-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="8ee0f-201">Экземпляр сущности нельзя сравнивать с явной ссылкой.</span><span class="sxs-lookup"><span data-stu-id="8ee0f-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="8ee0f-202">При попытке такого сравнения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="8ee0f-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="8ee0f-203">Например, следующий запрос вызовет исключение:</span><span class="sxs-lookup"><span data-stu-id="8ee0f-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="8ee0f-204"><sup>2</sup> Свойства сложных типов сплющиваются перед отправкой в магазин, поэтому они становятся сопоставимыми (пока все их свойства сопоставимы).</span><span class="sxs-lookup"><span data-stu-id="8ee0f-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="8ee0f-205">Также <sup>см. 4.</sup></span><span class="sxs-lookup"><span data-stu-id="8ee0f-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="8ee0f-206"><sup>3</sup> Время выполнения системы entity Framework обнаруживает неподдерживаемый случай и выбрасывает значимое исключение без привлечения поставщика/магазина.</span><span class="sxs-lookup"><span data-stu-id="8ee0f-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="8ee0f-207"><sup>4</sup> Предпринимается попытка сравнить все свойства.</span><span class="sxs-lookup"><span data-stu-id="8ee0f-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="8ee0f-208">Если имеется свойство несравнимого типа, например text, ntext или image, может возникнуть серверное исключение.</span><span class="sxs-lookup"><span data-stu-id="8ee0f-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="8ee0f-209"><sup>5</sup> Сравниваются все отдельные элементы ссылок (в него входит имя набора сущности и все ключевые свойства типа сущности).</span><span class="sxs-lookup"><span data-stu-id="8ee0f-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee0f-210">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8ee0f-210">See also</span></span>

- [<span data-ttu-id="8ee0f-211">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8ee0f-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
