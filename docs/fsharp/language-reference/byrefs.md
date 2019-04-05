---
title: Byrefs
description: Дополнительные сведения о byref и типов, схожих с byref в F#, которые используются для программирования низкого уровня.
ms.date: 09/02/2018
ms.openlocfilehash: c0bad26672fbb9eb315eee1c3e275183ddeb9297
ms.sourcegitcommit: 68eb5c4928e2b082f178a42c16f73fedf52c2ab8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59055369"
---
# <a name="byrefs"></a><span data-ttu-id="85b36-103">Byrefs</span><span class="sxs-lookup"><span data-stu-id="85b36-103">Byrefs</span></span>

<span data-ttu-id="85b36-104">F#имеет два основных функциональных областей, которые работают в пространстве низкоуровневого программирования:</span><span class="sxs-lookup"><span data-stu-id="85b36-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="85b36-105">`byref` / `inref` / `outref` Типы, которые являются управляемыми указателями.</span><span class="sxs-lookup"><span data-stu-id="85b36-105">The `byref`/`inref`/`outref` types, which are a managed pointers.</span></span> <span data-ttu-id="85b36-106">Они имеют ограничения на использование, так что не удается скомпилировать программу, которая является недопустимым во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="85b36-106">They have restrictions on usage so that you cannot compile a program that is invalid at runtime.</span></span>
* <span data-ttu-id="85b36-107">Объект `byref`-как структуры, который является [структуры](structures.md) имеет похожую семантику и те же ограничения во время компиляции, что `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="85b36-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="85b36-108">Одним из примеров является <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="85b36-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="85b36-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85b36-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="85b36-110">ByRef, inref и outref</span><span class="sxs-lookup"><span data-stu-id="85b36-110">Byref, inref, and outref</span></span>

<span data-ttu-id="85b36-111">Существует три формы `byref`:</span><span class="sxs-lookup"><span data-stu-id="85b36-111">There are three forms of `byref`:</span></span>

* `inref<'T>`<span data-ttu-id="85b36-112">, управляемый указатель для чтения базового значения.</span><span class="sxs-lookup"><span data-stu-id="85b36-112">, a managed pointer for reading the underlying value.</span></span>
* `outref<'T>`<span data-ttu-id="85b36-113">, управляемый указатель для записи к исходному значению.</span><span class="sxs-lookup"><span data-stu-id="85b36-113">, a managed pointer for writing to the underlying value.</span></span>
* `byref<'T>`<span data-ttu-id="85b36-114">, управляемый указатель для чтения и записи базовое значение.</span><span class="sxs-lookup"><span data-stu-id="85b36-114">, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="85b36-115">Объект `byref<'T>` могут передаваться где `inref<'T>` ожидается.</span><span class="sxs-lookup"><span data-stu-id="85b36-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="85b36-116">Аналогичным образом `byref<'T>` могут передаваться где `outref<'T>` ожидается.</span><span class="sxs-lookup"><span data-stu-id="85b36-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="85b36-117">С помощью byrefs</span><span class="sxs-lookup"><span data-stu-id="85b36-117">Using byrefs</span></span>

<span data-ttu-id="85b36-118">Чтобы использовать `inref<'T>`, необходимо получить значение указателя с `&`:</span><span class="sxs-lookup"><span data-stu-id="85b36-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    
let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="85b36-119">Для записи указателя с помощью `outref<'T>` или `byref<'T>`, кроме того, необходимо получить указатель на значение `mutable`.</span><span class="sxs-lookup"><span data-stu-id="85b36-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="85b36-120">При создании указателя, не считывая их рассмотрите возможность использования `outref<'T>` вместо `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="85b36-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="85b36-121">Семантика Inref</span><span class="sxs-lookup"><span data-stu-id="85b36-121">Inref semantics</span></span>

