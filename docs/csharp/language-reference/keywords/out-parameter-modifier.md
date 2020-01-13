---
title: Справочник по C#. Модификатор параметров out
ms.date: 03/26/2019
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: bc3814b91ed4327f4af1a4a1bfbda632b0393bb8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713274"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="813fe-102">Модификатор параметров out (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="813fe-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="813fe-103">Ключевое `out` инициирует передачу аргументов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="813fe-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="813fe-104">В результате этот формальный параметр становится псевдонимом для аргумента, который должен представлять собой переменную.</span><span class="sxs-lookup"><span data-stu-id="813fe-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="813fe-105">Другими словами, любая операция в параметре осуществляется с аргументом.</span><span class="sxs-lookup"><span data-stu-id="813fe-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="813fe-106">Оно схоже с ключевым словом [ref](ref.md) за исключением того, что при использовании `ref` перед передачей переменную необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="813fe-106">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="813fe-107">Оно также похоже на ключевое слово [in](in-parameter-modifier.md) за исключением того, что `in` не позволяет вызываемому методу изменять значение аргумента.</span><span class="sxs-lookup"><span data-stu-id="813fe-107">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="813fe-108">Для применения параметра `out` определение метода и метод вызова должны явно использовать ключевое слово `out`.</span><span class="sxs-lookup"><span data-stu-id="813fe-108">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="813fe-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="813fe-109">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> <span data-ttu-id="813fe-110">Ключевое слово `out` также можно использовать с параметром универсального типа для указания на то, что тип параметра является ковариантным.</span><span class="sxs-lookup"><span data-stu-id="813fe-110">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="813fe-111">Дополнительные сведения об использовании ключевого слова `out` в этом контексте см. в разделе [out (универсальный модификатор)](out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="813fe-111">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="813fe-112">Переменные, передаваемые в качестве аргументов `out`, не требуется инициализировать перед передачей в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="813fe-112">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="813fe-113">Но перед передачей управления из вызванного метода он должен присвоить значение.</span><span class="sxs-lookup"><span data-stu-id="813fe-113">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="813fe-114">Ключевые слова `in`, `ref` и `out` не считаются частью сигнатуры метода для разрешения перегрузки.</span><span class="sxs-lookup"><span data-stu-id="813fe-114">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="813fe-115">Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref` или `in`, а другой — `out`.</span><span class="sxs-lookup"><span data-stu-id="813fe-115">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="813fe-116">Следующий код, например, компилироваться не будет.</span><span class="sxs-lookup"><span data-stu-id="813fe-116">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="813fe-117">Перегрузка допустима, если один метод принимает аргумент `ref`, `in` или `out`, а другой не использует ни один из этих модификаторов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="813fe-117">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="813fe-118">Компилятор выбирает наиболее подходящую перегрузку, сравнивая модификаторы параметров в месте вызова с модификаторами параметров в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="813fe-118">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>
 
<span data-ttu-id="813fe-119">Свойства не являются переменными и поэтому не могут быть переданы как параметры `out`.</span><span class="sxs-lookup"><span data-stu-id="813fe-119">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="813fe-120">Ключевые слова `in`, `ref` и `out` запрещено использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="813fe-120">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="813fe-121">Асинхронные методы, которые определяются с помощью модификатора [async](./async.md).</span><span class="sxs-lookup"><span data-stu-id="813fe-121">Async methods, which you define by using the [async](./async.md) modifier.</span></span>  
  
- <span data-ttu-id="813fe-122">Методы итератора, которые включают оператор [yield return](./yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="813fe-122">Iterator methods, which include a [yield return](./yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-parameters"></a><span data-ttu-id="813fe-123">Объявление параметров `out`</span><span class="sxs-lookup"><span data-stu-id="813fe-123">Declaring `out` parameters</span></span>   

<span data-ttu-id="813fe-124">Объявление метода с аргументами `out` — стандартное решение для возвращения нескольких значений.</span><span class="sxs-lookup"><span data-stu-id="813fe-124">Declaring a method with `out` arguments is a classic workaround to return multiple values.</span></span> <span data-ttu-id="813fe-125">Начиная с версии C# 7.0, вы можете использовать [кортежи](../../tuples.md) для таких сценариев.</span><span class="sxs-lookup"><span data-stu-id="813fe-125">Beginning with C# 7.0, consider [tuples](../../tuples.md) for similar scenarios.</span></span> <span data-ttu-id="813fe-126">В следующем примере используется `out` для возвращения трех переменных с помощью вызова одного метода.</span><span class="sxs-lookup"><span data-stu-id="813fe-126">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="813fe-127">Обратите внимание, что третьему аргумент присвоено значение null.</span><span class="sxs-lookup"><span data-stu-id="813fe-127">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="813fe-128">Это позволяет методам возвращать значения по желанию.</span><span class="sxs-lookup"><span data-stu-id="813fe-128">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="813fe-129">Вызов метода с аргументом `out`</span><span class="sxs-lookup"><span data-stu-id="813fe-129">Calling a method with an `out` argument</span></span>

<span data-ttu-id="813fe-130">В C# 6 и более ранних версиях необходимо было объявлять переменную в отдельном операторе, прежде чем передавать ее как аргумент `out`.</span><span class="sxs-lookup"><span data-stu-id="813fe-130">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="813fe-131">В следующем примере переменная `number` объявляется перед передачей в метод [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), который пытается преобразовать строку в число.</span><span class="sxs-lookup"><span data-stu-id="813fe-131">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="813fe-132">Начиная с C# версии 7.0 переменную `out` можно объявлять в списке аргументов вызова метода, а не отдельно.</span><span class="sxs-lookup"><span data-stu-id="813fe-132">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="813fe-133">Это делает код более кратким и удобным для восприятия, а также предотвращает непреднамеренное присвоение значения переменной перед вызовом метода.</span><span class="sxs-lookup"><span data-stu-id="813fe-133">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="813fe-134">Следующий пример аналогичен предыдущему за тем исключением, что переменная `number` объявляется в вызове метода [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="813fe-134">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
<span data-ttu-id="813fe-135">В предыдущем примере переменная `number` строго типизирована как `int`.</span><span class="sxs-lookup"><span data-stu-id="813fe-135">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="813fe-136">Вы также можете объявить неявно типизированную локальную переменную, как в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="813fe-136">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="813fe-137">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="813fe-137">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="813fe-138">См. также</span><span class="sxs-lookup"><span data-stu-id="813fe-138">See also</span></span>

- [<span data-ttu-id="813fe-139">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="813fe-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="813fe-140">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="813fe-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="813fe-141">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="813fe-141">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="813fe-142">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="813fe-142">Method Parameters</span></span>](./method-parameters.md)
