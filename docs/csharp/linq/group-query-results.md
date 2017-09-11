---
title: "Группировка результатов запросов"
description: "Сведения о группировке результатов."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1c1639651699afbe5fb768db26b98a9b2d734315
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="group-query-results"></a><span data-ttu-id="3255b-104">Группировка результатов запросов</span><span class="sxs-lookup"><span data-stu-id="3255b-104">Group query results</span></span>

<span data-ttu-id="3255b-105">Группирование — одна из самых эффективных функций LINQ.</span><span class="sxs-lookup"><span data-stu-id="3255b-105">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="3255b-106">В приведенных ниже примерах демонстрируются различные способы группирования данных:</span><span class="sxs-lookup"><span data-stu-id="3255b-106">The following examples show how to group data in various ways:</span></span>  
  
-   <span data-ttu-id="3255b-107">по отдельному свойству;</span><span class="sxs-lookup"><span data-stu-id="3255b-107">By a single property.</span></span>  
  
-   <span data-ttu-id="3255b-108">по первой букве строкового свойства;</span><span class="sxs-lookup"><span data-stu-id="3255b-108">By the first letter of a string property.</span></span>  
  
-   <span data-ttu-id="3255b-109">по расчетному числовому диапазону;</span><span class="sxs-lookup"><span data-stu-id="3255b-109">By a computed numeric range.</span></span>  
  
-   <span data-ttu-id="3255b-110">по логическому предикату или другому выражению;</span><span class="sxs-lookup"><span data-stu-id="3255b-110">By Boolean predicate or other expression.</span></span>  
  
