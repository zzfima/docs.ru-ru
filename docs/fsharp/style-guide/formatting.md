---
title: Рекомендации по форматированию кода F#
description: Ознакомьтесь с рекомендациями F# по форматированию кода.
ms.date: 11/04/2019
ms.openlocfilehash: 895c8211731b47bd4c59d762d5806cfc1bfe232d
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089320"
---
# <a name="f-code-formatting-guidelines"></a>Рекомендации по форматированию кода F#

В этой статье приводятся рекомендации по форматированию кода, чтобы F# код:

* Обычно просматривается как более разборчиво
* В соответствии с соглашениями, применяемыми средствами форматирования в Visual Studio и других редакторах
* Аналогично другому коду в Интернете

Эти рекомендации основаны на [исчерпывающем руководстве по F# форматированию соглашений](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) с помощью [АНХ-dung Phan](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Общие правила для отступов

F#по умолчанию использует значащие пробелы. Следующие рекомендации предназначены для указания того, как решать некоторые проблемы, которые могут накладываться.

### <a name="using-spaces"></a>Использование пробелов

Если требуется отступ, необходимо использовать пробелы, а не символы табуляции. Требуется по крайней мере один пробел. Ваша организация может создавать стандарты кодирования для указания количества пробелов, используемых для отступов; два, три или четыре пробела на каждом уровне, где происходит отступ, являются типичными.

**Для отступов рекомендуется использовать по 4 пространства.**

С другой стороны, отступы программ являются субъективным вопросом. Варианты — ОК, но первым правилом, которое следует следовать, является *согласованность отступов*. Выберите общепринятый стиль отступов и используйте его систематически во всей базе кода.

## <a name="formatting-white-space"></a>Форматирование пробелов

F#учитывает пробельные символы. Хотя большая семантика из пустого пространства охватывается правильным отступом, необходимо учитывать некоторые другие моменты.

### <a name="formatting-operators-in-arithmetic-expressions"></a>Операторы форматирования в арифметических выражениях

Всегда используйте пробелы вокруг двоичных арифметических выражений:

```fsharp
let subtractThenAdd x = x - 1 + 3
```

Унарные операторы `-` всегда должны иметь значение, которое они отменяют сразу после:

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

Добавление символа пробела после оператора `-` может привести к путанице в других случаях.

В целом, важно всегда:

* Заключить бинарные операторы в пробелы
* Никогда не иметь конечных пробелов после унарного оператора

Особенно важна рекомендация бинарных арифметических операторов. Если не заключить бинарный `-` оператор, в сочетании с определенными вариантами форматирования, может привести к интерпретации его как унарного `-`.

### <a name="surround-a-custom-operator-definition-with-white-space"></a>Заключить определение пользовательского оператора с помощью пробела

Всегда используйте пробелы, чтобы заключить определение оператора:

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

Для любого пользовательского оператора, начинающегося с `*` и имеющего более одного символа, необходимо добавить пробел в начало определения, чтобы избежать неоднозначности компилятора. Поэтому рекомендуется просто заключить определения всех операторов в один символ пробела.

### <a name="surround-function-parameter-arrows-with-white-space"></a>Стрелки параметров вокруг функции с пробелами

При определении сигнатуры функции используйте пробел вокруг `->` символа:

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a>Аргументы функции вокруг пробелов

При определении функции следует использовать пробел вокруг каждого аргумента.

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-very-long-member-definitions"></a>Размещайте параметры в новой строке для слишком длинных определений элементов

При наличии слишком длинного определения члена разместите параметры на новых строках и поставьте отступ для одной области.

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

Это также относится к конструкторам:

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a>Аннотации типов

#### <a name="right-pad-function-argument-type-annotations"></a>Заметки о типе аргумента функции в правой панели

При определении аргументов с аннотациями типа используйте пробел после `:` символа:

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a>Заметка возвращаемого типа вокруг пробелов

В заметке функции, привязанной к let, или типе значения (возвращаемый тип в случае функции) используйте пробелы до и после символа `:`:

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a>Форматирование пустых строк

* Отдельные определения функций и классов верхнего уровня с двумя пустыми строками.
* Определения методов внутри класса разделяются одной пустой строкой.
* Для разделения групп связанных функций можно использовать дополнительные пустые строки (с осторожностью). Пустые строки могут быть опущены между несколькими строками с одной строкой (например, набором фиктивных реализаций).
* Для обозначения логических разделов используйте в функциях пустые строки.

## <a name="formatting-comments"></a>Форматирование комментариев

Обычно в качестве комментариев блока в стиле ML предпочтительно несколько комментариев с двойной косой чертой.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

Встроенные комментарии должны заменять первую букву прописной.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Соглашения об именах

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Использовать camelCase для привязанных к классам значений и функций, связанных с шаблонами, и функциями

Распространенный и принятый F# стиль для использования camelCase для всех имен, привязанных как локальные переменные или в соответствии с шаблонами и определениями функций.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Функции с локальной привязкой в классах также должны использовать camelCase.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Использование camelCase для открытых функций, привязанных к модулю

Если функция, привязанная к модулю, является частью общедоступного API, она должна использовать camelCase:

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Использовать camelCase для внутренних и частных привязанных к модулю значений и функций

Используйте camelCase для частных значений, привязанных к модулю, включая следующие:

* Специальные функции в скриптах

* Значения, составляющие внутреннюю реализацию модуля или типа

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>Использование camelCase для параметров

Все параметры должны использовать camelCase в соответствии с соглашениями об именовании .NET.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>Использование PascalCase для модулей

Все модули (верхний, внутренний, частный, вложенный) должны использовать PascalCase.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Использование PascalCase для объявлений типов, элементов и меток

Классы, интерфейсы, структуры, перечисления, делегаты, записи и размеченные объединения должны иметь имена с PascalCase. Элементы в типах и метках для записей и размеченных объединений должны также использовать PascalCase.

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Использование PascalCase для конструкций, встроенных в .NET

Пространства имен, исключения, события и имена проектов и`.dll` также должны использовать PascalCase. Это не только делает использование других языков .NET более естественным для потребителей, но также согласуется с соглашениями об именовании .NET, которые, скорее всего, встречаются.

### <a name="avoid-underscores-in-names"></a>Не используйте знаки подчеркивания в именах

Исторически в некоторых F# библиотеках в именах используются символы подчеркивания. Однако он больше не принимается частично, поскольку он противоречит соглашениям об именовании .NET. С другой стороны, F# некоторые программисты часто используют подчеркивания, частично по историческим причинам, а чувствительность и уважение важны. Однако имейте в виду, что стиль часто отличается от других, которые имеют возможность выбрать, следует ли использовать его.

Некоторые исключения включают взаимодействие с собственными компонентами, в которых знаки подчеркивания очень распространены.

### <a name="use-standard-f-operators"></a>Использовать стандартные F# операторы

Следующие операторы определены в F# стандартной библиотеке и должны использоваться вместо определения эквивалентов. Рекомендуется использовать эти операторы, так как он, как правило, делает код более читаемым и идиоматическим. Разработчики с фоном в OCaml или другом языке функционального программирования могут прилагаться к различным идиомам. В следующем списке перечислены рекомендуемые F# операторы.

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Использовать префиксный синтаксис для универсальных типов (`Foo<T>`) в качестве предпочтительного для постфиксного синтаксиса (`T Foo`)

F#наследует постфиксный стиль именования универсальных типов (например, `int list`), а также стиль префикса .NET (например, `list<int>`). Предпочитать стиль .NET, за исключением пяти конкретных типов:

1. Для F# списков используйте постфиксную форму: `int list`, а не `list<int>`.
2. Для F# параметров используйте постфиксную форму: `int option`, а не `option<int>`.
3. Для F# параметров значения используйте постфиксную форму: `int voption`, а не `voption<int>`.
4. Для F# массивов используйте синтаксические имена `int[]` а не `int array` или `array<int>`.
5. Для ссылочных ячеек используйте `int ref`, а не `ref<int>` или `Ref<int>`.

Для всех остальных типов используйте форму префикса.

## <a name="formatting-tuples"></a>Форматирование кортежей

Создание экземпляра кортежа должно быть заключено в круглые скобки, а за разделителями в пределах должно быть один пробел, например: `(1, 2)`, `(x, y, z)`.

Обычно можно опустить круглые скобки в шаблоне, сопоставленном с кортежами:

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

Также обычно можно опустить круглые скобки, если кортеж является возвращаемым значением функции:

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

В заключение следует предпочесть создание экземпляров кортежей в круглых скобках, но при использовании кортежей для сопоставления шаблонов или возвращаемого значения оно считается точным, чтобы избежать круглых скобок.

## <a name="formatting-discriminated-union-declarations"></a>Форматирование объявлений размеченного объединения

Отступ `|` в определении типа по 4 пробелам:

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a>Форматирование размеченных объединений

Экземпляры с различенными объединениями, разделенными по нескольким строкам, должны предоставлять новой области с отступами следующие данные.

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

Закрывающая круглая скобка также может находиться на новой строке:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>Форматирование объявлений записей

Понизить `{` в определении типа на 4 пробела и начать список полей в той же строке:

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

Помещение открывающего маркера в новую строку и закрывающий маркер в новой строке предпочтительнее, если объявить реализации интерфейса или элементы в записи:

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    } with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a>Форматирование записей

