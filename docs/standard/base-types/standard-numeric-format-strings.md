---
title: Строки стандартных числовых форматов
ms.date: 06/10/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- standard format strings, numeric
- format strings
- numbers [.NET Framework], formatting
- format specifiers, numeric
- standard numeric format strings
- formatting numbers [.NET Framework]
- format specifiers, standard numeric format strings
ms.openlocfilehash: 04ac99c6b5100c3749eefc219e51b4d0084bef06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398463"
---
# <a name="standard-numeric-format-strings"></a>Строки стандартных числовых форматов

Строки стандартных числовых форматов служат для форматирования стандартных числовых типов. Строка стандартных числовых форматов использует формат `Axx`, где:

- `A` — это один буквенный символ, который называют *описателем формата*. Любая строка числового формата, содержащая более одной буквы, включая пробелы, интерпретируется как строка настраиваемого числового формата. Дополнительные сведения см. в разделе [Строки настраиваемых числовых форматов](../../../docs/standard/base-types/custom-numeric-format-strings.md).

- `xx` — это необязательное целое число, которое называют *описателем точности*. Спецификатор точности находится в диапазоне от 0 до 99 и влияет на число цифр в результате. Описатель точности управляет количеством цифр в строковом представлении числа. Он не округляет само число. Для выполнения операции округления используйте метод <xref:System.Math.Ceiling%2A?displayProperty=nameWithType>, <xref:System.Math.Floor%2A?displayProperty=nameWithType> или <xref:System.Math.Round%2A?displayProperty=nameWithType>.

  Когда *указатель точности* ограничивает число цифр дробной части в итоговой строке, числа в итоговых строках округляются до представимого результата, ближайшего к бесконечно точному. Если имеются два одинаково близких представимых результата:
  - **В .NET Framework и .NET Core вплоть до версии 2.0** среда выполнения выбирает результат с большей наименее значащей цифрой (то есть с использованием <xref:System.MidpointRounding.AwayFromZero?displayProperty=nameWithType>).
  - **В .NET Core 2.1 и более поздних версиях** среда выполнения выбирает результат с четной наименее значащей цифрой (то есть с использованием <xref:System.MidpointRounding.ToEven?displayProperty=nameWithType>).

  > [!NOTE]
  > Описатель точности определяет число цифр в результирующей строке. Чтобы заполнить строку результата начальными или конечными пробелами, используйте функцию [составного форматирования](../../../docs/standard/base-types/composite-formatting.md) и определите  *компонент выравнивания* в элементе форматирования.

Строки стандартных числовых форматов поддерживаются в следующих сценариях.

- Некоторые перегрузки метода `ToString` для всех числовых типов. Например, можно задать строку числового формата для методов <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> и <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>.

- [Функция составного форматирования](../../../docs/standard/base-types/composite-formatting.md) .NET, которая используется некоторыми методами `Write` и `WriteLine` классов <xref:System.Console> и <xref:System.IO.StreamWriter>, методом <xref:System.String.Format%2A?displayProperty=nameWithType> и методом <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>. Композитный формат позволяет включить строковое представление нескольких элементов данных в одну строку, чтобы задать ширину поля и выровнять числа в поле. Дополнительные сведения см. в разделе [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md).

- [Интерполированные строки](../../csharp/language-reference/tokens/interpolated.md) в C# и Visual Basic, которые предоставляют упрощенный синтаксис по сравнению со строками составного формата.

