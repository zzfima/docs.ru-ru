---
title: Группировка результатов запросов (LINQ в C#)
description: Узнайте, как группировать результаты с помощью LINQ в C#.
ms.date: 12/01/2016
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.openlocfilehash: 577a358c31fcf5346e7aab7a2e2b6be10fd1beff
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857857"
---
# <a name="group-query-results"></a><span data-ttu-id="6abad-103">Группировка результатов запросов</span><span class="sxs-lookup"><span data-stu-id="6abad-103">Group query results</span></span>

<span data-ttu-id="6abad-104">Группирование — одна из самых эффективных функций LINQ.</span><span class="sxs-lookup"><span data-stu-id="6abad-104">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="6abad-105">В приведенных ниже примерах демонстрируются различные способы группирования данных:</span><span class="sxs-lookup"><span data-stu-id="6abad-105">The following examples show how to group data in various ways:</span></span>

- <span data-ttu-id="6abad-106">по отдельному свойству;</span><span class="sxs-lookup"><span data-stu-id="6abad-106">By a single property.</span></span>

- <span data-ttu-id="6abad-107">по первой букве строкового свойства;</span><span class="sxs-lookup"><span data-stu-id="6abad-107">By the first letter of a string property.</span></span>

- <span data-ttu-id="6abad-108">по расчетному числовому диапазону;</span><span class="sxs-lookup"><span data-stu-id="6abad-108">By a computed numeric range.</span></span>

- <span data-ttu-id="6abad-109">по логическому предикату или другому выражению;</span><span class="sxs-lookup"><span data-stu-id="6abad-109">By Boolean predicate or other expression.</span></span>

- <span data-ttu-id="6abad-110">по составному ключу.</span><span class="sxs-lookup"><span data-stu-id="6abad-110">By a compound key.</span></span>

<span data-ttu-id="6abad-111">Кроме того, два последних запроса передают свои результаты в новый анонимный тип, содержащий только имя и фамилию студента.</span><span class="sxs-lookup"><span data-stu-id="6abad-111">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="6abad-112">Дополнительные сведения см. в разделе [Предложение group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6abad-112">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="6abad-113">Пример</span><span class="sxs-lookup"><span data-stu-id="6abad-113">Example</span></span>

<span data-ttu-id="6abad-114">Во всех примерах в этом разделе используются указанные ниже вспомогательные классы и источники данных.</span><span class="sxs-lookup"><span data-stu-id="6abad-114">All the examples in this topic use the following helper classes and data sources.</span></span>

[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]

## <a name="example"></a><span data-ttu-id="6abad-115">Пример</span><span class="sxs-lookup"><span data-stu-id="6abad-115">Example</span></span>

<span data-ttu-id="6abad-116">В этом примере показана группировка элементов источника с помощью отдельного свойства элемента в качестве ключа группы.</span><span class="sxs-lookup"><span data-stu-id="6abad-116">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="6abad-117">В данном случае в качестве ключа используется `string`, фамилия учащегося.</span><span class="sxs-lookup"><span data-stu-id="6abad-117">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="6abad-118">Для ключа можно также использовать подстроку.</span><span class="sxs-lookup"><span data-stu-id="6abad-118">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="6abad-119">При операции группирования используется компаратор проверки на равенство, используемый по умолчанию для данного типа.</span><span class="sxs-lookup"><span data-stu-id="6abad-119">The grouping operation uses the default equality comparer for the type.</span></span>

<span data-ttu-id="6abad-120">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="6abad-120">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="6abad-121">Измените оператор вызова в методе `Main` на `sc.GroupBySingleProperty()`.</span><span class="sxs-lookup"><span data-stu-id="6abad-121">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>

[!code-csharp[csProgGuideLINQ#17](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]

## <a name="example"></a><span data-ttu-id="6abad-122">Пример</span><span class="sxs-lookup"><span data-stu-id="6abad-122">Example</span></span>

<span data-ttu-id="6abad-123">В этом примере показана группировка элементов источника, когда в качестве ключа группы используется не свойство объекта.</span><span class="sxs-lookup"><span data-stu-id="6abad-123">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="6abad-124">В данном случае в качестве ключа используется первая буква фамилии учащегося.</span><span class="sxs-lookup"><span data-stu-id="6abad-124">In this example, the key is the first letter of the student's last name.</span></span>

<span data-ttu-id="6abad-125">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="6abad-125">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="6abad-126">Измените оператор вызова в методе `Main` на `sc.GroupBySubstring()`.</span><span class="sxs-lookup"><span data-stu-id="6abad-126">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>

[!code-csharp[csProgGuideLINQ#18](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]

## <a name="example"></a><span data-ttu-id="6abad-127">Пример</span><span class="sxs-lookup"><span data-stu-id="6abad-127">Example</span></span>

<span data-ttu-id="6abad-128">В этом примере показана группировка элементов источника путем использования числового диапазона в качестве ключа группы.</span><span class="sxs-lookup"><span data-stu-id="6abad-128">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="6abad-129">Затем запрос передает результаты в анонимный тип, содержащий только имя и фамилию, а также диапазон процентилей, к которому принадлежит студент.</span><span class="sxs-lookup"><span data-stu-id="6abad-129">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="6abad-130">Использование анонимного типа объясняется тем, что для отображения результатов не требуется использовать полный объект `Student`.</span><span class="sxs-lookup"><span data-stu-id="6abad-130">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="6abad-131">`GetPercentile` — это вспомогательная функция, которая вычисляет процент на основе средних результатов учащегося.</span><span class="sxs-lookup"><span data-stu-id="6abad-131">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="6abad-132">Метод возвращает целое число в диапазоне от 0 до 10.</span><span class="sxs-lookup"><span data-stu-id="6abad-132">The method returns an integer between 0 and 10.</span></span>

[!code-csharp[csProgGuideLINQ#50](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]

<span data-ttu-id="6abad-133">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="6abad-133">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="6abad-134">Измените оператор вызова в методе `Main` на `sc.GroupByRange()`.</span><span class="sxs-lookup"><span data-stu-id="6abad-134">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>

[!code-csharp[csProgGuideLINQ#19](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]

## <a name="example"></a><span data-ttu-id="6abad-135">Пример</span><span class="sxs-lookup"><span data-stu-id="6abad-135">Example</span></span>

<span data-ttu-id="6abad-136">В этом примере показана группировка элементов источника с помощью выражения логического сравнения.</span><span class="sxs-lookup"><span data-stu-id="6abad-136">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="6abad-137">В этом случае логическое выражение проверяет, превосходит ли среднее значение экзаменационного результата учащегося 75 баллов.</span><span class="sxs-lookup"><span data-stu-id="6abad-137">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="6abad-138">Как и в предыдущих примерах, результаты передаются в анонимный тип, так как весь элемент источника не требуется.</span><span class="sxs-lookup"><span data-stu-id="6abad-138">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="6abad-139">Обратите внимание на то, что свойства в анонимном типе становятся свойствами в члене `Key`, а при выполнении запроса доступ к ним можно получить по имени.</span><span class="sxs-lookup"><span data-stu-id="6abad-139">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>

<span data-ttu-id="6abad-140">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="6abad-140">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="6abad-141">Измените оператор вызова в методе `Main` на `sc.GroupByBoolean()`.</span><span class="sxs-lookup"><span data-stu-id="6abad-141">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>

[!code-csharp[csProgGuideLINQ#20](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]

## <a name="example"></a><span data-ttu-id="6abad-142">Пример</span><span class="sxs-lookup"><span data-stu-id="6abad-142">Example</span></span>

<span data-ttu-id="6abad-143">В этом примере показано, как использовать анонимный тип для инкапсуляции ключа, содержащего несколько значений.</span><span class="sxs-lookup"><span data-stu-id="6abad-143">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="6abad-144">В данном случае в качестве первого значения ключа используется первая буква фамилии учащегося.</span><span class="sxs-lookup"><span data-stu-id="6abad-144">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="6abad-145">Второе значение ключа является логическим и указывает, набрал ли учащийся более 85 баллов на первом экзамене.</span><span class="sxs-lookup"><span data-stu-id="6abad-145">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="6abad-146">Группы можно сортировать по любому из свойств в ключе.</span><span class="sxs-lookup"><span data-stu-id="6abad-146">You can order the groups by any property in the key.</span></span>

<span data-ttu-id="6abad-147">Вставьте приведенный ниже метод в класс `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="6abad-147">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="6abad-148">Измените оператор вызова в методе `Main` на `sc.GroupByCompositeKey()`.</span><span class="sxs-lookup"><span data-stu-id="6abad-148">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>

[!code-csharp[csProgGuideLINQ#21](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]

## <a name="see-also"></a><span data-ttu-id="6abad-149">См. также</span><span class="sxs-lookup"><span data-stu-id="6abad-149">See also</span></span>

- <xref:System.Linq.Enumerable.GroupBy%2A>
- <xref:System.Linq.IGrouping%602>
- [<span data-ttu-id="6abad-150">LINQ</span><span class="sxs-lookup"><span data-stu-id="6abad-150">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="6abad-151">предложение group</span><span class="sxs-lookup"><span data-stu-id="6abad-151">group clause</span></span>](../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="6abad-152">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="6abad-152">Anonymous Types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="6abad-153">Вложенный запрос в операции группирования</span><span class="sxs-lookup"><span data-stu-id="6abad-153">Perform a Subquery on a Grouping Operation</span></span>](perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="6abad-154">Создание вложенной группы</span><span class="sxs-lookup"><span data-stu-id="6abad-154">Create a Nested Group</span></span>](create-a-nested-group.md)
- [<span data-ttu-id="6abad-155">Группировка данных</span><span class="sxs-lookup"><span data-stu-id="6abad-155">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)
