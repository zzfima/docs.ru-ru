---
title: Практическое руководство. Добавление к числу начальных нулей.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ce3b59db027ffebf616a035b018629cb7aed30c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569776"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="d6f8a-102">Практическое руководство. Добавление к числу начальных нулей.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-102">How to: Pad a Number with Leading Zeros</span></span>
<span data-ttu-id="d6f8a-103">К целому числу можно добавить начальные нули, используя [строку стандартного числового формата](../../../docs/standard/base-types/standard-numeric-format-strings.md) "D" с описателем точности.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-103">You can add leading zeros to an integer by using the "D" [standard numeric format string](../../../docs/standard/base-types/standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="d6f8a-104">С помощью [строки настраиваемого числового формата](../../../docs/standard/base-types/custom-numeric-format-strings.md) начальные нули можно добавлять как к целым числам, так и к числам с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-104">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](../../../docs/standard/base-types/custom-numeric-format-strings.md).</span></span> <span data-ttu-id="d6f8a-105">В этой статье показано, как использовать оба метода для дополнения числа начальными нулями.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-105">This topic shows how to use both methods to pad a number with leading zeros.</span></span>  
  
### <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="d6f8a-106">Дополнение целого числа начальными нулями до определенной длины</span><span class="sxs-lookup"><span data-stu-id="d6f8a-106">To pad an integer with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="d6f8a-107">Определите минимальное число разрядов для целого числа.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-107">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="d6f8a-108">Добавьте к этому значению число начальных разрядов.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-108">Include any leading digits in this number.</span></span>  
  
