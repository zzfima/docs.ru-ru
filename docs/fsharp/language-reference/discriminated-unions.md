---
title: Размеченные объединения
description: Сведения об использовании F# размеченные объединения.
ms.date: 05/16/2016
ms.openlocfilehash: 9d3f423d068df1c43791919b0d71ca82304ae85e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766031"
---
# <a name="discriminated-unions"></a><span data-ttu-id="69862-103">Размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="69862-103">Discriminated Unions</span></span>

<span data-ttu-id="69862-104">Размеченные объединения обеспечивают поддержку значений, которые может принимать одно из множества именованных вариантов, возможно, с разными значениями и типами.</span><span class="sxs-lookup"><span data-stu-id="69862-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="69862-105">Размеченные объединения удобны для разнородных данных; данные, которые могут иметь особые случаи, включая допустимые и ошибочные; данные, зависит от одного экземпляра типа в другой. и в качестве альтернативы иерархии небольших объектов.</span><span class="sxs-lookup"><span data-stu-id="69862-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="69862-106">Кроме того, рекурсивные размеченные объединения используются для представления древовидных структур данных.</span><span class="sxs-lookup"><span data-stu-id="69862-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="69862-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69862-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="69862-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="69862-108">Remarks</span></span>

<span data-ttu-id="69862-109">Размеченные объединения аналогичны типам объединений в других языках, но существуют различия.</span><span class="sxs-lookup"><span data-stu-id="69862-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="69862-110">Как с типом объединения в C++ или типа variant в Visual Basic, данные, хранящиеся в значении не фиксирована; он может принимать одно из нескольких отдельных вариантов.</span><span class="sxs-lookup"><span data-stu-id="69862-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="69862-111">В отличие от объединений в этих других языках, однако каждому из таких возможных вариантов присваивается *идентификатор варианта*.</span><span class="sxs-lookup"><span data-stu-id="69862-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="69862-112">Идентификаторы варианта представляют собой имена для различных типов возможных значений, которые могут быть объекты этого типа; значения являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="69862-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="69862-113">Если значения отсутствуют, вариант эквивалентен варианту перечисления.</span><span class="sxs-lookup"><span data-stu-id="69862-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="69862-114">Если значения присутствуют, каждое значение может быть одно значение заданного типа или кортежем, объединяющим несколько полей из одной или разных типов.</span><span class="sxs-lookup"><span data-stu-id="69862-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="69862-115">Можно присвоить имя, определенное поле, но имя является необязательным, даже если другие поля в том же регистре имеют имена.</span><span class="sxs-lookup"><span data-stu-id="69862-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="69862-116">По умолчанию специальные возможности для размеченных объединений `public`.</span><span class="sxs-lookup"><span data-stu-id="69862-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="69862-117">Например рассмотрим следующее объявление типа Shape.</span><span class="sxs-lookup"><span data-stu-id="69862-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="69862-118">Предыдущий код объявляет фигуры размеченного объединения, которая может иметь значения любого из трех случаях: Прямоугольник, круг и Prism.</span><span class="sxs-lookup"><span data-stu-id="69862-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="69862-119">Каждый случай имеет другой набор полей.</span><span class="sxs-lookup"><span data-stu-id="69862-119">Each case has a different set of fields.</span></span> <span data-ttu-id="69862-120">Случае прямоугольника имеет два именованных поля, оба типа `float`, которые имеют длину и ширину.</span><span class="sxs-lookup"><span data-stu-id="69862-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="69862-121">В случае с кругом имеется только одно именованное поле radius.</span><span class="sxs-lookup"><span data-stu-id="69862-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="69862-122">В случае призмы поля содержит 3, два из которых (ширина и высота) с именем поля.</span><span class="sxs-lookup"><span data-stu-id="69862-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="69862-123">Неименованные поля называются анонимные поля.</span><span class="sxs-lookup"><span data-stu-id="69862-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="69862-124">Объекты создаются путем задания значений для именованных и анонимных полей согласно следующим примерам.</span><span class="sxs-lookup"><span data-stu-id="69862-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="69862-125">Этот код показывает, что вы можете использовать именованные поля в инициализации или можно полагаться на упорядочивание полей в объявлении и просто предоставить значения для каждого поля, в свою очередь.</span><span class="sxs-lookup"><span data-stu-id="69862-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="69862-126">Вызов конструктора для `rect` в предыдущем коде использует именованные поля, но вызов конструктора для `circ` использует порядок.</span><span class="sxs-lookup"><span data-stu-id="69862-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="69862-127">Вы можете совместно использовать упорядоченные и именованные поля, как конструирование `prism`.</span><span class="sxs-lookup"><span data-stu-id="69862-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="69862-128">`option` Тип — это простое размеченное объединение в F# основной библиотеки.</span><span class="sxs-lookup"><span data-stu-id="69862-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="69862-129">`option` Тип объявляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="69862-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="69862-130">Предыдущий код указывает, что тип `Option` — это размеченное объединение, имеющее два варианта `Some` и `None`.</span><span class="sxs-lookup"><span data-stu-id="69862-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="69862-131">`Some` Case имеет связанное значение, которое состоит из одного анонимные поля, тип которого представлен параметром типа `'a`.</span><span class="sxs-lookup"><span data-stu-id="69862-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="69862-132">`None` Случай не имеет связанного значения.</span><span class="sxs-lookup"><span data-stu-id="69862-132">The `None` case has no associated value.</span></span> <span data-ttu-id="69862-133">Таким образом `option` тип указывает универсальный тип, который либо имеет значение некоторого типа, либо не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="69862-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="69862-134">Тип `Option` также имеет псевдоним в нижнем регистре, `option`, то есть сведения, которые обычно используются.</span><span class="sxs-lookup"><span data-stu-id="69862-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="69862-135">Идентификаторы варианта может использоваться в качестве конструкторов типа размеченного объединения.</span><span class="sxs-lookup"><span data-stu-id="69862-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="69862-136">Например, следующий код используется для создания значений `option` типа.</span><span class="sxs-lookup"><span data-stu-id="69862-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="69862-137">Идентификаторы варианта также используются в выражениях сопоставления шаблонов.</span><span class="sxs-lookup"><span data-stu-id="69862-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="69862-138">В выражении сопоставления с шаблонами идентификаторы предоставляются для значений, связанных с отдельными вариантами.</span><span class="sxs-lookup"><span data-stu-id="69862-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="69862-139">Например, в следующем коде `x` идентификатор, которому присваивается значение, с которым связан `Some` вариант `option` типа.</span><span class="sxs-lookup"><span data-stu-id="69862-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="69862-140">В выражениях сопоставления шаблонов можно использовать именованные поля для задания соответствия размеченным объединениям.</span><span class="sxs-lookup"><span data-stu-id="69862-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="69862-141">Для типа фигуры, который был объявлен ранее можно использовать именованные поля, как показывает следующий код для извлечения значений полей.</span><span class="sxs-lookup"><span data-stu-id="69862-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

