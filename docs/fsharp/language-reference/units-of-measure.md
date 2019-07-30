---
title: Единицы измерения
description: Узнайте, как значения с плавающей запятой и F# целым числом со знаком в могут иметь связанные единицы измерения, которые обычно используются для обозначения длины, объема и массы.
ms.date: 05/16/2016
ms.openlocfilehash: f97eac9984f934c55aff8cf9f287afbc3aa098f3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630159"
---
# <a name="units-of-measure"></a><span data-ttu-id="6e319-103">Единицы измерения</span><span class="sxs-lookup"><span data-stu-id="6e319-103">Units of Measure</span></span>

<span data-ttu-id="6e319-104">Целочисленные значения с плавающей запятой F# и со знаком в могут иметь связанные единицы измерения, которые обычно используются для обозначения длины, объема, массы и т. д.</span><span class="sxs-lookup"><span data-stu-id="6e319-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="6e319-105">Используя количественные единицы, вы включаете компилятор, чтобы убедиться, что арифметические связи имеют правильные единицы, что помогает предотвратить ошибки программирования.</span><span class="sxs-lookup"><span data-stu-id="6e319-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e319-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e319-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="6e319-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6e319-107">Remarks</span></span>

<span data-ttu-id="6e319-108">В предыдущем синтаксисе параметр *Unit-Name* определяется как единица измерения.</span><span class="sxs-lookup"><span data-stu-id="6e319-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="6e319-109">Необязательная часть используется для определения новой меры с точки зрения ранее определенных единиц.</span><span class="sxs-lookup"><span data-stu-id="6e319-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="6e319-110">Например, в следующей строке определяется мера `cm` (сантиметр).</span><span class="sxs-lookup"><span data-stu-id="6e319-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="6e319-111">Следующая строка определяет меру `ml` (миллилитер) как кубический сантиметр (`cm^3`).</span><span class="sxs-lookup"><span data-stu-id="6e319-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="6e319-112">В предыдущем синтаксисе *мера* — это формула, в которой участвуют единицы.</span><span class="sxs-lookup"><span data-stu-id="6e319-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="6e319-113">В формулах, в которых задействованы единицы, целочисленные степени поддерживаются (положительные и отрицательные), пробелы между единицами указывают `*` на произведение двух единиц, также указывают `/` на произведение единиц и обозначает частное число единиц.</span><span class="sxs-lookup"><span data-stu-id="6e319-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="6e319-114">Для обратной единицы можно использовать отрицательное целое число или значение `/` , которое обозначает разделение между числителем и знаменателем формулы единицы.</span><span class="sxs-lookup"><span data-stu-id="6e319-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="6e319-115">Несколько единиц в знаменателе должны быть заключены в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="6e319-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="6e319-116">Единицы, разделенные пробелами `/` после, обрабатываются как часть знаменателя, но все единицы после a `*` обрабатываются как часть числителя.</span><span class="sxs-lookup"><span data-stu-id="6e319-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="6e319-117">Можно использовать 1 в выражениях единиц измерения, чтобы указать количество без измерения или вместе с другими единицами, например в числителе.</span><span class="sxs-lookup"><span data-stu-id="6e319-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="6e319-118">Например, единицы курса записываются как `1/s`, где `s` — секунды.</span><span class="sxs-lookup"><span data-stu-id="6e319-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="6e319-119">Круглые скобки не используются в формулах единиц.</span><span class="sxs-lookup"><span data-stu-id="6e319-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="6e319-120">Константы числового преобразования не указываются в формулах единиц; Однако константы преобразования можно определить с помощью единиц по отдельности и использовать их в вычислениях с проверкой единиц измерения.</span><span class="sxs-lookup"><span data-stu-id="6e319-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="6e319-121">Формулы единиц, означающие то же самое, можно написать различными способами.</span><span class="sxs-lookup"><span data-stu-id="6e319-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="6e319-122">Таким образом, компилятор преобразует формулы единиц в согласованную форму, которая преобразует отрицательные степени в обратные, группирует единицы в один числитель и знаменатель и алфабетизес единицы в числителе и знаменателе.</span><span class="sxs-lookup"><span data-stu-id="6e319-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="6e319-123">Например, формулы `kg m s^-2` единиц и `m /s s * kg` преобразуются в `kg m/s^2`.</span><span class="sxs-lookup"><span data-stu-id="6e319-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="6e319-124">Единицы измерения используются в выражениях с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="6e319-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="6e319-125">Использование чисел с плавающей запятой вместе со связанными единицами измерения позволяет добавить другой уровень безопасности типа и помогает избежать ошибок несоответствия единиц, которые могут возникать в формулах при использовании слабо типизированных чисел с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="6e319-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="6e319-126">При написании выражения с плавающей запятой, в котором используются единицы измерения, единицы в выражении должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="6e319-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="6e319-127">Литералы можно закомментировать с помощью формулы единицы в угловых скобках, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="6e319-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="6e319-128">Между числом и угловой скобкой не ставится пробел. Однако можно включить литеральный суффикс `f`, например, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6e319-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="6e319-129">Такая Аннотация изменяет тип литерала с его примитивного типа (например `float` `float<miles/hour>`,) на размер измерения, `float<cm>` например или, в данном случае.</span><span class="sxs-lookup"><span data-stu-id="6e319-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="6e319-130">Заметка единицы измерения `<1>` указывает на неизмерение количества, и его тип эквивалентен типу-примитиву без параметра Unit.</span><span class="sxs-lookup"><span data-stu-id="6e319-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="6e319-131">Тип единицы измерения — это целочисленный тип с плавающей запятой или со знаком, а также дополнительный комментарий к единице, обозначенный в квадратных скобках.</span><span class="sxs-lookup"><span data-stu-id="6e319-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="6e319-132">Таким образом, при написании типа преобразования из `g` (грамм) в `kg` (килограммы) эти типы описываются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6e319-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="6e319-133">Единицы измерения используются для проверки единиц времени компиляции, но не сохраняются в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="6e319-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="6e319-134">Поэтому они не влияют на производительность.</span><span class="sxs-lookup"><span data-stu-id="6e319-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="6e319-135">Единицы измерения можно применять к любому типу, а не только к типам с плавающей запятой. Тем не менее, только типы с плавающей запятой, целочисленные типы со знаком и десятичные типы поддерживают измерения количества.</span><span class="sxs-lookup"><span data-stu-id="6e319-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="6e319-136">Поэтому имеет смысл использовать единицы измерения только для примитивных типов и для агрегатов, содержащих эти примитивные типы.</span><span class="sxs-lookup"><span data-stu-id="6e319-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="6e319-137">В следующем примере показано использование единиц измерения.</span><span class="sxs-lookup"><span data-stu-id="6e319-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

