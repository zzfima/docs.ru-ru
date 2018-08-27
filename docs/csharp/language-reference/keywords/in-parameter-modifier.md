---
title: Модификатор параметров in (справочник по C#)
ms.date: 03/06/2018
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: 913957e6afad1d9d516a01f4bb0e377b94a40aea
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924992"
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="1422b-102">Модификатор параметров in (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1422b-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="1422b-103">Ключевое `in` инициирует передачу аргументов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="1422b-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="1422b-104">Оно аналогично ключевым словам [ref](ref.md) и [out](out-parameter-modifier.md), за исключением того, что аргументы `in` не могут быть изменены вызываемым методом.</span><span class="sxs-lookup"><span data-stu-id="1422b-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method.</span></span> <span data-ttu-id="1422b-105">В то время как аргументы `ref` могут быть изменены, аргументы `out` должны быть изменены вызывающим объектом, и эти изменения отслеживаются в вызывающем контексте.</span><span class="sxs-lookup"><span data-stu-id="1422b-105">Whereas `ref` arguments may be modified,  `out` arguments must be modified by the caller, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="1422b-106">Предыдущий пример показывает, что модификатор `in` обычно не требуется в месте вызова.</span><span class="sxs-lookup"><span data-stu-id="1422b-106">The preceding example demonstrates that the `in` modifier is usually unnecessary at the call site.</span></span> <span data-ttu-id="1422b-107">Он нужен только в объявлении метода.</span><span class="sxs-lookup"><span data-stu-id="1422b-107">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="1422b-108">Ключевое слово `in` также можно использовать с параметром универсального типа для указания на то, что тип параметра является контравариантным, в рамках оператора `foreach` или предложения `join` в запросе LINQ.</span><span class="sxs-lookup"><span data-stu-id="1422b-108">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="1422b-109">Дополнительные сведения об использовании ключевого слова `in` в таких контекстах см. в разделе [in](in.md), где приведены все соответствующие ссылки.</span><span class="sxs-lookup"><span data-stu-id="1422b-109">For more information on the use of the `in` keyword in these contexts, see [in](in.md), which provides links to all those uses.</span></span>
  
 <span data-ttu-id="1422b-110">Переменные, передаваемые в качестве аргументов `in`, требуется инициализировать перед передачей в вызов метода.</span><span class="sxs-lookup"><span data-stu-id="1422b-110">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="1422b-111">Но вызванный метод не может присвоить значение или изменить аргумент.</span><span class="sxs-lookup"><span data-stu-id="1422b-111">However, the called method may not assign a value or modify the argument.</span></span>  
  
 <span data-ttu-id="1422b-112">Хотя ключевые слова `in`, `ref` и `out` вызывают разное поведение во время выполнения, они не считаются частью сигнатуры метода во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="1422b-112">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="1422b-113">Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref` или `in`, а другой — `out`.</span><span class="sxs-lookup"><span data-stu-id="1422b-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="1422b-114">Следующий код, например, компилироваться не будет.</span><span class="sxs-lookup"><span data-stu-id="1422b-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="1422b-115">Перегрузка, основанная на наличии `in`, допустима:</span><span class="sxs-lookup"><span data-stu-id="1422b-115">Overloading based on the presence of `in` is allowed:</span></span>  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a><span data-ttu-id="1422b-116">Правила разрешения перегрузки</span><span class="sxs-lookup"><span data-stu-id="1422b-116">Overload resolution rules</span></span>

<span data-ttu-id="1422b-117">Разобраться в правилах разрешения перегрузки для методов по значению и аргументам `in` можно, поняв основания для применения аргументов `in`.</span><span class="sxs-lookup"><span data-stu-id="1422b-117">You can understand the overload resolution rules for methods with by value vs. `in` arguments by understanding the motivation for `in` arguments.</span></span> <span data-ttu-id="1422b-118">Определение методов с помощью параметров `in` является потенциальной оптимизацией производительности.</span><span class="sxs-lookup"><span data-stu-id="1422b-118">Defining methods using `in` parameters is a potential performance optimization.</span></span> <span data-ttu-id="1422b-119">Некоторые аргументы типа `struct` могут иметь большой размер, и при вызове методов в ограниченных циклах или критических путях кода стоимость копирования этих структур имеет определяющее значение.</span><span class="sxs-lookup"><span data-stu-id="1422b-119">Some `struct` type arguments may be large in size, and when methods are called in tight loops or critical code paths, the cost of copying those structures is critical.</span></span> <span data-ttu-id="1422b-120">Методы объявляют параметры `in`, чтобы указать, что аргументы можно безопасно передавать по ссылке, так как вызываемый метод не изменяет состояние этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="1422b-120">Methods declare `in` parameters to specify that arguments may be passed by reference safely because the called method does not modify the state of that argument.</span></span> <span data-ttu-id="1422b-121">Передача этих аргументов по ссылке позволяет избежать (потенциально) дорогого копирования.</span><span class="sxs-lookup"><span data-stu-id="1422b-121">Passing those arguments by reference avoids the (potentially) expensive copy.</span></span> 

<span data-ttu-id="1422b-122">Указывать `in` для аргументов в месте вызова обычно необязательно.</span><span class="sxs-lookup"><span data-stu-id="1422b-122">Specifying `in` for arguments at the call site is typically optional.</span></span> <span data-ttu-id="1422b-123">Нет семантического различия между передачей аргументов по значению и передачей их по ссылке с помощью модификатора `in`.</span><span class="sxs-lookup"><span data-stu-id="1422b-123">There is no semantic difference between passing arguments by value and passing them by reference using the `in` modifier.</span></span> <span data-ttu-id="1422b-124">Модификатор `in` в месте вызова является необязательным, так как не нужно указывать, что значение аргумента может изменяться.</span><span class="sxs-lookup"><span data-stu-id="1422b-124">The `in` modifier at the call site is optional because you don't need to indicate that the argument's value might be changed.</span></span> <span data-ttu-id="1422b-125">Вы явным образом добавляете модификатор `in` в место вызова, чтобы аргумент передавался по ссылке, а не по значению.</span><span class="sxs-lookup"><span data-stu-id="1422b-125">You explicitly add the `in` modifier at the call site to ensure the argument is passed by reference, not by value.</span></span> <span data-ttu-id="1422b-126">Явное использование `in` приводит к двум результатам.</span><span class="sxs-lookup"><span data-stu-id="1422b-126">Explicitly using `in` has the following two effects:</span></span>

<span data-ttu-id="1422b-127">Во-первых, указание `in` в месте вызова вынуждает компилятор выбрать метод, определенный с помощью соответствующего параметра `in`.</span><span class="sxs-lookup"><span data-stu-id="1422b-127">First, specifying `in` at the call site forces the compiler to select a method defined with a matching `in` parameter.</span></span> <span data-ttu-id="1422b-128">В противном случае, когда два метода отличаются только наличием `in`, перегрузка по значению подходит лучше.</span><span class="sxs-lookup"><span data-stu-id="1422b-128">Otherwise, when two methods differ only in the presence of `in`, the by value overload is a better match.</span></span>

<span data-ttu-id="1422b-129">Во-вторых, указав `in`, вы объявляете о намерении передать аргумент по ссылке.</span><span class="sxs-lookup"><span data-stu-id="1422b-129">Second, specifying `in` declares your intent to pass an argument by reference.</span></span> <span data-ttu-id="1422b-130">Аргумент, используемый с `in`, должен представлять расположение, на которое можно сослаться напрямую.</span><span class="sxs-lookup"><span data-stu-id="1422b-130">The argument used with `in` must represent a location that can be directly referred to.</span></span> <span data-ttu-id="1422b-131">Те же общие правила применяются для аргументов `out` и `ref`: вы не можете использовать константы, обычные свойства или другие выражения, возвращающие значения.</span><span class="sxs-lookup"><span data-stu-id="1422b-131">The same general rules for `out` and `ref` arguments apply: You cannot use constants, ordinary properties, or other expressions that produce values.</span></span> <span data-ttu-id="1422b-132">В противном случае пропуск `in` в месте вызова сообщает компилятору, что вы разрешите ему создать временную переменную для передачи с помощью ссылки на метод, доступной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1422b-132">Otherwise, omitting `in` at the call site informs the compiler that you will allow it to create a temporary variable to pass by read-only reference to the method.</span></span> <span data-ttu-id="1422b-133">Компилятор создает временную переменную, чтобы преодолеть некоторые ограничения для аргументов `in`:</span><span class="sxs-lookup"><span data-stu-id="1422b-133">The compiler creates a temporary variable to overcome several restrictions with `in` arguments:</span></span>

- <span data-ttu-id="1422b-134">Временная переменная позволяет использовать константы времени компиляции, например параметры `in`.</span><span class="sxs-lookup"><span data-stu-id="1422b-134">A temporary variable allows compile-time constants as `in` parameters.</span></span>
- <span data-ttu-id="1422b-135">Временная переменная позволяет использовать свойства или другие выражения для параметров `in`.</span><span class="sxs-lookup"><span data-stu-id="1422b-135">A temporary variable allows properties, or other expressions for `in` parameters.</span></span>
- <span data-ttu-id="1422b-136">Временная переменная позволяет использовать аргументы, где выполняется неявное преобразование из типа аргумента в тип параметра.</span><span class="sxs-lookup"><span data-stu-id="1422b-136">A temporary variable allows arguments where there is an implicit conversion from the argument type to the parameter type.</span></span>

<span data-ttu-id="1422b-137">Во всех предыдущих случаях компилятор создает временную переменную, хранящую значение константы, свойства или другого выражения.</span><span class="sxs-lookup"><span data-stu-id="1422b-137">In all the preceding instances, the compiler creates a temporary variable that stores the value of the constant, property, or other expression.</span></span>

<span data-ttu-id="1422b-138">Эти правила проиллюстрированы в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="1422b-138">The following code illustrates these rules:</span></span>

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="1422b-139">Теперь предположим, что был доступен другой метод, использующий аргументы по значению.</span><span class="sxs-lookup"><span data-stu-id="1422b-139">Now, suppose another method using by value arguments was available.</span></span> <span data-ttu-id="1422b-140">Результаты изменяются, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="1422b-140">The results change as shown in the following code:</span></span>

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="1422b-141">Аргумент передается по ссылке только в последнем вызове метода.</span><span class="sxs-lookup"><span data-stu-id="1422b-141">The only method call where the argument is passed by reference is the final one.</span></span>

> [!NOTE]
> <span data-ttu-id="1422b-142">Для простоты предыдущий код использует `int` в качестве типа аргумента.</span><span class="sxs-lookup"><span data-stu-id="1422b-142">The preceding code uses `int` as the argument type for simplicity.</span></span> <span data-ttu-id="1422b-143">Так как по размеру `int` не больше ссылки на большинстве современных компьютеров, не имеет смысла передавать один `int` в качестве ссылки, доступной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1422b-143">Because `int` is no larger than a reference in most modern machines, there is no benefit to passing a single `int` as a readonly reference.</span></span> 

## <a name="limitations-on-in-parameters"></a><span data-ttu-id="1422b-144">Ограничения для параметров `in`</span><span class="sxs-lookup"><span data-stu-id="1422b-144">Limitations on `in` parameters</span></span>

<span data-ttu-id="1422b-145">Ключевые слова `in`, `ref` и `out` запрещено использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="1422b-145">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="1422b-146">Асинхронные методы, которые определяются с помощью модификатора [async](async.md).</span><span class="sxs-lookup"><span data-stu-id="1422b-146">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="1422b-147">Методы итератора, которые включают оператор [yield return](yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="1422b-147">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="1422b-148">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="1422b-148">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1422b-149">См. также</span><span class="sxs-lookup"><span data-stu-id="1422b-149">See Also</span></span>  
 [<span data-ttu-id="1422b-150">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1422b-150">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="1422b-151">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1422b-151">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="1422b-152">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="1422b-152">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="1422b-153">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="1422b-153">Method Parameters</span></span>](method-parameters.md)  
 [<span data-ttu-id="1422b-154">Семантика ссылок с типами значений</span><span class="sxs-lookup"><span data-stu-id="1422b-154">Reference Semantics with Value Types</span></span>](../../reference-semantics-with-value-types.md)  
