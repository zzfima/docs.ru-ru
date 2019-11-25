---
title: Справочник по C#. Предложение group
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
ms.openlocfilehash: dd14a4baf9967f41690e7978b8b6cf57c9275e36
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428500"
---
# <a name="group-clause-c-reference"></a><span data-ttu-id="4d3ce-102">Предложение group (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-102">group clause (C# Reference)</span></span>

<span data-ttu-id="4d3ce-103">Предложение `group` возвращает последовательность объектов <xref:System.Linq.IGrouping%602>, содержащих нуль или более элементов, соответствующих значению ключа группы.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-103">The `group` clause returns a sequence of <xref:System.Linq.IGrouping%602> objects that contain zero or more items that match the key value for the group.</span></span> <span data-ttu-id="4d3ce-104">Например, можно сгруппировать последовательность строк в соответствии с первой буквой в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-104">For example, you can group a sequence of strings according to the first letter in each string.</span></span> <span data-ttu-id="4d3ce-105">В этом случае первая буква является ключом и имеет тип [char](../builtin-types/char.md). Она хранится в свойстве `Key` каждого объекта <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-105">In this case, the first letter is the key and has a type [char](../builtin-types/char.md), and is stored in the `Key` property of each <xref:System.Linq.IGrouping%602> object.</span></span> <span data-ttu-id="4d3ce-106">Тип ключа определяется компилятором.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-106">The compiler infers the type of the key.</span></span>

<span data-ttu-id="4d3ce-107">Завершить выражение запроса с предложением `group` можно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-107">You can end a query expression with a `group` clause, as shown in the following example:</span></span>