<span data-ttu-id="6e319-138">В следующем примере кода показано, как преобразовать из числа с плавающей запятой, не определяющего, в измерение с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="6e319-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="6e319-139">Вы просто умножаете на 1,0, применяя измерения к 1,0.</span><span class="sxs-lookup"><span data-stu-id="6e319-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="6e319-140">Это можно представить в виде функции, например `degreesFahrenheit`.</span><span class="sxs-lookup"><span data-stu-id="6e319-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="6e319-141">Кроме того, при передаче измеренных значений в функции, которые предполагают безразмерные числа с плавающей запятой, необходимо отказаться от `float` единиц или привести `float` к типу с помощью оператора.</span><span class="sxs-lookup"><span data-stu-id="6e319-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="6e319-142">В этом примере вы делите `1.0<degC>` на `printf` аргументы в, так как `printf` предполагается количество безразмерных измерений.</span><span class="sxs-lookup"><span data-stu-id="6e319-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="6e319-143">В следующем примере сеанса показаны выходные данные и входные данные этого кода.</span><span class="sxs-lookup"><span data-stu-id="6e319-143">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="6e319-144">Использование универсальных единиц</span><span class="sxs-lookup"><span data-stu-id="6e319-144">Using Generic Units</span></span>

<span data-ttu-id="6e319-145">Можно создавать универсальные функции, которые работают с данными, имеющими связанную единицу измерения.</span><span class="sxs-lookup"><span data-stu-id="6e319-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="6e319-146">Для этого нужно указать тип вместе с универсальной единицей в качестве параметра типа, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="6e319-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="6e319-147">Создание агрегатных типов с универсальными единицами</span><span class="sxs-lookup"><span data-stu-id="6e319-147">Creating Aggregate Types with Generic Units</span></span>

