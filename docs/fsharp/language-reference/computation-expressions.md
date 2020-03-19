---
title: Выражения вычисления
description: Узнайте, как создать удобный синтаксис для написания вычислений в ФЗ, которые можно секвенировать и комбинировать с помощью конструкций и привязок потоков управления.
ms.date: 11/04/2019
ms.openlocfilehash: 55406cc12d9e6e890fe69d712f79486d23b84452
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401085"
---
# <a name="computation-expressions"></a>Выражения вычисления

Выражения вычислений в F-образном варианте обеспечивают удобный синтаксис для написания вычислений, которые можно секвенировать и комбинировать с помощью конструкций и переплетов потоков управления. В зависимости от вида вычислительного выражения, их можно рассматривать как способ выражения монад, моноиды, монадные трансформаторы и применимые фанкторы. Однако, в отличие от других языков (таких как *do-notation* в Haskell), они не привязаны к одной абстракции, и не полагаются на макросы или другие формы метапрограммирования для выполнения удобного и чувствительного к контексту синтаксиса.

## <a name="overview"></a>Обзор

Вычисления могут принимать различные формы. Наиболее распространенной формой вычислений является однопоточное выполнение, которое легко понять и изменить. Однако не все формы вычислений так просты, как однопоточное выполнение. Некоторые примеры:

- Недетерминированные вычисления
- Асинхронные вычисления
- Эффективные вычисления
- Генеративные вычисления

В более общем плане существуют чувствительные к *контексту* вычисления, которые необходимо выполнять в определенных частях приложения. Написание чувствительного к контексту кода может быть сложной задачей, так как легко «утечка» вычислений за пределами данного контекста без абстракций, чтобы помешать вам сделать это. Эти абстракции часто сложно писать самостоятельно, поэтому у F-образного способа сделать так называемые **вычислительные выражения.**

Выражения вычислений предлагают единую модель синтаксиса и абстракции для кодирования чувствительных к контексту вычислений.

