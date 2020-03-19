---
title: Руководство по программированию на C#. Неявно типизированные локальные переменные
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: d39e4c4dd180ba35b7555d61211a34d696b04f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398433"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="ae382-102">Неявно типизированные локальные переменные (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="ae382-102">Implicitly typed local variables (C# Programming Guide)</span></span>

<span data-ttu-id="ae382-103">Локальные переменные можно объявлять без указания конкретного типа.</span><span class="sxs-lookup"><span data-stu-id="ae382-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="ae382-104">Ключевое слово `var` указывает, что компилятор должен вывести тип переменной из выражения справа от оператора инициализации.</span><span class="sxs-lookup"><span data-stu-id="ae382-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="ae382-105">Выведенный тип может быть встроенным, анонимным, определяемым пользователем либо типом, определяемым в библиотеке классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ae382-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="ae382-106">Дополнительные сведения об инициализации массивов с `var` см. в разделе [Неявно типизированные массивы](../arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="ae382-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>

<span data-ttu-id="ae382-107">В приведенных ниже примерах показаны различные способы объявления локальных переменных с помощью `var`:</span><span class="sxs-lookup"><span data-stu-id="ae382-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>

[!code-csharp[csProgGuideLINQ#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#43)]

<span data-ttu-id="ae382-108">Важно понимать, что ключевое слово `var` не означает "variant" и не означает, что переменная является слабо типизированной или имеет позднее связывание.</span><span class="sxs-lookup"><span data-stu-id="ae382-108">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="ae382-109">Он указывает только на то, что компилятор определяет и назначает наиболее подходящий тип.</span><span class="sxs-lookup"><span data-stu-id="ae382-109">It just means that the compiler determines and assigns the most appropriate type.</span></span>

<span data-ttu-id="ae382-110">Ключевое слово `var` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="ae382-110">The `var` keyword may be used in the following contexts:</span></span>

- <span data-ttu-id="ae382-111">С локальными переменными (переменными, объявленными в области метода), как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="ae382-111">On local variables (variables declared at method scope) as shown in the previous example.</span></span>

- <span data-ttu-id="ae382-112">В операторе инициализации [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="ae382-112">In a [for](../../language-reference/keywords/for.md) initialization statement.</span></span>

    ```csharp
    for (var x = 1; x < 10; x++)
    ```

- <span data-ttu-id="ae382-113">В операторе инициализации [foreach](../../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="ae382-113">In a [foreach](../../language-reference/keywords/foreach-in.md) initialization statement.</span></span>

    ```csharp
    foreach (var item in list) {...}
    ```

- <span data-ttu-id="ae382-114">В операторе [using](../../language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae382-114">In a [using](../../language-reference/keywords/using-statement.md) statement.</span></span>

    ```csharp
    using (var file = new StreamReader("C:\\myfile.txt")) {...}
    ```

<span data-ttu-id="ae382-115">Дополнительные сведения см. в разделе [Практическое руководство. Использование неявно типизированных локальных переменных и массивов в выражении запроса](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="ae382-115">For more information, see [How to use implicitly typed local variables and arrays in a query expression](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>

## <a name="var-and-anonymous-types"></a><span data-ttu-id="ae382-116">Переменная var и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="ae382-116">var and anonymous types</span></span>

<span data-ttu-id="ae382-117">Во многих случаях переменная `var` не является обязательной и предназначена только для синтаксического удобства.</span><span class="sxs-lookup"><span data-stu-id="ae382-117">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="ae382-118">Тем не менее если переменная инициализируется с помощью анонимного типа и вам потребуется доступ к свойствам объекта на более позднем этапе, ее необходимо объявить как `var`.</span><span class="sxs-lookup"><span data-stu-id="ae382-118">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="ae382-119">Это распространенный сценарий в выражениях запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="ae382-119">This is a common scenario in LINQ query expressions.</span></span> <span data-ttu-id="ae382-120">Дополнительные сведения см. в статье [Анонимные типы](anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="ae382-120">For more information, see [Anonymous Types](anonymous-types.md).</span></span>

<span data-ttu-id="ae382-121">С точки зрения исходного кода анонимный тип безымянен.</span><span class="sxs-lookup"><span data-stu-id="ae382-121">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="ae382-122">Таким образом, если переменная запроса инициализирована с помощью `var`, то единственный способ получить доступ к свойствам в возвращаемой последовательности объектов — это использовать `var` как тип переменной итерации в операторе `foreach`.</span><span class="sxs-lookup"><span data-stu-id="ae382-122">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>

[!code-csharp[csProgGuideLINQ#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#44)]

## <a name="remarks"></a><span data-ttu-id="ae382-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="ae382-123">Remarks</span></span>

<span data-ttu-id="ae382-124">В объявлениям неявно типизированных переменных применяются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="ae382-124">The following restrictions apply to implicitly-typed variable declarations:</span></span>

- <span data-ttu-id="ae382-125">`var` можно использовать только в том случае, если локальная переменная объявляется и инициализируется в одном и том же операторе; переменная не может инициализироваться в нулевое значение, в группу методов или в анонимную функцию.</span><span class="sxs-lookup"><span data-stu-id="ae382-125">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>

- <span data-ttu-id="ae382-126">`var` нельзя применять к полям в области видимости класса.</span><span class="sxs-lookup"><span data-stu-id="ae382-126">`var` cannot be used on fields at class scope.</span></span>

- <span data-ttu-id="ae382-127">Переменные, объявленные с помощью `var`, нельзя использовать в выражении инициализации.</span><span class="sxs-lookup"><span data-stu-id="ae382-127">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="ae382-128">Другими словами, это выражение является допустимым выражением: `int i = (i = 20);`, но вызывает ошибку времени компиляции: `var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="ae382-128">In other words, this expression is legal: `int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>

- <span data-ttu-id="ae382-129">Инициализировать сразу несколько неявно типизированных переменных в одном и том же операторе нельзя.</span><span class="sxs-lookup"><span data-stu-id="ae382-129">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>

- <span data-ttu-id="ae382-130">Если тип с именем `var` входит в область видимости, то ключевое слово `var` разрешится в это имя типа и не будет обрабатываться как часть объявления неявно типизированной локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="ae382-130">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>

<span data-ttu-id="ae382-131">Неявное типизирование с ключевым словом `var` может применяться только к переменным в области локального метода.</span><span class="sxs-lookup"><span data-stu-id="ae382-131">Implicit typing with the `var` keyword can only be applied to variables at local method scope.</span></span> <span data-ttu-id="ae382-132">Неявное типизирование недоступно для полей класса C#, так как при обработке кода компилятор столкнется с логическим парадоксом: компилятор должен знать тип поля, но он не может определить тип, пока не проанализирует выражение присваивания, и не может вычислить выражение, не зная тип.</span><span class="sxs-lookup"><span data-stu-id="ae382-132">Implicit typing is not available for class fields as the C# compiler would encounter a logical paradox as it processed the code: the compiler needs to know the type of the field, but it cannot determine the type until the assignment expression is analyzed, and the expression cannot be evaluated without knowing the type.</span></span> <span data-ttu-id="ae382-133">Рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="ae382-133">Consider the following code:</span></span>

```csharp
private var bookTitles;
```

<span data-ttu-id="ae382-134">`bookTitles` — это поле класса, которому присваивается тип `var`.</span><span class="sxs-lookup"><span data-stu-id="ae382-134">`bookTitles` is a class field given the type `var`.</span></span> <span data-ttu-id="ae382-135">Так как поле не имеет выражения для оценки, то компилятор не сможет вывести тип `bookTitles`.</span><span class="sxs-lookup"><span data-stu-id="ae382-135">As the field has no expression to evaluate, it is impossible for the compiler to infer what type `bookTitles` is supposed to be.</span></span> <span data-ttu-id="ae382-136">Кроме того, добавления выражения в поле (так же, как для локальной переменной) тоже недостаточно:</span><span class="sxs-lookup"><span data-stu-id="ae382-136">In addition, adding an expression to the field (like you would for a local variable) is also insufficient:</span></span>

```csharp
private var bookTitles = new List<string>();
```

<span data-ttu-id="ae382-137">Когда компилятор обнаруживает поля во время компиляции кода, он записывает тип каждого поля перед обработкой любого выражения, связанного с ним.</span><span class="sxs-lookup"><span data-stu-id="ae382-137">When the compiler encounters fields during code compilation, it records each field's type before processing any expressions associated with it.</span></span> <span data-ttu-id="ae382-138">Компилятор обнаруживает тот же парадокс при попытке анализа `bookTitles`: он должен знать тип поля, но обычно он определяет тип `var` путем анализа выражения, который невозможно определить, если заранее не знать тип.</span><span class="sxs-lookup"><span data-stu-id="ae382-138">The compiler encounters the same paradox trying to parse `bookTitles`: it needs to know the type of the field, but the compiler would normally determine `var`'s type by analyzing the expression, which isn't possible without knowing the type beforehand.</span></span>

<span data-ttu-id="ae382-139">Переменную `var` можно также использовать в выражениях запросов, где точный сконструированный тип переменной запроса определить непросто.</span><span class="sxs-lookup"><span data-stu-id="ae382-139">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="ae382-140">Подобная ситуация может возникнуть в операциях группировки и сортировки.</span><span class="sxs-lookup"><span data-stu-id="ae382-140">This can occur with grouping and ordering operations.</span></span>

<span data-ttu-id="ae382-141">Кроме того, ключевое слово `var` может пригодиться, если конкретный тип переменной сложно набрать с клавиатуры, а также если он очевиден либо затрудняет чтение кода.</span><span class="sxs-lookup"><span data-stu-id="ae382-141">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="ae382-142">Использовать `var` таким образом можно, например, с вложенными универсальными типами — подобные типы применяются в групповых операциях.</span><span class="sxs-lookup"><span data-stu-id="ae382-142">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="ae382-143">В следующем запросе переменная запроса имеет тип `IEnumerable<IGrouping<string, Student>>`.</span><span class="sxs-lookup"><span data-stu-id="ae382-143">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="ae382-144">Если вы и другие пользователи, которые работают с кодом, это понимаете, использовать неявный ввод для удобства и краткости кода можно без проблем.</span><span class="sxs-lookup"><span data-stu-id="ae382-144">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

<span data-ttu-id="ae382-145">Ключевое слово `var` позволяет упростить код, однако его следует использовать только там, где оно действительно необходимо или где оно облегчает понимание кода.</span><span class="sxs-lookup"><span data-stu-id="ae382-145">The use of `var` helps simplify your code, but its use should be restricted to cases where it is required, or when it makes your code easier to read.</span></span> <span data-ttu-id="ae382-146">Дополнительные сведения о том, когда следует использовать ключевое слово `var`, см. в разделе [Неявно типизированные локальные переменные](../inside-a-program/coding-conventions.md#implicitly-typed-local-variables) в статье с рекомендациями по написанию кода C#.</span><span class="sxs-lookup"><span data-stu-id="ae382-146">For more information about when to use `var` properly, see the [Implicitly typed local variables](../inside-a-program/coding-conventions.md#implicitly-typed-local-variables) section on the C# Coding Guidelines article.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae382-147">См. также</span><span class="sxs-lookup"><span data-stu-id="ae382-147">See also</span></span>

- [<span data-ttu-id="ae382-148">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ae382-148">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="ae382-149">Неявно типизированные массивы</span><span class="sxs-lookup"><span data-stu-id="ae382-149">Implicitly Typed Arrays</span></span>](../arrays/implicitly-typed-arrays.md)
- [<span data-ttu-id="ae382-150">Практическое руководство. Использование неявно типизированных локальных переменных и массивов в выражении запроса</span><span class="sxs-lookup"><span data-stu-id="ae382-150">How to use implicitly typed local variables and arrays in a query expression</span></span>](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)
- [<span data-ttu-id="ae382-151">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="ae382-151">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="ae382-152">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="ae382-152">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
- [<span data-ttu-id="ae382-153">var</span><span class="sxs-lookup"><span data-stu-id="ae382-153">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="ae382-154">LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="ae382-154">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="ae382-155">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="ae382-155">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="ae382-156">for</span><span class="sxs-lookup"><span data-stu-id="ae382-156">for</span></span>](../../language-reference/keywords/for.md)
- [<span data-ttu-id="ae382-157">foreach, in</span><span class="sxs-lookup"><span data-stu-id="ae382-157">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="ae382-158">Оператор using</span><span class="sxs-lookup"><span data-stu-id="ae382-158">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