<span data-ttu-id="85b36-122">Рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="85b36-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="85b36-123">Семантически это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="85b36-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="85b36-124">Владелец `x` указатель может использовать только для чтения значения.</span><span class="sxs-lookup"><span data-stu-id="85b36-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="85b36-125">Любой указатель, необходимые для `struct` вложенных полей `SomeStruct` получают тип `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="85b36-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="85b36-126">Ниже также верно:</span><span class="sxs-lookup"><span data-stu-id="85b36-126">The following is also true:</span></span>

* <span data-ttu-id="85b36-127">Нет практической другие потоки или псевдонимы имеет доступ на запись к `x`.</span><span class="sxs-lookup"><span data-stu-id="85b36-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="85b36-128">Нет практической, `SomeStruct` является неизменяемым посредством `x` , `inref`.</span><span class="sxs-lookup"><span data-stu-id="85b36-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="85b36-129">Однако для F# типы значения, которые **являются** неизменяемым, `this` указатель определяется как `inref`.</span><span class="sxs-lookup"><span data-stu-id="85b36-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="85b36-130">Все вместе эти правила означает, что владелец `inref` указатель не может изменять немедленно содержимое, на которые указывает объем памяти.</span><span class="sxs-lookup"><span data-stu-id="85b36-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="85b36-131">Семантика Outref</span><span class="sxs-lookup"><span data-stu-id="85b36-131">Outref semantics</span></span>

<span data-ttu-id="85b36-132">Цель `outref<'T>` необходимо указать, что указатель должен выполняться только чтение.</span><span class="sxs-lookup"><span data-stu-id="85b36-132">The purpose of `outref<'T>` is to indicate that the pointer should only be read from.</span></span> <span data-ttu-id="85b36-133">Неожиданно `outref<'T>` разрешает чтение базового значение несмотря на свое название.</span><span class="sxs-lookup"><span data-stu-id="85b36-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="85b36-134">Это необходимо для обеспечения совместимости.</span><span class="sxs-lookup"><span data-stu-id="85b36-134">This is for compatibility purposes.</span></span> <span data-ttu-id="85b36-135">Семантически `outref<'T>` ничем не отличается от `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="85b36-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="85b36-136">Взаимодействие с c#\#</span><span class="sxs-lookup"><span data-stu-id="85b36-136">Interop with C\#</span></span>

<span data-ttu-id="85b36-137">Язык C# поддерживает `in ref` и `out ref` ключевые слова, в дополнение к `ref` возвращает.</span><span class="sxs-lookup"><span data-stu-id="85b36-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="85b36-138">В следующей таблице показано, как F# интерпретирует что C# выдает:</span><span class="sxs-lookup"><span data-stu-id="85b36-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="85b36-139">Конструкция C#</span><span class="sxs-lookup"><span data-stu-id="85b36-139">C# construct</span></span>|<span data-ttu-id="85b36-140">F#Выводит</span><span class="sxs-lookup"><span data-stu-id="85b36-140">F# infers</span></span>|
|------------|---------|
|`ref` <span data-ttu-id="85b36-141">возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="85b36-141">return value</span></span>|`outref<'T>`|
|`ref readonly` <span data-ttu-id="85b36-142">возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="85b36-142">return value</span></span>|`inref<'T>`|
|`in ref` <span data-ttu-id="85b36-143">параметр</span><span class="sxs-lookup"><span data-stu-id="85b36-143">parameter</span></span>|`inref<'T>`|
|`out ref` <span data-ttu-id="85b36-144">параметр</span><span class="sxs-lookup"><span data-stu-id="85b36-144">parameter</span></span>|`outref<'T>`|

