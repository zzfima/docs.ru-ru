---
title: Byref
description: Сведения о типах, схожих с ByRef и F#ByRef, в, которые используются для низкоуровневого программирования.
ms.date: 11/04/2019
ms.openlocfilehash: 2c46cea2329b6817dd753e67c6702fb163ce2193
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976829"
---
# <a name="byrefs"></a><span data-ttu-id="9cf86-103">Byref</span><span class="sxs-lookup"><span data-stu-id="9cf86-103">Byrefs</span></span>

<span data-ttu-id="9cf86-104">F#имеет две основные функциональные области, которые имеют место в пространстве низкоуровневого программирования:</span><span class="sxs-lookup"><span data-stu-id="9cf86-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="9cf86-105">`byref`/`inref`/типы `outref`, являющиеся управляемыми указателями.</span><span class="sxs-lookup"><span data-stu-id="9cf86-105">The `byref`/`inref`/`outref` types, which are a managed pointers.</span></span> <span data-ttu-id="9cf86-106">Они имеют ограничения на использование, поэтому нельзя компилировать программу, недопустимую во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9cf86-106">They have restrictions on usage so that you cannot compile a program that is invalid at runtime.</span></span>
* <span data-ttu-id="9cf86-107">Структура, подобная `byref`, которая представляет собой [структуру](structures.md) , которая имеет подобную семантику и те же ограничения времени компиляции, что и `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="9cf86-108">Один из примеров — <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="9cf86-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="9cf86-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cf86-109">Syntax</span></span>

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a><span data-ttu-id="9cf86-110">ByRef, инреф и аутреф</span><span class="sxs-lookup"><span data-stu-id="9cf86-110">Byref, inref, and outref</span></span>

<span data-ttu-id="9cf86-111">Существует три формы `byref`:</span><span class="sxs-lookup"><span data-stu-id="9cf86-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="9cf86-112">`inref<'T>`— управляемый указатель для чтения базового значения.</span><span class="sxs-lookup"><span data-stu-id="9cf86-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="9cf86-113">`outref<'T>`— управляемый указатель для записи в базовое значение.</span><span class="sxs-lookup"><span data-stu-id="9cf86-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="9cf86-114">`byref<'T>`— управляемый указатель для чтения и записи базового значения.</span><span class="sxs-lookup"><span data-stu-id="9cf86-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="9cf86-115">Можно передать `byref<'T>`, где ожидается `inref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="9cf86-116">Аналогичным образом можно передать `byref<'T>`, где ожидается `outref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="9cf86-117">Использование ByRef</span><span class="sxs-lookup"><span data-stu-id="9cf86-117">Using byrefs</span></span>

<span data-ttu-id="9cf86-118">Чтобы использовать `inref<'T>`, необходимо получить значение указателя с `&`:</span><span class="sxs-lookup"><span data-stu-id="9cf86-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="9cf86-119">Для записи в указатель с помощью `outref<'T>` или `byref<'T>`необходимо также сделать значение, которое захватит указатель на `mutable`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

<span data-ttu-id="9cf86-120">Если вы пишете только указатель, а не читаете его, рассмотрите возможность использования `outref<'T>` вместо `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="9cf86-121">Семантика инреф</span><span class="sxs-lookup"><span data-stu-id="9cf86-121">Inref semantics</span></span>

<span data-ttu-id="9cf86-122">Рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="9cf86-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="9cf86-123">В семантическом виде это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="9cf86-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="9cf86-124">Владелец указателя `x` может использовать его только для чтения значения.</span><span class="sxs-lookup"><span data-stu-id="9cf86-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="9cf86-125">Любой указатель, полученный к `struct` полям, вложенным в `SomeStruct`, получает `inref<_>`типа.</span><span class="sxs-lookup"><span data-stu-id="9cf86-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="9cf86-126">Также верно следующее:</span><span class="sxs-lookup"><span data-stu-id="9cf86-126">The following is also true:</span></span>

* <span data-ttu-id="9cf86-127">Нет никаких последствие того, что другие потоки или псевдонимы не имеют доступа на запись к `x`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="9cf86-128">Нечего никакое `SomeStruct` неизменяемо, поскольку `x` является `inref`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="9cf86-129">Однако для F# типов значений, которые **являются** неизменяемыми, `this` указатель выводится как `inref`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="9cf86-130">Все эти правила вместе означают, что владелец указателя `inref` не может изменить немедленное содержимое памяти, на которое указывает.</span><span class="sxs-lookup"><span data-stu-id="9cf86-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="9cf86-131">Семантика аутреф</span><span class="sxs-lookup"><span data-stu-id="9cf86-131">Outref semantics</span></span>

<span data-ttu-id="9cf86-132">Цель `outref<'T>` — указать, что указатель должен быть только прочитан из.</span><span class="sxs-lookup"><span data-stu-id="9cf86-132">The purpose of `outref<'T>` is to indicate that the pointer should only be read from.</span></span> <span data-ttu-id="9cf86-133">Неожиданно `outref<'T>` позволяет считывать базовое значение, несмотря на его имя.</span><span class="sxs-lookup"><span data-stu-id="9cf86-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="9cf86-134">Это происходит в целях совместимости.</span><span class="sxs-lookup"><span data-stu-id="9cf86-134">This is for compatibility purposes.</span></span> <span data-ttu-id="9cf86-135">Семантически `outref<'T>` не отличается от `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="9cf86-136">Взаимодействие с\#ом C</span><span class="sxs-lookup"><span data-stu-id="9cf86-136">Interop with C\#</span></span>