<span data-ttu-id="6e319-148">В следующем коде показано, как создать агрегатный тип, состоящий из отдельных значений с плавающей запятой, имеющих универсальные единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="6e319-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="6e319-149">Это позволяет создать один тип, который работает с различными единицами измерения.</span><span class="sxs-lookup"><span data-stu-id="6e319-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="6e319-150">Кроме того, универсальные единицы измерения сохраняют безопасность типа, гарантируя, что универсальный тип, имеющий один набор единиц, отличается от типа того же универсального типа с другим набором единиц.</span><span class="sxs-lookup"><span data-stu-id="6e319-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="6e319-151">На основе этого метода `Measure` можно применить атрибут к параметру типа.</span><span class="sxs-lookup"><span data-stu-id="6e319-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a><span data-ttu-id="6e319-152">Единицы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="6e319-152">Units at Runtime</span></span>

<span data-ttu-id="6e319-153">Единицы измерения используются для проверки статических типов.</span><span class="sxs-lookup"><span data-stu-id="6e319-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="6e319-154">При компиляции значений с плавающей запятой единицы измерения исключаются, поэтому они теряются во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6e319-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="6e319-155">Таким образом, любая попытка реализовать функциональность, зависящую от проверки единиц во время выполнения, невозможна.</span><span class="sxs-lookup"><span data-stu-id="6e319-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="6e319-156">Например, невозможно реализовать `ToString` функцию для вывода единиц на печать.</span><span class="sxs-lookup"><span data-stu-id="6e319-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>

## <a name="conversions"></a><span data-ttu-id="6e319-157">Преобразования</span><span class="sxs-lookup"><span data-stu-id="6e319-157">Conversions</span></span>

<span data-ttu-id="6e319-158">Для преобразования типа с единицами (например, `float<'u>`) в тип, не имеющий единиц, можно использовать стандартную функцию преобразования.</span><span class="sxs-lookup"><span data-stu-id="6e319-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="6e319-159">Например, можно использовать `float` для преобразования `float` в значение, не имеющее единиц, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="6e319-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="6e319-160">Чтобы преобразовать значение без единиц измерения в значение, имеющее единицы измерения, можно умножить его на значение 1 или 1,0 с заметками соответствующих единиц.</span><span class="sxs-lookup"><span data-stu-id="6e319-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="6e319-161">Однако для написания уровней взаимодействия существуют также некоторые явные функции, которые можно использовать для преобразования бесмодульных значений в значения с единицами измерения.</span><span class="sxs-lookup"><span data-stu-id="6e319-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="6e319-162">Они находятся в модуле [Microsoft. FSharp. Core. LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) .</span><span class="sxs-lookup"><span data-stu-id="6e319-162">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="6e319-163">Например, чтобы выполнить преобразование из бесмодульного `float` модуля `float<cm>`в, используйте [флоатвисмеасуре](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="6e319-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a><span data-ttu-id="6e319-164">Единицы измерения в F# основной библиотеке</span><span class="sxs-lookup"><span data-stu-id="6e319-164">Units of Measure in the F# Core library</span></span>

<span data-ttu-id="6e319-165">Библиотека единиц измерения доступна в `FSharp.Data.UnitSystems.SI` пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="6e319-165">A unit library is available in the `FSharp.Data.UnitSystems.SI` namespace.</span></span> <span data-ttu-id="6e319-166">Она включает в себя единицы СИ как в виде символов ( `m` например, для счетчика `UnitSymbols` ) в подпространстве имен, так и `meter` их полное имя (например, для `UnitNames` счетчика) в подпространстве имен.</span><span class="sxs-lookup"><span data-stu-id="6e319-166">It includes SI units in both their symbol form (like `m` for meter) in the `UnitSymbols` sub-namespace, and their full name (like `meter` for meter) in the `UnitNames` sub-namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e319-167">См. также</span><span class="sxs-lookup"><span data-stu-id="6e319-167">See also</span></span>

- [<span data-ttu-id="6e319-168">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="6e319-168">F# Language Reference</span></span>](index.md)