<span data-ttu-id="85b36-145">В следующей таблице показано, что F# выдает:</span><span class="sxs-lookup"><span data-stu-id="85b36-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="85b36-146">F#Конструкция</span><span class="sxs-lookup"><span data-stu-id="85b36-146">F# construct</span></span>|<span data-ttu-id="85b36-147">Выпущенный конструкция</span><span class="sxs-lookup"><span data-stu-id="85b36-147">Emitted construct</span></span>|
|------------|-----------------|
|`inref<'T>` <span data-ttu-id="85b36-148">аргумент</span><span class="sxs-lookup"><span data-stu-id="85b36-148">argument</span></span>|`[In]` <span data-ttu-id="85b36-149">аргумент атрибута</span><span class="sxs-lookup"><span data-stu-id="85b36-149">attribute on argument</span></span>|
|`inref<'T>` <span data-ttu-id="85b36-150">return</span><span class="sxs-lookup"><span data-stu-id="85b36-150">return</span></span>|`modreq` <span data-ttu-id="85b36-151">значение атрибута</span><span class="sxs-lookup"><span data-stu-id="85b36-151">attribute on value</span></span>|
|`inref<'T>` <span data-ttu-id="85b36-152">в абстрактный слот или реализации</span><span class="sxs-lookup"><span data-stu-id="85b36-152">in abstract slot or implementation</span></span>|`modreq` <span data-ttu-id="85b36-153">на аргумента или возвращаемого</span><span class="sxs-lookup"><span data-stu-id="85b36-153">on argument or return</span></span>|
|`outref<'T>` <span data-ttu-id="85b36-154">аргумент</span><span class="sxs-lookup"><span data-stu-id="85b36-154">argument</span></span>|`[Out]` <span data-ttu-id="85b36-155">аргумент атрибута</span><span class="sxs-lookup"><span data-stu-id="85b36-155">attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="85b36-156">Вывод типа и правила перегрузки</span><span class="sxs-lookup"><span data-stu-id="85b36-156">Type inference and overloading rules</span></span>

<span data-ttu-id="85b36-157">`inref<'T>` Определить тип F# компилятора в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="85b36-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="85b36-158">.NET параметра или возвращаемого типа, имеющего `IsReadOnly` атрибута.</span><span class="sxs-lookup"><span data-stu-id="85b36-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="85b36-159">`this` Указатель на тип структуры, не имеет изменяемых полей.</span><span class="sxs-lookup"><span data-stu-id="85b36-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="85b36-160">Адрес области памяти, производным от другого `inref<_>` указатель.</span><span class="sxs-lookup"><span data-stu-id="85b36-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="85b36-161">Когда неявные адрес `inref` выполнено не было перегрузка с аргументом типа `SomeType` предпочтительнее перегрузка с аргументом типа `inref<SomeType>`.</span><span class="sxs-lookup"><span data-stu-id="85b36-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="85b36-162">Пример:</span><span class="sxs-lookup"><span data-stu-id="85b36-162">For example:</span></span>

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

<span data-ttu-id="85b36-163">В обоих случаях перегрузок, принимающих `System.DateTime` разрешаются вместо того чтобы перегрузок, принимающих `inref<System.DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="85b36-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="85b36-164">Структуры типа ByRef</span><span class="sxs-lookup"><span data-stu-id="85b36-164">Byref-like structs</span></span>

<span data-ttu-id="85b36-165">В дополнение к `byref` / `inref` / `outref` вычислительные, вы можете определить собственные структуры, можно придерживаться `byref`-семантику, например.</span><span class="sxs-lookup"><span data-stu-id="85b36-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="85b36-166">Это делается с помощью <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> атрибут:</span><span class="sxs-lookup"><span data-stu-id="85b36-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` <span data-ttu-id="85b36-167">не подразумевает `Struct`.</span><span class="sxs-lookup"><span data-stu-id="85b36-167">does not imply `Struct`.</span></span> <span data-ttu-id="85b36-168">Оба должны присутствовать на тип.</span><span class="sxs-lookup"><span data-stu-id="85b36-168">Both must be present on the type.</span></span>

