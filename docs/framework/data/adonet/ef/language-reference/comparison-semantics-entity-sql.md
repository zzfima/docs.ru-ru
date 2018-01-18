---
title: "Семантика сравнения (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c6d22b72e05e6293a7fd3bcf7ddfba6e116e441f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="597db-102">Семантика сравнения (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="597db-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="597db-103">Выполнение любого следующего оператора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] подразумевает сравнение типов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="597db-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="597db-104">Явное сравнение</span><span class="sxs-lookup"><span data-stu-id="597db-104">Explicit comparison</span></span>  
 <span data-ttu-id="597db-105">Операции сравнения:</span><span class="sxs-lookup"><span data-stu-id="597db-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="597db-106">!=</span><span class="sxs-lookup"><span data-stu-id="597db-106">!=</span></span>  
  
 <span data-ttu-id="597db-107">Операции упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="597db-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 <span data-ttu-id="597db-108">Операции допустимости значений NULL:</span><span class="sxs-lookup"><span data-stu-id="597db-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="597db-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="597db-109">IS NULL</span></span>  
  
-   <span data-ttu-id="597db-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="597db-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="597db-111">Явное отличие</span><span class="sxs-lookup"><span data-stu-id="597db-111">Explicit distinction</span></span>  
 <span data-ttu-id="597db-112">Отличие равенства:</span><span class="sxs-lookup"><span data-stu-id="597db-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="597db-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="597db-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="597db-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="597db-114">GROUP BY</span></span>  
  
 <span data-ttu-id="597db-115">Отличие упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="597db-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="597db-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="597db-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="597db-117">Неявное отличие</span><span class="sxs-lookup"><span data-stu-id="597db-117">Implicit distinction</span></span>  
 <span data-ttu-id="597db-118">Операция и предикаты для работы с наборами (равенство):</span><span class="sxs-lookup"><span data-stu-id="597db-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="597db-119">UNION</span><span class="sxs-lookup"><span data-stu-id="597db-119">UNION</span></span>  
  
-   <span data-ttu-id="597db-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="597db-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="597db-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="597db-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="597db-122">SET</span><span class="sxs-lookup"><span data-stu-id="597db-122">SET</span></span>  
  
-   <span data-ttu-id="597db-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="597db-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="597db-124">Предикаты элементов (равенство):</span><span class="sxs-lookup"><span data-stu-id="597db-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="597db-125">IN</span><span class="sxs-lookup"><span data-stu-id="597db-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="597db-126">Поддерживаемые сочетания</span><span class="sxs-lookup"><span data-stu-id="597db-126">Supported Combinations</span></span>  
 <span data-ttu-id="597db-127">В следующей таблице приводятся все поддерживаемые сочетания операторов сравнения для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="597db-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="597db-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="597db-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="597db-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="597db-129">**!=**</span></span>|<span data-ttu-id="597db-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="597db-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="597db-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="597db-131">**DISTINCT**</span></span>|<span data-ttu-id="597db-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="597db-132">**UNION**</span></span><br /><br /> <span data-ttu-id="597db-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="597db-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="597db-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="597db-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="597db-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="597db-135">**SET**</span></span><br /><br /> <span data-ttu-id="597db-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="597db-136">**OVERLAPS**</span></span>|<span data-ttu-id="597db-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="597db-137">**IN**</span></span>|<span data-ttu-id="597db-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="597db-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="597db-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="597db-139">**>   >=**</span></span>|<span data-ttu-id="597db-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="597db-140">**ORDER BY**</span></span>|<span data-ttu-id="597db-141">**ИМЕЕТ ЗНАЧЕНИЕ NULL**</span><span class="sxs-lookup"><span data-stu-id="597db-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="597db-142">**НЕ ИМЕЕТ ЗНАЧЕНИЕ NULL**</span><span class="sxs-lookup"><span data-stu-id="597db-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="597db-143">Тип сущности</span><span class="sxs-lookup"><span data-stu-id="597db-143">Entity type</span></span>|<span data-ttu-id="597db-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="597db-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="597db-145">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="597db-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="597db-146">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="597db-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="597db-147">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="597db-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="597db-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="597db-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="597db-151">Сложный тип</span><span class="sxs-lookup"><span data-stu-id="597db-151">Complex type</span></span>|<span data-ttu-id="597db-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="597db-159">Строка</span><span class="sxs-lookup"><span data-stu-id="597db-159">Row</span></span>|<span data-ttu-id="597db-160">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="597db-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="597db-161">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="597db-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="597db-162">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="597db-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="597db-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-165">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="597db-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="597db-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="597db-167">Тип-примитив</span><span class="sxs-lookup"><span data-stu-id="597db-167">Primitive type</span></span>|<span data-ttu-id="597db-168">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="597db-168">Provider-specific</span></span>|<span data-ttu-id="597db-169">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="597db-169">Provider-specific</span></span>|<span data-ttu-id="597db-170">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="597db-170">Provider-specific</span></span>|<span data-ttu-id="597db-171">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="597db-171">Provider-specific</span></span>|<span data-ttu-id="597db-172">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="597db-172">Provider-specific</span></span>|<span data-ttu-id="597db-173">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="597db-173">Provider-specific</span></span>|<span data-ttu-id="597db-174">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="597db-174">Provider-specific</span></span>|  