> [!TIP]
> Вы можете загрузить **служебную программу форматирования** — приложение Windows Forms для .NET Core, позволяющее применять строки формата к значениям даты и времени и числовым значениям и отображающее результирующую строку. Исходный код доступен для [C#](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs) и [Visual Basic](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-vb).

<a name="table"></a> В следующей таблице приведены описатели стандартного числового формата и примеры выходных данных, формируемых каждым описателем формата. Дополнительные сведения о использовании строк стандартных числовых форматов см. в разделе [Примечания](#NotesStandardFormatting). Обширную демонстрацию их использования см. в разделе [Пример](#example).

|Спецификатор формата|Имя|Описание:|Примеры|
|----------------------|----------|-----------------|--------------|
|"C" или "c"|Валюта|Результат: значение валюты.<br /><br /> Поддерживается: для всех числовых типов данных.<br /><br /> Описатель точности: количество цифр дробной части.<br /><br /> Описатель точности по умолчанию: определяется <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Дополнительные сведения см. в подразделе [Описатель формата валюты (C)](#CFormatString).|123.456 ("C", en-US) -> \\$123.46<br /><br /> 123.456 ("C", fr-FR) -> 123,46 €<br /><br /> 123.456 ("C", ja-JP) -> ¥123<br /><br /> -123.456 ("C3", en-US) -> (\\$123.456)<br /><br /> -123.456 ("C3", fr-FR) -> -123,456 €<br /><br /> -123.456 ("C3", ja-JP) -> -¥123.456|
|"D" или "d"|Decimal|Результат: целочисленные цифры с необязательным отрицательным знаком.<br /><br /> Поддерживается: только целочисленными типами данных.<br /><br /> Описатель точности: минимальное число цифр.<br /><br /> Описатель точности по умолчанию: минимальное необходимое число цифр.<br /><br /> Дополнительные сведения см. в подразделе [Описатель десятичного формата (D)](#DFormatString).|1234 ("D") -> 1234<br /><br /> -1234 ("D6") -> -001234|
|"E" или "e"|Экспоненциальный (научный)|Результат: экспоненциальная нотация.<br /><br /> Поддерживается: для всех числовых типов данных.<br /><br /> Описатель точности: количество цифр дробной части.<br /><br /> Описатель точности по умолчанию: 6.<br /><br /> Дополнительные сведения см. в подразделе [Описатель экспоненциального формата (E)](#EFormatString).|1052.0329112756 ("E", en-US) -> 1.052033E+003<br /><br /> 1052.0329112756 ("e", fr-FR) -> 1,052033e+003<br /><br /> -1052.0329112756 ("e2", en-US) -> -1.05e+003<br /><br /> –1052.0329112756 ("E2", fr-FR) -> –1,05E+003|
|"F" или "f"|С фиксированной запятой|Результат: цифры целой и дробной частей с необязательным отрицательным знаком.<br /><br /> Поддерживается: для всех числовых типов данных.<br /><br /> Описатель точности: количество цифр дробной части.<br /><br /> Описатель точности по умолчанию: определяется <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Дополнительные сведения см. в подразделе [Описатель формата с фиксированной запятой (F)](#FFormatString).|1234.567 ("F", en-US) -> 1234.57<br /><br /> 1234.567 ("F", de-DE) -> 1234,57<br /><br /> 1234 ("F1", en-US) -> 1234.0<br /><br /> 1234 ("F1", de-DE) -> 1234,0<br /><br /> -1234.56 ("F4", en-US) -> -1234.5600<br /><br /> -1234.56 ("F4", de-DE) -> -1234,5600|
|"G" или "g"|Общие сведения|Результат: наиболее компактная запись из двух вариантов — экспоненциального и с фиксированной запятой.<br /><br /> Поддерживается: для всех числовых типов данных.<br /><br /> Описатель точности: количество значащих цифр.<br /><br /> Описатель точности по умолчанию: определяется численным типом.<br /><br /> Дополнительные сведения см. в подразделе [Описатель общего формата (G)](#GFormatString).|-123.456 ("G", en-US) -> -123.456<br /><br /> -123.456 ("G", sv-SE) -> -123,456<br /><br /> 123.4546 ("G4", en-US) -> 123.5<br /><br /> 123.4546 ("G4", sv-SE) -> 123,5<br /><br /> -1.234567890e-25 ("G", en-US) -> -1.23456789E-25<br /><br /> -1.234567890e-25 ("G", sv-SE) -> -1,23456789E-25|
|"N" или "n"|Number|Результат: цифры целой и дробной частей, разделители групп и разделитель целой и дробной частей с необязательным отрицательным знаком.<br /><br /> Поддерживается: для всех числовых типов данных.<br /><br /> Описатель точности: желаемое число знаков дробной части.<br /><br /> Описатель точности по умолчанию: определяется <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Дополнительные сведения см. в подразделе [Описатель числового формата (N)](#NFormatString).|1234.567 ("N", en-US) -> 1,234.57<br /><br /> 1234.567 ("N", ru-RU) -> 1 234,57<br /><br /> 1234 ("N1", en-US) -> 1,234.0<br /><br /> 1234 ("N1", ru-RU) -> 1 234,0<br /><br /> -1234.56 ("N3", en-US) -> -1,234.560<br /><br /> -1234.56 ("N3", ru-RU) -> -1 234,560|
|"P" или "p"|Процент|Результат: число, умноженное на 100 и отображаемое с символом процента.<br /><br /> Поддерживается: для всех числовых типов данных.<br /><br /> Описатель точности: желаемое число знаков дробной части.<br /><br /> Описатель точности по умолчанию: определяется значением <xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Дополнительные сведения см. в подразделе [Описатель формата процента (P)](#PFormatString).|1 ("P", en-US) -> 100.00 %<br /><br /> 1 ("P", fr-FR) -> 100,00 %<br /><br /> -0.39678 ("P1", en-US) -> -39.7 %<br /><br /> -0.39678 ("P1", fr-FR) -> -39,7 %|
|"R" или "r"|Приемо-передача|Результат: строка, дающая при обратном преобразовании идентичное число.<br /><br /> Поддерживается: <xref:System.Single>, <xref:System.Double> и <xref:System.Numerics.BigInteger>.<br /><br /> Примечание. Мы рекомендуем использовать только для типа <xref:System.Numerics.BigInteger>. Для типов <xref:System.Double> используйте "G17", а для типов <xref:System.Single> — "G9". <br> Описатель точности: игнорируется.<br /><br /> Дополнительные сведения см. в подразделе [Описатель формата обратного преобразования (R)](#RFormatString).|123456789.12345678 ("R") -> 123456789.12345678<br /><br /> -1234567890.12345678 ("R") -> -1234567890.1234567|
|"X" или "x"|Шестнадцатеричный|Результат: шестнадцатеричная строка.<br /><br /> Поддерживается: только целочисленными типами данных.<br /><br /> Описатель точности: число цифр в результирующей строке.<br /><br /> Дополнительные сведения см. в подразделе [Описатель шестнадцатеричного формата (X)](#XFormatString).|255 ("X") -> FF<br /><br /> -1 ("x") -> ff<br /><br /> 255 ("x4") -> 00ff<br /><br /> -1 ("X4") -> 00FF|
|Любой другой символ|Неизвестный описатель|Результат: порождение исключения <xref:System.FormatException> во время выполнения.||

<a name="Using"></a>

## <a name="using-standard-numeric-format-strings"></a>Использование строк стандартных числовых форматов

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Строку стандартного числового формата можно использовать для определения форматирования числового значения одним из двух следующих способов:

- Ее можно передать перегруженному методу `ToString`, у которого есть параметр `format`. В следующем примере осуществляется форматирование числового значения в качестве строки со значением валюты для текущего языка и региональных параметров (en-US).

  [!code-cpp[Formatting.Numeric.Standard#10](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#10)]
  [!code-csharp-interactive[Formatting.Numeric.Standard#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#10)]
  [!code-vb[Formatting.Numeric.Standard#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#10)]

- Эту строку можно передать в качестве аргумента `formatString` в элемент форматирования, используемый с методами <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> и <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md). В следующем примере элемент форматирования используется для вставки значения валюты в строку.

  [!code-cpp[Formatting.Numeric.Standard#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#11)]
  [!code-csharp-interactive[Formatting.Numeric.Standard#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#11)]
  [!code-vb[Formatting.Numeric.Standard#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#11)]

  При желании вы можете передать аргумент `alignment`, чтобы указать ширину числового поля и установить выравнивание по правому или левому краю. В следующем примере денежное значение в поле длиной 28 символов выравнивается по левому краю, а денежное значение в поле длиной 14 символов выравнивается по правому краю.

  [!code-cpp[Formatting.Numeric.Standard#12](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#12)]
  [!code-csharp-interactive[Formatting.Numeric.Standard#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#12)]
  [!code-vb[Formatting.Numeric.Standard#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#12)]

- Его можно предоставить в виде аргумента `formatString` в элементе интерполированного выражения интерполированной строки. Дополнительные сведения см. в разделе [Интерполяция строк](../../csharp/language-reference/tokens/interpolated.md) справочника по C# или разделе [Интерполяция строк](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) справочника по Visual Basic.

В приведенных ниже разделах содержится подробная информация о всех строках стандартных числовых форматов.

<a name="CFormatString"></a>

## <a name="the-currency-c-format-specifier"></a>Описатель формата валюты ("C")

При использовании описателя формата валюты ("C") число преобразуется в строку, представляющую сумму в некоторой валюте. Желаемое количество знаков дробной части в результирующей строке задается описателем точности. Если описатель точности не задан, точность по умолчанию определяется свойством <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A?displayProperty=nameWithType>.

Если форматируемое значение содержит больше десятичных знаков, чем задано или возможно по умолчанию, в результирующей строке дробное значение округляется. Если значение справа от заданного числа десятичных знаков больше или равно 5, последний знак в результирующей строке округляется в сторону от нуля.

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием возвращаемой строки.

|Свойство NumberFormatInfo|Описание:|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern%2A>|Определяет положение символа валюты в положительных значениях.|
|<xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern%2A>|Определяет положение символа валюты в отрицательных значениях и указывает, как именно представляется отрицательный знак: круглыми скобками или свойством <xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>.|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Задает отрицательный знак, используемый в случае, если свойство <xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern%2A> указывает на то, что скобки для отрицания не используются.|
|<xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A>|Определяет символ валюты.|
|<xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A>|Определяет количество цифр дробной части в значении валюты по умолчанию. Это значение можно переопределить с помощью описателя точности.|
|<xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|
|<xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A>|Определяет строку, разделяющую группы цифр целой части.|
|<xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes%2A>|Определяет число целочисленных цифр, входящих в группу.|

В следующем примере значение <xref:System.Double> форматируется с помощью описателя денежного формата:

[!code-cpp[Formatting.Numeric.Standard#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#1)]
[!code-csharp[Formatting.Numeric.Standard#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#1)]
[!code-vb[Formatting.Numeric.Standard#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#1)]

[К таблице](#table)

<a name="DFormatString"></a>

## <a name="the-decimal-d-format-specifier"></a>Описатель десятичного формата ("D")

При использовании описателя десятичного формата ("D") число преобразуется в строку, состоящую из десятичных цифр (0–9); если число отрицательное, перед ним ставится отрицательный знак. Этот формат доступен только для целых типов.

Минимальное количество знаков в выходной строке задается спецификатором точности. Недостающие знаки в строке заменяются нулями. Если описатель точности не задан, по умолчанию используется минимальное значение, позволяющее представить целое число без нулей в начале.

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. Как показано в следующей таблице, управление форматированием результирующей строки осуществляется с помощью одного свойства.

|Свойство NumberFormatInfo|Описание:|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|

В следующем примере значение <xref:System.Int32> форматируется с помощью описателя десятичного формата.

[!code-cpp[Formatting.Numeric.Standard#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#2)]
[!code-csharp-interactive[Formatting.Numeric.Standard#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#2)]
[!code-vb[Formatting.Numeric.Standard#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#2)]

[К таблице](#table)

<a name="EFormatString"></a>

## <a name="the-exponential-e-format-specifier"></a>Описатель экспоненциального формата ("E")

При использовании описателя экспоненциального формата ("E") число преобразуется в строку вида "-d.ddd…E+ddd" или "-d.ddd…e+ddd", где каждый символ "d" обозначает цифру (0–9). Если число отрицательное, в начале строки ставится отрицательный знак. Перед разделителем целой и дробной части всегда стоит ровно одна цифра.

Требуемое число знаков дробной части задается спецификатором точности. Если спецификатор точности отсутствует, по умолчанию число знаков дробной части равно шести.

Регистр описателя формата задает регистр буквы, стоящей перед экспонентой ("E" или "e"). Экспонента состоит из знака "плюс" или "минус" и трех цифр. Недостающие до минимума цифры заменяются нулями, если это необходимо.

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием возвращаемой строки.

|Свойство NumberFormatInfo|Описание:|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую на то, что число является отрицательным (как мантисса, так и экспонента).|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части мантиссы.|
|<xref:System.Globalization.NumberFormatInfo.PositiveSign%2A>|Определяет строку, указывающую, что экспонента является положительной.|

В следующем примере значение <xref:System.Double> форматируется с помощью описателя экспоненциального формата.

[!code-cpp[Formatting.Numeric.Standard#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#3)]
[!code-csharp[Formatting.Numeric.Standard#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#3)]
[!code-vb[Formatting.Numeric.Standard#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#3)]

[К таблице](#table)

<a name="FFormatString"></a>

## <a name="the-fixed-point-f-format-specifier"></a>Описатель формата с фиксированной запятой ("F")

При использовании описателя формата с фиксированной запятой ("F") число преобразуется в строку вида "-ddd.ddd…", где каждый символ "d" обозначает цифру (0–9). Если число отрицательное, в начале строки ставится отрицательный знак.

Требуемое число знаков дробной части задается спецификатором точности. Если описатель точности отсутствует, то используется численная точность, определяемая текущим значением свойства <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType>.

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства объекта <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием результирующей строки.

|Свойство NumberFormatInfo|Описание:|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A>|Определяет количество цифр дробной части по умолчанию. Это значение можно переопределить с помощью описателя точности.|

В следующем примере значение <xref:System.Double> и значение <xref:System.Int32> форматируются с помощью описателя формата с фиксированной точкой.

[!code-cpp[Formatting.Numeric.Standard#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#4)]
[!code-csharp[Formatting.Numeric.Standard#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#4)]
[!code-vb[Formatting.Numeric.Standard#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#4)]

[К таблице](#table)

<a name="GFormatString"></a>

## <a name="the-general-g-format-specifier"></a>Описатель общего формата ("G")

При использовании описателя общего формата ("G") число преобразуется в более короткий из двух вариантов: запись с фиксированной запятой или экспоненциальная запись. При этом учитывается тип числа и наличие описателя точности. Описатель точности определяет максимальное количество значащих цифр, которые могут быть использованы в результирующей строке. Если описатель точности не задан или равен нулю, точность определяется типом числа, как показано в следующей таблице.

|Числовой тип|Точность по умолчанию|
|------------------|-----------------------|
|<xref:System.Byte> или <xref:System.SByte>|3 знака|
|<xref:System.Int16> или <xref:System.UInt16>|5 знака|
|<xref:System.Int32> или <xref:System.UInt32>|10 знака|
|<xref:System.Int64>|19 знака|
|<xref:System.UInt64>|20 знака|
|<xref:System.Numerics.BigInteger>|Без ограничений (то же, что и [R](#RFormatString))|
|<xref:System.Single>|7 знака|
|<xref:System.Double>|15 знаков|
|<xref:System.Decimal>|29 знака|

Нотация с фиксированной запятой используется, если экспонента результата в экспоненциальной нотации длиннее пяти знаков, но меньше спецификатора точности, в противном случае используется научная нотация. При необходимости результат содержит разделитель целой и дробной частей; нули в конце дробной части после разделителя отбрасываются. Если описатель точности задан и число значащих цифр результата превосходит указанное значение точности, лишние цифры отбрасываются округлением.

Тем не менее, если число относится к типу <xref:System.Decimal> и описатель точности не задан, всегда используется нотация с фиксированной запятой, а нули в конце не отбрасываются.

Если используется экспоненциальная нотация, регистр буквы, стоящей перед экспонентой, определяется регистром описателя формата (буква "E" соответствует "G", "e" соответствует "g"). Экспонента содержит не менее двух цифр. Это отличает данный формат от экспоненциальной записи, создаваемой при использовании описателя экспоненциального формата, поскольку в последнем случае экспонента содержит не менее трех цифр.

Обратите внимание, что при использовании совместно со значением <xref:System.Double> описатель формата G17 гарантирует обратимость преобразования исходного значения <xref:System.Double>. Это связано с тем, что <xref:System.Double> совместим со стандартом IEEE 754-2008 для чисел двойной точности (`binary64`) с плавающей запятой, в котором определена точность до 17 значащих цифр. Мы рекомендуем использовать этот формат вместо [описателя формата "R"](#RFormatString), который в некоторых случаях не гарантирует обратимость преобразования чисел двойной точности с плавающей запятой. В следующем примере представлен один такой случай.

[!code-csharp-interactive[Round-tripping a Double](../../../samples/snippets/standard/base-types/format-strings/csharp/g17.cs#GeneralFormatSpecifier)]
[!code-vb[Round-tripping a Double](../../../samples/snippets/standard/base-types/format-strings/vb/g17.vb)]

При использовании со значением <xref:System.Single> описатель формата G9 гарантирует обратимость преобразования исходного значения <xref:System.Single>. Это связано с тем, что <xref:System.Single> совместим со стандартом IEEE 754-2008 для чисел одиночной точности (`binary32`) с плавающей запятой, в котором определена точность до 9 значащих цифр. Из соображений производительности рекомендуется использовать его вместо [описателя формата "R"](#RFormatString).

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием результирующей строки.

|Свойство NumberFormatInfo|Описание:|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|
|<xref:System.Globalization.NumberFormatInfo.PositiveSign%2A>|Определяет строку, указывающую, что экспонента является положительной.|

В следующем примере различные значения с плавающей запятой форматируются с помощью описателя общего формата.

[!code-cpp[Formatting.Numeric.Standard#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#5)]
[!code-csharp[Formatting.Numeric.Standard#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#5)]
[!code-vb[Formatting.Numeric.Standard#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#5)]

[К таблице](#table)

<a name="NFormatString"></a>

## <a name="the-numeric-n-format-specifier"></a>Описатель числового формата ("N")

Спецификатор числового формата ("N") преобразует число в стоку вида "-d,ddd,ddd.ddd… ", где знак "-" при необходимости представляет знак отрицательного числа, знак "d" означает цифру (0-9), знак "," — разделитель групп, а знак "." —- разделитель целой и дробной части. Требуемое число знаков дробной части задается спецификатором точности. Если описатель точности не задан, число десятичных знаков определяется текущим свойством <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType>.

Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием результирующей строки.

|Свойство NumberFormatInfo|Описание:|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|
|<xref:System.Globalization.NumberFormatInfo.NumberNegativePattern%2A>|Определяет формат отрицательных значений и указывает, как именно представляется отрицательный знак: круглыми скобками или свойством <xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>.|
|<xref:System.Globalization.NumberFormatInfo.NumberGroupSizes%2A>|Определяет число цифр целой части, стоящих между разделителями групп.|
|<xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A>|Определяет строку, разделяющую группы цифр целой части.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A>|Определяет количество цифр дробной части по умолчанию. Это значение можно переопределить с помощью описателя точности.|

В следующем примере различные значения с плавающей запятой форматируются с помощью описателя числового формата.

[!code-cpp[Formatting.Numeric.Standard#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#6)]
[!code-csharp[Formatting.Numeric.Standard#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#6)]
[!code-vb[Formatting.Numeric.Standard#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#6)]

[К таблице](#table)

<a name="PFormatString"></a>

## <a name="the-percent-p-format-specifier"></a>Описатель формата процента ("P")

При использовании описателя формата процента ("P") число умножается на 100 и преобразуется в строку, представляющую процентную долю. Требуемое число знаков дробной части задается спецификатором точности. Если описатель точности отсутствует, то используется значение точности числа по умолчанию, заданное свойством <xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A>.

В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием возвращаемой строки.

|Свойство NumberFormatInfo|Описание:|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.PercentPositivePattern%2A>|Определяет положение символа процента в положительных значениях.|
|<xref:System.Globalization.NumberFormatInfo.PercentNegativePattern%2A>|Определяет положение символа процента и отрицательного знака в отрицательных значениях.|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|
|<xref:System.Globalization.NumberFormatInfo.PercentSymbol%2A>|Определяет символ процента.|
|<xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A>|Определяет количество цифр дробной части в значении процента по умолчанию. Это значение можно переопределить с помощью описателя точности.|
|<xref:System.Globalization.NumberFormatInfo.PercentDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|
|<xref:System.Globalization.NumberFormatInfo.PercentGroupSeparator%2A>|Определяет строку, разделяющую группы цифр целой части.|
|<xref:System.Globalization.NumberFormatInfo.PercentGroupSizes%2A>|Определяет число целочисленных цифр, входящих в группу.|

В следующем примере значения с плавающей запятой форматируются с помощью описателя процентного формата.

[!code-cpp[Formatting.Numeric.Standard#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#7)]
[!code-csharp[Formatting.Numeric.Standard#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#7)]
[!code-vb[Formatting.Numeric.Standard#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#7)]

[К таблице](#table)

<a name="RFormatString"></a>

## <a name="the-round-trip-r-format-specifier"></a>Описатель формата обратного преобразования ("R")

Описатель формата обратного преобразования ("R") пытается выполнить преобразование числового значения в строку так, чтобы при обратном преобразовании этой строки можно было получить то же самое числовое значение. Этот формат поддерживается только для типов <xref:System.Single>, <xref:System.Double> и <xref:System.Numerics.BigInteger>.

Для значений <xref:System.Double> описатель формата "R" в некоторых случаях не может гарантировать правильное обратное преобразование. Для значений <xref:System.Double> и <xref:System.Single> он также обеспечивает относительно низкую производительность. Вместо него мы рекомендуем использовать описатель формата [G17](#GFormatString) для значений <xref:System.Double> и описатель формата [G9](#GFormatString) для значений <xref:System.Single>, которые гарантируют правильное обратное преобразование.

Если с помощью этого описателя форматируется значение типа <xref:System.Numerics.BigInteger>, то его строковое представление будет содержать все значащие цифры <xref:System.Numerics.BigInteger>.

Хотя описатель точности можно указать, он будет проигнорирован. Приведенные указатели приема-передачи в данном случае имеют преимущество перед указателем точности.
Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием результирующей строки.

|Свойство NumberFormatInfo|Описание:|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|
|<xref:System.Globalization.NumberFormatInfo.PositiveSign%2A>|Определяет строку, указывающую, что экспонента является положительной.|

В следующем примере форматируется значение <xref:System.Numerics.BigInteger> с применением спецификатора формата обратного преобразования.

[!code-cpp[R format specifier with a BigInteger](../../../samples/snippets/standard/base-types/format-strings/biginteger-r.cpp)]
[!code-csharp[R format specifier with a BigInteger](../../../samples/snippets/standard/base-types/format-strings/biginteger-r.cs)]
[!code-vb[R format specifier with a BigInteger](../../../samples/snippets/standard/base-types/format-strings/biginteger-r.vb)]

> [!IMPORTANT]
> В некоторых случаях для значений <xref:System.Double>, отформатированных с использованием строки стандартного числового формата "R", не удается успешно выполнить обратное преобразование при компиляции с использованием параметра `/platform:x64` или `/platform:anycpu` и запуска в 64-разрядных системах. Дополнительные сведения см. в следующем абзаце.

Чтобы избежать проблемы со значениями <xref:System.Double>, отформатированными с использованием строки стандартного числового формата R, для которых не удалось выполнить обратное преобразование при компиляции с использованием параметра `/platform:x64` или `/platform:anycpu` в 64-разрядных системах, можно отформатировать значения <xref:System.Double> с помощью строки стандартного числового формата G17. В примере ниже используется строка формата "R" со значением <xref:System.Double>, для которого не удается выполнить обратное преобразование, а также строка формата "G17" для успешного обратного преобразования исходного значения:

[!code-csharp[System.Double.ToString#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Double.ToString/cs/roundtripex1.cs#RoundTrip)]
[!code-vb[System.Double.ToString#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Double.ToString/vb/roundtripex1.vb#5)]

[К таблице](#table)

<a name="XFormatString"></a>

## <a name="the-hexadecimal-x-format-specifier"></a>Описатель шестнадцатеричного формата ("X")

При использовании описателя шестнадцатеричного формата ("X") число преобразуется в строку шестнадцатеричных цифр. Регистр шестнадцатеричных цифр больше 9 совпадает с регистром описателя формата. Например, чтобы получить запись "ABCDEF", задайте описатель X" или, наоборот, задайте описатель "x", чтобы получить "abcdef". Этот формат доступен только для целых типов.

Минимальное количество знаков в выходной строке задается спецификатором точности. Недостающие знаки в строке заменяются нулями.

Форматирование результирующей строки не зависит от сведений о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>.

В следующем примере значения <xref:System.Int32> форматируются с помощью спецификатора шестнадцатеричного формата.

[!code-cpp[Formatting.Numeric.Standard#9](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#9)]
[!code-csharp-interactive[Formatting.Numeric.Standard#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#9)]
[!code-vb[Formatting.Numeric.Standard#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#9)]

[К таблице](#table)

<a name="NotesStandardFormatting"></a>

## <a name="notes"></a>Примечания

### <a name="control-panel-settings"></a>Настройки панели управления

На строку, полученную в результате форматирования, влияют параметры, задаваемые в разделе **Язык и региональные стандарты** панели управления. Эти параметры используются для инициализации объекта <xref:System.Globalization.NumberFormatInfo>, связанного с языком и региональными параметрами текущего потока, откуда берутся значения, используемые для управления форматированием. Результирующие строки будут различаться на компьютерах с разными параметрами.

Кроме того, если конструктор <xref:System.Globalization.CultureInfo.%23ctor%28System.String%29?displayProperty=nameWithType> используется для создания нового объекта <xref:System.Globalization.CultureInfo>, представляющего язык и региональные параметры, аналогичные текущим в системе, то все настройки, заданные в разделе **Язык и региональные стандарты** на панели управления, будут применяться к новому объекту <xref:System.Globalization.CultureInfo>. Можно воспользоваться конструктором <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> для создания объекта <xref:System.Globalization.CultureInfo> , который не отражает настройки системы.

### <a name="numberformatinfo-properties"></a>Свойства NumberFormatInfo

На форматирование влияют свойства текущего объекта <xref:System.Globalization.NumberFormatInfo>, который неявно определяется на основе языка и региональных параметров текущего потока или явно задается параметром <xref:System.IFormatProvider> метода, который вызывает форматирование. Укажите объект <xref:System.Globalization.NumberFormatInfo> или объект <xref:System.Globalization.CultureInfo> для этого параметра.

> [!NOTE]
> Дополнительные сведения о настройке шаблонов или строк, используемых в форматировании числовых значений см. статью о классе <xref:System.Globalization.NumberFormatInfo>.

### <a name="integral-and-floating-point-numeric-types"></a>Целочисленные типы и типы с плавающей запятой

Некоторые описания спецификаторов стандартных числовых форматов относятся к целочисленным типам и типам с плавающей запятой. Целочисленные типы — это <xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64> и <xref:System.Numerics.BigInteger>. Числовыми типами с плавающей запятой являются <xref:System.Decimal>, <xref:System.Single> и <xref:System.Double>.

### <a name="floating-point-infinities-and-nan"></a>Бесконечности действительных чисел с плавающей запятой и NaN

Если, вне зависимости от строки формата, значение типа с плавающей запятой <xref:System.Single> или <xref:System.Double> является положительной бесконечностью, отрицательной бесконечностью или не является числом (NaN), отформатированная строка будет содержать значение соответствующего свойства (<xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol%2A>, <xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol%2A> или <xref:System.Globalization.NumberFormatInfo.NaNSymbol%2A>) применимого в настоящий момент объекта <xref:System.Globalization.NumberFormatInfo>.

## <a name="example"></a>Пример

[!INCLUDE[interactive-note](~/includes/csharp-interactive-partial-note.md)]

В следующем примере с помощью языка и региональных параметров "en-US" и всех описателей стандартных числовых форматов форматируется целочисленное значение и числовое значение с плавающей запятой. В этом примере используются два числовых типа (<xref:System.Double> и <xref:System.Int32>), но аналогичные результаты были бы получены для любых других числовых типов (<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>, <xref:System.Numerics.BigInteger>, <xref:System.Decimal> и <xref:System.Single>).

[!code-csharp[system.x.tostring-and-culture#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.X.ToString-and-Culture/cs/xts.cs#FinalExample)]
[!code-vb[system.x.tostring-and-culture#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.X.ToString-and-Culture/vb/xts.vb#1)]

## <a name="see-also"></a>См. также раздел

- <xref:System.Globalization.NumberFormatInfo>
- [Строки настраиваемых числовых форматов](../../../docs/standard/base-types/custom-numeric-format-strings.md)
- [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)
- [Практическое руководство. Добавление к числу начальных нулей](../../../docs/standard/base-types/how-to-pad-a-number-with-leading-zeros.md)
- [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md)
- [Пример: служебная программа форматирования .NET Core WinForms (C#)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs)
- [Пример: служебная программа форматирования .NET Core WinForms (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-vb)
