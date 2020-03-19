---
title: Byref
description: Узнайте о типах byref и byref-подобных в F-, которые используются для программирования низкого уровня.
ms.date: 11/04/2019
ms.openlocfilehash: 527f465ee87fe153a2deae1306b6730531dc4123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187053"
---
# <a name="byrefs"></a><span data-ttu-id="f3fc0-103">Byref</span><span class="sxs-lookup"><span data-stu-id="f3fc0-103">Byrefs</span></span>

<span data-ttu-id="f3fc0-104">ФЗ имеет две основные функциональные области, которые имеют дело в пространстве низкоуровневого программирования:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="f3fc0-105">`byref` / `inref` / Типы, `outref` которыми управляют указатели.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="f3fc0-106">Они имеют ограничения на использование, так что вы не можете собрать программу, которая является недействительной во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="f3fc0-107">A-как `byref`структурирует, который представляет собой [структуру,](structures.md) которая имеет аналогичную `byref<'T>`семантику и те же ограничения времени компиляции, как .</span><span class="sxs-lookup"><span data-stu-id="f3fc0-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="f3fc0-108">Одним из <xref:System.Span%601>примеров является .</span><span class="sxs-lookup"><span data-stu-id="f3fc0-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="f3fc0-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3fc0-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="f3fc0-110">Byref, inref, и outref</span><span class="sxs-lookup"><span data-stu-id="f3fc0-110">Byref, inref, and outref</span></span>

<span data-ttu-id="f3fc0-111">Существует три `byref`формы:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="f3fc0-112">`inref<'T>`, управляемый указатель для чтения базового значения.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="f3fc0-113">`outref<'T>`, управляемый указатель для записи к базовому значению.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="f3fc0-114">`byref<'T>`, управляемый указатель для чтения и написания базового значения.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="f3fc0-115">A `byref<'T>` может быть `inref<'T>` пройден там, где ожидается.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="f3fc0-116">Аналогичным образом, a `byref<'T>` может `outref<'T>` быть пройден там, где ожидается.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="f3fc0-117">Использование байрефов</span><span class="sxs-lookup"><span data-stu-id="f3fc0-117">Using byrefs</span></span>

<span data-ttu-id="f3fc0-118">Для `inref<'T>`использования, вам нужно получить значение `&`указателя с:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="f3fc0-119">Чтобы написать указателю с `outref<'T>` `byref<'T>`помощью или, вы также должны сделать значение вы захватить указатель на `mutable`.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="f3fc0-120">Если вы пишете только указатель вместо того, `byref<'T>`чтобы читать его, рассмотреть вопрос об использовании `outref<'T>` вместо .</span><span class="sxs-lookup"><span data-stu-id="f3fc0-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="f3fc0-121">Семантика Инрефа</span><span class="sxs-lookup"><span data-stu-id="f3fc0-121">Inref semantics</span></span>

<span data-ttu-id="f3fc0-122">Рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="f3fc0-123">Семантически это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="f3fc0-124">Держатель указателя `x` может использовать его только для чтения значения.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="f3fc0-125">Любой указатель, приобретенный на `struct` полях, вложенных в, `SomeStruct` дается типом. `inref<_>`</span><span class="sxs-lookup"><span data-stu-id="f3fc0-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="f3fc0-126">Верно и следующее:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-126">The following is also true:</span></span>

* <span data-ttu-id="f3fc0-127">Существует никаких последствий, что другие потоки или `x`псевдонимы не имеют доступа к записи .</span><span class="sxs-lookup"><span data-stu-id="f3fc0-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="f3fc0-128">Существует никаких `SomeStruct` последствий, что является `x` непреложной в силу того, что `inref`.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="f3fc0-129">Тем не менее, для **are** типов значений `this` F, которые являются неизменяемыми, указатель выводится как `inref`.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="f3fc0-130">Все эти правила вместе означают, `inref` что держатель указателя не может изменять немедленное содержимое памяти, на которую указывается.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="f3fc0-131">Семантика Аутрефа</span><span class="sxs-lookup"><span data-stu-id="f3fc0-131">Outref semantics</span></span>