[!code-csharp[cscsrefQueryKeywords#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#10)]

<span data-ttu-id="4d3ce-108">Чтобы выполнить дополнительные запросы для каждой из групп, можно указать временный идентификатор, воспользовавшись для этого контекстным ключевым словом [into](into.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-108">If you want to perform additional query operations on each group, you can specify a temporary identifier by using the [into](into.md) contextual keyword.</span></span> <span data-ttu-id="4d3ce-109">При использовании ключевого слова `into` необходимо продолжить запрос и завершить его инструкцией `select` или другим предложением `group`, как показано в следующем фрагменте:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-109">When you use `into`, you must continue with the query, and eventually end it with either a `select` statement or another `group` clause, as shown in the following excerpt:</span></span>

[!code-csharp[cscsrefQueryKeywords#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#11)]

<span data-ttu-id="4d3ce-110">Более подробные примеры использования предложения `group` с ключевым словом `into` и без него см. в разделе "Пример" в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-110">More complete examples of the use of `group` with and without `into` are provided in the Example section of this article.</span></span>

## <a name="enumerating-the-results-of-a-group-query"></a><span data-ttu-id="4d3ce-111">Перечисление результатов запроса group</span><span class="sxs-lookup"><span data-stu-id="4d3ce-111">Enumerating the results of a group query</span></span>

<span data-ttu-id="4d3ce-112">Так как возвращаемые запросом `group` объекты <xref:System.Linq.IGrouping%602> представляют собой список списков, для доступа к каждому из элементов этих групп необходимо использовать вложенный цикл [foreach](foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-112">Because the <xref:System.Linq.IGrouping%602> objects produced by a `group` query are essentially a list of lists, you must use a nested [foreach](foreach-in.md) loop to access the items in each group.</span></span> <span data-ttu-id="4d3ce-113">Во внешнем цикле итерация будет выполняться по ключам групп, а во внутреннем цикле — по элементам самих групп.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-113">The outer loop iterates over the group keys, and the inner loop iterates over each item in the group itself.</span></span> <span data-ttu-id="4d3ce-114">У группы может быть ключ, но не быть элементов.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-114">A group may have a key but no elements.</span></span> <span data-ttu-id="4d3ce-115">Ниже приведен пример цикла `foreach`, который выполняет запрос, показанный в предыдущих примерах кода:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-115">The following is the `foreach` loop that executes the query in the previous code examples:</span></span>

[!code-csharp[cscsrefQueryKeywords#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#12)]

## <a name="key-types"></a><span data-ttu-id="4d3ce-116">Типы ключей</span><span class="sxs-lookup"><span data-stu-id="4d3ce-116">Key types</span></span>

<span data-ttu-id="4d3ce-117">Ключи групп могут быть любого типа, например строкового, встроенного числового, пользовательского именованного или анонимного типа.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-117">Group keys can be any type, such as a string, a built-in numeric type, or a user-defined named type or anonymous type.</span></span>

### <a name="grouping-by-string"></a><span data-ttu-id="4d3ce-118">Группировка по строке</span><span class="sxs-lookup"><span data-stu-id="4d3ce-118">Grouping by string</span></span>

<span data-ttu-id="4d3ce-119">В предыдущих примерах кода использовался ключ типа `char`.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-119">The previous code examples used a `char`.</span></span> <span data-ttu-id="4d3ce-120">Вместо него можно было указать строку, например фамилию:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-120">A string key could easily have been specified instead, for example the complete last name:</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

### <a name="grouping-by-bool"></a><span data-ttu-id="4d3ce-121">Группировка по логическому значению</span><span class="sxs-lookup"><span data-stu-id="4d3ce-121">Grouping by bool</span></span>

<span data-ttu-id="4d3ce-122">В следующем примере показано разбиение результатов на две группы в зависимости от значения логического ключа.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-122">The following example shows the use of a bool value for a key to divide the results into two groups.</span></span> <span data-ttu-id="4d3ce-123">Обратите внимание, что значение формируется с помощью входящего в состав предложения `group` выражения.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-123">Note that the value is produced by a sub-expression in the `group` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#14)]

### <a name="grouping-by-numeric-range"></a><span data-ttu-id="4d3ce-124">Группировка по числовому диапазону</span><span class="sxs-lookup"><span data-stu-id="4d3ce-124">Grouping by numeric range</span></span>

<span data-ttu-id="4d3ce-125">В следующем примере с помощью выражения создаются числовые ключи групп, обозначающие диапазоны значений в выборке.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-125">The next example uses an expression to create numeric group keys that represent a percentile range.</span></span> <span data-ttu-id="4d3ce-126">Обратите внимание на удобное использование [let](let-clause.md) для хранения результатов вызова метода, чтобы в предложении `group` не приходилось вызывать метод дважды.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-126">Note the use of [let](let-clause.md) as a convenient location to store a method call result, so that you don't have to call the method two times in the `group` clause.</span></span> <span data-ttu-id="4d3ce-127">Дополнительные сведения о безопасном использовании методов в выражениях запросов см. в практическом руководстве по [ обработке исключений в выражениях запросов](../../linq/handle-exceptions-in-query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-127">For more information about how to safely use methods in query expressions, see [How to: Handle Exceptions in Query Expressions](../../linq/handle-exceptions-in-query-expressions.md).</span></span>

[!code-csharp[cscsrefQueryKeywords#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#15)]

### <a name="grouping-by-composite-keys"></a><span data-ttu-id="4d3ce-128">Группировка по составному ключу</span><span class="sxs-lookup"><span data-stu-id="4d3ce-128">Grouping by composite keys</span></span>

<span data-ttu-id="4d3ce-129">Составные ключи используются в тех случаях, когда необходимо сгруппировать элементы по более чем одному ключу.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-129">Use a composite key when you want to group elements according to more than one key.</span></span> <span data-ttu-id="4d3ce-130">Составной ключ создается с помощью анонимного типа или именованного типа для хранения элементов ключа.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-130">You create a composite key by using an anonymous type or a named type to hold the key element.</span></span> <span data-ttu-id="4d3ce-131">В следующем примере предполагается, что для класса `Person` были объявлены члены `surname` и `city`.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-131">In the following example, assume that a class `Person` has been declared with members named `surname` and `city`.</span></span> <span data-ttu-id="4d3ce-132">Предложение `group` позволяет создать отдельную группу для каждого набора людей, имеющих одинаковые фамилии и города.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-132">The `group` clause causes a separate group to be created for each set of persons with the same last name and the same city.</span></span>

```csharp
group person by new {name = person.surname, city = person.city};
```

<span data-ttu-id="4d3ce-133">Если требуется передать переменную запроса другому методу, следует использовать именованные типы.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-133">Use a named type if you must pass the query variable to another method.</span></span> <span data-ttu-id="4d3ce-134">Создайте особый класс, используя автоматически реализуемые свойства для ключей, а затем переопределите методы <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-134">Create a special class using auto-implemented properties for the keys, and then override the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods.</span></span> <span data-ttu-id="4d3ce-135">Можно также воспользоваться структурой, чтобы избежать необходимости переопределять эти методы.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-135">You can also use a struct, in which case you do not strictly have to override those methods.</span></span> <span data-ttu-id="4d3ce-136">Дополнительные сведения см. в статьях [Практическое руководство. Реализация облегченного класса с автоматически реализуемыми свойствами](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) и [Практическое руководство. выполнению запросов повторяющихся файлов в дереве каталогов](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-136">For more information see [How to implement a lightweight class with auto-implemented properties](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) and [How to: Query for Duplicate Files in a Directory Tree](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md).</span></span> <span data-ttu-id="4d3ce-137">В последней статье имеется пример кода, демонстрирующий использование составных ключей с именованным типом.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-137">The latter article has a code example that demonstrates how to use a composite key with a named type.</span></span>

## <a name="example"></a><span data-ttu-id="4d3ce-138">Пример</span><span class="sxs-lookup"><span data-stu-id="4d3ce-138">Example</span></span>

<span data-ttu-id="4d3ce-139">В следующем примере показан стандартный шаблон для разбиения данных на группы без применения к группам дополнительной логики запроса.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-139">The following example shows the standard pattern for ordering source data into groups when no additional query logic is applied to the groups.</span></span> <span data-ttu-id="4d3ce-140">Такой прием называется группировкой без продолжения.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-140">This is called a grouping without a continuation.</span></span> <span data-ttu-id="4d3ce-141">Элементы массива строк группируются в соответствии со своими первыми буквами.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-141">The elements in an array of strings are grouped according to their first letter.</span></span> <span data-ttu-id="4d3ce-142">Результатом запроса является тип <xref:System.Linq.IGrouping%602>, который содержит открытое свойство `Key` типа `char` и коллекцию <xref:System.Collections.Generic.IEnumerable%601>, содержащую каждый элемент в группе.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-142">The result of the query is an <xref:System.Linq.IGrouping%602> type that contains a public `Key` property of type `char` and an <xref:System.Collections.Generic.IEnumerable%601> collection that contains each item in the grouping.</span></span>

<span data-ttu-id="4d3ce-143">Результатом выполнения предложения `group` является последовательность из последовательностей.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-143">The result of a `group` clause is a sequence of sequences.</span></span> <span data-ttu-id="4d3ce-144">Таким образом, для доступа к отдельным элементам каждой из полученных групп следует использовать вложенный цикл `foreach`, в котором итерация выполняется по ключам групп, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-144">Therefore, to access the individual elements within each returned group, use a nested `foreach` loop inside the loop that iterates the group keys, as shown in the following example.</span></span>

[!code-csharp[cscsrefQueryKeywords#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#16)]

## <a name="example"></a><span data-ttu-id="4d3ce-145">Пример</span><span class="sxs-lookup"><span data-stu-id="4d3ce-145">Example</span></span>

<span data-ttu-id="4d3ce-146">В этом примере показано выполнение дополнительных операций над группами после их создания. Для этого используется *continuation* с `into`.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-146">This example shows how to perform additional logic on the groups after you have created them, by using a *continuation* with `into`.</span></span> <span data-ttu-id="4d3ce-147">Дополнительные сведения см. в разделе [into](into.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-147">For more information, see [into](into.md).</span></span> <span data-ttu-id="4d3ce-148">В следующем примере создается запрос, выбирающий только те группы, элементы которых начинаются на гласную.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-148">The following example queries each group to select only those whose key value is a vowel.</span></span>

[!code-csharp[cscsrefQueryKeywords#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#17)]

## <a name="remarks"></a><span data-ttu-id="4d3ce-149">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d3ce-149">Remarks</span></span>

<span data-ttu-id="4d3ce-150">Во время компиляции предложения `group` преобразуются в вызовы метода <xref:System.Linq.Enumerable.GroupBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-150">At compile time, `group` clauses are translated into calls to the <xref:System.Linq.Enumerable.GroupBy%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d3ce-151">См. также</span><span class="sxs-lookup"><span data-stu-id="4d3ce-151">See also</span></span>

- <xref:System.Linq.IGrouping%602>
- <xref:System.Linq.Enumerable.GroupBy%2A>
- <xref:System.Linq.Enumerable.ThenBy%2A>
- <xref:System.Linq.Enumerable.ThenByDescending%2A>
- [<span data-ttu-id="4d3ce-152">Ключевые слова запроса</span><span class="sxs-lookup"><span data-stu-id="4d3ce-152">Query Keywords</span></span>](query-keywords.md)
- [<span data-ttu-id="4d3ce-153">LINQ</span><span class="sxs-lookup"><span data-stu-id="4d3ce-153">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="4d3ce-154">Создание вложенной группы</span><span class="sxs-lookup"><span data-stu-id="4d3ce-154">Create a nested group</span></span>](../../linq/create-a-nested-group.md)
- [<span data-ttu-id="4d3ce-155">Группировка результатов запросов</span><span class="sxs-lookup"><span data-stu-id="4d3ce-155">Group query results</span></span>](../../linq/group-query-results.md)
- [<span data-ttu-id="4d3ce-156">Вложенный запрос в операции группирования</span><span class="sxs-lookup"><span data-stu-id="4d3ce-156">Perform a subquery on a grouping operation</span></span>](../../linq/perform-a-subquery-on-a-grouping-operation.md)
