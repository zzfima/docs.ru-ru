---
title: Справочник по C#. Таблица форматирования числовых результатов
description: Сведения об использовании строк стандартных числовых форматов C#
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: eb93f0a4f3c66e9f7b295366a77b9fb099fc3a1e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713511"
---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="20957-103">Таблица форматирования числовых результатов (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="20957-103">Formatting numeric results table (C# Reference)</span></span>

<span data-ttu-id="20957-104">В следующей таблице приводятся описатели поддерживаемых форматов для форматирования числовых результатов.</span><span class="sxs-lookup"><span data-stu-id="20957-104">The following table shows supported format specifiers for formatting numeric results.</span></span> <span data-ttu-id="20957-105">Форматированный результат в последнем столбце соответствует формату "en-US" (<xref:System.Globalization.CultureInfo>).</span><span class="sxs-lookup"><span data-stu-id="20957-105">The formatted result in the last column corresponds to the "en-US" <xref:System.Globalization.CultureInfo>.</span></span>

|<span data-ttu-id="20957-106">Описатель формата</span><span class="sxs-lookup"><span data-stu-id="20957-106">Format specifier</span></span>|<span data-ttu-id="20957-107">Описание</span><span class="sxs-lookup"><span data-stu-id="20957-107">Description</span></span>|<span data-ttu-id="20957-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="20957-108">Examples</span></span>|<span data-ttu-id="20957-109">Результат</span><span class="sxs-lookup"><span data-stu-id="20957-109">Result</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="20957-110">C или c</span><span class="sxs-lookup"><span data-stu-id="20957-110">C or c</span></span>|<span data-ttu-id="20957-111">Валюта</span><span class="sxs-lookup"><span data-stu-id="20957-111">Currency</span></span>|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|<span data-ttu-id="20957-112">\\$2.50</span><span class="sxs-lookup"><span data-stu-id="20957-112">\\$2.50</span></span><br /><br /> <span data-ttu-id="20957-113">(\\$2.50)</span><span class="sxs-lookup"><span data-stu-id="20957-113">(\\$2.50)</span></span>|  
|<span data-ttu-id="20957-114">D или d</span><span class="sxs-lookup"><span data-stu-id="20957-114">D or d</span></span>|<span data-ttu-id="20957-115">Decimal</span><span class="sxs-lookup"><span data-stu-id="20957-115">Decimal</span></span>|`string s = $"{25:D5}";`|<span data-ttu-id="20957-116">00025</span><span class="sxs-lookup"><span data-stu-id="20957-116">00025</span></span>|  
|<span data-ttu-id="20957-117">E или e</span><span class="sxs-lookup"><span data-stu-id="20957-117">E or e</span></span>|<span data-ttu-id="20957-118">Экспоненциальный</span><span class="sxs-lookup"><span data-stu-id="20957-118">Exponential</span></span>|`string s = $"{250000:E2}";`|<span data-ttu-id="20957-119">2.50E+005</span><span class="sxs-lookup"><span data-stu-id="20957-119">2.50E+005</span></span>|  
|<span data-ttu-id="20957-120">F или f</span><span class="sxs-lookup"><span data-stu-id="20957-120">F or f</span></span>|<span data-ttu-id="20957-121">С фиксированной запятой</span><span class="sxs-lookup"><span data-stu-id="20957-121">Fixed-point</span></span>|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|<span data-ttu-id="20957-122">2.50</span><span class="sxs-lookup"><span data-stu-id="20957-122">2.50</span></span><br /><br /> <span data-ttu-id="20957-123">3</span><span class="sxs-lookup"><span data-stu-id="20957-123">3</span></span>|  
|<span data-ttu-id="20957-124">G или g</span><span class="sxs-lookup"><span data-stu-id="20957-124">G or g</span></span>|<span data-ttu-id="20957-125">Общее</span><span class="sxs-lookup"><span data-stu-id="20957-125">General</span></span>|`string s = $"{2.5:G}";`|<span data-ttu-id="20957-126">2.5</span><span class="sxs-lookup"><span data-stu-id="20957-126">2.5</span></span>|  
|<span data-ttu-id="20957-127">N или n</span><span class="sxs-lookup"><span data-stu-id="20957-127">N or n</span></span>|<span data-ttu-id="20957-128">Numeric</span><span class="sxs-lookup"><span data-stu-id="20957-128">Numeric</span></span>|`string s = $"{2500000:N}";`|<span data-ttu-id="20957-129">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="20957-129">2,500,000.00</span></span>|  
|<span data-ttu-id="20957-130">P или p</span><span class="sxs-lookup"><span data-stu-id="20957-130">P or p</span></span>|<span data-ttu-id="20957-131">Процент</span><span class="sxs-lookup"><span data-stu-id="20957-131">Percent</span></span>|`string s = $"{0.25:P}";`|<span data-ttu-id="20957-132">25.00%</span><span class="sxs-lookup"><span data-stu-id="20957-132">25.00%</span></span>|  
|<span data-ttu-id="20957-133">R или r</span><span class="sxs-lookup"><span data-stu-id="20957-133">R or r</span></span>|<span data-ttu-id="20957-134">Приемо-передача</span><span class="sxs-lookup"><span data-stu-id="20957-134">Round-trip</span></span>|`string s = $"{2.5:R}";`|<span data-ttu-id="20957-135">2.5</span><span class="sxs-lookup"><span data-stu-id="20957-135">2.5</span></span>|  
|<span data-ttu-id="20957-136">X или x</span><span class="sxs-lookup"><span data-stu-id="20957-136">X or x</span></span>|<span data-ttu-id="20957-137">Шестнадцатеричный</span><span class="sxs-lookup"><span data-stu-id="20957-137">Hexadecimal</span></span>|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|<span data-ttu-id="20957-138">FA</span><span class="sxs-lookup"><span data-stu-id="20957-138">FA</span></span><br /><br /> <span data-ttu-id="20957-139">FFFF</span><span class="sxs-lookup"><span data-stu-id="20957-139">FFFF</span></span>|  

## <a name="remarks"></a><span data-ttu-id="20957-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="20957-140">Remarks</span></span>

<span data-ttu-id="20957-141">Для создания строки формата используйте описатель формата.</span><span class="sxs-lookup"><span data-stu-id="20957-141">You use a format specifier to create a format string.</span></span> <span data-ttu-id="20957-142">Строка формата имеет вид `Axx`:</span><span class="sxs-lookup"><span data-stu-id="20957-142">The format string is of the following form: `Axx`, where</span></span>

- <span data-ttu-id="20957-143">где `A` — это описатель формата, который управляет типом форматирования, применяемым к числовому значению;</span><span class="sxs-lookup"><span data-stu-id="20957-143">`A` is the format specifier, which controls the type of formatting applied to the numeric value.</span></span>
- <span data-ttu-id="20957-144">а `xx` — указатель точности, который влияет на количество цифр в форматированном выводе.</span><span class="sxs-lookup"><span data-stu-id="20957-144">`xx` is the precision specifier, which affects the number of digits in the formatted output.</span></span> <span data-ttu-id="20957-145">Значение описателя точности находится в диапазоне от 0 до 99.</span><span class="sxs-lookup"><span data-stu-id="20957-145">The value of the precision specifier ranges from 0 to 99.</span></span>

<span data-ttu-id="20957-146">Описатели десятичного ("D" или "d") и шестнадцатеричного форматов ("X" или "x") поддерживаются только для целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="20957-146">The decimal ("D" or "d") and hexadecimal ("X" or "x") format specifiers are supported only for integral types.</span></span> <span data-ttu-id="20957-147">Описатель формата обратного преобразования ("R" или "r") поддерживается только для типов <xref:System.Single>, <xref:System.Double> и <xref:System.Numerics.BigInteger>.</span><span class="sxs-lookup"><span data-stu-id="20957-147">The round-trip ("R" or "r") format specifier is supported only for <xref:System.Single>, <xref:System.Double>, and <xref:System.Numerics.BigInteger> types.</span></span>

<span data-ttu-id="20957-148">Строки стандартных числовых форматов поддерживаются в следующих сценариях.</span><span class="sxs-lookup"><span data-stu-id="20957-148">Standard numeric format strings are supported by:</span></span>

- <span data-ttu-id="20957-149">Некоторые перегрузки метода `ToString` для всех числовых типов.</span><span class="sxs-lookup"><span data-stu-id="20957-149">Some overloads of the `ToString` method of all numeric types.</span></span> <span data-ttu-id="20957-150">Например, можно задать строку числового формата для методов <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> и <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="20957-150">For example, you can supply a numeric format string to the <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> and <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> methods.</span></span>

- <span data-ttu-id="20957-151">[Функция составного форматирования](../../../standard/base-types/composite-formatting.md) .NET, которая поддерживается методом <xref:System.String.Format%2A?displayProperty=nameWithType>, например.</span><span class="sxs-lookup"><span data-stu-id="20957-151">The .NET [composite formatting feature](../../../standard/base-types/composite-formatting.md), which is supported by the <xref:System.String.Format%2A?displayProperty=nameWithType> method, for example.</span></span>

- <span data-ttu-id="20957-152">[Интерполированные строки](../tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="20957-152">[Interpolated strings](../tokens/interpolated.md).</span></span>

<span data-ttu-id="20957-153">Дополнительные сведения см. в статье [Строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md).</span><span class="sxs-lookup"><span data-stu-id="20957-153">For more information, see [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="20957-154">См. также</span><span class="sxs-lookup"><span data-stu-id="20957-154">See also</span></span>

- [<span data-ttu-id="20957-155">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="20957-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="20957-156">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="20957-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="20957-157">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="20957-157">Formatting types</span></span>](../../../standard/base-types/formatting-types.md)
- [<span data-ttu-id="20957-158">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="20957-158">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="20957-159">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="20957-159">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="20957-160">string</span><span class="sxs-lookup"><span data-stu-id="20957-160">string</span></span>](../builtin-types/reference-types.md)
