---
title: Выражения вычисления (F#)
description: 'Описание способов создания удобный синтаксис для записи вычислений в F #, который можно упорядочивать и комбинировать с помощью конструкций потока управления и привязок.'
ms.date: 05/16/2016
ms.openlocfilehash: a4ddb3fde284452bc901c5270551611e43742c1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="computation-expressions"></a>Выражения вычисления

Вычисление выражений в F # предоставляют удобный синтаксис для записи вычислений, которые можно упорядочивать и комбинировать с помощью конструкций потока управления и привязок. Их можно использовать для обеспечения удобного синтаксиса для *компоненты Monad*, функционального программирования, который может использоваться для управления данными, управления и побочными эффектами в функциональных программах.


## <a name="built-in-workflows"></a>Встроенные рабочие процессы
Выражения последовательностей являются Примером вычислительного выражения асинхронные рабочие потоки и выражения запроса. Дополнительные сведения см. в разделе [последовательности](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [выражения запросов](query-expressions.md).

Некоторые функции являются общими для выражения последовательностей и асинхронные рабочие процессы и иллюстрируют базовый синтаксис для вычислительного выражения:

```fsharp
builder-name { expression }
```

Представленный выше синтаксис определяет, что данное выражение является вычислительным типа, заданного *имени построителя*. Вычислительное выражение может быть встроенным рабочим процессом, например `seq` или `async`, или это может быть что-то определении. *Имени построителя* — это идентификатор экземпляра специального типа, известный как *тип построителя*. Тип построителя является типом класса, который определяет особые методы, которые задают способ фрагментов вычислительного выражения объединяются, то есть код, которое управляет выполнением выражения. Другой способ класс построителя — сказать, что он позволяет настраивать работу многих конструкций языка F #, такие как циклы и привязки.

В вычислительных выражениях для некоторых общих конструкций языка доступны две формы. Варианты конструкций можно вызвать с помощью! (восклицательный знак) суффикс определенные ключевые слова, такие как `let!`, `do!`, и т. д. Такие специальные формы заставляют некоторые функции, определенные в классе построителя для замены обычное встроенное поведение этих операций. Эти формы подобны `yield!` форму `yield` ключевое слово, которое используется в выражениях последовательности. Дополнительные сведения см. в разделе [последовательности](sequences.md).


## <a name="creating-a-new-type-of-computation-expression"></a>Создание нового типа вычислительного выражения
Можно определить характеристики собственных вычислительных выражений, создав класс построителя и определив специальные методы в классе. Класс построителя при необходимости можно определить методы, перечисленные в следующей таблице.

В следующей таблице описаны методы, которые могут использоваться в классе построителя рабочего процесса.


|**Метод**|**Типичные сигнатуры**|**Описание**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Вызывается для `let!` и `do!` в вычислительных выражениях.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Создает оболочку вычислительного выражения в виде функции.|
|`Return`|`'T -> M<'T>`|Вызывается для `return` в вычислительных выражениях.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Вызывается для `return!` в вычислительных выражениях.|
|`Run`|`M<'T> -> M<'T>` или<br /><br />`M<'T> -> 'T`|Выполняет вычислительное выражение.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` или<br /><br />`M<unit> * M<'T> -> M<'T>`|Вызывается для последовательности в вычислительных выражениях.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` или<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Вызывается для `for...do` в вычислительных выражениях.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Вызывается для `try...finally` в вычислительных выражениях.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Вызывается для `try...with` в вычислительных выражениях.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|Вызывается для `use` привязки в вычислительных выражениях.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Вызывается для `while...do` в вычислительных выражениях.|
|`Yield`|`'T -> M<'T>`|Вызывается для `yield` в вычислительных выражениях.|
|`YieldFrom`|`M<'T> -> M<'T>`|Вызывается для `yield!` в вычислительных выражениях.|
|`Zero`|`unit -> M<'T>`|Вызывается для пустых `else` ответвления `if...then` в вычислительных выражениях.|
Многие методы в классе построителя используют и возвращают `M<'T>` конструкцию, которая обычно является отдельно определенный тип, характеризующий вид объединяемых вычислений, например, `Async<'T>` асинхронные рабочие процессы и `Seq<'T>` для рабочих процессов последовательности. Сигнатуры этих методов включить их следует объединить и вложенные друг с другом, чтобы объект рабочего процесса, возвращаемый из одной конструкции могут передаваться в следующий. Когда компилятор анализирует вычислительное выражение преобразует его в ряд вложенные вызовы функций с помощью методов в предыдущей таблице и кода в вычислительное выражение.

Вложенное выражение имеет следующую форму:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

В приведенном выше коде вызовы `Run` и `Delay` пропускаются, если они не определены в классе построителя вычислительных выражений. Тело вычислительного выражения, обозначенное здесь как `{| cexpr |}`, преобразуются в вызовы с участием методов класса построителя посредством преобразований, приведенных в следующей таблице. Вычислительное выражение `{| cexpr |}` определяется рекурсивно в соответствии с этими преобразованиями где `expr` выражение F # и `cexpr` выражение вычисления.



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
В таблице выше `other-expr` соответствует выражению, в противном случае не указан в таблице. Класс построителя не реализует все методы и поддерживает все переводы, перечисленные в предыдущей таблице. Эти конструкции, которые не реализованы недоступны в вычислительных выражениях данного типа. Например, если не требуется поддерживать `use` ключевое слово в вычислительных выражениях можно опустить определение `Use` в классе построителя.

В следующем примере кода показано выражение вычисления, инкапсулирующий вычисление вычисленному один шаг ряд шагов, которые могут быть одновременно. Объект размеченные объединения типа `OkOrException`, кодирует состояние ошибки выражения, вычисленному на данный момент. Этот код демонстрирует несколько типичных шаблонов, которые можно использовать в выражениях вычислений, таких как стандартный реализации для некоторых методов построителя.

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

Вычислительное выражение имеет базовый тип, который возвращает выражение. Базовый тип может представлять вычисленных результирующих или отложенное вычисление, которое может быть выполнена, или обеспечивают способ итерации по коллекции своего рода. В предыдущем примере был базовый тип **со временем**. В случае выражения последовательности базовым типом является <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Для выражения запроса, базовым типом является <xref:System.Linq.IQueryable?displayProperty=nameWithType>. Для асинхронного рабочего процесса, базовым типом является [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7). `Async` Трудозатрат для вычисления результат представляет объект. Например, можно вызвать [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) для выполнения вычислений и возвращают результат.

## <a name="custom-operations"></a>Пользовательские операции
Можно определить пользовательскую операцию на вычислительное выражение и использовать пользовательскую операцию как оператор в выражении вычисления. Например можно включить оператора запроса в выражении запроса. При определении пользовательскую операцию, необходимо определить доход и для методов в вычислительное выражение. Чтобы определить пользовательскую операцию, поместите его в классе построитель вычислительного выражения и примените [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19). Этот атрибут принимает строку в качестве аргумента, то есть имя для использования в пользовательской операции. Это имя поступает в область видимости в начале открывающая фигурная скобка вычислительного выражения. Таким образом не следует использовать идентификаторы, которые имеют имя, совпадающее с именем пользовательской операции в этом блоке. Например, такие как Избегайте использования идентификаторов `all` или `last` в выражениях запросов.

## <a name="see-also"></a>См. также
[Справочник по языку F#](index.md)

[Асинхронные рабочие потоки](asynchronous-workflows.md)

[Последовательности](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[Выражения запросов](query-expressions.md)
