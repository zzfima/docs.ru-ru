---
title: "Группировка результатов запросов"
description: "Сведения о группировке результатов."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.openlocfilehash: ca68cf96a2c27bbd1999d5445c14fc93e8e2566c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="group-query-results"></a><span data-ttu-id="cc140-104">Группировка результатов запросов</span><span class="sxs-lookup"><span data-stu-id="cc140-104">Group query results</span></span>

<span data-ttu-id="cc140-105">Группирование — одна из самых эффективных функций LINQ.</span><span class="sxs-lookup"><span data-stu-id="cc140-105">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="cc140-106">В приведенных ниже примерах демонстрируются различные способы группирования данных:</span><span class="sxs-lookup"><span data-stu-id="cc140-106">The following examples show how to group data in various ways:</span></span>  
  
-   <span data-ttu-id="cc140-107">по отдельному свойству;</span><span class="sxs-lookup"><span data-stu-id="cc140-107">By a single property.</span></span>  
  
-   <span data-ttu-id="cc140-108">по первой букве строкового свойства;</span><span class="sxs-lookup"><span data-stu-id="cc140-108">By the first letter of a string property.</span></span>  
  
-   <span data-ttu-id="cc140-109">по расчетному числовому диапазону;</span><span class="sxs-lookup"><span data-stu-id="cc140-109">By a computed numeric range.</span></span>  
  
-   <span data-ttu-id="cc140-110">по логическому предикату или другому выражению;</span><span class="sxs-lookup"><span data-stu-id="cc140-110">By Boolean predicate or other expression.</span></span>  
  
-   <span data-ttu-id="cc140-111">по составному ключу.</span><span class="sxs-lookup"><span data-stu-id="cc140-111">By a compound key.</span></span>  
  
 <span data-ttu-id="cc140-112">Кроме того, два последних запроса передают свои результаты в новый анонимный тип, содержащий только имя и фамилию студента.</span><span class="sxs-lookup"><span data-stu-id="cc140-112">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="cc140-113">Дополнительные сведения см. в разделе [Предложение group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="cc140-113">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc140-114">Пример</span><span class="sxs-lookup"><span data-stu-id="cc140-114">Example</span></span>  
 <span data-ttu-id="cc140-115">Во всех примерах в этом разделе используются указанные ниже вспомогательные классы и источники данных.</span><span class="sxs-lookup"><span data-stu-id="cc140-115">All the examples in this topic use the following helper classes and data sources.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="cc140-116">Пример</span><span class="sxs-lookup"><span data-stu-id="cc140-116">Example</span></span>  
 <span data-ttu-id="cc140-117">В этом примере показана группировка элементов источника с помощью отдельного свойства элемента в качестве ключа группы.</span><span class="sxs-lookup"><span data-stu-id="cc140-117">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="cc140-118">В данном случае в качестве ключа используется `string`, фамилия учащегося.</span><span class="sxs-lookup"><span data-stu-id="cc140-118">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="cc140-119">Для ключа можно также использовать подстроку.</span><span class="sxs-lookup"><span data-stu-id="cc140-119">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="cc140-120">При операции группирования используется компаратор проверки на равенство, используемый по умолчанию для данного типа.</span><span class="sxs-lookup"><span data-stu-id="cc140-120">The grouping operation uses the default equality comparer for the type.</span></span>  
  
 <span data-ttu-id="cc140-121">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="cc140-121">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="cc140-122">Измените оператор вызова в методе `Main` на `sc.GroupBySingleProperty()`.</span><span class="sxs-lookup"><span data-stu-id="cc140-122">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="cc140-123">Пример</span><span class="sxs-lookup"><span data-stu-id="cc140-123">Example</span></span>  
 <span data-ttu-id="cc140-124">В этом примере показана группировка элементов источника, когда в качестве ключа группы используется не свойство объекта.</span><span class="sxs-lookup"><span data-stu-id="cc140-124">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="cc140-125">В данном случае в качестве ключа используется первая буква фамилии учащегося.</span><span class="sxs-lookup"><span data-stu-id="cc140-125">In this example, the key is the first letter of the student's last name.</span></span>  
  
 <span data-ttu-id="cc140-126">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="cc140-126">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="cc140-127">Измените оператор вызова в методе `Main` на `sc.GroupBySubstring()`.</span><span class="sxs-lookup"><span data-stu-id="cc140-127">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="cc140-128">Пример</span><span class="sxs-lookup"><span data-stu-id="cc140-128">Example</span></span>  
 <span data-ttu-id="cc140-129">В этом примере показана группировка элементов источника путем использования числового диапазона в качестве ключа группы.</span><span class="sxs-lookup"><span data-stu-id="cc140-129">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="cc140-130">Затем запрос передает результаты в анонимный тип, содержащий только имя и фамилию, а также диапазон процентилей, к которому принадлежит студент.</span><span class="sxs-lookup"><span data-stu-id="cc140-130">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="cc140-131">Использование анонимного типа объясняется тем, что для отображения результатов не требуется использовать полный объект `Student`.</span><span class="sxs-lookup"><span data-stu-id="cc140-131">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="cc140-132">`GetPercentile` — это вспомогательная функция, которая вычисляет процент на основе средних результатов учащегося.</span><span class="sxs-lookup"><span data-stu-id="cc140-132">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="cc140-133">Метод возвращает целое число в диапазоне от 0 до 10.</span><span class="sxs-lookup"><span data-stu-id="cc140-133">The method returns an integer between 0 and 10.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]  
  
 <span data-ttu-id="cc140-134">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="cc140-134">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="cc140-135">Измените оператор вызова в методе `Main` на `sc.GroupByRange()`.</span><span class="sxs-lookup"><span data-stu-id="cc140-135">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]  
  
