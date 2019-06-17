---
title: Анонимные записей
description: Узнайте, как использовать конструкции, а анонимные записей, — функцию языка, помогает управления данными.
ms.date: 06/12/2019
ms.openlocfilehash: e576210d4fb76ccfd09f8feb157ef4542aa94ccf
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041808"
---
# <a name="anonymous-records"></a>Анонимные записей

Анонимные записи являются простые агрегаты именованных значений, которые не нужно быть объявлена до использования. Их можно объявить как структуры или ссылочный тип. Они ссылочных типов по умолчанию.

## <a name="syntax"></a>Синтаксис

В следующих примерах демонстрируется синтаксис анонимный записи. Элементы с разделителями в виде `[item]` являются необязательными.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>Основное использование

Анонимные записей лучше всего представить себе как F# типов, которые не должны быть объявлена до создания экземпляра записей.

Например здесь о том, как вы можете взаимодействовать с функцией, формирующий запись анонимных:

```fsharp

open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

В следующем примере расширяется на предыдущий с `printCircleStats` функцию, которая принимает запись анонимных как входные данные:

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let printCircleStats r (stats: {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

Вызов `printCircleStats` с любой анонимный тип записи, не совпадают «» как тип входных данных не удастся скомпилировать:

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>Записи анонимные структуры

Анонимные записи также могут определяться как структуры с помощью необязательного `struct` ключевое слово. Следующий пример расширяет предыдущий, создавая и используя запись анонимные структуры:

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    // Note that the keyword comes before the '{| |}' brace pair
    struct {| Area = a; Circumference = c; Diameter = d |}

// the 'struct' keyword also comes before the '{| |}' brace pair when declaring the parameter type
let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

### <a name="structness-inference"></a>Вывод Structness

Записи анонимные структуры также обеспечивают «определение structness» где не нужно указывать `struct` ключевое слово во время вызова. В этом примере elide `struct` ключевое слово при вызове `printCircleStats`:

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

Обратное шаблон - указание `struct` Если входной тип не анонимный записи структуры - скомпилировано не будет.

## <a name="embedding-anonymous-records-within-other-types"></a>Внедрение анонимный записи в другие типы

Это полезно для объявления [размеченные объединения](discriminated-unions.md) , регистр которых являются записями. Но если данные в записях, совпадает с типом размеченного объединения, необходимо определить все типы как взаимно рекурсивные. Использование анонимных записей позволяет избежать это ограничение. Ниже приведен пример тип и функцию этот шаблон соответствует над ним:

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named for Manager and Executive would require mutually recursive definitions.
type Employee =
    | Engineer of FullName
    | Manager of {| Name: FullName; Reports: Employee list |}
    | Executive of {| Name: FullName; Reports: Employee list; Assistant: Employee |}

let getFirstName e =
    match e with
    | Engineer fullName -> fullName.FirstName
    | Manager m -> m.Name.FirstName
    | Executive ex -> ex.Name.FirstName
```

## <a name="copy-and-update-expressions"></a>Копирование и обновление выражений

Анонимные записей поддержки конструкции с [копирование и обновление выражений](copy-and-update-record-expressions.md). Например, вот как можно построить новый экземпляр анонимного записи, которая копирует существующий единицы данных:

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

Тем не менее, в отличие от именованного записей анонимный записи позволяют создавать совершенно разные формы с копией и обновите выражения. Следующий пример принимает ту же запись анонимных из предыдущего примера и увеличивает его в новый анонимный запись:

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

Можно также для создания анонимных записей из экземпляров именованных записей:

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

Можно также скопировать данные в и из ссылки и структура анонимный записей:

```fsharp
// Copy data from a reference record into a struct anonymous record
type R1 = { X: int }
let r1 = { X = 1 }

let data1 = struct {| r1 with Y = 1 |}

// Copy data from a struct record into a reference anonymous record
[<Struct>]
type R2 = { X: int }
let r2 = { X = 1 }

let data2 = {| r1 with Y = 1 |}

// Copy the reference anonymous record data into a struct anonymous record
let data3 = struct {| data2 with Z = r2.X |}
```

