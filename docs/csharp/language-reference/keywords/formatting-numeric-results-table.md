---
title: "Таблица форматирования числовых результатов (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 16976f5a59bd4eb0eca29553aff87d4fe0b1d247
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="9fde4-102">Таблица форматирования числовых результатов (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9fde4-102">Formatting Numeric Results Table (C# Reference)</span></span>
<span data-ttu-id="9fde4-103">Для форматирования результатов можно воспользоваться методом <xref:System.String.Format%2A?displayProperty=fullName>, а также методом <xref:System.Console.Write%2A?displayProperty=fullName> или <xref:System.Console.WriteLine%2A?displayProperty=fullName>, вызывающим метод `String.Format`.</span><span class="sxs-lookup"><span data-stu-id="9fde4-103">You can format numeric results by using the <xref:System.String.Format%2A?displayProperty=fullName> method, or through the <xref:System.Console.Write%2A?displayProperty=fullName> or <xref:System.Console.WriteLine%2A?displayProperty=fullName> method, which calls `String.Format`.</span></span> <span data-ttu-id="9fde4-104">Формат задается с помощью строк формата.</span><span class="sxs-lookup"><span data-stu-id="9fde4-104">The format is specified by using format strings.</span></span> <span data-ttu-id="9fde4-105">В следующей таблице приведены поддерживаемые строки стандартных форматов.</span><span class="sxs-lookup"><span data-stu-id="9fde4-105">The following table contains the supported standard format strings.</span></span> <span data-ttu-id="9fde4-106">Строка формата принимает следующую форму: `Axx`, где `A` — описатель формата, а `xx` — описатель точности.</span><span class="sxs-lookup"><span data-stu-id="9fde4-106">The format string takes the following form: `Axx`, where `A` is the format specifier and `xx` is the precision specifier.</span></span> <span data-ttu-id="9fde4-107">Описатель формата управляет типом форматирования, применяемым к числовому значению, а описатель точности управляет количеством значащих цифр или десятичных знаков форматированного результата.</span><span class="sxs-lookup"><span data-stu-id="9fde4-107">The format specifier controls the type of formatting applied to the numeric value, and the precision specifier controls the number of significant digits or decimal places of the formatted output.</span></span> <span data-ttu-id="9fde4-108">Значение описателя точности находится в диапазоне от 0 до 99.</span><span class="sxs-lookup"><span data-stu-id="9fde4-108">The value of the precision specifier ranges from 0 to 99.</span></span>  
  
 <span data-ttu-id="9fde4-109">Дополнительные сведения о строках стандартных и пользовательских форматов см. в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="9fde4-109">For more information about standard and custom formatting strings, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="9fde4-110">Дополнительные сведения о методе `String.Format` см. в разделе <xref:System.String.Format%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="9fde4-110">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=fullName>.</span></span>  
  
|<span data-ttu-id="9fde4-111">Описатель формата</span><span class="sxs-lookup"><span data-stu-id="9fde4-111">Format Specifier</span></span>|<span data-ttu-id="9fde4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9fde4-112">Description</span></span>|<span data-ttu-id="9fde4-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="9fde4-113">Examples</span></span>|<span data-ttu-id="9fde4-114">Вывод</span><span class="sxs-lookup"><span data-stu-id="9fde4-114">Output</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="9fde4-115">C или c</span><span class="sxs-lookup"><span data-stu-id="9fde4-115">C or c</span></span>|<span data-ttu-id="9fde4-116">Валюта</span><span class="sxs-lookup"><span data-stu-id="9fde4-116">Currency</span></span>|<span data-ttu-id="9fde4-117">Console.Write("{0:C}", 2.5);</span><span class="sxs-lookup"><span data-stu-id="9fde4-117">Console.Write("{0:C}", 2.5);</span></span><br /><br /> <span data-ttu-id="9fde4-118">Console.Write("{0:C}", -2.5);</span><span class="sxs-lookup"><span data-stu-id="9fde4-118">Console.Write("{0:C}", -2.5);</span></span>|<span data-ttu-id="9fde4-119">$2.50</span><span class="sxs-lookup"><span data-stu-id="9fde4-119">$2.50</span></span><br /><br /> <span data-ttu-id="9fde4-120">($2.50)</span><span class="sxs-lookup"><span data-stu-id="9fde4-120">($2.50)</span></span>|  
|<span data-ttu-id="9fde4-121">D или d</span><span class="sxs-lookup"><span data-stu-id="9fde4-121">D or d</span></span>|<span data-ttu-id="9fde4-122">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="9fde4-122">Decimal</span></span>|<span data-ttu-id="9fde4-123">Console.Write("{0:D5}", 25);</span><span class="sxs-lookup"><span data-stu-id="9fde4-123">Console.Write("{0:D5}", 25);</span></span>|<span data-ttu-id="9fde4-124">00025</span><span class="sxs-lookup"><span data-stu-id="9fde4-124">00025</span></span>|  
|<span data-ttu-id="9fde4-125">E или e</span><span class="sxs-lookup"><span data-stu-id="9fde4-125">E or e</span></span>|<span data-ttu-id="9fde4-126">Экспоненциальный</span><span class="sxs-lookup"><span data-stu-id="9fde4-126">Scientific</span></span>|<span data-ttu-id="9fde4-127">Console.Write("{0:E}", 250000);</span><span class="sxs-lookup"><span data-stu-id="9fde4-127">Console.Write("{0:E}", 250000);</span></span>|<span data-ttu-id="9fde4-128">2.500000E+005</span><span class="sxs-lookup"><span data-stu-id="9fde4-128">2.500000E+005</span></span>|  
|<span data-ttu-id="9fde4-129">F или f</span><span class="sxs-lookup"><span data-stu-id="9fde4-129">F or f</span></span>|<span data-ttu-id="9fde4-130">С фиксированной запятой</span><span class="sxs-lookup"><span data-stu-id="9fde4-130">Fixed-point</span></span>|<span data-ttu-id="9fde4-131">Console.Write("{0:F2}", 25);</span><span class="sxs-lookup"><span data-stu-id="9fde4-131">Console.Write("{0:F2}", 25);</span></span><br /><br /> <span data-ttu-id="9fde4-132">Console.Write("{0:F0}", 25);</span><span class="sxs-lookup"><span data-stu-id="9fde4-132">Console.Write("{0:F0}", 25);</span></span>|<span data-ttu-id="9fde4-133">25.00</span><span class="sxs-lookup"><span data-stu-id="9fde4-133">25.00</span></span><br /><br /> <span data-ttu-id="9fde4-134">25</span><span class="sxs-lookup"><span data-stu-id="9fde4-134">25</span></span>|  
|<span data-ttu-id="9fde4-135">G или g</span><span class="sxs-lookup"><span data-stu-id="9fde4-135">G or g</span></span>|<span data-ttu-id="9fde4-136">Общие</span><span class="sxs-lookup"><span data-stu-id="9fde4-136">General</span></span>|<span data-ttu-id="9fde4-137">Console.Write("{0:G}", 2.5);</span><span class="sxs-lookup"><span data-stu-id="9fde4-137">Console.Write("{0:G}", 2.5);</span></span>|<span data-ttu-id="9fde4-138">2.5</span><span class="sxs-lookup"><span data-stu-id="9fde4-138">2.5</span></span>|  
|<span data-ttu-id="9fde4-139">N или n</span><span class="sxs-lookup"><span data-stu-id="9fde4-139">N or n</span></span>|<span data-ttu-id="9fde4-140">Число</span><span class="sxs-lookup"><span data-stu-id="9fde4-140">Number</span></span>|<span data-ttu-id="9fde4-141">Console.Write("{0:N}", 2500000);</span><span class="sxs-lookup"><span data-stu-id="9fde4-141">Console.Write("{0:N}", 2500000);</span></span>|<span data-ttu-id="9fde4-142">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="9fde4-142">2,500,000.00</span></span>|  
|<span data-ttu-id="9fde4-143">X или x</span><span class="sxs-lookup"><span data-stu-id="9fde4-143">X or x</span></span>|<span data-ttu-id="9fde4-144">Шестнадцатеричный</span><span class="sxs-lookup"><span data-stu-id="9fde4-144">Hexadecimal</span></span>|<span data-ttu-id="9fde4-145">Console.Write("{0:X}", 250);</span><span class="sxs-lookup"><span data-stu-id="9fde4-145">Console.Write("{0:X}", 250);</span></span><br /><br /> <span data-ttu-id="9fde4-146">Console.Write("{0:X}", 0xffff);</span><span class="sxs-lookup"><span data-stu-id="9fde4-146">Console.Write("{0:X}", 0xffff);</span></span>|<span data-ttu-id="9fde4-147">FA</span><span class="sxs-lookup"><span data-stu-id="9fde4-147">FA</span></span><br /><br /> <span data-ttu-id="9fde4-148">FFFF</span><span class="sxs-lookup"><span data-stu-id="9fde4-148">FFFF</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9fde4-149">См. также</span><span class="sxs-lookup"><span data-stu-id="9fde4-149">See Also</span></span>  
 <span data-ttu-id="9fde4-150">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9fde4-150">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9fde4-151">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9fde4-151">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9fde4-152">[Строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md) </span><span class="sxs-lookup"><span data-stu-id="9fde4-152">[Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md) </span></span>  
 <span data-ttu-id="9fde4-153">[Справочные таблицы по типам](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="9fde4-153">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 [<span data-ttu-id="9fde4-154">string</span><span class="sxs-lookup"><span data-stu-id="9fde4-154">string</span></span>](../../../csharp/language-reference/keywords/string.md)

