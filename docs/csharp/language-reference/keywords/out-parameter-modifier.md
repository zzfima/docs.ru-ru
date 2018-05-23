---
title: Модификатор параметров out (справочник по C#)
ms.date: 03/06/2018
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: 76c2c27d4575918bb2ed4209a7ff7d2b0517b6f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="8e276-102">Модификатор параметров out (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8e276-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="8e276-103">Ключевое `out` инициирует передачу аргументов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="8e276-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="8e276-104">Оно схоже с ключевым словом [ref](ref.md) за исключением того, что при использовании `ref` перед передачей переменную необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="8e276-104">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="8e276-105">Оно также похоже на ключевое слово [in](in-parameter-modifier.md) за исключением того, что `in` не позволяет вызываемому методу изменять значение аргумента.</span><span class="sxs-lookup"><span data-stu-id="8e276-105">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="8e276-106">Для применения параметра `out` определение метода и метод вызова должны явно использовать ключевое слово `out`.</span><span class="sxs-lookup"><span data-stu-id="8e276-106">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="8e276-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e276-107">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> <span data-ttu-id="8e276-108">Ключевое слово `out` также можно использовать с параметром универсального типа для указания на то, что тип параметра является ковариантным.</span><span class="sxs-lookup"><span data-stu-id="8e276-108">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="8e276-109">Дополнительные сведения об использовании ключевого слова `out` в этом контексте см. в разделе [out (универсальный модификатор)](out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="8e276-109">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="8e276-110">Переменные, передаваемые в качестве аргументов `out`, не требуется инициализировать перед передачей в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="8e276-110">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="8e276-111">Но перед передачей управления из вызванного метода он должен присвоить значение.</span><span class="sxs-lookup"><span data-stu-id="8e276-111">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="8e276-112">Хотя ключевые слова `in`, `ref` и `out` вызывают разное поведение во время выполнения, они не считаются частью сигнатуры метода во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="8e276-112">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="8e276-113">Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref` или `in`, а другой — `out`.</span><span class="sxs-lookup"><span data-stu-id="8e276-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="8e276-114">Следующий код, например, компилироваться не будет.</span><span class="sxs-lookup"><span data-stu-id="8e276-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="8e276-115">Перегрузка допустима, если один метод принимает аргумент `ref`, `in` или `out`, а другой не использует ни один из этих модификаторов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8e276-115">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="8e276-116">Компилятор выбирает наиболее подходящую перегрузку, сравнивая модификаторы параметров в месте вызова с модификаторами параметров в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="8e276-116">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>
 
<span data-ttu-id="8e276-117">Свойства не являются переменными и поэтому не могут быть переданы как параметры `out`.</span><span class="sxs-lookup"><span data-stu-id="8e276-117">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
 <span data-ttu-id="8e276-118">Сведения о передаче массивов см. в разделе [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="8e276-118">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="8e276-119">Ключевые слова `in`, `ref` и `out` запрещено использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="8e276-119">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="8e276-120">Асинхронные методы, которые определяются с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="8e276-120">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="8e276-121">Методы итератора, которые включают оператор [yield return](../../../csharp/language-reference/keywords/yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="8e276-121">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="8e276-122">Объявление аргументов `out`</span><span class="sxs-lookup"><span data-stu-id="8e276-122">Declaring `out` arguments</span></span>   

 <span data-ttu-id="8e276-123">Объявление метода с аргументами `out` полезно в случае, если требуется, чтобы метод возвращал несколько значений.</span><span class="sxs-lookup"><span data-stu-id="8e276-123">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="8e276-124">В следующем примере используется `out` для возвращения трех переменных с помощью вызова одного метода.</span><span class="sxs-lookup"><span data-stu-id="8e276-124">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="8e276-125">Обратите внимание, что третьему аргумент присвоено значение null.</span><span class="sxs-lookup"><span data-stu-id="8e276-125">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="8e276-126">Это позволяет методам возвращать значения по желанию.</span><span class="sxs-lookup"><span data-stu-id="8e276-126">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

 <span data-ttu-id="8e276-127">[Шаблон Try](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) предполагает возврат значения типа `bool`, указывающего на успешность выполнения операции, и значения, полученного в результате операции, в аргументе `out`.</span><span class="sxs-lookup"><span data-stu-id="8e276-127">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="8e276-128">Этот шаблон используется несколькими методами анализа, например методом [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)).</span><span class="sxs-lookup"><span data-stu-id="8e276-128">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="8e276-129">Вызов метода с аргументом `out`</span><span class="sxs-lookup"><span data-stu-id="8e276-129">Calling a method with an `out` argument</span></span>

<span data-ttu-id="8e276-130">В C# 6 и более ранних версиях необходимо было объявлять переменную в отдельном операторе, прежде чем передавать ее как аргумент `out`.</span><span class="sxs-lookup"><span data-stu-id="8e276-130">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="8e276-131">В следующем примере переменная `number` объявляется перед передачей в метод [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), который пытается преобразовать строку в число.</span><span class="sxs-lookup"><span data-stu-id="8e276-131">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="8e276-132">Начиная с C# версии 7.0 переменную `out` можно объявлять в списке аргументов вызова метода, а не отдельно.</span><span class="sxs-lookup"><span data-stu-id="8e276-132">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="8e276-133">Это делает код более кратким и удобным для восприятия, а также предотвращает непреднамеренное присвоение значения переменной перед вызовом метода.</span><span class="sxs-lookup"><span data-stu-id="8e276-133">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="8e276-134">Следующий пример аналогичен предыдущему за тем исключением, что переменная `number` объявляется в вызове метода [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="8e276-134">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
<span data-ttu-id="8e276-135">В предыдущем примере переменная `number` строго типизирована как `int`.</span><span class="sxs-lookup"><span data-stu-id="8e276-135">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="8e276-136">Вы также можете объявить неявно типизированную локальную переменную, как в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="8e276-136">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="8e276-137">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8e276-137">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e276-138">См. также</span><span class="sxs-lookup"><span data-stu-id="8e276-138">See Also</span></span>  
 [<span data-ttu-id="8e276-139">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8e276-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8e276-140">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8e276-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8e276-141">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="8e276-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8e276-142">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="8e276-142">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
