---
title: Размеченные объединения
description: Узнайте, как использовать дискриминируемые союзы.
ms.date: 05/16/2016
ms.openlocfilehash: 539e2843c0bbc8c5ac9c0597ffc5443f8cd127f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401073"
---
# <a name="discriminated-unions"></a><span data-ttu-id="84b61-103">Размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="84b61-103">Discriminated Unions</span></span>

<span data-ttu-id="84b61-104">Дискриминируемые союзы обеспечивают поддержку ценностей, которые могут быть одним из нескольких названных случаев, возможно, каждый с различными значениями и типами.</span><span class="sxs-lookup"><span data-stu-id="84b61-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="84b61-105">Дискриминируемые союзы полезны для получения неоднородных данных; данные, которые могут иметь особые случаи, включая действительные и случаи ошибки; данные, которые различаются по типу в зависимости от другого; и в качестве альтернативы для малых объектов иерархии.</span><span class="sxs-lookup"><span data-stu-id="84b61-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="84b61-106">Кроме того, для представления структур данных о деревьях используются рекурсивные дискриминирующие союзы.</span><span class="sxs-lookup"><span data-stu-id="84b61-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="84b61-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84b61-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="84b61-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="84b61-108">Remarks</span></span>

<span data-ttu-id="84b61-109">Дискриминируемые союзы аналогичны типам профсоюзов на других языках, но существуют различия.</span><span class="sxs-lookup"><span data-stu-id="84b61-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="84b61-110">Как и в отношении типа соединения в C- или типа варианта в Visual Basic, данные, хранящиеся в значении, не фиксируются; это может быть один из нескольких различных вариантов.</span><span class="sxs-lookup"><span data-stu-id="84b61-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="84b61-111">В отличие от союзов на этих других языках, однако, каждый из возможных вариантов дается *идентификатор случая*.</span><span class="sxs-lookup"><span data-stu-id="84b61-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="84b61-112">Идентификаторы случаев представляют имена для различных возможных типов значений, которыми могут быть объекты этого типа; значения не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="84b61-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="84b61-113">Если значения отсутствуют, случай эквивалентен делу о перечислении.</span><span class="sxs-lookup"><span data-stu-id="84b61-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="84b61-114">При наличии значений каждое значение может быть либо одним значением определенного типа, либо тулутом, который агрегирует несколько полей одного или одного типа.</span><span class="sxs-lookup"><span data-stu-id="84b61-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="84b61-115">Вы можете дать отдельному полю имя, но имя необязательно, даже если названы другие поля в том же случае.</span><span class="sxs-lookup"><span data-stu-id="84b61-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="84b61-116">Доступность для дискриминируемых `public`профсоюзов по умолчанию .</span><span class="sxs-lookup"><span data-stu-id="84b61-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="84b61-117">Например, рассмотрим следующую декларацию типа формы.</span><span class="sxs-lookup"><span data-stu-id="84b61-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="84b61-118">Предыдущий код объявляет дискриминационную форму союза, которая может иметь значения любого из трех случаев: Rectangle, Circle и Prism.</span><span class="sxs-lookup"><span data-stu-id="84b61-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="84b61-119">Каждый случай имеет свой набор полей.</span><span class="sxs-lookup"><span data-stu-id="84b61-119">Each case has a different set of fields.</span></span> <span data-ttu-id="84b61-120">Корпус Rectangle имеет два названных `float`поля, оба типа, которые имеют ширину и длину названий.</span><span class="sxs-lookup"><span data-stu-id="84b61-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="84b61-121">В корпусе Круга есть только одно названное поле радиус.</span><span class="sxs-lookup"><span data-stu-id="84b61-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="84b61-122">Случай Prism имеет три поля, два из которых (ширина и высота) названы полями.</span><span class="sxs-lookup"><span data-stu-id="84b61-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="84b61-123">Неназванные поля называются анонимными полями.</span><span class="sxs-lookup"><span data-stu-id="84b61-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="84b61-124">Объекты строятся, предоставляя значения для названных и анонимных полей в соответствии со следующими примерами.</span><span class="sxs-lookup"><span data-stu-id="84b61-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="84b61-125">Этот код показывает, что вы можете использовать названные поля в инициализации, либо можно положиться на упорядочение полей в декларации и просто предоставить значения для каждого поля в свою очередь.</span><span class="sxs-lookup"><span data-stu-id="84b61-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="84b61-126">Конструктор вызова `rect` в предыдущем коде использует названные поля, но `circ` конструктор вызова для использования заказа.</span><span class="sxs-lookup"><span data-stu-id="84b61-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="84b61-127">Можно смешивать заказанные поля и названные `prism`поля, как при строительстве.</span><span class="sxs-lookup"><span data-stu-id="84b61-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="84b61-128">Тип `option` представляет собой простой дискриминируемый союз в основной библиотеке F.</span><span class="sxs-lookup"><span data-stu-id="84b61-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="84b61-129">Тип `option` объявляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="84b61-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="84b61-130">Предыдущий код указывает, что `Option` тип является дискриминируемым `Some` союзом, который имеет два случая, и `None`.</span><span class="sxs-lookup"><span data-stu-id="84b61-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="84b61-131">Случай `Some` имеет связанное значение, которое состоит из одного анонимного `'a`поля, тип которого представлен параметром типа.</span><span class="sxs-lookup"><span data-stu-id="84b61-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="84b61-132">Случай `None` не имеет связанного значения.</span><span class="sxs-lookup"><span data-stu-id="84b61-132">The `None` case has no associated value.</span></span> <span data-ttu-id="84b61-133">Таким `option` образом, тип определяет общий тип, который либо имеет значение определенного типа, либо не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="84b61-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="84b61-134">Тип `Option` также имеет псевдоним нижнего типа, `option`который чаще используется.</span><span class="sxs-lookup"><span data-stu-id="84b61-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="84b61-135">Идентификаторы случаев могут использоваться в качестве конструкторов для дискриминируемого типа профсоюза.</span><span class="sxs-lookup"><span data-stu-id="84b61-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="84b61-136">Например, для создания значений `option` типа используется следующий код.</span><span class="sxs-lookup"><span data-stu-id="84b61-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="84b61-137">Идентификаторы случая также используются в выражениях, соответствующих шаблонам.</span><span class="sxs-lookup"><span data-stu-id="84b61-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="84b61-138">В выражении, соответствуя шаблону, идентификаторы предоставляются значения, связанные с отдельными случаями.</span><span class="sxs-lookup"><span data-stu-id="84b61-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="84b61-139">Например, в следующем `x` коде является идентификатор, `Some` учитывая `option` значение, связанное с случаем типа.</span><span class="sxs-lookup"><span data-stu-id="84b61-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="84b61-140">При сопоставлении шаблонов можно использовать именные поля для указания дискриминированных совпадений соединения.</span><span class="sxs-lookup"><span data-stu-id="84b61-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="84b61-141">Для типа формы, который был объявлен ранее, можно использовать названные поля в качестве следующего кода для извлечения значений полей.</span><span class="sxs-lookup"><span data-stu-id="84b61-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

