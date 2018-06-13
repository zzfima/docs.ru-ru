---
title: Единицы измерения (F#)
description: 'Узнайте, как число с плавающей запятой и целое число со знаком значения в языке F #, могут иметь связанные единицы измерения, которые обычно используются для указания длины, тома и запоминающих устройств.'
ms.date: 05/16/2016
ms.openlocfilehash: 3e47c92100c1dd99161be709a065913f501854f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564955"
---
# <a name="units-of-measure"></a><span data-ttu-id="7ae64-103">Единицы измерения</span><span class="sxs-lookup"><span data-stu-id="7ae64-103">Units of Measure</span></span>

<span data-ttu-id="7ae64-104">Число с плавающей точкой и значения целого числа со знаком в языке F # могут иметь связанные единицы измерения, которые обычно используются для указания длины, объема, массовый, и т. д.</span><span class="sxs-lookup"><span data-stu-id="7ae64-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="7ae64-105">Используя количества единиц, включите компилятору Проверять арифметические связи у правильный единицы, что позволяет избежать ошибок программирования.</span><span class="sxs-lookup"><span data-stu-id="7ae64-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>


## <a name="syntax"></a><span data-ttu-id="7ae64-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ae64-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="7ae64-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ae64-107">Remarks</span></span>
<span data-ttu-id="7ae64-108">Определяет в предыдущем синтаксисе *имя устройства* как в единицах измерения.</span><span class="sxs-lookup"><span data-stu-id="7ae64-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="7ae64-109">Необязательная часть используется для определения новой меры в терминах ранее определенных единиц измерения.</span><span class="sxs-lookup"><span data-stu-id="7ae64-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="7ae64-110">Например, в следующей строке определяется мера `cm` (сантиметр).</span><span class="sxs-lookup"><span data-stu-id="7ae64-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="7ae64-111">В следующей строке определяется мера `ml` (миллиметр определяется) с помощью кубического сантиметра (`cm^3`).</span><span class="sxs-lookup"><span data-stu-id="7ae64-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="7ae64-112">В предыдущем синтаксисе *мер* — это формула, которая содержит единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="7ae64-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="7ae64-113">В формулах, содержащих единицы измерения, поддерживаются целочисленные степени (положительные и отрицательные), пробелы между единицами указывают на произведение двух частей, `*` также указывает, измерения, и `/` указывает на частное единиц.</span><span class="sxs-lookup"><span data-stu-id="7ae64-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="7ae64-114">Для обратных единиц можно использовать power отрицательное целое число или `/` , разделяющий числитель и знаменатель формулы единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="7ae64-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="7ae64-115">Несколько блоков в знаменателе должны быть заключены в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="7ae64-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="7ae64-116">Единицы разделяя их пробелами после `/` , считаются частью знаменателя, но единицы, следующие `*` интерпретируются как часть числитель.</span><span class="sxs-lookup"><span data-stu-id="7ae64-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="7ae64-117">1 можно использовать в выражениях единиц, либо отдельно, чтобы указать количество без измерений, или вместе с другими единицами, как в числителе.</span><span class="sxs-lookup"><span data-stu-id="7ae64-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="7ae64-118">Например, единицы частоты записываются в виде `1/s`, где `s` секунд.</span><span class="sxs-lookup"><span data-stu-id="7ae64-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="7ae64-119">В формулах единиц не используются скобки.</span><span class="sxs-lookup"><span data-stu-id="7ae64-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="7ae64-120">Числовые константы преобразования не указан в формулах единиц; Тем не менее можно определить константы преобразования с использованием единиц отдельно и использовать их в вычислениях с проверкой единиц.</span><span class="sxs-lookup"><span data-stu-id="7ae64-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="7ae64-121">Формулы единиц, означающие одно и то же самое можно записать различными способами.</span><span class="sxs-lookup"><span data-stu-id="7ae64-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="7ae64-122">Таким образом компилятор преобразует формулы единиц в единообразный вид, который преобразует отрицательные степени в обратные, группирует единицы в один числитель и знаменатель и выполняет сортировку по алфавиту единицы в числителе и знаменатель.</span><span class="sxs-lookup"><span data-stu-id="7ae64-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="7ae64-123">Например, формулы единиц `kg m s^-2` и `m /s s * kg` преобразуются в `kg m/s^2`.</span><span class="sxs-lookup"><span data-stu-id="7ae64-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="7ae64-124">Единицы измерения используются выражения с плавающей точкой.</span><span class="sxs-lookup"><span data-stu-id="7ae64-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="7ae64-125">С помощью числа с плавающей запятой соответствующих единиц измерения повышает уровень безопасности типов и помогает избежать ошибок несоответствие единицы, которые могут произойти в формулах, при использовании слабо типизированным числа с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="7ae64-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="7ae64-126">При написании плавающей точки выражение, которое использует единицы, единицы измерения в выражении должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="7ae64-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="7ae64-127">Можно снабдить литералы с формулы единиц в угловых скобках, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="7ae64-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="7ae64-128">Не следует помещать пробел между числом и угловых скобок; Тем не менее, можно включить суффикс литерала, такие как `f`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7ae64-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="7ae64-129">Такой заметки изменяет тип литерала с примитивного (такие как `float`) на тип с измерением, таких как `float<cm>` или, в этом случае `float<miles/hour>`.</span><span class="sxs-lookup"><span data-stu-id="7ae64-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="7ae64-130">Заметка единицы `<1>` указывает количество без измерений, а также тип эквивалентен типу-примитиву без параметра единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="7ae64-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="7ae64-131">Тип единицы измерения является тип с плавающей запятой или целочисленным типом, а также дополнительных модульных заметки, указаны в скобках со знаком.</span><span class="sxs-lookup"><span data-stu-id="7ae64-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="7ae64-132">Таким образом, при создании типа преобразования из `g` (граммов) для `kg` (килограмм) типы описываются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7ae64-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="7ae64-133">Единицы измерения используются для проверки единиц во время компиляции, но не сохраняются в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="7ae64-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="7ae64-134">Таким образом они не влияют на производительность.</span><span class="sxs-lookup"><span data-stu-id="7ae64-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="7ae64-135">Единицы измерения, которые могут применяться к любому типу, не только типы с плавающей запятой; Однако только типы с плавающей запятой, подписана целочисленных типов и типов decimal поддерживают количества с измерениями.</span><span class="sxs-lookup"><span data-stu-id="7ae64-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="7ae64-136">Таким образом он имеет смысл только для использования единиц измерения с примитивными типами и статистическими выражениями, которые содержат эти примитивные типы.</span><span class="sxs-lookup"><span data-stu-id="7ae64-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="7ae64-137">Следующий пример иллюстрирует использование единиц измерения.</span><span class="sxs-lookup"><span data-stu-id="7ae64-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]
    
