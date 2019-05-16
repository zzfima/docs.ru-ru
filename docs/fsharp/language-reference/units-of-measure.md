---
title: Единицы измерения
description: Узнайте, как число с плавающей запятой и вошли целочисленных значений в F# могут иметь связанные единицы измерения, которые обычно используются для указания длины, тома и запоминающих устройств.
ms.date: 05/16/2016
ms.openlocfilehash: 217ef67912625c0a4b187a7ee13a739de811cfcb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641632"
---
# <a name="units-of-measure"></a><span data-ttu-id="ba841-103">Единицы измерения</span><span class="sxs-lookup"><span data-stu-id="ba841-103">Units of Measure</span></span>

<span data-ttu-id="ba841-104">Число с плавающей запятой и вошли целочисленных значений в F# могут иметь связанные единицы измерения, которые обычно используются для указания длины, тома, запоминающих устройств и т. д.</span><span class="sxs-lookup"><span data-stu-id="ba841-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="ba841-105">С помощью количества единиц, позволяет компилятору проверять, что арифметические связи имеют правильный единицы измерения, что позволяет избежать ошибок программирования.</span><span class="sxs-lookup"><span data-stu-id="ba841-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba841-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba841-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="ba841-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba841-107">Remarks</span></span>

<span data-ttu-id="ba841-108">Предыдущий синтаксис определяет *наименование единицы измерения* как единица измерения.</span><span class="sxs-lookup"><span data-stu-id="ba841-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="ba841-109">Необязательная часть используется для определения новой меры с точки зрения ранее определенных единиц измерения.</span><span class="sxs-lookup"><span data-stu-id="ba841-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="ba841-110">Например, следующая строка определяет меру `cm` (сантиметр).</span><span class="sxs-lookup"><span data-stu-id="ba841-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="ba841-111">В следующей строке определяется мера `ml` (миллиметр определяется) с помощью кубического сантиметра (`cm^3`).</span><span class="sxs-lookup"><span data-stu-id="ba841-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="ba841-112">В приведенном выше синтаксисе *мер* — это формула, которая содержит единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="ba841-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="ba841-113">В формулах, содержащих единицы измерения, поддерживаются целочисленные степени (положительные и отрицательные), пробелы между единицами указывают на произведение двух блоков, `*` также указывает измерения, и `/` указывает на частное единиц.</span><span class="sxs-lookup"><span data-stu-id="ba841-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="ba841-114">Для обратных единиц, вы можете использовать power отрицательное целое число или `/` , разделяющий числителя и знаменателя формулы единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="ba841-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="ba841-115">Несколько единиц в знаменателе должны быть заключены в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="ba841-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="ba841-116">Единицы, разделенного пробелами после `/` интерпретируются как часть знаменатель, но единицы, следующие `*` интерпретируются как часть числитель.</span><span class="sxs-lookup"><span data-stu-id="ba841-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="ba841-117">1 можно использовать в выражениях модульных, либо отдельно, чтобы обозначить количество без измерений, или другие единицы измерения, как в числителе.</span><span class="sxs-lookup"><span data-stu-id="ba841-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="ba841-118">Например, единицы частоты записываются в виде `1/s`, где `s` секунд.</span><span class="sxs-lookup"><span data-stu-id="ba841-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="ba841-119">В формулах единиц не используются скобки.</span><span class="sxs-lookup"><span data-stu-id="ba841-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="ba841-120">Числовые константы преобразования не указан в формулах единиц; Тем не менее можно определить преобразование константы с единицами отдельно и использовать их в вычислениях с проверкой единиц.</span><span class="sxs-lookup"><span data-stu-id="ba841-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="ba841-121">Формулы единиц, означает то же могут записываться различными способами.</span><span class="sxs-lookup"><span data-stu-id="ba841-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="ba841-122">Таким образом компилятор преобразует формулы единиц в единообразный вид, который преобразует отрицательные степени на обратные, группирует единицы в единый числителя и знаменателя и выполняет сортировку по алфавиту единицы в числителя и знаменателя.</span><span class="sxs-lookup"><span data-stu-id="ba841-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="ba841-123">Например, формулы единиц `kg m s^-2` и `m /s s * kg` преобразуются в `kg m/s^2`.</span><span class="sxs-lookup"><span data-stu-id="ba841-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="ba841-124">You use units of measure in floating point expressions.</span><span class="sxs-lookup"><span data-stu-id="ba841-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="ba841-125">С помощью числа с плавающей запятой соответствующих единиц измерения повышает уровень безопасности типов и помогает избежать ошибки несоответствия единицы, которые могут возникнуть в формулах, при использовании слабо типизированным числа с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="ba841-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="ba841-126">При написании плавающей точки выражение, которое использует единицы, единицы измерения в выражении должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="ba841-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="ba841-127">Пользователь может снабдить литералы с формулы единицы измерения в угловых скобках, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="ba841-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="ba841-128">Не следует добавлять пробел между числом и угловой скобки; Тем не менее, можно включить литеральный суффикс, такие как `f`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ba841-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="ba841-129">Такой заметки изменяет тип литерала с примитивного (такие как `float`) на тип с измерением, такие как `float<cm>` или, в этом случае `float<miles/hour>`.</span><span class="sxs-lookup"><span data-stu-id="ba841-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="ba841-130">Заметка единицы `<1>` указывает количество без измерений и его тип эквивалентен типу-примитиву без параметра единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="ba841-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="ba841-131">Тип единицы измерения — это число с плавающей запятой или целого типа, а также дополнительных модульных заметки, указаны в скобках со знаком.</span><span class="sxs-lookup"><span data-stu-id="ba841-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="ba841-132">Таким образом, при создании типа преобразования из `g` (г) для `kg` (килограммы) типы описываются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ba841-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="ba841-133">Единицы измерения используются для проверки единиц компиляции, но не сохраняются в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="ba841-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="ba841-134">Таким образом они не влияют на производительность.</span><span class="sxs-lookup"><span data-stu-id="ba841-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="ba841-135">Единицы измерения, которые могут применяться к любому типу, не только типы с плавающей запятой; Тем не менее только типы с плавающей запятой, вошедшим целочисленные типы и десятичных типов поддерживают количества с измерениями.</span><span class="sxs-lookup"><span data-stu-id="ba841-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="ba841-136">Таким образом он имеет смысл только использовать единицы измерения, на типы-примитивы и статистических выражений, содержащих эти типы-примитивы.</span><span class="sxs-lookup"><span data-stu-id="ba841-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="ba841-137">Следующий пример иллюстрирует использование единиц измерения.</span><span class="sxs-lookup"><span data-stu-id="ba841-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