<span data-ttu-id="84b61-142">Как правило, идентификаторы случаев могут быть использованы без квалификации их с именем союза.</span><span class="sxs-lookup"><span data-stu-id="84b61-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="84b61-143">Если вы хотите, чтобы имя всегда квалифицировалось с названием союза, вы можете применить атрибут [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) к определению типа соединения.</span><span class="sxs-lookup"><span data-stu-id="84b61-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="84b61-144">Разворачивание дискриминированных союзов</span><span class="sxs-lookup"><span data-stu-id="84b61-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="84b61-145">В F-дискриированных союзах часто используются в моделировании доменов для упаковки одного типа.</span><span class="sxs-lookup"><span data-stu-id="84b61-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="84b61-146">Легко извлечь основное значение с помощью шаблона соответствия, а также.</span><span class="sxs-lookup"><span data-stu-id="84b61-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="84b61-147">Вам не нужно использовать выражение соответствия для одного случая:</span><span class="sxs-lookup"><span data-stu-id="84b61-147">You don't need to use a match expression for a single case:</span></span>

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

<span data-ttu-id="84b61-148">Следующий пример демонстрирует это:</span><span class="sxs-lookup"><span data-stu-id="84b61-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

<span data-ttu-id="84b61-149">Соответствие шаблона также допускается непосредственно в параметрах функции, так что вы можете развернуть один случай там:</span><span class="sxs-lookup"><span data-stu-id="84b61-149">Pattern matching is also allowed directly in function parameters, so you can unwrap a single case there:</span></span>

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="84b61-150">Struct дискриминируемые союзы</span><span class="sxs-lookup"><span data-stu-id="84b61-150">Struct Discriminated Unions</span></span>

