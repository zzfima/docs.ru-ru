---
title: Byref
description: Сведения о типах, схожих с ByRef и F#ByRef, в, которые используются для низкоуровневого программирования.
ms.date: 11/04/2019
ms.openlocfilehash: 5aaee1e4eac9ce0d7e9ba89a2ab5f745d31367a0
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901310"
---
# <a name="byrefs"></a>Byref

F#имеет две основные функциональные области, которые имеют место в пространстве низкоуровневого программирования:

* `byref`/`inref`/типы `outref`, которые являются управляемыми указателями. Они имеют ограничения на использование, поэтому нельзя компилировать программу, недопустимую во время выполнения.
* Структура, подобная `byref`, которая представляет собой [структуру](structures.md) , которая имеет подобную семантику и те же ограничения времени компиляции, что и `byref<'T>`. Один из примеров — <xref:System.Span%601>.

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

## <a name="byref-inref-and-outref"></a>ByRef, инреф и аутреф

Существует три формы `byref`:

* `inref<'T>`— управляемый указатель для чтения базового значения.
* `outref<'T>`— управляемый указатель для записи в базовое значение.
* `byref<'T>`— управляемый указатель для чтения и записи базового значения.

Можно передать `byref<'T>`, где ожидается `inref<'T>`. Аналогичным образом можно передать `byref<'T>`, где ожидается `outref<'T>`.

## <a name="using-byrefs"></a>Использование ByRef

Чтобы использовать `inref<'T>`, необходимо получить значение указателя с `&`:

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

Для записи в указатель с помощью `outref<'T>` или `byref<'T>`необходимо также сделать значение, которое захватит указатель на `mutable`.

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

Если вы пишете только указатель, а не читаете его, рассмотрите возможность использования `outref<'T>` вместо `byref<'T>`.

### <a name="inref-semantics"></a>Семантика инреф

Рассмотрим следующий код.

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

В семантическом виде это означает следующее:

* Владелец указателя `x` может использовать его только для чтения значения.
* Любой указатель, полученный к `struct` полям, вложенным в `SomeStruct`, получает `inref<_>`типа.

Также верно следующее:

* Нет никаких последствие того, что другие потоки или псевдонимы не имеют доступа на запись к `x`.
* Нечего никакое `SomeStruct` неизменяемо, поскольку `x` является `inref`.

Однако для F# типов значений, которые **являются** неизменяемыми, `this` указатель выводится как `inref`.

Все эти правила вместе означают, что владелец указателя `inref` не может изменить немедленное содержимое памяти, на которое указывает.

### <a name="outref-semantics"></a>Семантика аутреф

Цель `outref<'T>` — указать, что указатель должен быть записан только в. Неожиданно `outref<'T>` позволяет считывать базовое значение, несмотря на его имя. Это происходит в целях совместимости. Семантически `outref<'T>` не отличается от `byref<'T>`.

### <a name="interop-with-c"></a>Взаимодействие с\#ом C

C#поддерживает ключевые слова `in ref` и `out ref`, а также возвращает `ref`. В следующей таблице показано, F# как интерпретирует C# выдачи:

|C#создания|F#выводит|
|------------|---------|
|`ref` возвращаемое значение|`outref<'T>`|
|`ref readonly` возвращаемое значение|`inref<'T>`|
|Параметр `in ref`|`inref<'T>`|
|Параметр `out ref`|`outref<'T>`|

В следующей таблице показано, F# какие выдачи:

|F#создания|Выпущенная конструкция|
|------------|-----------------|
|Аргумент `inref<'T>`|атрибут `[In]` в аргументе|
|`inref<'T>` возврат|атрибут `modreq` в значении|
|`inref<'T>` в абстрактном слоте или реализации|`modreq` аргумента или Return|
|Аргумент `outref<'T>`|атрибут `[Out]` в аргументе|

### <a name="type-inference-and-overloading-rules"></a>Определение типа и перегрузка правил

Тип `inref<'T>` выводится F# компилятором в следующих случаях:

1. Параметр или возвращаемый тип .NET, имеющий атрибут `IsReadOnly`.
2. `this` указатель на тип структуры, не имеющий изменяемых полей.
3. Адрес области памяти, полученной из другого указателя `inref<_>`.

При использовании неявного адреса `inref` перегрузку с аргументом типа `SomeType` предпочтительнее для перегрузки с аргументом типа `inref<SomeType>`. Например:

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

В обоих случаях перегрузки, принимающие `System.DateTime`, разрешаются вместо перегрузок, принимающих `inref<System.DateTime>`.

## <a name="byref-like-structs"></a>Структуры, аналогичные ByRef

Помимо `byref`/`inref`/`outref` три, можно определить собственные структуры, которые могут соответствовать семантике `byref`. Это делается с помощью атрибута <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` не подразумевает `Struct`. Оба должны присутствовать в типе.

"`byref`-похожая" структура в F# — это тип значения, привязанный к стеку. Он никогда не выделяется в управляемой куче. Структура, подобная `byref`, полезна для высокопроизводительного программирования, так как она применяется к набору строгих проверок времени существования и без записи. Правила таковы.

* Их можно использовать в качестве параметров функций, параметров методов, локальных переменных, возвращаемых методом.
* Они не могут быть статическими или членами экземпляров класса или обычной структуры.
* Они не могут быть захвачены какой-либо конструкцией замыкания (`async` методами или лямбда-выражениями).
* Их нельзя использовать в качестве универсального параметра.

Последний момент является ключевым для F# программирования в стиле конвейера, так как `|>` является универсальной функцией, которая выполняет параметризацию входных типов. Это ограничение может быть ослаблено для `|>` в будущем, так как оно встроено и не вызывает невстроенные универсальные функции в своем тексте.

Хотя эти правила строго ограничивают использование, они делают это для обеспечения безопасности высокопроизводительных вычислительных систем.

## <a name="byref-returns"></a>Возвраты по ссылке

Функция ByRef возвращает F# из функций или членов, которые могут быть созданы и использованы. При использовании метода, возвращающего `byref`, значение неявно разыменовано. Например:

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

Чтобы избежать неявного разыменования, например передачи ссылки через несколько цепочек вызовов, используйте `&x` (где `x` является значением).

Можно также напрямую назначить `byref`возврата. Рассмотрим следующую (очень императивную) программу:

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

## <a name="scoping-for-byrefs"></a>Определение области для ByRef

Значение с привязкой к `let`не может превышать область, в которой он был определен. Например, запрещены следующие возможности:

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

Это предотвращает получение различных результатов в зависимости от того, выполняется ли компиляция с оптимизацией.
