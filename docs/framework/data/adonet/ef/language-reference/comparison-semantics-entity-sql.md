---
title: "Семантика сравнения (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e20d47e0ae97067d2dcafcf929f717598d4e3e80
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="0bc22-102">Семантика сравнения (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0bc22-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="0bc22-103">Выполнение любого следующего оператора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] подразумевает сравнение типов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="0bc22-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="0bc22-104">Явное сравнение</span><span class="sxs-lookup"><span data-stu-id="0bc22-104">Explicit comparison</span></span>  
 <span data-ttu-id="0bc22-105">Операции сравнения:</span><span class="sxs-lookup"><span data-stu-id="0bc22-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="0bc22-106">!=</span><span class="sxs-lookup"><span data-stu-id="0bc22-106">!=</span></span>  
  
 <span data-ttu-id="0bc22-107">Операции упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="0bc22-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="0bc22-108">Операции допустимости значений NULL:</span><span class="sxs-lookup"><span data-stu-id="0bc22-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="0bc22-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="0bc22-109">IS NULL</span></span>  
  
-   <span data-ttu-id="0bc22-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="0bc22-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="0bc22-111">Явное отличие</span><span class="sxs-lookup"><span data-stu-id="0bc22-111">Explicit distinction</span></span>  
 <span data-ttu-id="0bc22-112">Отличие равенства:</span><span class="sxs-lookup"><span data-stu-id="0bc22-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="0bc22-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="0bc22-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="0bc22-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="0bc22-114">GROUP BY</span></span>  
  
 <span data-ttu-id="0bc22-115">Отличие упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="0bc22-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="0bc22-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="0bc22-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="0bc22-117">Неявное отличие</span><span class="sxs-lookup"><span data-stu-id="0bc22-117">Implicit distinction</span></span>  
 <span data-ttu-id="0bc22-118">Операция и предикаты для работы с наборами (равенство):</span><span class="sxs-lookup"><span data-stu-id="0bc22-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="0bc22-119">UNION</span><span class="sxs-lookup"><span data-stu-id="0bc22-119">UNION</span></span>  
  
-   <span data-ttu-id="0bc22-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="0bc22-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="0bc22-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="0bc22-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="0bc22-122">SET</span><span class="sxs-lookup"><span data-stu-id="0bc22-122">SET</span></span>  
  
-   <span data-ttu-id="0bc22-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="0bc22-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="0bc22-124">Предикаты элементов (равенство):</span><span class="sxs-lookup"><span data-stu-id="0bc22-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="0bc22-125">IN</span><span class="sxs-lookup"><span data-stu-id="0bc22-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="0bc22-126">Поддерживаемые сочетания</span><span class="sxs-lookup"><span data-stu-id="0bc22-126">Supported Combinations</span></span>  
 <span data-ttu-id="0bc22-127">В следующей таблице приводятся все поддерживаемые сочетания операторов сравнения для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="0bc22-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="0bc22-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="0bc22-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="0bc22-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="0bc22-129">**!=**</span></span>|<span data-ttu-id="0bc22-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="0bc22-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="0bc22-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="0bc22-131">**DISTINCT**</span></span>|<span data-ttu-id="0bc22-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="0bc22-132">**UNION**</span></span><br /><br /> <span data-ttu-id="0bc22-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="0bc22-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="0bc22-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="0bc22-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="0bc22-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="0bc22-135">**SET**</span></span><br /><br /> <span data-ttu-id="0bc22-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="0bc22-136">**OVERLAPS**</span></span>|<span data-ttu-id="0bc22-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="0bc22-137">**IN**</span></span>|<span data-ttu-id="0bc22-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="0bc22-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="0bc22-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="0bc22-139">**>   >=**</span></span>|<span data-ttu-id="0bc22-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="0bc22-140">**ORDER BY**</span></span>|<span data-ttu-id="0bc22-141">**ИМЕЕТ ЗНАЧЕНИЕ NULL**</span><span class="sxs-lookup"><span data-stu-id="0bc22-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="0bc22-142">**НЕ ИМЕЕТ ЗНАЧЕНИЕ NULL**</span><span class="sxs-lookup"><span data-stu-id="0bc22-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="0bc22-143">Тип сущности</span><span class="sxs-lookup"><span data-stu-id="0bc22-143">Entity type</span></span>|<span data-ttu-id="0bc22-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="0bc22-145">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="0bc22-146">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="0bc22-147">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="0bc22-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="0bc22-151">Сложный тип</span><span class="sxs-lookup"><span data-stu-id="0bc22-151">Complex type</span></span>|<span data-ttu-id="0bc22-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="0bc22-159">Строка</span><span class="sxs-lookup"><span data-stu-id="0bc22-159">Row</span></span>|<span data-ttu-id="0bc22-160">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="0bc22-161">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="0bc22-162">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="0bc22-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-165">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="0bc22-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="0bc22-167">Тип-примитив</span><span class="sxs-lookup"><span data-stu-id="0bc22-167">Primitive type</span></span>|<span data-ttu-id="0bc22-168">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="0bc22-168">Provider-specific</span></span>|<span data-ttu-id="0bc22-169">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="0bc22-169">Provider-specific</span></span>|<span data-ttu-id="0bc22-170">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="0bc22-170">Provider-specific</span></span>|<span data-ttu-id="0bc22-171">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="0bc22-171">Provider-specific</span></span>|<span data-ttu-id="0bc22-172">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="0bc22-172">Provider-specific</span></span>|<span data-ttu-id="0bc22-173">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="0bc22-173">Provider-specific</span></span>|<span data-ttu-id="0bc22-174">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="0bc22-174">Provider-specific</span></span>|  
