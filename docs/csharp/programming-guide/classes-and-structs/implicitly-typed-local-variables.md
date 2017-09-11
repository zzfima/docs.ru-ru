---
title: "Неявно типизированные локальные переменные (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cc02c0f7ef5fbbbf3c60188426a8027f6a60fb89
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="036ac-102">Неявно типизированные локальные переменные (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="036ac-102">Implicitly Typed Local Variables (C# Programming Guide)</span></span>
<span data-ttu-id="036ac-103">Локальные переменные можно объявлять без указания конкретного типа.</span><span class="sxs-lookup"><span data-stu-id="036ac-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="036ac-104">Ключевое слово `var` указывает, что компилятор должен вывести тип переменной из выражения справа от оператора инициализации.</span><span class="sxs-lookup"><span data-stu-id="036ac-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="036ac-105">Выведенный тип может быть встроенным, анонимным, определяемым пользователем либо типом, определяемым в библиотеке классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="036ac-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="036ac-106">Дополнительные сведения об инициализации массивов с `var` см. в разделе [Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="036ac-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
 <span data-ttu-id="036ac-107">В приведенных ниже примерах показаны различные способы объявления локальных переменных с помощью `var`:</span><span class="sxs-lookup"><span data-stu-id="036ac-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>  
  
 <span data-ttu-id="036ac-108">[!code-cs[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="036ac-108">[!code-cs[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]</span></span>  
  
 <span data-ttu-id="036ac-109">Важно понимать, что ключевое слово `var` не означает "variant" и не означает, что переменная является слабо типизированной или имеет позднее связывание.</span><span class="sxs-lookup"><span data-stu-id="036ac-109">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="036ac-110">Он указывает только на то, что компилятор определяет и назначает наиболее подходящий тип.</span><span class="sxs-lookup"><span data-stu-id="036ac-110">It just means that the compiler determines and assigns the most appropriate type.</span></span>  
  
 <span data-ttu-id="036ac-111">Ключевое слово `var` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="036ac-111">The `var` keyword may be used in the following contexts:</span></span>  
  
-   <span data-ttu-id="036ac-112">С локальными переменными (переменными, объявленными в области метода), как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="036ac-112">On local variables (variables declared at method scope) as shown in the previous example.</span></span>  
  
-   <span data-ttu-id="036ac-113">В операторе инициализации [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="036ac-113">In a [for](../../../csharp/language-reference/keywords/for.md) initialization statement.</span></span>  
  
    ```  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   <span data-ttu-id="036ac-114">В операторе инициализации [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="036ac-114">In a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) initialization statement.</span></span>  
  
    ```  
    foreach(var item in list){...}  
    ```  
  
-   <span data-ttu-id="036ac-115">В операторе [using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="036ac-115">In a [using](../../../csharp/language-reference/keywords/using-statement.md) statement.</span></span>  
  
    ```  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 <span data-ttu-id="036ac-116">Дополнительные сведения см. в разделе [Практическое руководство. Использование явно введенных локальных переменных и массивов в выражении запроса](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="036ac-116">For more information, see [How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>  
  
## <a name="var-and-anonymous-types"></a><span data-ttu-id="036ac-117">Переменная var и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="036ac-117">var and Anonymous Types</span></span>  
 <span data-ttu-id="036ac-118">Во многих случаях переменная `var` не является обязательной и предназначена только для синтаксического удобства.</span><span class="sxs-lookup"><span data-stu-id="036ac-118">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="036ac-119">Тем не менее если переменная инициализируется с помощью анонимного типа и вам потребуется доступ к свойствам объекта на более позднем этапе, ее необходимо объявить как `var`.</span><span class="sxs-lookup"><span data-stu-id="036ac-119">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="036ac-120">Это — распространенный сценарий в выражениях запросов [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="036ac-120">This is a common scenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="036ac-121">Дополнительные сведения см. в разделе [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="036ac-121">For more information, see [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
 <span data-ttu-id="036ac-122">С точки зрения исходного кода анонимный тип безымянен.</span><span class="sxs-lookup"><span data-stu-id="036ac-122">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="036ac-123">Таким образом, если переменная запроса инициализирована с помощью `var`, то единственный способ получить доступ к свойствам в возвращаемой последовательности объектов — это использовать `var` как тип переменной итерации в операторе `foreach`.</span><span class="sxs-lookup"><span data-stu-id="036ac-123">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>  
  
 <span data-ttu-id="036ac-124">[!code-cs[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="036ac-124">[!code-cs[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="036ac-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="036ac-125">Remarks</span></span>  
 <span data-ttu-id="036ac-126">В объявлениям неявно типизированных переменных применяются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="036ac-126">The following restrictions apply to implicitly-typed variable declarations:</span></span>  
  
-   <span data-ttu-id="036ac-127">`var` можно использовать только в том случае, если локальная переменная объявляется и инициализируется в одном и том же операторе; переменная не может инициализироваться в нулевое значение, в группу методов или в анонимную функцию.</span><span class="sxs-lookup"><span data-stu-id="036ac-127">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>  
  
-   <span data-ttu-id="036ac-128">`var` нельзя применять к полям в области видимости класса.</span><span class="sxs-lookup"><span data-stu-id="036ac-128">`var` cannot be used on fields at class scope.</span></span>  
  
-   <span data-ttu-id="036ac-129">Переменные, объявленные с помощью `var`, нельзя использовать в выражении инициализации.</span><span class="sxs-lookup"><span data-stu-id="036ac-129">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="036ac-130">Другими словами, это выражение является допустимым выражением `: int i = (i = 20);`, но вызывает ошибку времени компиляции: `var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="036ac-130">In other words, this expression is legal`: int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>  
  
-   <span data-ttu-id="036ac-131">Инициализировать сразу несколько неявно типизированных переменных в одном и том же операторе нельзя.</span><span class="sxs-lookup"><span data-stu-id="036ac-131">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>  
  
-   <span data-ttu-id="036ac-132">Если тип с именем `var` входит в область видимости, то ключевое слово `var` разрешится в это имя типа и не будет обрабатываться как часть объявления неявно типизированной локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="036ac-132">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>  
  
 <span data-ttu-id="036ac-133">Переменную `var` можно также использовать в выражениях запросов, где точный сконструированный тип переменной запроса определить непросто.</span><span class="sxs-lookup"><span data-stu-id="036ac-133">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="036ac-134">Подобная ситуация может возникнуть в операциях группировки и сортировки.</span><span class="sxs-lookup"><span data-stu-id="036ac-134">This can occur with grouping and ordering operations.</span></span>  
  
 <span data-ttu-id="036ac-135">Кроме того, ключевое слово `var` может пригодиться, если конкретный тип переменной сложно набрать с клавиатуры, а также если он очевиден либо затрудняет чтение кода.</span><span class="sxs-lookup"><span data-stu-id="036ac-135">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="036ac-136">Использовать `var` таким образом можно, например, с вложенными универсальными типами — подобные типы применяются в групповых операциях.</span><span class="sxs-lookup"><span data-stu-id="036ac-136">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="036ac-137">В следующем запросе переменная запроса имеет тип `IEnumerable<IGrouping<string, Student>>`.</span><span class="sxs-lookup"><span data-stu-id="036ac-137">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="036ac-138">Если вы и другие пользователи, которые работают с кодом, это понимаете, использовать неявный ввод для удобства и краткости кода можно без проблем.</span><span class="sxs-lookup"><span data-stu-id="036ac-138">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>  
  
 <span data-ttu-id="036ac-139">[!code-cs[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="036ac-139">[!code-cs[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]</span></span>  
  
 <span data-ttu-id="036ac-140">При этом использование ключевого слова `var` может усложнить понимание вашего кода для других разработчиков.</span><span class="sxs-lookup"><span data-stu-id="036ac-140">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="036ac-141">В связи с этим в документации по C# `var` применяется только в тех случаях, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="036ac-141">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="036ac-142">См. также</span><span class="sxs-lookup"><span data-stu-id="036ac-142">See Also</span></span>  
 <span data-ttu-id="036ac-143">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="036ac-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="036ac-144">[Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="036ac-144">[Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md) </span></span>  
 <span data-ttu-id="036ac-145">[Практическое руководство. Использование явно введенных локальных переменных и массивов в выражении запроса](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md) </span><span class="sxs-lookup"><span data-stu-id="036ac-145">[How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md) </span></span>  
 <span data-ttu-id="036ac-146">[Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="036ac-146">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="036ac-147">[Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span><span class="sxs-lookup"><span data-stu-id="036ac-147">[Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span></span>  
 <span data-ttu-id="036ac-148">[var](../../../csharp/language-reference/keywords/var.md) </span><span class="sxs-lookup"><span data-stu-id="036ac-148">[var](../../../csharp/language-reference/keywords/var.md) </span></span>  
 <span data-ttu-id="036ac-149">[Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="036ac-149">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="036ac-150">[Встроенный язык запросов LINQ](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="036ac-150">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="036ac-151">[for](../../../csharp/language-reference/keywords/for.md) </span><span class="sxs-lookup"><span data-stu-id="036ac-151">[for](../../../csharp/language-reference/keywords/for.md) </span></span>  
 <span data-ttu-id="036ac-152">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="036ac-152">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 [<span data-ttu-id="036ac-153">Оператор using</span><span class="sxs-lookup"><span data-stu-id="036ac-153">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

