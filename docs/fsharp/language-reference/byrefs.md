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
# <a name="byrefs"></a>Byref

ФЗ имеет две основные функциональные области, которые имеют дело в пространстве низкоуровневого программирования:

* `byref` / `inref` / Типы, `outref` которыми управляют указатели. Они имеют ограничения на использование, так что вы не можете собрать программу, которая является недействительной во время выполнения.
* A-как `byref`структурирует, который представляет собой [структуру,](structures.md) которая имеет аналогичную `byref<'T>`семантику и те же ограничения времени компиляции, как . Одним из <xref:System.Span%601>примеров является .

## <a name="syntax"></a>Синтаксис

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

## <a name="byref-inref-and-outref"></a>Byref, inref, и outref

Существует три `byref`формы:

* `inref<'T>`, управляемый указатель для чтения базового значения.
* `outref<'T>`, управляемый указатель для записи к базовому значению.
* `byref<'T>`, управляемый указатель для чтения и написания базового значения.

A `byref<'T>` может быть `inref<'T>` пройден там, где ожидается. Аналогичным образом, a `byref<'T>` может `outref<'T>` быть пройден там, где ожидается.

## <a name="using-byrefs"></a>Использование байрефов

Для `inref<'T>`использования, вам нужно получить значение `&`указателя с:

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

Чтобы написать указателю с `outref<'T>` `byref<'T>`помощью или, вы также должны сделать значение вы захватить указатель на `mutable`.

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

Если вы пишете только указатель вместо того, `byref<'T>`чтобы читать его, рассмотреть вопрос об использовании `outref<'T>` вместо .

### <a name="inref-semantics"></a>Семантика Инрефа

Рассмотрим следующий код.

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

Семантически это означает следующее:

* Держатель указателя `x` может использовать его только для чтения значения.
* Любой указатель, приобретенный на `struct` полях, вложенных в, `SomeStruct` дается типом. `inref<_>`

Верно и следующее:

* Существует никаких последствий, что другие потоки или `x`псевдонимы не имеют доступа к записи .
* Существует никаких `SomeStruct` последствий, что является `x` непреложной в силу того, что `inref`.

Тем не менее, для **are** типов значений `this` F, которые являются неизменяемыми, указатель выводится как `inref`.

Все эти правила вместе означают, `inref` что держатель указателя не может изменять немедленное содержимое памяти, на которую указывается.

### <a name="outref-semantics"></a>Семантика Аутрефа

Цель состоит `outref<'T>` в том, чтобы указать, что указатель должен быть написан только. Неожиданно `outref<'T>` позволяет читать базовое значение, несмотря на его название. Это для целей совместимости. Семантически, `outref<'T>` ничем `byref<'T>`не отличается от .

### <a name="interop-with-c"></a>Интероп с C\#

В дополнение `in ref` к `out ref` возвратам, в `ref` дополнение к возвратам, компания поддерживает и ключевые слова. В следующей таблице показано, как f's интерпретирует то, что испускает C':

|Конструкция СИ|Выводы ФЗ|
|------------|---------|
|`ref`возвратное значение|`outref<'T>`|
|`ref readonly`возвратное значение|`inref<'T>`|
|Параметр `in ref`|`inref<'T>`|
|Параметр `out ref`|`outref<'T>`|

В следующей таблице показано, что испускает F-излучает:

|Конструкция ФЗ|Излучаемые конструкции|
|------------|-----------------|
|Аргумент `inref<'T>`|`[In]`атрибут на аргумент|
|`inref<'T>`Вернуться|`modreq`атрибут по стоимости|
|`inref<'T>`в абстрактном слоте или реализации|`modreq`на аргумент или возвращение|
|Аргумент `outref<'T>`|`[Out]`атрибут на аргумент|

### <a name="type-inference-and-overloading-rules"></a>Правила выводов и перегрузки

Тип `inref<'T>` выводит компилятор F's в следующих случаях:

1. Параметр .NET или тип `IsReadOnly` возврата с атрибутом.
2. Указатель `this` на тип структуры, который не имеет изменяемых полей.
3. Адрес местоположения памяти, полученный из другого `inref<_>` указателя.

Когда неявный `inref` адрес в настоящее время принимаются, перегрузка с аргументом `SomeType` `inref<SomeType>`типа предпочтительнее перегрузки с аргументом типа . Пример:

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

В обоих случаях, перегрузки принимая `System.DateTime` решаются, а не перегрузки принимая. `inref<System.DateTime>`

## <a name="byref-like-structs"></a>Быреф-подобные структуры

В дополнение `byref` / `inref` / `outref` к трио, вы можете определить свои `byref`собственные структуры, которые могут придерживаться- как семантика. Это делается <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> с атрибутом:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike`не подразумевает `Struct`. Оба должны присутствовать по типу.

Структура`byref`"-как" в F-фз — это тип значения, связанный со стеком. Он никогда не выделяется на управляемой куче. A-like `byref`struct полезен для высокопроизводительного программирования, так как он применяется с набором сильных проверок о продолжительности жизни и незахвата. Правила:

* Они могут быть использованы в качестве параметров функции, параметров метода, локальных переменных, возвратов методов.
* Они не могут быть статичными или экземплярами класса или нормальной структурой.
* Они не могут быть захвачены любой конструкцией закрытия (методы`async` или выражения лямбда).
* Они не могут быть использованы в качестве общего параметра.

Этот последний пункт имеет решающее значение `|>` для программирования в стиле конвейера, как и общая функция, которая параметризирует его типы ввода. Это ограничение может `|>` быть смягчено в будущем, так как оно является встроенным и не делает никаких звонков на невстроенные общие функции в его организме.

Хотя эти правила сильно ограничивают использование, они делают это, чтобы выполнить обещание высокопроизводительных вычислений безопасным способом.

## <a name="byref-returns"></a>Байреф возвращается

Byref возвращается из функций или членов F, которые могут быть произведены и использованы. При потреблении метода `byref`возврата значения косвенно разымают. Пример:

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

Чтобы вернуть значение byref, переменная, содержащая значение, должна жить дольше текущей области.
Кроме того, чтобы вернуть `&value` byref, используйте (где значение является переменной, которая живет дольше, чем текущий объем).

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

Чтобы избежать неявного упоминания, например, передачи ссылки через несколько цепных вызовов, используйте `&x` (где `x` значение).

Вы также можете непосредственно назначить возврат. `byref` Рассмотрим следующую (крайне императивную) программу:

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

Результат.

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a>Отслеживание для байрефов

Значение `let`A-bound не может иметь свою ссылку, превышающей область, в которой оно было определено. Например, не допускается следующее:

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

Это предотвращает получение различных результатов в зависимости от того, компилируете с помощью оптимизации или нет.
