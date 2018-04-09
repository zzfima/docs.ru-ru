---
title: $ — интерполяция строк (справочник по C#)
description: Интерполяция строк предоставляет более понятный и удобный синтаксис для форматирования строковых выходных данных, чем традиционное составное форматирование строк.
ms.date: 03/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6873c3b419323fa9f5523143ad607289b6fd6e2
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="02d96-103">$ — интерполяция строк (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="02d96-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="02d96-104">Специальный знак `$` идентифицирует строковый литерал как *интерполированную строку*.</span><span class="sxs-lookup"><span data-stu-id="02d96-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="02d96-105">Интерполированное строковое выражение выглядит как строка шаблона, которая содержит *интерполированные выражения*.</span><span class="sxs-lookup"><span data-stu-id="02d96-105">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span> <span data-ttu-id="02d96-106">При разрешении интерполированной строки, например в операторе присваивания или вызове метода, интерполированные выражения заменяются строковыми представлениями их результатов для создания результирующей строки.</span><span class="sxs-lookup"><span data-stu-id="02d96-106">When the interpolated string is resolved, for example in an assignment statement or a method call, interpolated expressions are replaced by the string representations of their results to produce the result string.</span></span> <span data-ttu-id="02d96-107">Эта возможность доступна в C# 6 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="02d96-107">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="02d96-108">Интерполяция строк предоставляет более понятный и удобный способ для создания форматированных строк по сравнению с функцией [составного форматирования строк](../../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="02d96-108">String interpolation is a more readable and convenient way to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="02d96-109">В следующем примере обе этих функции используются для получения одинаковых выходных данных:</span><span class="sxs-lookup"><span data-stu-id="02d96-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

> [!NOTE]
> <span data-ttu-id="02d96-110">Между `$` и `"` в начале строки не может быть пробела.</span><span class="sxs-lookup"><span data-stu-id="02d96-110">You cannot have any white space between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="02d96-111">Это приводит к ошибке времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="02d96-111">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="02d96-112">Структура элемента с интерполированным выражением выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="02d96-112">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="02d96-113">Элементы в квадратных скобках являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="02d96-113">Elements in square brackets are optional.</span></span> <span data-ttu-id="02d96-114">Каждый из элементов описан в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="02d96-114">The following table describes each element.</span></span>

|<span data-ttu-id="02d96-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="02d96-115">Element</span></span>|<span data-ttu-id="02d96-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="02d96-116">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="02d96-117">Выражение, вычисляемое для получения форматируемого результата.</span><span class="sxs-lookup"><span data-stu-id="02d96-117">The expression to evaluate to get a result to be formatted.</span></span> <span data-ttu-id="02d96-118">Строковым представлением результата `null` является <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="02d96-118">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="02d96-119">Константное выражение, значение которого определяет минимальное число символов в строковом представлении результата интерполированного выражения.</span><span class="sxs-lookup"><span data-stu-id="02d96-119">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="02d96-120">Если оно положительное, строковое представление выравнивается по правому краю, если отрицательное — по левому краю.</span><span class="sxs-lookup"><span data-stu-id="02d96-120">If positive, the string representation is right-aligned; if negative, it is left-aligned.</span></span> <span data-ttu-id="02d96-121">Дополнительные сведения см. в разделе [Компонент выравнивания](../../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="02d96-121">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="02d96-122">Стандартная или пользовательская строка форматирования, поддерживаемая типом результата выражения.</span><span class="sxs-lookup"><span data-stu-id="02d96-122">A standard or custom format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="02d96-123">Дополнительные сведения см. в разделе [Компонент строки форматирования](../../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="02d96-123">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="02d96-124">Следующий пример использует необязательные компоненты форматирования, описанные в приведенной выше таблице:</span><span class="sxs-lookup"><span data-stu-id="02d96-124">The following example uses optional formatting components described in the table above:</span></span>

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

<span data-ttu-id="02d96-125">Чтобы включить в текст, создаваемый интерполированной строкой, фигурную скобку ("{" или "}"), используйте две фигурные скобки — "{{" или "}}".</span><span class="sxs-lookup"><span data-stu-id="02d96-125">To include a curly brace ("{" or "}") in the text produced by an interpolated string, use two curly braces, "{{" or "}}".</span></span> <span data-ttu-id="02d96-126">Подробнее см. в разделе [Экранирование фигурных скобок](../../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="02d96-126">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="02d96-127">Двоеточие (:) имеет особое значение в элемент интерполированного выражения. Чтобы использовать [условный оператор](../operators/conditional-operator.md) в интерполированном выражении, заключите это выражение в скобки.</span><span class="sxs-lookup"><span data-stu-id="02d96-127">As the colon (:) has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="02d96-128">В следующем примере показано, как включить фигурную скобку в результирующую строку, а также использовать условный оператор в интерполированном выражении:</span><span class="sxs-lookup"><span data-stu-id="02d96-128">The following example shows how to include a curly brace into the result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="02d96-129">В интерполированных строках Verbatim используется символ `$`, за которым следует символ `@`.</span><span class="sxs-lookup"><span data-stu-id="02d96-129">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="02d96-130">Дополнительные сведения о строках Verbatim см. в разделе о [строках](../keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="02d96-130">For more information about verbatim strings, see the [string](../keywords/string.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="02d96-131">В интерполированной строке Verbatim токен `$` должен находиться перед токеном `@`.</span><span class="sxs-lookup"><span data-stu-id="02d96-131">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions"></a><span data-ttu-id="02d96-132">Неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="02d96-132">Implicit conversions</span></span>

<span data-ttu-id="02d96-133">Существует три преобразования неявных типов из интерполированных строк.</span><span class="sxs-lookup"><span data-stu-id="02d96-133">There are three implicit type conversions from an interpolated string:</span></span>

1. <span data-ttu-id="02d96-134">Преобразование интерполированной строки в экземпляр <xref:System.String>, являющийся результатом разрешения интерполированной строки, где элементы интерполированного выражения заменяются на должным образом форматированные строковые представления их результатов.</span><span class="sxs-lookup"><span data-stu-id="02d96-134">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="02d96-135">Это преобразование использует текущие значения языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="02d96-135">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="02d96-136">Преобразование интерполированной строки в переменную <xref:System.FormattableString>, представляющую строку составного формата, а также форматируемые результаты выражения.</span><span class="sxs-lookup"><span data-stu-id="02d96-136">Conversion of an interpolated string to a <xref:System.FormattableString> variable that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="02d96-137">Это позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.FormattableString>.</span><span class="sxs-lookup"><span data-stu-id="02d96-137">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="02d96-138">Для этого вызовите один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="02d96-138">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="02d96-139">Перегрузка <xref:System.FormattableString.ToString>, которая формирует результирующую строку для <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="02d96-139">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="02d96-140">Метод <xref:System.FormattableString.Invariant%2A>, который формирует результирующую строку для <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="02d96-140">A <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="02d96-141">Метод <xref:System.FormattableString.ToString(System.IFormatProvider)>, который формирует результирующую строку для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="02d96-141">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

1. <span data-ttu-id="02d96-142">Преобразование интерполированной строки в переменную <xref:System.IFormattable>, которая также позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="02d96-142">Conversion of an interpolated string to an <xref:System.IFormattable> variable that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="02d96-143">Следующий пример использует неявное преобразование в <xref:System.FormattableString> для создания результирующих строк для конкретного языка:</span><span class="sxs-lookup"><span data-stu-id="02d96-143">The following example uses implicit conversion to <xref:System.FormattableString> for creating culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-reading"></a><span data-ttu-id="02d96-144">Дополнительные материалы для чтения</span><span class="sxs-lookup"><span data-stu-id="02d96-144">Additional reading</span></span>

<span data-ttu-id="02d96-145">Если вы не знакомы с интерполяцией строк, ознакомьтесь с [кратким руководством](../../quick-starts//interpolated-strings.yml) по ней.</span><span class="sxs-lookup"><span data-stu-id="02d96-145">If you are new to the string interpolation, check the [interpolated strings quickstart](../../quick-starts//interpolated-strings.yml).</span></span> <span data-ttu-id="02d96-146">Дополнительные сведения см. в [учебнике по интерполяции строк](../../tutorials/string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="02d96-146">For more examples, see the [string interpolation tutorial](../../tutorials/string-interpolation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="02d96-147">См. также</span><span class="sxs-lookup"><span data-stu-id="02d96-147">See also</span></span>  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [<span data-ttu-id="02d96-148">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="02d96-148">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)  
 [<span data-ttu-id="02d96-149">Строки</span><span class="sxs-lookup"><span data-stu-id="02d96-149">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="02d96-150">Специальные символы в C#</span><span class="sxs-lookup"><span data-stu-id="02d96-150">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)  
 [<span data-ttu-id="02d96-151">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="02d96-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="02d96-152">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="02d96-152">C# Reference</span></span>](../../../csharp/language-reference/index.md)  