Короткие записи можно записать в одной строке:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

Записи, которые больше не должны использовать новые строки для меток:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Размещение открывающего маркера на новой строке, содержимое, вкладка над одной областью, и закрывающий маркер в новой строке предпочтительнее, если вы:

* Перемещение записей в коде с разными областями отступов
* Передача их в функцию

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

Для списка и элементов массива применяются те же правила.

## <a name="formatting-copy-and-update-record-expressions"></a>Форматирование выражений записи копирования и обновления

Выражение записи копирования и обновления по-прежнему является записью, поэтому применяются аналогичные рекомендации.

Короткие выражения могут помещаться в одну строку:

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

В более длинных выражениях должны использоваться новые строки:

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Как и в руководстве по записям, может потребоваться выделить отдельные строки для фигурных скобок и задать отступ для одной области справа с помощью выражения. Обратите внимание, что в некоторых особых случаях, например при переносе значения с необязательными скобками, может потребоваться разместить фигурную скобку в одной строке:

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a>Форматирование списков и массивов

Напишите `x :: l` с пробелами вокруг оператора `::` (`::` является оператором инфиксные, поэтому он заключен в пробелы).

Список и массивы, объявленные в одной строке, должны содержать пробел после открывающей скобки и перед закрывающей скобкой:

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