<span data-ttu-id="f3fc0-132">Цель состоит `outref<'T>` в том, чтобы указать, что указатель должен быть написан только.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="f3fc0-133">Неожиданно `outref<'T>` позволяет читать базовое значение, несмотря на его название.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="f3fc0-134">Это для целей совместимости.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-134">This is for compatibility purposes.</span></span> <span data-ttu-id="f3fc0-135">Семантически, `outref<'T>` ничем `byref<'T>`не отличается от .</span><span class="sxs-lookup"><span data-stu-id="f3fc0-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="f3fc0-136">Интероп с C\#</span><span class="sxs-lookup"><span data-stu-id="f3fc0-136">Interop with C\#</span></span>

<span data-ttu-id="f3fc0-137">В дополнение `in ref` к `out ref` возвратам, в `ref` дополнение к возвратам, компания поддерживает и ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="f3fc0-138">В следующей таблице показано, как f's интерпретирует то, что испускает C':</span><span class="sxs-lookup"><span data-stu-id="f3fc0-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="f3fc0-139">Конструкция СИ</span><span class="sxs-lookup"><span data-stu-id="f3fc0-139">C# construct</span></span>|<span data-ttu-id="f3fc0-140">Выводы ФЗ</span><span class="sxs-lookup"><span data-stu-id="f3fc0-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="f3fc0-141">`ref`возвратное значение</span><span class="sxs-lookup"><span data-stu-id="f3fc0-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="f3fc0-142">`ref readonly`возвратное значение</span><span class="sxs-lookup"><span data-stu-id="f3fc0-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="f3fc0-143">Параметр `in ref`</span><span class="sxs-lookup"><span data-stu-id="f3fc0-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="f3fc0-144">Параметр `out ref`</span><span class="sxs-lookup"><span data-stu-id="f3fc0-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="f3fc0-145">В следующей таблице показано, что испускает F-излучает:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="f3fc0-146">Конструкция ФЗ</span><span class="sxs-lookup"><span data-stu-id="f3fc0-146">F# construct</span></span>|<span data-ttu-id="f3fc0-147">Излучаемые конструкции</span><span class="sxs-lookup"><span data-stu-id="f3fc0-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="f3fc0-148">Аргумент `inref<'T>`</span><span class="sxs-lookup"><span data-stu-id="f3fc0-148">`inref<'T>` argument</span></span>|<span data-ttu-id="f3fc0-149">`[In]`атрибут на аргумент</span><span class="sxs-lookup"><span data-stu-id="f3fc0-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="f3fc0-150">`inref<'T>`Вернуться</span><span class="sxs-lookup"><span data-stu-id="f3fc0-150">`inref<'T>` return</span></span>|<span data-ttu-id="f3fc0-151">`modreq`атрибут по стоимости</span><span class="sxs-lookup"><span data-stu-id="f3fc0-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="f3fc0-152">`inref<'T>`в абстрактном слоте или реализации</span><span class="sxs-lookup"><span data-stu-id="f3fc0-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="f3fc0-153">`modreq`на аргумент или возвращение</span><span class="sxs-lookup"><span data-stu-id="f3fc0-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="f3fc0-154">Аргумент `outref<'T>`</span><span class="sxs-lookup"><span data-stu-id="f3fc0-154">`outref<'T>` argument</span></span>|<span data-ttu-id="f3fc0-155">`[Out]`атрибут на аргумент</span><span class="sxs-lookup"><span data-stu-id="f3fc0-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="f3fc0-156">Правила выводов и перегрузки</span><span class="sxs-lookup"><span data-stu-id="f3fc0-156">Type inference and overloading rules</span></span>

<span data-ttu-id="f3fc0-157">Тип `inref<'T>` выводит компилятор F's в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="f3fc0-158">Параметр .NET или тип `IsReadOnly` возврата с атрибутом.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="f3fc0-159">Указатель `this` на тип структуры, который не имеет изменяемых полей.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="f3fc0-160">Адрес местоположения памяти, полученный из другого `inref<_>` указателя.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="f3fc0-161">Когда неявный `inref` адрес в настоящее время принимаются, перегрузка с аргументом `SomeType` `inref<SomeType>`типа предпочтительнее перегрузки с аргументом типа .</span><span class="sxs-lookup"><span data-stu-id="f3fc0-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="f3fc0-162">Пример:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-162">For example:</span></span>

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