<span data-ttu-id="9cf86-137">C#поддерживает ключевые слова `in ref` и `out ref`, а также возвращает `ref`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="9cf86-138">В следующей таблице показано, F# как интерпретирует C# выдачи:</span><span class="sxs-lookup"><span data-stu-id="9cf86-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="9cf86-139">C#создания</span><span class="sxs-lookup"><span data-stu-id="9cf86-139">C# construct</span></span>|<span data-ttu-id="9cf86-140">F#выводит</span><span class="sxs-lookup"><span data-stu-id="9cf86-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="9cf86-141">`ref` возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9cf86-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="9cf86-142">`ref readonly` возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9cf86-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="9cf86-143">`in ref`, параметр</span><span class="sxs-lookup"><span data-stu-id="9cf86-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="9cf86-144">`out ref`, параметр</span><span class="sxs-lookup"><span data-stu-id="9cf86-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="9cf86-145">В следующей таблице показано, F# какие выдачи:</span><span class="sxs-lookup"><span data-stu-id="9cf86-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="9cf86-146">F#создания</span><span class="sxs-lookup"><span data-stu-id="9cf86-146">F# construct</span></span>|<span data-ttu-id="9cf86-147">Выпущенная конструкция</span><span class="sxs-lookup"><span data-stu-id="9cf86-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="9cf86-148">`inref<'T>` аргумент</span><span class="sxs-lookup"><span data-stu-id="9cf86-148">`inref<'T>` argument</span></span>|<span data-ttu-id="9cf86-149">атрибут `[In]` в аргументе</span><span class="sxs-lookup"><span data-stu-id="9cf86-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="9cf86-150">`inref<'T>` возврат</span><span class="sxs-lookup"><span data-stu-id="9cf86-150">`inref<'T>` return</span></span>|<span data-ttu-id="9cf86-151">атрибут `modreq` в значении</span><span class="sxs-lookup"><span data-stu-id="9cf86-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="9cf86-152">`inref<'T>` в абстрактном слоте или реализации</span><span class="sxs-lookup"><span data-stu-id="9cf86-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="9cf86-153">`modreq` аргумента или Return</span><span class="sxs-lookup"><span data-stu-id="9cf86-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="9cf86-154">`outref<'T>` аргумент</span><span class="sxs-lookup"><span data-stu-id="9cf86-154">`outref<'T>` argument</span></span>|<span data-ttu-id="9cf86-155">атрибут `[Out]` в аргументе</span><span class="sxs-lookup"><span data-stu-id="9cf86-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="9cf86-156">Определение типа и перегрузка правил</span><span class="sxs-lookup"><span data-stu-id="9cf86-156">Type inference and overloading rules</span></span>

<span data-ttu-id="9cf86-157">Тип `inref<'T>` выводится F# компилятором в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="9cf86-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="9cf86-158">Параметр или возвращаемый тип .NET, имеющий атрибут `IsReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="9cf86-159">`this` указатель на тип структуры, не имеющий изменяемых полей.</span><span class="sxs-lookup"><span data-stu-id="9cf86-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="9cf86-160">Адрес области памяти, полученной из другого указателя `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="9cf86-161">При использовании неявного адреса `inref` перегрузку с аргументом типа `SomeType` предпочтительнее для перегрузки с аргументом типа `inref<SomeType>`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="9cf86-162">Пример:</span><span class="sxs-lookup"><span data-stu-id="9cf86-162">For example:</span></span>

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

