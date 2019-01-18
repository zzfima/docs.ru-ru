---
title: Руководство по программированию на C#. Неявно типизированные локальные переменные
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: 9c6f7ae5d7a579abead2a62f8fdc7c63e5c53328
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222713"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="2e91b-102">Неявно типизированные локальные переменные (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="2e91b-102">Implicitly typed local variables (C# Programming Guide)</span></span>

<span data-ttu-id="2e91b-103">Локальные переменные можно объявлять без указания конкретного типа.</span><span class="sxs-lookup"><span data-stu-id="2e91b-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="2e91b-104">Ключевое слово `var` указывает, что компилятор должен вывести тип переменной из выражения справа от оператора инициализации.</span><span class="sxs-lookup"><span data-stu-id="2e91b-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="2e91b-105">Выведенный тип может быть встроенным, анонимным, определяемым пользователем либо типом, определяемым в библиотеке классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2e91b-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="2e91b-106">Дополнительные сведения об инициализации массивов с `var` см. в разделе [Неявно типизированные массивы](../arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="2e91b-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>

<span data-ttu-id="2e91b-107">В приведенных ниже примерах показаны различные способы объявления локальных переменных с помощью `var`:</span><span class="sxs-lookup"><span data-stu-id="2e91b-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>

[!code-csharp[csProgGuideLINQ#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#43)]

<span data-ttu-id="2e91b-108">Важно понимать, что ключевое слово `var` не означает "variant" и не означает, что переменная является слабо типизированной или имеет позднее связывание.</span><span class="sxs-lookup"><span data-stu-id="2e91b-108">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="2e91b-109">Он указывает только на то, что компилятор определяет и назначает наиболее подходящий тип.</span><span class="sxs-lookup"><span data-stu-id="2e91b-109">It just means that the compiler determines and assigns the most appropriate type.</span></span>

<span data-ttu-id="2e91b-110">Ключевое слово `var` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="2e91b-110">The `var` keyword may be used in the following contexts:</span></span>

- <span data-ttu-id="2e91b-111">С локальными переменными (переменными, объявленными в области метода), как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="2e91b-111">On local variables (variables declared at method scope) as shown in the previous example.</span></span>

- <span data-ttu-id="2e91b-112">В операторе инициализации [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="2e91b-112">In a [for](../../language-reference/keywords/for.md) initialization statement.</span></span>

    ```csharp
    for(var x = 1; x < 10; x++)
    ```

- <span data-ttu-id="2e91b-113">В операторе инициализации [foreach](../../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="2e91b-113">In a [foreach](../../language-reference/keywords/foreach-in.md) initialization statement.</span></span>

    ```csharp
    foreach(var item in list){...}
    ```

- <span data-ttu-id="2e91b-114">В операторе [using](../../language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2e91b-114">In a [using](../../language-reference/keywords/using-statement.md) statement.</span></span>

    ```csharp
    using (var file = new StreamReader("C:\\myfile.txt")) {...}
    ```

<span data-ttu-id="2e91b-115">Дополнительные сведения см. в разделе [Как Руководство по программированию на C#. Использование явно введенных локальных переменных и массивов в выражении запроса](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2e91b-115">For more information, see [How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>

## <a name="var-and-anonymous-types"></a><span data-ttu-id="2e91b-116">Переменная var и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="2e91b-116">var and anonymous types</span></span>

<span data-ttu-id="2e91b-117">Во многих случаях переменная `var` не является обязательной и предназначена только для синтаксического удобства.</span><span class="sxs-lookup"><span data-stu-id="2e91b-117">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="2e91b-118">Тем не менее если переменная инициализируется с помощью анонимного типа и вам потребуется доступ к свойствам объекта на более позднем этапе, ее необходимо объявить как `var`.</span><span class="sxs-lookup"><span data-stu-id="2e91b-118">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="2e91b-119">Это — распространенный сценарий в выражениях запросов [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e91b-119">This is a common scenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="2e91b-120">Дополнительные сведения см. в разделе [Анонимные типы](anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="2e91b-120">For more information, see [Anonymous Types](anonymous-types.md).</span></span>

<span data-ttu-id="2e91b-121">С точки зрения исходного кода анонимный тип безымянен.</span><span class="sxs-lookup"><span data-stu-id="2e91b-121">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="2e91b-122">Таким образом, если переменная запроса инициализирована с помощью `var`, то единственный способ получить доступ к свойствам в возвращаемой последовательности объектов — это использовать `var` как тип переменной итерации в операторе `foreach`.</span><span class="sxs-lookup"><span data-stu-id="2e91b-122">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>

[!code-csharp[csProgGuideLINQ#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#44)]

## <a name="remarks"></a><span data-ttu-id="2e91b-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e91b-123">Remarks</span></span>

<span data-ttu-id="2e91b-124">В объявлениям неявно типизированных переменных применяются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="2e91b-124">The following restrictions apply to implicitly-typed variable declarations:</span></span>

- <span data-ttu-id="2e91b-125">`var` можно использовать только в том случае, если локальная переменная объявляется и инициализируется в одном и том же операторе; переменная не может инициализироваться в нулевое значение, в группу методов или в анонимную функцию.</span><span class="sxs-lookup"><span data-stu-id="2e91b-125">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>

- <span data-ttu-id="2e91b-126">`var` нельзя применять к полям в области видимости класса.</span><span class="sxs-lookup"><span data-stu-id="2e91b-126">`var` cannot be used on fields at class scope.</span></span>

- <span data-ttu-id="2e91b-127">Переменные, объявленные с помощью `var`, нельзя использовать в выражении инициализации.</span><span class="sxs-lookup"><span data-stu-id="2e91b-127">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="2e91b-128">Другими словами, это выражение является допустимым выражением `: int i = (i = 20);`, но вызывает ошибку времени компиляции: `var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="2e91b-128">In other words, this expression is legal`: int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>

- <span data-ttu-id="2e91b-129">Инициализировать сразу несколько неявно типизированных переменных в одном и том же операторе нельзя.</span><span class="sxs-lookup"><span data-stu-id="2e91b-129">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>

- <span data-ttu-id="2e91b-130">Если тип с именем `var` входит в область видимости, то ключевое слово `var` разрешится в это имя типа и не будет обрабатываться как часть объявления неявно типизированной локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="2e91b-130">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>

<span data-ttu-id="2e91b-131">Переменную `var` можно также использовать в выражениях запросов, где точный сконструированный тип переменной запроса определить непросто.</span><span class="sxs-lookup"><span data-stu-id="2e91b-131">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="2e91b-132">Подобная ситуация может возникнуть в операциях группировки и сортировки.</span><span class="sxs-lookup"><span data-stu-id="2e91b-132">This can occur with grouping and ordering operations.</span></span>

<span data-ttu-id="2e91b-133">Кроме того, ключевое слово `var` может пригодиться, если конкретный тип переменной сложно набрать с клавиатуры, а также если он очевиден либо затрудняет чтение кода.</span><span class="sxs-lookup"><span data-stu-id="2e91b-133">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="2e91b-134">Использовать `var` таким образом можно, например, с вложенными универсальными типами — подобные типы применяются в групповых операциях.</span><span class="sxs-lookup"><span data-stu-id="2e91b-134">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="2e91b-135">В следующем запросе переменная запроса имеет тип `IEnumerable<IGrouping<string, Student>>`.</span><span class="sxs-lookup"><span data-stu-id="2e91b-135">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="2e91b-136">Если вы и другие пользователи, которые работают с кодом, это понимаете, использовать неявный ввод для удобства и краткости кода можно без проблем.</span><span class="sxs-lookup"><span data-stu-id="2e91b-136">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

<span data-ttu-id="2e91b-137">При этом использование ключевого слова `var` может усложнить понимание вашего кода для других разработчиков.</span><span class="sxs-lookup"><span data-stu-id="2e91b-137">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="2e91b-138">В связи с этим в документации по C# `var` применяется только в тех случаях, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="2e91b-138">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e91b-139">См. также</span><span class="sxs-lookup"><span data-stu-id="2e91b-139">See also</span></span>

- [<span data-ttu-id="2e91b-140">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2e91b-140">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="2e91b-141">Неявно типизированные массивы</span><span class="sxs-lookup"><span data-stu-id="2e91b-141">Implicitly Typed Arrays</span></span>](../arrays/implicitly-typed-arrays.md)
- [<span data-ttu-id="2e91b-142">Практическое руководство. Использование явно введенных локальных переменных и массивов в выражении запроса</span><span class="sxs-lookup"><span data-stu-id="2e91b-142">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression</span></span>](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)
- [<span data-ttu-id="2e91b-143">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="2e91b-143">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="2e91b-144">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="2e91b-144">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
- [<span data-ttu-id="2e91b-145">var</span><span class="sxs-lookup"><span data-stu-id="2e91b-145">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="2e91b-146">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="2e91b-146">LINQ Query Expressions</span></span>](../linq-query-expressions/index.md)
- [<span data-ttu-id="2e91b-147">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="2e91b-147">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="2e91b-148">for</span><span class="sxs-lookup"><span data-stu-id="2e91b-148">for</span></span>](../../language-reference/keywords/for.md)
- [<span data-ttu-id="2e91b-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="2e91b-149">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="2e91b-150">Оператор using</span><span class="sxs-lookup"><span data-stu-id="2e91b-150">using Statement</span></span>](../../language-reference/keywords/using-statement.md)