## <a name="example"></a><span data-ttu-id="cc140-136">Пример</span><span class="sxs-lookup"><span data-stu-id="cc140-136">Example</span></span>  
 <span data-ttu-id="cc140-137">В этом примере показана группировка элементов источника с помощью выражения логического сравнения.</span><span class="sxs-lookup"><span data-stu-id="cc140-137">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="cc140-138">В этом случае логическое выражение проверяет, превосходит ли среднее значение экзаменационного результата учащегося 75 баллов.</span><span class="sxs-lookup"><span data-stu-id="cc140-138">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="cc140-139">Как и в предыдущих примерах, результаты передаются в анонимный тип, так как весь элемент источника не требуется.</span><span class="sxs-lookup"><span data-stu-id="cc140-139">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="cc140-140">Обратите внимание на то, что свойства в анонимном типе становятся свойствами в члене `Key`, а при выполнении запроса доступ к ним можно получить по имени.</span><span class="sxs-lookup"><span data-stu-id="cc140-140">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>  
  
 <span data-ttu-id="cc140-141">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="cc140-141">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="cc140-142">Измените оператор вызова в методе `Main` на `sc.GroupByBoolean()`.</span><span class="sxs-lookup"><span data-stu-id="cc140-142">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]  
  
## <a name="example"></a><span data-ttu-id="cc140-143">Пример</span><span class="sxs-lookup"><span data-stu-id="cc140-143">Example</span></span>  
 <span data-ttu-id="cc140-144">В этом примере показано, как использовать анонимный тип для инкапсуляции ключа, содержащего несколько значений.</span><span class="sxs-lookup"><span data-stu-id="cc140-144">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="cc140-145">В данном случае в качестве первого значения ключа используется первая буква фамилии учащегося.</span><span class="sxs-lookup"><span data-stu-id="cc140-145">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="cc140-146">Второе значение ключа является логическим и указывает, набрал ли учащийся более 85 баллов на первом экзамене.</span><span class="sxs-lookup"><span data-stu-id="cc140-146">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="cc140-147">Группы можно сортировать по любому из свойств в ключе.</span><span class="sxs-lookup"><span data-stu-id="cc140-147">You can order the groups by any property in the key.</span></span>  
  
 <span data-ttu-id="cc140-148">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="cc140-148">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="cc140-149">Измените оператор вызова в методе `Main` на `sc.GroupByCompositeKey()`.</span><span class="sxs-lookup"><span data-stu-id="cc140-149">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="cc140-150">См. также</span><span class="sxs-lookup"><span data-stu-id="cc140-150">See also</span></span>  
 <xref:System.Linq.Enumerable.GroupBy%2A>  
 <xref:System.Linq.IGrouping%602>  
 [<span data-ttu-id="cc140-151">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="cc140-151">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="cc140-152">предложение group</span><span class="sxs-lookup"><span data-stu-id="cc140-152">group clause</span></span>](../language-reference/keywords/group-clause.md)  
 [<span data-ttu-id="cc140-153">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="cc140-153">Anonymous Types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="cc140-154">Выполнить вложенный запрос в операции группирования</span><span class="sxs-lookup"><span data-stu-id="cc140-154">Perform a Subquery on a Grouping Operation</span></span>](perform-a-subquery-on-a-grouping-operation.md)  
 [<span data-ttu-id="cc140-155">Создание вложенной группы</span><span class="sxs-lookup"><span data-stu-id="cc140-155">Create a Nested Group</span></span>](create-a-nested-group.md)  
 [<span data-ttu-id="cc140-156">Группировка данных</span><span class="sxs-lookup"><span data-stu-id="cc140-156">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)
