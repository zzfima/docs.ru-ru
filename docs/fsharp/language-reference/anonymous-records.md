---
title: Анонимные записи
description: Узнайте, как использовать конструкцию и анонимные записи — функции языка, которые помогают управлять данными.
ms.date: 06/12/2019
ms.openlocfilehash: 0a7a819cc471c6579feacd621ed15aa89a6423ba
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569472"
---
# <a name="anonymous-records"></a>Анонимные записи

Анонимные записи — это простые статистические выражения именованных значений, которые не нужно объявлять перед использованием. Их можно объявить как структуры или ссылочные типы. По умолчанию они являются ссылочными типами.

## <a name="syntax"></a>Синтаксис

В следующих примерах демонстрируется синтаксис анонимных записей. Элементы, разделенные `[item]`, являются необязательными.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>Основное использование

Анонимные записи лучше рассматривать как F# типы записей, которые не нужно объявлять перед созданием экземпляра.

Например, вот как можно взаимодействовать с функцией, которая создает анонимную запись:

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

В следующем примере предыдущий объект разворачивается с помощью функции `printCircleStats`, которая принимает анонимную запись в качестве входных данных:

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

Вызов `printCircleStats` с любым типом анонимных записей, который не имеет такой же "формы", как и тип входных данных, не может компилироваться:

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>Анонимные записи структуры

Анонимные записи также можно определить как структуру с необязательным `struct` ключевым словом. В следующем примере предыдущий объект расширяется путем создания и использования анонимной записи структуры:

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

### <a name="structness-inference"></a>Определение структуры

Анонимные записи структуры также позволяют «выведение структуры», где не нужно указывать ключевое слово `struct` в месте вызова. В этом примере вы елиде ключевое слово `struct` при вызове `printCircleStats`:

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

Обратный шаблон — указывает, `struct` если входной тип не является структурой анонимной записи, компиляция не будет выполнена.

## <a name="embedding-anonymous-records-within-other-types"></a>Внедрение анонимных записей в другие типы

Полезно объявлять [Размеченные объединения](discriminated-unions.md) , варианты которых являются записями. Но если данные в записях имеют тот же тип, что и размеченное объединение, необходимо определить все типы как взаимные рекурсивные. Использование анонимных записей позволяет избежать этого ограничения. Ниже приведен пример типа и функции, которые соответствуют шаблону:

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

Анонимные записи поддерживают конструкцию с [выражениями копирования и обновления](copy-and-update-record-expressions.md). Например, вот как можно создать новый экземпляр анонимной записи, который копирует существующие данные.

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

Однако в отличие от именованных записей анонимные записи позволяют создавать совершенно разные формы с выражениями копирования и обновления. Следующий пример принимает ту же анонимную запись из предыдущего примера и разворачивает ее в новую анонимную запись:

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

Кроме того, можно создавать анонимные записи из экземпляров именованных записей.

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

Также можно скопировать данные в анонимные записи ссылок и структуры и обратно:

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

Анонимные записи имеют ряд характеристик, необходимых для полного понимания того, как их можно использовать.

### <a name="anonymous-records-are-nominal"></a>Анонимные записи являются номинальными

Анонимные записи — это [Номинальные типы](https://en.wikipedia.org/wiki/Nominal_type_system). Они лучше рассматривать как именованные типы [записей](records.md) (которые также являются номинальными), для которых не требуется объявление переднего плана.

Рассмотрим следующий пример с двумя анонимными объявлениями записей:

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

Значения `x` и `y` имеют разные типы и несовместимы друг с другом. Они не являются сопоставимыми и не являются сравнимыми. Чтобы проиллюстрировать это, рассмотрим эквивалент именованной записи:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

При сравнении с их эквивалентами типов анонимные записи по-разному не различаются.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>Анонимные записи используют структурное равенство и сравнение

Как и типы записей, анонимные записи имеют структурную равенство и сравнимы. Это справедливо только в том случае, если все составные типы поддерживают равенство и сравнение, как и типы записей. Для поддержки равенства или сравнения две анонимные записи должны иметь одинаковую форму.

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>Анонимные записи являются сериализуемыми

Можно выполнять сериализацию анонимных записей так же, как и с именованными записями. Ниже приведен пример использования [Newtonsoft. JSON](https://www.nuget.org/packages/Newtonsoft.Json/):

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

Анонимные записи полезны для отправки облегченных данных по сети без необходимости определения домена для сериализованных и десериализованных типов.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>Анонимные записи взаимодействуют с C# анонимными типами

Можно использовать API-интерфейс .NET, который требует использования [ C# анонимных типов](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). C#Анонимные типы являются тривиальными для взаимодействия с с помощью анонимных записей. В следующем примере показано, как использовать анонимные записи для вызова перегрузки [LINQ](../../csharp/programming-guide/concepts/linq/index.md) , для которой требуется анонимный тип:

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

Существует множество других API-интерфейсов, используемых в .NET, требующих передачи анонимного типа. Анонимные записи — это средство для работы с ними.

## <a name="limitations"></a>Ограничения

Анонимные записи имеют некоторые ограничения в их использовании. Некоторые из них относятся к их проектированию, но другие податлива.

### <a name="limitations-with-pattern-matching"></a>Ограничения, связанные с сопоставлением шаблонов

Анонимные записи не поддерживают сопоставление шаблонов, в отличие от именованных записей. Существует три причины.

1. Шаблон должен учитывать каждое поле анонимной записи, в отличие от именованных типов записей. Это обусловлено тем, что анонимные записи не поддерживают структурную подтипизацию — они являются номинальными типами.
2. Из-за (1) нет возможности иметь дополнительные шаблоны в выражении соответствия шаблону, так как каждый отдельный шаблон подразумевает другой анонимный тип записи.
3. Из-за (3) любой анонимный шаблон записи будет более подробным, чем использование нотации "точка".

Существует предложение Open Language, позволяющее [сопоставлять шаблоны в ограниченных контекстах](https://github.com/fsharp/fslang-suggestions/issues/713).

### <a name="limitations-with-mutability"></a>Ограничения с изменяемостью

В настоящее время невозможно определить анонимную запись с `mutable` данными. Существует [предложение Open Language](https://github.com/fsharp/fslang-suggestions/issues/732) , разрешающее изменяющиеся данные.

### <a name="limitations-with-struct-anonymous-records"></a>Ограничения для анонимных записей структуры

Невозможно объявить анонимные записи структуры как `IsByRefLike` или `IsReadOnly`. Существует [предложение Open Language](https://github.com/fsharp/fslang-suggestions/issues/712) для `IsByRefLike` и `IsReadOnly` анонимных записей.