-   <span data-ttu-id="3255b-111">по составному ключу.</span><span class="sxs-lookup"><span data-stu-id="3255b-111">By a compound key.</span></span>  
  
 <span data-ttu-id="3255b-112">Кроме того, два последних запроса передают свои результаты в новый анонимный тип, содержащий только имя и фамилию студента.</span><span class="sxs-lookup"><span data-stu-id="3255b-112">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="3255b-113">Дополнительные сведения см. в разделе [Предложение group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3255b-113">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3255b-114">Пример</span><span class="sxs-lookup"><span data-stu-id="3255b-114">Example</span></span>  
 <span data-ttu-id="3255b-115">Во всех примерах в этом разделе используются указанные ниже вспомогательные классы и источники данных.</span><span class="sxs-lookup"><span data-stu-id="3255b-115">All the examples in this topic use the following helper classes and data sources.</span></span>  
  
 <span data-ttu-id="3255b-116">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3255b-116">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3255b-117">Пример</span><span class="sxs-lookup"><span data-stu-id="3255b-117">Example</span></span>  
 <span data-ttu-id="3255b-118">В этом примере показана группировка элементов источника с помощью отдельного свойства элемента в качестве ключа группы.</span><span class="sxs-lookup"><span data-stu-id="3255b-118">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="3255b-119">В данном случае в качестве ключа используется `string`, фамилия учащегося.</span><span class="sxs-lookup"><span data-stu-id="3255b-119">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="3255b-120">Для ключа можно также использовать подстроку.</span><span class="sxs-lookup"><span data-stu-id="3255b-120">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="3255b-121">При операции группирования используется компаратор проверки на равенство, используемый по умолчанию для данного типа.</span><span class="sxs-lookup"><span data-stu-id="3255b-121">The grouping operation uses the default equality comparer for the type.</span></span>  
  
 <span data-ttu-id="3255b-122">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="3255b-122">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="3255b-123">Измените оператор вызова в методе `Main` на `sc.GroupBySingleProperty()`.</span><span class="sxs-lookup"><span data-stu-id="3255b-123">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>  
  
 <span data-ttu-id="3255b-124">[!code-cs[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3255b-124">[!code-cs[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3255b-125">Пример</span><span class="sxs-lookup"><span data-stu-id="3255b-125">Example</span></span>  
 <span data-ttu-id="3255b-126">В этом примере показана группировка элементов источника, когда в качестве ключа группы используется не свойство объекта.</span><span class="sxs-lookup"><span data-stu-id="3255b-126">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="3255b-127">В данном случае в качестве ключа используется первая буква фамилии учащегося.</span><span class="sxs-lookup"><span data-stu-id="3255b-127">In this example, the key is the first letter of the student's last name.</span></span>  
  
 <span data-ttu-id="3255b-128">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="3255b-128">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="3255b-129">Измените оператор вызова в методе `Main` на `sc.GroupBySubstring()`.</span><span class="sxs-lookup"><span data-stu-id="3255b-129">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>  
  
 <span data-ttu-id="3255b-130">[!code-cs[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="3255b-130">[!code-cs[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3255b-131">Пример</span><span class="sxs-lookup"><span data-stu-id="3255b-131">Example</span></span>  
 <span data-ttu-id="3255b-132">В этом примере показана группировка элементов источника путем использования числового диапазона в качестве ключа группы.</span><span class="sxs-lookup"><span data-stu-id="3255b-132">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="3255b-133">Затем запрос передает результаты в анонимный тип, содержащий только имя и фамилию, а также диапазон процентилей, к которому принадлежит студент.</span><span class="sxs-lookup"><span data-stu-id="3255b-133">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="3255b-134">Использование анонимного типа объясняется тем, что для отображения результатов не требуется использовать полный объект `Student`.</span><span class="sxs-lookup"><span data-stu-id="3255b-134">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="3255b-135">`GetPercentile` — это вспомогательная функция, которая вычисляет процент на основе средних результатов учащегося.</span><span class="sxs-lookup"><span data-stu-id="3255b-135">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="3255b-136">Метод возвращает целое число в диапазоне от 0 до 10.</span><span class="sxs-lookup"><span data-stu-id="3255b-136">The method returns an integer between 0 and 10.</span></span>  
  
 <span data-ttu-id="3255b-137">[!code-cs[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="3255b-137">[!code-cs[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]</span></span>  
  
 <span data-ttu-id="3255b-138">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="3255b-138">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="3255b-139">Измените оператор вызова в методе `Main` на `sc.GroupByRange()`.</span><span class="sxs-lookup"><span data-stu-id="3255b-139">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>  
  
 <span data-ttu-id="3255b-140">[!code-cs[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="3255b-140">[!code-cs[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3255b-141">Пример</span><span class="sxs-lookup"><span data-stu-id="3255b-141">Example</span></span>  
 <span data-ttu-id="3255b-142">В этом примере показана группировка элементов источника с помощью выражения логического сравнения.</span><span class="sxs-lookup"><span data-stu-id="3255b-142">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="3255b-143">В этом случае логическое выражение проверяет, превосходит ли среднее значение экзаменационного результата учащегося 75 баллов.</span><span class="sxs-lookup"><span data-stu-id="3255b-143">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="3255b-144">Как и в предыдущих примерах, результаты передаются в анонимный тип, так как весь элемент источника не требуется.</span><span class="sxs-lookup"><span data-stu-id="3255b-144">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="3255b-145">Обратите внимание на то, что свойства в анонимном типе становятся свойствами в члене `Key`, а при выполнении запроса доступ к ним можно получить по имени.</span><span class="sxs-lookup"><span data-stu-id="3255b-145">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>  
  
 <span data-ttu-id="3255b-146">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="3255b-146">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="3255b-147">Измените оператор вызова в методе `Main` на `sc.GroupByBoolean()`.</span><span class="sxs-lookup"><span data-stu-id="3255b-147">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>  
  
 <span data-ttu-id="3255b-148">[!code-cs[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="3255b-148">[!code-cs[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3255b-149">Пример</span><span class="sxs-lookup"><span data-stu-id="3255b-149">Example</span></span>  
 <span data-ttu-id="3255b-150">В этом примере показано, как использовать анонимный тип для инкапсуляции ключа, содержащего несколько значений.</span><span class="sxs-lookup"><span data-stu-id="3255b-150">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="3255b-151">В данном случае в качестве первого значения ключа используется первая буква фамилии учащегося.</span><span class="sxs-lookup"><span data-stu-id="3255b-151">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="3255b-152">Второе значение ключа является логическим и указывает, набрал ли учащийся более 85 баллов на первом экзамене.</span><span class="sxs-lookup"><span data-stu-id="3255b-152">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="3255b-153">Группы можно сортировать по любому из свойств в ключе.</span><span class="sxs-lookup"><span data-stu-id="3255b-153">You can order the groups by any property in the key.</span></span>  
  
 <span data-ttu-id="3255b-154">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="3255b-154">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="3255b-155">Измените оператор вызова в методе `Main` на `sc.GroupByCompositeKey()`.</span><span class="sxs-lookup"><span data-stu-id="3255b-155">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>  
  
 <span data-ttu-id="3255b-156">[!code-cs[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="3255b-156">[!code-cs[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3255b-157">См. также</span><span class="sxs-lookup"><span data-stu-id="3255b-157">See also</span></span>  
 <span data-ttu-id="3255b-158"><xref:System.Linq.Enumerable.GroupBy%2A></span><span class="sxs-lookup"><span data-stu-id="3255b-158"><xref:System.Linq.Enumerable.GroupBy%2A></span></span>   
 <span data-ttu-id="3255b-159"><xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="3255b-159"><xref:System.Linq.IGrouping%602></span></span>   
 <span data-ttu-id="3255b-160">[Выражения запросов LINQ](index.md) </span><span class="sxs-lookup"><span data-stu-id="3255b-160">[LINQ Query Expressions](index.md) </span></span>  
 <span data-ttu-id="3255b-161">[Предложение group](../language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="3255b-161">[group clause](../language-reference/keywords/group-clause.md) </span></span>  
 <span data-ttu-id="3255b-162">[Анонимные типы](../programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="3255b-162">[Anonymous Types](../programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="3255b-163">[Вложенный запрос в операции группирования](perform-a-subquery-on-a-grouping-operation.md) </span><span class="sxs-lookup"><span data-stu-id="3255b-163">[Perform a Subquery on a Grouping Operation](perform-a-subquery-on-a-grouping-operation.md) </span></span>  
 <span data-ttu-id="3255b-164">[Создание вложенной группы](create-a-nested-group.md) </span><span class="sxs-lookup"><span data-stu-id="3255b-164">[Create a Nested Group](create-a-nested-group.md) </span></span>  
 [<span data-ttu-id="3255b-165">Группировка данных</span><span class="sxs-lookup"><span data-stu-id="3255b-165">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)

