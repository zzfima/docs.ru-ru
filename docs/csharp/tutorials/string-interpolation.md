---
title: Интерполяция строк в C#
description: Узнайте, как включить форматированные результаты выражения в строку результатов в C# с интерполяцией строк.
author: pkulikov
ms.date: 05/09/2018
ms.openlocfilehash: 5a66ba9215579a459b543a24ece338ffbbfd9aea
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920718"
---
# <a name="string-interpolation-in-c"></a><span data-ttu-id="2b87c-103">Интерполяция строк на C\#</span><span class="sxs-lookup"><span data-stu-id="2b87c-103">String interpolation in C\#</span></span>

<span data-ttu-id="2b87c-104">В этом руководстве описано, как использовать [интерполяцию строк](../language-reference/tokens/interpolated.md) для форматирования и включения результатов выражения в строку результатов.</span><span class="sxs-lookup"><span data-stu-id="2b87c-104">This tutorial shows you how to use [string interpolation](../language-reference/tokens/interpolated.md) to format and include expression results in a result string.</span></span> <span data-ttu-id="2b87c-105">В примерах предполагается, что вам знакомы основные принципы C# и форматирования типов .NET.</span><span class="sxs-lookup"><span data-stu-id="2b87c-105">The examples assume that you are familiar with basic C# concepts and .NET type formatting.</span></span> <span data-ttu-id="2b87c-106">Если вы не знакомы с интерполяцией строк или форматированием типов .NET, сначала ознакомьтесь с [интерактивным учебником по интерполяции строк](exploration/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="2b87c-106">If you are new to string interpolation or .NET type formatting, check out the [interactive string interpolation tutorial](exploration/interpolated-strings.yml) first.</span></span> <span data-ttu-id="2b87c-107">Дополнительные сведения о форматировании типов в .NET см. в разделе [Типы форматирования в .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="2b87c-107">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) topic.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

## <a name="introduction"></a><span data-ttu-id="2b87c-108">Вступление</span><span class="sxs-lookup"><span data-stu-id="2b87c-108">Introduction</span></span>

<span data-ttu-id="2b87c-109">Функция [интерполяции строк](../language-reference/tokens/interpolated.md) создана на основе функции [составного форматирования](../../standard/base-types/composite-formatting.md) и имеет более удобный синтаксис для включения форматированных результатов выражения в строку результатов.</span><span class="sxs-lookup"><span data-stu-id="2b87c-109">The [string interpolation](../language-reference/tokens/interpolated.md) feature is built on top of the [composite formatting](../../standard/base-types/composite-formatting.md) feature and provides a more readable and convenient syntax to include formatted expression results in a result string.</span></span>

<span data-ttu-id="2b87c-110">Для определения строкового литерала в качестве интерполированной строки добавьте к началу символ `$`.</span><span class="sxs-lookup"><span data-stu-id="2b87c-110">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="2b87c-111">Вы можете внедрить любое допустимое выражение C#, возвращающее значение в интерполированной строке.</span><span class="sxs-lookup"><span data-stu-id="2b87c-111">You can embed any valid C# expression that returns a value in an interpolated string.</span></span> <span data-ttu-id="2b87c-112">В следующем примере после вычисления выражения его результат преобразуется в строку и включается в строку результатов:</span><span class="sxs-lookup"><span data-stu-id="2b87c-112">In the following example, as soon as an expression is evaluated, its result is converted into a string and included in a result string:</span></span>