<span data-ttu-id="9cf86-163">В обоих случаях перегрузки, принимающие `System.DateTime`, разрешаются вместо перегрузок, принимающих `inref<System.DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="9cf86-164">Структуры, аналогичные ByRef</span><span class="sxs-lookup"><span data-stu-id="9cf86-164">Byref-like structs</span></span>

<span data-ttu-id="9cf86-165">Помимо `byref`/`inref`/`outref` три, можно определить собственные структуры, которые могут соответствовать семантике `byref`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="9cf86-166">Это делается с помощью атрибута <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>:</span><span class="sxs-lookup"><span data-stu-id="9cf86-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="9cf86-167">`IsByRefLike` не подразумевает `Struct`.</span><span class="sxs-lookup"><span data-stu-id="9cf86-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="9cf86-168">Оба должны присутствовать в типе.</span><span class="sxs-lookup"><span data-stu-id="9cf86-168">Both must be present on the type.</span></span>

<span data-ttu-id="9cf86-169">"`byref`-похожая" структура в F# — это тип значения, привязанный к стеку.</span><span class="sxs-lookup"><span data-stu-id="9cf86-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="9cf86-170">Он никогда не выделяется в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="9cf86-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="9cf86-171">Структура, подобная `byref`, полезна для высокопроизводительного программирования, так как она применяется к набору строгих проверок времени существования и без записи.</span><span class="sxs-lookup"><span data-stu-id="9cf86-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="9cf86-172">Правила:</span><span class="sxs-lookup"><span data-stu-id="9cf86-172">The rules are:</span></span>

* <span data-ttu-id="9cf86-173">Их можно использовать в качестве параметров функций, параметров методов, локальных переменных, возвращаемых методом.</span><span class="sxs-lookup"><span data-stu-id="9cf86-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="9cf86-174">Они не могут быть статическими или членами экземпляров класса или обычной структуры.</span><span class="sxs-lookup"><span data-stu-id="9cf86-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="9cf86-175">Они не могут быть захвачены какой-либо конструкцией замыкания (`async` методами или лямбда-выражениями).</span><span class="sxs-lookup"><span data-stu-id="9cf86-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="9cf86-176">Их нельзя использовать в качестве универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="9cf86-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="9cf86-177">Последний момент является ключевым для F# программирования в стиле конвейера, так как `|>` является универсальной функцией, которая выполняет параметризацию входных типов.</span><span class="sxs-lookup"><span data-stu-id="9cf86-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="9cf86-178">Это ограничение может быть ослаблено для `|>` в будущем, так как оно встроено и не вызывает невстроенные универсальные функции в своем тексте.</span><span class="sxs-lookup"><span data-stu-id="9cf86-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="9cf86-179">Хотя эти правила очень сильно ограничивают использование, они делают это для обеспечения безопасности высокопроизводительных вычислительных систем надежным способом.</span><span class="sxs-lookup"><span data-stu-id="9cf86-179">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="9cf86-180">Возвраты по ссылке</span><span class="sxs-lookup"><span data-stu-id="9cf86-180">Byref returns</span></span>

<span data-ttu-id="9cf86-181">Функция ByRef возвращает F# из функций или членов, которые могут быть созданы и использованы.</span><span class="sxs-lookup"><span data-stu-id="9cf86-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="9cf86-182">При использовании метода, возвращающего `byref`, значение неявно разыменовано.</span><span class="sxs-lookup"><span data-stu-id="9cf86-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="9cf86-183">Пример:</span><span class="sxs-lookup"><span data-stu-id="9cf86-183">For example:</span></span>

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

<span data-ttu-id="9cf86-184">Чтобы избежать неявного разыменования, например передачи ссылки через несколько цепочек вызовов, используйте `&x` (где `x` является значением).</span><span class="sxs-lookup"><span data-stu-id="9cf86-184">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="9cf86-185">Можно также напрямую назначить `byref`возврата.</span><span class="sxs-lookup"><span data-stu-id="9cf86-185">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="9cf86-186">Рассмотрим следующую (очень императивную) программу:</span><span class="sxs-lookup"><span data-stu-id="9cf86-186">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override _.ToString() = String.Join(' ', nums)

    member _.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

<span data-ttu-id="9cf86-187">Результат.</span><span class="sxs-lookup"><span data-stu-id="9cf86-187">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="9cf86-188">Определение области для ByRef</span><span class="sxs-lookup"><span data-stu-id="9cf86-188">Scoping for byrefs</span></span>

<span data-ttu-id="9cf86-189">Значение с привязкой к `let`не может превышать область, в которой он был определен.</span><span class="sxs-lookup"><span data-stu-id="9cf86-189">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="9cf86-190">Например, запрещены следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="9cf86-190">For example, the following is disallowed:</span></span>

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

<span data-ttu-id="9cf86-191">Это предотвращает получение различных результатов в зависимости от того, выполняется ли компиляция с оптимизацией.</span><span class="sxs-lookup"><span data-stu-id="9cf86-191">This prevents you from getting different results depending on if you compile with optimizations on or off.</span></span>