Всегда используйте хотя бы один пробел между двумя различными операторами, похожими на фигурные скобки. Например, оставьте пробел между `[` и `{`.

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

Одно и то же правило применимо к спискам или массивам кортежей.

Списки и массивы, разделенные по нескольким строкам, следуют тому же правилу, что и записи:

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

И, как и в случае с записями, объявление открывающих и закрывающих квадратных скобок в собственной строке сделает код более простым и походит к функциям.

При создании массивов и списков программным способом предпочтительнее `->` для `do ... yield` при создании значения всегда:

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

Более старые версии F# языка требовали указания `yield` в ситуациях, когда данные могут создаваться условно, или для вычисления последовательных выражений. Рекомендуется опустить эти ключевые слова `yield`, если не требуется компиляция с использованием F# более старой версии языка:

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

В некоторых случаях `do...yield` может помочь в удобочитаемости. В этих случаях следует учитывать субъективные ситуации.

## <a name="formatting-if-expressions"></a>Форматирование выражений if

Отступы условий зависят от размеров выражений, составляющих их. Если `cond`, `e1` и `e2` короткие, просто запишите их на одной строке:

```fsharp
if cond then e1 else e2
```

Если один из `cond`, `e1` или `e2` больше, но не является многострочным:

```fsharp
if cond
then e1
else e2
```

