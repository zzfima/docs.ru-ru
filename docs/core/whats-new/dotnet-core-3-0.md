---
title: Новые возможности .NET Core 3.0
description: Дополнительные сведения о новых возможностях .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/31/2018
ms.openlocfilehash: 89264098ed17b398c83bc2dcddd98d9d8fc958f7
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679740"
---
# <a name="whats-new-in-net-core-30-preview-2"></a><span data-ttu-id="b6fad-103">Новые возможности .NET Core 3.0 (предварительная версия 2)</span><span class="sxs-lookup"><span data-stu-id="b6fad-103">What's new in .NET Core 3.0 (Preview 2)</span></span>

<span data-ttu-id="b6fad-104">В этой статье описываются новые возможности в .NET Core 3.0 (предварительная версия 2).</span><span class="sxs-lookup"><span data-stu-id="b6fad-104">This article describes what is new in .NET Core 3.0 (preview 2).</span></span> <span data-ttu-id="b6fad-105">Одно из основных усовершенствований — это поддержка классических приложений Windows (только Windows).</span><span class="sxs-lookup"><span data-stu-id="b6fad-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="b6fad-106">Используя пакет SDK для .NET Core 3.0 под названием Windows Desktop, вы можете перенести приложения Windows Forms и Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="b6fad-106">By utilizing a .NET Core 3.0 SDK component called Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="b6fad-107">Следует уточнить, что компонент Windows Desktop поддерживается и включен только в Windows.</span><span class="sxs-lookup"><span data-stu-id="b6fad-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="b6fad-108">Дополнительные сведения см. в разделе [Классические приложения Windows](#windows-desktop), приведенном ниже.</span><span class="sxs-lookup"><span data-stu-id="b6fad-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="b6fad-109">В .NET Core 3.0 добавлена поддержка C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="b6fad-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="b6fad-110">[Скачайте и начните работу с .NET Core 3.0 (предварительная версия 2)](https://aka.ms/netcore3download) прямо сейчас в Windows, Mac и Linux.</span><span class="sxs-lookup"><span data-stu-id="b6fad-110">[Download and get started with .NET Core 3.0 Preview 2](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="b6fad-111">Полное описание выпуска .NET Core 3.0 (предварительная версия 2) см. [здесь](https://aka.ms/netcore3releasenotes).</span><span class="sxs-lookup"><span data-stu-id="b6fad-111">You can see complete details of the release in the [.NET Core 3.0 Preview 2 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="b6fad-112">Ддля получения дополнительных сведений о новых возможностях в каждой версии см. следующие объявления:</span><span class="sxs-lookup"><span data-stu-id="b6fad-112">For more information about what was released with each version, see the following announcements:</span></span>

- [<span data-ttu-id="b6fad-113">Объявление о .NET Core 3.0, предварительная версия 1</span><span class="sxs-lookup"><span data-stu-id="b6fad-113">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)
- [<span data-ttu-id="b6fad-114">Объявление о .NET Core 3.0, предварительная версия 2</span><span class="sxs-lookup"><span data-stu-id="b6fad-114">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)

## <a name="c-8"></a><span data-ttu-id="b6fad-115">C# 8</span><span class="sxs-lookup"><span data-stu-id="b6fad-115">C# 8</span></span>

<span data-ttu-id="b6fad-116">.NET Core 3.0 поддерживает C# 8, а начиная с .NET Core 3.0, предварительная версия 2, поддерживает эти новые функции.</span><span class="sxs-lookup"><span data-stu-id="b6fad-116">.NET Core 3.0 supports C# 8, and as of .NET Core 3.0 Preview 2, supports these new features.</span></span> <span data-ttu-id="b6fad-117">Дополнительные сведения о функциях C# 8.0 см. в следующих записях блога:</span><span class="sxs-lookup"><span data-stu-id="b6fad-117">For more information about C# 8.0 features, see the following blog posts:</span></span>

- [<span data-ttu-id="b6fad-118">Расширенные возможности шаблонов в C# 8.0</span><span class="sxs-lookup"><span data-stu-id="b6fad-118">Do more with patterns in C# 8.0</span></span>](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/)
- [<span data-ttu-id="b6fad-119">C# 8.0 для ускорения работы</span><span class="sxs-lookup"><span data-stu-id="b6fad-119">Take C# 8.0 for a spin</span></span>](https://devblogs.microsoft.com/dotnet/take-c-8-0-for-a-spin/)
- [<span data-ttu-id="b6fad-120">Сборка на C# 8.0</span><span class="sxs-lookup"><span data-stu-id="b6fad-120">Building C# 8.0</span></span>](https://devblogs.microsoft.com/dotnet/building-c-8-0/)


### <a name="ranges-and-indices"></a><span data-ttu-id="b6fad-121">Диапазоны и индексы</span><span class="sxs-lookup"><span data-stu-id="b6fad-121">Ranges and indices</span></span>

<span data-ttu-id="b6fad-122">Новый тип `Index` можно использовать для индексирования.</span><span class="sxs-lookup"><span data-stu-id="b6fad-122">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="b6fad-123">Вы можете создать с помощью `int` индекс, который отсчитывается с начала, а с помощью оператора `^` префикса (C#) индекс, который отсчитывается с конца:</span><span class="sxs-lookup"><span data-stu-id="b6fad-123">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="b6fad-124">Кроме того, есть тип `Range`, который состоит из двух значений `Index` (одно для начала и одно для конца) и который можно написать с помощью выражения диапазона `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="b6fad-124">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="b6fad-125">Затем можно индексировать с помощью `Range` для создания среза:</span><span class="sxs-lookup"><span data-stu-id="b6fad-125">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

### <a name="async-streams"></a><span data-ttu-id="b6fad-126">Асинхронные потоки</span><span class="sxs-lookup"><span data-stu-id="b6fad-126">Async streams</span></span>

<span data-ttu-id="b6fad-127">Тип `IAsyncEnumerable<T>` — это новая асинхронная версия `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-127">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="b6fad-128">Язык позволяет выполнить действие `await foreach` с этими объектами `IAsyncEnumerable<T>`, чтобы использовать их элементы, и действие `yield return` по отношению к ним, чтобы создать элементы.</span><span class="sxs-lookup"><span data-stu-id="b6fad-128">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="b6fad-129">В приведенном ниже примере демонстрируется создание и применение асинхронных потоков.</span><span class="sxs-lookup"><span data-stu-id="b6fad-129">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="b6fad-130">Инструкция `foreach` является асинхронной и использует `yield return`, чтобы создать асинхронные потоки для вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="b6fad-130">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="b6fad-131">Этот шаблон (с использованием `yield return`) является рекомендуемой моделью для создания асинхронных потоков.</span><span class="sxs-lookup"><span data-stu-id="b6fad-131">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

<span data-ttu-id="b6fad-132">Помимо возможности `await foreach` вы также можете создать асинхронные итераторы, например, итератор, который возвращает `IAsyncEnumerable/IAsyncEnumerator`, для которого можно применить `await` и `yield`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-132">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="b6fad-133">Для объектов, которые необходимо удалить, можно использовать `IAsyncDisposable`, который реализовывают различные типы BCL, такие как `Stream` и `Timer`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-133">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

>[!NOTE]
><span data-ttu-id="b6fad-134">Вам потребуется .NET Core 3.0, предварительная версия 2, для использования асинхронных потоков, если вы хотите выполнять разработку с помощью Visual Studio 2019, предварительная версия 2, или последней предварительной версии [расширения C# для Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5).</span><span class="sxs-lookup"><span data-stu-id="b6fad-134">You need .NET Core 3.0 Preview 2 to use async streams if you want to develop with either Visual Studio 2019 Preview 2 or the latest preview of the [C# extension for Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5).</span></span> <span data-ttu-id="b6fad-135">Если вы используете .NET Core 3.0, предварительная версия 2, из командной строки, все будет работать правильно.</span><span class="sxs-lookup"><span data-stu-id="b6fad-135">If you are using .NET Core 3.0 Preview 2 at the command line, then everything will work as expected.</span></span>

### <a name="using-declarations"></a><span data-ttu-id="b6fad-136">Использование объявлений</span><span class="sxs-lookup"><span data-stu-id="b6fad-136">Using Declarations</span></span>

<span data-ttu-id="b6fad-137">*Объявления using* — это новый способ обеспечить правильную ликвидацию объекта.</span><span class="sxs-lookup"><span data-stu-id="b6fad-137">*Using declarations* are a new way to ensure your object is properly disposed.</span></span> <span data-ttu-id="b6fad-138">*Объявление using* поддерживает активность объекта, пока он остается в области.</span><span class="sxs-lookup"><span data-stu-id="b6fad-138">A *using declaration* keeps the object alive while it is still in scope.</span></span> <span data-ttu-id="b6fad-139">Когда объект выходит за пределы области, он автоматически удаляется.</span><span class="sxs-lookup"><span data-stu-id="b6fad-139">Once the object becomes out of scope, it is automatically disposed.</span></span> <span data-ttu-id="b6fad-140">Это позволяет сократить количество вложенных *инструкций using* и сделать код чище.</span><span class="sxs-lookup"><span data-stu-id="b6fad-140">This will reduce nested *using statements* and make your code cleaner.</span></span>

```csharp
static void Main(string[] args)
{
    using var options = Parse(args);
    if (options["verbose"]) { WriteLine("Logging..."); }

} // options disposed here
```

### <a name="switch-expressions"></a><span data-ttu-id="b6fad-141">Выражения switch</span><span class="sxs-lookup"><span data-stu-id="b6fad-141">Switch Expressions</span></span>

<span data-ttu-id="b6fad-142">*Выражения switch* — это более аккуратный способ передать *оператор switch*, но, так как это выражение, оно возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="b6fad-142">*Switch expressions* are a cleaner way of doing a *switch statement* but, since it's an expression, returns a value.</span></span> <span data-ttu-id="b6fad-143">*Выражения switch* также полностью интегрированы с сопоставлением шаблонов и используют шаблон пустой переменной `_`, чтобы представить значение `default`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-143">*Switch expressions* are also fully integrated with pattern matching, and use the discard pattern, `_`, to represent the `default` value.</span></span>

<span data-ttu-id="b6fad-144">Синтаксис *выражения switch* показан в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b6fad-144">You can see the syntax for *switch expressions* in the following example:</span></span>

```csharp
static string Display(object o) => o switch
{
    Point { X: 0, Y: 0 }         => "origin",
    Point { X: var x, Y: var y } => $"({x}, {y})",
    _                            => "unknown"
};
```

<span data-ttu-id="b6fad-145">В этом примере важны два шаблона.</span><span class="sxs-lookup"><span data-stu-id="b6fad-145">There are two patterns at play in this example.</span></span> <span data-ttu-id="b6fad-146">`o` сначала сопоставляется с *типом шаблона* `Point`, а затем с *шаблоном свойств* внутри *{фигурных скобок}*.</span><span class="sxs-lookup"><span data-stu-id="b6fad-146">`o` first matches with the `Point` *type pattern* and then with the *property pattern* inside the *{curly braces}*.</span></span> <span data-ttu-id="b6fad-147">`_` описывает `discard pattern`, который является аналогом `default` для *операторов switch*.</span><span class="sxs-lookup"><span data-stu-id="b6fad-147">The `_` describes the `discard pattern`, which is the same as `default` for *switch statements*.</span></span>

<span data-ttu-id="b6fad-148">Шаблоны позволяют писать декларативный код, который выражает ваши намерения, а не процедурный код, реализующий для них тесты.</span><span class="sxs-lookup"><span data-stu-id="b6fad-148">Patterns enable you to write declarative code that captures your intent instead of procedural code that implements tests for it.</span></span> <span data-ttu-id="b6fad-149">Компилятор отвечает за реализацию этого скучного процедурного кода и всегда делает это правильно.</span><span class="sxs-lookup"><span data-stu-id="b6fad-149">The compiler becomes responsible for implementing that boring procedural code and is guaranteed to always do it correctly.</span></span>

<span data-ttu-id="b6fad-150">По-прежнему будут происходить ситуации, к которым *операторы switch* подходят лучше, чем *выражения switch*, и шаблоны могут использоваться в обоих стилях синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="b6fad-150">There will still be cases where *switch statements* will be a better choice than *switch expressions* and patterns can be used with both syntax styles.</span></span>

<span data-ttu-id="b6fad-151">Дополнительные сведения см. в разделе [Расширенные возможности шаблонов в C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/).</span><span class="sxs-lookup"><span data-stu-id="b6fad-151">For more information, see [Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="b6fad-152">Усовершенствования чисел с плавающей запятой по IEEE</span><span class="sxs-lookup"><span data-stu-id="b6fad-152">IEEE Floating-point improvements</span></span>

<span data-ttu-id="b6fad-153">API плавающей запятой сейчас обновляются, чтобы соответствовать [редакции IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span><span class="sxs-lookup"><span data-stu-id="b6fad-153">Floating point APIs are in the process of being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="b6fad-154">Цель этих изменений — предоставлять все обязательные операции и гарантировать, что их поведение будет соответствовать спецификации IEEE.</span><span class="sxs-lookup"><span data-stu-id="b6fad-154">The goal of these changes is to expose all "required" operations and ensure that they are behaviorally compliant with the IEEE spec.</span></span>

<span data-ttu-id="b6fad-155">Исправления синтаксического анализа и форматирования:</span><span class="sxs-lookup"><span data-stu-id="b6fad-155">Parsing and formatting fixes:</span></span>

* <span data-ttu-id="b6fad-156">Правильный анализ и округление входных данных любой длины.</span><span class="sxs-lookup"><span data-stu-id="b6fad-156">Correctly parse and round inputs of any length.</span></span>
* <span data-ttu-id="b6fad-157">Правильный анализ и форматирование отрицательного нуля.</span><span class="sxs-lookup"><span data-stu-id="b6fad-157">Correctly parse and format negative zero.</span></span>
* <span data-ttu-id="b6fad-158">Правильный анализ знака бесконечности, а не чисел с помощью проверки без учета регистра и допущения необязательного `+` в начале, где это применимо.</span><span class="sxs-lookup"><span data-stu-id="b6fad-158">Correctly parse Infinity and NaN by performing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="b6fad-159">Новые математические API-интерфейсы:</span><span class="sxs-lookup"><span data-stu-id="b6fad-159">New Math APIs have:</span></span>

* `BitIncrement/BitDecrement`\
<span data-ttu-id="b6fad-160">Соответствует операциям IEEE `nextUp` и `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-160">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="b6fad-161">Они возвращают наименьшее число с плавающей запятой, которое может быть больше или меньше входных данных (соответственно).</span><span class="sxs-lookup"><span data-stu-id="b6fad-161">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="b6fad-162">Например, `Math.BitIncrement(0.0)` вернет `double.Epsilon`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-162">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

* `MaxMagnitude/MinMagnitude`\
<span data-ttu-id="b6fad-163">Соответствуют операциям IEEE `maxNumMag` и `minNumMag`. Они возвращают значение, которое будет больше или меньше из двух величин (соответственно).</span><span class="sxs-lookup"><span data-stu-id="b6fad-163">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="b6fad-164">Например, `Math.MaxMagnitude(2.0, -3.0)` вернет `-3.0`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-164">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

* `ILogB`\
<span data-ttu-id="b6fad-165">Соответствует операции IEEE `logB`, которая возвращает целочисленное значение. Она возвращает целочисленный логарифм по основанию 2 входного параметра.</span><span class="sxs-lookup"><span data-stu-id="b6fad-165">Corresponds to the `logB` IEEE operation which returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="b6fad-166">Это фактически то же, что `floor(log2(x))`, но с минимальными погрешностями округления.</span><span class="sxs-lookup"><span data-stu-id="b6fad-166">This is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

* `ScaleB`\
<span data-ttu-id="b6fad-167">Соответствует операции IEEE `scaleB`, которая принимает целочисленное значение. Возвращает `x * pow(2, n)`, но выполняется с минимальными погрешностями округления.</span><span class="sxs-lookup"><span data-stu-id="b6fad-167">Corresponds to the `scaleB` IEEE operation which takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

* `Log2`\
<span data-ttu-id="b6fad-168">Соответствует операции IEEE `log2`. Возвращает логарифм по основанию 2.</span><span class="sxs-lookup"><span data-stu-id="b6fad-168">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="b6fad-169">Сводит к минимуму погрешность округления.</span><span class="sxs-lookup"><span data-stu-id="b6fad-169">It minimizes rounding error.</span></span>

* `FusedMultiplyAdd`\
<span data-ttu-id="b6fad-170">Соответствует операции IEEE `fma`. Выполняет умножение и сложение.</span><span class="sxs-lookup"><span data-stu-id="b6fad-170">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="b6fad-171">То есть он выполняет `(x * y) + z` как одну операцию, тем самым сводя к минимуму погрешность округления.</span><span class="sxs-lookup"><span data-stu-id="b6fad-171">That is, it does `(x * y) + z` as a single operation, there-by minimizing the rounding error.</span></span> <span data-ttu-id="b6fad-172">Пример — `FusedMultiplyAdd(1e308, 2.0, -1e308)`, возвращающий `1e308`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-172">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="b6fad-173">Стандартный `(1e308 * 2.0) - 1e308` возвращает `double.PositiveInfinity`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-173">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

* `CopySign`\
<span data-ttu-id="b6fad-174">Соответствует операции IEEE `copySign`. Возвращает значение `x`, но со знаком `y`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-174">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="b6fad-175">Встроенные объекты, зависимые от платформы .NET</span><span class="sxs-lookup"><span data-stu-id="b6fad-175">.NET Platform Dependent Intrinsics</span></span>

<span data-ttu-id="b6fad-176">Были добавлены API-интерфейсы, которые разрешают доступ к определенным инструкциям ЦП, ориентированным на производительность, например **SIMD** или наборы **инструкций побитовой обработки**.</span><span class="sxs-lookup"><span data-stu-id="b6fad-176">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="b6fad-177">Эти инструкции помогут значительно улучшить производительность в некоторых сценариях, таких как эффективная параллельная обработка данных.</span><span class="sxs-lookup"><span data-stu-id="b6fad-177">These instructions can help achieve big performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span> <span data-ttu-id="b6fad-178">Помимо предоставления API-интерфейсов для программ, библиотеки .NET стали использовать эти инструкции для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="b6fad-178">In addition to exposing the APIs for your programs to use, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="b6fad-179">Следующие запросы на вытягивание CoreCLR демонстрируют другие встроенные функции через реализацию или использование:</span><span class="sxs-lookup"><span data-stu-id="b6fad-179">The following CoreCLR PRs demonstrate a few of the intrinsics, either via implementation or use:</span></span>

* [<span data-ttu-id="b6fad-180">Реализация простых встроенных объектов оборудования SSE2</span><span class="sxs-lookup"><span data-stu-id="b6fad-180">Implement simple SSE2 hardware intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/15585)
* [<span data-ttu-id="b6fad-181">Реализация встроенных объектов оборудования SSE</span><span class="sxs-lookup"><span data-stu-id="b6fad-181">Implement the SSE hardware intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/15538)
* [<span data-ttu-id="b6fad-182">Встроенные объекты Arm64 Base HW</span><span class="sxs-lookup"><span data-stu-id="b6fad-182">Arm64 Base HW Intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/16822)
* [<span data-ttu-id="b6fad-183">Использование TZCNT и LZCNT для Locate{First|Last}Found{Byte|Char}</span><span class="sxs-lookup"><span data-stu-id="b6fad-183">Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}</span></span>](https://github.com/dotnet/coreclr/pull/21073)

<span data-ttu-id="b6fad-184">Дополнительные сведения см. в разделе [Встроенные объекты, зависимые от платформы .NET](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md), где описан подход к определению этой аппаратной инфраструктуры, который позволяет Майкрософт, поставщикам микросхем или другим людям и компаниям определять API оборудования или микросхем, которые должны быть предоставлены коду .NET.</span><span class="sxs-lookup"><span data-stu-id="b6fad-184">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md), which defines an approach for defining this hardware infrastructure, allowing Microsoft, chip vendors, or any other company or individual to define hardware/chip APIs that should be exposed to .NET code.</span></span>

## <a name="default-executables"></a><span data-ttu-id="b6fad-185">Исполняемые файлы по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b6fad-185">Default executables</span></span>

<span data-ttu-id="b6fad-186">.NET Core теперь будет создавать [зависящие от платформы исполняемые файлы](../deploying/index.md#framework-dependent-executables-fde) по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b6fad-186">.NET Core will now build [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="b6fad-187">Это новый аспект для приложений, использующих глобально установленную версию .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6fad-187">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="b6fad-188">До настоящего времени исполняемые файлы создавались только в [автономных развертываниях](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="b6fad-188">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="b6fad-189">Во время выполнения команды `dotnet build` или `dotnet publish` создается исполняемый файл, который соответствует среде и платформе используемого пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="b6fad-189">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="b6fad-190">Предполагается, что с этими исполняемыми файлами можно выполнять те же действия, что и с другими исполняемыми файлами в машинном коде, например:</span><span class="sxs-lookup"><span data-stu-id="b6fad-190">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="b6fad-191">исполняемый файл можно дважды щелкнуть;</span><span class="sxs-lookup"><span data-stu-id="b6fad-191">You can double-click on the executable.</span></span>
* <span data-ttu-id="b6fad-192">приложение можно запустить из командной строки напрямую, например `myapp.exe` в Windows и `./myapp` в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="b6fad-192">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="b6fad-193">Сборка копирует зависимости</span><span class="sxs-lookup"><span data-stu-id="b6fad-193">Build copies dependencies</span></span>

<span data-ttu-id="b6fad-194">`dotnet build` теперь копирует зависимости NuGet для вашего приложения из кэша NuGet в выходную папку сборки.</span><span class="sxs-lookup"><span data-stu-id="b6fad-194">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="b6fad-195">Ранее зависимости копировались только в рамках выполнения команды `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-195">Previously, dependencies were only copied as part of `dotnet publish`.</span></span> 

<span data-ttu-id="b6fad-196">Для некоторых операций, таких как связывание и публикация страницы Razor, по-прежнему будет требоваться публикация.</span><span class="sxs-lookup"><span data-stu-id="b6fad-196">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>


## <a name="local-dotnet-tools"></a><span data-ttu-id="b6fad-197">Локальные средства dotnet</span><span class="sxs-lookup"><span data-stu-id="b6fad-197">Local dotnet tools</span></span>

>[!WARNING]
><span data-ttu-id="b6fad-198">Произошло изменение в локальных средствах .NET Core между .NET Core 3.0, предварительная версия 1, и .NET Core 3.0, предварительная версия 2.</span><span class="sxs-lookup"><span data-stu-id="b6fad-198">There was a change in .NET Core Local Tools between .NET Core 3.0 Preview 1 and .NET Core 3.0 Preview 2.</span></span>  <span data-ttu-id="b6fad-199">Если вы опробовали локальные средства в предварительной версии 1 с помощью команды `dotnet tool restore` или `dotnet tool install`, удалите папку кэша локальных средств, чтобы локальные средства правильно работали в предварительной версии 2.</span><span class="sxs-lookup"><span data-stu-id="b6fad-199">If you tried out local tools in Preview 1 by running a command like `dotnet tool restore` or `dotnet tool install`, you need to delete your local tools cache folder before local tools will work correctly in Preview 2.</span></span> <span data-ttu-id="b6fad-200">Эта папка находится по адресу:</span><span class="sxs-lookup"><span data-stu-id="b6fad-200">This folder is located at:</span></span>
>
><span data-ttu-id="b6fad-201">На Mac, в Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="b6fad-201">On mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
><span data-ttu-id="b6fad-202">В Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="b6fad-202">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>
>
><span data-ttu-id="b6fad-203">Если вы не удалите папку, вы получите ошибку.</span><span class="sxs-lookup"><span data-stu-id="b6fad-203">If you do not delete this folder, you will receive an error.</span></span>

<span data-ttu-id="b6fad-204">Хотя в .NET Core 2.1 была поддержка глобальных средств, в .NET Core 3.0 теперь есть локальные средства.</span><span class="sxs-lookup"><span data-stu-id="b6fad-204">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="b6fad-205">Локальные средства похожи на глобальные средства, но связаны с определенным расположением на диске.</span><span class="sxs-lookup"><span data-stu-id="b6fad-205">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="b6fad-206">Это обеспечивает инструменты для отдельных проектов и репозиториев.</span><span class="sxs-lookup"><span data-stu-id="b6fad-206">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="b6fad-207">Любое средство, установленное локально, недоступно глобально.</span><span class="sxs-lookup"><span data-stu-id="b6fad-207">Any tool installed locally isn't available globally.</span></span> <span data-ttu-id="b6fad-208">Средства распространяются в виде пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="b6fad-208">Tools are distributed as NuGet packages.</span></span>

<span data-ttu-id="b6fad-209">Локальные средства используют имя файла манифеста `dotnet-tools.json` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b6fad-209">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="b6fad-210">Этот файл манифеста определяет, какие средства доступны в этой папке и далее.</span><span class="sxs-lookup"><span data-stu-id="b6fad-210">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="b6fad-211">Если создать этот файл манифеста в корне репозитория, любой пользователь, клонировавший код, сможет восстановить и использовать средства, необходимые для успешной работы с кодом.</span><span class="sxs-lookup"><span data-stu-id="b6fad-211">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="b6fad-212">Чтобы создать файл манифеста `dotnet-tools.json`, используйте:</span><span class="sxs-lookup"><span data-stu-id="b6fad-212">To create a `dotnet-tools.json` manifest file, use:</span></span>

```console
dotnet new tool-manifest
```

<span data-ttu-id="b6fad-213">Добавьте новое средство в локальный манифест с помощью:</span><span class="sxs-lookup"><span data-stu-id="b6fad-213">Add a new tool to the local manifest with:</span></span>

```console
dotnet tool install <packageId>
```

<span data-ttu-id="b6fad-214">Можно также перечислить средства в локальном манифесте с помощью:</span><span class="sxs-lookup"><span data-stu-id="b6fad-214">You can also list the tools in the local manifest with:</span></span>

```console
dotnet tool list
```

<span data-ttu-id="b6fad-215">Чтобы узнать, какие средства установлены глобально, используйте:</span><span class="sxs-lookup"><span data-stu-id="b6fad-215">To see what tools are installed globally, use:</span></span>

```console
dotnet tool list -g
```

<span data-ttu-id="b6fad-216">Если файл манифеста локальных средств доступен, но средства, определенные в манифесте, не установлены, выполните приведенную ниже команду, чтобы автоматически скачать и установить эти средства:</span><span class="sxs-lookup"><span data-stu-id="b6fad-216">When the local tools manifest file is available, but the tools defined in the manifest have not been installed, use the following command to automatically download and install those tools:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="b6fad-217">Запустите локальное средство с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="b6fad-217">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="b6fad-218">При запуске локального средства dotnet выполняет поиск манифеста вверх по текущей структуре каталогов.</span><span class="sxs-lookup"><span data-stu-id="b6fad-218">When a local tool is run, dotnet searches for a manifest up the current directory structure.</span></span> <span data-ttu-id="b6fad-219">Когда файл манифеста средства обнаруживается, выполняется поиск запрашиваемого средства.</span><span class="sxs-lookup"><span data-stu-id="b6fad-219">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="b6fad-220">Если средство обнаруживается в манифесте, а не в кэше, пользователь получает сообщение об ошибке и должен запустить `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-220">If the tool is found in the manifest, but not the cache, the user receives an error and needs to run `dotnet tool restore`.</span></span>

<span data-ttu-id="b6fad-221">Чтобы удалить средство из локального файла манифеста средства, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b6fad-221">To remove a tool from the local tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <packageId>
```

<span data-ttu-id="b6fad-222">Файл манифеста средства разработан так, чтобы его можно было редактировать вручную, например, когда необходимо обновить требуемую версию для работы с репозиторием.</span><span class="sxs-lookup"><span data-stu-id="b6fad-222">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span> <span data-ttu-id="b6fad-223">Ниже приведен пример файла `dotnet-tools.json`:</span><span class="sxs-lookup"><span data-stu-id="b6fad-223">Here is an example `dotnet-tools.json` file:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

<span data-ttu-id="b6fad-224">Для глобальных и локальных средств требуется совместимая версия среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6fad-224">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="b6fad-225">Сейчас на сайте NuGet.org многие средства предназначены для среды выполнения .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="b6fad-225">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="b6fad-226">Чтобы установить их глобально или локально, по-прежнему необходимо установить [среду выполнения NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="b6fad-226">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="b6fad-227">Классические приложения Windows</span><span class="sxs-lookup"><span data-stu-id="b6fad-227">Windows desktop</span></span>

<span data-ttu-id="b6fad-228">Начиная с .NET Core 3.0 (предварительная версия 1), можно создавать классические приложения Windows с помощью WPF и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b6fad-228">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="b6fad-229">Эти платформы также поддерживают использование современных элементов управления и стилей Fluent из библиотеки XAML пользовательского интерфейса Windows (WinUI) через [острова XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="b6fad-229">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="b6fad-230">Компонент Windows Desktop является частью пакета SDK .NET Core 3.0 для Windows.</span><span class="sxs-lookup"><span data-stu-id="b6fad-230">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="b6fad-231">Вы можете создать приложение WPF или Windows Forms с помощью следующих команд `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="b6fad-231">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="b6fad-232">Visual Studio 2019, предварительная версия 2, добавляет шаблоны **Новый проект** для .NET Core 3.0 Windows Forms и WPF.</span><span class="sxs-lookup"><span data-stu-id="b6fad-232">Visual Studio 2019 Preview 2 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span> <span data-ttu-id="b6fad-233">Конструкторы по-прежнему не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b6fad-233">Designers are still not yet supported.</span></span> <span data-ttu-id="b6fad-234">Вы можете открывать, запускать и отлаживать эти проекты в Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="b6fad-234">And you can open, launch, and debug these projects in Visual Studio 2019.</span></span>

<span data-ttu-id="b6fad-235">Visual Studio 2017 15.9 добавляет возможность [включать предварительные версии .NET Core](https://devblogs.microsoft.com/dotnet/net-core-tooling-update-for-visual-studio-2017-version-15-9/), но необходимо включить эту функцию, и это не поддерживаемый сценарий.</span><span class="sxs-lookup"><span data-stu-id="b6fad-235">Visual Studio 2017 15.9 adds the ability to [enable .NET Core previews](https://devblogs.microsoft.com/dotnet/net-core-tooling-update-for-visual-studio-2017-version-15-9/), but you need to turn that feature on, and it's not a supported scenario.</span></span>

<span data-ttu-id="b6fad-236">Новые проекты идентичны имеющимся проектам .NET Core с некоторыми добавлениями.</span><span class="sxs-lookup"><span data-stu-id="b6fad-236">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="b6fad-237">Ниже приведено сравнение базового консольного проекта .NET Core и базового проекта Windows Forms и WPF.</span><span class="sxs-lookup"><span data-stu-id="b6fad-237">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="b6fad-238">Консольный проект .NET Core использует пакет SDK `Microsoft.NET.Sdk` и объявляет зависимость в .NET Core 3.0 с помощью требуемой версии .NET Framework `netcoreapp3.0`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-238">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="b6fad-239">Чтобы создать приложение Windows Desktop, используйте пакет SDK `Microsoft.NET.Sdk.WindowsDesktop` и выберите, какую платформу пользовательского интерфейса использовать:</span><span class="sxs-lookup"><span data-stu-id="b6fad-239">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="b6fad-240">Чтобы выбрать Windows Forms вместо WPF, установите `UseWindowsForms` вместо `UseWPF`:</span><span class="sxs-lookup"><span data-stu-id="b6fad-240">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="b6fad-241">Для `UseWPF` и `UseWindowsForms` можно задать значение `true`, если приложение использует обе платформы, например, если в диалоговом окне Windows Forms размещен элемент управления WPF.</span><span class="sxs-lookup"><span data-stu-id="b6fad-241">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="b6fad-242">Оставьте свой отзыв в репозитории [dotnet/winforms](https://github.com/dotnet/winforms/issues), [dotnet/wpf](https://github.com/dotnet/wpf/issues) и [dotnet/core](https://github.com/dotnet/core/issues).</span><span class="sxs-lookup"><span data-stu-id="b6fad-242">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="msix-deployment-for-windows-desktop"></a><span data-ttu-id="b6fad-243">Развертывание MSIX для Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="b6fad-243">MSIX Deployment for Windows Desktop</span></span>

<span data-ttu-id="b6fad-244">[MSIX](https://docs.microsoft.com/windows/msix/) — это новый формат пакета приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="b6fad-244">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows app package format.</span></span> <span data-ttu-id="b6fad-245">Его можно использовать для развертывания классических приложений .NET Core 3.0 для Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b6fad-245">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="b6fad-246">[Проект упаковки приложений Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), доступный в Visual Studio 2019, предварительная версия 2, позволяет создавать пакеты MSIX с [автономными](../deploying/index.md#self-contained-deployments-scd) приложениями .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6fad-246">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019 Preview 2, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

><span data-ttu-id="b6fad-247">Примечание. Файл проекта .NET Core должен указывать поддерживаемые среды выполнения в свойстве `<RuntimeIdentifiers>`:</span><span class="sxs-lookup"><span data-stu-id="b6fad-247">Note: The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>
```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="fast-built-in-json-support"></a><span data-ttu-id="b6fad-248">Быстрая встроенная поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="b6fad-248">Fast built-in JSON support</span></span>

<span data-ttu-id="b6fad-249">В экосистеме .NET использовалась [**Json.NET**](https://www.newtonsoft.com/json) и другие популярные библиотеки JSON, которые по-прежнему остаются хорошими вариантами.</span><span class="sxs-lookup"><span data-stu-id="b6fad-249">The .NET ecosystem has relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="b6fad-250">**Json.NET** использует в качестве базового типа данных строки .NET, которые обладают внутренней структурой UTF-16.</span><span class="sxs-lookup"><span data-stu-id="b6fad-250">**Json.NET** uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span>

<span data-ttu-id="b6fad-251">Новая встроенная поддержка JSON отличается высокой производительностью и малым распределением и основана на `Span<byte>`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-251">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="b6fad-252">Были добавлены три новых основных типа, связанных с JSON, в пространство имен `System.Text.Json` в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6fad-252">Three new main JSON-related types have been added to .NET Core 3.0 the `System.Text.Json` namespace.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="b6fad-253">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="b6fad-253">Utf8JsonReader</span></span>

<span data-ttu-id="b6fad-254">`System.Text.Json.Utf8JsonReader` — это однопроходный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` с высокой производительностью и низким уровнем распределения.</span><span class="sxs-lookup"><span data-stu-id="b6fad-254">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="b6fad-255">`Utf8JsonReader` — это основной тип низкого уровня, с помощью которого можно создавать пользовательские средства синтаксического анализа и десериализаторы.</span><span class="sxs-lookup"><span data-stu-id="b6fad-255">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="b6fad-256">Чтение полезных данных JSON с помощью нового `Utf8JsonReader` осуществляется в два раза быстрее, чем при использовании модуля чтения от **JSON.NET**.</span><span class="sxs-lookup"><span data-stu-id="b6fad-256">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="b6fad-257">Распределение не осуществляется, пока не понадобится актуализировать токены JSON в виде строк (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="b6fad-257">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="b6fad-258">Этот новый интерфейс API будет включать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="b6fad-258">This new API will include the following components:</span></span>

* <span data-ttu-id="b6fad-259">В предварительной версии 1: модуль чтения JSON (последовательный доступ).</span><span class="sxs-lookup"><span data-stu-id="b6fad-259">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="b6fad-260">Ожидается в следующем выпуске: модуль записи JSON, DOM (произвольный доступ), сериализатор poco, десериализатор poco.</span><span class="sxs-lookup"><span data-stu-id="b6fad-260">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="b6fad-261">Ниже приведен цикл базового модуля чтения для `Utf8JsonReader`, который можно использовать в качестве отправной точки:</span><span class="sxs-lookup"><span data-stu-id="b6fad-261">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

### <a name="utf8jsonwriter"></a><span data-ttu-id="b6fad-262">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="b6fad-262">Utf8JsonWriter</span></span>

<span data-ttu-id="b6fad-263">`System.Text.Json.Utf8JsonWriter` предоставляет высокопроизводительный, не использующий кэширование и однонаправленный способ записи текста JSON в кодировке UTF-8 из распространенных типов .NET, например `String`, `Int32` и `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-263">`System.Text.Json.Utf8JsonWriter` provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="b6fad-264">Как и средство чтения, средство записи — это основной тип низкого уровня, с помощью которого можно создавать пользовательские сериализаторы.</span><span class="sxs-lookup"><span data-stu-id="b6fad-264">Like the reader, the writer is a foundational, low-level type, that can be leveraged to build custom serializers.</span></span> <span data-ttu-id="b6fad-265">Запись полезных данных JSON с помощью нового `Utf8JsonWriter` выполняется на 30–80 % быстрее, чем с помощью средства записи из **Json.NET**, и не требует выделения.</span><span class="sxs-lookup"><span data-stu-id="b6fad-265">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and does not allocate.</span></span>

<span data-ttu-id="b6fad-266">Ниже приведен пример использования `Utf8JsonWriter`, который может использоваться в качестве отправной точки:</span><span class="sxs-lookup"><span data-stu-id="b6fad-266">Here is a sample usage of the `Utf8JsonWriter` that can be used as a starting point:</span></span>

```csharp
static int WriteJson(IBufferWriter<byte> output, long[] extraData)
{
    var json = new Utf8JsonWriter(output, state: default);

    json.WriteStartObject();

    json.WriteNumber("age", 15, escape: false);
    json.WriteString("date", DateTime.Now);
    json.WriteString("first", "John");
    json.WriteString("last", "Smith");

    json.WriteStartArray("phoneNumbers", escape: false);
    json.WriteStringValue("425-000-1212", escape: false);
    json.WriteStringValue("425-000-1213");
    json.WriteEndArray();

    json.WriteStartObject("address");
    json.WriteString("street", "1 Microsoft Way");
    json.WriteString("city", "Redmond");
    json.WriteNumber("zip", 98052);
    json.WriteEndObject();

    json.WriteStartArray("ExtraArray");
    for (var i = 0; i < extraData.Length; i++)
    {
        json.WriteNumberValue(extraData[i]);
    }
    json.WriteEndArray();

    json.WriteEndObject();

    json.Flush(isFinalBlock: true);

    return (int)json.BytesWritten;
}
```

<span data-ttu-id="b6fad-267">`Utf8JsonWriter` принимает `IBufferWriter<byte>` в качестве выходного расположения для синхронной записи данных json, и вы, как вызывающий объект, должны предоставить конкретную реализацию.</span><span class="sxs-lookup"><span data-stu-id="b6fad-267">The `Utf8JsonWriter` accepts `IBufferWriter<byte>` as the output location to synchronously write the json data into, and you as the caller need to provide a concrete implementation.</span></span> <span data-ttu-id="b6fad-268">В настоящее время платформа не включает реализацию этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b6fad-268">The platform does not currently include an implementation of this interface.</span></span> <span data-ttu-id="b6fad-269">Пример `IBufferWriter<byte>` см. в [https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35](https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35)</span><span class="sxs-lookup"><span data-stu-id="b6fad-269">For an example of `IBufferWriter<byte>`, see [https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35](https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35)</span></span>

### <a name="jsondocument"></a><span data-ttu-id="b6fad-270">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="b6fad-270">JsonDocument</span></span>

<span data-ttu-id="b6fad-271">`System.Text.Json.JsonDocument` создается на основе `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-271">`System.Text.Json.JsonDocument` is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="b6fad-272">`JsonDocument` предоставляет возможность анализировать данные JSON и создавать модель DOM только для чтения, которая может запрашиваться для поддержки случайного доступа и перечисления.</span><span class="sxs-lookup"><span data-stu-id="b6fad-272">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="b6fad-273">Доступ к элементам JSON, составляющим данные, может осуществляться через тип `JsonElement`, который предоставляется `JsonDocument` как свойство с именем `RootElement`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-273">The JSON elements that compose the data can be accessed via the `JsonElement` type which is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="b6fad-274">`JsonElement` содержит перечислители массива и объекта JSON вместе с API-интерфейсами для преобразования текста JSON в стандартные типы .NET.</span><span class="sxs-lookup"><span data-stu-id="b6fad-274">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="b6fad-275">Синтаксический анализ типичных полезных данных JSON и доступ ко всем членам с помощью `JsonDocument` выполняется в 2–3 раза быстрее, чем **Json.NET**, с небольшим количеством распределений данных приемлемого размера (т. е. < 1 МБ).</span><span class="sxs-lookup"><span data-stu-id="b6fad-275">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with very little allocations for data that is reasonably sized (i.e. < 1 MB).</span></span>

<span data-ttu-id="b6fad-276">Ниже приведен пример использования `JsonDocument` и `JsonElement`, который может использоваться в качестве отправной точки:</span><span class="sxs-lookup"><span data-stu-id="b6fad-276">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

```csharp
static double ParseJson()
{
    const string json = " [ { \"name\": \"John\" }, [ \"425-000-1212\", 15 ], { \"grades\": [ 90, 80, 100, 75 ] } ]";

    double average = -1;

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        JsonElement root = doc.RootElement;
        JsonElement info = root[1];

        string phoneNumber = info[0].GetString();
        int age = info[1].GetInt32();

        JsonElement grades = root[2].GetProperty("grades");

        double sum = 0;
        foreach (JsonElement grade in grades.EnumerateArray())
        {
            sum += grade.GetInt32();
        }

        int numberOfCourses = grades.GetArrayLength();
        average = sum / numberOfCourses;
    }

    return average;
}
```

## <a name="assembly-unloadability"></a><span data-ttu-id="b6fad-277">Возможность выгрузки сборки</span><span class="sxs-lookup"><span data-stu-id="b6fad-277">Assembly Unloadability</span></span>

<span data-ttu-id="b6fad-278">Выгрузка сборки — это новая возможность `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-278">Assembly unloadability is a new capability of `AssemblyLoadContext`.</span></span> <span data-ttu-id="b6fad-279">Эта новая функция довольно прозрачна с точки зрения API и предоставляется с помощью всего нескольких новых API.</span><span class="sxs-lookup"><span data-stu-id="b6fad-279">This new feature is largely transparent from an API perspective, exposed with just a few new APIs.</span></span> <span data-ttu-id="b6fad-280">Она позволяет выгружать контекст загрузчика, освобождая всю память для экземпляров типов, статических полей, а также для самой сборки.</span><span class="sxs-lookup"><span data-stu-id="b6fad-280">It enables a loader context to be unloaded, releasing all memory for instantiated types, static fields and for the assembly itself.</span></span> <span data-ttu-id="b6fad-281">Приложение должно всегда иметь возможность загрузки и выгрузки сборок с помощью этого механизма без утечки памяти.</span><span class="sxs-lookup"><span data-stu-id="b6fad-281">An application should be able to load and unload assemblies via this mechanism forever without experiencing a memory leak.</span></span>

<span data-ttu-id="b6fad-282">Эта новая возможность может использоваться в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="b6fad-282">This new capability can be used for scenarios similar to:</span></span>

* <span data-ttu-id="b6fad-283">Подключаемый модуль, где требуется загрузка и выгрузка динамического подключаемого модуля.</span><span class="sxs-lookup"><span data-stu-id="b6fad-283">Plugin scenarios where dynamic plugin loading and unloading is required.</span></span> 
* <span data-ttu-id="b6fad-284">Динамическая компиляция, запуск и затем очистка кода.</span><span class="sxs-lookup"><span data-stu-id="b6fad-284">Dynamically compiling, running and then flushing code.</span></span> <span data-ttu-id="b6fad-285">Это удобно для веб-сайтов, модулей написания скриптов и т. д.</span><span class="sxs-lookup"><span data-stu-id="b6fad-285">Useful for web sites, scripting engines, etc.</span></span>
* <span data-ttu-id="b6fad-286">Загрузка сборок для анализа (например, ReflectionOnlyLoad), хотя [MetadataLoadContext](#type-metadataloadcontext) (выпущенный в предварительной версии 1) подойдет лучше во многих случаях.</span><span class="sxs-lookup"><span data-stu-id="b6fad-286">Loading assemblies for introspection (like ReflectionOnlyLoad), although [MetadataLoadContext](#type-metadataloadcontext) (released in Preview 1) will be a better choice in many cases.</span></span>

<span data-ttu-id="b6fad-287">Дополнительные сведения см. в статье [Использование выгрузки](https://github.com/dotnet/coreclr/pull/22221).</span><span class="sxs-lookup"><span data-stu-id="b6fad-287">For more information, see the [Using Unloadability](https://github.com/dotnet/coreclr/pull/22221) document.</span></span>

<span data-ttu-id="b6fad-288">Выгрузка сборки требует большой осторожности, так как вы должны понимать и контролировать все ссылки на управляемые объекты вне контекста загрузчика.</span><span class="sxs-lookup"><span data-stu-id="b6fad-288">Assembly unloading requires significant care to ensure that all references to managed objects from outside a loader context are understood and managed.</span></span> <span data-ttu-id="b6fad-289">При запросе выгрузки контекста загрузчика необходимо отменить все внешние ссылки, чтобы контекст загрузчика соответствовал только самому себе.</span><span class="sxs-lookup"><span data-stu-id="b6fad-289">When the loader context is requested to be unloaded, any outside references need to have been unreferenced so that the loader context is self-consistent only to itself.</span></span>

<span data-ttu-id="b6fad-290">Возможность выгрузки сборки предоставляется доменами приложения .NET Framework, которые не поддерживаются .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6fad-290">Assembly unloadability was provided in the .NET Framework by Application Domains (AppDomains), which are not supported with .NET Core.</span></span> <span data-ttu-id="b6fad-291">Домены приложений имеют свои преимущества и ограничения по сравнению с этой новой моделью.</span><span class="sxs-lookup"><span data-stu-id="b6fad-291">AppDomains had both benefits and limitations compared to this new model.</span></span> <span data-ttu-id="b6fad-292">Новая модель загрузчика отличается большей гибкостью и производительностью по сравнению с доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="b6fad-292">Consider this new loader model to be more flexible and higher performant when compared to AppDomains.</span></span>

## <a name="windows-native-interop"></a><span data-ttu-id="b6fad-293">Собственное взаимодействие Windows</span><span class="sxs-lookup"><span data-stu-id="b6fad-293">Windows Native Interop</span></span>

<span data-ttu-id="b6fad-294">Windows предоставляет собственный API с широкими возможностями в виде API C, COM и WinRT.</span><span class="sxs-lookup"><span data-stu-id="b6fad-294">Windows offers a rich native API, in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="b6fad-295">Начиная с .NET Core 1.0 поддерживается **P/Invoke**.</span><span class="sxs-lookup"><span data-stu-id="b6fad-295">Since .NET Core 1.0, **P/Invoke** has been supported.</span></span> <span data-ttu-id="b6fad-296">Теперь с .NET Core 3.0 поддерживается возможность **совместного создания API COM** и **активации API WinRT**.</span><span class="sxs-lookup"><span data-stu-id="b6fad-296">Now with .NET Core 3.0, support for the ability to **CoCreate COM APIs** and **Activate WinRT APIs** has been added.</span></span>

<span data-ttu-id="b6fad-297">Пример использования COM вы найдете в [исходном коде демонстрации Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="b6fad-297">You can see an example of using COM with the [Excel Demo source code](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>


## <a name="type-sequencereader"></a><span data-ttu-id="b6fad-298">Тип: SequenceReader</span><span class="sxs-lookup"><span data-stu-id="b6fad-298">Type: SequenceReader</span></span>

<span data-ttu-id="b6fad-299">В .NET Core 3.0 добавлен `System.Buffers.SequenceReader`, который можно использовать в качестве модуля чтения для `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-299">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="b6fad-300">Это обеспечивает простой и высокопроизводительный анализ данных `System.IO.Pipelines` с низким уровнем распределения, которые могут пересекать несколько буферов резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="b6fad-300">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span> 

<span data-ttu-id="b6fad-301">В следующем примере входные данные `Sequence` разбиваются на допустимые строки `CR/LF` с разделителями:</span><span class="sxs-lookup"><span data-stu-id="b6fad-301">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a><span data-ttu-id="b6fad-302">Тип: MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="b6fad-302">Type: MetadataLoadContext</span></span>

<span data-ttu-id="b6fad-303">Добавлен тип `MetadataLoadContext`, позволяющий считывать метаданные сборки, не влияя на домен приложения вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="b6fad-303">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="b6fad-304">Сборки считываются как данные, включая сборки, созданные для различных архитектур и платформ, а не для текущей среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6fad-304">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="b6fad-305">`MetadataLoadContext` перекрывается с <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, который доступен только в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6fad-305">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="b6fad-306">`MetdataLoadContext` доступен в [пакете System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span><span class="sxs-lookup"><span data-stu-id="b6fad-306">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="b6fad-307">Это пакет .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="b6fad-307">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="b6fad-308">`MetadataLoadContext` предоставляет интерфейсы API, подобные типу <xref:System.Runtime.Loader.AssemblyLoadContext>, но не на основе этого типа.</span><span class="sxs-lookup"><span data-stu-id="b6fad-308">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="b6fad-309">Подобно <xref:System.Runtime.Loader.AssemblyLoadContext> `MetadataLoadContext` обеспечивает загрузку сборок в изолированной вселенной загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="b6fad-309">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="b6fad-310">Интерфейсы API `MetdataLoadContext` возвращают объекты <xref:System.Reflection.Assembly>, позволяя использовать знакомые API отражения.</span><span class="sxs-lookup"><span data-stu-id="b6fad-310">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="b6fad-311">Интерфейсы API, ориентированные на выполнение, такие как [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), не разрешены и вызывают исключение InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="b6fad-311">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="b6fad-312">В следующем примере показано, как найти конкретные типы в сборке, которая реализует данный интерфейс:</span><span class="sxs-lookup"><span data-stu-id="b6fad-312">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

<span data-ttu-id="b6fad-313">Сценарии для `MetadataLoadContext` включают в себя возможности времени разработки, инструменты, используемые во время сборки, и возможности подготовки среды выполнения, в которые должна входить проверка набора сборок в качестве данных. В них есть все блокировки файлов, а после проверки память освобождается.</span><span class="sxs-lookup"><span data-stu-id="b6fad-313">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="b6fad-314">В `MetadataLoadContext` есть класс сопоставителя, переданный в конструктор.</span><span class="sxs-lookup"><span data-stu-id="b6fad-314">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="b6fad-315">Заданием сопоставителя является загрузка сборки (`Assembly`) с учетом ее `AssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-315">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="b6fad-316">Класс сопоставителя является производным от абстрактного класса `MetadataAssemblyResolver`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-316">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="b6fad-317">Реализация сопоставителя для сценариев на основе пути входит в состав `PathAssemblyResolver`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-317">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="b6fad-318">[Тесты MetadataLoadContext](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) демонстрируют множество вариантов использования.</span><span class="sxs-lookup"><span data-stu-id="b6fad-318">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="b6fad-319">[Тесты сборки](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) — хорошее место для начала.</span><span class="sxs-lookup"><span data-stu-id="b6fad-319">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="b6fad-320">TLS 1.3 и OpenSSL 1.1.1 в Linux</span><span class="sxs-lookup"><span data-stu-id="b6fad-320">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="b6fad-321">.NET Core теперь будет использовать преимущества [поддержки TLS 1.3 в OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), когда она станет доступна в данной среде.</span><span class="sxs-lookup"><span data-stu-id="b6fad-321">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="b6fad-322">Есть несколько преимуществ TLS 1.3 для [команды OpenSSL](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span><span class="sxs-lookup"><span data-stu-id="b6fad-322">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="b6fad-323">уменьшено время соединения в результате уменьшения количества круговых путей между клиентом и сервером;</span><span class="sxs-lookup"><span data-stu-id="b6fad-323">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="b6fad-324">улучшена безопасность в результате удаления различных устаревших и небезопасных алгоритмов шифрования и шифрования нескольких подтверждений соединения.</span><span class="sxs-lookup"><span data-stu-id="b6fad-324">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="b6fad-325">В .NET Core 3.0 (предварительная версия 1) предусмотрена возможность использования **OpenSSL 1.1.1**, **OpenSSL 1.1.0** или **OpenSSL 1.0.2** (зависит от того, какая лучшая версия найдена в системе Linux).</span><span class="sxs-lookup"><span data-stu-id="b6fad-325">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="b6fad-326">Когда **OpenSSL 1.1.1** доступен, типы SslStream и HttpClient будут применять **TLS 1.3** при использовании `SslProtocols.None` (протоколы системы по умолчанию) при условии, что клиент и сервер поддерживают **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="b6fad-326">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="b6fad-327">В следующем примере показано, как .NET Core 3.0 (предварительная версия 1) подключается к Ubuntu 18.10 <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="b6fad-327">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
><span data-ttu-id="b6fad-328">Windows и macOS еще не поддерживают **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="b6fad-328">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="b6fad-329">.NET Core 3.0 будет поддерживать **TLS 1.3** в этих операционных системах, когда поддержка станет доступной.</span><span class="sxs-lookup"><span data-stu-id="b6fad-329">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="b6fad-330">Шифрование</span><span class="sxs-lookup"><span data-stu-id="b6fad-330">Cryptography</span></span>

<span data-ttu-id="b6fad-331">Добавлена поддержка шифров **AES-GCM** и **AES-CCM**, реализованных с помощью `System.Security.Cryptography.AesGcm` и `System.Security.Cryptography.AesCcm`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-331">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="b6fad-332">Эти алгоритмы являются [алгоритмами шифрования с проверкой подлинности с присоединенными данными](https://en.wikipedia.org/wiki/Authenticated_encryption), и первые алгоритмы шифрования с проверкой подлинности добавлены в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6fad-332">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="b6fad-333">В следующем коде показано использование шифра **AesGcm** для шифрования и расшифровки случайных данных.</span><span class="sxs-lookup"><span data-stu-id="b6fad-333">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="b6fad-334">Код для **AesCcm** выглядит почти так же (только имена переменных класса отличаются).</span><span class="sxs-lookup"><span data-stu-id="b6fad-334">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="b6fad-335">Импорт и экспорт криптографических ключей</span><span class="sxs-lookup"><span data-stu-id="b6fad-335">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="b6fad-336">.NET Core 3.0 (предварительная версия 1) поддерживает импорт и экспорт асимметричных открытых и закрытых ключей из стандартных форматов, и при этом не нужно использовать сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="b6fad-336">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="b6fad-337">Все основные типы (RSA, DSA, ECDsa, ECDiffieHellman) поддерживают формат **X.509 SubjectPublicKeyInfo** для открытых ключей и форматы **PKCS#8 PrivateKeyInfo** и **PKCS#8 EncryptedPrivateKeyInfo** для закрытых ключей.</span><span class="sxs-lookup"><span data-stu-id="b6fad-337">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="b6fad-338">RSA также поддерживает **PKCS#1 RSAPublicKey** и **PKCS#1 RSAPrivateKey**.</span><span class="sxs-lookup"><span data-stu-id="b6fad-338">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="b6fad-339">Все методы экспорта создают двоичные данные в кодировке DER, а методы импорта выполняют то же самое.</span><span class="sxs-lookup"><span data-stu-id="b6fad-339">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="b6fad-340">Если ключ хранится в формате PEM в виде текста, вызывающему объекту потребуется выполнить декодирование содержимого в формате base64, прежде чем вызывать метод импорта.</span><span class="sxs-lookup"><span data-stu-id="b6fad-340">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

<span data-ttu-id="b6fad-341">Файлы PKCS#8 можно проверить с помощью класса `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-341">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="b6fad-342">Файлы PFX/PKCS#12 можно проверить и использовать с помощью `System.Security.Cryptography.Pkcs.Pkcs12Info` и `System.Security.Cryptography.Pkcs.Pkcs12Builder` соответственно.</span><span class="sxs-lookup"><span data-stu-id="b6fad-342">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="b6fad-343">SerialPort для Linux</span><span class="sxs-lookup"><span data-stu-id="b6fad-343">SerialPort for Linux</span></span>

<span data-ttu-id="b6fad-344">.NET Core 3.0 теперь поддерживает <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> в Linux.</span><span class="sxs-lookup"><span data-stu-id="b6fad-344">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="b6fad-345">Ранее среда .NET Core поддерживала только использование типа `SerialPort` в Windows.</span><span class="sxs-lookup"><span data-stu-id="b6fad-345">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="b6fad-346">Дополнительные улучшения BCL</span><span class="sxs-lookup"><span data-stu-id="b6fad-346">More BCL Improvements</span></span>

<span data-ttu-id="b6fad-347">`Span<T>`, `Memory<T>` и связанные типы, которые впервые появились в .NET Core 2.1, были оптимизированы в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6fad-347">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="b6fad-348">Такие распространенные операции, как создание span, создание срезов, анализ и форматирование, теперь работают лучше.</span><span class="sxs-lookup"><span data-stu-id="b6fad-348">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span> 

<span data-ttu-id="b6fad-349">Кроме того, усовершенствованы такие типы, как `String`, чтобы повысить их эффективность при использовании в качестве ключей с `Dictionary<TKey, TValue>` и другими коллекциями.</span><span class="sxs-lookup"><span data-stu-id="b6fad-349">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="b6fad-350">Для использования этих преимуществ изменения кода не требуются.</span><span class="sxs-lookup"><span data-stu-id="b6fad-350">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="b6fad-351">Следующие улучшения также являются новшествами в .NET Core 3 (предварительная версия 1):</span><span class="sxs-lookup"><span data-stu-id="b6fad-351">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="b6fad-352">поддержка Brotli, встроенная в HttpClient;</span><span class="sxs-lookup"><span data-stu-id="b6fad-352">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="b6fad-353">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem);</span><span class="sxs-lookup"><span data-stu-id="b6fad-353">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="b6fad-354">Unsafe.Unbox;</span><span class="sxs-lookup"><span data-stu-id="b6fad-354">Unsafe.Unbox</span></span>
* <span data-ttu-id="b6fad-355">CancellationToken.Unregister;</span><span class="sxs-lookup"><span data-stu-id="b6fad-355">CancellationToken.Unregister</span></span>
* <span data-ttu-id="b6fad-356">сложные арифметические операторы;</span><span class="sxs-lookup"><span data-stu-id="b6fad-356">Complex arithmetic operators</span></span>
* <span data-ttu-id="b6fad-357">интерфейсы API сокета для поддержки TCP в активном состоянии;</span><span class="sxs-lookup"><span data-stu-id="b6fad-357">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="b6fad-358">StringBuilder.GetChunks;</span><span class="sxs-lookup"><span data-stu-id="b6fad-358">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="b6fad-359">синтаксический анализ IPEndPoint;</span><span class="sxs-lookup"><span data-stu-id="b6fad-359">IPEndPoint parsing</span></span>
* <span data-ttu-id="b6fad-360">RandomNumberGenerator.GetInt32.</span><span class="sxs-lookup"><span data-stu-id="b6fad-360">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="b6fad-361">Многоуровневая компиляция</span><span class="sxs-lookup"><span data-stu-id="b6fad-361">Tiered compilation</span></span>

<span data-ttu-id="b6fad-362">[Многоуровневая компиляция](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) по умолчанию включена в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6fad-362">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="b6fad-363">Это возможность, благодаря которой среда выполнения более адаптивно использует компилятор JIT для повышения производительности при запуске и максимального увеличения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="b6fad-363">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="b6fad-364">Эта возможность добавлена в качестве возможности, включаемой пользователем в [.NET Core 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-1/), а затем была включена по умолчанию в [.NET Core 2.2 (предварительная версия 2)](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span><span class="sxs-lookup"><span data-stu-id="b6fad-364">This feature was added as an opt-in feature in [.NET Core 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="b6fad-365">Затем в выпуске .NET Core 2.2 она была возвращена в состояние возможности, включаемой пользователем.</span><span class="sxs-lookup"><span data-stu-id="b6fad-365">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="b6fad-366">Поддержка ARM64 Linux</span><span class="sxs-lookup"><span data-stu-id="b6fad-366">ARM64 Linux support</span></span>

<span data-ttu-id="b6fad-367">Для Linux добавлена поддержка ARM64.</span><span class="sxs-lookup"><span data-stu-id="b6fad-367">Support has been added for ARM64 for Linux.</span></span> <span data-ttu-id="b6fad-368">Основной вариант использования для ARM64 в данный момент — это сценарии Интернета вещей.</span><span class="sxs-lookup"><span data-stu-id="b6fad-368">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="b6fad-369">[Образы Docker Alpine, Debian и Ubuntu доступны для .NET Core для ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="b6fad-369">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="b6fad-370">Дополнительные сведения см. в статье о [состоянии .NET Core ARM64](https://github.com/dotnet/announcements/issues/82).</span><span class="sxs-lookup"><span data-stu-id="b6fad-370">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="b6fad-371">Поддержка **ARM64** в Windows еще недоступна.</span><span class="sxs-lookup"><span data-stu-id="b6fad-371">**ARM64** Windows support isn't yet available.</span></span>

## <a name="install-net-core-30-previews-on-linux-with-snap"></a><span data-ttu-id="b6fad-372">Установка предварительных версий .NET Core 3.0 в Linux с помощью Snap</span><span class="sxs-lookup"><span data-stu-id="b6fad-372">Install .NET Core 3.0 Previews on Linux with Snap</span></span>

<span data-ttu-id="b6fad-373">Snap — это предпочтительный способ устанавливать и испытывать предварительные версии .NET Core в [дистрибутивах Linux с поддержкой Snap](https://docs.snapcraft.io/installing-snapd/6735).</span><span class="sxs-lookup"><span data-stu-id="b6fad-373">Snap is the preferred way to install and try .NET Core previews on [Linux distributions that support Snap](https://docs.snapcraft.io/installing-snapd/6735).</span></span>

<span data-ttu-id="b6fad-374">После настройки Snap в системе выполните следующую команду, чтобы установить [предварительную версию пакета SDK для .NET Core 3.0](https://snapcraft.io/dotnet-sdk).</span><span class="sxs-lookup"><span data-stu-id="b6fad-374">After configuring Snap on your system, run the following command to install the [.NET Core SDK 3.0 Preview SDK](https://snapcraft.io/dotnet-sdk).</span></span>

```console
sudo snap install dotnet-sdk --beta --classic
```
 
<span data-ttu-id="b6fad-375">Если .NET Core установлен с помощью пакета Snap, команда .NET Core по умолчанию — `dotnet-sdk.dotnet`, а не `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="b6fad-375">When .NET Core in installed using the Snap package, the default .NET Core command is `dotnet-sdk.dotnet`, as opposed to just `dotnet`.</span></span> <span data-ttu-id="b6fad-376">Преимущество команды с пространством имен в том, что она не будет конфликтовать с глобально установленной версией .NET Core, если она у вас есть.</span><span class="sxs-lookup"><span data-stu-id="b6fad-376">The benefit of the namespaced command is that it will not conflict with a globally installed .NET Core version you may have.</span></span> <span data-ttu-id="b6fad-377">Эта команда может получить псевдоним `dotnet` с помощью:</span><span class="sxs-lookup"><span data-stu-id="b6fad-377">This command can be aliased to `dotnet` with:</span></span>

```console
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="b6fad-378">Для некоторых дистрибутивов требуется дополнительный шаг, чтобы разрешить доступ к SSL-сертификату.</span><span class="sxs-lookup"><span data-stu-id="b6fad-378">Some distros require an additional step to enable access to the SSL certificate.</span></span> <span data-ttu-id="b6fad-379">Дополнительные сведения см. в разделе [Настройка для Linux](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md).</span><span class="sxs-lookup"><span data-stu-id="b6fad-379">See our [Linux Setup](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md) for details.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="b6fad-380">Поддержка GPIO для Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="b6fad-380">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="b6fad-381">В NuGet выпущено два новых пакета, которые можно использовать для программирования GPIO.</span><span class="sxs-lookup"><span data-stu-id="b6fad-381">Two new packages have been released to NuGet that you can use for GPIO programming.</span></span>

* [<span data-ttu-id="b6fad-382">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="b6fad-382">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio/0.1.0-prerelease.19078.2)
* [<span data-ttu-id="b6fad-383">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="b6fad-383">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings/0.1.0-prerelease.19078.2)

<span data-ttu-id="b6fad-384">Пакеты GPIO содержат API для устройств GPIO, SPI, I2C и PWM.</span><span class="sxs-lookup"><span data-stu-id="b6fad-384">The GPIO Packages includes APIs for GPIO, SPI, I2C and PWM devices.</span></span> <span data-ttu-id="b6fad-385">Пакет привязок Интернета вещей включает в себя [привязки устройств](https://github.com/dotnet/iot/blob/master/src/devices/README.md) для различных микросхем и датчиков, которые доступны в [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).</span><span class="sxs-lookup"><span data-stu-id="b6fad-385">The IoT bindings package includes [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) for various chips and sensors, the same ones available at [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).</span></span>

<span data-ttu-id="b6fad-386">Обновленные API последовательного порта, которые были объявлены как часть .NET Core 3.0, предварительная версия 1, не входят в эти пакеты, но доступны как часть платформы .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6fad-386">The updated serial port APIs that were announced as part of .NET Core 3.0 Preview 1 are not part of these packages but are available as part of the .NET Core platform.</span></span>


## <a name="platform-support"></a><span data-ttu-id="b6fad-387">Поддержка платформ</span><span class="sxs-lookup"><span data-stu-id="b6fad-387">Platform Support</span></span>

<span data-ttu-id="b6fad-388">.NET Core 3.0 поддерживается в следующих операционных системах:</span><span class="sxs-lookup"><span data-stu-id="b6fad-388">.NET Core 3 will be supported on the following operating systems:</span></span>

* <span data-ttu-id="b6fad-389">Windows Client: 7, 8.1, 10 (1607+)</span><span class="sxs-lookup"><span data-stu-id="b6fad-389">Windows Client: 7, 8.1, 10 (1607+)</span></span>
* <span data-ttu-id="b6fad-390">Windows Server: 2012 R2 с пакетом обновления 1 (SP1) и выше</span><span class="sxs-lookup"><span data-stu-id="b6fad-390">Windows Server: 2012 R2 SP1+</span></span>
* <span data-ttu-id="b6fad-391">macOS: 10.12+</span><span class="sxs-lookup"><span data-stu-id="b6fad-391">macOS: 10.12+</span></span>
* <span data-ttu-id="b6fad-392">RHEL: 6+</span><span class="sxs-lookup"><span data-stu-id="b6fad-392">RHEL: 6+</span></span>
* <span data-ttu-id="b6fad-393">Fedora: 26+</span><span class="sxs-lookup"><span data-stu-id="b6fad-393">Fedora: 26+</span></span>
* <span data-ttu-id="b6fad-394">Ubuntu: 16.04+</span><span class="sxs-lookup"><span data-stu-id="b6fad-394">Ubuntu: 16.04+</span></span>
* <span data-ttu-id="b6fad-395">Debian: 9+</span><span class="sxs-lookup"><span data-stu-id="b6fad-395">Debian: 9+</span></span>
* <span data-ttu-id="b6fad-396">SLES: 12+</span><span class="sxs-lookup"><span data-stu-id="b6fad-396">SLES: 12+</span></span>
* <span data-ttu-id="b6fad-397">openSUSE: 42.3+</span><span class="sxs-lookup"><span data-stu-id="b6fad-397">openSUSE: 42.3+</span></span>
* <span data-ttu-id="b6fad-398">Alpine: 3.8+</span><span class="sxs-lookup"><span data-stu-id="b6fad-398">Alpine: 3.8+</span></span>

<span data-ttu-id="b6fad-399">Поддержка микросхемы:</span><span class="sxs-lookup"><span data-stu-id="b6fad-399">Chip support follows:</span></span>

* <span data-ttu-id="b6fad-400">x64 в Windows, macOS и Linux</span><span class="sxs-lookup"><span data-stu-id="b6fad-400">x64 on Windows, macOS, and Linux</span></span>
* <span data-ttu-id="b6fad-401">x86 в Windows</span><span class="sxs-lookup"><span data-stu-id="b6fad-401">x86 on Windows</span></span>
* <span data-ttu-id="b6fad-402">ARM32 в Windows и Linux</span><span class="sxs-lookup"><span data-stu-id="b6fad-402">ARM32 on Windows and Linux</span></span>
* <span data-ttu-id="b6fad-403">ARM64 в Linux</span><span class="sxs-lookup"><span data-stu-id="b6fad-403">ARM64 on Linux</span></span>

<span data-ttu-id="b6fad-404">Для Linux ARM32 поддерживается на Debian 9+ и Ubuntu 16.04+.</span><span class="sxs-lookup"><span data-stu-id="b6fad-404">For Linux, ARM32 is supported on Debian 9+ and Ubuntu 16.04+.</span></span> <span data-ttu-id="b6fad-405">ARM64 аналогично ARM32, но с добавлением Alpine 3.8.</span><span class="sxs-lookup"><span data-stu-id="b6fad-405">For ARM64, it is the same as ARM32 with the addition of Alpine 3.8.</span></span> <span data-ttu-id="b6fad-406">Это те же версии этих дистрибутивов, что и для X64.</span><span class="sxs-lookup"><span data-stu-id="b6fad-406">These are the same versions of those distros as is supported for X64.</span></span>

<span data-ttu-id="b6fad-407">Образы Docker для .NET Core 3.0 можно найти в [microsoft/dotnet в Docker Hub](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="b6fad-407">Docker images for .NET Core 3.0 are available at [microsoft/dotnet on Docker Hub](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="b6fad-408">В настоящее время Майкрософт внедряет [реестр контейнеров Microsoft (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/), и предполагается, что окончательные образы .NET Core 3.0 будут опубликованы только в MCR.</span><span class="sxs-lookup"><span data-stu-id="b6fad-408">Microsoft is currently in the process of adopting [Microsoft Container Registry (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) and it is expected that the final .NET Core 3.0 images will only be published to MCR.</span></span>