<span data-ttu-id="85b36-169">Объект "`byref`-как «структура в F# является типом значения стека привязки.</span><span class="sxs-lookup"><span data-stu-id="85b36-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="85b36-170">Он никогда не выделяется в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="85b36-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="85b36-171">Объект `byref`-как структура полезна для программирования высокой производительности, как реализована с помощью набора строгим проверкам, о времени существования и незахвата.</span><span class="sxs-lookup"><span data-stu-id="85b36-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="85b36-172">Ниже приведены правила.</span><span class="sxs-lookup"><span data-stu-id="85b36-172">The rules are:</span></span>

* <span data-ttu-id="85b36-173">Они могут использоваться как параметры функции, параметры метода, локальные переменные, метод возвращает.</span><span class="sxs-lookup"><span data-stu-id="85b36-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="85b36-174">Они не может быть статическим или члены класса или обычной структуры экземпляров.</span><span class="sxs-lookup"><span data-stu-id="85b36-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="85b36-175">Не может быть перехвачено любой конструкции замыкание (`async` методы или лямбда-выражений).</span><span class="sxs-lookup"><span data-stu-id="85b36-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="85b36-176">Они не может использоваться в качестве универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="85b36-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="85b36-177">Это последнее является исключительно важным для F# программирования конвейера, как `|>` является универсальной функции, которая параметризует его типы входных данных.</span><span class="sxs-lookup"><span data-stu-id="85b36-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="85b36-178">Это ограничение может быть снижено для `|>` в будущем, так как она является встроенной и не выполняет каких-либо вызовов неподставляемый универсальные функции в его тексте.</span><span class="sxs-lookup"><span data-stu-id="85b36-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="85b36-179">Несмотря на то, что эти правила очень строго ограничить использование, они появляющимися достигается за счет высокопроизводительные вычислительные системы безопасным образом.</span><span class="sxs-lookup"><span data-stu-id="85b36-179">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="85b36-180">Возвраты ByRef</span><span class="sxs-lookup"><span data-stu-id="85b36-180">Byref returns</span></span>

<span data-ttu-id="85b36-181">Возвраты ByRef из F# функциям или членам можно создать и использовать.</span><span class="sxs-lookup"><span data-stu-id="85b36-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="85b36-182">При использовании `byref`-возвращать метод, значение неявным образом не имеет.</span><span class="sxs-lookup"><span data-stu-id="85b36-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="85b36-183">Пример:</span><span class="sxs-lookup"><span data-stu-id="85b36-183">For example:</span></span>

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

<span data-ttu-id="85b36-184">Чтобы избежать неявного разыменования, например передачи ссылки через несколько цепочки вызовов, используйте `&x` (где `x` -значение).</span><span class="sxs-lookup"><span data-stu-id="85b36-184">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="85b36-185">Можно также напрямую назначить возвращаемое значение `byref`.</span><span class="sxs-lookup"><span data-stu-id="85b36-185">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="85b36-186">Рассмотрим следующую программу (высокой императивный):</span><span class="sxs-lookup"><span data-stu-id="85b36-186">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override __.ToString() = String.Join(' ', nums)

    member __.FindLargestSmallerThan(target: int) =
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

<span data-ttu-id="85b36-187">Результат.</span><span class="sxs-lookup"><span data-stu-id="85b36-187">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="85b36-188">Отнесение в областям для byrefs</span><span class="sxs-lookup"><span data-stu-id="85b36-188">Scoping for byrefs</span></span>

<span data-ttu-id="85b36-189">Объект `let`-привязанное значение не может иметь ссылку превышать область, в котором он был определен.</span><span class="sxs-lookup"><span data-stu-id="85b36-189">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="85b36-190">Например ниже запрещено:</span><span class="sxs-lookup"><span data-stu-id="85b36-190">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="85b36-191">Это предотвращает получение разных результатов в зависимости от того, если компиляция выполняется с оптимизациями, включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="85b36-191">This prevents you from getting different results depending on if you compile with optimizations on or off.</span></span>