<span data-ttu-id="f3fc0-163">В обоих случаях, перегрузки принимая `System.DateTime` решаются, а не перегрузки принимая. `inref<System.DateTime>`</span><span class="sxs-lookup"><span data-stu-id="f3fc0-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="f3fc0-164">Быреф-подобные структуры</span><span class="sxs-lookup"><span data-stu-id="f3fc0-164">Byref-like structs</span></span>

<span data-ttu-id="f3fc0-165">В дополнение `byref` / `inref` / `outref` к трио, вы можете определить свои `byref`собственные структуры, которые могут придерживаться- как семантика.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="f3fc0-166">Это делается <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> с атрибутом:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="f3fc0-167">`IsByRefLike`не подразумевает `Struct`.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="f3fc0-168">Оба должны присутствовать по типу.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-168">Both must be present on the type.</span></span>

<span data-ttu-id="f3fc0-169">Структура`byref`"-как" в F-фз — это тип значения, связанный со стеком.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="f3fc0-170">Он никогда не выделяется на управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="f3fc0-171">A-like `byref`struct полезен для высокопроизводительного программирования, так как он применяется с набором сильных проверок о продолжительности жизни и незахвата.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="f3fc0-172">Правила:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-172">The rules are:</span></span>

* <span data-ttu-id="f3fc0-173">Они могут быть использованы в качестве параметров функции, параметров метода, локальных переменных, возвратов методов.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="f3fc0-174">Они не могут быть статичными или экземплярами класса или нормальной структурой.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="f3fc0-175">Они не могут быть захвачены любой конструкцией закрытия (методы`async` или выражения лямбда).</span><span class="sxs-lookup"><span data-stu-id="f3fc0-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="f3fc0-176">Они не могут быть использованы в качестве общего параметра.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="f3fc0-177">Этот последний пункт имеет решающее значение `|>` для программирования в стиле конвейера, как и общая функция, которая параметризирует его типы ввода.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="f3fc0-178">Это ограничение может `|>` быть смягчено в будущем, так как оно является встроенным и не делает никаких звонков на невстроенные общие функции в его организме.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="f3fc0-179">Хотя эти правила сильно ограничивают использование, они делают это, чтобы выполнить обещание высокопроизводительных вычислений безопасным способом.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="f3fc0-180">Байреф возвращается</span><span class="sxs-lookup"><span data-stu-id="f3fc0-180">Byref returns</span></span>

<span data-ttu-id="f3fc0-181">Byref возвращается из функций или членов F, которые могут быть произведены и использованы.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="f3fc0-182">При потреблении метода `byref`возврата значения косвенно разымают.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="f3fc0-183">Пример:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

<span data-ttu-id="f3fc0-184">Чтобы вернуть значение byref, переменная, содержащая значение, должна жить дольше текущей области.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="f3fc0-185">Кроме того, чтобы вернуть `&value` byref, используйте (где значение является переменной, которая живет дольше, чем текущий объем).</span><span class="sxs-lookup"><span data-stu-id="f3fc0-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="f3fc0-186">Чтобы избежать неявного упоминания, например, передачи ссылки через несколько цепных вызовов, используйте `&x` (где `x` значение).</span><span class="sxs-lookup"><span data-stu-id="f3fc0-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="f3fc0-187">Вы также можете непосредственно назначить возврат. `byref`</span><span class="sxs-lookup"><span data-stu-id="f3fc0-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="f3fc0-188">Рассмотрим следующую (крайне императивную) программу:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-188">Consider the following (highly imperative) program:</span></span>

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

<span data-ttu-id="f3fc0-189">Результат.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="f3fc0-190">Отслеживание для байрефов</span><span class="sxs-lookup"><span data-stu-id="f3fc0-190">Scoping for byrefs</span></span>

<span data-ttu-id="f3fc0-191">Значение `let`A-bound не может иметь свою ссылку, превышающей область, в которой оно было определено.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="f3fc0-192">Например, не допускается следующее:</span><span class="sxs-lookup"><span data-stu-id="f3fc0-192">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="f3fc0-193">Это предотвращает получение различных результатов в зависимости от того, компилируете с помощью оптимизации или нет.</span><span class="sxs-lookup"><span data-stu-id="f3fc0-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