<span data-ttu-id="84b61-151">Вы также можете представлять дискриминируемые союзы как структуры.</span><span class="sxs-lookup"><span data-stu-id="84b61-151">You can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="84b61-152">Это делается `[<Struct>]` с атрибутом.</span><span class="sxs-lookup"><span data-stu-id="84b61-152">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="84b61-153">Поскольку это типы значений, а не типы ссылок, существуют дополнительные соображения по сравнению со ссылками дискриминируемых союзов:</span><span class="sxs-lookup"><span data-stu-id="84b61-153">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="84b61-154">Они копируются как типы значений и имеют семантику типа значений.</span><span class="sxs-lookup"><span data-stu-id="84b61-154">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="84b61-155">Вы не можете использовать рекурсивное определение типа с многокомпонентным структурированным дискриминированным союзом.</span><span class="sxs-lookup"><span data-stu-id="84b61-155">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="84b61-156">Вы должны предоставить уникальные имена дел для многокомпонентного структурного дискриминируемого союза.</span><span class="sxs-lookup"><span data-stu-id="84b61-156">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="84b61-157">Использование дискриминируемых союзов вместо иерархии объектов</span><span class="sxs-lookup"><span data-stu-id="84b61-157">Using Discriminated Unions Instead of Object Hierarchies</span></span>

<span data-ttu-id="84b61-158">Часто можно использовать дискриминируемый союз как более простую альтернативу иерархии малых объектов.</span><span class="sxs-lookup"><span data-stu-id="84b61-158">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="84b61-159">Например, вместо `Shape` базового класса, который вывел типы для круга, квадрата и так далее, можно использовать следующий дискриминируемый союз.</span><span class="sxs-lookup"><span data-stu-id="84b61-159">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="84b61-160">Вместо виртуального метода вычисления области или периметра, как это можно использовать в объектно-ориентированной реализации, можно использовать шаблон, соответствующий ветвке, соответствующим формулам для вычисления этих количеств.</span><span class="sxs-lookup"><span data-stu-id="84b61-160">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="84b61-161">В следующем примере для вычисления области используются различные формулы в зависимости от формы.</span><span class="sxs-lookup"><span data-stu-id="84b61-161">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="84b61-162">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="84b61-162">The output is as follows:</span></span>

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="84b61-163">Использование дискриминируемых союзов для структур данных деревьев</span><span class="sxs-lookup"><span data-stu-id="84b61-163">Using Discriminated Unions for Tree Data Structures</span></span>

<span data-ttu-id="84b61-164">Дискриминируемые союзы могут быть рекурсивными, а это означает, что сам союз может быть включен в тип одного или нескольких случаев.</span><span class="sxs-lookup"><span data-stu-id="84b61-164">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="84b61-165">Рекурсивные дискриминируемые союзы могут использоваться для создания структур деревьев, которые используются для моделирования выражений в языках программирования.</span><span class="sxs-lookup"><span data-stu-id="84b61-165">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="84b61-166">В следующем коде для создания бинарной структуры данных дерева используется рекурсивный дискриминируемый союз.</span><span class="sxs-lookup"><span data-stu-id="84b61-166">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="84b61-167">Союз состоит из двух `Node`случаев, которые представляет собой узла с цельным значением и левые и правые поддеревья, и `Tip`, который завершает дерево.</span><span class="sxs-lookup"><span data-stu-id="84b61-167">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="84b61-168">В предыдущем коде значение `resultSumTree` 10.</span><span class="sxs-lookup"><span data-stu-id="84b61-168">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="84b61-169">Следующая иллюстрация показывает `myTree`структуру дерева для .</span><span class="sxs-lookup"><span data-stu-id="84b61-169">The following illustration shows the tree structure for `myTree`.</span></span>

