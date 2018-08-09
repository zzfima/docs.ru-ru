---
title: Выражения вычисления (F#)
description: 'Узнайте, как создать удобный синтаксис для записи вычислений в F #, который можно упорядочивать и комбинировать с помощью привязок и конструкций потока управления.'
ms.date: 07/27/2018
ms.openlocfilehash: 4995efc757d99a575ee9fad3abf0465a32398c44
ms.sourcegitcommit: 78bcb629abdbdbde0e295b4e81f350a477864aba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "36207437"
---
# <a name="computation-expressions"></a>Выражения вычисления

Вычисление выражений в F # обеспечивают удобный синтаксис для записи вычислений, которые можно упорядочивать и комбинировать с помощью привязок и конструкций потока управления. В зависимости от типа вычислительного выражения они могут рассматриваться как способ выражения оболочки Monad, monoids, преобразователи monad и applicative функторы. Тем не менее, в отличие от других языках (таких как *нотации* в Haskell), они не привязаны к одну ограниченную абстракцию и не следует полагаться на макросов или других видов метапрограммирование для выполнения удобный и контекстно-зависимые синтаксис.

## <a name="overview"></a>Обзор

Вычисления могут принимать различные формы. Наиболее распространенная форма вычислений является однопоточным выполнением, который является простым для понимания и изменить. Однако не все виды вычисления, так же просто, как однопоточного выполнения. Ниже приведены некоторые примеры таких ситуаций.

* Недетерминированные вычислений
* Асинхронные вычисления
* Effectful вычислений
* Генерирующих вычислений

Как правило, существуют *контекстно-зависимые* вычислений, которые необходимо выполнить в определенных частях приложения. Написание кода контекстно-зависимые может оказаться сложной задачей, как легко вызывал «утечку» вычислений за пределами данного контекста без абстракции, чтобы запретить делать это. Эти абстракции часто трудно написать самостоятельно, поэтому F # имеет общий способ сделать так называемых **выражения вычисления**.

Выражения вычисления предложить универсальный синтаксис и абстракции модель для кодирования контекстно-зависимые вычислений.

Каждое выражение вычисления реализуется *построитель* типа. Тип построителя определяет операции, доступные для вычисления выражения. См. в разделе [Создание нового типа из вычислительного выражения](computation-expressions.md#creating-a-new-type-of-computation-expression), показано, как создать пользовательский вычислительного выражения.

### <a name="syntax-overview"></a>Общие сведения о синтаксисе

Все выражения вычисления иметь следующий вид:

```
builder-expr { cexper }
```

где `builder-expr` имя тип построителя, который определяет вычислительного выражения, и `cexper` является тело выражения вычислительного выражения. Например `async` вычисление выражения кода может выглядеть следующим образом:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

Нет специальных, дополнительный синтаксис в выражении вычисления, как показано в предыдущем примере. С помощью вычислительных выражений возможны следующие выражения формы:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Каждый из этих ключевых слов и других стандартных F # ключевых слов доступны только в выражение вычисления, если они не были определены в резервный тип построителя. Единственное исключение — `match!`, который сам является синтаксическая сладость для применения `let!` следуют шаблону на результат.

Тип построителя — это объект, определяющий специальные методы, которые управляют способом объединенные фрагменты вычислительного выражения; то есть его методы управления, работой вычислительного выражения. Другой способ класс построителя — сказать, что он позволяет настраивать работу многих конструкций F #, такие как циклы и привязки.

### `let!`

`let!` Ключевое слово привязывает результат вызова другого выражения вычисления с именем:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

Привязка вызов вычислительного выражения с `let`, вы не получите результат вычисления выражения. Вместо этого будет привязано значение *нереализованных* вызвать для этого вычисления выражения. Используйте `let!` для привязки к результату.

`let!` определяется `Bind(x, f)` элемент для типа построителя.

### `do!`

`do!` Ключевое слово является для вызов вычислительного выражения, которая возвращает `unit`-тип, такие как (определяется `Zero` член в построителе):

```fsharp
let doThingsAsync data url =
    async {
        do! sumbitData data url
        ...
    }
```

Для [асинхронный рабочий процесс](asynchronous-workflows.md), этот тип является `Async<unit>`. Для других вычислительных выражениях, вероятно, будет тип `CExpType<unit>`.

`do!` определяется `Bind(x, f)` члену в тип построителя, где `f` создает `unit`.

### `yield`

`yield` Ключевое слово является для возврата значения из вычислительного выражения таким образом, чтобы он мог использоваться в качестве <xref:System.Collections.Generic.IEnumerable%601>:

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

Как и в [yield-ключевое слово в C#](../../csharp/language-reference/keywords/yield.md), каждый элемент в вычислительном выражении передается обратно в том случае, как будет выполнен.

`yield` определяется `Yield(x)` члену в тип построителя, где `x` является элементом, чтобы получить обратно.

### `yield!`

`yield!` Ключевое слово является выравнивания коллекция значений из вычислительного выражения:

```fsharp
let squares =
    seq {
        for i in 1..3 -> i * i
    }

let cubes =
    seq {
        for i in 1..3 -> i * i * i
    }

let squaresAndCubes =
    seq {
        yield! squares
        yield! cubes
    }

printfn "%A" squaresAndCubes // Prints - 1; 4; 9; 1; 8; 27
```

Вызывается при вычислении выражения вычисления `yield!` будет иметь свои элементы, полученная назад по одному, выравнивание результата.

`yield!` определяется `YieldFrom(x)` члену в тип построителя, где `x` является коллекцией значений.

### `return`

`return` Ключевое слово заключает значение в тип, соответствующий вычислительного выражения. Помимо вычисления выражений, с помощью `yield`, он используется на «выполнено» вычислительного выражения:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return` определяется `Return(x)` члену в тип построителя, где `x` — это элемент программы-оболочки.

### `return!`

`return!` Ключевое слово понимает, что значение выражения вычисления и помещает результат в тип, соответствующий вычислительное выражение:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!` определяется `ReturnFrom(x)` члену в тип построителя, где `x` является другой вычислительного выражения.

### `match!`

Начиная с F # 4.5, `match!` ключевое слово позволяет встроенный вызов другой вычисления выражений и шаблон сопоставления по его результат:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

При вызове вычислительного выражения с `match!`, он увидит, результат вызова как `let!`. Это часто используется при вызове вычислительного выражения, результат [необязательно](options.md).

## <a name="built-in-computation-expressions"></a>Встроенные вычислительные выражения

Основной библиотеки F # определяет три встроенных вычисление выражения: [выражения последовательности](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [выражения запросов](query-expressions.md).

## <a name="creating-a-new-type-of-computation-expression"></a>Создание нового типа вычислительного выражения

Можно определить характеристики собственных вычислительных выражений, создав класс построителя и определив специальные методы в классе. Класс построителя при необходимости можно определить методы, перечисленные в следующей таблице.

Ниже перечислены методы, которые могут использоваться в классе построитель рабочего процесса.

|**Метод**|**Типичные сигнатуры**|**Описание**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Вызывается для `let!` и `do!` в вычислительные выражения.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Создает оболочку вычислительного выражения в виде функции.|
|`Return`|`'T -> M<'T>`|Вызывается для `return` в вычислительные выражения.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Вызывается для `return!` в вычислительные выражения.|
|`Run`|`M<'T> -> M<'T>` или<br /><br />`M<'T> -> 'T`|Выполняет выражение вычисления.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` или<br /><br />`M<unit> * M<'T> -> M<'T>`|Вызывается для последовательности в вычислительные выражения.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` или<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Вызывается для `for...do` в вычислительных выражениях.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Вызывается для `try...finally` в вычислительных выражениях.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Вызывается для `try...with` в вычислительных выражениях.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|Вызывается для `use` привязок в вычислительные выражения.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Вызывается для `while...do` в вычислительных выражениях.|
|`Yield`|`'T -> M<'T>`|Вызывается для `yield` в вычислительных выражениях.|
|`YieldFrom`|`M<'T> -> M<'T>`|Вызывается для `yield!` в вычислительных выражениях.|
|`Zero`|`unit -> M<'T>`|Вызывается для пустых `else` ветвей `if...then` в вычислительных выражениях.|

Многие методы в класс построителя используют и возвращают `M<'T>` construct, который обычно представляет собой отдельно определенный тип, характеризующий вид объединяемых вычислений, например, `Async<'T>` асинхронные рабочие процессы и `Seq<'T>` для рабочих процессов последовательности. Сигнатуры методов включите их следует объединить и вложенными друг с другом, для объекта рабочего процесса, возвращаемых из одной конструкции, которые могут передаваться на следующий. Когда компилятор анализирует вычислительное выражение, преобразует выражение в серию вложенные вызовы функций с помощью методов в приведенной выше таблице и код в вычислительном выражении.

Вложенное выражение имеет следующую форму:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

В приведенном выше коде вызовы `Run` и `Delay` пропускаются, если они не определены в классе построитель вычисления выражения. Тело выражения вычисление, обозначенное здесь как `{| cexpr |}`, преобразуется в вызовы с участием методов класса построителя посредством преобразований, приведенных в следующей таблице. Вычислительное выражение `{| cexpr |}` определяется рекурсивно в соответствии с этих переводов где `expr` выражение F # и `cexpr` представляет собой выражение вычисления.



|Выражение|Перевод|
|----------|-----------|
|<code>{&#124; let binding in cexpr &#124;}</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{&#124; let! pattern = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; do! expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; yield expr &#124;}</code>|`builder.Yield(expr)`|
|<code>{&#124; yield! expr &#124;}</code>|`builder.YieldFrom(expr)`|
|<code>{&#124; return expr &#124;}</code>|`builder.Return(expr)`|
|<code>{&#124; return! expr &#124;}</code>|`builder.ReturnFrom(expr)`|
|<code>{&#124; use pattern = expr in cexpr &#124;}</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; use! value = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> {&#124; cexpr &#124;}))))</code>|
|<code>{&#124; if expr then cexpr0 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else binder.Zero()</code>|
|<code>{&#124; if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else {&#124; cexpr1 &#124;}</code>|
|<code>{&#124; match expr with &#124; pattern_i -> cexpr_i &#124;}</code>|<code>match expr with &#124; pattern_i -> {&#124; cexpr_i &#124;}</code>|
|<code>{&#124; for pattern in expr do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; for identifier = expr1 to expr2 do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun identifier -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; while expr do cexpr &#124;}</code>|<code>builder.While(fun () -> expr), builder.Delay({&#124;cexpr &#124;})</code>|
|<code>{&#124; try cexpr with &#124; pattern_i -> expr_i &#124;}</code>|<code>builder.TryWith(builder.Delay({&#124; cexpr &#124;}), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{&#124; try cexpr finally expr &#124;}</code>|<code>builder.TryFinally(builder.Delay( {&#124; cexpr &#124;}), (fun () -> expr))</code>|
|<code>{&#124; cexpr1; cexpr2 &#124;}</code>|<code>builder.Combine({&#124;cexpr1 &#124;}, {&#124; cexpr2 &#124;})</code>|
|<code>{&#124; other-expr; cexpr &#124;}</code>|<code>expr; {&#124; cexpr &#124;}</code>|
|<code>{&#124; other-expr &#124;}</code>|`expr; builder.Zero()`|
В предыдущей таблице `other-expr` соответствует выражению, в противном случае отсутствует в таблице. Класс построителя не требуется реализовывать все методы обеспечения поддержки преобразований, приведенных в предыдущей таблице. Эти конструкции, которые не реализованы недоступны в вычислительные выражения этого типа. Например, если вы не хотите поддерживать `use` ключевое слово в вычисление выражения, можно опустить определение `Use` в классе построителя.

В следующем примере кода показано выражение вычисления, инкапсулирующий вычисление вычисленному один шаг ряд шагов, которые могут быть одновременно. Объект размеченные объединения типа `OkOrException`, кодирует состояние ошибки, выражения, вычисленному на данный момент. Этот код демонстрирует несколько типичных шаблонов, которые можно использовать в выражениях вычисления, такие как стандартный реализации некоторых методов построителя.

```fsharp
// Computations that can be run step by step
type Eventually<'T> =
    | Done of 'T
    | NotYetDone of (unit -> Eventually<'T>)

module Eventually =
    // The bind for the computations. Append 'func' to the
    // computation.
    let rec bind func expr =
        match expr with
        | Done value -> NotYetDone (fun () -> func value)
        | NotYetDone work -> NotYetDone (fun () -> bind func (work()))

    // Return the final value wrapped in the Eventually type.
    let result value = Done value

    type OkOrException<'T> =
        | Ok of 'T
        | Exception of System.Exception

    // The catch for the computations. Stitch try/with throughout
    // the computation, and return the overall result as an OkOrException.
    let rec catch expr =
        match expr with
        | Done value -> result (Ok value)
        | NotYetDone work ->
            NotYetDone (fun () ->
                let res = try Ok(work()) with | exn -> Exception exn
                match res with
                | Ok cont -> catch cont // note, a tailcall
                | Exception exn -> result (Exception exn))

    // The delay operator.
    let delay func = NotYetDone (fun () -> func())

    // The stepping action for the computations.
    let step expr =
        match expr with
        | Done _ -> expr
        | NotYetDone func -> func ()

    // The rest of the operations are boilerplate.
    // The tryFinally operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryFinally expr compensation =
        catch (expr)
        |> bind (fun res -> 
            compensation();
            match res with
            | Ok value -> result value
            | Exception exn -> raise exn)

    // The tryWith operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryWith exn handler =
        catch exn
        |> bind (function Ok value -> result value | Exception exn -> handler exn)

    // The whileLoop operator.
    // This is boilerplate in terms of "result" and "bind".
    let rec whileLoop pred body =
        if pred() then body |> bind (fun _ -> whileLoop pred body)
        else result ()

    // The sequential composition operator.
    // This is boilerplate in terms of "result" and "bind".
    let combine expr1 expr2 =
        expr1 |> bind (fun () -> expr2)

    // The using operator.
    let using (resource: #System.IDisposable) func =
        tryFinally (func resource) (fun () -> resource.Dispose())

    // The forLoop operator.
    // This is boilerplate in terms of "catch", "result", and "bind".
    let forLoop (collection:seq<_>) func =
        let ie = collection.GetEnumerator()
        tryFinally 
            (whileLoop 
                (fun () -> ie.MoveNext()) 
                (delay (fun () -> let value = ie.Current in func value)))
            (fun () -> ie.Dispose())

// The builder class.
type EventuallyBuilder() =
    member x.Bind(comp, func) = Eventually.bind func comp
    member x.Return(value) = Eventually.result value
    member x.ReturnFrom(value) = value
    member x.Combine(expr1, expr2) = Eventually.combine expr1 expr2
    member x.Delay(func) = Eventually.delay func
    member x.Zero() = Eventually.result ()
    member x.TryWith(expr, handler) = Eventually.tryWith expr handler
    member x.TryFinally(expr, compensation) = Eventually.tryFinally expr compensation
    member x.For(coll:seq<_>, func) = Eventually.forLoop coll func
    member x.Using(resource, expr) = Eventually.using resource expr

let eventually = new EventuallyBuilder()

let comp = eventually {
    for x in 1..2 do
        printfn " x = %d" x
    return 3 + 4 }

// Try the remaining lines in F# interactive to see how this 
// computation expression works in practice.
let step x = Eventually.step x

// returns "NotYetDone <closure>"
comp |> step

// prints "x = 1"
// returns "NotYetDone <closure>"
comp |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "NotYetDone <closure>"
comp |> step |> step |> step |> step |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step |> step |> step |> step |> step
```

Вычислительное выражение имеет базовый тип, который возвращает выражение. Базовый тип может представлять вычисленный результат или отложенное вычисление, которое может быть выполнена, или обеспечивают способ итерации по коллекции какого-либо рода. В предыдущем примере, был базовый тип **со временем**. Для выражения последовательности, базовым типом является <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Для выражения запроса, базовым типом является <xref:System.Linq.IQueryable?displayProperty=nameWithType>. Для асинхронных рабочих процессов, базовым типом является [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7). `Async` Объект представляет работу, выполняемую для вычисления результата. Например, можно вызвать метод [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) для выполнения вычислений и возвращают результат.

## <a name="custom-operations"></a>Пользовательские операции
Можно определить пользовательскую операцию вычисления выражения и использовать пользовательскую операцию в качестве оператора в выражение вычисления. Например можно включить оператор запроса в выражении запроса. При определении пользовательской операции, необходимо определить доход и для методов в выражение вычисления. Чтобы определить пользовательскую операцию, поместить его в класс построителя для вычисления выражения, а затем применить [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19). Этот атрибут принимает строку в качестве аргумента, которое является именем для использования в пользовательской операции. Это имя поступает в область действия в начале открывающая фигурная скобка вычислительного выражения. Таким образом не следует использовать идентификаторы, которые имеют имя, совпадающее с именем пользовательской операции в этом блоке. Например, такие как избежать использования идентификаторов `all` или `last` в выражениях запросов.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Расширение существующего построители с новых пользовательских операций
Если у вас уже есть класс построителя, можно расширить его пользовательских операций из вне данного класса построителя. Расширения необходимо объявлять в модулях. Пространства имен не может содержать члены расширений, за исключением в файле одной и той же группе объявление пространства имен, где определен тип.

В следующем примере показано расширение существующего `Microsoft.FSharp.Linq.QueryBuilder` класса.

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>См. также
[Справочник по языку F#](index.md)

[Асинхронные рабочие потоки](asynchronous-workflows.md)

[Последовательности](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[Выражения запросов](query-expressions.md)
