---
title: Справочник по C#. $ — интерполяция строк
ms.custom: seodec18
description: Интерполяция строк предоставляет более понятный и удобный синтаксис для форматирования строковых выходных данных, чем традиционное составное форматирование строк.
ms.date: 04/29/2019
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.author: ronpet
ms.openlocfilehash: bc27eedcf1957a109a9bcb80cf9a49e9606921fd
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251002"
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="668b0-103">$ — интерполяция строк (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="668b0-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="668b0-104">Специальный знак `$` идентифицирует строковый литерал как *интерполированную строку*.</span><span class="sxs-lookup"><span data-stu-id="668b0-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="668b0-105">Интерполированная строка — это строковый литерал, который может содержать *выражения интерполяции*.</span><span class="sxs-lookup"><span data-stu-id="668b0-105">An interpolated string is a string literal that might contain *interpolation expressions*.</span></span> <span data-ttu-id="668b0-106">При разрешении интерполированной строки в результирующую элементы с выражениями интерполяции заменяются строковыми представлениями результатов выражений.</span><span class="sxs-lookup"><span data-stu-id="668b0-106">When an interpolated string is resolved to a result string, items with interpolation expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="668b0-107">Эта возможность доступна в C# 6 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="668b0-107">This feature is available in C# 6 and later versions of the language.</span></span>

<span data-ttu-id="668b0-108">Интерполяция строк предоставляет более понятный и удобный синтаксис для создания форматированных строк по сравнению с функцией [составного форматирования строк](../../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="668b0-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="668b0-109">В следующем примере обе этих функции используются для получения одинаковых выходных данных:</span><span class="sxs-lookup"><span data-stu-id="668b0-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a><span data-ttu-id="668b0-110">Структура интерполированной строки</span><span class="sxs-lookup"><span data-stu-id="668b0-110">Structure of an interpolated string</span></span>

<span data-ttu-id="668b0-111">Для определения строкового литерала в качестве интерполированной строки добавьте к началу символ `$`.</span><span class="sxs-lookup"><span data-stu-id="668b0-111">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="668b0-112">Между `$` и `"` в начале строкового литерала не может быть пробела.</span><span class="sxs-lookup"><span data-stu-id="668b0-112">You cannot have any white space between the `$` and the `"` that starts a string literal.</span></span> <span data-ttu-id="668b0-113">Это приводит к ошибке времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="668b0-113">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="668b0-114">Структура элемента с выражением интерполяции выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="668b0-114">The structure of an item with an interpolation expression is as follows:</span></span>

```
{<interpolationExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="668b0-115">Элементы в квадратных скобках являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="668b0-115">Elements in square brackets are optional.</span></span> <span data-ttu-id="668b0-116">Каждый из элементов описан в таблице ниже:</span><span class="sxs-lookup"><span data-stu-id="668b0-116">The following table describes each element:</span></span>

|<span data-ttu-id="668b0-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="668b0-117">Element</span></span>|<span data-ttu-id="668b0-118">Описание</span><span class="sxs-lookup"><span data-stu-id="668b0-118">Description</span></span>|
|-------------|-----------------|
|`interpolationExpression`|<span data-ttu-id="668b0-119">Выражение, создающее форматируемый результат.</span><span class="sxs-lookup"><span data-stu-id="668b0-119">The expression that produces a result to be formatted.</span></span> <span data-ttu-id="668b0-120">Строковым представлением результата `null` является <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="668b0-120">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="668b0-121">Константное выражение, значение которого определяет минимальное число символов в строковом представлении результата выражения интерполяции.</span><span class="sxs-lookup"><span data-stu-id="668b0-121">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolation expression.</span></span> <span data-ttu-id="668b0-122">Если оно положительное, строковое представление выравнивается по правому краю, если отрицательное — по левому краю.</span><span class="sxs-lookup"><span data-stu-id="668b0-122">If positive, the string representation is right-aligned; if negative, it's left-aligned.</span></span> <span data-ttu-id="668b0-123">Дополнительные сведения см. в разделе [Компонент выравнивания](../../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="668b0-123">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="668b0-124">Строка форматирования, поддерживаемая типом результата выражения.</span><span class="sxs-lookup"><span data-stu-id="668b0-124">A format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="668b0-125">Дополнительные сведения см. в разделе [Компонент строки форматирования](../../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="668b0-125">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="668b0-126">В следующем примере используются необязательные компоненты форматирования, описанные выше:</span><span class="sxs-lookup"><span data-stu-id="668b0-126">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a><span data-ttu-id="668b0-127">Специальные символы</span><span class="sxs-lookup"><span data-stu-id="668b0-127">Special characters</span></span>

<span data-ttu-id="668b0-128">Чтобы включить в текст, создаваемый интерполированной строкой, фигурную скобку "{" или "}", используйте две фигурные скобки — "{{" или "}}".</span><span class="sxs-lookup"><span data-stu-id="668b0-128">To include a brace, "{" or "}", in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="668b0-129">Подробнее см. в разделе [Экранирование фигурных скобок](../../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="668b0-129">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="668b0-130">Двоеточие (:) имеет особое значение в элементе выражения интерполяции. Чтобы использовать [условный оператор](../operators/conditional-operator.md) в выражении интерполяции, заключите это выражение в скобки.</span><span class="sxs-lookup"><span data-stu-id="668b0-130">As the colon (":") has special meaning in an interpolation expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolation expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="668b0-131">В следующем примере показано, как включить фигурную скобку в результирующую строку, а также использовать условный оператор в выражении интерполяции:</span><span class="sxs-lookup"><span data-stu-id="668b0-131">The following example shows how to include a brace in a result string and how to use a conditional operator in an interpolation expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="668b0-132">В буквальных интерполированных строках используется символ `$`, за которым следует символ `@`.</span><span class="sxs-lookup"><span data-stu-id="668b0-132">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="668b0-133">Дополнительные сведения о буквальных строках см. в разделах о [строках](../keywords/string.md) и [буквальном идентификаторе](verbatim.md)).</span><span class="sxs-lookup"><span data-stu-id="668b0-133">For more information about verbatim strings, see the [string](../keywords/string.md) and [verbatim identifier](verbatim.md) topics.</span></span>

> [!NOTE]
> <span data-ttu-id="668b0-134">В буквальной интерполированной строке токен `$` должен находиться перед токеном `@`.</span><span class="sxs-lookup"><span data-stu-id="668b0-134">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a><span data-ttu-id="668b0-135">Неявные преобразования и указание реализации `IFormatProvider`</span><span class="sxs-lookup"><span data-stu-id="668b0-135">Implicit conversions and specifying `IFormatProvider` implementation</span></span>

<span data-ttu-id="668b0-136">Существует три неявных преобразования из интерполированных строк.</span><span class="sxs-lookup"><span data-stu-id="668b0-136">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="668b0-137">Преобразование интерполированной строки в экземпляр <xref:System.String>, являющийся результатом разрешения интерполированной строки, где элементы выражения интерполяции заменяются на должным образом форматированные строковые представления их результатов.</span><span class="sxs-lookup"><span data-stu-id="668b0-137">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolation expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="668b0-138">Это преобразование использует текущие значения языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="668b0-138">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="668b0-139">Преобразование интерполированной строки в экземпляр <xref:System.FormattableString>, представляющий строку составного формата, а также форматируемые результаты выражения.</span><span class="sxs-lookup"><span data-stu-id="668b0-139">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="668b0-140">Это позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.FormattableString>.</span><span class="sxs-lookup"><span data-stu-id="668b0-140">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="668b0-141">Для этого вызовите один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="668b0-141">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="668b0-142">Перегрузка <xref:System.FormattableString.ToString>, которая формирует результирующую строку для <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="668b0-142">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="668b0-143">Метод <xref:System.FormattableString.Invariant%2A>, который формирует результирующую строку для <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="668b0-143">An <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="668b0-144">Метод <xref:System.FormattableString.ToString(System.IFormatProvider)>, который формирует результирующую строку для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="668b0-144">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

    <span data-ttu-id="668b0-145">Также можно использовать метод <xref:System.FormattableString.ToString(System.IFormatProvider)>, чтобы предоставить пользовательские реализации интерфейса <xref:System.IFormatProvider>, который поддерживает настраиваемое форматирование.</span><span class="sxs-lookup"><span data-stu-id="668b0-145">You also can use the <xref:System.FormattableString.ToString(System.IFormatProvider)> method to provide a user-defined implementation of the <xref:System.IFormatProvider> interface that supports custom formatting.</span></span> <span data-ttu-id="668b0-146">Дополнительные сведения см. в разделе [Настраиваемое форматирование с использованием интерфейса ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span><span class="sxs-lookup"><span data-stu-id="668b0-146">For more information, see [Custom Formatting with ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span></span>

1. <span data-ttu-id="668b0-147">Преобразование интерполированной строки в экземпляр <xref:System.IFormattable>, который также позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="668b0-147">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="668b0-148">В следующем примере используется неявное преобразование в <xref:System.FormattableString> для создания результирующих строк для конкретного языка:</span><span class="sxs-lookup"><span data-stu-id="668b0-148">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a><span data-ttu-id="668b0-149">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="668b0-149">Additional resources</span></span>

<span data-ttu-id="668b0-150">Если вы не знакомы с интерполяцией строк, ознакомьтесь с интерактивным руководством [по интерполяции строк в C#](../../tutorials/exploration/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="668b0-150">If you are new to string interpolation, see the [String interpolation in C#](../../tutorials/exploration/interpolated-strings.yml) interactive tutorial.</span></span> <span data-ttu-id="668b0-151">Вы также можете изучить другой учебник, [Интерполяция строк в C# ](../../tutorials/string-interpolation.md), в котором показано, как использовать интерполированные строки для форматирования.</span><span class="sxs-lookup"><span data-stu-id="668b0-151">You also can check another [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial that demonstrates how to use interpolated strings to produce formatted strings.</span></span>

## <a name="compilation-of-interpolated-strings"></a><span data-ttu-id="668b0-152">Компиляция интерполированных строк</span><span class="sxs-lookup"><span data-stu-id="668b0-152">Compilation of interpolated strings</span></span>

<span data-ttu-id="668b0-153">Если интерполированная строка имеет тип `string`, обычно она преобразуется в вызов метода <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="668b0-153">If an interpolated string has the type `string`, it's typically transformed into a <xref:System.String.Format%2A?displayProperty=nameWithType> method call.</span></span> <span data-ttu-id="668b0-154">Компилятор может заменить <xref:System.String.Format%2A?displayProperty=nameWithType> на <xref:System.String.Concat%2A?displayProperty=nameWithType>, если проанализированное поведение будет эквивалентно объединению.</span><span class="sxs-lookup"><span data-stu-id="668b0-154">The compiler may replace <xref:System.String.Format%2A?displayProperty=nameWithType> with <xref:System.String.Concat%2A?displayProperty=nameWithType> if the analyzed behavior would be equivalent to concatenation.</span></span>

<span data-ttu-id="668b0-155">Если интерполированная строка имеет тип <xref:System.IFormattable> или <xref:System.FormattableString>, компилятор создает вызов метода <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="668b0-155">If an interpolated string has the type <xref:System.IFormattable> or <xref:System.FormattableString>, the compiler generates a call to the <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType> method.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="668b0-156">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="668b0-156">C# language specification</span></span>

<span data-ttu-id="668b0-157">Дополнительные сведения см. в разделе [Интерполированные строки](~/_csharplang/spec/expressions.md#interpolated-strings) [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="668b0-157">For more information, see the [Interpolated strings](~/_csharplang/spec/expressions.md#interpolated-strings) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="668b0-158">См. также</span><span class="sxs-lookup"><span data-stu-id="668b0-158">See also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [<span data-ttu-id="668b0-159">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="668b0-159">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="668b0-160">Таблица форматирования числовых результатов</span><span class="sxs-lookup"><span data-stu-id="668b0-160">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="668b0-161">Строки</span><span class="sxs-lookup"><span data-stu-id="668b0-161">Strings</span></span>](../../programming-guide/strings/index.md)
- [<span data-ttu-id="668b0-162">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="668b0-162">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="668b0-163">Специальные символы в C#</span><span class="sxs-lookup"><span data-stu-id="668b0-163">C# Special Characters</span></span>](index.md)
- [<span data-ttu-id="668b0-164">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="668b0-164">C# Reference</span></span>](../index.md)
