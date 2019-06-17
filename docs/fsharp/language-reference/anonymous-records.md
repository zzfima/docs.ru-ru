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
# <a name="anonymous-records"></a><span data-ttu-id="3c61a-103">Анонимные записей</span><span class="sxs-lookup"><span data-stu-id="3c61a-103">Anonymous Records</span></span>

<span data-ttu-id="3c61a-104">Анонимные записи являются простые агрегаты именованных значений, которые не нужно быть объявлена до использования.</span><span class="sxs-lookup"><span data-stu-id="3c61a-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="3c61a-105">Их можно объявить как структуры или ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="3c61a-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="3c61a-106">Они ссылочных типов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3c61a-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c61a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c61a-107">Syntax</span></span>

<span data-ttu-id="3c61a-108">В следующих примерах демонстрируется синтаксис анонимный записи.</span><span class="sxs-lookup"><span data-stu-id="3c61a-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="3c61a-109">Элементы с разделителями в виде `[item]` являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="3c61a-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="3c61a-110">Основное использование</span><span class="sxs-lookup"><span data-stu-id="3c61a-110">Basic usage</span></span>

<span data-ttu-id="3c61a-111">Анонимные записей лучше всего представить себе как F# типов, которые не должны быть объявлена до создания экземпляра записей.</span><span class="sxs-lookup"><span data-stu-id="3c61a-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="3c61a-112">Например здесь о том, как вы можете взаимодействовать с функцией, формирующий запись анонимных:</span><span class="sxs-lookup"><span data-stu-id="3c61a-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

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

<span data-ttu-id="3c61a-113">В следующем примере расширяется на предыдущий с `printCircleStats` функцию, которая принимает запись анонимных как входные данные:</span><span class="sxs-lookup"><span data-stu-id="3c61a-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

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

<span data-ttu-id="3c61a-114">Вызов `printCircleStats` с любой анонимный тип записи, не совпадают «» как тип входных данных не удастся скомпилировать:</span><span class="sxs-lookup"><span data-stu-id="3c61a-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="3c61a-115">Записи анонимные структуры</span><span class="sxs-lookup"><span data-stu-id="3c61a-115">Struct anonymous records</span></span>

<span data-ttu-id="3c61a-116">Анонимные записи также могут определяться как структуры с помощью необязательного `struct` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="3c61a-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="3c61a-117">Следующий пример расширяет предыдущий, создавая и используя запись анонимные структуры:</span><span class="sxs-lookup"><span data-stu-id="3c61a-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

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

### <a name="structness-inference"></a><span data-ttu-id="3c61a-118">Вывод Structness</span><span class="sxs-lookup"><span data-stu-id="3c61a-118">Structness inference</span></span>

<span data-ttu-id="3c61a-119">Записи анонимные структуры также обеспечивают «определение structness» где не нужно указывать `struct` ключевое слово во время вызова.</span><span class="sxs-lookup"><span data-stu-id="3c61a-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="3c61a-120">В этом примере elide `struct` ключевое слово при вызове `printCircleStats`:</span><span class="sxs-lookup"><span data-stu-id="3c61a-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="3c61a-121">Обратное шаблон - указание `struct` Если входной тип не анонимный записи структуры - скомпилировано не будет.</span><span class="sxs-lookup"><span data-stu-id="3c61a-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="3c61a-122">Внедрение анонимный записи в другие типы</span><span class="sxs-lookup"><span data-stu-id="3c61a-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="3c61a-123">Это полезно для объявления [размеченные объединения](discriminated-unions.md) , регистр которых являются записями.</span><span class="sxs-lookup"><span data-stu-id="3c61a-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="3c61a-124">Но если данные в записях, совпадает с типом размеченного объединения, необходимо определить все типы как взаимно рекурсивные.</span><span class="sxs-lookup"><span data-stu-id="3c61a-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="3c61a-125">Использование анонимных записей позволяет избежать это ограничение.</span><span class="sxs-lookup"><span data-stu-id="3c61a-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="3c61a-126">Ниже приведен пример тип и функцию этот шаблон соответствует над ним:</span><span class="sxs-lookup"><span data-stu-id="3c61a-126">What follows is an example type and function that pattern matches over it:</span></span>

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

## <a name="copy-and-update-expressions"></a><span data-ttu-id="3c61a-127">Копирование и обновление выражений</span><span class="sxs-lookup"><span data-stu-id="3c61a-127">Copy and update expressions</span></span>