Каждое выражение вычислений поддерживается типом *builder.* Тип builder определяет операции, доступные для выражения вычислений. Смотрите [Создание нового типа выражения вычислений](computation-expressions.md#creating-a-new-type-of-computation-expression), который показывает, как создать пользовательское выражение вычислений.

### <a name="syntax-overview"></a>Общие сведения о синтаксисе

Все вычислительные выражения имеют следующую форму:

```fsharp
builder-expr { cexper }
```

где `builder-expr` находится имя типа builder, определяющего выражение вычислений, и `cexper` является выражением выражения вычислений. Например, `async` код выражения вычислений может выглядеть следующим образом:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

В вычислительном выражении имеется специальный дополнительный синтаксис, как показано в предыдущем примере. Возможны следующие формы выражения с помощью вычислительных выражений:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Каждое из этих ключевых слов и другие стандартные ключевые слова F's доступны только в выражении вычислений, если они были определены в типе резервного строителя. Единственным исключением является, `match!`который сам по себе синтаксического сахара для использования `let!` следуют шаблон матч на результат.

Тип builder — это объект, определяющий специальные методы, определяющие способ объединения фрагментов выражения вычислений; то есть, его методы контролируют, как работает выражение вычислений. Другой способ описания класса builder заключается в том, чтобы сказать, что он позволяет настроить работу многих конструкций F, таких как петли и привязки.

### `let!`

Ключевое `let!` слово связывает результат вызова с другим выражением вычислений с именем:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

Если вы привяжете вызов `let`к экспрессии вычислений с, вы не получите результат выражения вычислений. Вместо этого вы будете связаны значение *нереализованного* вызова, что выражение вычислений. Используйте `let!` для привязки к результату.

`let!`определяется `Bind(x, f)` участником по типу builder.

### `do!`

Ключевое `do!` слово предназначено для вызова вычислительного выражения, которое возвращает `unit`тип типа -like (определяемый `Zero` участником в builder):

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

Для [рабочего процесса async](asynchronous-workflows.md) `Async<unit>`этот тип . Для других вычислений тип, скорее `CExpType<unit>`всего, будет .

`do!`определяется участником `Bind(x, f)` по типу `f` builder, `unit`где производится .

### `yield`

Ключевое `yield` слово предназначено для возвращения значения из выражения вычислений, <xref:System.Collections.Generic.IEnumerable%601>чтобы его можно было использовать как:

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

В большинстве случаев, он может быть опущен абонентов. Наиболее распространенный `yield` способ опустить это с оператором: `->`

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

Для более сложных выражений, которые могут дать много различных значений, и, возможно, условно, просто опуская ключевое слово может сделать:

```fsharp
let weekdays includeWeekend =
    seq {
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    }
```

Как и в том, что ключевое [слово доходности в C,](../../csharp/language-reference/keywords/yield.md)каждый элемент в выражении вычислений возвращается, так как он итерирован.

`yield`определяется участником `Yield(x)` по типу `x` builder, где элемент должен уступить.

### `yield!`

Ключевое `yield!` слово предназначено для выравнивания коллекции значений из вычислительного выражения:

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

При оценке вызываемые `yield!` выражения вычислений будут иметь свои элементы, которые будут отступать один за одним, уплощение результата.

`yield!`определяется участником `YieldFrom(x)` по типу `x` builder, где находится собрание значений.

В `yield` `yield!` отличие от , должны быть четко указаны. Его поведение не подразумевается в выражениях вычислений.

### `return`

Ключевое `return` слово обертывает значение в типе, соответствующем выражению вычислений. Помимо использования `yield`вычислительных выражений, он используется для "завершения" вычислительного выражения:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return`определяется участником `Return(x)` на типе `x` builder, где находится элемент для обертывания.

### `return!`

Ключевое `return!` слово реализует значение выражения вычислений и обертывания, которые приводят к типу, соответствующему выражению вычислений:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!`определяется участником `ReturnFrom(x)` на типе `x` builder, где находится другое выражение вычислений.

### `match!`

Ключевое `match!` слово позволяет ввести вызов в другое выражение вычислений и шаблон соответствия по его результату:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

При вызове вычислительного `match!`выражения с помощью, он `let!`будет понимать результат вызова, как . Это часто используется при вызове вычислительного выражения, где результат является [необязательным.](options.md)

## <a name="built-in-computation-expressions"></a>Встроенные вычислительные выражения

В базовой библиотеке F-образной физики определены три встроенных вычисления: [экспрессии последовательности,](sequences.md) [асинхронные рабочие процессы](asynchronous-workflows.md)и [экспрессии запросов.](query-expressions.md)

## <a name="creating-a-new-type-of-computation-expression"></a>Создание нового типа вычислительного выражения

Характеристики собственных вычислений можно определить, создав класс строителя и определив определенные специальные методы в классе. Класс builder может дополнительно определить методы, перечисленные в следующей таблице.

В следующей таблице описаны методы, которые могут быть использованы в классе строителей рабочего процесса.

|**Метод**|**Типичная подпись (ы)**|**Описание**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Вызывается `let!` `do!` и в вычислительных выражениях.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Оберните выражение вычислений в качестве функции.|
|`Return`|`'T -> M<'T>`|Вызывается `return` в вычислительных выражениях.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Вызывается `return!` в вычислительных выражениях.|
|`Run`|`M<'T> -> M<'T>` или<br /><br />`M<'T> -> 'T`|Выполняет вычисление выражения.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` или<br /><br />`M<unit> * M<'T> -> M<'T>`|Требуется секвенирование в вычислительных выражениях.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` или<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Вызывается `for...do` выражения в выражениях вычислений.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Вызывается `try...finally` выражения в выражениях вычислений.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Вызывается `try...with` выражения в выражениях вычислений.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|Вызывается `use` привязки в вычислительных выражениях.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Вызывается `while...do` выражения в выражениях вычислений.|
|`Yield`|`'T -> M<'T>`|Вызывается `yield` выражения в выражениях вычислений.|
|`YieldFrom`|`M<'T> -> M<'T>`|Вызывается `yield!` выражения в выражениях вычислений.|
|`Zero`|`unit -> M<'T>`|Вызывается `else` пустые `if...then` ветви выражений в вычислительных выражениях.|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|Означает, что выражение вычислений `Run` передается участнику в качестве цитаты. Он переводит все экземпляры вычислений в цитату.|

Многие методы в классе строителей используют `M<'T>` и возвращают конструкцию, которая обычно является отдельно определенным типом, который `Async<'T>` характеризует вид вычислений, комбинируется, например, для асинхронных рабочих процессов и `Seq<'T>` для рабочих процессов последовательности. Подписи этих методов позволяют объединять и вкладывать друг с другом, так что объект рабочего процесса, возвращенный из одной конструкции, может быть передан другой. Компилятор, когда он разбирает выражение вычислений, преобразует выражение в ряд вложенных вызовов функции, используя методы в предыдущей таблице и код в выражении вычислений.

Вложенное выражение имеет следующую форму:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

В приведенном выше коде вызовы `Run` и `Delay` опущены, если они не определены в классе builder выражения вычислений. Тело выражения вычисления, здесь обозначается как `{| cexpr |}`, переводится в вызовы, связанные с методами класса строитель переводы, описанные в следующей таблице. Выражение `{| cexpr |}` вычислений определяется рекурсивно в соответствии с этими переводами, где `expr` является выражением F и `cexpr` является вычислительным выражением.

|Выражение|Перевод|
|----------|-----------|
|<code>{ let binding in cexpr }</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{ let! pattern = expr in cexpr }</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ do! expr in cexpr }</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{ yield expr }</code>|`builder.Yield(expr)`|
|<code>{ yield! expr }</code>|`builder.YieldFrom(expr)`|
|<code>{ return expr }</code>|`builder.Return(expr)`|
|<code>{ return! expr }</code>|`builder.ReturnFrom(expr)`|
|<code>{ use pattern = expr in cexpr }</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ use! value = expr in cexpr }</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> { cexpr }))))</code>|
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else builder.Zero()</code>|
|<code>{ if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then { cexpr0 } else { cexpr1 }</code>|
|<code>{ match expr with &#124; pattern_i -> cexpr_i }</code>|<code>match expr with &#124; pattern_i -> { cexpr_i }</code>|
|<code>{ for pattern in expr do cexpr }</code>|<code>builder.For(enumeration, (fun pattern -> { cexpr }))</code>|
|<code>{ for identifier = expr1 to expr2 do cexpr }</code>|<code>builder.For(enumeration, (fun identifier -> { cexpr }))</code>|
|<code>{ while expr do cexpr }</code>|<code>builder.While(fun () -> expr, builder.Delay({ cexpr }))</code>|
|<code>{ try cexpr with &#124; pattern_i -> expr_i }</code>|<code>builder.TryWith(builder.Delay({ cexpr }), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{ try cexpr finally expr }</code>|<code>builder.TryFinally(builder.Delay( { cexpr }), (fun () -> expr))</code>|
|<code>{ cexpr1; cexpr2 }</code>|<code>builder.Combine({ cexpr1 }, { cexpr2 })</code>|
|<code>{ other-expr; cexpr }</code>|<code>expr; { cexpr }</code>|
|<code>{ other-expr }</code>|`expr; builder.Zero()`|

В предыдущей `other-expr` таблице описывается выражение, которое в противном случае не перечислено в таблице. Классу строителя не нужно реализовывать все методы и поддерживать все переводы, перечисленные в предыдущей таблице. Те конструкции, которые не реализованы, недоступны в вычислительных выражениях этого типа. Например, если вы не хотите `use` поддерживать ключевое слово в выражениях вычислений, `Use` вы можете пропустить определение в классе builder.

Следующий пример кода показывает выражение вычислений, которое инкапсулирует вычисление как ряд шагов, которые можно оценить на один шаг за один раз. Дискриминируемый `OkOrException`тип союза, кодирует состояние ошибки выражения, оцениваемые до сих пор. Этот код демонстрирует несколько типичных шаблонов, которые можно использовать в выражениях вычислений, например шаблонные реализации некоторых методов builder.

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
        | Done value -> func value
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
// returns "Done 7"
comp |> step |> step |> step |> step
```

Выражение вычислений имеет базовый тип, который возвращает выражение. Базовый тип может представлять вычисленный результат или задержку вычислений, которые могут быть выполнены, или он может обеспечить способ итерации через некоторый тип коллекции. В предыдущем примере базовый тип был **в конечном итоге**. Для выражения последовательности базовый <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>тип . Для выражения запроса базовый тип <xref:System.Linq.IQueryable?displayProperty=nameWithType>— это . Для асинхронного рабочего процесса базовый тип [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7). Объект `Async` представляет работу, которую предстоит выполнить для вычисления результата. Например, вы [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) призываете выполнить вычисление и вернуть результат.

## <a name="custom-operations"></a>Пользовательские операции

Можно определить пользовательскую операцию на вычислительном выражении и использовать пользовательскую операцию в качестве оператора в выражении вычислений. Например, можно включить оператора запроса в выражение запроса. При определении пользовательской операции необходимо определить доходность и методы в выражении вычислений. Чтобы определить пользовательскую операцию, поместите ее в класс builder [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)для выражения вычислений, а затем примените . Этот атрибут использует строку в качестве аргумента, то есть имя, которое будет использоваться в пользовательской операции. Это имя вступает в сферу применения в начале вступительной скобки вычислительного выражения. Поэтому не следует использовать идентификаторы с тем же именем, что и пользовательская операция в этом блоке. Например, избегайте использования идентификаторов, таких как `all` или `last` в выражениях запросов.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Расширение существующих строителей с новыми пользовательскими операциями

Если у вас уже есть класс builder, его пользовательские операции могут быть расширены из-за пределов этого класса builder. Расширения должны быть объявлены в модулях. Пространства имен не могут содержать члены расширения, за исключением того же файла и той же группы декларации пространства имен, где определяется тип.

Следующий пример показывает расширение `Microsoft.FSharp.Linq.QueryBuilder` существующего класса.

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>См. также раздел

- [Ссылка на язык F](index.md)
- [Асинхронные рабочие потоки](asynchronous-workflows.md)
- [Последовательности](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [Выражения запросов](query-expressions.md)