![Диаграмма, которая показывает структуру дерева для myTree.](../media/discriminated-unions/tree-structure-mytree.png)

<span data-ttu-id="84b61-171">Дискриминированные союзы хорошо работают, если узлы в дереве неоднородны.</span><span class="sxs-lookup"><span data-stu-id="84b61-171">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="84b61-172">В следующем коде `Expression` тип представляет абстрактное древо синтаксиса выражения на простом языке программирования, которое поддерживает добавление и умножение чисел и переменных.</span><span class="sxs-lookup"><span data-stu-id="84b61-172">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="84b61-173">Некоторые из случаев соединения не являются рекурсивными и представляют собой либо цифры ()`Number`или переменные ().`Variable`</span><span class="sxs-lookup"><span data-stu-id="84b61-173">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="84b61-174">Другие случаи являются рекурсивными, и представляют операции (и`Add` `Multiply`), где операции также выражения.</span><span class="sxs-lookup"><span data-stu-id="84b61-174">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="84b61-175">Функция `Evaluate` использует выражение соответствия для рекурсивной обработки дерева синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="84b61-175">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="84b61-176">Когда этот код выполняется, `result` значение 5.</span><span class="sxs-lookup"><span data-stu-id="84b61-176">When this code is executed, the value of `result` is 5.</span></span>

## <a name="members"></a><span data-ttu-id="84b61-177">Члены</span><span class="sxs-lookup"><span data-stu-id="84b61-177">Members</span></span>

<span data-ttu-id="84b61-178">Можно определить членов по дискриминируемым профсоюзам.</span><span class="sxs-lookup"><span data-stu-id="84b61-178">It is possible to define members on discriminated unions.</span></span> <span data-ttu-id="84b61-179">В следующем примере показано, как определить свойство и реализовать интерфейс:</span><span class="sxs-lookup"><span data-stu-id="84b61-179">The following example shows how to define a property and implement an interface:</span></span>

```fsharp
open System

type IPrintable =
    abstract Print: unit -> unit

type Shape =
    | Circle of float
    | EquilateralTriangle of float
    | Square of float
    | Rectangle of float * float

    member this.Area =
        match this with
        | Circle r -> 2.0 * Math.PI * r
        | EquilateralTriangle s -> s * s * sqrt 3.0 / 4.0
        | Square s -> s * s
        | Rectangle(l, w) -> l * w

    interface IPrintable with
        member this.Print () =
            match this with
            | Circle r -> printfn "Circle with radius %f" r
            | EquilateralTriangle s -> printfn "Equilateral Triangle of side %f" s
            | Square s -> printfn "Square with side %f" s
            | Rectangle(l, w) -> printfn "Rectangle with length %f and width %f" l w
```

## <a name="common-attributes"></a><span data-ttu-id="84b61-180">Общие атрибуты</span><span class="sxs-lookup"><span data-stu-id="84b61-180">Common attributes</span></span>

<span data-ttu-id="84b61-181">Следующие атрибуты обычно наблюдаются в дискриминируемых союзах:</span><span class="sxs-lookup"><span data-stu-id="84b61-181">The following attributes are commonly seen in discriminated unions:</span></span>

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a><span data-ttu-id="84b61-182">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84b61-182">See also</span></span>

- [<span data-ttu-id="84b61-183">Ссылка на язык F</span><span class="sxs-lookup"><span data-stu-id="84b61-183">F# Language Reference</span></span>](index.md)