<span data-ttu-id="3c61a-128">Анонимные записей поддержки конструкции с [копирование и обновление выражений](copy-and-update-record-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3c61a-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="3c61a-129">Например, вот как можно построить новый экземпляр анонимного записи, которая копирует существующий единицы данных:</span><span class="sxs-lookup"><span data-stu-id="3c61a-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="3c61a-130">Тем не менее, в отличие от именованного записей анонимный записи позволяют создавать совершенно разные формы с копией и обновите выражения.</span><span class="sxs-lookup"><span data-stu-id="3c61a-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="3c61a-131">Следующий пример принимает ту же запись анонимных из предыдущего примера и увеличивает его в новый анонимный запись:</span><span class="sxs-lookup"><span data-stu-id="3c61a-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="3c61a-132">Можно также для создания анонимных записей из экземпляров именованных записей:</span><span class="sxs-lookup"><span data-stu-id="3c61a-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="3c61a-133">Можно также скопировать данные в и из ссылки и структура анонимный записей:</span><span class="sxs-lookup"><span data-stu-id="3c61a-133">You can also copy data to and from reference and struct anonymous records:</span></span>

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

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="3c61a-134">Свойства анонимного записей</span><span class="sxs-lookup"><span data-stu-id="3c61a-134">Properties of anonymous records</span></span>

<span data-ttu-id="3c61a-135">Анонимные записи имеют ряд характеристик, которые необходимы для полного представления о том, как они могут использоваться.</span><span class="sxs-lookup"><span data-stu-id="3c61a-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="3c61a-136">Анонимные записи являются Номинальное</span><span class="sxs-lookup"><span data-stu-id="3c61a-136">Anonymous records are nominal</span></span>

<span data-ttu-id="3c61a-137">Анонимные записей [номинальные типы](https://en.wikipedia.org/wiki/Nominal_type_system).</span><span class="sxs-lookup"><span data-stu-id="3c61a-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="3c61a-138">Они лучше всего считать как с именем [записи](records.md) типов (которые также Номинальное), не требующие первоначальных объявление.</span><span class="sxs-lookup"><span data-stu-id="3c61a-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="3c61a-139">Рассмотрим следующий пример с помощью двух объявлений анонимных записи:</span><span class="sxs-lookup"><span data-stu-id="3c61a-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="3c61a-140">`x` И `y` значения имеют разные типы и не совместимы друг с другом.</span><span class="sxs-lookup"><span data-stu-id="3c61a-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="3c61a-141">Они не сериализовывать и они не поддерживают сравнение.</span><span class="sxs-lookup"><span data-stu-id="3c61a-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="3c61a-142">Чтобы проиллюстрировать это, рассмотрим эквивалентный именованный записи:</span><span class="sxs-lookup"><span data-stu-id="3c61a-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="3c61a-143">Нет никаких действий по своей природе отличия анонимный записей по сравнению с их эквивалентами именованный записи при относительно эквивалентности типа или сравнения.</span><span class="sxs-lookup"><span data-stu-id="3c61a-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="3c61a-144">Использовать анонимный записей структурного равенства и сравнения</span><span class="sxs-lookup"><span data-stu-id="3c61a-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="3c61a-145">Как и типы записей анонимные записи являются структурно сериализовывать и сравним.</span><span class="sxs-lookup"><span data-stu-id="3c61a-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="3c61a-146">Это только значение true, если все составные типы поддерживают равенства и сравнения, как и с типами записей.</span><span class="sxs-lookup"><span data-stu-id="3c61a-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="3c61a-147">Для поддержки проверки на равенство и сравнение, два анонимный записях должны же «фигуры».</span><span class="sxs-lookup"><span data-stu-id="3c61a-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="3c61a-148">Анонимные записи являются сериализуемыми</span><span class="sxs-lookup"><span data-stu-id="3c61a-148">Anonymous records are serializable</span></span>

<span data-ttu-id="3c61a-149">Можно сериализовать анонимный записей, так же, как с помощью именованных записей.</span><span class="sxs-lookup"><span data-stu-id="3c61a-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="3c61a-150">Ниже приведен пример с помощью [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span><span class="sxs-lookup"><span data-stu-id="3c61a-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

<span data-ttu-id="3c61a-151">Анонимные записей можно использовать для отправки небольшого количества данных в сети без необходимости определения домена заранее типы сериализацией и десериализацией.</span><span class="sxs-lookup"><span data-stu-id="3c61a-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="3c61a-152">Анонимные записей взаимодействовать с C# анонимные типы</span><span class="sxs-lookup"><span data-stu-id="3c61a-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="3c61a-153">Можно использовать API .NET, который требует применения [ C# анонимные типы](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="3c61a-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="3c61a-154">C#Анонимные типы просты для взаимодействия с с использованием анонимных записей.</span><span class="sxs-lookup"><span data-stu-id="3c61a-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="3c61a-155">Приведенный ниже показано, как использовать анонимный записи, чтобы вызвать [LINQ](../../csharp/programming-guide/concepts/linq/index.md) перегрузка, которая требует анонимного типа:</span><span class="sxs-lookup"><span data-stu-id="3c61a-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

<span data-ttu-id="3c61a-156">Существует множество других API, используемые в .NET, требуют использования передав анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="3c61a-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="3c61a-157">Анонимные записи являются ваше средство для работы с ними.</span><span class="sxs-lookup"><span data-stu-id="3c61a-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="3c61a-158">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3c61a-158">Limitations</span></span>

<span data-ttu-id="3c61a-159">Анонимные записи имеют некоторые ограничения в их использования.</span><span class="sxs-lookup"><span data-stu-id="3c61a-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="3c61a-160">Некоторые принадлежат в проектировании, а другие — способной приноравливаться к изменениям.</span><span class="sxs-lookup"><span data-stu-id="3c61a-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="3c61a-161">Ограничения с сопоставлением шаблонов</span><span class="sxs-lookup"><span data-stu-id="3c61a-161">Limitations with pattern matching</span></span>

<span data-ttu-id="3c61a-162">Анонимные записей не поддерживают сопоставление шаблонов, в отличие от именованного записей.</span><span class="sxs-lookup"><span data-stu-id="3c61a-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="3c61a-163">Существуют три причины:</span><span class="sxs-lookup"><span data-stu-id="3c61a-163">There are three reasons:</span></span>

1. <span data-ttu-id="3c61a-164">Шаблон бы учетной записи для каждого поля, анонимного записи, в отличие от типов именованных записей.</span><span class="sxs-lookup"><span data-stu-id="3c61a-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="3c61a-165">Это обусловлено анонимный записей не поддерживают структурное подтипов — они номинальных типов.</span><span class="sxs-lookup"><span data-stu-id="3c61a-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="3c61a-166">Из-за (1) отсутствие возможности иметь дополнительные шаблоны в выражении соответствия шаблону каждый шаблон distinct бы подразумевают типа анонимного записи.</span><span class="sxs-lookup"><span data-stu-id="3c61a-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="3c61a-167">Из-за (3) любой шаблон анонимный записи будет более подробным, чем использование «точками».</span><span class="sxs-lookup"><span data-stu-id="3c61a-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="3c61a-168">Отсутствует предложение языка с открытым [Разрешить сопоставление шаблонов в ограниченные контексты](https://github.com/fsharp/fslang-suggestions/issues/713).</span><span class="sxs-lookup"><span data-stu-id="3c61a-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="3c61a-169">Ограничения, связанные с изменяемостью</span><span class="sxs-lookup"><span data-stu-id="3c61a-169">Limitations with mutability</span></span>

<span data-ttu-id="3c61a-170">В настоящее время невозможно определить запись анонимных с `mutable` данных.</span><span class="sxs-lookup"><span data-stu-id="3c61a-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="3c61a-171">Существует [откройте предложение языка](https://github.com/fsharp/fslang-suggestions/issues/732) чтобы разрешить изменяемые данные.</span><span class="sxs-lookup"><span data-stu-id="3c61a-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="3c61a-172">Ограничения при использовании записей анонимные структуры</span><span class="sxs-lookup"><span data-stu-id="3c61a-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="3c61a-173">Невозможно объявить анонимный записи в виде структуры `IsByRefLike` или `IsReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="3c61a-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="3c61a-174">Существует [откройте предложение языка](https://github.com/fsharp/fslang-suggestions/issues/712) для для `IsByRefLike` и `IsReadOnly` анонимный записей.</span><span class="sxs-lookup"><span data-stu-id="3c61a-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
