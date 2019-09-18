---
title: Новые возможности C# 8.0. Руководство по языку C#
description: Обзор новых функций, доступных в C# 8.0. В этой статье представлены возможности предварительной версии 5.
ms.date: 09/10/2019
ms.openlocfilehash: 141f7a2fa0bc5f6a2a253e196a218938dd4c170e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926529"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="b4036-104">Новые возможности C# 8.0</span><span class="sxs-lookup"><span data-stu-id="b4036-104">What's new in C# 8.0</span></span>

<span data-ttu-id="b4036-105">Для языка C# представлено множество улучшений, которые вы уже можете опробовать.</span><span class="sxs-lookup"><span data-stu-id="b4036-105">There are many enhancements to the C# language that you can try out already.</span></span>

- [<span data-ttu-id="b4036-106">Члены только для чтения</span><span class="sxs-lookup"><span data-stu-id="b4036-106">Readonly members</span></span>](#readonly-members)
- [<span data-ttu-id="b4036-107">Члены интерфейса по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b4036-107">Default interface members</span></span>](#default-interface-members)
- <span data-ttu-id="b4036-108">[Улучшения сопоставления шаблонов](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="b4036-108">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  - <span data-ttu-id="b4036-109">[выражения switch](#switch-expressions);</span><span class="sxs-lookup"><span data-stu-id="b4036-109">[Switch expressions](#switch-expressions)</span></span>
  - <span data-ttu-id="b4036-110">[шаблоны свойств](#property-patterns);</span><span class="sxs-lookup"><span data-stu-id="b4036-110">[Property patterns](#property-patterns)</span></span>
  - <span data-ttu-id="b4036-111">[шаблоны кортежей](#tuple-patterns);</span><span class="sxs-lookup"><span data-stu-id="b4036-111">[Tuple patterns](#tuple-patterns)</span></span>
  - <span data-ttu-id="b4036-112">[позиционные шаблоны](#positional-patterns).</span><span class="sxs-lookup"><span data-stu-id="b4036-112">[Positional patterns](#positional-patterns)</span></span>
- <span data-ttu-id="b4036-113">[Объявления using](#using-declarations).</span><span class="sxs-lookup"><span data-stu-id="b4036-113">[Using declarations](#using-declarations)</span></span>
- <span data-ttu-id="b4036-114">[Статические локальные функции](#static-local-functions).</span><span class="sxs-lookup"><span data-stu-id="b4036-114">[Static local functions](#static-local-functions)</span></span>
- <span data-ttu-id="b4036-115">[Удаляемые ссылочные структуры](#disposable-ref-structs).</span><span class="sxs-lookup"><span data-stu-id="b4036-115">[Disposable ref structs](#disposable-ref-structs)</span></span>
- [<span data-ttu-id="b4036-116">Ссылочные типы, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="b4036-116">Nullable reference types</span></span>](#nullable-reference-types)
- <span data-ttu-id="b4036-117">[Асинхронные потоки](#asynchronous-streams).</span><span class="sxs-lookup"><span data-stu-id="b4036-117">[Asynchronous streams](#asynchronous-streams)</span></span>
- <span data-ttu-id="b4036-118">[Индексы и диапазоны](#indices-and-ranges).</span><span class="sxs-lookup"><span data-stu-id="b4036-118">[Indices and ranges](#indices-and-ranges)</span></span>
- [<span data-ttu-id="b4036-119">Присваивание объединения со значением NULL</span><span class="sxs-lookup"><span data-stu-id="b4036-119">Null-coalescing assignment</span></span>](#null-coalescing-assignment)
- [<span data-ttu-id="b4036-120">Неуправляемые сконструированные типы</span><span class="sxs-lookup"><span data-stu-id="b4036-120">Unmanaged constructed types</span></span>](#unmanaged-constructed-types)
- [<span data-ttu-id="b4036-121">Улучшение интерполированных строк verbatim</span><span class="sxs-lookup"><span data-stu-id="b4036-121">Enhancement of interpolated verbatim strings</span></span>](#enhancement-of-interpolated-verbatim-strings)

> [!NOTE]
> <span data-ttu-id="b4036-122">Эта статья последний раз обновлялась для предварительной версии 5 C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="b4036-122">This article was last updated for C# 8.0 preview 5.</span></span>

<span data-ttu-id="b4036-123">В остальных разделах этой статьи кратко описываются эти возможности.</span><span class="sxs-lookup"><span data-stu-id="b4036-123">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="b4036-124">Здесь приведены ссылки на эти подробные руководства и обзоры (если они доступны).</span><span class="sxs-lookup"><span data-stu-id="b4036-124">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span> <span data-ttu-id="b4036-125">Эти функции можно изучить в своей среде с помощью глобального средства `dotnet try`:</span><span class="sxs-lookup"><span data-stu-id="b4036-125">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="b4036-126">Установите глобальное средство [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).</span><span class="sxs-lookup"><span data-stu-id="b4036-126">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="b4036-127">Клонируйте репозиторий [dotnet/try-samples](https://github.com/dotnet/try-samples).</span><span class="sxs-lookup"><span data-stu-id="b4036-127">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="b4036-128">Для репозитория *try-samples* установите в качестве текущего каталога подкаталог *csharp8*.</span><span class="sxs-lookup"><span data-stu-id="b4036-128">Set the current directory to the *csharp8* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="b4036-129">Запустите `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="b4036-129">Run `dotnet try`.</span></span>

## <a name="readonly-members"></a><span data-ttu-id="b4036-130">Члены только для чтения</span><span class="sxs-lookup"><span data-stu-id="b4036-130">Readonly members</span></span>

<span data-ttu-id="b4036-131">Модификатор `readonly` можно применить к любому члену структуры.</span><span class="sxs-lookup"><span data-stu-id="b4036-131">You can apply the `readonly` modifier to any member of a struct.</span></span> <span data-ttu-id="b4036-132">Он означает, что член не изменяет состояние.</span><span class="sxs-lookup"><span data-stu-id="b4036-132">It indicates that the member does not modify state.</span></span> <span data-ttu-id="b4036-133">Это более детализированный способ, чем применение модификатора `readonly` в объявлении `struct`.</span><span class="sxs-lookup"><span data-stu-id="b4036-133">It's more granular than applying the `readonly` modifier to a `struct` declaration.</span></span>  <span data-ttu-id="b4036-134">Рассмотрим следующую изменяемую структуру:</span><span class="sxs-lookup"><span data-stu-id="b4036-134">Consider the following mutable struct:</span></span>

```csharp
public struct Point
{
    public double X { get; set; }
    public double Y { get; set; }
    public double Distance => Math.Sqrt(X * X + Y * Y);

    public override string ToString() =>
        $"({X}, {Y}) is {Distance} from the origin";
}
```

<span data-ttu-id="b4036-135">Как и большинство структур, метод `ToString()` не изменяет состояние.</span><span class="sxs-lookup"><span data-stu-id="b4036-135">Like most structs, the `ToString()` method does not modify state.</span></span> <span data-ttu-id="b4036-136">Это можно указать, добавив модификатор `readonly` в объявление `ToString()`:</span><span class="sxs-lookup"><span data-stu-id="b4036-136">You could indicate that by adding the `readonly` modifier to the declaration of `ToString()`:</span></span>

```csharp
public readonly override string ToString() =>
    $"({X}, {Y}) is {Distance} from the origin";
```

<span data-ttu-id="b4036-137">Предыдущее изменение создает предупреждение компилятора, так как `ToString` обращается к свойству `Distance`, которое не помечено как `readonly`:</span><span class="sxs-lookup"><span data-stu-id="b4036-137">The preceding change generates a compiler warning, because `ToString` accesses the `Distance` property, which is not marked `readonly`:</span></span>

```console
warning CS8656: Call to non-readonly member 'Point.Distance.get' from a 'readonly' member results in an implicit copy of 'this'
```

<span data-ttu-id="b4036-138">Компилятор выдает предупреждение, когда ему требуется создать защитную копию.</span><span class="sxs-lookup"><span data-stu-id="b4036-138">The compiler warns you when it needs to create a defensive copy.</span></span>  <span data-ttu-id="b4036-139">Свойство `Distance` не изменяет состояние, поэтому вы можете устранить это предупреждение, добавив модификатор `readonly` в объявление:</span><span class="sxs-lookup"><span data-stu-id="b4036-139">The `Distance` property does not change state, so you can fix this warning by adding the `readonly` modifier to the declaration:</span></span>

```csharp
public readonly double Distance => Math.Sqrt(X * X + Y * Y);
```

<span data-ttu-id="b4036-140">Обратите внимание, что модификатор `readonly` необходим для свойства только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b4036-140">Notice that the `readonly` modifier is necessary on a read only property.</span></span> <span data-ttu-id="b4036-141">Компилятор не предполагает, что методы доступа `get` не изменяют состояние: `readonly` необходимо объявить явно.</span><span class="sxs-lookup"><span data-stu-id="b4036-141">The compiler doesn't assume `get` accessors do not modify state; you must declare `readonly` explicitly.</span></span> <span data-ttu-id="b4036-142">Компилятор применяет правило о том, что члены `readonly` не изменяют состояние.</span><span class="sxs-lookup"><span data-stu-id="b4036-142">The compiler does enforce the rule that `readonly` members do not modify state.</span></span> <span data-ttu-id="b4036-143">Следующий метод не будет компилироваться, если не удален модификатор `readonly`:</span><span class="sxs-lookup"><span data-stu-id="b4036-143">The following method will not compile unless you remove the `readonly` modifier:</span></span>

```csharp
public readonly void Translate(int xOffset, int yOffset)
{
    X += xOffset;
    Y += yOffset;
}
```

<span data-ttu-id="b4036-144">Эта функция позволяет указать намерение вашего проекта, чтобы компилятор мог применить его и выполнить оптимизацию на основе намерения.</span><span class="sxs-lookup"><span data-stu-id="b4036-144">This feature lets you specify your design intent so the compiler can enforce it, and make optimizations based on that intent.</span></span>

## <a name="default-interface-members"></a><span data-ttu-id="b4036-145">Члены интерфейса по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b4036-145">Default interface members</span></span>

<span data-ttu-id="b4036-146">Теперь вы можете добавлять члены в интерфейсы и предоставлять реализацию для этих членов.</span><span class="sxs-lookup"><span data-stu-id="b4036-146">You can now add members to interfaces and provide an implementation for those members.</span></span> <span data-ttu-id="b4036-147">Эта возможность языка позволяет разработчикам API добавлять методы в интерфейс в более поздних версиях, не нарушая исходный код или совместимость на уровне двоичного кода с существующими реализациями этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b4036-147">This language feature enables API authors to add methods to an interface in later versions without breaking source or binary compatibility with existing implementations of that interface.</span></span> <span data-ttu-id="b4036-148">Существующие реализации *наследуют* реализацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b4036-148">Existing implementations *inherit* the default implementation.</span></span> <span data-ttu-id="b4036-149">Эта функция также позволяет C# взаимодействовать с API-интерфейсами, предназначенными для Android или Swift, которые поддерживают аналогичные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="b4036-149">This feature also enables C# to interoperate with APIs that target Android or Swift, which support similar features.</span></span> <span data-ttu-id="b4036-150">Члены интерфейса по умолчанию также поддерживают сценарии, аналогичные функции языка "признаки".</span><span class="sxs-lookup"><span data-stu-id="b4036-150">Default interface members also enable scenarios similar to a "traits" language feature.</span></span>

<span data-ttu-id="b4036-151">Члены интерфейса по умолчанию влияют на многие сценарии и элементы языка.</span><span class="sxs-lookup"><span data-stu-id="b4036-151">Default interface members affects many scenarios and language elements.</span></span> <span data-ttu-id="b4036-152">В нашем первом учебнике рассматривается [изменение интерфейса с помощью реализаций по умолчанию](../tutorials/default-interface-members-versions.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-152">Our first tutorial covers [updating an interface with default implementations](../tutorials/default-interface-members-versions.md).</span></span> <span data-ttu-id="b4036-153">Выпуск общедоступных версий обновлений других руководств и справочника ожидается в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="b4036-153">Other tutorials and reference updates are coming in time for general release.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="b4036-154">Дополнительные шаблоны в нескольких расположениях</span><span class="sxs-lookup"><span data-stu-id="b4036-154">More patterns in more places</span></span>

<span data-ttu-id="b4036-155">Возможность **сопоставления шаблонов** позволяет работать с шаблонами в зависимости от формата в связанных, но различных типах данных.</span><span class="sxs-lookup"><span data-stu-id="b4036-155">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="b4036-156">В C# 7.0 появился синтаксис для шаблонов типа и шаблонов константы, использующий выражение [`is`](../language-reference/keywords/is.md) и инструкцию [`switch`](../language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-156">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="b4036-157">Эти функции представляют первые пробные шаги на пути к поддержке парадигм программирования, где данные и функции разделены.</span><span class="sxs-lookup"><span data-stu-id="b4036-157">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="b4036-158">По мере того как отрасль переходит на использование микрослужб и других облачных архитектур, необходимы также средства других языков.</span><span class="sxs-lookup"><span data-stu-id="b4036-158">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="b4036-159">В C# 8.0 расширены эти возможности, так что вы можете использовать дополнительные выражения шаблонов в нескольких расположениях в коде.</span><span class="sxs-lookup"><span data-stu-id="b4036-159">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="b4036-160">Учитывайте эти функции, когда данные и функциональные возможности представлены отдельно.</span><span class="sxs-lookup"><span data-stu-id="b4036-160">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="b4036-161">Рассмотрите возможность сопоставления шаблонов, когда алгоритмы зависят от фактов, отличных от типа среды выполнения объекта.</span><span class="sxs-lookup"><span data-stu-id="b4036-161">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="b4036-162">Эти методы предоставляют другой способ выражения проектов.</span><span class="sxs-lookup"><span data-stu-id="b4036-162">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="b4036-163">Помимо новых шаблонов в новых расположениях, в C# 8.0 добавлены **рекурсивные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="b4036-163">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="b4036-164">Результат выражения любого шаблона — это выражение языка.</span><span class="sxs-lookup"><span data-stu-id="b4036-164">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="b4036-165">Рекурсивный шаблон является просто выражением шаблона, которое применяется к результатам другого выражения шаблона.</span><span class="sxs-lookup"><span data-stu-id="b4036-165">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="b4036-166">Выражения switch</span><span class="sxs-lookup"><span data-stu-id="b4036-166">switch expressions</span></span>

<span data-ttu-id="b4036-167">Часто инструкция [`switch`](../language-reference/keywords/switch.md) возвращает значение в каждом из блоков `case`.</span><span class="sxs-lookup"><span data-stu-id="b4036-167">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="b4036-168">**Выражения switch** позволяет использовать более краткий синтаксис выражения.</span><span class="sxs-lookup"><span data-stu-id="b4036-168">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="b4036-169">В нем меньше повторяющихся ключевых слов `case` и `break`, а также меньше фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="b4036-169">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="b4036-170">Например, рассмотрим следующее перечисление, которое выводит список цветов радуги:</span><span class="sxs-lookup"><span data-stu-id="b4036-170">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Green,
    Blue,
    Indigo,
    Violet
}
```

<span data-ttu-id="b4036-171">Если для приложения определен тип `RGBColor`, который создается на основе компонентов `R`, `G` и `B`, вы можете преобразовать значение `Rainbow` в RGB-значение, используя следующий метод, содержащий выражение switch:</span><span class="sxs-lookup"><span data-stu-id="b4036-171">If your application defined an `RGBColor` type that is constructed from the `R`, `G` and `B` components, you could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Green  => new RGBColor(0x00, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

<span data-ttu-id="b4036-172">Здесь представлено несколько улучшений синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="b4036-172">There are several syntax improvements here:</span></span>

- <span data-ttu-id="b4036-173">Переменная расположена перед ключевым словом `switch`.</span><span class="sxs-lookup"><span data-stu-id="b4036-173">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="b4036-174">Другой порядок позволяет визуально легко отличить выражение switch от инструкции switch.</span><span class="sxs-lookup"><span data-stu-id="b4036-174">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="b4036-175">Элементы `case` и `:` заменяются на `=>`.</span><span class="sxs-lookup"><span data-stu-id="b4036-175">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="b4036-176">Это более лаконично и интуитивно понятно.</span><span class="sxs-lookup"><span data-stu-id="b4036-176">It's more concise and intuitive.</span></span>
- <span data-ttu-id="b4036-177">Случай `default` заменяется пустой переменной `_`.</span><span class="sxs-lookup"><span data-stu-id="b4036-177">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="b4036-178">Тексты являются выражениями, а не инструкциями.</span><span class="sxs-lookup"><span data-stu-id="b4036-178">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="b4036-179">Сравните это с эквивалентным кодом, где используется классическая инструкция `switch`:</span><span class="sxs-lookup"><span data-stu-id="b4036-179">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

```csharp
public static RGBColor FromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Green:
            return new RGBColor(0x00, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a><span data-ttu-id="b4036-180">Шаблоны свойств</span><span class="sxs-lookup"><span data-stu-id="b4036-180">Property patterns</span></span>

<span data-ttu-id="b4036-181">**Шаблон свойств** позволяет сопоставлять свойства исследуемого объекта.</span><span class="sxs-lookup"><span data-stu-id="b4036-181">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="b4036-182">Рассмотрим сайт электронной коммерции, на котором должен вычисляться налог с продаж по адресу покупателя.</span><span class="sxs-lookup"><span data-stu-id="b4036-182">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="b4036-183">Это вычисление не является основной задачей класса `Address`.</span><span class="sxs-lookup"><span data-stu-id="b4036-183">That computation is not a core responsibility of an `Address` class.</span></span> <span data-ttu-id="b4036-184">Оно меняется со временем и, скорее всего, чаще, чем изменения формата адреса.</span><span class="sxs-lookup"><span data-stu-id="b4036-184">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="b4036-185">Сумма налога с продаж зависит от свойства `State` адреса.</span><span class="sxs-lookup"><span data-stu-id="b4036-185">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="b4036-186">В следующем методе используется шаблон свойства для вычисления налога с продаж по адресу и цене:</span><span class="sxs-lookup"><span data-stu-id="b4036-186">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
```

<span data-ttu-id="b4036-187">При сопоставлении шаблонов создается сокращенный синтаксис для выражения этого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="b4036-187">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="b4036-188">Шаблоны кортежей</span><span class="sxs-lookup"><span data-stu-id="b4036-188">Tuple patterns</span></span>

<span data-ttu-id="b4036-189">Некоторые алгоритмы зависят от нескольких наборов входных данных.</span><span class="sxs-lookup"><span data-stu-id="b4036-189">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="b4036-190">**Шаблоны кортежей** позволяют переключаться между несколькими значениями, выраженными как [кортежи](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-190">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).</span></span>  <span data-ttu-id="b4036-191">В следующем примере кода показано выражение switch для игры *камень, ножницы, бумага*:</span><span class="sxs-lookup"><span data-stu-id="b4036-191">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
```

<span data-ttu-id="b4036-192">В сообщении указан победитель.</span><span class="sxs-lookup"><span data-stu-id="b4036-192">The messages indicate the winner.</span></span> <span data-ttu-id="b4036-193">В случае отклонения представляются три комбинации, ведущие к ничьей, или другие текстовые входные данные.</span><span class="sxs-lookup"><span data-stu-id="b4036-193">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="b4036-194">Позиционные шаблоны</span><span class="sxs-lookup"><span data-stu-id="b4036-194">Positional patterns</span></span>

<span data-ttu-id="b4036-195">Некоторые типы включают метод `Deconstruct`, свойства которого деконструируются на дискретные переменные.</span><span class="sxs-lookup"><span data-stu-id="b4036-195">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="b4036-196">Если метод `Deconstruct` доступен, можно использовать **позиционные шаблоны** для проверки свойств объекта и использовать эти свойства для шаблона.</span><span class="sxs-lookup"><span data-stu-id="b4036-196">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="b4036-197">Рассмотрим следующий класс `Point`, который содержит метод `Deconstruct` для создания дискретных переменных для `X` и `Y`:</span><span class="sxs-lookup"><span data-stu-id="b4036-197">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

<span data-ttu-id="b4036-198">Кроме того, нужно учитывать следующее перечисление, представляющее различные позиции квадранта:</span><span class="sxs-lookup"><span data-stu-id="b4036-198">Additionally, consider the following enum that represents various positions of a quadrant:</span></span>

```csharp
public enum Quadrant
{
    Unknown,
    Origin,
    One,
    Two,
    Three,
    Four,
    OnBorder
}
```

<span data-ttu-id="b4036-199">В следующем методе используется **позиционный шаблон** для извлечения значений `x` и `y`.</span><span class="sxs-lookup"><span data-stu-id="b4036-199">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="b4036-200">Затем используется предложение `when` для определения `Quadrant` точки:</span><span class="sxs-lookup"><span data-stu-id="b4036-200">Then, it uses a `when` clause to determine the `Quadrant` of the point:</span></span>

```csharp
static Quadrant GetQuadrant(Point point) => point switch
{
    (0, 0) => Quadrant.Origin,
    var (x, y) when x > 0 && y > 0 => Quadrant.One,
    var (x, y) when x < 0 && y > 0 => Quadrant.Two,
    var (x, y) when x < 0 && y < 0 => Quadrant.Three,
    var (x, y) when x > 0 && y < 0 => Quadrant.Four,
    var (_, _) => Quadrant.OnBorder,
    _ => Quadrant.Unknown
};
```

<span data-ttu-id="b4036-201">Шаблон пустой переменной в предыдущем операторе switch совпадает с выражением, если `x` или `y`, но не оба, имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="b4036-201">The discard pattern in the preceding switch matches when either `x` or `y` is 0, but not both.</span></span> <span data-ttu-id="b4036-202">Выражение switch должно создавать значение или исключение.</span><span class="sxs-lookup"><span data-stu-id="b4036-202">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="b4036-203">Если ни один из вариантов не совпадает, выражение switch создает исключение.</span><span class="sxs-lookup"><span data-stu-id="b4036-203">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="b4036-204">Компилятор создает предупреждение, если в выражении switch не охватываются все возможные случаи.</span><span class="sxs-lookup"><span data-stu-id="b4036-204">The compiler generates a warning for you if you do not cover all possible cases in your switch expression.</span></span>

<span data-ttu-id="b4036-205">Ознакомиться с методами сопоставления шаблонов можно в [этом подробном учебнике](../tutorials/pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-205">You can explore pattern matching techniques in this [advanced tutorial on pattern matching](../tutorials/pattern-matching.md).</span></span>

## <a name="using-declarations"></a><span data-ttu-id="b4036-206">Объявления using</span><span class="sxs-lookup"><span data-stu-id="b4036-206">using declarations</span></span>

<span data-ttu-id="b4036-207">**Объявление using** — это объявление переменной, которому предшествует ключевое слово `using`.</span><span class="sxs-lookup"><span data-stu-id="b4036-207">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="b4036-208">Оно сообщает компилятору, что объявляемая переменная должна быть удалена в конце области видимости.</span><span class="sxs-lookup"><span data-stu-id="b4036-208">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="b4036-209">Для примера рассмотрим следующий код, в котором записывается текстовый файл:</span><span class="sxs-lookup"><span data-stu-id="b4036-209">For example, consider the following code that writes a text file:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

<span data-ttu-id="b4036-210">В приведенном выше примере файл удаляется при достижении закрывающей фигурной скобки метода.</span><span class="sxs-lookup"><span data-stu-id="b4036-210">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="b4036-211">Это конец области, в котором объявляется `file`.</span><span class="sxs-lookup"><span data-stu-id="b4036-211">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="b4036-212">Приведенный выше код эквивалентен следующему коду, в котором используется классическая [инструкция using](../language-reference/keywords/using-statement.md):</span><span class="sxs-lookup"><span data-stu-id="b4036-212">The preceding code is equivalent to the following code that uses the classic [using statement](../language-reference/keywords/using-statement.md):</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

<span data-ttu-id="b4036-213">В приведенном выше примере файл удаляется при достижении закрывающей фигурной скобки, связанной с инструкцией `using`.</span><span class="sxs-lookup"><span data-stu-id="b4036-213">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="b4036-214">В обоих случаях компилятор создает вызов метода `Dispose()`.</span><span class="sxs-lookup"><span data-stu-id="b4036-214">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="b4036-215">Компилятор создает ошибку, если выражение в инструкции `using` нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="b4036-215">The compiler generates an error if the expression in the `using` statement is not disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="b4036-216">Статические локальные функции</span><span class="sxs-lookup"><span data-stu-id="b4036-216">Static local functions</span></span>

<span data-ttu-id="b4036-217">Теперь вы можете добавить модификатор `static` для локальных функций, чтобы убедиться, что локальная функция не захватывает (не ссылается на) какие-либо переменные из области видимости.</span><span class="sxs-lookup"><span data-stu-id="b4036-217">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="b4036-218">Это приводит к возникновению ошибки `CS8421`: "A static local function can't contain a reference to \<variable>" (Статическая локальная функция не может содержать ссылку на <переменная>).</span><span class="sxs-lookup"><span data-stu-id="b4036-218">Doing so generates `CS8421`, "A static local function can't contain a reference to \<variable>."</span></span> 

<span data-ttu-id="b4036-219">Рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="b4036-219">Consider the following code.</span></span> <span data-ttu-id="b4036-220">Локальная функция `LocalFunction` обращается к переменной `y`, объявленной в области видимости (метод `M`).</span><span class="sxs-lookup"><span data-stu-id="b4036-220">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="b4036-221">Таким образом `LocalFunction` не может объявляться с помощью модификатора `static`:</span><span class="sxs-lookup"><span data-stu-id="b4036-221">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="b4036-222">Следующий код содержит статическую локальную функцию.</span><span class="sxs-lookup"><span data-stu-id="b4036-222">The following code contains a static local function.</span></span> <span data-ttu-id="b4036-223">Она может быть статической, так как она не обращается ко всем переменным в области видимости:</span><span class="sxs-lookup"><span data-stu-id="b4036-223">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="b4036-224">Удаляемые ссылочные структуры</span><span class="sxs-lookup"><span data-stu-id="b4036-224">Disposable ref structs</span></span>

<span data-ttu-id="b4036-225">Объект `struct`, объявленный с помощью модификатора `ref`, не может реализовывать интерфейсы и поэтому не может реализовать <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="b4036-225">A `struct` declared with the `ref` modifier may not implement any interfaces and so cannot implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="b4036-226">Таким образом, чтобы объект `ref struct` можно было удалить, у него должен быть доступный метод `void Dispose()`.</span><span class="sxs-lookup"><span data-stu-id="b4036-226">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="b4036-227">Это также относится к объявлениям `readonly ref struct`.</span><span class="sxs-lookup"><span data-stu-id="b4036-227">This also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="b4036-228">Ссылочные типы, допускающие значение null</span><span class="sxs-lookup"><span data-stu-id="b4036-228">Nullable reference types</span></span>

<span data-ttu-id="b4036-229">Внутри контекста заметок, допускающих значение null, любая переменная ссылочного типа считается переменной **ссылочного типа, не допускающего значения null**.</span><span class="sxs-lookup"><span data-stu-id="b4036-229">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="b4036-230">Если вы хотите указать, что переменная может принимать значение null, необходимо добавить к имени типа `?`, чтобы объявить переменную как переменную **ссылочного типа, допускающего значения null**.</span><span class="sxs-lookup"><span data-stu-id="b4036-230">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="b4036-231">Для ссылочных типов, не допускающих значение null, компилятор использует анализ потока, чтобы убедиться, что локальные переменные инициализируются в значение, отличное от null, при объявлении.</span><span class="sxs-lookup"><span data-stu-id="b4036-231">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="b4036-232">Поля должны быть инициализированы во время построения.</span><span class="sxs-lookup"><span data-stu-id="b4036-232">Fields must be initialized during construction.</span></span> <span data-ttu-id="b4036-233">Компилятор создает предупреждение, если переменная не задана с помощью вызова любого из доступных конструкторов или с помощью инициализатора.</span><span class="sxs-lookup"><span data-stu-id="b4036-233">The compiler generates a warning if the variable is not set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="b4036-234">Кроме того, ссылочным типам, не допускающим значение null, нельзя задать значение, которое может быть null.</span><span class="sxs-lookup"><span data-stu-id="b4036-234">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="b4036-235">Ссылочные типы, допускающие значение null, не проверяются на предмет того, назначено ли им значение null или получили ли они его после инициализации.</span><span class="sxs-lookup"><span data-stu-id="b4036-235">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="b4036-236">Тем не менее, компилятор использует анализ потока, чтобы убедиться, что любая переменная ссылочного типа, допускающего значение null, проверяется на наличие значения null, прежде чем обратиться к ней или назначить ей ссылочный тип, не допускающий значение null.</span><span class="sxs-lookup"><span data-stu-id="b4036-236">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="b4036-237">Дополнительные сведения о функции см. в обзоре [ссылочных типов, допускающих значение null](../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-237">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="b4036-238">Попробуйте самостоятельно применить эту возможность в новом приложении в этом [руководстве по ссылочным типам, допускающим значение null](../tutorials/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-238">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="b4036-239">Дополнительные сведения о шагах переноса существующей базы кода для использования ссылочных типов, допускающих значение null, см. в [этом руководстве](../tutorials/upgrade-to-nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-239">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="b4036-240">Асинхронные потоки</span><span class="sxs-lookup"><span data-stu-id="b4036-240">Asynchronous streams</span></span>

<span data-ttu-id="b4036-241">Начиная с C# версии 8.0 можно создавать и использовать потоки асинхронно.</span><span class="sxs-lookup"><span data-stu-id="b4036-241">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="b4036-242">В методе, который возвращает асинхронный поток, есть три свойства:</span><span class="sxs-lookup"><span data-stu-id="b4036-242">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="b4036-243">Он объявлен с помощью модификатора `async`.</span><span class="sxs-lookup"><span data-stu-id="b4036-243">It's declared with the `async` modifier.</span></span>
1. <span data-ttu-id="b4036-244">Он возвращает интерфейс <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="b4036-244">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="b4036-245">Метод содержит инструкции `yield return` для возвращения последовательных элементов в асинхронном потоке.</span><span class="sxs-lookup"><span data-stu-id="b4036-245">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="b4036-246">Для использования асинхронного потока требуется добавить ключевое слово `await` перед ключевым словом `foreach` при перечислении элементов потока.</span><span class="sxs-lookup"><span data-stu-id="b4036-246">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="b4036-247">Для добавления ключевого слова `await` требуется, чтобы метод, который перечисляет асинхронный поток, был объявлен с помощью модификатора `async` и возвращал тип, допустимый для метода `async`.</span><span class="sxs-lookup"><span data-stu-id="b4036-247">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="b4036-248">Обычно это означает возвращение структуры <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="b4036-248">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="b4036-249">Это также может быть структура <xref:System.Threading.Tasks.ValueTask> или <xref:System.Threading.Tasks.ValueTask%601>.</span><span class="sxs-lookup"><span data-stu-id="b4036-249">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="b4036-250">Метод может использовать и создавать асинхронный поток. Это означает, что будет возвращен интерфейс <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="b4036-250">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="b4036-251">Следующий код создает последовательность чисел от 0 до 19 с интервалом 100 мс между генерированием каждого числа:</span><span class="sxs-lookup"><span data-stu-id="b4036-251">The following code generates a sequence from 0 to 19, waiting 100 ms between generating each number:</span></span>

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

<span data-ttu-id="b4036-252">Вы бы перечислили последовательность с использованием инструкции `await foreach`:</span><span class="sxs-lookup"><span data-stu-id="b4036-252">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="b4036-253">Вы можете попробовать асинхронные потоки самостоятельно в нашем руководстве по [созданию и использованию асинхронных потоков](../tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-253">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="b4036-254">Индексы и диапазоны</span><span class="sxs-lookup"><span data-stu-id="b4036-254">Indices and ranges</span></span>

<span data-ttu-id="b4036-255">Диапазоны и индексы обеспечивают лаконичный синтаксис для указания поддиапазонов массива: <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="b4036-255">Ranges and indices provide a succinct syntax for specifying subranges in an array, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span>

<span data-ttu-id="b4036-256">Поддержка языков опирается на два новых типа и два новых оператора:</span><span class="sxs-lookup"><span data-stu-id="b4036-256">This language support relies on two new types, and two new operators:</span></span>

- <span data-ttu-id="b4036-257"><xref:System.Index?displayProperty=nameWithType> представляет индекс в последовательности.</span><span class="sxs-lookup"><span data-stu-id="b4036-257"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="b4036-258">Оператор `^`, который указывает, что индекс указан относительно конца последовательности.</span><span class="sxs-lookup"><span data-stu-id="b4036-258">The `^` operator, which specifies that an index is relative to the end of the sequence.</span></span>
- <span data-ttu-id="b4036-259"><xref:System.Range?displayProperty=nameWithType> представляет вложенный диапазон последовательности.</span><span class="sxs-lookup"><span data-stu-id="b4036-259"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="b4036-260">Оператор диапазона (`..`), который задает начало и конец диапазона в качестве своих операндов.</span><span class="sxs-lookup"><span data-stu-id="b4036-260">The Range operator (`..`), which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="b4036-261">Начнем с правил для использования в индексах.</span><span class="sxs-lookup"><span data-stu-id="b4036-261">Let's start with the rules for indexes.</span></span> <span data-ttu-id="b4036-262">Рассмотрим массив `sequence`.</span><span class="sxs-lookup"><span data-stu-id="b4036-262">Consider an array `sequence`.</span></span> <span data-ttu-id="b4036-263">Индекс `0` совпадает с `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="b4036-263">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="b4036-264">Индекс `^0` совпадает с `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="b4036-264">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="b4036-265">Обратите внимание, что `sequence[^0]` создает исключение так же, как и `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="b4036-265">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="b4036-266">Для любого числа `n` индекс `^n` совпадает с `sequence.Length - n`.</span><span class="sxs-lookup"><span data-stu-id="b4036-266">For any number `n`, the index `^n` is the same as `sequence.Length - n`.</span></span>

<span data-ttu-id="b4036-267">Диапазон указывает *начало* и *конец* диапазона.</span><span class="sxs-lookup"><span data-stu-id="b4036-267">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="b4036-268">Начало диапазона включается, а окончание — исключается, то есть *start* входит в диапазон, а *end* — не входит.</span><span class="sxs-lookup"><span data-stu-id="b4036-268">The start of the range is inclusive, but the end of the range is exclusive, meaning the *start* is included in the range but the *end* is not included in the range.</span></span> <span data-ttu-id="b4036-269">Диапазон `[0..^0]` представляет весь диапазон так же, как `[0..sequence.Length]` представляет весь диапазон.</span><span class="sxs-lookup"><span data-stu-id="b4036-269">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="b4036-270">Рассмотрим несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="b4036-270">Let's look at a few examples.</span></span> <span data-ttu-id="b4036-271">Обратите внимание на следующий массив, который помечен индексом от начала и от конца:</span><span class="sxs-lookup"><span data-stu-id="b4036-271">Consider the following array, annotated with its index from the start and from the end:</span></span>

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="b4036-272">Вы можете получить последнее слово с помощью индекса `^1`:</span><span class="sxs-lookup"><span data-stu-id="b4036-272">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="b4036-273">Следующий код создает поддиапазон со словами "quick", "brown" и "fox".</span><span class="sxs-lookup"><span data-stu-id="b4036-273">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="b4036-274">Он включает в себя элементы от `words[1]` до `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="b4036-274">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="b4036-275">Элемент `words[4]` находится вне диапазона.</span><span class="sxs-lookup"><span data-stu-id="b4036-275">The element `words[4]` is not in the range.</span></span>

```csharp
var quickBrownFox = words[1..4];
```

<span data-ttu-id="b4036-276">Следующий код создает поддиапазон со словами "lazy" и "dog".</span><span class="sxs-lookup"><span data-stu-id="b4036-276">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="b4036-277">Он включает элементы `words[^2]` и `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="b4036-277">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="b4036-278">Конечный индекс `words[^0]` не включен:</span><span class="sxs-lookup"><span data-stu-id="b4036-278">The end index `words[^0]` is not included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="b4036-279">В следующих примерах создаются диапазоны, которые должны быть открыты для начала, конца или в обоих случаях:</span><span class="sxs-lookup"><span data-stu-id="b4036-279">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the", "lazy" and "dog"
```

<span data-ttu-id="b4036-280">Вы также можете объявить диапазоны как переменные:</span><span class="sxs-lookup"><span data-stu-id="b4036-280">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="b4036-281">Затем вы можете использовать диапазон внутри символов `[` и `]`:</span><span class="sxs-lookup"><span data-stu-id="b4036-281">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```

<span data-ttu-id="b4036-282">Вы можете изучить сведения об индексах и диапазонах адресов в руководстве [Индексы и диапазоны](../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-282">You can explore more about indices and ranges in the tutorial on [indices and ranges](../tutorials/ranges-indexes.md).</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="b4036-283">Присваивание объединения со значением NULL</span><span class="sxs-lookup"><span data-stu-id="b4036-283">Null-coalescing assignment</span></span>

<span data-ttu-id="b4036-284">В C# 8.0 появился оператор присваивания объединения со значением NULL `??=`.</span><span class="sxs-lookup"><span data-stu-id="b4036-284">C# 8.0 introduces the null-coalescing assignment operator `??=`.</span></span> <span data-ttu-id="b4036-285">Оператор `??=` можно использовать для присваивания значения правого операнда левому операнду только в том случае, если левый операнд принимает значение `null`.</span><span class="sxs-lookup"><span data-stu-id="b4036-285">You can use the `??=` operator to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span>

```csharp
List<int> numbers = null;
int? i = null;

numbers ??= new List<int>();
numbers.Add(i ??= 17);
numbers.Add(i ??= 20);

Console.WriteLine(string.Join(' ', numbers));  // output: 17 17
Console.WriteLine(i);  // output: 17
```

<span data-ttu-id="b4036-286">Дополнительные сведения см. в статье [Операторы ?? и ??=](../language-reference/operators/null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-286">For more information, see the [?? and ??= operators](../language-reference/operators/null-coalescing-operator.md) article.</span></span>

## <a name="unmanaged-constructed-types"></a><span data-ttu-id="b4036-287">Неуправляемые сконструированные типы</span><span class="sxs-lookup"><span data-stu-id="b4036-287">Unmanaged constructed types</span></span>

<span data-ttu-id="b4036-288">В C# 7.3 и более ранних версиях сконструированный тип (тип, содержащий по крайней мере один аргумент типа) не может быть [неуправляемым типом](../language-reference/builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-288">In C# 7.3 and earlier, a constructed type (a type that includes at least one type argument) cannot be an [unmanaged type](../language-reference/builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="b4036-289">Начиная с C# 8.0, сконструированный тип значения является неуправляемым, если он содержит поля исключительно неуправляемых типов.</span><span class="sxs-lookup"><span data-stu-id="b4036-289">Starting with C# 8.0, a constructed value type is unmanaged if it contains fields of unmanaged types only.</span></span>

<span data-ttu-id="b4036-290">Например, при наличии следующего определения универсального типа `Coords<T>`:</span><span class="sxs-lookup"><span data-stu-id="b4036-290">For example, given the following definition of the generic `Coords<T>` type:</span></span>

```csharp
public struct Coords<T>
{
    public T X;
    public T Y;
}
```

<span data-ttu-id="b4036-291">тип `Coords<int>` является неуправляемым в C# 8.0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="b4036-291">the `Coords<int>` type is an unmanaged type in C# 8.0 and later.</span></span> <span data-ttu-id="b4036-292">Как и для любого неуправляемого типа, вы можете создать указатель на переменную этого типа или [выделить блок памяти в стеке](../language-reference/operators/stackalloc.md) для экземпляров этого типа:</span><span class="sxs-lookup"><span data-stu-id="b4036-292">Like for any unmanaged type, you can create a pointer to a variable of this type or [allocate a block of memory on the stack](../language-reference/operators/stackalloc.md) for instances of this type:</span></span>

```csharp
Span<Coords<int>> coordinates = stackalloc[]
{
    new Coords<int> { X = 0, Y = 0 },
    new Coords<int> { X = 0, Y = 3 },
    new Coords<int> { X = 4, Y = 0 }
};
```

<span data-ttu-id="b4036-293">Дополнительные сведения см. в разделе [Неуправляемые типы](../language-reference/builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="b4036-293">For more information, see [Unmanaged types](../language-reference/builtin-types/unmanaged-types.md).</span></span>

## <a name="enhancement-of-interpolated-verbatim-strings"></a><span data-ttu-id="b4036-294">Улучшение интерполированных строк verbatim</span><span class="sxs-lookup"><span data-stu-id="b4036-294">Enhancement of interpolated verbatim strings</span></span>

<span data-ttu-id="b4036-295">Порядок маркеров `$` и `@` в [интерполированных ](../language-reference/tokens/interpolated.md) строках verbatim может быть любым: и `$@"..."`, и `@$"..."` являются допустимыми интерполированными строками verbatim.</span><span class="sxs-lookup"><span data-stu-id="b4036-295">Order of the `$` and `@` tokens in [interpolated](../language-reference/tokens/interpolated.md) verbatim strings can be any: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings.</span></span> <span data-ttu-id="b4036-296">В более ранних версиях C# маркер`$` должен располагаться перед маркером `@`.</span><span class="sxs-lookup"><span data-stu-id="b4036-296">In earlier C# versions, the `$` token must appear before the `@` token.</span></span>