<span data-ttu-id="7ae64-138">В следующем примере кода показано, как преобразовать из безразмерное число с плавающей запятой в размерные значение с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="7ae64-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="7ae64-139">Вы только что умножить 1.0, применить размерность 1.0.</span><span class="sxs-lookup"><span data-stu-id="7ae64-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="7ae64-140">Абстрактно это можно представить в виде функции типа `degreesFahrenheit`.</span><span class="sxs-lookup"><span data-stu-id="7ae64-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="7ae64-141">Кроме того, при передаче размерные значения в функции, ожидающие безразмерные числа с плавающей запятой, необходимо исключить единицы измерения или привести к `float` с помощью `float` оператор.</span><span class="sxs-lookup"><span data-stu-id="7ae64-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="7ae64-142">В этом примере выполняется деление `1.0<degC>` для аргументов `printf` из-за `printf` ожидает безразмерные.</span><span class="sxs-lookup"><span data-stu-id="7ae64-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="7ae64-143">В следующем примере сеанса показаны выходные данные и входные данные этого кода.</span><span class="sxs-lookup"><span data-stu-id="7ae64-143">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="7ae64-144">Использование универсальных единиц</span><span class="sxs-lookup"><span data-stu-id="7ae64-144">Using Generic Units</span></span>
<span data-ttu-id="7ae64-145">Можно написать универсальных функций, которые работают на данные, которые имеют связанную единицу измерения.</span><span class="sxs-lookup"><span data-stu-id="7ae64-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="7ae64-146">Это делается путем указания типа вместе с универсальной единицей в качестве параметра типа, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="7ae64-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]
    
## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="7ae64-147">Создание типов статистических выражений с универсальными единицами</span><span class="sxs-lookup"><span data-stu-id="7ae64-147">Creating Aggregate Types with Generic Units</span></span>
<span data-ttu-id="7ae64-148">Следующий код показано, как создать тип статистических выражений, состоящий из отдельных значений с плавающей запятой с универсальными единицами.</span><span class="sxs-lookup"><span data-stu-id="7ae64-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="7ae64-149">Это позволяет создавать один тип должен быть создан, работает с множеством единиц.</span><span class="sxs-lookup"><span data-stu-id="7ae64-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="7ae64-150">Кроме того универсальные единицы повышают безопасность типа, гарантируя, что универсальный тип с одним набором единиц, тип которого отличается от одного универсального типа с другим набором значений.</span><span class="sxs-lookup"><span data-stu-id="7ae64-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="7ae64-151">Является основой этой технологии, `Measure` атрибут может применяться к параметру типа.</span><span class="sxs-lookup"><span data-stu-id="7ae64-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]
    
## <a name="units-at-runtime"></a><span data-ttu-id="7ae64-152">Единицы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="7ae64-152">Units at Runtime</span></span>
<span data-ttu-id="7ae64-153">Единицы измерения используются для проверки статических типов.</span><span class="sxs-lookup"><span data-stu-id="7ae64-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="7ae64-154">При компиляции значений с плавающей запятой единицы измерения исключаются, поэтому единицы будут потеряны во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7ae64-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="7ae64-155">Таким образом любые попытки реализовать функциональные возможности, основанные на проверке единиц времени выполнения невозможна.</span><span class="sxs-lookup"><span data-stu-id="7ae64-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="7ae64-156">Например, реализация `ToString` функцию для распечатки единиц невозможна.</span><span class="sxs-lookup"><span data-stu-id="7ae64-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>


## <a name="conversions"></a><span data-ttu-id="7ae64-157">Преобразования</span><span class="sxs-lookup"><span data-stu-id="7ae64-157">Conversions</span></span>
<span data-ttu-id="7ae64-158">Для преобразования типа, который содержит единицы (например, `float<'u>`) для типа, у которого нет единиц, можно использовать функцию стандартное преобразование.</span><span class="sxs-lookup"><span data-stu-id="7ae64-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="7ae64-159">Например, можно использовать `float` для преобразования `float` значение, которое не имеет единицы, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="7ae64-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="7ae64-160">Чтобы преобразовать значение, которое имеет единицы безразмерное значение, можно умножить значение 1 или 1,0, которое помечается с соответствующие единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="7ae64-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="7ae64-161">Однако для создания уровней взаимодействия, существуют некоторые явные функции, которые можно использовать для безразмерное значения преобразуются в значения с единицы.</span><span class="sxs-lookup"><span data-stu-id="7ae64-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="7ae64-162">Они находятся в [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) модуля.</span><span class="sxs-lookup"><span data-stu-id="7ae64-162">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="7ae64-163">Например, для преобразования из безразмерное `float` для `float<cm>`, используйте [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="7ae64-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]
    
## <a name="units-of-measure-in-the-f-power-pack"></a><span data-ttu-id="7ae64-164">Единицы измерения в F # Power Pack</span><span class="sxs-lookup"><span data-stu-id="7ae64-164">Units of Measure in the F# Power Pack</span></span>
<span data-ttu-id="7ae64-165">Библиотека модульных доступен в PowerPack F #.</span><span class="sxs-lookup"><span data-stu-id="7ae64-165">A unit library is available in the F# PowerPack.</span></span> <span data-ttu-id="7ae64-166">Она включает системы СИ и физические константы.</span><span class="sxs-lookup"><span data-stu-id="7ae64-166">The unit library includes SI units and physical constants.</span></span>


## <a name="see-also"></a><span data-ttu-id="7ae64-167">См. также</span><span class="sxs-lookup"><span data-stu-id="7ae64-167">See Also</span></span>
[<span data-ttu-id="7ae64-168">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="7ae64-168">F# Language Reference</span></span>](index.md)