Если любое из выражений имеет несколько строк:

```fsharp
if cond then
    e1
else
    e2
```

Несколько условий с `elif` и `else` отображаются с отступом в той же области, что и `if`:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Конструкции сопоставления шаблонов

Используйте `|` для каждого предложения соответствия без отступов. Если выражение является коротким, можно использовать одну строку, если каждая часть выражения также является простой.

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

Если выражение справа от стрелки сопоставления шаблонов слишком велико, переместите его в следующую строку с отступом на один шаг из `match`/`|`.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Шаблон сопоставления анонимных функций, начиная с `function`, не должен слишком далеко иметь отступы. Например, чтобы задать отступ для одной области, сделайте следующее:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Сопоставление шаблонов в функциях, определенных `let` или `let rec`, должно иметь отступ в 4 пробелах после начала `let`, даже если используется ключевое слово `function`:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Не рекомендуется выровняйте стрелки.

## <a name="formatting-trywith-expressions"></a>Форматирование выражений try и with

Сопоставление шаблонов для типа исключения должно иметь отступ на том же уровне, что и `with`.

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a>Приложение параметров функции форматирования

Как правило, большинство параметров функции выполняются в одной строке.

Если вы хотите применить параметры к функции в новой строке, понизить их до одной области.

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

Те же рекомендации применяются для лямбда-выражений в качестве аргументов функции. Если тело лямбда-выражения, текст может иметь другую строку, с отступом на одну область

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

Однако если тело лямбда-выражения является более одной строкой, рекомендуется разбить его на отдельную функцию, а не использовать многострочную конструкцию, применяемую в качестве одного аргумента для функции.

### <a name="formatting-infix-operators"></a>Форматирование операторов инфиксные

Разделяйте операторы по пробелам. Очевидными исключениями из этого правила являются операторы `!` и `.`.

Выражения инфиксные являются допустимыми для сопоставления по одному и тому же столбцу:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Форматирование операторов конвейера

Операторы конвейера `|>` должны идти в соответствии с выражениями, над которыми они работают.

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a>Модули форматирования

Код в локальном модуле должен иметь отступ относительно модуля, но код в модуле верхнего уровня не должен иметь отступы. Элементы пространства имен не обязательно должны иметь отступы.

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a>Форматирование выражений и интерфейсов объекта

Выражения объектов и интерфейсы должны быть выровнены так же, как `member` с отступом после 4 пробелов.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>Форматирование пробелов в выражениях

Избегайте появления лишних F# пробелов в выражениях.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

У именованных аргументов также не должно быть пробелов, окружающих `=`:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a>Атрибуты форматирования

[Атрибуты](../language-reference/attributes.md) помещаются над конструкцией:

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a>Атрибуты форматирования для параметров

Атрибуты также могут быть размещаются в параметрах. В этом случае поместите его в ту же строку, что и параметр, и перед именем:

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>Форматирование нескольких атрибутов

Если к конструкции, которая не является параметром, применяется несколько атрибутов, их следует размещать таким образом, чтобы в каждой строке был один атрибут:

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

При применении к параметру они должны находиться в той же строке и разделяться разделителем `;`.

## <a name="formatting-literals"></a>Литералы форматирования

литералы, использующие атрибут `Literal`, должны располагать атрибут в отдельной строке и использовать именование PascalCase: [ F# ](../language-reference/literals.md)

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

Старайтесь не размещать атрибут в той же строке, что и значение.
