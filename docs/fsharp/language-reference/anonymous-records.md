---
title: Анонимные записи
description: Узнайте, как использовать построение и использование Anonymous Records, языковой функции, которая помогает с манипулированием данными.
ms.date: 06/12/2019
ms.openlocfilehash: ef3aa8fccdb6ff406542932816e4138040845a59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187496"
---
# <a name="anonymous-records"></a>Анонимные записи

Анонимные записи — это простые агрегаты именных значений, которые не нужно декларировать перед использованием. Вы можете объявить их как либо структур, либо типов ссылок. Они типов ссылок по умолчанию.

## <a name="syntax"></a>Синтаксис

Следующие примеры демонстрируют анонимный синтаксис записи. Элементы делимитированы как `[item]` необязательные.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>Основное использование

Анонимные записи лучше всего рассматривать как типы записей F-записей, которые не должны быть объявлены до мгновенного.

Например, здесь, как можно взаимодействовать с функцией, которая производит анонимные записи:

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

Следующий пример расширяет предыдущий с `printCircleStats` функцией, которая принимает анонимные записи в качестве ввода:

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

Вызов `printCircleStats` с любым анонимным типом записи, который не имеет той же "формы", что и тип ввода, не сможет компилироваться:

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>Struct анонимные записи

Анонимные записи также могут быть `struct` определены как структурировать с дополнительным ключевым словом. Следующий пример дополняет предыдущий, производя и потребляя анонимную запись структурирования:

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

### <a name="structness-inference"></a>Вывод о структурности

Struct анонимные записи также позволяют "structness вывод", `struct` где вам не нужно указывать ключевое слово на сайте вызова. В этом примере вы `struct` ускользаете от ключевого слова при вызове: `printCircleStats`

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

Обратный шаблон - `struct` указание, когда тип ввода не является структурной анонимной записью - не сможет компилироваться.

## <a name="embedding-anonymous-records-within-other-types"></a>Внедрение анонимных записей в другие типы

Полезно объявить [дискриминированные профсоюзы,](discriminated-unions.md) дела которых являются отчетами. Но если данные в записях имеют тот же тип, что и дискриминируемый союз, необходимо определить все типы как взаимно повторяющихся. Использование анонимных записей позволяет избежать этого ограничения. Ниже приводится пример типа и функции, которые шаблон совпадает над ним:

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

Анонимные записи поддержки строительства с [копией и обновления выражения](copy-and-update-record-expressions.md). Например, вот как можно создать новый экземпляр анонимной записи, которая копирует существующие данные:

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

Однако, в отличие от названных записей, анонимные записи позволяют создавать совершенно разные формы с помощью выражений копирования и обновления. В следующем примере приводится та же анонимная запись из предыдущего примера и расширяется ее в новую анонимную запись:

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

Также можно создавать анонимные записи из экземпляров названных записей:

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

Вы также можете копировать данные и из ссылки и структурировать анонимные записи:

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

## <a name="properties-of-anonymous-records"></a>Свойства анонимных записей

Анонимные записи имеют ряд характеристик, которые необходимы для полного понимания того, как они могут быть использованы.

### <a name="anonymous-records-are-nominal"></a>Анонимные записи являются номинальными

Анонимные записи являются [номинальными типами.](https://en.wikipedia.org/wiki/Nominal_type_system) Они лучше всего рассматривать как названные типы [записей](records.md) (которые также являются номинальными), которые не требуют предварительного объявления.

Рассмотрим следующий пример с двумя анонимными отчетными декларациями:

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

Значения `x` `y` и значения имеют разные типы и не совместимы друг с другом. Они не являются равноденновыми и несопоставимы. Чтобы проиллюстрировать это, рассмотрим именованный эквивалент записи:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

Существует не что-нибудь по своей сути отличается об анонимных записей по сравнению с их имени эквиваленты записи, когда относительно эквивалентности типа или сравнения.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>Анонимные записи используют структурное равенство и сравнение

Как и типы записей, анонимные записи структурно приравниваемы и сопоставимы. Это верно только в том случае, если все составные типы поддерживают равенство и сравнение, как с типами записей. Для поддержки равенства или сравнения две анонимные записи должны иметь одинаковую "форму".

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>Анонимные записи являются сериализуемыми

Вы можете сериализировать анонимные записи так же, как вы можете с именем записей. Вот пример использования [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip')

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

Анонимные записи полезны для отправки легких данных по сети без необходимости определения домена для сериализованных/десериализованных типов заранее.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>Анонимные записи взаимодействуют с анонимными типами C

Можно использовать API .NET, который требует использования [анонимных типов C.](../../csharp/programming-guide/classes-and-structs/anonymous-types.md) Анонимные типы C' тривиальны для работы с помощью анонимных записей. В следующем примере показано, как использовать анонимные записи для вызова перегрузки [LIN,](../../csharp/programming-guide/concepts/linq/index.md) которая требует анонимного типа:

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

Есть множество других AA, используемых во всем .NET, которые требуют использования прохождения в анонимном типе. Анонимные записи являются вашим инструментом для работы с ними.

## <a name="limitations"></a>Ограничения

Анонимные записи имеют некоторые ограничения в их использовании. Некоторые из них присущи их дизайн, но другие поддаются изменениям.

### <a name="limitations-with-pattern-matching"></a>Ограничения с сопоставлением шаблонов

Анонимные записи не поддерживают соответствие шаблона, в отличие от названных записей. Есть три причины:

1. Шаблон должен учитывать каждое поле анонимной записи, в отличие от названных типов записей. Это связано с тем, что анонимные записи не поддерживают структурное субтипирование – они являются номинальными типами.
2. Из-за (1) нет возможности иметь дополнительные шаблоны в выражении шаблона, так как каждый отдельный шаблон подразумевал бы другой анонимный тип записи.
3. Из-за (3) любой анонимный шаблон записи будет более многословен, чем использование обозначения "точка".

Существует открытое предложение языка, чтобы [позволить шаблон соответствия в ограниченных контекстах.](https://github.com/fsharp/fslang-suggestions/issues/713)

### <a name="limitations-with-mutability"></a>Ограничения с изменяемостью

В настоящее время невозможно определить `mutable` анонимную запись с данными. Существует [открытое предложение языка,](https://github.com/fsharp/fslang-suggestions/issues/732) чтобы позволить изменяемые данные.

### <a name="limitations-with-struct-anonymous-records"></a>Ограничения с структурировать анонимные записи

Невозможно объявить структурировать анонимные `IsByRefLike` записи как или `IsReadOnly`. Существует [открытое предложение](https://github.com/fsharp/fslang-suggestions/issues/712) языка `IsByRefLike` `IsReadOnly` для и анонимных записей.
