---
title: "Анонимные методы (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 31
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
ms.openlocfilehash: 92842becf26a15ab1a6f5e9621002abf71dc67bc
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="anonymous-methods-c-programming-guide"></a><span data-ttu-id="58bec-102">Анонимные методы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="58bec-102">Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="58bec-103">В версиях языка C# до 2.0 объявить [делегат](../../../csharp/language-reference/keywords/delegate.md) можно было только с помощью [именованных методов](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="58bec-103">In versions of C# before 2.0, the only way to declare a [delegate](../../../csharp/language-reference/keywords/delegate.md) was to use [named methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span></span> <span data-ttu-id="58bec-104">В версии C# 2.0 были представлены анонимные методы, в версии C# 3.0 и более поздних замененные лямбда-выражениями, которые теперь рекомендуется использовать для написания встроенного кода.</span><span class="sxs-lookup"><span data-stu-id="58bec-104">C# 2.0 introduced anonymous methods and in C# 3.0 and later, lambda expressions supersede anonymous methods as the preferred way to write inline code.</span></span> <span data-ttu-id="58bec-105">Тем не менее сведения об анонимных методах из этого раздела также относятся и к лямбда-выражениям.</span><span class="sxs-lookup"><span data-stu-id="58bec-105">However, the information about anonymous methods in this topic also applies to lambda expressions.</span></span> <span data-ttu-id="58bec-106">В одном случае анонимные методы реализуют функциональные возможности, недоступные при использовании лямбда-выражений.</span><span class="sxs-lookup"><span data-stu-id="58bec-106">There is one case in which an anonymous method provides functionality not found in lambda expressions.</span></span> <span data-ttu-id="58bec-107">При использовании анонимных методов можно опустить список параметров.</span><span class="sxs-lookup"><span data-stu-id="58bec-107">Anonymous methods enable you to omit the parameter list.</span></span> <span data-ttu-id="58bec-108">Это значит, что анонимный метод может быть преобразован в делегаты с различными сигнатурами.</span><span class="sxs-lookup"><span data-stu-id="58bec-108">This means that an anonymous method can be converted to delegates with a variety of signatures.</span></span> <span data-ttu-id="58bec-109">При работе с лямбда-выражениями это невозможно.</span><span class="sxs-lookup"><span data-stu-id="58bec-109">This is not possible with lambda expressions.</span></span> <span data-ttu-id="58bec-110">Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="58bec-110">For more information specifically about lambda expressions, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="58bec-111">Создавая анонимные методы, вы фактически передаете блок кода в качестве параметра делегата.</span><span class="sxs-lookup"><span data-stu-id="58bec-111">Creating anonymous methods is essentially a way to pass a code block as a delegate parameter.</span></span> <span data-ttu-id="58bec-112">Вот два примера.</span><span class="sxs-lookup"><span data-stu-id="58bec-112">Here are two examples:</span></span>  
  
 <span data-ttu-id="58bec-113">[!code-cs[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="58bec-113">[!code-cs[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="58bec-114">[!code-cs[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="58bec-114">[!code-cs[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="58bec-115">Использование анонимных методов позволяет сократить время на написание кода для создания экземпляров делегатов, поскольку в этом случае не требуется создавать отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="58bec-115">By using anonymous methods, you reduce the coding overhead in instantiating delegates because you do not have to create a separate method.</span></span>  
  
 <span data-ttu-id="58bec-116">Например, можно указать блок кода вместо делегата в том случае, когда создание отдельного метода выглядит излишним.</span><span class="sxs-lookup"><span data-stu-id="58bec-116">For example, specifying a code block instead of a delegate can be useful in a situation when having to create a method might seem an unnecessary overhead.</span></span> <span data-ttu-id="58bec-117">В качестве примера можно привести создание нового потока.</span><span class="sxs-lookup"><span data-stu-id="58bec-117">A good example would be when you start a new thread.</span></span> <span data-ttu-id="58bec-118">Этот класс создает поток и также может содержать код, который выполняется потоком, причем для этого не требуется добавлять дополнительный метод делегата.</span><span class="sxs-lookup"><span data-stu-id="58bec-118">This class creates a thread and also contains the code that the thread executes without creating an additional method for the delegate.</span></span>  
  
 <span data-ttu-id="58bec-119">[!code-cs[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="58bec-119">[!code-cs[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58bec-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="58bec-120">Remarks</span></span>  
 <span data-ttu-id="58bec-121">Областью действия параметров анонимного метода является *блок анонимного метода*.</span><span class="sxs-lookup"><span data-stu-id="58bec-121">The scope of the parameters of an anonymous method is the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="58bec-122">Использование инструкций перехода, таких как [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) или [continue](../../../csharp/language-reference/keywords/continue.md), внутри блока анонимного метода является ошибкой в том случае, если цель перехода располагается за пределами блока.</span><span class="sxs-lookup"><span data-stu-id="58bec-122">It is an error to have a jump statement, such as [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md), or [continue](../../../csharp/language-reference/keywords/continue.md), inside the anonymous method block if the target is outside the block.</span></span> <span data-ttu-id="58bec-123">Также ошибкой будет использование инструкции перехода, такой как `goto`, `break` или `continue`, вне блока анонимного метода, если цель перехода располагается внутри этого блока.</span><span class="sxs-lookup"><span data-stu-id="58bec-123">It is also an error to have a jump statement, such as `goto`, `break`, or `continue`, outside the anonymous method block if the target is inside the block.</span></span>  
  
 <span data-ttu-id="58bec-124">Локальные переменные и параметры, область действия которых включает объявление анонимного метода, называются *внешними* переменными анонимного метода.</span><span class="sxs-lookup"><span data-stu-id="58bec-124">The local variables and parameters whose scope contains an anonymous method declaration are called *outer* variables of the anonymous method.</span></span> <span data-ttu-id="58bec-125">Например, в следующем фрагменте кода `n` является внешней переменной:</span><span class="sxs-lookup"><span data-stu-id="58bec-125">For example, in the following code segment, `n` is an outer variable:</span></span>  
  
 <span data-ttu-id="58bec-126">[!code-cs[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="58bec-126">[!code-cs[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]</span></span>  
  
 <span data-ttu-id="58bec-127">Ссылка на внешнюю переменную `n` при создании делегата считается *захваченной*.</span><span class="sxs-lookup"><span data-stu-id="58bec-127">A reference to the outer variable `n` is said to be *captured* when the delegate is created.</span></span> <span data-ttu-id="58bec-128">В отличие от локальных переменных, время существования захваченной переменной длится до тех пор, пока делегаты, ссылающиеся на анонимные методы, могут участвовать в сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="58bec-128">Unlike local variables, the lifetime of a captured variable extends until the delegates that reference the anonymous methods are eligible for garbage collection.</span></span>  
  
 <span data-ttu-id="58bec-129">Анонимный метод не может получить доступ к параметрам [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out.md) во внешней области действия.</span><span class="sxs-lookup"><span data-stu-id="58bec-129">An anonymous method cannot access the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters of an outer scope.</span></span>  
  
 <span data-ttu-id="58bec-130">Также невозможен доступ к небезопасному коду из *блока анонимного метода*.</span><span class="sxs-lookup"><span data-stu-id="58bec-130">No unsafe code can be accessed within the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="58bec-131">Анонимные методы нельзя использовать в левой части оператора [is](../../../csharp/language-reference/keywords/is.md).</span><span class="sxs-lookup"><span data-stu-id="58bec-131">Anonymous methods are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58bec-132">Пример</span><span class="sxs-lookup"><span data-stu-id="58bec-132">Example</span></span>  
 <span data-ttu-id="58bec-133">В следующем примере показаны два способа создания экземпляра делегата:</span><span class="sxs-lookup"><span data-stu-id="58bec-133">The following example demonstrates two ways of instantiating a delegate:</span></span>  
  
-   <span data-ttu-id="58bec-134">Связывание делегата с анонимным методом.</span><span class="sxs-lookup"><span data-stu-id="58bec-134">Associating the delegate with an anonymous method.</span></span>  
  
-   <span data-ttu-id="58bec-135">Связывание делегата с именованным методом (`DoWork`).</span><span class="sxs-lookup"><span data-stu-id="58bec-135">Associating the delegate with a named method (`DoWork`).</span></span>  
  
 <span data-ttu-id="58bec-136">В обоих случаях при вызове делегата отображается сообщение.</span><span class="sxs-lookup"><span data-stu-id="58bec-136">In each case, a message is displayed when the delegate is invoked.</span></span>  
  
 <span data-ttu-id="58bec-137">[!code-cs[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="58bec-137">[!code-cs[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58bec-138">См. также</span><span class="sxs-lookup"><span data-stu-id="58bec-138">See Also</span></span>  
 <span data-ttu-id="58bec-139">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="58bec-139">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="58bec-140">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="58bec-140">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="58bec-141">[Делегаты](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="58bec-141">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="58bec-142">[Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="58bec-142">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 <span data-ttu-id="58bec-143">[Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="58bec-143">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="58bec-144">[Methods (C# Programming Guide)](../../../csharp/programming-guide/classes-and-structs/methods.md)  (Методы (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="58bec-144">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 [<span data-ttu-id="58bec-145">Делегаты с именованными методами и делегаты с анонимными методами</span><span class="sxs-lookup"><span data-stu-id="58bec-145">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)