2.  <span data-ttu-id="d6f8a-109">Определите, хотите ли вы показывать целое число как десятичное или шестнадцатеричное.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-109">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>  
  
    -   <span data-ttu-id="d6f8a-110">Чтобы показать целое число как десятичное, вызовите метод `ToString(String)` и передайте строку "D*n*" как значение параметра `format`, где *n* представляет минимальную длину строки.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-110">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
    -   <span data-ttu-id="d6f8a-111">Чтобы показать целое число как шестнадцатеричное, вызовите метод `ToString(String)` и передайте строку "X*n*" как значение параметра `format`, где *n* представляет минимальную длину строки.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-111">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
     <span data-ttu-id="d6f8a-112">Вы также можете использовать строку формата в методе, например <xref:System.String.Format%2A> или <xref:System.Console.WriteLine%2A>, который использует [составное форматирование](../../../docs/standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="d6f8a-112">You can also use the format string in a method, such as <xref:System.String.Format%2A> or <xref:System.Console.WriteLine%2A>, that uses [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="d6f8a-113">Следующий пример форматирует несколько целых значений с добавлением начальных нулей, чтобы общая длина форматированного числа составляла по крайней мере 8 символов.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-113">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="d6f8a-114">Дополнение целого числа определенным количеством начальных нулей</span><span class="sxs-lookup"><span data-stu-id="d6f8a-114">To pad an integer with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="d6f8a-115">Определите, сколько начальных нулей должно быть в целом числе.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-115">Determine how many leading zeros you want the integer value to display.</span></span>  
  
2.  <span data-ttu-id="d6f8a-116">Определите, хотите ли вы показывать целое число как десятичное или шестнадцатеричное.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-116">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span> <span data-ttu-id="d6f8a-117">Чтобы отформатировать число как десятичное значение, необходимо использовать стандартный описатель формата "D", чтобы отформатировать число как шестнадцатеричное значение, используйте стандартный описатель формата "X".</span><span class="sxs-lookup"><span data-stu-id="d6f8a-117">Formatting it as a decimal value requires that you use the "D" standard format specifier; formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>  
  
3.  <span data-ttu-id="d6f8a-118">Определите длину недополненной числовой строки, вызвав метод `ToString("D").Length` или `ToString("X").Length` целого числа.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-118">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>  
  
4.  <span data-ttu-id="d6f8a-119">Добавьте число начальных нулей, которое следует добавить в форматированную строку, к длине недополненной числовой строки.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-119">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="d6f8a-120">Будет получена общая длина результирующей строки.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-120">This defines the total length of the padded string.</span></span>  
  
5.  <span data-ttu-id="d6f8a-121">Вызовите для целого значения метод `ToString(String)` и передайте строку "D*n*" для десятичных строк или строку "X*n*" для шестнадцатеричных строк, где *n* означает общую длину дополненной строки.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-121">Call the integer value's `ToString(String)` method, and pass the string "D*n*" for decimal strings and "X*n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="d6f8a-122">Строку форматирования "D*n*" или "X*n*" можно также использовать в методе, поддерживающем составное форматирование.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-122">You can also use the "D*n*" or "X*n*" format string in a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="d6f8a-123">Следующий пример дополняет целое число пятью начальными нулями.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-123">The following example pads an integer value with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="d6f8a-124">Дополнение числового значения начальными нулями до определенной длины</span><span class="sxs-lookup"><span data-stu-id="d6f8a-124">To pad a numeric value with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="d6f8a-125">Определите, сколько разрядов слева от десятичного разделителя должно быть в строковом представлении числа.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-125">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="d6f8a-126">Добавьте к этому значению число начальных нулей.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-126">Include any leading zeros in this total number of digits.</span></span>  
  
2.  <span data-ttu-id="d6f8a-127">Определите строку настраиваемого формата числа, использующую местозаполнитель нуля ("0") для представления минимального количества нулей.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-127">Define a custom numeric format string that uses the zero placeholder ("0") to represent the minimum number of zeros.</span></span>  
  
3.  <span data-ttu-id="d6f8a-128">Вызовите метод `ToString(String)` числа и передайте ему строку настраиваемого формата.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-128">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="d6f8a-129">Вы также можете использовать строку настраиваемого формата с методом, поддерживающим составное форматирование.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-129">You can also use the custom format string with a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="d6f8a-130">Следующий пример форматирует несколько числовых значений с добавлением начальных нулей, чтобы общая длина форматированного числа составляла по крайней мере 8 символов слева от десятичного разделителя.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-130">The following example formats several numeric values with leading zeros so that the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="d6f8a-131">Дополнение числового значения определенным количеством начальных нулей</span><span class="sxs-lookup"><span data-stu-id="d6f8a-131">To pad a numeric value with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="d6f8a-132">Определите, сколько начальных нулей должно быть в числовом значении.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-132">Determine how many leading zeros you want the numeric value to have.</span></span>  
  
2.  <span data-ttu-id="d6f8a-133">Определите количество разрядов слева от десятичного разделителя в недополненной числовой строке.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-133">Determine the number of digits to the left of the decimal in the unpadded numeric string.</span></span> <span data-ttu-id="d6f8a-134">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-134">To do this:</span></span>  
  
    1.  <span data-ttu-id="d6f8a-135">Определите, содержит ли строковое представление числа символ десятичной точки.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-135">Determine whether the string representation of a number includes a decimal point symbol.</span></span>  
  
    2.  <span data-ttu-id="d6f8a-136">Если это так, определите число символов слева от десятичной точки.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-136">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>  
  
         <span data-ttu-id="d6f8a-137">- или -</span><span class="sxs-lookup"><span data-stu-id="d6f8a-137">-or-</span></span>  
  
         <span data-ttu-id="d6f8a-138">Если строка не содержит десятичную точку, определите длину строки.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-138">If it does not include a decimal point symbol, determine the string's length.</span></span>  
  
3.  <span data-ttu-id="d6f8a-139">Создайте строку настраиваемого формата, использующую нулевой местозаполнитель ("0") для каждого начального нуля, которые будут добавлены в строку, и использующую нулевой местозаполнитель или местозаполнитель разряда ("#") для представления каждого разряда в строке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-139">Create a custom format string that uses the zero placeholder ("0") for each of the leading zeros to appear in the string, and that uses either the zero placeholder or the digit placeholder ("#") to represent each digit in the default string.</span></span>  
  
4.  <span data-ttu-id="d6f8a-140">Передайте строку настраиваемого формата как параметр методу `ToString(String)` числа или методу, поддерживающему составное форматирование.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-140">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="d6f8a-141">Следующий пример дополняет два значения типа <xref:System.Double> число пятью начальными нулями.</span><span class="sxs-lookup"><span data-stu-id="d6f8a-141">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="d6f8a-142">См. также</span><span class="sxs-lookup"><span data-stu-id="d6f8a-142">See Also</span></span>  
 [<span data-ttu-id="d6f8a-143">Custom Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="d6f8a-143">Custom Numeric Format Strings</span></span>](../../../docs/standard/base-types/custom-numeric-format-strings.md)  
 [<span data-ttu-id="d6f8a-144">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="d6f8a-144">Standard Numeric Format Strings</span></span>](../../../docs/standard/base-types/standard-numeric-format-strings.md)  
 [<span data-ttu-id="d6f8a-145">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="d6f8a-145">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