[!code-csharp-interactive[string interpolation example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#1)]

<span data-ttu-id="2b87c-113">Как показано в примере, можно включить выражение в интерполированную строку, заключив его в фигурные скобки:</span><span class="sxs-lookup"><span data-stu-id="2b87c-113">As the example shows, you include an expression in an interpolated string by enclosing it with braces:</span></span>

```
{<interpolatedExpression>}
```

<span data-ttu-id="2b87c-114">Во время компиляции интерполированная строка обычно преобразуется в вызов метода <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2b87c-114">At compile time, an interpolated string is typically transformed into a <xref:System.String.Format%2A?displayProperty=nameWithType> method call.</span></span> <span data-ttu-id="2b87c-115">Так вы сможете использовать все возможности функции [составного форматирования строки](../../standard/base-types/composite-formatting.md) при работе с интерполированными строками.</span><span class="sxs-lookup"><span data-stu-id="2b87c-115">That makes all the capabilities of the [string composite formatting](../../standard/base-types/composite-formatting.md) feature available to you to use with interpolated strings as well.</span></span>

<span data-ttu-id="2b87c-116">Компилятор может заменить <xref:System.String.Format%2A?displayProperty=nameWithType> на <xref:System.String.Concat%2A?displayProperty=nameWithType>, если проанализированное поведение будет эквивалентно объединению.</span><span class="sxs-lookup"><span data-stu-id="2b87c-116">The compiler may substitute a <xref:System.String.Format%2A?displayProperty=nameWithType> for <xref:System.String.Concat%2A?displayProperty=nameWithType> if the analyzed behavior would be equivalent to concatenation.</span></span>

## <a name="how-to-specify-a-format-string-for-an-interpolated-expression"></a><span data-ttu-id="2b87c-117">Как указать строку формата для интерполированного выражения</span><span class="sxs-lookup"><span data-stu-id="2b87c-117">How to specify a format string for an interpolated expression</span></span>

<span data-ttu-id="2b87c-118">Задайте строку формата, которая поддерживается типом результата выражения, указав ее после интерполированного выражения через двоеточие:</span><span class="sxs-lookup"><span data-stu-id="2b87c-118">You specify a format string that is supported by the type of the expression result by following the interpolated expression with a colon (":") and the format string:</span></span>

```
{<interpolatedExpression>:<formatString>}
```

<span data-ttu-id="2b87c-119">В следующем примере показано, как задать стандартные и настраиваемые строки формата для выражений, возвращающих дату и время или числовые результаты:</span><span class="sxs-lookup"><span data-stu-id="2b87c-119">The following example shows how to specify standard and custom format strings for expressions that produce date and time or numeric results:</span></span>

[!code-csharp-interactive[format string example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#2)]

<span data-ttu-id="2b87c-120">Дополнительные сведения см. в разделе [Компонент строки формата](../../standard/base-types/composite-formatting.md#format-string-component) в статье [Составное форматирование](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2b87c-120">For more information, see the [Format String Component](../../standard/base-types/composite-formatting.md#format-string-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span> <span data-ttu-id="2b87c-121">Этот раздел содержит ссылки на разделы, описывающие стандартные и настраиваемые строки формата, поддерживаемые базовыми типами .NET.</span><span class="sxs-lookup"><span data-stu-id="2b87c-121">That section provides links to the topics that describe standard and custom format strings supported by .NET base types.</span></span>

## <a name="how-to-control-the-field-width-and-alignment-of-the-formatted-interpolated-expression"></a><span data-ttu-id="2b87c-122">Управление шириной поля и выравниванием в форматированных интерполированных выражениях</span><span class="sxs-lookup"><span data-stu-id="2b87c-122">How to control the field width and alignment of the formatted interpolated expression</span></span>

<span data-ttu-id="2b87c-123">Задайте минимальную ширину поля и выравнивание форматированного результата выражения, указав константное выражение после интерполированного выражения через запятую:</span><span class="sxs-lookup"><span data-stu-id="2b87c-123">You specify the minimum field width and the alignment of the formatted expression result by following the interpolated expression with a comma (",") and the constant expression:</span></span>

```
{<interpolatedExpression>,<alignment>}
```

<span data-ttu-id="2b87c-124">Если значение *alignment* положительное, форматированное выражение будет выровнено по правому краю, а если отрицательное — по левому.</span><span class="sxs-lookup"><span data-stu-id="2b87c-124">If the *alignment* value is positive, the formatted expression result is right-aligned; if negative, it's left-aligned.</span></span>

<span data-ttu-id="2b87c-125">Если вам нужно задать и выравнивание, и строку формата, начните с компонента выравнивания:</span><span class="sxs-lookup"><span data-stu-id="2b87c-125">If you need to specify both alignment and a format string, start with the alignment component:</span></span>

```
{<interpolatedExpression>,<alignment>:<formatString>}
```

<span data-ttu-id="2b87c-126">В следующем примере показано, как задать выравнивание. Текстовые поля разграничены символом вертикальной черты ("|"):</span><span class="sxs-lookup"><span data-stu-id="2b87c-126">The following example shows how to specify alignment and uses pipe characters ("|") to delimit text fields:</span></span>

[!code-csharp-interactive[alignment example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#3)]

<span data-ttu-id="2b87c-127">В выходных данных в примере видно, что если длина форматированного результата выражения превышает заданную ширину поля, значение *alignment* игнорируется.</span><span class="sxs-lookup"><span data-stu-id="2b87c-127">As the example output shows, if the length of the formatted expression result exceeds specified field width, the *alignment* value is ignored.</span></span>

<span data-ttu-id="2b87c-128">Дополнительные сведения см. в разделе [Компонент выравнивания](../../standard/base-types/composite-formatting.md#alignment-component) в статье [Составное форматирование](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2b87c-128">For more information, see the [Alignment Component](../../standard/base-types/composite-formatting.md#alignment-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

## <a name="how-to-use-escape-sequences-in-an-interpolated-string"></a><span data-ttu-id="2b87c-129">Как использовать escape-последовательности в интерполированной строке</span><span class="sxs-lookup"><span data-stu-id="2b87c-129">How to use escape sequences in an interpolated string</span></span>

<span data-ttu-id="2b87c-130">Интерполированные строки поддерживают все escape-последовательности, которые могут использоваться в обычных строковых литералах.</span><span class="sxs-lookup"><span data-stu-id="2b87c-130">Interpolated strings support all escape sequences that can be used in ordinary string literals.</span></span> <span data-ttu-id="2b87c-131">Дополнительные сведения см. в статье [Escape-последовательности строки](../programming-guide/strings/index.md#string-escape-sequences).</span><span class="sxs-lookup"><span data-stu-id="2b87c-131">For more information, see [String escape sequences](../programming-guide/strings/index.md#string-escape-sequences).</span></span>

<span data-ttu-id="2b87c-132">Для литеральной интерпретации escape-последовательности используйте строковый литерал [verbatim](../language-reference/tokens/verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="2b87c-132">To interpret escape sequences literally, use a [verbatim](../language-reference/tokens/verbatim.md) string literal.</span></span> <span data-ttu-id="2b87c-133">В интерполированных строках verbatim используется символ `$`, за которым следует символ `@`.</span><span class="sxs-lookup"><span data-stu-id="2b87c-133">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span>

<span data-ttu-id="2b87c-134">В строке результатов указывайте двойную фигурную скобку "{{" или "}}".</span><span class="sxs-lookup"><span data-stu-id="2b87c-134">To include a brace, "{" or "}", in a result string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="2b87c-135">Дополнительные сведения см. в разделе [escape-скобки](../../standard/base-types/composite-formatting.md#escaping-braces) в статье [Составное форматирование](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2b87c-135">For more information, see the [Escaping Braces](../../standard/base-types/composite-formatting.md#escaping-braces) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

<span data-ttu-id="2b87c-136">В следующем примере показано, как включить фигурные скобки в строку результата и создать интерполированную строку verbatim:</span><span class="sxs-lookup"><span data-stu-id="2b87c-136">The following example shows how to include braces in a result string and construct a verbatim interpolated string:</span></span>

[!code-csharp-interactive[escape sequence example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#4)]

## <a name="how-to-use-a-ternary-conditional-operator--in-an-interpolated-expression"></a><span data-ttu-id="2b87c-137">Как использовать троичный условный оператор `?:` в интерполированном выражении</span><span class="sxs-lookup"><span data-stu-id="2b87c-137">How to use a ternary conditional operator `?:` in an interpolated expression</span></span>

<span data-ttu-id="2b87c-138">Двоеточие (:) имеет особое значение в элементе интерполированного выражения. Чтобы использовать [условный оператор](../language-reference/operators/conditional-operator.md) в выражении, заключите это выражение в скобки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="2b87c-138">As the colon (":") has special meaning in an item with an interpolated expression, in order to use a [conditional operator](../language-reference/operators/conditional-operator.md) in an expression, enclose it in parentheses, as the following example shows:</span></span>

[!code-csharp-interactive[conditional operator example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#5)]

## <a name="how-to-create-a-culture-specific-result-string-with-string-interpolation"></a><span data-ttu-id="2b87c-139">Создание строки результата с интерполяцией для определенного языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="2b87c-139">How to create a culture-specific result string with string interpolation</span></span>

<span data-ttu-id="2b87c-140">По умолчанию в интерполированной строке используется текущий язык и региональные параметры, определяемые свойством <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> для всех операций форматирования.</span><span class="sxs-lookup"><span data-stu-id="2b87c-140">By default, an interpolated string uses the current culture defined by the <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> property for all formatting operations.</span></span> <span data-ttu-id="2b87c-141">Используйте неявное преобразование интерполированной строки для экземпляра <xref:System.FormattableString?displayProperty=nameWithType> и вызовите метод <xref:System.FormattableString.ToString(System.IFormatProvider)>, чтобы создать строку результата с определенным языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="2b87c-141">Use implicit conversion of an interpolated string to a <xref:System.FormattableString?displayProperty=nameWithType> instance and call its <xref:System.FormattableString.ToString(System.IFormatProvider)> method to create a culture-specific result string.</span></span> <span data-ttu-id="2b87c-142">Следующий пример показывает, как это сделать:</span><span class="sxs-lookup"><span data-stu-id="2b87c-142">The following example shows how to do that:</span></span>

[!code-csharp-interactive[specify different cultures](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#6)]

<span data-ttu-id="2b87c-143">Как показано в примере, можно использовать один экземпляр <xref:System.FormattableString> для создания нескольких строк результата для различных языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="2b87c-143">As the example shows, you can use one <xref:System.FormattableString> instance to generate multiple result strings for various cultures.</span></span>

## <a name="how-to-create-a-result-string-using-the-invariant-culture"></a><span data-ttu-id="2b87c-144">Как создать строку результата с помощью инвариантного языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="2b87c-144">How to create a result string using the invariant culture</span></span>

<span data-ttu-id="2b87c-145">Наряду с методом <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> можно использовать статический метод <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType>, чтобы разрешить интерполированную строку в строке результата для <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="2b87c-145">Along with the <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> method, you can use the static <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> method to resolve an interpolated string to a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span> <span data-ttu-id="2b87c-146">Следующий пример показывает, как это сделать:</span><span class="sxs-lookup"><span data-stu-id="2b87c-146">The following example shows how to do that:</span></span>

[!code-csharp-interactive[format with invariant culture](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#7)]

## <a name="conclusion"></a><span data-ttu-id="2b87c-147">Заключение</span><span class="sxs-lookup"><span data-stu-id="2b87c-147">Conclusion</span></span>

<span data-ttu-id="2b87c-148">В этом руководстве описаны распространенные сценарии использования интерполяции строк.</span><span class="sxs-lookup"><span data-stu-id="2b87c-148">This tutorial describes common scenarios of string interpolation usage.</span></span> <span data-ttu-id="2b87c-149">Дополнительные сведения об интерполяции строк см. в разделе [Интерполяция строк](../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="2b87c-149">For more information about string interpolation, see the [String interpolation](../language-reference/tokens/interpolated.md) topic.</span></span> <span data-ttu-id="2b87c-150">Дополнительные сведения о форматировании типов в .NET см. в разделах [Типы форматирования в .NET](../../standard/base-types/formatting-types.md) и [Составное форматирование](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2b87c-150">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) and [Composite formatting](../../standard/base-types/composite-formatting.md) topics.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b87c-151">См. также</span><span class="sxs-lookup"><span data-stu-id="2b87c-151">See also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [<span data-ttu-id="2b87c-152">Строки</span><span class="sxs-lookup"><span data-stu-id="2b87c-152">Strings</span></span>](../programming-guide/strings/index.md)
