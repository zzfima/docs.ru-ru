---
title: "Использование пространств имен (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.names
dev_langs:
- CSharp
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
caps.latest.revision: 26
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
ms.openlocfilehash: 61b5d78f1c4924e3858c14876d36e52d4ee46ceb
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="a1c26-102">Использование пространств имен (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="a1c26-102">Using Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="a1c26-103">Пространства имен часто используются в программировании на C# двумя способами.</span><span class="sxs-lookup"><span data-stu-id="a1c26-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="a1c26-104">Первый способ — платформа .NET Framework использует пространства имен для упорядочения множества ее классов.</span><span class="sxs-lookup"><span data-stu-id="a1c26-104">Firstly, the .NET Framework classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="a1c26-105">Второй способ — объявление собственных пространств имен поможет вам контролировать область имен классов и методов в более крупных проектах.</span><span class="sxs-lookup"><span data-stu-id="a1c26-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="a1c26-106">Доступ к пространствам имен</span><span class="sxs-lookup"><span data-stu-id="a1c26-106">Accessing Namespaces</span></span>  
 <span data-ttu-id="a1c26-107">Большинство приложений на языке C# начинается с раздела директив `using`.</span><span class="sxs-lookup"><span data-stu-id="a1c26-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="a1c26-108">В этом разделе перечисляются пространства имен, которые будут часто использоваться приложением, благодаря чему программист может не указывать их полные названия каждый раз, когда вызывается содержащийся в них метод.</span><span class="sxs-lookup"><span data-stu-id="a1c26-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="a1c26-109">Например, включив строку</span><span class="sxs-lookup"><span data-stu-id="a1c26-109">For example, by including the line:</span></span>  
  
 <span data-ttu-id="a1c26-110">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-110">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]</span></span>  
  
 <span data-ttu-id="a1c26-111">в начале программы, программист может использовать код</span><span class="sxs-lookup"><span data-stu-id="a1c26-111">At the start of a program, the programmer can use the code:</span></span>  
  
 <span data-ttu-id="a1c26-112">[!code-cs[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-112">[!code-cs[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]</span></span>  
  
 <span data-ttu-id="a1c26-113">вместо следующего кода:</span><span class="sxs-lookup"><span data-stu-id="a1c26-113">Instead of:</span></span>  
  
 <span data-ttu-id="a1c26-114">[!code-cs[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-114">[!code-cs[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]</span></span>  
  
## <a name="namespace-aliases"></a><span data-ttu-id="a1c26-115">Псевдонимы пространств имен</span><span class="sxs-lookup"><span data-stu-id="a1c26-115">Namespace Aliases</span></span>  
 <span data-ttu-id="a1c26-116">С помощью [директивы using](../../../csharp/language-reference/keywords/using-directive.md) также можно создавать псевдонимы [пространств имен](../../../csharp/language-reference/keywords/namespace.md).</span><span class="sxs-lookup"><span data-stu-id="a1c26-116">The [using Directive](../../../csharp/language-reference/keywords/using-directive.md) can also be used to create an alias for a [namespace](../../../csharp/language-reference/keywords/namespace.md).</span></span> <span data-ttu-id="a1c26-117">Например, при использовании ранее указанного пространства имен, содержащего вложенные пространства имен, можно объявить псевдоним для быстрого обращения к нему, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a1c26-117">For example, if you are using a previously written namespace that contains nested namespaces, you might want to declare an alias to provide a shorthand way of referencing one in particular, as in the following example:</span></span>  
  
 <span data-ttu-id="a1c26-118">[!code-cs[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-118">[!code-cs[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]</span></span>  
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="a1c26-119">Использование пространств имен для управления областью действия</span><span class="sxs-lookup"><span data-stu-id="a1c26-119">Using Namespaces to control scope</span></span>  
 <span data-ttu-id="a1c26-120">Область действия объявляется с помощью ключевого слова `namespace`.</span><span class="sxs-lookup"><span data-stu-id="a1c26-120">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="a1c26-121">Определяя области действия в проекте, вы можете упорядочивать код и создавать уникальные на глобальном уровне типы.</span><span class="sxs-lookup"><span data-stu-id="a1c26-121">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="a1c26-122">В следующем примере класс `SampleClass` определяется в двух пространствах имен, одно из которых вложено в другое.</span><span class="sxs-lookup"><span data-stu-id="a1c26-122">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="a1c26-123">[. Для определения конкретного вызываемого метода используется оператор ](../../../csharp/language-reference/operators/member-access-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a1c26-123">The [. Operator](../../../csharp/language-reference/operators/member-access-operator.md) is used to differentiate which method gets called.</span></span>  
  
 <span data-ttu-id="a1c26-124">[!code-cs[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-124">[!code-cs[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="a1c26-125">полные имена</span><span class="sxs-lookup"><span data-stu-id="a1c26-125">Fully Qualified Names</span></span>  
 <span data-ttu-id="a1c26-126">Пространства имен и типы имеют уникальные названия, которые описываются полными именами, определяющими их место в логической иерархии.</span><span class="sxs-lookup"><span data-stu-id="a1c26-126">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="a1c26-127">Например, инструкция `A.B` указывает, что `A` — это пространство имен или тип, а `B` — вложенный в него элемент.</span><span class="sxs-lookup"><span data-stu-id="a1c26-127">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="a1c26-128">В следующем примере показаны вложенные классы и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a1c26-128">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="a1c26-129">Полное имя каждого элемента указано в комментарии рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="a1c26-129">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 <span data-ttu-id="a1c26-130">[!code-cs[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-130">[!code-cs[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]</span></span>  
  
 <span data-ttu-id="a1c26-131">В предыдущем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="a1c26-131">In the previous code segment:</span></span>  
  
-   <span data-ttu-id="a1c26-132">Пространство имен `N1` является членом глобального пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a1c26-132">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="a1c26-133">Его полное имя: `N1`.</span><span class="sxs-lookup"><span data-stu-id="a1c26-133">Its fully qualified name is `N1`.</span></span>  
  
-   <span data-ttu-id="a1c26-134">Пространство имен `N2` является членом пространства имен `N1`.</span><span class="sxs-lookup"><span data-stu-id="a1c26-134">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="a1c26-135">Его полное имя: `N1.N2`.</span><span class="sxs-lookup"><span data-stu-id="a1c26-135">Its fully qualified name is `N1.N2`.</span></span>  
  
-   <span data-ttu-id="a1c26-136">Класс `C1` является членом пространства имен `N1`.</span><span class="sxs-lookup"><span data-stu-id="a1c26-136">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="a1c26-137">Его полное имя: `N1.C1`.</span><span class="sxs-lookup"><span data-stu-id="a1c26-137">Its fully qualified name is `N1.C1`.</span></span>  
  
-   <span data-ttu-id="a1c26-138">В этом коде имя класса `C2` используется два раза.</span><span class="sxs-lookup"><span data-stu-id="a1c26-138">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="a1c26-139">Тем не менее полные имена являются уникальными.</span><span class="sxs-lookup"><span data-stu-id="a1c26-139">However, the fully qualified names are unique.</span></span> <span data-ttu-id="a1c26-140">Первый экземпляр `C2` объявляется в классе `C1`. Соответственно, его полное имя: `N1.C1.C2`.</span><span class="sxs-lookup"><span data-stu-id="a1c26-140">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="a1c26-141">Второй экземпляр `C2` объявляется в пространстве имен `N2`. Соответственно, его полное имя: `N1.N2.C2`.</span><span class="sxs-lookup"><span data-stu-id="a1c26-141">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="a1c26-142">Используя представленный выше фрагмент кода, вы можете добавить новый элемент класса `C3` в пространство имен `N1.N2`, как показано выше:</span><span class="sxs-lookup"><span data-stu-id="a1c26-142">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 <span data-ttu-id="a1c26-143">[!code-cs[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-143">[!code-cs[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]</span></span>  
  
 <span data-ttu-id="a1c26-144">В общем случае следует использовать `::` для ссылки на псевдоним пространства имен или `global::` для ссылки на глобальное пространство имен, а также `.` для определения типов или элементов.</span><span class="sxs-lookup"><span data-stu-id="a1c26-144">In general, use `::` to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="a1c26-145">Использование `::` с псевдонимом, ссылающимся на тип вместо пространства имен, будет ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a1c26-145">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="a1c26-146">Пример:</span><span class="sxs-lookup"><span data-stu-id="a1c26-146">For example:</span></span>  
  
 <span data-ttu-id="a1c26-147">[!code-cs[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-147">[!code-cs[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]</span></span>  
  
 <span data-ttu-id="a1c26-148">[!code-cs[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-148">[!code-cs[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]</span></span>  
  
 <span data-ttu-id="a1c26-149">Помните, что слово `global` не является предопределенным псевдонимом и, соответственно, выражение `global.X` не имеет какого-либо конкретного значения.</span><span class="sxs-lookup"><span data-stu-id="a1c26-149">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="a1c26-150">Конкретное значение будет получено только при его использовании вместе с `::`.</span><span class="sxs-lookup"><span data-stu-id="a1c26-150">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="a1c26-151">Если определить псевдоним с именем global, возникнет предупреждение компилятора CS0440. Это связано с тем, что `global::` всегда ссылается на глобальное пространство имен, а не на псевдоним.</span><span class="sxs-lookup"><span data-stu-id="a1c26-151">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="a1c26-152">Например, предупреждение возникнет в следующем случае:</span><span class="sxs-lookup"><span data-stu-id="a1c26-152">For example, the following line generates the warning:</span></span>  
  
 <span data-ttu-id="a1c26-153">[!code-cs[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-153">[!code-cs[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]</span></span>  
  
 <span data-ttu-id="a1c26-154">При работе с псевдонимами рекомендуется использовать `::`, поскольку это обеспечивает защиту от случайного определения дополнительных типов.</span><span class="sxs-lookup"><span data-stu-id="a1c26-154">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="a1c26-155">Рассмотрим следующий пример:</span><span class="sxs-lookup"><span data-stu-id="a1c26-155">For example, consider this example:</span></span>  
  
 <span data-ttu-id="a1c26-156">[!code-cs[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-156">[!code-cs[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]</span></span>  
  
 <span data-ttu-id="a1c26-157">[!code-cs[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]</span><span class="sxs-lookup"><span data-stu-id="a1c26-157">[!code-cs[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]</span></span>  
  
 <span data-ttu-id="a1c26-158">Этот код будет работать, однако если впоследствии определить тип с именем `Alias`, выражение `Alias.` будет связываться с этим типом.</span><span class="sxs-lookup"><span data-stu-id="a1c26-158">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="a1c26-159">Используя выражение `Alias::Exception`, вы гарантируете, что `Alias` будет обрабатываться как псевдоним пространства имен и не будет ошибочно связываться с типом.</span><span class="sxs-lookup"><span data-stu-id="a1c26-159">Using `Alias::Exception` insures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  
  
 <span data-ttu-id="a1c26-160">В разделе [Практическое руководство. Использование псевдонима глобального пространства имен](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) приводятся дополнительные сведения об использовании псевдонима `global`.</span><span class="sxs-lookup"><span data-stu-id="a1c26-160">See the topic [How to: Use the Global Namespace Alias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) for more information regarding the `global` alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c26-161">См. также</span><span class="sxs-lookup"><span data-stu-id="a1c26-161">See Also</span></span>  
 <span data-ttu-id="a1c26-162">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a1c26-162">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a1c26-163">[Пространства имен](../../../csharp/programming-guide/namespaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="a1c26-163">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 <span data-ttu-id="a1c26-164">[Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="a1c26-164">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="a1c26-165">[. Оператор](../../../csharp/language-reference/operators/member-access-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a1c26-165">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span></span>  
 <span data-ttu-id="a1c26-166">[Оператор ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="a1c26-166">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="a1c26-167">extern</span><span class="sxs-lookup"><span data-stu-id="a1c26-167">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)

