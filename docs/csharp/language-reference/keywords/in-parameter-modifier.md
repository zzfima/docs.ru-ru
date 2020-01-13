---
title: Справочник по C#. Модификатор параметров in
ms.date: 03/26/2019
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: 10e7b91f9a6bf280c5f0654b243492bac8cde1e0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715251"
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="c2a8b-102">Модификатор параметров in (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c2a8b-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="c2a8b-103">Ключевое `in` инициирует передачу аргументов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="c2a8b-104">В результате этот формальный параметр становится псевдонимом для аргумента, который должен представлять собой переменную.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="c2a8b-105">Другими словами, любая операция в параметре осуществляется с аргументом.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="c2a8b-106">Оно аналогично ключевым словам [ref](ref.md) и [out](out-parameter-modifier.md), за исключением того, что аргументы `in` не могут быть изменены вызываемым методом.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-106">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method.</span></span> <span data-ttu-id="c2a8b-107">В то время как аргументы `ref` могут быть изменены, аргументы `out` должны быть изменены вызывающим объектом, и эти изменения отслеживаются в вызывающем контексте.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-107">Whereas `ref` arguments may be modified, `out` arguments must be modified by the called method, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="c2a8b-108">Предыдущий пример показывает, что модификатор `in` обычно не требуется в месте вызова.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-108">The preceding example demonstrates that the `in` modifier is usually unnecessary at the call site.</span></span> <span data-ttu-id="c2a8b-109">Он нужен только в объявлении метода.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-109">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="c2a8b-110">Ключевое слово `in` также можно использовать с параметром универсального типа для указания на то, что тип параметра является контравариантным, в рамках оператора `foreach` или предложения `join` в запросе LINQ.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-110">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="c2a8b-111">Дополнительные сведения об использовании ключевого слова `in` в таких контекстах см. в разделе [in](in.md), где приведены все соответствующие ссылки.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-111">For more information on the use of the `in` keyword in these contexts, see [in](in.md), which provides links to all those uses.</span></span>
  
<span data-ttu-id="c2a8b-112">Переменные, передаваемые в качестве аргументов `in`, требуется инициализировать перед передачей в вызов метода.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-112">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="c2a8b-113">Но вызванный метод не может присвоить значение или изменить аргумент.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-113">However, the called method may not assign a value or modify the argument.</span></span>  

<span data-ttu-id="c2a8b-114">Модификатор параметра `in` доступен в C# 7.2 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-114">The `in` parameter modifier is available in C# 7.2 and later.</span></span> <span data-ttu-id="c2a8b-115">Предыдущие версии создают ошибку компилятора `CS8107` ("Функция "Ссылки только для чтения" недоступна в C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-115">Previous versions generate compiler error `CS8107` ("Feature 'readonly references' is not available in C# 7.0.</span></span> <span data-ttu-id="c2a8b-116">Используйте языковую версию 7.2 или выше"), чтобы настроить языковую версию компилятора, см. [Выбор версии языка C#](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="c2a8b-116">Please use language version 7.2 or greater.") To configure the compiler language version, see [Select the C# language version](../configure-language-version.md).</span></span>

<span data-ttu-id="c2a8b-117">Ключевые слова `in`, `ref` и `out` не считаются частью сигнатуры метода для разрешения перегрузки.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-117">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="c2a8b-118">Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref` или `in`, а другой — `out`.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-118">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="c2a8b-119">Следующий код, например, компилироваться не будет.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-119">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="c2a8b-120">Перегрузка, основанная на наличии `in`, допустима:</span><span class="sxs-lookup"><span data-stu-id="c2a8b-120">Overloading based on the presence of `in` is allowed:</span></span>  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a><span data-ttu-id="c2a8b-121">Правила разрешения перегрузки</span><span class="sxs-lookup"><span data-stu-id="c2a8b-121">Overload resolution rules</span></span>

<span data-ttu-id="c2a8b-122">Разобраться в правилах разрешения перегрузки для методов по значению и аргументам `in` можно, поняв основания для применения аргументов `in`.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-122">You can understand the overload resolution rules for methods with by value vs. `in` arguments by understanding the motivation for `in` arguments.</span></span> <span data-ttu-id="c2a8b-123">Определение методов с помощью параметров `in` является потенциальной оптимизацией производительности.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-123">Defining methods using `in` parameters is a potential performance optimization.</span></span> <span data-ttu-id="c2a8b-124">Некоторые аргументы типа `struct` могут иметь большой размер, и при вызове методов в ограниченных циклах или критических путях кода стоимость копирования этих структур имеет определяющее значение.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-124">Some `struct` type arguments may be large in size, and when methods are called in tight loops or critical code paths, the cost of copying those structures is critical.</span></span> <span data-ttu-id="c2a8b-125">Методы объявляют параметры `in`, чтобы указать, что аргументы можно безопасно передавать по ссылке, так как вызываемый метод не изменяет состояние этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-125">Methods declare `in` parameters to specify that arguments may be passed by reference safely because the called method does not modify the state of that argument.</span></span> <span data-ttu-id="c2a8b-126">Передача этих аргументов по ссылке позволяет избежать (потенциально) дорогого копирования.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-126">Passing those arguments by reference avoids the (potentially) expensive copy.</span></span> 

<span data-ttu-id="c2a8b-127">Указывать `in` для аргументов в месте вызова обычно необязательно.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-127">Specifying `in` for arguments at the call site is typically optional.</span></span> <span data-ttu-id="c2a8b-128">Нет семантического различия между передачей аргументов по значению и передачей их по ссылке с помощью модификатора `in`.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-128">There is no semantic difference between passing arguments by value and passing them by reference using the `in` modifier.</span></span> <span data-ttu-id="c2a8b-129">Модификатор `in` в месте вызова является необязательным, так как не нужно указывать, что значение аргумента может изменяться.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-129">The `in` modifier at the call site is optional because you don't need to indicate that the argument's value might be changed.</span></span> <span data-ttu-id="c2a8b-130">Вы явным образом добавляете модификатор `in` в место вызова, чтобы аргумент передавался по ссылке, а не по значению.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-130">You explicitly add the `in` modifier at the call site to ensure the argument is passed by reference, not by value.</span></span> <span data-ttu-id="c2a8b-131">Явное использование `in` приводит к двум результатам.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-131">Explicitly using `in` has the following two effects:</span></span>

<span data-ttu-id="c2a8b-132">Во-первых, указание `in` в месте вызова вынуждает компилятор выбрать метод, определенный с помощью соответствующего параметра `in`.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-132">First, specifying `in` at the call site forces the compiler to select a method defined with a matching `in` parameter.</span></span> <span data-ttu-id="c2a8b-133">В противном случае, когда два метода отличаются только наличием `in`, перегрузка по значению подходит лучше.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-133">Otherwise, when two methods differ only in the presence of `in`, the by value overload is a better match.</span></span>

<span data-ttu-id="c2a8b-134">Во-вторых, указав `in`, вы объявляете о намерении передать аргумент по ссылке.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-134">Second, specifying `in` declares your intent to pass an argument by reference.</span></span> <span data-ttu-id="c2a8b-135">Аргумент, используемый с `in`, должен представлять расположение, на которое можно сослаться напрямую.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-135">The argument used with `in` must represent a location that can be directly referred to.</span></span> <span data-ttu-id="c2a8b-136">Такие же общие правила применяются к аргументам `out` и `ref`: вы не можете использовать константы, обычные свойства или другие выражения, возвращающие значения.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-136">The same general rules for `out` and `ref` arguments apply: You cannot use constants, ordinary properties, or other expressions that produce values.</span></span> <span data-ttu-id="c2a8b-137">В противном случае пропуск `in` в месте вызова сообщает компилятору, что вы разрешите ему создать временную переменную для передачи с помощью ссылки на метод, доступной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-137">Otherwise, omitting `in` at the call site informs the compiler that you will allow it to create a temporary variable to pass by read-only reference to the method.</span></span> <span data-ttu-id="c2a8b-138">Компилятор создает временную переменную, чтобы преодолеть некоторые ограничения для аргументов `in`:</span><span class="sxs-lookup"><span data-stu-id="c2a8b-138">The compiler creates a temporary variable to overcome several restrictions with `in` arguments:</span></span>

- <span data-ttu-id="c2a8b-139">Временная переменная позволяет использовать константы времени компиляции, например параметры `in`.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-139">A temporary variable allows compile-time constants as `in` parameters.</span></span>
- <span data-ttu-id="c2a8b-140">Временная переменная позволяет использовать свойства или другие выражения для параметров `in`.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-140">A temporary variable allows properties, or other expressions for `in` parameters.</span></span>
- <span data-ttu-id="c2a8b-141">Временная переменная позволяет использовать аргументы, где выполняется неявное преобразование из типа аргумента в тип параметра.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-141">A temporary variable allows arguments where there is an implicit conversion from the argument type to the parameter type.</span></span>

<span data-ttu-id="c2a8b-142">Во всех предыдущих случаях компилятор создает временную переменную, хранящую значение константы, свойства или другого выражения.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-142">In all the preceding instances, the compiler creates a temporary variable that stores the value of the constant, property, or other expression.</span></span>

<span data-ttu-id="c2a8b-143">Эти правила проиллюстрированы в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="c2a8b-143">The following code illustrates these rules:</span></span>

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

<span data-ttu-id="c2a8b-144">Теперь предположим, что был доступен другой метод, использующий аргументы по значению.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-144">Now, suppose another method using by value arguments was available.</span></span> <span data-ttu-id="c2a8b-145">Результаты изменяются, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="c2a8b-145">The results change as shown in the following code:</span></span>

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

<span data-ttu-id="c2a8b-146">Аргумент передается по ссылке только в последнем вызове метода.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-146">The only method call where the argument is passed by reference is the final one.</span></span>

> [!NOTE]
> <span data-ttu-id="c2a8b-147">Для простоты предыдущий код использует `int` в качестве типа аргумента.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-147">The preceding code uses `int` as the argument type for simplicity.</span></span> <span data-ttu-id="c2a8b-148">Так как по размеру `int` не больше ссылки на большинстве современных компьютеров, не имеет смысла передавать один `int` в качестве ссылки, доступной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-148">Because `int` is no larger than a reference in most modern machines, there is no benefit to passing a single `int` as a readonly reference.</span></span> 

## <a name="limitations-on-in-parameters"></a><span data-ttu-id="c2a8b-149">Ограничения для параметров `in`</span><span class="sxs-lookup"><span data-stu-id="c2a8b-149">Limitations on `in` parameters</span></span>

<span data-ttu-id="c2a8b-150">Ключевые слова `in`, `ref` и `out` запрещено использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-150">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="c2a8b-151">Асинхронные методы, которые определяются с помощью модификатора [async](async.md).</span><span class="sxs-lookup"><span data-stu-id="c2a8b-151">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="c2a8b-152">Методы итератора, которые включают оператор [yield return](yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="c2a8b-152">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="c2a8b-153">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c2a8b-153">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c2a8b-154">См. также</span><span class="sxs-lookup"><span data-stu-id="c2a8b-154">See also</span></span>

- [<span data-ttu-id="c2a8b-155">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c2a8b-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c2a8b-156">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c2a8b-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c2a8b-157">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="c2a8b-157">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c2a8b-158">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="c2a8b-158">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="c2a8b-159">Написание безопасного и эффективного кода</span><span class="sxs-lookup"><span data-stu-id="c2a8b-159">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