<span data-ttu-id="ba841-138">В следующем примере кода показано, как преобразовать из безразмерные число с плавающей запятой в случае многомерных значение с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="ba841-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="ba841-139">Вы только что умножьте 1.0, применение размеры 1.0.</span><span class="sxs-lookup"><span data-stu-id="ba841-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="ba841-140">Это можно было абстрагировать в функции, например `degreesFahrenheit`.</span><span class="sxs-lookup"><span data-stu-id="ba841-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="ba841-141">Кроме того, при передаче размерные значения в функции, ожидающие безразмерные числа с плавающей запятой, необходимо исключить единицы измерения или привести к `float` с помощью `float` оператор.</span><span class="sxs-lookup"><span data-stu-id="ba841-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="ba841-142">В этом примере выполняется деление `1.0<degC>` для аргументов `printf` поскольку `printf` ожидает безразмерные.</span><span class="sxs-lookup"><span data-stu-id="ba841-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="ba841-143">В следующем примере сеанса показаны выходные данные и входные данные этого кода.</span><span class="sxs-lookup"><span data-stu-id="ba841-143">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="ba841-144">Использование универсальных единиц</span><span class="sxs-lookup"><span data-stu-id="ba841-144">Using Generic Units</span></span>

<span data-ttu-id="ba841-145">Можно написать универсальные функции, которые работают на данные, которые имеют связанную единицу измерения.</span><span class="sxs-lookup"><span data-stu-id="ba841-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="ba841-146">Это делается путем указания типа вместе с универсальной единицей в качестве параметра типа, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ba841-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="ba841-147">Создание типов статистических выражений с универсальными единицами</span><span class="sxs-lookup"><span data-stu-id="ba841-147">Creating Aggregate Types with Generic Units</span></span>

