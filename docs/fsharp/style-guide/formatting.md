---
title: 'Рекомендациями по форматированию кода F #'
description: 'Дополнительные сведения, касающиеся форматирования кода на F #.'
ms.date: 05/14/2018
ms.openlocfilehash: 0d7d2d1771710db55bf990f3a06079b2aec48fd7
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "43858009"
---
# <a name="f-code-formatting-guidelines"></a>Рекомендациями по форматированию кода F #

В данной статье рассматриваются рекомендации по форматированию кода таким образом, код F #:

* Обычно рассматривать как более читаемым
* — В соответствии с соглашениями об примененное форматирование средства в Visual Studio и другие редакторы
* Аналогично другим кодом по сети

Эти рекомендации основаны на [полное руководство по правилам форматирования F #](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) по [Anh-Данг Фан](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Общие правила для отступа

F # по умолчанию используется значащим пробелом. Следующие рекомендации предназначены для предоставления рекомендации о том, как корпоративные некоторые проблемы, это может создать.

### <a name="using-spaces"></a>С помощью пробелов

Если требуется отступ, необходимо использовать не знаки табуляции. Необходим по крайней мере один пробел. Организации могут создавать стандарты кодирования, чтобы указать число пробелов, используемых для отступов; двух, трех или четырех пробелов отступа на каждом уровне, где происходит отступа является типичным.

**Мы рекомендуем 4 пробелов для отступа.**

С другой стороны, отступы программ сводится к субъективным. Варианты ОК, но первое правило, необходимо следовать *согласованности отступа*. Выберите широко распространенный стиль отступов и используйте его систематически во всей базе кода.

## <a name="formatting-blank-lines"></a>Форматирование пустых строк

* Отдельные верхнего уровня функций и классов определения двух пустыми строками.
* Определения методов внутри класса разделяются одна пустая строка.
* Лишних пустых строк может использоваться для разделения групп связанных функций (только в случае необходимости). Можно опустить пустые строки между ряд связанных командных строк (например, набор заглушки).
* Используйте пустые строки в функции, только в случае необходимости, чтобы указать логические разделы.

## <a name="formatting-comments"></a>Форматирование комментарии

Обычно предпочтение комментарии блок в стиле ML несколько комментариев двойной косой чертой.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

Встроенные комментарии должны преобразование первой буквы.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Соглашения об именах

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Использующие camelCase для класса, привязанного к выражению с связыванием и шаблон значения и функции

Довольно часто и стиль принятые F # для использования camelCase все имена привязку как локальные переменные или соответствия шаблону и определения функций.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Локально функций в классах, также следует использовать camelCase.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Использующие camelCase для связанного с модулем открытых функций

Когда связанного с модулем функции является частью открытого API, его следует использовать camelCase.

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Использующие camelCase для внутреннего использования и частных значения связанного с модулем и функции

Использования camelCase закрытый значений связанного с модулем, включая следующие:

* Нерегламентированные функции в скриптах

* Значения, входящим в состав внутренняя реализация модуля или тип

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>Использующие camelCase для параметров

Все параметры следует использовать camelCase в соответствии с соглашениями об именовании .NET.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>Используйте PascalCase для модулей

Все модули (верхнего уровня, внутренний, закрытый, вложенные) следует использовать PascalCase.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Использующие PascalCase для объявления типов, членов и меток

Классы, интерфейсы, структуры, перечисления, делегаты, записи и размеченные объединения должны иметь имя с PascalCase. Элементы типов и метки для записи и размеченные объединения также следует использовать PascalCase.

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Использующие PascalCase для конструкций, встроенными в .NET

Пространства имен, исключения, события и проект /`.dll` имена также следует использовать PascalCase. Не только делает ли это потребление из других языков .NET, в целом более привычны для потребителей, он также был совместим с .NET соглашения об именовании, которые могут возникнуть.

### <a name="avoid-underscores-in-names"></a>Избежать символов подчеркивания в именах

Исторически сложилось так, что некоторые библиотеки F # использовали символы подчеркивания в именах. Тем не менее принимается больше не широко, отчасти потому, что он противоречит соглашения об именовании .NET. С другой стороны, некоторые программисты на F # используйте символы подчеркивания во многом, отчасти по историческим причинам и важно допуска и уважение. Однако имейте в виду, что стиль часто нравилось с другими пользователями, существует выбор, следует ли использовать его.

Некоторые исключения включает в себя взаимодействие с компонентами в машинном коде, где очень распространены символы подчеркивания.

### <a name="use-standard-f-operators"></a>Использовать стандартные операторы F #

Следующие операторы определены в стандартной библиотеке F # и должен использоваться вместо определения эквиваленты. Использование этих операторов рекомендуется, так как он, как правило, чтобы сделать код более читаемым и устойчивым. Разработчиков, имеющих опыт в OCaml или других функциональный язык программирования, могли привыкнуть к различных выражений. В следующем списке перечислены рекомендуемые операторов F #.

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Используйте синтаксис префикс для универсальных типов (`Foo<T>`) предпочтение постфиксный синтаксис (`T Foo`)

F # наследует стиль постфиксного ML именования универсальных типов (например, `int list`) а также префикс стиля .NET (например, `list<int>`). Предпочитаете в стиле .NET, за исключением четырех определенных типов:

1. Для списки F #, используйте в постфиксной форме: `int list` вместо `list<int>`.
2. Для параметры F #, используйте в постфиксной форме: `int option` вместо `option<int>`.
3. Для F # массивы, используйте имя синтаксические `int[]` вместо `int array` или `array<int>`.
4. Ссылочные ячейки, используйте `int ref` вместо `ref<int>` или `Ref<int>`.

Для всех других типов используйте форму префикс.

## <a name="formatting-tuples"></a>Форматирование кортежей

Создание экземпляра кортежа должно быть заключено в скобки и разделителей запятые внутри должен следовать один пробел, например: `(1, 2)`, `(x, y, z)`.

Обычно принимается опустить скобки при сопоставлении шаблонов кортежей:

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-discriminated-union-declarations"></a>Форматирование размеченные объявления объединений

Отступ `|` в определении типа по 4 пробела:

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

## <a name="formatting-discriminated-unions"></a>Форматирование размеченные объединения

Созданный экземпляр размеченные объединения, которые разбиваются на несколько строк следует предоставить новую область с отступами содержащиеся данные:

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

Также может быть закрывающую скобку на новой строке:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>Форматирование запись объявления

Отступ `{` в типе определения по 4, пробелы и начать полей списка полей в той же строке:

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

Поместив токен открывающий в той же строке, а также маркер закрытия в новой строке также допустимо, но имейте в виду, что вам нужно использовать [подробный синтаксис](../language-reference/verbose-syntax.md) для определения элементов ( `with` ключевое слово):

```fsharp
//  OK, but verbose syntax required
type PostalAddress = { 
    Address: string
    City: string
    Zip: string
} with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
```

## <a name="formatting-records"></a>Форматирование записей

Короткие записи могут быть написаны на одной строке:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

Длинные записи следует использовать новые строки для меток:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Поместив токен открывающий в той же строке, а также маркер закрытия в новой строке также очень мило:

```fsharp
let rainbow = {
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
```

Те же правила применяются для элементов списка и массива.

## <a name="formatting-lists-and-arrays"></a>Форматирование, списки и массивы

Запись `x :: l` с пробелы вокруг `::` оператор (`::` инфиксные оператор, поэтому окружен пробелами) и `[1; 2; 3]` (`;` — разделитель, следовательно, разделенных пробелами).

Всегда используйте по крайней мере один пробел между двумя операторами distinct стиле фигурную скобку. Например, оставьте пробел между `[` и `{`.

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

Списки и массивы, которые разбиты на несколько строк выполните аналогичные правила, как записи.

```fsharp
let pascalsTriangle = [|
    [|1|]
    [|1; 1|]
    [|1; 2; 1|]
    [|1; 3; 3; 1|]
    [|1; 4; 6; 4; 1|]
    [|1; 5; 10; 10; 5; 1|]
    [|1; 6; 15; 20; 15; 6; 1|]
    [|1; 7; 21; 35; 35; 21; 7; 1|]
    [|1; 8; 28; 56; 70; 56; 28; 8; 1|]
|]
```

## <a name="formatting-if-expressions"></a>Если форматирования выражения

Отступ элемента условные выражения зависит от размеров выражений, составляющих их. Если `cond`, `e1` и `e2` короткие, просто записывать их в одной строке:

```fsharp
if cond then e1 else e2
```

Если параметр `cond`, `e1` или `e2` больше времени, но не несколько строк:

```fsharp
if cond
then e1
else e2
```

Если любое из выражений несколько строк:

```fsharp
if cond then
    e1
else
    e2
```

Несколько условий с `elif` и `else` отображаются с отступом в той же области, что `if`:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Шаблон сопоставления конструкции

Используйте `|` для каждого предложения совпадения с без отступов. Если выражение является коротким, можно с помощью одной строки, если каждой части выражения стоит также выполняется очень просто.

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> _
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> _
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

Если выражение справа сопоставления стрелку шаблона слишком велико, перемещается в следующую строку, с отступом один шаг из `match` / `|`.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Сопоставления анонимных функций, начиная с шаблонов `function`, обычно не создать отступы слишком далеко. Например следующим образом отступов одну область очень мило:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Шаблоны в функциях, определяемых `let` или `let rec` должно быть с отступом 4 пробелов после начала `let`, даже если `function` используется ключевое слово:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Мы не рекомендуем выравнивание кнопки со стрелками.

## <a name="formatting-trywith-expressions"></a>Форматирования try / with выражения

Сопоставление шаблонов в тип исключения должен иметь отступ на том же уровне, что `with`.

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

## <a name="formatting-function-parameter-application"></a>Форматирование функции параметр приложения

Как правило большинство функции параметр приложения выполняется в той же строке.

Если вы хотите применить параметры функции с новой строки, отступ их на одну область.

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

Те же правила применяются для лямбда-выражения как аргументы функции. Если тело лямбда-выражения, текст может иметь другую строку, отступом в одну область

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

Тем не менее если тело лямбда-выражения является более одной строки, рассмотрите возможность факторинг его в отдельную функцию вместо конструкцию многострочного применяется как один аргумент функции.

### <a name="formatting-infix-operators"></a>Форматирование инфиксные операторы

Отдельные операторы пробелами. Очевидным исключения этого правила являются `!` и `.` операторы.

Инфиксные выражения — ОК в линейку и того же столбца:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Форматирование конвейерных операторов

Конвейер `|>` операторы должны начать выполняться под выражения, они работают.

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

Код в локальном модуле должен иметь отступ относительно модуля, но код в модуль верхнего уровня не должен иметь отступ. Элементы пространства имен нет необходимости иметь отступ.

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

### <a name="formatting-object-expressions-and-interfaces"></a>Форматирование выражения объекта и интерфейсов

Выражения объекта и интерфейсы должны быть выровнены с таким же образом `member` с отступом после 4 пробела.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>Форматирование пустое пространство в выражениях

Избегайте лишние пробелы в выражения F #.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Именованные аргументы также не должны иметь пространство вокруг `=`:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```