|<span data-ttu-id="0bc22-175">Мультинабор</span><span class="sxs-lookup"><span data-stu-id="0bc22-175">Multiset</span></span>|<span data-ttu-id="0bc22-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="0bc22-183">Ссылочный</span><span class="sxs-lookup"><span data-stu-id="0bc22-183">Ref</span></span>|<span data-ttu-id="0bc22-184">Yes<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="0bc22-185">Yes<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="0bc22-186">Yes<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="0bc22-187">Yes<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="0bc22-188">Throw</span><span class="sxs-lookup"><span data-stu-id="0bc22-188">Throw</span></span>|<span data-ttu-id="0bc22-189">Throw</span><span class="sxs-lookup"><span data-stu-id="0bc22-189">Throw</span></span>|<span data-ttu-id="0bc22-190">Yes<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="0bc22-191">Ассоциация</span><span class="sxs-lookup"><span data-stu-id="0bc22-191">Association</span></span><br /><br /> <span data-ttu-id="0bc22-192">type</span><span class="sxs-lookup"><span data-stu-id="0bc22-192">type</span></span>|<span data-ttu-id="0bc22-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-194">Throw</span><span class="sxs-lookup"><span data-stu-id="0bc22-194">Throw</span></span>|<span data-ttu-id="0bc22-195">Throw</span><span class="sxs-lookup"><span data-stu-id="0bc22-195">Throw</span></span>|<span data-ttu-id="0bc22-196">Throw</span><span class="sxs-lookup"><span data-stu-id="0bc22-196">Throw</span></span>|<span data-ttu-id="0bc22-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="0bc22-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="0bc22-200"><sup>1</sup>ссылки на тип экземпляров данной сущности неявно сравниваются, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0bc22-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="0bc22-201">Экземпляр сущности нельзя сравнивать с явной ссылкой.</span><span class="sxs-lookup"><span data-stu-id="0bc22-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="0bc22-202">При попытке такого сравнения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="0bc22-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="0bc22-203">Например, следующий запрос вызовет исключение:</span><span class="sxs-lookup"><span data-stu-id="0bc22-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="0bc22-204"><sup>2</sup>свойства сложных типов выравниваются перед его отправкой в хранилище, поэтому они станут сопоставимых (поскольку сравнимы их свойства).</span><span class="sxs-lookup"><span data-stu-id="0bc22-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="0bc22-205">См. также <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="0bc22-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="0bc22-206"><sup>3</sup>выполнения платформа Entity Framework обнаруживает неподдерживаемый вариант и вызывает значимое исключение, не вовлекая поставщик или хранилище.</span><span class="sxs-lookup"><span data-stu-id="0bc22-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="0bc22-207"><sup>4</sup>попытка сравнить все свойства.</span><span class="sxs-lookup"><span data-stu-id="0bc22-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="0bc22-208">Если имеется свойство несравнимого типа, например text, ntext или image, может возникнуть серверное исключение.</span><span class="sxs-lookup"><span data-stu-id="0bc22-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="0bc22-209"><sup>5</sup>сравниваются все отдельные элементы ссылок (включая имя набора сущностей и все ключевые свойства этого типа сущности).</span><span class="sxs-lookup"><span data-stu-id="0bc22-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc22-210">См. также</span><span class="sxs-lookup"><span data-stu-id="0bc22-210">See Also</span></span>  
 [<span data-ttu-id="0bc22-211">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0bc22-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