<span data-ttu-id="ba841-148">Приведенный ниже показано, как создать Агрегатный тип, состоящий из отдельных значений с плавающей запятой единиц измерения, которые являются обобщенными.</span><span class="sxs-lookup"><span data-stu-id="ba841-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="ba841-149">Это позволяет один тип должен быть создан, работает с несколькими единицами.</span><span class="sxs-lookup"><span data-stu-id="ba841-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="ba841-150">Кроме того универсальные единицы повышают безопасность типа, гарантируя, что универсальный тип, который имеет один набор единицы — это тип, отличный от одного универсального типа с другим набором значений.</span><span class="sxs-lookup"><span data-stu-id="ba841-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="ba841-151">Основой этого приема является то, что `Measure` атрибут может быть применен к параметру типа.</span><span class="sxs-lookup"><span data-stu-id="ba841-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a><span data-ttu-id="ba841-152">Единицы, во время выполнения</span><span class="sxs-lookup"><span data-stu-id="ba841-152">Units at Runtime</span></span>

<span data-ttu-id="ba841-153">Единицы измерения используются для проверки статических типов.</span><span class="sxs-lookup"><span data-stu-id="ba841-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="ba841-154">При компиляции с плавающей запятой единицы измерения исключаются, поэтому единицы измерения будут потеряны во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ba841-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="ba841-155">Таким образом любая попытка реализации функциональности, зависит от того, проверки единицы измерения во время выполнения не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ba841-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="ba841-156">Например, реализация `ToString` функцию для распечатки единиц не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ba841-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>

## <a name="conversions"></a><span data-ttu-id="ba841-157">Преобразования</span><span class="sxs-lookup"><span data-stu-id="ba841-157">Conversions</span></span>

<span data-ttu-id="ba841-158">Для преобразования типа, имеющего единицы (например, `float<'u>`) к типу, который не поддерживает единиц, можно использовать функцию стандартное преобразование.</span><span class="sxs-lookup"><span data-stu-id="ba841-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="ba841-159">Например, можно использовать `float` для преобразования в `float` значение, которое не поддерживает единицы, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ba841-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="ba841-160">Чтобы преобразовать значение без единиц измерения в значение, которое имеет единиц, можно умножить значение 1 или 1.0, которое помечается с помощью соответствующие единицы.</span><span class="sxs-lookup"><span data-stu-id="ba841-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="ba841-161">Однако для создания уровней взаимодействия, существуют также некоторые явные функции, которые можно использовать для преобразования значений без единиц измерения в значения с единицами измерения.</span><span class="sxs-lookup"><span data-stu-id="ba841-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="ba841-162">Они находятся в [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) модуля.</span><span class="sxs-lookup"><span data-stu-id="ba841-162">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="ba841-163">Например, для преобразования из в `float` для `float<cm>`, использовать [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ba841-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a><span data-ttu-id="ba841-164">Единицы измерения в F# основной библиотеки</span><span class="sxs-lookup"><span data-stu-id="ba841-164">Units of Measure in the F# Core library</span></span>

<span data-ttu-id="ba841-165">Библиотека модульных доступен в `FSharp.Data.UnitSystems.SI` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ba841-165">A unit library is available in the `FSharp.Data.UnitSystems.SI` namespace.</span></span> <span data-ttu-id="ba841-166">Он включает SI единицы в оба символа форме (как `m` для метрики) в `UnitSymbols` sub-пространство имен, а также их полным именам (как `meter` для метрики) в `UnitNames` sub-пространство имен.</span><span class="sxs-lookup"><span data-stu-id="ba841-166">It includes SI units in both their symbol form (like `m` for meter) in the `UnitSymbols` sub-namespace, and their full name (like `meter` for meter) in the `UnitNames` sub-namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba841-167">См. также</span><span class="sxs-lookup"><span data-stu-id="ba841-167">See also</span></span>

- [<span data-ttu-id="ba841-168">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="ba841-168">F# Language Reference</span></span>](index.md)