## <a name="properties-of-anonymous-records"></a>Свойства анонимного записей

Анонимные записи имеют ряд характеристик, которые необходимы для полного представления о том, как они могут использоваться.

### <a name="anonymous-records-are-nominal"></a>Анонимные записи являются Номинальное

Анонимные записей [номинальные типы](https://en.wikipedia.org/wiki/Nominal_type_system). Они лучше всего считать как с именем [записи](records.md) типов (которые также Номинальное), не требующие первоначальных объявление.

Рассмотрим следующий пример с помощью двух объявлений анонимных записи:

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

`x` И `y` значения имеют разные типы и не совместимы друг с другом. Они не сериализовывать и они не поддерживают сравнение. Чтобы проиллюстрировать это, рассмотрим эквивалентный именованный записи:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

Нет никаких действий по своей природе отличия анонимный записей по сравнению с их эквивалентами именованный записи при относительно эквивалентности типа или сравнения.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>Использовать анонимный записей структурного равенства и сравнения

Как и типы записей анонимные записи являются структурно сериализовывать и сравним. Это только значение true, если все составные типы поддерживают равенства и сравнения, как и с типами записей. Для поддержки проверки на равенство и сравнение, два анонимный записях должны же «фигуры».

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>Анонимные записи являются сериализуемыми

Можно сериализовать анонимный записей, так же, как с помощью именованных записей. Ниже приведен пример с помощью [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

Анонимные записей можно использовать для отправки небольшого количества данных в сети без необходимости определения домена заранее типы сериализацией и десериализацией.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>Анонимные записей взаимодействовать с C# анонимные типы

Можно использовать API .NET, который требует применения [ C# анонимные типы](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). C#Анонимные типы просты для взаимодействия с с использованием анонимных записей. Приведенный ниже показано, как использовать анонимный записи, чтобы вызвать [LINQ](../../csharp/programming-guide/concepts/linq/index.md) перегрузка, которая требует анонимного типа:

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

Существует множество других API, используемые в .NET, требуют использования передав анонимный тип. Анонимные записи являются ваше средство для работы с ними.

## <a name="limitations"></a>Ограничения

Анонимные записи имеют некоторые ограничения в их использования. Некоторые принадлежат в проектировании, а другие — способной приноравливаться к изменениям.

### <a name="limitations-with-pattern-matching"></a>Ограничения с сопоставлением шаблонов

Анонимные записей не поддерживают сопоставление шаблонов, в отличие от именованного записей. Существуют три причины:

1. Шаблон бы учетной записи для каждого поля, анонимного записи, в отличие от типов именованных записей. Это обусловлено анонимный записей не поддерживают структурное подтипов — они номинальных типов.
2. Из-за (1) отсутствие возможности иметь дополнительные шаблоны в выражении соответствия шаблону каждый шаблон distinct бы подразумевают типа анонимного записи.
3. Из-за (3) любой шаблон анонимный записи будет более подробным, чем использование «точками».

Отсутствует предложение языка с открытым [Разрешить сопоставление шаблонов в ограниченные контексты](https://github.com/fsharp/fslang-suggestions/issues/713).

### <a name="limitations-with-mutability"></a>Ограничения, связанные с изменяемостью

В настоящее время невозможно определить запись анонимных с `mutable` данных. Существует [откройте предложение языка](https://github.com/fsharp/fslang-suggestions/issues/732) чтобы разрешить изменяемые данные.

### <a name="limitations-with-struct-anonymous-records"></a>Ограничения при использовании записей анонимные структуры

Невозможно объявить анонимный записи в виде структуры `IsByRefLike` или `IsReadOnly`. Существует [откройте предложение языка](https://github.com/fsharp/fslang-suggestions/issues/712) для для `IsByRefLike` и `IsReadOnly` анонимный записей.
