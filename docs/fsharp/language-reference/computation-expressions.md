---
title: Выражения вычисления
description: Узнайте, как создать удобный синтаксис для написания вычислений в F# , которые могут быть упорядочены и объединены с помощью конструкций и привязок потока управления.
ms.date: 03/15/2019
ms.openlocfilehash: ea560bb6eec82672544c7c442b671b63e405474c
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799055"
---
# <a name="computation-expressions"></a>Выражения вычисления

Вычислительные выражения F# в предоставляют удобный синтаксис для написания вычислений, которые могут быть упорядочены и объединены с помощью конструкций и привязок потока управления. В зависимости от типа вычислительного выражения их можно представить как способ выражения составных, моноидс, нестандартных преобразователей и аппликативе операторов. Однако, в отличие от других языков (например *, в* Haskell), они не привязаны к одной абстракции и не полагаются на макросы или другие формы метапрограммирование для выполнения удобного и контекстно-чувствительного синтаксиса.

## <a name="overview"></a>Обзор

Вычисления могут принимать множество форм. Наиболее распространенной формой вычислений является однопотоковое выполнение, которое легко понять и изменить. Однако не все формы вычислений являются простым выполнением с одним потоком. Ниже приведены некоторые примеры таких ситуаций.

- Недетерминированные вычисления
- Асинхронные вычисления
- Вычисления с эффективностью
- Регенеративные вычисления

Как правило, существуют *зависящие от контекста* вычисления, которые необходимо выполнить в определенных частях приложения. Написание контекстно-зависимого кода может быть непростой задачей, так как легко «утечку» вычислений за пределами данного контекста без абстракций, чтобы предотвратить это. Эти абстракции часто сложны в написании самих себя, т F# . е. у них есть обобщенный способ сделать это, называемый **вычислительными выражениями**.

Вычислительные выражения предлагают единый синтаксис и модель абстракции для кодирования зависящих от контекста вычислений.

