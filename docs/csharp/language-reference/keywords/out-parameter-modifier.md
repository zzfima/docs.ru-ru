---
title: "Модификатор параметров out (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 68ef554f95fe71f925cfa22cc49758cec3da237e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="903f2-102">Модификатор параметров out (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="903f2-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="903f2-103">Ключевое `out` инициирует передачу аргументов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="903f2-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="903f2-104">Оно схоже с ключевым словом [ref](../../../csharp/language-reference/keywords/ref.md) за исключением того, что при использовании `ref` перед передачей переменную необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="903f2-104">It is like the [ref](../../../csharp/language-reference/keywords/ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="903f2-105">Для применения параметра `out` определение метода и метод вызова должны явно использовать ключевое слово `out`.</span><span class="sxs-lookup"><span data-stu-id="903f2-105">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="903f2-106">Пример:</span><span class="sxs-lookup"><span data-stu-id="903f2-106">For example:</span></span>  
  
 [!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]  

> [!NOTE] 
> <span data-ttu-id="903f2-107">Ключевое слово `out` также можно использовать с параметром универсального типа для указания на то, что тип параметра является ковариантным.</span><span class="sxs-lookup"><span data-stu-id="903f2-107">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="903f2-108">Дополнительные сведения об использовании ключевого слова `out` в этом контексте см. в разделе [out (универсальный модификатор)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="903f2-108">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span></span>
  
 <span data-ttu-id="903f2-109">Переменные, передаваемые в качестве аргументов `out`, не требуется инициализировать перед передачей в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="903f2-109">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="903f2-110">Но перед передачей управления из вызванного метода он должен присвоить значение.</span><span class="sxs-lookup"><span data-stu-id="903f2-110">However, the called method is required to assign a value before the method returns.</span></span>  
  
 <span data-ttu-id="903f2-111">Несмотря на то, что ключевые слова `ref` и `out` вызвать другое поведение среды выполнения, они не считаются частью подписи метода во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="903f2-111">Although the `ref` and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="903f2-112">Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref`, а другой — аргумент `out`.</span><span class="sxs-lookup"><span data-stu-id="903f2-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="903f2-113">Следующий код, например, компилироваться не будет.</span><span class="sxs-lookup"><span data-stu-id="903f2-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="903f2-114">Перегрузка допустима, если один метод принимает аргумент `ref` или `out`, а другой не использует ни одного из них, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="903f2-114">Overloading is legal, however, if one method takes a `ref` or `out` argument and the other uses neither, like this:</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]  
  
 <span data-ttu-id="903f2-115">Свойства не являются переменными и поэтому не могут быть переданы как параметры `out`.</span><span class="sxs-lookup"><span data-stu-id="903f2-115">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>  
  
 <span data-ttu-id="903f2-116">Сведения о передаче массивов см. в разделе [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="903f2-116">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="903f2-117">Ключевые слова `ref` и `out` нельзя использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="903f2-117">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="903f2-118">Асинхронные методы, которые определяются с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="903f2-118">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="903f2-119">Методы итератора, которые включают оператор [yield return](../../../csharp/language-reference/keywords/yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="903f2-119">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="903f2-120">Объявление аргументов `out`</span><span class="sxs-lookup"><span data-stu-id="903f2-120">Declaring `out` arguments</span></span>   

 <span data-ttu-id="903f2-121">Объявление метода с аргументами `out` полезно в случае, если требуется, чтобы метод возвращал несколько значений.</span><span class="sxs-lookup"><span data-stu-id="903f2-121">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="903f2-122">В следующем примере используется `out` для возвращения трех переменных с помощью вызова одного метода.</span><span class="sxs-lookup"><span data-stu-id="903f2-122">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="903f2-123">Обратите внимание, что третьему аргумент присвоено значение null.</span><span class="sxs-lookup"><span data-stu-id="903f2-123">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="903f2-124">Это позволяет методам возвращать значения по желанию.</span><span class="sxs-lookup"><span data-stu-id="903f2-124">This enables methods to return values optionally.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]  

 <span data-ttu-id="903f2-125">[Шаблон Try](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) предполагает возврат значения типа `bool`, указывающего на успешность выполнения операции, и значения, полученного в результате операции, в аргументе `out`.</span><span class="sxs-lookup"><span data-stu-id="903f2-125">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="903f2-126">Этот шаблон используется несколькими методами анализа, например методом [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)).</span><span class="sxs-lookup"><span data-stu-id="903f2-126">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="903f2-127">Вызов метода с аргументом `out`</span><span class="sxs-lookup"><span data-stu-id="903f2-127">Calling a method with an `out` argument</span></span>

<span data-ttu-id="903f2-128">В C# 6 и более ранних версиях необходимо было объявлять переменную в отдельном операторе, прежде чем передавать ее как аргумент `out`.</span><span class="sxs-lookup"><span data-stu-id="903f2-128">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="903f2-129">В следующем примере переменная `number` объявляется перед передачей в метод [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), который пытается преобразовать строку в число.</span><span class="sxs-lookup"><span data-stu-id="903f2-129">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]  

<span data-ttu-id="903f2-130">Начиная с версии 7 языка C# переменную `out` можно объявлять в списке аргументов вызова метода, а не отдельно.</span><span class="sxs-lookup"><span data-stu-id="903f2-130">Starting with C# 7, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="903f2-131">Это делает код более кратким и удобным для восприятия, а также предотвращает непреднамеренное присвоение значения переменной перед вызовом метода.</span><span class="sxs-lookup"><span data-stu-id="903f2-131">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="903f2-132">Следующий пример аналогичен предыдущему за тем исключением, что переменная `number` объявляется в вызове метода [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="903f2-132">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]  
   
<span data-ttu-id="903f2-133">В предыдущем примере переменная `number` строго типизирована как `int`.</span><span class="sxs-lookup"><span data-stu-id="903f2-133">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="903f2-134">Вы также можете объявить неявно типизированную локальную переменную, как в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="903f2-134">You can also declare an implicitly typed local variable, as the following example does.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="903f2-135">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="903f2-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="903f2-136">См. также</span><span class="sxs-lookup"><span data-stu-id="903f2-136">See Also</span></span>  
 [<span data-ttu-id="903f2-137">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="903f2-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="903f2-138">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="903f2-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="903f2-139">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="903f2-139">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="903f2-140">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="903f2-140">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