<span data-ttu-id="69862-142">Обычно идентификаторы варианта могут использоваться без указания имени объединения.</span><span class="sxs-lookup"><span data-stu-id="69862-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="69862-143">Если вы хотите использовать имя, чтобы всегда уточняться именем объединения, можно применить [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) к определению типа объединения атрибут.</span><span class="sxs-lookup"><span data-stu-id="69862-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="69862-144">Распаковки размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="69862-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="69862-145">В F# размеченные объединения часто используются в модели предметной области для упаковки одного типа.</span><span class="sxs-lookup"><span data-stu-id="69862-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="69862-146">Это можно легко извлечь базового значения с помощью сопоставления шаблонов, а также.</span><span class="sxs-lookup"><span data-stu-id="69862-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="69862-147">Не нужно использовать выражение match для одного объекта:</span><span class="sxs-lookup"><span data-stu-id="69862-147">You don't need to use a match expression for a single case:</span></span>

```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

<span data-ttu-id="69862-148">Следующий пример демонстрирует это:</span><span class="sxs-lookup"><span data-stu-id="69862-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

<span data-ttu-id="69862-149">Сопоставление шаблонов также допускается непосредственно в виде параметров, поэтому можно снять оболочку с одного варианта:</span><span class="sxs-lookup"><span data-stu-id="69862-149">Pattern matching is also allowed directly in function parameters, so you can unwrap a single case there:</span></span>

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="69862-150">Размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="69862-150">Struct Discriminated Unions</span></span>

<span data-ttu-id="69862-151">Начиная с F# 4.1, может также представлять размеченные объединения, как структуры.</span><span class="sxs-lookup"><span data-stu-id="69862-151">Starting with F# 4.1, you can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="69862-152">Это делается с помощью `[<Struct>]` атрибута.</span><span class="sxs-lookup"><span data-stu-id="69862-152">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="69862-153">Так как они являются типами значений и не ссылаться на типы, существуют дополнительные рекомендации по сравнению со ссылкой на размеченные объединения:</span><span class="sxs-lookup"><span data-stu-id="69862-153">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="69862-154">Они будут скопированы в качестве типов значений и имеют семантика типа значения.</span><span class="sxs-lookup"><span data-stu-id="69862-154">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="69862-155">Рекурсивное определение типа нельзя использовать со структурой multicase размеченные объединения.</span><span class="sxs-lookup"><span data-stu-id="69862-155">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="69862-156">Необходимо указать уникальные имена вариантов для структуры multicase размеченные объединения.</span><span class="sxs-lookup"><span data-stu-id="69862-156">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="69862-157">Использование размеченных объединений вместо иерархий объектов</span><span class="sxs-lookup"><span data-stu-id="69862-157">Using Discriminated Unions Instead of Object Hierarchies</span></span>

<span data-ttu-id="69862-158">Часто размеченное объединение можно использовать в качестве более простой альтернативы небольшой иерархии объектов.</span><span class="sxs-lookup"><span data-stu-id="69862-158">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="69862-159">Например, следующее размеченное объединение может использоваться вместо `Shape` базового класса, имеющего производные классы для окружности, квадрата и т. д.</span><span class="sxs-lookup"><span data-stu-id="69862-159">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="69862-160">Вместо виртуального метода для вычисления площади или периметра, который бы использовался в объектно ориентированной реализации, можно использовать сопоставление шаблонов для выбора соответствующих формул расчета этих величин.</span><span class="sxs-lookup"><span data-stu-id="69862-160">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="69862-161">В следующем примере различные формулы используются для вычисления площади, зависит от формы.</span><span class="sxs-lookup"><span data-stu-id="69862-161">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="69862-162">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="69862-162">The output is as follows:</span></span>

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="69862-163">Использование размеченных объединений для древовидных структур данных</span><span class="sxs-lookup"><span data-stu-id="69862-163">Using Discriminated Unions for Tree Data Structures</span></span>

<span data-ttu-id="69862-164">Размеченные объединения могут быть рекурсивными, это означает, что само объединение может быть включено в тип одного или нескольких случаях.</span><span class="sxs-lookup"><span data-stu-id="69862-164">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="69862-165">Рекурсивные размеченные объединения могут использоваться для создания древовидных структур, которые используются для моделирования выражений в языках программирования.</span><span class="sxs-lookup"><span data-stu-id="69862-165">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="69862-166">В следующем коде рекурсивное размеченное объединение используется для создания древовидной структуры двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="69862-166">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="69862-167">Объединение состоит из двух вариантов `Node`, который является узел с целым значением, а также левую и правую ветви, и `Tip`, завершающий дерево.</span><span class="sxs-lookup"><span data-stu-id="69862-167">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="69862-168">В приведенном выше коде `resultSumTree` имеет значение 10.</span><span class="sxs-lookup"><span data-stu-id="69862-168">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="69862-169">Ниже показана структура дерева для `myTree`.</span><span class="sxs-lookup"><span data-stu-id="69862-169">The following illustration shows the tree structure for `myTree`.</span></span>

![Схема, показывающая структура дерева myTree.](../media/discriminated-unions/tree-structure-mytree.png)

<span data-ttu-id="69862-171">Размеченные объединения хорошо работают, если узлы дерева являются разнородными.</span><span class="sxs-lookup"><span data-stu-id="69862-171">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="69862-172">В следующем коде, тип `Expression` представляет дерево абстрактного синтаксиса выражения в простом языке программирования, поддерживающем сложение и умножение чисел и переменных.</span><span class="sxs-lookup"><span data-stu-id="69862-172">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="69862-173">Некоторые из вариантов объединения не являются рекурсивными и представляют либо числа (`Number`) или переменные (`Variable`).</span><span class="sxs-lookup"><span data-stu-id="69862-173">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="69862-174">Другие варианты являются рекурсивными и представляют операции (`Add` и `Multiply`), в которых операнды также являются выражениями.</span><span class="sxs-lookup"><span data-stu-id="69862-174">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="69862-175">`Evaluate` Функции используется выражение match для рекурсивной обработки дерева синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="69862-175">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="69862-176">При выполнении этого кода, значение `result` равно 5.</span><span class="sxs-lookup"><span data-stu-id="69862-176">When this code is executed, the value of `result` is 5.</span></span>

## <a name="common-attributes"></a><span data-ttu-id="69862-177">Общие атрибуты</span><span class="sxs-lookup"><span data-stu-id="69862-177">Common Attributes</span></span>

<span data-ttu-id="69862-178">Следующие атрибуты часто встречающихся в размеченные объединения:</span><span class="sxs-lookup"><span data-stu-id="69862-178">The following attributes are commonly seen in discriminated unions:</span></span>

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* `[Struct]`

## <a name="see-also"></a><span data-ttu-id="69862-179">См. также</span><span class="sxs-lookup"><span data-stu-id="69862-179">See also</span></span>

- [<span data-ttu-id="69862-180">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="69862-180">F# Language Reference</span></span>](index.md)