Каждое вычислительное выражение поддерживается типом *построителя* . Тип построителя определяет операции, доступные для вычислительного выражения. См. раздел [Создание нового типа вычислительного выражения](computation-expressions.md#creating-a-new-type-of-computation-expression), в котором показано, как создать пользовательское вычислительное выражение.

### <a name="syntax-overview"></a>Обзор синтаксиса

Все выражения вычислений имеют следующий вид:

```fsharp
builder-expr { cexper }
```

где `builder-expr` — имя типа построителя, определяющего вычислительное выражение, а `cexper` — тело выражения вычисления. Например, `async` код выражения вычисления может выглядеть следующим образом:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

В вычислительном выражении доступен Специальный дополнительный синтаксис, как показано в предыдущем примере. В выражениях вычислений возможны следующие формы выражений:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Каждое из этих ключевых слов и другие стандартные F# ключевые слова доступны только в вычислительном выражении, если они были определены в типе построителя резервных копий. Единственным исключением из этого является `match!`, которое само по себе является синтаксическим SugarCRM для использования `let!`, за которым следует соответствие шаблона в результате.

Тип построителя — это объект, который определяет специальные методы, определяющие способ объединения фрагментов вычислительного выражения. то есть его методы управляют тем, как работает вычислительное выражение. Другой способ описать класс построителя — сказать, что он позволяет настраивать работу многих F# конструкций, таких как циклы и привязки.

### `let!`

Ключевое слово `let!` привязывает результат вызова другого вычислительного выражения к имени:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

При привязке вызова к вычислительному выражению с `let`не будет получен результат вычисления выражения. Вместо этого вы привязываете значение *нереализованного* вызова к этому вычислительному выражению. Для привязки к результату используйте `let!`.

`let!` определяется членом `Bind(x, f)` в типе построителя.

### `do!`

Ключевое слово `do!` предназначено для вызова вычислительного выражения, возвращающего тип, схожий с `unit`(определяется элементом `Zero` в построителе):

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

Для [асинхронного рабочего процесса](asynchronous-workflows.md)этот тип `Async<unit>`. Для других вычислительных выражений тип, скорее всего, будет `CExpType<unit>`.

`do!` определяется членом `Bind(x, f)` в типе построителя, где `f` создает `unit`.

### `yield`

Ключевое слово `yield` используется для возвращения значения из вычислительного выражения, чтобы его можно было использовать как <xref:System.Collections.Generic.IEnumerable%601>:

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

Как и в случае с [ключевым C#словом yield в ](../../csharp/language-reference/keywords/yield.md), каждый элемент в вычислительном выражении получает обратную передачу по мере выполнения итерации.

`yield` определяется членом `Yield(x)` в типе построителя, где `x` — это элемент, который необходимо вернуть.

### `yield!`

Ключевое слово `yield!` предназначено для выравнивания коллекции значений из вычислительного выражения:

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

При вычислении вычислительное выражение, вызываемое `yield!`, будет возвращать возвращенные элементы по одному, сведеня результат.

`yield!` определяется членом `YieldFrom(x)` в типе построителя, где `x` является коллекцией значений.

### `return`

Ключевое слово `return` заключает в оболочку значение в типе, соответствующем вычислительному выражению. Помимо вычислительных выражений, использующих `yield`, оно используется для полного выражения вычислений:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return` определяется членом `Return(x)` в типе построителя, где `x` — это элемент для переноса.

### `return!`

Ключевое слово `return!` вычисляет значение вычислительного выражения и заключает результат в тип, соответствующий вычислительному выражению:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!` определяется членом `ReturnFrom(x)` в типе построителя, где `x` является другим вычислительным выражением.

### `match!`

Начиная с F# 4,5, ключевое слово`match!`позволяет встроено вызвать в другое вычислительное выражение и сопоставить шаблон с его результатом:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

При вызове вычислительного выражения с `match!`будет выдаваться результат такого вызова, как `let!`. Это часто используется при вызове вычислительного выражения, в котором результат является [необязательным](options.md).

## <a name="built-in-computation-expressions"></a>Встроенные вычислительные выражения

F# Базовая библиотека определяет три встроенных вычислительных выражения: [выражения последовательности](sequences.md), [асинхронные рабочие процессы](asynchronous-workflows.md)и [выражения запросов](query-expressions.md).

## <a name="creating-a-new-type-of-computation-expression"></a>Создание нового типа вычислительного выражения

Вы можете определить характеристики собственных вычислительных выражений, создав класс построителя и определив определенные специальные методы в классе. Класс построителя может дополнительно определять методы, перечисленные в следующей таблице.

В следующей таблице описаны методы, которые можно использовать в классе построителя рабочих процессов.

|**Метод**|**Типичные подписи**|**Описание**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Вызывается для `let!` и `do!` в вычислительных выражениях.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Заключает в оболочку вычислительное выражение как функцию.|
|`Return`|`'T -> M<'T>`|Вызывается для `return` в вычислительных выражениях.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Вызывается для `return!` в вычислительных выражениях.|
|`Run`|`M<'T> -> M<'T>` или<br /><br />`M<'T> -> 'T`|Выполняет вычислительное выражение.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` или<br /><br />`M<unit> * M<'T> -> M<'T>`|Вызывается для виртуализации в вычислительных выражениях.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` или<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Вызывается для `for...do` выражений в вычислительных выражениях.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Вызывается для `try...finally` выражений в вычислительных выражениях.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Вызывается для `try...with` выражений в вычислительных выражениях.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|Вызывается для `use` привязок в вычислительных выражениях.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Вызывается для `while...do` выражений в вычислительных выражениях.|
|`Yield`|`'T -> M<'T>`|Вызывается для `yield` выражений в вычислительных выражениях.|
|`YieldFrom`|`M<'T> -> M<'T>`|Вызывается для `yield!` выражений в вычислительных выражениях.|
|`Zero`|`unit -> M<'T>`|Вызывается для пустых `else` ветвей `if...then` выражений в вычислительных выражениях.|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|Указывает, что вычислительное выражение передается в элемент `Run` в качестве предложения. Он преобразует все экземпляры вычислений в кавычки.|

Многие методы в классе построителя используют и возвращают `M<'T>` конструкцию, которая обычно представляет собой отдельный определяемый тип, который характеризует тип объединяемых вычислений, например `Async<'T>` для асинхронных рабочих процессов и `Seq<'T>` для последовательности. nЭто. Сигнатуры этих методов позволяют объединять и вкладывать друг в друга, чтобы объект рабочего процесса, возвращенный из одной конструкции, можно было передать далее. Компилятор при синтаксическом анализе вычислительного выражения преобразует выражение в ряд вложенных вызовов функций, используя методы из предыдущей таблицы и код в вычислительном выражении.

Вложенное выражение имеет следующий вид:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

В приведенном выше коде вызовы `Run` и `Delay` опущены, если они не определены в классе построителя вычислительных выражений. Текст вычислительного выражения, обозначенный как `{| cexpr |}`, преобразуется в вызовы, в которых используются методы класса Builder, с помощью переводов, описанных в следующей таблице. Выражение вычисления `{| cexpr |}` определяется рекурсивно в соответствии с этими переводами, где `expr` является F# выражением, а`cexpr`является вычислительным выражением.

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
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else binder.Zero()</code>|
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

В предыдущей таблице `other-expr` описывает выражение, которое не указано в таблице в других случаях. Классу построителя не требуется реализовывать все методы и поддерживать все переводы, перечисленные в предыдущей таблице. Эти конструкции, которые не реализованы, недоступны в вычислительных выражениях этого типа. Например, если не требуется поддерживать ключевое слово `use` в вычислительных выражениях, можно опустить определение `Use` в классе построителя.

В следующем примере кода показано вычислительное выражение, которое инкапсулирует вычисление в виде последовательности шагов, которые можно оценить по одному шагу за раз. Тип размеченного объединения, `OkOrException`, кодирует состояние ошибки выражения, как было оценено до сих пор. Этот код демонстрирует несколько типовых шаблонов, которые можно использовать в вычислительных выражениях, таких как стандартные реализации некоторых методов построителя.

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

Вычислительное выражение имеет базовый тип, который возвращает выражение. Базовый тип может представлять вычисленный результат или отложенное вычисление, которое может быть выполнено, или может предоставить способ итерации некоторого типа коллекции. В предыдущем примере базовый тип был в **конечном итоге**. Для выражения последовательности базовым типом является <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Для выражения запроса базовый тип <xref:System.Linq.IQueryable?displayProperty=nameWithType>. Для асинхронного рабочего процесса базовый тип [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7). Объект `Async` представляет работу, которую необходимо выполнить для вычисления результата. Например, вызовите [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) , чтобы выполнить вычисление и вернуть результат.

## <a name="custom-operations"></a>Пользовательские операции

Можно определить пользовательскую операцию в вычислительном выражении и использовать настраиваемую операцию в качестве оператора в вычислительном выражении. Например, оператор запроса можно включить в выражение запроса. При определении пользовательской операции необходимо определить методы yield и for в вычислительном выражении. Чтобы определить пользовательскую операцию, добавьте ее в класс построителя для вычислительного выражения, а затем примените [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19). Этот атрибут принимает строку в качестве аргумента, который является именем, используемым в пользовательской операции. Это имя поступает в область в начале открывающей фигурной скобки вычислительного выражения. Поэтому не следует использовать идентификаторы, имена которых совпадают с именами пользовательских операций в этом блоке. Например, Избегайте использования идентификаторов, таких как `all` или `last` в выражениях запросов.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Расширение существующих построителей с помощью новых настраиваемых операций

Если у вас уже есть класс построителя, его пользовательские операции можно расширить за пределами этого класса построителя. Расширения должны быть объявлены в модулях. Пространства имен не могут содержать элементы Extension, кроме в том же файле и в той же группе объявлений пространства имен, где определен тип.

В следующем примере показано расширение существующего класса `Microsoft.FSharp.Linq.QueryBuilder`.

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Асинхронные рабочие потоки](asynchronous-workflows.md)
- [Последовательности](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [Выражения запросов](query-expressions.md)
