---
title: 'Byrefs (F #)'
description: 'Дополнительные сведения о byref и типов, схожих byref в F #, которые используются для программирования низкого уровня.'
ms.date: 09/02/2018
ms.openlocfilehash: 6131104e4325f77da84368c337f998c6b2b5309b
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615839"
---
# <a name="byrefs"></a>Byrefs

F # имеет два основных функциональных областей, которые работают в пространстве низкоуровневого программирования:

* `byref` / `inref` / `outref` Типы, которые являются управляемыми указателями. Они имеют ограничения на использование, так что не удается скомпилировать программу, которая является недопустимым во время выполнения.
* Объект `byref`-как структуры, который является [структуры](structures.md) имеет похожую семантику и те же ограничения во время компиляции, что `byref<'T>`. Одним из примеров является <xref:System.Span%601>.

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

## <a name="byref-inref-and-outref"></a>ByRef, inref и outref

Существует три формы `byref`:

* `inref<'T>`, управляемый указатель для чтения базового значения.
* `outref<'T>`, управляемый указатель для записи к исходному значению.
* `byref<'T>`, управляемый указатель для чтения и записи базовое значение.

Объект `byref<'T>` могут передаваться где `inref<'T>` ожидается. Аналогичным образом `byref<'T>` могут передаваться где `outref<'T>` ожидается.

## <a name="using-byrefs"></a>С помощью byrefs

Чтобы использовать `inref<'T>`, необходимо получить значение указателя с `&`:

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let dt = DateTime.Now
f &dt // Pass a pointer to 'dt'
```

Для записи указателя с помощью `outref<'T>` или `byref<'T>`, кроме того, необходимо получить указатель на значение `mutable`.

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

При создании указателя, не считывая их рассмотрите возможность использования `outref<'T>` вместо `byref<'T>`.

### <a name="inref-semantics"></a>Семантика Inref

Рассмотрим следующий код.

```fsharp
let f (x: inref<SomeStruct>) = s.SomeField
```

Семантически это означает следующее:

* Владелец `x` указатель может использовать только для чтения значения.
* Любой указатель, необходимые для `struct` вложенных полей `SomeStruct` получают тип `inref<_>`.

Ниже также верно:

* Нет практической другие потоки или псевдонимы имеет доступ на запись к `x`.
* Нет практической, `SomeStruct` является неизменяемым посредством `x` , `inref`.

Тем не менее, для языка F # типы значения, которые **являются** неизменяемым, `this` указатель определяется как `inref`.

Все вместе эти правила означает, что владелец `inref` указатель не может изменять немедленно содержимое, на которые указывает объем памяти.

### <a name="outref-semantics"></a>Семантика Outref

Цель `outref<'T>` необходимо указать, что указатель должен выполняться только чтение. Неожиданно `outref<'T>` разрешает чтение базового значение несмотря на свое название. Это необходимо для обеспечения совместимости. Семантически `outref<'T>` ничем не отличается от `byref<'T>`.

### <a name="interop-with-c"></a>Взаимодействие с C# #

Язык C# поддерживает `in ref` и `out ref` ключевые слова, в дополнение к `ref` возвращает. В следующей таблице показаны как F # интерпретирует C# выдает что:

|Конструкция C#|F # определил|
|------------|---------|
|`ref` Возвращаемое значение|`outref<'T>`|
|`ref readonly` Возвращаемое значение|`inref<'T>`|
|`in ref` Параметр|`inref<'T>`|
|`out ref` Параметр|`outref<'T>`|

В следующей таблице показаны F # создает новые:

|Конструкции F #|Выпущенный конструкция|
|------------|-----------------|
|`inref<'T>` Аргумент|`[In]` аргумент атрибута|
|`inref<'T>` вернуть|`modreq` значение атрибута|
|`inref<'T>` в абстрактный слот или реализации|`modreq` на аргумента или возвращаемого|
|`outref<'T>` Аргумент|`[Out]` аргумент атрибута|

### <a name="type-inference-and-overloading-rules"></a>Вывод типа и правила перегрузки

`inref<'T>` Тип выводится компилятором F # в следующих случаях:

1. .NET параметра или возвращаемого типа, имеющего `IsReadOnly` атрибута.
2. `this` Указатель на тип структуры, не имеет изменяемых полей.
3. Адрес области памяти, производным от другого `inref<_>` указатель.

Когда неявные адрес `inref` выполнено не было перегрузка с аргументом типа `SomeType` предпочтительнее перегрузка с аргументом типа `inref<SomeType>`. Пример:

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

В обоих случаях перегрузок, принимающих `System.DateTime` разрешаются вместо того чтобы перегрузок, принимающих `inref<System.DateTime>`.

## <a name="byref-like-structs"></a>Структуры типа ByRef

В дополнение к `byref` / `inref` / `outref` вычислительные, вы можете определить собственные структуры, можно придерживаться `byref`-семантику, например. Это делается с помощью <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> атрибут:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` не подразумевает `Struct`. Оба должны присутствовать на тип.

Объект "`byref`-как «структура в F # является типом значения стека привязки. Он никогда не выделяется в управляемой куче. Объект `byref`-как структура полезна для программирования высокой производительности, как реализована с помощью набора строгим проверкам, о времени существования и незахвата. Ниже приведены правила.

* Они могут использоваться как параметры функции, параметры метода, локальные переменные, метод возвращает.
* Они не может быть статическим или члены класса или обычной структуры экземпляров.
* Не может быть перехвачено любой конструкции замыкание (`async` методы или лямбда-выражений).
* Они не может использоваться в качестве универсального параметра.

Последний факт имеет решающее значение для стиля конвейера программирование на F #, как `|>` является универсальной функции, которая параметризует его типы входных данных. Это ограничение может быть снижено для `|>` в будущем, так как она является встроенной и не выполняет каких-либо вызовов неподставляемый универсальные функции в его тексте.

Несмотря на то, что эти правила очень строго ограничить использование, они появляющимися достигается за счет высокопроизводительные вычислительные системы безопасным образом.

## <a name="byref-returns"></a>Возвраты ByRef

Возвраты ByRef из функции F # или члены, которые можно создать и использовать. При использовании `byref`-возвращать метод, значение неявным образом не имеет. Пример:

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

Чтобы избежать неявного разыменования, например передачи ссылки через несколько цепочки вызовов, используйте `&x` (где `x` -значение).

Можно также напрямую назначить возвращаемое значение `byref`. Рассмотрим следующую программу (высокой императивный):

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

Результат.

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a>Отнесение в областям для byrefs

Объект `let`-привязанное значение не может иметь ссылку превышать область, в котором он был определен. Например ниже запрещено:

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

Это предотвращает получение разных результатов в зависимости от того, если компиляция выполняется с оптимизациями, включить или отключить.
