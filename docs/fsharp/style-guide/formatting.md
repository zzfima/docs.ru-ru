---
title: F#рекомендации по форматированию кода
description: Дополнительные сведения, касающиеся форматирования F# кода.
ms.date: 11/26/2018
ms.openlocfilehash: e8e0af2ebffd0e2f3720896bf710961afa11e7bd
ms.sourcegitcommit: 49af435bfdd41faf26d38c20c5b0cc07e87bea60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53396829"
---
# <a name="f-code-formatting-guidelines"></a>F#рекомендации по форматированию кода

В этой статье приведены инструкции по форматированию кода, чтобы ваши F# код:

* Обычно рассматривать как более читаемым
* — В соответствии с соглашениями об примененное форматирование средства в Visual Studio и другие редакторы
* Аналогично другим кодом по сети

Эти рекомендации основаны на [полное руководство по F# соглашения о форматировании](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) по [Anh-Данг Фан](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Общие правила для отступа

F#по умолчанию используется значащим пробелом. Следующие рекомендации предназначены для предоставления рекомендации о том, как корпоративные некоторые проблемы, это может создать.

### <a name="using-spaces"></a>С помощью пробелов

Если требуется отступ, необходимо использовать не знаки табуляции. Необходим по крайней мере один пробел. Организации могут создавать стандарты кодирования, чтобы указать число пробелов, используемых для отступов; двух, трех или четырех пробелов отступа на каждом уровне, где происходит отступа является типичным.

**Мы рекомендуем 4 пробелов для отступа.**

С другой стороны, отступы программ сводится к субъективным. Варианты ОК, но первое правило, необходимо следовать *согласованности отступа*. Выберите широко распространенный стиль отступов и используйте его систематически во всей базе кода.

## <a name="formatting-white-space"></a>Форматирование пустое пространство

F#чувствителен ли пустое пространство. Несмотря на то, что большинство семантику из пробелов, охватываются правильного отступа, существуют некоторые вещи, которые следует учитывать.

### <a name="formatting-operators-in-arithmetic-expressions"></a>Форматирование операторов в арифметических выражениях

Всегда используйте пробелы вокруг двоичные арифметические выражения:

```fsharp
let subtractThenAdd x = x - 1 + 3
```

Унарный `-` операторы всегда должны иметь значения, они Инверсия следовать сразу за:

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

Добавление пробела после `-` оператор может привести к путанице для других пользователей.

Таким образом важно всегда:

* Вокруг бинарных операторов с пробела
* Никогда не имеют конечный пробел после унарного оператора

Ориентировочная бинарный оператор арифметического особенно важна. Сбой вокруг двоичный файл `-` оператора, где сочетаются разные варианты форматирования может привести к его интерпретировать как унарный `-`.

### <a name="surround-a-custom-operator-definition-with-white-space"></a>Определение пользовательского оператора с пустого пространства вокруг

Всегда используете пробелы вокруг определение оператора:

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

Для любого пользовательского оператора, который начинается с `*`, вам потребуется добавить пробел в начале определения, чтобы избежать неоднозначности компилятора. По этой причине рекомендуется просто заключите определения всех операторов в виде одного символа пробела.

### <a name="surround-function-parameter-arrows-with-white-space"></a>Заключите стрелки параметра функции с пробела

При определении Сигнатура функции, используйте пустое пространство вокруг `->` символа:

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

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

Распространенный и принятых F# стиль, используемый camelCase, для всех имен привязан как локальные переменные или в соответствие шаблону и функцию, определения.

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

Исторически сложилось так, что некоторые F# библиотеки использовали символы подчеркивания в именах. Тем не менее принимается больше не широко, отчасти потому, что он противоречит соглашения об именовании .NET. С другой стороны, некоторые F# программисты используют символы подчеркивания во многом, отчасти по историческим причинам, и важно допуска и уважение. Однако имейте в виду, что стиль часто нравилось с другими пользователями, существует выбор, следует ли использовать его.

Некоторые исключения включает в себя взаимодействие с компонентами в машинном коде, где очень распространены символы подчеркивания.

### <a name="use-standard-f-operators"></a>Используйте стандартные F# операторы

Следующие операторы определены в F# стандартной библиотеки и должны использоваться вместо определения эквиваленты. Использование этих операторов рекомендуется, так как он, как правило, чтобы сделать код более читаемым и устойчивым. Разработчиков, имеющих опыт в OCaml или других функциональный язык программирования, могли привыкнуть к различных выражений. В следующем списке перечислены рекомендуемые F# операторы.

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

F#наследует стиль постфиксного ML именования универсальных типов (например, `int list`) а также префикс стиля .NET (например, `list<int>`). Предпочитаете в стиле .NET, за исключением четырех определенных типов:

1. Для F# списки, используйте в постфиксной форме: `int list` вместо `list<int>`.
2. Для F# параметрах, используется в постфиксной форме: `int option` вместо `option<int>`.
3. Для F# массивы, используемое имя синтаксические `int[]` вместо `int array` или `array<int>`.
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

Помещение открывающей маркер на новую строку и закрытия токен в новой строке является рекомендуемое в том случае, если вы объявляете реализации интерфейса или элементы в записи:

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
        SomeField : int
    }
    interface IMyInterface
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

Поместив открывающий маркера в новой строке, с вкладками содержимое более чем одну область, и токен закрытия в новой строке рекомендуемое в том случае, если вы являетесь:

* Перемещение записей в коде с помощью отступов для разных областей
* Их по конвейеру в функцию

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
        SomeField : int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

Те же правила применяются для элементов списка и массива.

## <a name="formatting-lists-and-arrays"></a>Форматирование, списки и массивы

Запись `x :: l` с пробелы вокруг `::` оператор (`::` инфиксные оператор, поэтому окружен пробелами).

Список и массивов, объявленных в одной строке должны иметь пробел после открывающей скобки и перед закрывающей скобкой:

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

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

Же правило применяется для списков или массивы кортежей.

Списки и массивы, которые разбиты на несколько строк выполните аналогичные правила, как записи.

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

И с помощью записей объявление на строке открывающие и закрывающие скобки будут упрощают перемещение кода вокруг и передачи по конвейеру в функцию.

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
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
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

Избегайте лишние пробелы в F# выражения.

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

## <a name="formatting-attributes"></a>Атрибуты форматирования

[Атрибуты](../language-reference/attributes.md) помещаются выше конструкцию:

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

### <a name="formatting-attributes-on-parameters"></a>Атрибуты параметров форматирования

Атрибуты также могут быть окружение на параметры. В этом случае затем поместите в той же строке, в качестве параметра и перед именем:

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member __.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>Форматирование нескольких атрибутов

Если несколько атрибутов применяются к конструкцию, которая не является параметром, следует ли размещать их таким образом, что имеется один атрибут в строке:

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

При применении к параметру, они должны находиться в той же строке и разделены `;` разделителя.

## <a name="formatting-literals"></a>Форматирование литералы

[F#литералы](../language-reference/literals.md) с помощью `Literal` атрибут следует поместить атрибут на отдельной строке и использовать именования camelCase:

```fsharp
[<Literal>]
let path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let myUrl = "www.mywebsitethatiamworkingwith.com"
```

Избегайте размещения в той же строке, что значение атрибута.
