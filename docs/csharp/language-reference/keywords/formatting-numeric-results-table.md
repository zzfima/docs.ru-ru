---
title: Справочник по C#. Таблица форматирования числовых результатов
ms.custom: seodec18
description: Сведения об использовании строк стандартных числовых форматов C#
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: 2cba5e704787ae6368b2543c985babf2fde3b4dd
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422753"
---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="2c29f-103">Таблица форматирования числовых результатов (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2c29f-103">Formatting numeric results table (C# Reference)</span></span>

<span data-ttu-id="2c29f-104">В следующей таблице приводятся описатели поддерживаемых форматов для форматирования числовых результатов.</span><span class="sxs-lookup"><span data-stu-id="2c29f-104">The following table shows supported format specifiers for formatting numeric results.</span></span> <span data-ttu-id="2c29f-105">Форматированный результат в последнем столбце соответствует формату "en-US" (<xref:System.Globalization.CultureInfo>).</span><span class="sxs-lookup"><span data-stu-id="2c29f-105">The formatted result in the last column corresponds to the "en-US" <xref:System.Globalization.CultureInfo>.</span></span>

|<span data-ttu-id="2c29f-106">Описатель формата</span><span class="sxs-lookup"><span data-stu-id="2c29f-106">Format specifier</span></span>|<span data-ttu-id="2c29f-107">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="2c29f-107">Description</span></span>|<span data-ttu-id="2c29f-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="2c29f-108">Examples</span></span>|<span data-ttu-id="2c29f-109">Результат</span><span class="sxs-lookup"><span data-stu-id="2c29f-109">Result</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="2c29f-110">C или c</span><span class="sxs-lookup"><span data-stu-id="2c29f-110">C or c</span></span>|<span data-ttu-id="2c29f-111">Валюта</span><span class="sxs-lookup"><span data-stu-id="2c29f-111">Currency</span></span>|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|<span data-ttu-id="2c29f-112">$2.50</span><span class="sxs-lookup"><span data-stu-id="2c29f-112">$2.50</span></span><br /><br /> <span data-ttu-id="2c29f-113">($2.50)</span><span class="sxs-lookup"><span data-stu-id="2c29f-113">($2.50)</span></span>|  
|<span data-ttu-id="2c29f-114">D или d</span><span class="sxs-lookup"><span data-stu-id="2c29f-114">D or d</span></span>|<span data-ttu-id="2c29f-115">Decimal</span><span class="sxs-lookup"><span data-stu-id="2c29f-115">Decimal</span></span>|`string s = $"{25:D5}";`|<span data-ttu-id="2c29f-116">00025</span><span class="sxs-lookup"><span data-stu-id="2c29f-116">00025</span></span>|  
|<span data-ttu-id="2c29f-117">E или e</span><span class="sxs-lookup"><span data-stu-id="2c29f-117">E or e</span></span>|<span data-ttu-id="2c29f-118">Экспоненциальный</span><span class="sxs-lookup"><span data-stu-id="2c29f-118">Exponential</span></span>|`string s = $"{250000:E2}";`|<span data-ttu-id="2c29f-119">2.50E+005</span><span class="sxs-lookup"><span data-stu-id="2c29f-119">2.50E+005</span></span>|  
|<span data-ttu-id="2c29f-120">F или f</span><span class="sxs-lookup"><span data-stu-id="2c29f-120">F or f</span></span>|<span data-ttu-id="2c29f-121">С фиксированной запятой</span><span class="sxs-lookup"><span data-stu-id="2c29f-121">Fixed-point</span></span>|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|<span data-ttu-id="2c29f-122">2.50</span><span class="sxs-lookup"><span data-stu-id="2c29f-122">2.50</span></span><br /><br /> <span data-ttu-id="2c29f-123">3</span><span class="sxs-lookup"><span data-stu-id="2c29f-123">3</span></span>|  
|<span data-ttu-id="2c29f-124">G или g</span><span class="sxs-lookup"><span data-stu-id="2c29f-124">G or g</span></span>|<span data-ttu-id="2c29f-125">Общее</span><span class="sxs-lookup"><span data-stu-id="2c29f-125">General</span></span>|`string s = $"{2.5:G}";`|<span data-ttu-id="2c29f-126">2.5</span><span class="sxs-lookup"><span data-stu-id="2c29f-126">2.5</span></span>|  
|<span data-ttu-id="2c29f-127">N или n</span><span class="sxs-lookup"><span data-stu-id="2c29f-127">N or n</span></span>|<span data-ttu-id="2c29f-128">Numeric</span><span class="sxs-lookup"><span data-stu-id="2c29f-128">Numeric</span></span>|`string s = $"{2500000:N}";`|<span data-ttu-id="2c29f-129">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="2c29f-129">2,500,000.00</span></span>|  
|<span data-ttu-id="2c29f-130">P или p</span><span class="sxs-lookup"><span data-stu-id="2c29f-130">P or p</span></span>|<span data-ttu-id="2c29f-131">Процент</span><span class="sxs-lookup"><span data-stu-id="2c29f-131">Percent</span></span>|`string s = $"{0.25:P}";`|<span data-ttu-id="2c29f-132">25.00%</span><span class="sxs-lookup"><span data-stu-id="2c29f-132">25.00%</span></span>|  
|<span data-ttu-id="2c29f-133">R или r</span><span class="sxs-lookup"><span data-stu-id="2c29f-133">R or r</span></span>|<span data-ttu-id="2c29f-134">Приемо-передача</span><span class="sxs-lookup"><span data-stu-id="2c29f-134">Round-trip</span></span>|`string s = $"{2.5:R}";`|<span data-ttu-id="2c29f-135">2.5</span><span class="sxs-lookup"><span data-stu-id="2c29f-135">2.5</span></span>|  
|<span data-ttu-id="2c29f-136">X или x</span><span class="sxs-lookup"><span data-stu-id="2c29f-136">X or x</span></span>|<span data-ttu-id="2c29f-137">Шестнадцатеричный</span><span class="sxs-lookup"><span data-stu-id="2c29f-137">Hexadecimal</span></span>|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|<span data-ttu-id="2c29f-138">FA</span><span class="sxs-lookup"><span data-stu-id="2c29f-138">FA</span></span><br /><br /> <span data-ttu-id="2c29f-139">FFFF</span><span class="sxs-lookup"><span data-stu-id="2c29f-139">FFFF</span></span>|  

## <a name="remarks"></a><span data-ttu-id="2c29f-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="2c29f-140">Remarks</span></span>

<span data-ttu-id="2c29f-141">Для создания строки формата используйте описатель формата.</span><span class="sxs-lookup"><span data-stu-id="2c29f-141">You use a format specifier to create a format string.</span></span> <span data-ttu-id="2c29f-142">Строка формата имеет вид `Axx`:</span><span class="sxs-lookup"><span data-stu-id="2c29f-142">The format string is of the following form: `Axx`, where</span></span>

- <span data-ttu-id="2c29f-143">где `A` — это описатель формата, который управляет типом форматирования, применяемым к числовому значению;</span><span class="sxs-lookup"><span data-stu-id="2c29f-143">`A` is the format specifier, which controls the type of formatting applied to the numeric value.</span></span>
- <span data-ttu-id="2c29f-144">а `xx` — указатель точности, который влияет на количество цифр в форматированном выводе.</span><span class="sxs-lookup"><span data-stu-id="2c29f-144">`xx` is the precision specifier, which affects the number of digits in the formatted output.</span></span> <span data-ttu-id="2c29f-145">Значение описателя точности находится в диапазоне от 0 до 99.</span><span class="sxs-lookup"><span data-stu-id="2c29f-145">The value of the precision specifier ranges from 0 to 99.</span></span>

<span data-ttu-id="2c29f-146">Описатели десятичного ("D" или "d") и шестнадцатеричного форматов ("X" или "x") поддерживаются только для целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="2c29f-146">The decimal ("D" or "d") and hexadecimal ("X" or "x") format specifiers are supported only for integral types.</span></span> <span data-ttu-id="2c29f-147">Описатель формата обратного преобразования ("R" или "r") поддерживается только для типов <xref:System.Single>, <xref:System.Double> и <xref:System.Numerics.BigInteger>.</span><span class="sxs-lookup"><span data-stu-id="2c29f-147">The round-trip ("R" or "r") format specifier is supported only for <xref:System.Single>, <xref:System.Double>, and <xref:System.Numerics.BigInteger> types.</span></span>

<span data-ttu-id="2c29f-148">Строки стандартных числовых форматов поддерживаются в следующих сценариях.</span><span class="sxs-lookup"><span data-stu-id="2c29f-148">Standard numeric format strings are supported by:</span></span>

- <span data-ttu-id="2c29f-149">Некоторые перегрузки метода `ToString` для всех числовых типов.</span><span class="sxs-lookup"><span data-stu-id="2c29f-149">Some overloads of the `ToString` method of all numeric types.</span></span> <span data-ttu-id="2c29f-150">Например, можно задать строку числового формата для методов <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> и <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2c29f-150">For example, you can supply a numeric format string to the <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> and <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> methods.</span></span>

- <span data-ttu-id="2c29f-151">[Функция составного форматирования](../../../standard/base-types/composite-formatting.md) .NET, которая поддерживается методом <xref:System.String.Format%2A?displayProperty=nameWithType>, например.</span><span class="sxs-lookup"><span data-stu-id="2c29f-151">The .NET [composite formatting feature](../../../standard/base-types/composite-formatting.md), which is supported by the <xref:System.String.Format%2A?displayProperty=nameWithType> method, for example.</span></span>

- <span data-ttu-id="2c29f-152">[Интерполированные строки](../tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="2c29f-152">[Interpolated strings](../tokens/interpolated.md).</span></span>

<span data-ttu-id="2c29f-153">Дополнительные сведения см. в статье [Строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md).</span><span class="sxs-lookup"><span data-stu-id="2c29f-153">For more information, see [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2c29f-154">См. также</span><span class="sxs-lookup"><span data-stu-id="2c29f-154">See also</span></span>

- [<span data-ttu-id="2c29f-155">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2c29f-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2c29f-156">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2c29f-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2c29f-157">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="2c29f-157">Formatting types</span></span>](../../../standard/base-types/formatting-types.md)
- [<span data-ttu-id="2c29f-158">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="2c29f-158">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="2c29f-159">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="2c29f-159">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="2c29f-160">string</span><span class="sxs-lookup"><span data-stu-id="2c29f-160">string</span></span>](../builtin-types/reference-types.md)
