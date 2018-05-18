---
title: 'Рекомендации по форматирование кода F #'
description: 'Дополнительные рекомендации для форматирования кода F #.'
ms.date: 05/14/2018
ms.openlocfilehash: e5c700ca9ae3968243f11c1237b9e4b26e580dcf
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
---
# <a name="f-code-formatting-guidelines"></a>Правила форматирования кода F #

В этой статье предлагаются рекомендации по форматировать код так, чтобы код F #:

* Обычно рассматривать как более читаемым
* — В соответствии с соглашениями, применяется форматирование средств в Visual Studio и других редакторах
* Аналогично другим кодом по сети

Эти рекомендации основаны на [полное руководство по F # форматирование соглашения о](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) по [Phan Anh Dung](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Общие правила использования отступов

F # по умолчанию используется значимых пробелов. Следующие инструкции предназначены для предоставления рекомендации о том, как работать с определенными трудностями, это можно наложить.

### <a name="using-spaces"></a>С помощью пространств

Если требуется отступ, необходимо использовать пробелы, а не символы табуляции. Требуется по крайней мере один пробел. Организации могут создавать стандарты кодирования, чтобы указать количество пробелов, используемых для отступов; является типичным для двух, трех или четырех пробелов отступа на каждом уровне, где происходит отступов.

**Мы рекомендуем 4 пространств для каждого отступа.**

С другой стороны, отступы программ — это субъективная тема. Варианты ОК, но первое правило, необходимо следовать *согласованности отступа*. Выбор стиля общепринятые отступов и использовать его систематически во всей базе кода.

## <a name="formatting-discriminated-union-declarations"></a>Форматирование размеченные объединения объявления

Отступ `|` в определении типа 4 пробелами:

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

Созданный экземпляр размеченные объединения, которые разбиваются по нескольким строкам следует предоставить новой области с отступами содержащиеся данные:

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

## <a name="formatting-tuples"></a>Форматирование кортежи

Создание экземпляра кортежа следует заключать в круглые скобки и разделители запятые внутри должен следовать пробелом, например: `(1, 2)`, `(x, y, z)`.

Общепринятая исключение — пропустить круглые скобки в сопоставлениях с шаблоном кортежей:

```fsharp
let (x, y) = z // Destructuring

match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-records"></a>Форматирование записей

Короткие записи могут быть записаны в одной строке:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

Для меток записей, которые больше времени, следует использовать новые строки:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Размещение открывающей маркер на той же строке и закрытия маркер на новой строке будет нормально.

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

## <a name="formatting-lists-and-arrays"></a>Форматирование списки и массивы

Запись `x :: l` с пробелы вокруг `::` оператор (`::` инфиксные оператор, поэтому окружена пробелами) и `[1; 2; 3]` (`;` — разделитель, поэтому после пробела).

Всегда используйте по крайней мере один пробел между два различных оператора like фигурную скобку. Например, оставьте пробел между `[` и `{`.

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

## <a name="formatting-if-expressions"></a>Если форматировании выражений

Отступ условные выражения зависит от размеров выражений, составляющих их. Если `cond`, `e1` и `e2` небольшие, просто записывать их в одной строке:

```fsharp
if cond then e1 else e2
```

Если `e1` и `cond` небольшие, но `e2` большой:

```fsharp
if cond then e1
else
    e2
```

Если `e1` и `cond` велики и `e2` мал:

```fsharp
if cond then
    e1
else e2
```

Если все выражения имеют большой размер:

```fsharp
if cond then
    e1
else
    e2
```

Несколько условий с `elif` и `else` с отступом располагаются в той же области, как `if`:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Шаблон сопоставления конструкции

Используйте `|` для каждого предложения совпадения с без отступов. Если выражение короткий, можно использовать одну строку.

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

// OK
match l with [] -> false | _ :: _ -> true
```

Если выражение справа сопоставления стрелка шаблона слишком велико, переместите его на следующую строку с отступом один шаг из `match` / `|`.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Шаблон сопоставления анонимных функций, начиная с `function`, обычно не создать отступы слишком далеко. Например следующим отступов одну область подходит:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Совпадение по шаблону в функции, определенные по `let` или `let rec` должен быть с отступом 4 пробелов после начала `let`, даже если `function` используется ключевое слово:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Не рекомендуется выравнивание кнопки со стрелками.

## <a name="formatting-trywith-expressions"></a>Форматирование try / with выражения

Тип исключения сопоставления шаблонов должно иметь отступ на том же уровне, как `with`.

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

## <a name="formatting-function-parameter-application"></a>Применение параметра функции форматирования

Как правило большинство приложений параметра функция выполняется в той же строке.

Если вы хотите применить параметры к функции на новой строке, отступ их на одну область.

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

Анонимная функция аргументов может быть следующей строки или с висячего `fun` в строке аргумента:

```fsharp
// OK
let printListWithOffset a list1 =
    List.iter (fun elem ->
        printfn "%d" (a + elem)) list1

// OK, but prefer previous
let printListWithOffset a list1 =
    List.iter (
        fun elem ->
            printfn "%d" (a + elem)) list1
```

### <a name="formatting-infix-operators"></a>Форматирование инфиксные операторы

Отдельные операторы пробелами. Очевидным исключения из этого правила являются `!` и `.` операторы.

Выражения инфиксные — ОК разметка того же столбца.

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Форматирование конвейерных операторов

Конвейер `|>` должны перейти в начале строки непосредственно под, используемые в выражении:

```fsharp
// OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
               |> List.ofArray
               |> List.map (fun assm -> assm.GetTypes())
               |> Array.concat
               |> List.ofArray
               |> List.map (fun t -> t.GetMethods())
               |> Array.concat

// OK, but prefer previous
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

Код в локальном модуле должен иметь отступ относительно модуля, но код модуля верхнего уровня не должен иметь отступ. Элементы пространства имен не нужно иметь отступ.

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

### <a name="formatting-object-expressions-and-interfaces"></a>Форматирование выражения объектов и интерфейсов

Выражения объекта и интерфейсы должны быть выровнены с таким же образом `member` отступ после 4 пробела.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-whitespace-in-expressions"></a>Форматирование пробелов в выражениях

Избегайте лишних пробелов в выражениями языка F #.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Именованные аргументы также не следует пространство вокруг `=`:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-blank-lines"></a>Форматирование пустых строк

* Отдельные верхнего уровня функций и классов определения с две пустые строки.
* Метод определения внутри класса разделяются одна пустая строка.
* Лишних пустых строк может использоваться для разделения группы связанных функций (ограниченно). Можно опустить пустые строки между множества связанных командных строк (например, набор фиктивный реализации).
* Используйте пустые строки в функции, только в случае необходимости, чтобы указать логические разделы.

## <a name="formatting-comments"></a>Форматирование комментарии

Обычно предпочтение комментарии блока стиля ML несколько комментариев косая черта double.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    Generally avoid these kinds of comments.
*)
```

Встроенных комментариев следует преобразовать в прописную первую букву.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Соглашения об именах

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Используйте camelCase для класса привязанных к ограничениям, выражение привязки и шаблон значения и функции

Общие и принимаемые F # стиль camelCase для всех имен связан как локальные переменные или в соответствие шаблону и определения функций.

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

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Используйте camelCase для внутреннего использования и частных значения, связанные с модулем и функций

Используйте camelCase для частного значения, связанные с модуля, включая следующие:

* Нерегламентированные функции в скриптах

* Значения, входящим в состав внутренней реализации модуля или тип

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="avoid-underscores-in-names"></a>Избегайте подчеркивания в именах

Исторически некоторые библиотеки F # используется символ подчеркивания в именах. Тем не менее принимается больше не широко, так как он конфликтует с соглашения об именовании .NET. С другой стороны, некоторые программисты F # для использования подчеркивания сильно, частично Исторически сложилось так и обеспечения отказоустойчивости и уважение важен. Однако имейте в виду, что стиль часто не нравилось с другими пользователями, имеется возможность выбрать его использование.

Некоторые исключения включает взаимодействие с компонентами в машинном коде, где очень распространены символы подчеркивания.

### <a name="use-standard-f-operators"></a>Использовать стандартные операторы F #

Следующие операторы определены в стандартной библиотеке F # и должны использоваться вместо того чтобы определять эквиваленты. Рекомендуется использовать эти операторы, как он, как правило, чтобы сделать код более читаемым и идиоматическое. Возможно, разработчиков, имеющих опыт в OCaml или других функциональный язык программирования привыкли различные стили. В следующем списке перечислены рекомендуемые операторы F #.

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Throwing away a value
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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Используйте синтаксис префикс для универсальных шаблонов (`Foo<T>`) предпочтительнее, чем синтаксис постфиксная (`T Foo`)

F # наследует стиль постфиксная ML именования универсальных типов (например, `int list`) и префиксом .NET style (например, `list<int>`). Предпочитаю стиль .NET, за исключением четырех определенных типов.

1. Для F # список, используйте в постфиксной форме: `int list` вместо `list<int>`.
2. Для параметры F #, используйте в постфиксной форме: `int option` вместо `option<int>`.
3. В F # массивы, используется имя синтаксические `int[]` вместо `int array` или `array<int>`.
4. Ссылочные ячейки, используйте `int ref` вместо `ref<int>` или `Ref<int>`.

Для всех других типов используйте форму префикс.