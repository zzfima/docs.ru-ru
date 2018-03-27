---
title: Модификатор параметров in (справочник по C#)
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9b8b21e2bdc95829c831ee71f24b47986321b7d0
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2018
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="9075c-102">Модификатор параметров in (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9075c-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="9075c-103">Ключевое `in` инициирует передачу аргументов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="9075c-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="9075c-104">Оно похоже на ключевые слова [ref](ref.md) или [out](out-parameter-modifier.md) за исключением того, что аргументы `in` не могут быть изменены вызываемым методом, тогда как аргументы `ref` могут быть изменены, аргументы `out` должны быть изменены вызывающим объектом, и такие изменения можно наблюдать в контексте вызова.</span><span class="sxs-lookup"><span data-stu-id="9075c-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method, whereas `ref` arguments may be modified,  `out` arguments must be modified by the caller, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="9075c-105">Предыдущий пример показывает, что модификатор `in` не требуется в месте вызова.</span><span class="sxs-lookup"><span data-stu-id="9075c-105">The preceding example demonstrates that the `in` modifier is unnecessary at the call site.</span></span> <span data-ttu-id="9075c-106">Он нужен только в объявлении метода.</span><span class="sxs-lookup"><span data-stu-id="9075c-106">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="9075c-107">Ключевое слово `in` также можно использовать с параметром универсального типа для указания на то, что тип параметра является контравариантным, в рамках оператора `foreach` или предложения `join` в запросе LINQ.</span><span class="sxs-lookup"><span data-stu-id="9075c-107">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="9075c-108">Дополнительные сведения об использовании ключевого слова `in` в таких контекстах см. в разделе [in](in.md), где приведены все соответствующие ссылки.</span><span class="sxs-lookup"><span data-stu-id="9075c-108">For more information on the use of the `in` keyword in these contexts, see [in](in.md) which provides links to all those uses.</span></span>
  
 <span data-ttu-id="9075c-109">Переменные, передаваемые в качестве аргументов `in`, требуется инициализировать перед передачей в вызов метода.</span><span class="sxs-lookup"><span data-stu-id="9075c-109">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="9075c-110">Но вызванный метод не может присвоить значение или изменить аргумент.</span><span class="sxs-lookup"><span data-stu-id="9075c-110">However, the called method may not assign a value or modify the argument.</span></span>  
  
 <span data-ttu-id="9075c-111">Хотя ключевые слова `in`, `ref` и `out` вызывают разное поведение во время выполнения, они не считаются частью сигнатуры метода во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="9075c-111">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="9075c-112">Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref` или `in`, а другой — `out`.</span><span class="sxs-lookup"><span data-stu-id="9075c-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="9075c-113">Следующий код, например, компилироваться не будет.</span><span class="sxs-lookup"><span data-stu-id="9075c-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="9075c-114">Перегрузка, основанная на наличии `in`, допустима, но приводит к возникновению предупреждения компилятора.</span><span class="sxs-lookup"><span data-stu-id="9075c-114">Overloading based on the presence of `in` is allowed, but generates a compiler warning:</span></span>  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

<span data-ttu-id="9075c-115">Свойства или константы можно передавать в качестве параметров `in`, так как вызывающий метод не может изменять их значения.</span><span class="sxs-lookup"><span data-stu-id="9075c-115">Properties or constants may be passed as `in` parameters, because the calling method may not modify their values.</span></span>
  
<span data-ttu-id="9075c-116">Ключевые слова `in`, `ref` и `out` запрещено использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="9075c-116">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="9075c-117">Асинхронные методы, которые определяются с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="9075c-117">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
- <span data-ttu-id="9075c-118">Методы итератора, которые включают оператор [yield return](../../../csharp/language-reference/keywords/yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="9075c-118">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="9075c-119">Аргументы `in` обычно объявляется, чтобы предотвратить операции копирования, необходимые для передачи аргументов по значению.</span><span class="sxs-lookup"><span data-stu-id="9075c-119">You typically declare `in` arguments to avoid the copy operations necessary for passing arguments by value.</span></span> <span data-ttu-id="9075c-120">Это наиболее эффективно в тех случаях, когда аргументы являются такими типами значений, как структуры, где операции копирования требуют больше ресурсов, чем передача по ссылке.</span><span class="sxs-lookup"><span data-stu-id="9075c-120">This is most useful when arguments are value types such as structures where copy operations are more expensive than passing by reference.</span></span>

> [!WARNING]
>  <span data-ttu-id="9075c-121">Параметры `in` могут потреблять еще больше ресурсов при неправильном использовании.</span><span class="sxs-lookup"><span data-stu-id="9075c-121">`in` parameters can be even more expensive if misused.</span></span> <span data-ttu-id="9075c-122">Компилятор может не знать, изменяют ли методы элемента состояние структуры.</span><span class="sxs-lookup"><span data-stu-id="9075c-122">The compiler may not know if member methods modify the state of the struct.</span></span> <span data-ttu-id="9075c-123">Если компилятор не может защитить объект от изменений, он на всякий случай создает копию и с ее помощью вызывает ссылки на члены.</span><span class="sxs-lookup"><span data-stu-id="9075c-123">Whenever the compiler cannot ensure that the object is not modified, it defensively creates a copy and calls member references using that copy.</span></span> <span data-ttu-id="9075c-124">Любые возможные изменения будут вноситься в эту защитную копию.</span><span class="sxs-lookup"><span data-stu-id="9075c-124">Any possible modifications are to that defensive copy.</span></span> <span data-ttu-id="9075c-125">Есть два способа избежать копирования: передать параметры `in` в виде аргументов `in` или определить структуры как `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="9075c-125">The two ways to avoid these copies are to pass `in` parameters as `in` arguments or to define structures as `readonly struct`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9075c-126">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9075c-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9075c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="9075c-127">See Also</span></span>  
 [<span data-ttu-id="9075c-128">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9075c-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9075c-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9075c-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9075c-130">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="9075c-130">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="9075c-131">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="9075c-131">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)  
 [<span data-ttu-id="9075c-132">Семантика ссылок с типами значений</span><span class="sxs-lookup"><span data-stu-id="9075c-132">Reference Semantics with Value Types</span></span>](../../../csharp/reference-semantics-with-value-types.md)