|<span data-ttu-id="597db-175">Мультинабор</span><span class="sxs-lookup"><span data-stu-id="597db-175">Multiset</span></span>|<span data-ttu-id="597db-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="597db-183">Ссылочный</span><span class="sxs-lookup"><span data-stu-id="597db-183">Ref</span></span>|<span data-ttu-id="597db-184">Yes<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="597db-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="597db-185">Yes<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="597db-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="597db-186">Yes<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="597db-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="597db-187">Yes<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="597db-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="597db-188">Throw</span><span class="sxs-lookup"><span data-stu-id="597db-188">Throw</span></span>|<span data-ttu-id="597db-189">Throw</span><span class="sxs-lookup"><span data-stu-id="597db-189">Throw</span></span>|<span data-ttu-id="597db-190">Yes<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="597db-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="597db-191">Ассоциация</span><span class="sxs-lookup"><span data-stu-id="597db-191">Association</span></span><br /><br /> <span data-ttu-id="597db-192">type</span><span class="sxs-lookup"><span data-stu-id="597db-192">type</span></span>|<span data-ttu-id="597db-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-194">Throw</span><span class="sxs-lookup"><span data-stu-id="597db-194">Throw</span></span>|<span data-ttu-id="597db-195">Throw</span><span class="sxs-lookup"><span data-stu-id="597db-195">Throw</span></span>|<span data-ttu-id="597db-196">Throw</span><span class="sxs-lookup"><span data-stu-id="597db-196">Throw</span></span>|<span data-ttu-id="597db-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="597db-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="597db-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="597db-200"><sup>1</sup>ссылки на тип экземпляров данной сущности неявно сравниваются, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="597db-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="597db-201">Экземпляр сущности нельзя сравнивать с явной ссылкой.</span><span class="sxs-lookup"><span data-stu-id="597db-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="597db-202">При попытке такого сравнения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="597db-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="597db-203">Например, следующий запрос вызовет исключение:</span><span class="sxs-lookup"><span data-stu-id="597db-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="597db-204"><sup>2</sup>свойства сложных типов выравниваются перед его отправкой в хранилище, поэтому они станут сопоставимых (поскольку сравнимы их свойства).</span><span class="sxs-lookup"><span data-stu-id="597db-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="597db-205">См. также <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="597db-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="597db-206"><sup>3</sup>выполнения платформа Entity Framework обнаруживает неподдерживаемый вариант и вызывает значимое исключение, не вовлекая поставщик или хранилище.</span><span class="sxs-lookup"><span data-stu-id="597db-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="597db-207"><sup>4</sup>попытка сравнить все свойства.</span><span class="sxs-lookup"><span data-stu-id="597db-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="597db-208">Если имеется свойство несравнимого типа, например text, ntext или image, может возникнуть серверное исключение.</span><span class="sxs-lookup"><span data-stu-id="597db-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="597db-209"><sup>5</sup>сравниваются все отдельные элементы ссылок (включая имя набора сущностей и все ключевые свойства этого типа сущности).</span><span class="sxs-lookup"><span data-stu-id="597db-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="597db-210">См. также</span><span class="sxs-lookup"><span data-stu-id="597db-210">See Also</span></span>  
 [<span data-ttu-id="597db-211">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="597db-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
