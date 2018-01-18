---
title: "Примеры запросов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1b3aabf5a47088fa408547527c5f18fa69a48e02
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="query-examples"></a><span data-ttu-id="02076-102">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="02076-102">Query Examples</span></span>
<span data-ttu-id="02076-103">В этом разделе представлен ряд примеров [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] и C# стандартных запросов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02076-103">This section provides [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="02076-104">Разработчики, использующие [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], могут просмотреть гораздо больше примеров в образце решения, представленном в разделе "Образцы".</span><span class="sxs-lookup"><span data-stu-id="02076-104">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="02076-105">Дополнительные сведения см. в разделе [образцы](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span><span class="sxs-lookup"><span data-stu-id="02076-105">For more information, see [Samples](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="02076-106">*DB* часто используется в примерах кода в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] документации.</span><span class="sxs-lookup"><span data-stu-id="02076-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="02076-107">*DB* считается экземпляр *Northwind* класс, унаследованный от класса <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="02076-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02076-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="02076-108">In This Section</span></span>  
 [<span data-ttu-id="02076-109">Статистические запросы</span><span class="sxs-lookup"><span data-stu-id="02076-109">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <span data-ttu-id="02076-110">Содержит описание использования <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A> и т. д.</span><span class="sxs-lookup"><span data-stu-id="02076-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="02076-111">Возврат первого элемента в последовательности</span><span class="sxs-lookup"><span data-stu-id="02076-111">Return the First Element in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="02076-112">Содержит примеры использования <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="02076-113">Возврат или пропуск элементов последовательности</span><span class="sxs-lookup"><span data-stu-id="02076-113">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="02076-114">Содержит примеры использования <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="02076-115">Сортировка элементов последовательности</span><span class="sxs-lookup"><span data-stu-id="02076-115">Sort Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <span data-ttu-id="02076-116">Содержит примеры использования <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="02076-117">Группировка элементов последовательности</span><span class="sxs-lookup"><span data-stu-id="02076-117">Group Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <span data-ttu-id="02076-118">Содержит примеры использования <xref:System.Linq.Enumerable.GroupBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="02076-119">Удаление дубликатов элементов из последовательности</span><span class="sxs-lookup"><span data-stu-id="02076-119">Eliminate Duplicate Elements from a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="02076-120">Содержит примеры использования <xref:System.Linq.Enumerable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="02076-121">Проверка соответствия условию какого-либо или всех элементов</span><span class="sxs-lookup"><span data-stu-id="02076-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="02076-122">Содержит примеры использования <xref:System.Linq.Enumerable.All%2A> и <xref:System.Linq.Enumerable.Any%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="02076-123">Сцепление двух последовательностей</span><span class="sxs-lookup"><span data-stu-id="02076-123">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 <span data-ttu-id="02076-124">Содержит примеры использования <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="02076-125">Возврат разности наборов между двумя последовательностями</span><span class="sxs-lookup"><span data-stu-id="02076-125">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="02076-126">Содержит примеры использования <xref:System.Linq.Enumerable.Except%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="02076-127">Возврат пересечения наборов двух последовательностей</span><span class="sxs-lookup"><span data-stu-id="02076-127">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="02076-128">Содержит примеры использования <xref:System.Linq.Enumerable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="02076-129">Возврат объединения наборов двух последовательностей</span><span class="sxs-lookup"><span data-stu-id="02076-129">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="02076-130">Содержит примеры использования <xref:System.Linq.Enumerable.Union%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="02076-131">Преобразование последовательности в массив</span><span class="sxs-lookup"><span data-stu-id="02076-131">Convert a Sequence to an Array</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="02076-132">Содержит примеры использования <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="02076-133">Преобразование последовательности в универсальный список</span><span class="sxs-lookup"><span data-stu-id="02076-133">Convert a Sequence to a Generic List</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="02076-134">Содержит примеры использования <xref:System.Linq.Enumerable.ToList%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="02076-135">Преобразование типа в универсальный интерфейс IEnumerable</span><span class="sxs-lookup"><span data-stu-id="02076-135">Convert a Type to a Generic IEnumerable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="02076-136">Содержит примеры использования <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="02076-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="02076-137">Формулировка запросов-объединений и запросов векторного произведения</span><span class="sxs-lookup"><span data-stu-id="02076-137">Formulate Joins and Cross-Product Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="02076-138">Содержит примеры использования переходов внешнего ключа в предложениях `from`, `where` и `select`.</span><span class="sxs-lookup"><span data-stu-id="02076-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="02076-139">Формулировка проекций</span><span class="sxs-lookup"><span data-stu-id="02076-139">Formulate Projections</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 <span data-ttu-id="02076-140">Содержит примеры сочетания `select` с другими возможностями (например, *анонимные типы*) для создания проекций запросов.</span><span class="sxs-lookup"><span data-stu-id="02076-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="02076-141">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="02076-141">Related Sections</span></span>  
 [<span data-ttu-id="02076-142">Общие сведения о стандартных операторах запроса</span><span class="sxs-lookup"><span data-stu-id="02076-142">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 <span data-ttu-id="02076-143">Содержит основные сведения о стандартных операторах запроса.</span><span class="sxs-lookup"><span data-stu-id="02076-143">Explains the concept of standard query operators.</span></span>  
  
 [<span data-ttu-id="02076-144">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="02076-144">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="02076-145">Содержит описание использования [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] принципов, применимых к запросам.</span><span class="sxs-lookup"><span data-stu-id="02076-145">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="02076-146">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="02076-146">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="02076-147">Предоставляет портал для тем, в которых объясняются принципы программирования, связанные с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02076-147">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
