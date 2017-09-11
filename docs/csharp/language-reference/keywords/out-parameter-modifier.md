---
title: "Модификатор параметров out (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: 9
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
ms.sourcegitcommit: 59e445ac27f07c85d9e98c5f595cf5f935f75443
ms.openlocfilehash: 9a0a488c6f444608a335cd990847774fb6fe9e3f
ms.contentlocale: ru-ru
ms.lasthandoff: 08/31/2017

---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="4bbc4-102">Модификатор параметров out (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4bbc4-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="4bbc4-103">Ключевое `out` инициирует передачу аргументов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="4bbc4-104">Оно схоже с ключевым словом [ref](../../../csharp/language-reference/keywords/ref.md) за исключением того, что при использовании `ref` перед передачей переменную необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-104">It is like the [ref](../../../csharp/language-reference/keywords/ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="4bbc4-105">Для применения параметра `out` определение метода и метод вызова должны явно использовать ключевое слово `out`.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-105">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="4bbc4-106">Пример:</span><span class="sxs-lookup"><span data-stu-id="4bbc4-106">For example:</span></span>  
  
 <span data-ttu-id="4bbc4-107">[!code-cs[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4bbc4-107">[!code-cs[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="4bbc4-108">Ключевое слово `out` также можно использовать с параметром универсального типа для указания на то, что тип параметра является ковариантным.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-108">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="4bbc4-109">Дополнительные сведения об использовании ключевого слова `out` в этом контексте см. в разделе [out (универсальный модификатор)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="4bbc4-109">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span></span>
  
 <span data-ttu-id="4bbc4-110">Переменные, передаваемые в качестве аргументов `out`, не требуется инициализировать перед передачей в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-110">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="4bbc4-111">Но перед передачей управления из вызванного метода он должен присвоить значение.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-111">However, the called method is required to assign a value before the method returns.</span></span>  
  
 <span data-ttu-id="4bbc4-112">Несмотря на то, что ключевые слова `ref` и `out` вызвать другое поведение среды выполнения, они не считаются частью подписи метода во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-112">Although the `ref` and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="4bbc4-113">Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref`, а другой — аргумент `out`.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="4bbc4-114">Следующий код, например, компилироваться не будет.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="4bbc4-115">Перегрузка допустима, если один метод принимает аргумент `ref` или `out`, а другой не использует ни одного из них, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-115">Overloading is legal, however, if one method takes a `ref` or `out` argument and the other uses neither, like this:</span></span>  
  
 <span data-ttu-id="4bbc4-116">[!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="4bbc4-116">[!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]</span></span>  
  
 <span data-ttu-id="4bbc4-117">Свойства не являются переменными и поэтому не могут быть переданы как параметры `out`.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-117">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>  
  
 <span data-ttu-id="4bbc4-118">Сведения о передаче массивов см. в разделе [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="4bbc4-118">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="4bbc4-119">Ключевые слова `ref` и `out` нельзя использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-119">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="4bbc4-120">Асинхронные методы, которые определяются с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="4bbc4-120">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="4bbc4-121">Методы итератора, которые включают оператор [yield return](../../../csharp/language-reference/keywords/yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-121">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="4bbc4-122">Объявление аргументов `out`</span><span class="sxs-lookup"><span data-stu-id="4bbc4-122">Declaring `out` arguments</span></span>   

 <span data-ttu-id="4bbc4-123">Объявление метода с аргументами `out` полезно в случае, если требуется, чтобы метод возвращал несколько значений.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-123">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="4bbc4-124">В следующем примере используется `out` для возвращения трех переменных с помощью вызова одного метода.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-124">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="4bbc4-125">Обратите внимание, что третьему аргумент присвоено значение null.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-125">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="4bbc4-126">Это позволяет методам возвращать значения по желанию.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-126">This enables methods to return values optionally.</span></span>  
  
 <span data-ttu-id="4bbc4-127">[!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="4bbc4-127">[!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]</span></span>  

 <span data-ttu-id="4bbc4-128">[Шаблон Try](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) предполагает возврат значения типа `bool`, указывающего на успешность выполнения операции, и значения, полученного в результате операции, в аргументе `out`.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-128">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="4bbc4-129">Этот шаблон используется несколькими методами анализа, например методом [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)).</span><span class="sxs-lookup"><span data-stu-id="4bbc4-129">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="4bbc4-130">Вызов метода с аргументом `out`</span><span class="sxs-lookup"><span data-stu-id="4bbc4-130">Calling a method with an `out` argument</span></span>

<span data-ttu-id="4bbc4-131">В C# 6 и более ранних версиях необходимо было объявлять переменную в отдельном операторе, прежде чем передавать ее как аргумент `out`.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-131">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="4bbc4-132">В следующем примере переменная `number` объявляется перед передачей в метод [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), который пытается преобразовать строку в число.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-132">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

 <span data-ttu-id="4bbc4-133">[!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]</span><span class="sxs-lookup"><span data-stu-id="4bbc4-133">[!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]</span></span>  

<span data-ttu-id="4bbc4-134">Начиная с версии 7 языка C# переменную `out` можно объявлять в списке аргументов вызова метода, а не отдельно.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-134">Starting with C# 7, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="4bbc4-135">Это делает код более кратким и удобным для восприятия, а также предотвращает непреднамеренное присвоение значения переменной перед вызовом метода.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-135">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="4bbc4-136">Следующий пример аналогичен предыдущему за тем исключением, что переменная `number` объявляется в вызове метода [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="4bbc4-136">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

 <span data-ttu-id="4bbc4-137">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]</span><span class="sxs-lookup"><span data-stu-id="4bbc4-137">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]</span></span>  
   
<span data-ttu-id="4bbc4-138">В предыдущем примере переменная `number` строго типизирована как `int`.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-138">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="4bbc4-139">Вы также можете объявить неявно типизированную локальную переменную, как в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="4bbc4-139">You can also declare an implicitly typed local variable, as the following example does.</span></span>

 <span data-ttu-id="4bbc4-140">[!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]</span><span class="sxs-lookup"><span data-stu-id="4bbc4-140">[!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]</span></span>  
   
## <a name="c-language-specification"></a><span data-ttu-id="4bbc4-141">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4bbc4-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4bbc4-142">См. также</span><span class="sxs-lookup"><span data-stu-id="4bbc4-142">See Also</span></span>  
 <span data-ttu-id="4bbc4-143">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4bbc4-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4bbc4-144">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4bbc4-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4bbc4-145">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4bbc4-145">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="4bbc4-146">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="4bbc4-146">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

