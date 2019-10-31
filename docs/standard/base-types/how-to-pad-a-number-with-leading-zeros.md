---
title: Практическое руководство. Дополнение числа начальными нулями
ms.date: 02/25/2019
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
ms.openlocfilehash: 54c3eb734184adf5168607cfc8bcbf6c17ea493a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678899"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a>Практическое руководство. Дополнение числа начальными нулями

К целому числу можно добавить начальные нули, используя [строку стандартного числового формата](../../../docs/standard/base-types/standard-numeric-format-strings.md) "D" с описателем точности. С помощью [строки настраиваемого числового формата](../../../docs/standard/base-types/custom-numeric-format-strings.md) начальные нули можно добавлять как к целым числам, так и к числам с плавающей запятой. В этой статье показано, как использовать оба метода для дополнения числа начальными нулями.

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a>Дополнение целого числа начальными нулями до определенной длины

1. Определите минимальное число разрядов для целого числа. Добавьте к этому значению число начальных разрядов.

1. Определите, хотите ли вы показывать целое число как десятичное или шестнадцатеричное.

    - Чтобы показать целое число как десятичное, вызовите метод `ToString(String)` и передайте строку "D*n*" как значение параметра `format`, где *n* представляет минимальную длину строки.

    - Для отображения целого числа в виде шестнадцатеричного значения вызовите его метод `ToString(String)` и передайте строку "X*n*" в качестве значения параметра format, где *n* представляет минимальную длину строки.

Также можно использовать строку формата в интерполированной строке в [C# ](../../csharp/language-reference/tokens/interpolated.md) и [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) или вызвать метод, например <xref:System.String.Format%2A?displayProperty=nameWithType> или <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, который использует [составное форматирование](../../../docs/standard/base-types/composite-formatting.md).

Следующий пример форматирует несколько целых значений с добавлением начальных нулей, чтобы общая длина форматированного числа составляла по крайней мере 8 символов.

[!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
[!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a>Дополнение целого числа определенным количеством начальных нулей

1. Определите, сколько начальных нулей должно быть в целом числе.

1. Определите, хотите ли вы показывать целое число как десятичное или шестнадцатеричное.

    - Для форматирования в виде десятичного значения необходимо использовать описатель стандартного формата D.

    - Для форматирования в виде шестнадцатеричного значения необходимо использовать описатель стандартного формата X.

1. Определите длину недополненной числовой строки, вызвав метод `ToString("D").Length` или `ToString("X").Length` целого числа.

1. Добавьте число начальных нулей, которое следует добавить в форматированную строку, к длине недополненной числовой строки. Добавление количества начальных нулей определяет общую длину дополненной строки.

1. Вызовите для целого значения метод `ToString(String)` и передайте строку "D*n*" для десятичных строк или строку "X*n*" для шестнадцатеричных строк, где *n* означает общую длину дополненной строки. Строку форматирования "D*n*" или "X*n*" можно также использовать в методе, поддерживающем составное форматирование.

Следующий пример дополняет целое число пятью начальными нулями.

[!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
[!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a>Дополнение числового значения начальными нулями до определенной длины

1. Определите, сколько разрядов слева от десятичного разделителя должно быть в строковом представлении числа. Добавьте к этому значению число начальных нулей.

1. Определите строку настраиваемого формата числа, использующую местозаполнитель нуля (0) для представления минимального количества нулей.

1. Вызовите метод `ToString(String)` числа и передайте ему строку настраиваемого формата. Вы также можете использовать строку настраиваемого формата с интерполяцией строки или методом, поддерживающим составное форматирование.

Следующий пример форматирует несколько числовых значений с начальными нулями. В результате общая длина форматированного числа составляет по крайней мере восемь цифр слева от десятичного разделителя.

[!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
[!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a>Дополнение числового значения определенным количеством начальных нулей

1. Определите, сколько начальных нулей должно быть в числовом значении.

1. Определите количество разрядов слева от десятичного разделителя в недополненной числовой строке:

    1. Определите, содержит ли строковое представление числа символ десятичной точки.

    1. Если это так, определите число символов слева от десятичной точки.

         \- или -

         Если строка не содержит десятичный разделитель, определите длину строки.

1. Создайте строку настраиваемого формата, которая использует:

    - Местозаполнитель нуля для каждого начального нуля в строке.

    - Нулевой местозаполнитель или местозаполнитель разряда # для представления каждого разряда в строке по умолчанию.

1. Передайте строку настраиваемого формата как параметр методу `ToString(String)` числа или методу, поддерживающему составное форматирование.

Следующий пример дополняет два значения типа <xref:System.Double> число пятью начальными нулями.

[!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
[!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]

## <a name="see-also"></a>См. также

- [Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md)
- [Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md)
- [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md)
