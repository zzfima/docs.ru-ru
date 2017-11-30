---
title: "Строки стандартных числовых форматов"
ms.date: 09/10/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
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
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 81547bbcdbae5b4cc8dc1f20e829dfb5ede08963
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="standard-numeric-format-strings"></a>Строки стандартных числовых форматов
Строки стандартных числовых форматов служат для форматирования стандартных числовых типов. Строка стандартных числовых форматов использует формат `Axx`, где:  
  
-   `A` — это один буквенный символ, который называют *описателем формата*. Любая строка числового формата, содержащая более одной буквы, включая пробелы, интерпретируется как строка настраиваемого числового формата. Дополнительные сведения см. в разделе [Строки настраиваемых числовых форматов](../../../docs/standard/base-types/custom-numeric-format-strings.md).  
  
-   `xx` — это необязательное целое число, которое называют *описателем точности*. Спецификатор точности находится в диапазоне от 0 до 99 и влияет на число цифр в результате. Описатель точности управляет количеством цифр в строковом представлении числа. Он не округляет само число. Для выполнения операции округления используйте метод <xref:System.Math.Ceiling%2A?displayProperty=nameWithType>, <xref:System.Math.Floor%2A?displayProperty=nameWithType> или <xref:System.Math.Round%2A?displayProperty=nameWithType>.  
  
     Когда *описатель точности* определяет количество цифр дробной части в результирующей строке, в итоговых строках содержатся числа, округляемые (то есть с использованием <xref:System.MidpointRounding.AwayFromZero?displayProperty=nameWithType>).  
  
    > [!NOTE]
    >  Описатель точности определяет число цифр в результирующей строке. Чтобы заполнить строку результата начальными или конечными пробелами, используйте функцию [составного форматирования](../../../docs/standard/base-types/composite-formatting.md) и определите  *компонент выравнивания* в элементе форматирования.  
  
Строки стандартного числового формата поддерживаются:

- Некоторые перегрузки `ToString` метод всех числовых типов. Например, можно задать строку числового формата для <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> и <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> методы. 
 
- .NET [составного форматирования](../../../docs/standard/base-types/composite-formatting.md), который используется для некоторых `Write` и `WriteLine` методы <xref:System.Console> и <xref:System.IO.StreamWriter> классы, <xref:System.String.Format%2A?displayProperty=nameWithType> метода и <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> метод. Композитный формат позволяет включить строковое представление нескольких элементов данных в одну строку, чтобы задать ширину поля и выровнять числа в поле. Дополнительные сведения см. в разделе [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md).  

- [Интерполируются строки](../../csharp/language-reference/keywords/interpolated-strings.md) в C# и Visual Basic, которые предоставляют упрощенный синтаксис по сравнению с строк составного формата.
 
> [!TIP]
>  Вы можете загрузить [служебную программу форматирования](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)— приложение, позволяющее применять строки формата к значениям даты и времени и числовым значениям и отображающее результирующую строку.  
  
<a name="table"></a> В следующей таблице приведены описатели стандартного числового формата и примеры выходных данных, формируемых каждым описателем формата. Дополнительные сведения о использовании строк стандартных числовых форматов см. в разделе [Примечания](#NotesStandardFormatting). Обширную демонстрацию их использования см. в разделе [Пример](#example).  
  
|Описатель формата|Имя|Описание|Примеры|  
|----------------------|----------|-----------------|--------------|  
|"C" или "c"|Валюта|Результат: значение валюты.<br /><br /> Поддерживается: всеми числовыми типами данных.<br /><br /> Описатель точности: количество цифр в дробной части.<br /><br /> Описатель точности по умолчанию: определяется <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Дополнительные сведения см. в подразделе [Описатель формата валюты (C)](#CFormatString).|123.456 ("C", en-US) -> $123.46<br /><br /> 123.456 ("C", fr-FR) -> 123,46 €<br /><br /> 123.456 ("C", ja-JP) -> ¥123<br /><br /> -123.456 ("C3", en-US) -> ($123.456)<br /><br /> -123.456 ("C3", fr-FR) -> -123,456 €<br /><br /> -123.456 ("C3", ja-JP) -> -¥123.456|  
|"D" или "d"|Десятичное число|Результат: целочисленные цифры с необязательным отрицательным знаком.<br /><br /> Поддерживается: только целочисленными типами данных.<br /><br /> Описатель точности: минимальное число цифр.<br /><br /> Описатель точности по умолчанию: минимальное необходимое число цифр.<br /><br /> Дополнительные сведения см. в подразделе [Описатель десятичного формата (D)](#DFormatString).|1234 ("D") -> 1234<br /><br /> -1234 ("D6") -> -001234|  
|"E" или "e"|Экспоненциальный (научный)|Результат: экспоненциальная нотация.<br /><br /> Поддерживается: всеми числовыми типами данных.<br /><br /> Описатель точности: количество цифр дробной части.<br /><br /> Описатель точности по умолчанию: 6.<br /><br /> Дополнительные сведения см. в подразделе [Описатель экспоненциального формата (E)](#EFormatString).|1052.0329112756 ("E", en-US) -> 1.052033E+003<br /><br /> 1052.0329112756 ("e", fr-FR) -> 1,052033e+003<br /><br /> -1052.0329112756 ("e2", en-US) -> -1.05e+003<br /><br /> -1052.0329112756 ("E2", fr_FR) -> -1,05E+003|  
|"F" или "f"|С фиксированной запятой|Результат: цифры целой и дробной частей с необязательным отрицательным знаком.<br /><br /> Поддерживается: всеми числовыми типами данных.<br /><br /> Описатель точности: количество цифр в дробной части.<br /><br /> Описатель точности по умолчанию: определяется <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Дополнительные сведения см. в подразделе [Описатель формата с фиксированной запятой (F)](#FFormatString).|1234.567 ("F", en-US) -> 1234.57<br /><br /> 1234.567 ("F", de-DE) -> 1234,57<br /><br /> 1234 ("F1", en-US) -> 1234.0<br /><br /> 1234 ("F1", de-DE) -> 1234,0<br /><br /> -1234.56 ("F4", en-US) -> -1234.5600<br /><br /> -1234.56 ("F4", de-DE) -> -1234,5600|  
|"G" или "g"|Общие|Результат: наиболее компактная запись из двух вариантов — экспоненциального и с фиксированной запятой.<br /><br /> Поддерживается: для всех числовых типов данных.<br /><br /> Описатель точности: количество значащих цифр.<br /><br /> Описатель точности по умолчанию: определяется численным типом.<br /><br /> Дополнительные сведения см. в подразделе [Описатель общего формата (G)](#GFormatString).|-123.456 ("G", en-US) -> -123.456<br /><br /> -123.456 ("G", sv-SE) -> -123,456<br /><br /> 123.4546 ("G4", en-US) -> 123.5<br /><br /> 123.4546 ("G4", sv-SE) -> 123,5<br /><br /> -1.234567890e-25 ("G", en-US) -> -1.23456789E-25<br /><br /> -1.234567890e-25 ("G", sv-SE) -> -1,23456789E-25|  
|"N" или "n"|Числовой|Результат: цифры целой и дробной частей, разделители групп и разделитель целой и дробной частей с необязательным отрицательным знаком.<br /><br /> Поддерживается: всеми числовыми типами данных.<br /><br /> Описатель точности: желаемое число знаков дробной части.<br /><br /> Описатель точности по умолчанию: определяется <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Дополнительные сведения см. в подразделе [Описатель числового формата (N)](#NFormatString).|1234.567 ("N", en-US) -> 1,234.57<br /><br /> 1234.567 ("N", ru-RU) -> 1 234,57<br /><br /> 1234 ("N1", en-US) -> 1,234.0<br /><br /> 1234 ("N1", ru-RU) -> 1 234,0<br /><br /> -1234.56 ("N3", en-US) -> -1,234.560<br /><br /> -1234.56 ("N3", ru-RU) -> -1 234,560|  
|"P" или "p"|Процент|Результат: число, умноженное на 100 и отображаемое с символом процента.<br /><br /> Поддерживается: всеми числовыми типами данных.<br /><br /> Описатель точности: желаемое число знаков дробной части.<br /><br /> Описатель точности по умолчанию: определяется <xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Дополнительные сведения см. в подразделе [Описатель формата процента (P)](#PFormatString).|1 ("P", en-US) -> 100.00 %<br /><br /> 1 ("P", fr-FR) -> 100,00 %<br /><br /> -0.39678 ("P1", en-US) -> -39.7 %<br /><br /> -0.39678 ("P1", fr-FR) -> -39,7 %|  
|"R" или "r"|Приемо-передача|Результат: строка, дающая при обратном преобразовании идентичное число.<br /><br /> Поддерживается: <xref:System.Single>, <xref:System.Double> и <xref:System.Numerics.BigInteger>.<br /><br /> Примечание: Рекомендуется для <xref:System.Numerics.BigInteger> только типа. Для <xref:System.Double> типов, используйте «G17»; для <xref:System.Single> типов, используйте «G9». </br> Описатель точности: игнорируется.<br /><br /> Дополнительные сведения см. в подразделе [Описатель формата обратного преобразования (R)](#RFormatString).|123456789.12345678 ("R") -> 123456789.12345678<br /><br /> -1234567890.12345678 ("R") -> -1234567890.1234567|  
|"X" или "x"|Шестнадцатеричный|Результат: шестнадцатеричная строка.<br /><br /> Поддерживается: только целочисленными типами данных.<br /><br /> Описатель точности: число цифр в результирующей строке.<br /><br /> Дополнительные сведения см. в подразделе [Описатель шестнадцатеричного формата (X)](#XFormatString).|255 ("X") -> FF<br /><br /> -1 ("x") -> ff<br /><br /> 255 ("x4") -> 00ff<br /><br /> -1 ("X4") -> 00FF|  
|Любой другой символ|Неизвестный описатель|Результат: порождение исключения <xref:System.FormatException> во время выполнения.||  
  
<a name="Using"></a>   
## <a name="using-standard-numeric-format-strings"></a>Использование строк стандартных числовых форматов  
 Строку стандартного числового формата можно использовать для определения форматирования числового значения одним из двух следующих способов:  
  
-   Ее можно передать перегруженному методу `ToString`, у которого есть параметр `format`. Следующий пример форматирует числовое значение валюты в виде строки текущего языка и региональных параметров (в данном случае en-US).  
  
     [!code-cpp[Formatting.Numeric.Standard#10](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#10)]
     [!code-csharp[Formatting.Numeric.Standard#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#10)]
     [!code-vb[Formatting.Numeric.Standard#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#10)]  
  
-   Он может быть передано в качестве `formatString` аргумент в элементе форматирования, используемый с такими методами как <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, и <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md). В следующем примере элемент форматирования используется для вставки значения валюты в строку.  
  
     [!code-cpp[Formatting.Numeric.Standard#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#11)]
     [!code-csharp[Formatting.Numeric.Standard#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#11)]
     [!code-vb[Formatting.Numeric.Standard#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#11)]  
  
     При необходимости можно указать `alignment` аргумент, чтобы указать ширину числового поля и является оно справа или по левому краю. В следующем примере денежное значение в поле длиной 28 символов выравнивается по левому краю, а денежное значение в поле длиной 14 символов выравнивается по правому краю.  
  
     [!code-cpp[Formatting.Numeric.Standard#12](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#12)]
     [!code-csharp[Formatting.Numeric.Standard#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#12)]
     [!code-vb[Formatting.Numeric.Standard#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#12)]  
  
 В приведенных ниже разделах содержится подробная информация о всех строках стандартных числовых форматов.  
  
<a name="CFormatString"></a>   
## <a name="the-currency-c-format-specifier"></a>Описатель формата валюты ("C")  
 При использовании описателя формата валюты ("C") число преобразуется в строку, представляющую сумму в некоторой валюте. Желаемое количество знаков дробной части в результирующей строке задается описателем точности. Если описатель точности не задан, точность по умолчанию определяется свойством <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A?displayProperty=nameWithType>.  
  
 Если форматируемое значение содержит больше десятичных знаков, чем задано или возможно по умолчанию, в результирующей строке дробное значение округляется. Если значение справа от заданного числа десятичных знаков больше или равно 5, последний знак в результирующей строке округляется в сторону от нуля.  
  
 Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием возвращаемой строки.  
  
|Свойство NumberFormatInfo|Описание|  
|-------------------------------|-----------------|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern%2A>|Определяет положение символа валюты в положительных значениях.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern%2A>|Определяет положение символа валюты в отрицательных значениях и указывает, как именно представляется отрицательный знак: круглыми скобками или свойством <xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>.|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Задает отрицательный знак, если <xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern%2A> указывает, что скобки не применяются.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A>|Определяет символ валюты.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A>|Определяет количество цифр дробной части в значении валюты по умолчанию. Это значение можно переопределить с помощью описателя точности.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A>|Определяет строку, разделяющую группы цифр целой части.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes%2A>|Определяет число целочисленных цифр, входящих в группу.|  
  
 В следующем примере значение <xref:System.Double> форматируется с помощью спецификатора денежного формата.  
  
 [!code-cpp[Formatting.Numeric.Standard#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#1)]
 [!code-csharp[Formatting.Numeric.Standard#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#1)]
 [!code-vb[Formatting.Numeric.Standard#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#1)]  
  
 [К таблице](#table)  
  
<a name="DFormatString"></a>   
## <a name="the-decimal-d-format-specifier"></a>Описатель десятичного формата ("D")  
 При использовании описателя десятичного формата ("D") число преобразуется в строку, состоящую из десятичных цифр (0–9); если число отрицательное, перед ним ставится отрицательный знак. Этот формат доступен только для целых типов.  
  
 Минимальное количество знаков в выходной строке задается спецификатором точности. Недостающие знаки в строке заменяются нулями. Если описатель точности не задан, по умолчанию используется минимальное значение, позволяющее представить целое число без нулей в начале.  
  
 Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. Как показано в следующей таблице, управление форматированием результирующей строки осуществляется с помощью одного свойства.  
  
|Свойство NumberFormatInfo|Описание|  
|-------------------------------|-----------------|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|  
  
 В следующем примере значение <xref:System.Int32> форматируется с помощью описателя десятичного формата.  
  
 [!code-cpp[Formatting.Numeric.Standard#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#2)]
 [!code-csharp[Formatting.Numeric.Standard#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#2)]
 [!code-vb[Formatting.Numeric.Standard#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#2)]  
  
 [К таблице](#table)  
  
<a name="EFormatString"></a>   
## <a name="the-exponential-e-format-specifier"></a>Описатель экспоненциального формата ("E")  
 При использовании описателя экспоненциального формата ("E") число преобразуется в строку вида "-d.ddd…E+ddd" или "-d.ddd…e+ddd", где каждый символ "d" обозначает цифру (0–9). Если число отрицательное, в начале строки ставится отрицательный знак. Перед разделителем целой и дробной части всегда стоит ровно одна цифра.  
  
 Требуемое число знаков дробной части задается спецификатором точности. Если спецификатор точности отсутствует, по умолчанию число знаков дробной части равно шести.  
  
 Регистр описателя формата задает регистр буквы, стоящей перед экспонентой ("E" или "e"). Экспонента состоит из знака "плюс" или "минус" и трех цифр. Недостающие до минимума цифры заменяются нулями, если это необходимо.  
  
 Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием возвращаемой строки.  
  
|Свойство NumberFormatInfo|Описание|  
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
 Описатель формата с фиксированной запятой («F») число преобразуется в строку вида «-ддд...» где каждое "d" обозначает цифру (0–9). Если число отрицательное, в начале строки ставится отрицательный знак.  
  
 Требуемое число знаков дробной части задается спецификатором точности. Если описатель точности отсутствует, то используется численная точность, определяемая текущим значением свойства <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType>.  
  
 Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства объекта <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием результирующей строки.  
  
|Свойство NumberFormatInfo|Описание|  
|-------------------------------|-----------------|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A>|Определяет количество цифр дробной части по умолчанию. Это значение можно переопределить с помощью описателя точности.|  
  
 В следующем примере значение <xref:System.Double> и значение <xref:System.Int32> форматируются с помощью спецификатора формата с фиксированной точкой.  
  
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
|<xref:System.Double>|15 знака|  
|<xref:System.Decimal>|29 знака|  
  
 Нотация с фиксированной запятой используется, если экспонента результата в экспоненциальной нотации длиннее пяти знаков, но меньше спецификатора точности, в противном случае используется научная нотация. При необходимости результат содержит разделитель целой и дробной частей; нули в конце дробной части после разделителя отбрасываются. Если описатель точности задан и число значащих цифр результата превосходит указанное значение точности, лишние цифры отбрасываются округлением.  
  
 Тем не менее, если число относится к типу <xref:System.Decimal> и описатель точности не задан, всегда используется нотация с фиксированной запятой, а нули в конце не отбрасываются.  
  
 Если используется экспоненциальная нотация, регистр буквы, стоящей перед экспонентой, определяется регистром описателя формата (буква "E" соответствует "G", "e" соответствует "g"). Экспонента содержит не менее двух цифр. Это отличает данный формат от экспоненциальной записи, создаваемой при использовании описателя экспоненциального формата, поскольку в последнем случае экспонента содержит не менее трех цифр.  
 
Обратите внимание, что при использовании с <xref:System.Double> значение, описатель формата «G17» гарантирует, что исходный <xref:System.Double> успешно возвращено значение циклов приема-передачи. Это вызвано <xref:System.Double> является IEEE 754 2008-совместимое с двойной точностью (`binary64`) число с плавающей запятой, дает более 17 значащих цифр точности. Использовать его вместо рекомендуется [описатель формата «R»](#RFormatString), поскольку в некоторых случаях «R» не удается успешно выполнить обратное преобразование числа двойной точности значений с плавающей запятой. В следующем примере демонстрируется Подобная ситуация.

[!code-csharp[Round-tripping a Double](../../../samples/snippets/standard/base-types/format-strings/csharp/g17.cs)]   
[!code-vb[Round-tripping a Double](../../../samples/snippets/standard/base-types/format-strings/vb/g17.vb)]   

При использовании с <xref:System.Single> значение, описатель формата «G9» гарантирует, что исходный <xref:System.Single> успешно возвращено значение циклов приема-передачи. Это вызвано <xref:System.Single> является IEEE 754 2008-совместимое с двойной точностью (`binary32`) число с плавающей запятой, предоставляющий до девяти значащих цифр точности. Использовать его вместо рекомендуется [описатель формата «R»](#RFormatString), поскольку в некоторых случаях «R» не удается успешно приема-передачи одинарной точности значений с плавающей запятой.

 Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием результирующей строки.  
  
|Свойство NumberFormatInfo|Описание|  
|-------------------------------|-----------------|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|  
|<xref:System.Globalization.NumberFormatInfo.PositiveSign%2A>|Определяет строку, указывающую, что экспонента является положительной.|  
  
 В следующем примере различные значения с плавающей запятой форматируются с помощью спецификатора общего формата.  
  
 [!code-cpp[Formatting.Numeric.Standard#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#5)]
 [!code-csharp[Formatting.Numeric.Standard#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#5)]
 [!code-vb[Formatting.Numeric.Standard#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#5)]  
  
 [К таблице](#table)  
  
<a name="NFormatString"></a>   
## <a name="the-numeric-n-format-specifier"></a>Описатель числового формата ("N")  
 Спецификатор числового формата ("N") преобразует число в стоку вида "-d,ddd,ddd.ddd… ", где знак "-" при необходимости представляет знак отрицательного числа, знак "d" означает цифру (0-9), знак "," — разделитель групп, а знак "." —- разделитель целой и дробной части. Требуемое число знаков дробной части задается спецификатором точности. Если описатель точности не задан, число десятичных знаков определяется текущим свойством <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType>.  
  
 Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием результирующей строки.  
  
|Свойство NumberFormatInfo|Описание|  
|-------------------------------|-----------------|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|  
|<xref:System.Globalization.NumberFormatInfo.NumberNegativePattern%2A>|Определяет формат отрицательных значений и указывает, как именно представляется отрицательный знак: круглыми скобками или свойством <xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>.|  
|<xref:System.Globalization.NumberFormatInfo.NumberGroupSizes%2A>|Определяет число цифр целой части, стоящих между разделителями групп.|  
|<xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A>|Определяет строку, разделяющую группы цифр целой части.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A>|Определяет количество цифр дробной части по умолчанию. Это значение можно переопределить с помощью описателя точности.|  
  
 В следующем примере различные значения с плавающей запятой форматируются с помощью спецификатора числового формата.  
  
 [!code-cpp[Formatting.Numeric.Standard#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#6)]
 [!code-csharp[Formatting.Numeric.Standard#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#6)]
 [!code-vb[Formatting.Numeric.Standard#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#6)]  
  
 [К таблице](#table)  
  
<a name="PFormatString"></a>   
## <a name="the-percent-p-format-specifier"></a>Описатель формата процента ("P")  
 При использовании описателя формата процента ("P") число умножается на 100 и преобразуется в строку, представляющую процентную долю. Требуемое число знаков дробной части задается спецификатором точности. Если описатель точности отсутствует, то используется значение точности числа по умолчанию, заданное свойством <xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A>.  
  
 В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием возвращаемой строки.  
  
|Свойство NumberFormatInfo|Описание|  
|-------------------------------|-----------------|  
|<xref:System.Globalization.NumberFormatInfo.PercentPositivePattern%2A>|Определяет положение символа процента в положительных значениях.|  
|<xref:System.Globalization.NumberFormatInfo.PercentNegativePattern%2A>|Определяет положение символа процента и отрицательного знака в отрицательных значениях.|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|  
|<xref:System.Globalization.NumberFormatInfo.PercentSymbol%2A>|Определяет символ процента.|  
|<xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A>|Определяет количество цифр дробной части в значении процента по умолчанию. Это значение можно переопределить с помощью описателя точности.|  
|<xref:System.Globalization.NumberFormatInfo.PercentDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|  
|<xref:System.Globalization.NumberFormatInfo.PercentGroupSeparator%2A>|Определяет строку, разделяющую группы цифр целой части.|  
|<xref:System.Globalization.NumberFormatInfo.PercentGroupSizes%2A>|Определяет число целочисленных цифр, входящих в группу.|  
  
 В следующем примере значения с плавающей запятой форматируются с помощью спецификатора процентного формата.  
  
 [!code-cpp[Formatting.Numeric.Standard#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#7)]
 [!code-csharp[Formatting.Numeric.Standard#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#7)]
 [!code-vb[Formatting.Numeric.Standard#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#7)]  
  
 [К таблице](#table)  
  
<a name="RFormatString"></a>   
## <a name="the-round-trip-r-format-specifier"></a>Описатель формата обратного преобразования ("R")  
 Описатель формата обратного преобразования («R») пытается убедитесь, что числовое значение, которое преобразуется в строку анализируется обратно в то же числовое значение. Этот формат поддерживается только для типов <xref:System.Single>, <xref:System.Double> и <xref:System.Numerics.BigInteger>.  

Для <xref:System.Double> и <xref:System.Single> значения, описатель формата «R» в некоторых случаях не удается успешного обратного преобразования исходного значения и также предлагает относительно низкой производительности. Вместо этого рекомендуется использовать [«G17»](#GFormatString) описатель для формата <xref:System.Double> значения и [«G9»](#GFormatString) описатель формата для успешного обратного преобразования <xref:System.Single> значения.

 Если с помощью этого описателя форматируется значение типа <xref:System.Numerics.BigInteger>, то его строковое представление будет содержать все значащие цифры <xref:System.Numerics.BigInteger>.  
  
 Хотя описатель точности можно указать, он будет проигнорирован. Приведенные указатели приема-передачи в данном случае имеют преимущество перед указателем точности.    
 Форматирование результирующей строки определяется сведениями о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>. В следующей таблице представлены свойства <xref:System.Globalization.NumberFormatInfo>, обеспечивающие управление форматированием результирующей строки.  
  
|Свойство NumberFormatInfo|Описание|  
|-------------------------------|-----------------|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Определяет строку, указывающую, что число является отрицательным.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Определяет строку, разделяющую целую и дробную части числа.|  
|<xref:System.Globalization.NumberFormatInfo.PositiveSign%2A>|Определяет строку, указывающую, что экспонента является положительной.|  
  
 Следующие форматы пример <xref:System.Numerics.BigInteger> с помощью спецификатора формата приема-передачи.  
  
 [!code-cpp[R format specifier with a BigInteger](../../../samples/snippets/standard/base-types/format-strings/biginteger-r.cpp)]
 [!code-csharp[R format specifier with a BigInteger](../../../samples/snippets/standard/base-types/format-strings/biginteger-r.cs)]
 [!code-vb[R format specifier with a BigInteger](../../../samples/snippets/standard/base-types/format-strings/biginteger-r.vb)]  
  
> [!IMPORTANT]
>  В некоторых случаях для значений <xref:System.Double>, отформатированных с использованием строки стандартного числового формата "R", не удается успешно выполнить обратное преобразование при компиляции с использованием параметра `/platform:x64` или `/platform:anycpu` и запуска в 64-разрядных системах. Дополнительные сведения см. в следующем абзаце.  
  
 Чтобы избежать проблемы со значениями <xref:System.Double>, отформатированными с использованием строки стандартного числового формата R, для которых не удалось выполнить обратное преобразование при компиляции с использованием параметра `/platform:x64` или `/platform:anycpu` в 64-разрядных системах, можно отформатировать значения <xref:System.Double> с помощью строки стандартного числового формата G17. В примере ниже используется строка формата "R" со значением <xref:System.Double>, для которого не удается выполнить обратное преобразование, а также строка формата "G17" для успешного обратного преобразования исходного значения.  
  
 [!code-csharp[System.Double.ToString#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Double.ToString/cs/roundtripex1.cs#5)]
 [!code-vb[System.Double.ToString#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Double.ToString/vb/roundtripex1.vb#5)]  
  
 [К таблице](#table)  
  
<a name="XFormatString"></a>   
## <a name="the-hexadecimal-x-format-specifier"></a>Описатель шестнадцатеричного формата ("X")  
 При использовании описателя шестнадцатеричного формата ("X") число преобразуется в строку шестнадцатеричных цифр. Регистр шестнадцатеричных цифр больше 9 совпадает с регистром описателя формата. Например, чтобы получить запись "ABCDEF", задайте описатель X" или, наоборот, задайте описатель "x", чтобы получить "abcdef". Этот формат доступен только для целых типов.  
  
 Минимальное количество знаков в выходной строке задается спецификатором точности. Недостающие знаки в строке заменяются нулями.  
  
 Форматирование результирующей строки не зависит от сведений о форматировании в текущем объекте <xref:System.Globalization.NumberFormatInfo>.  
  
 В следующем примере значения <xref:System.Int32> форматируются с помощью спецификатора шестнадцатеричного формата.  
  
 [!code-cpp[Formatting.Numeric.Standard#9](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#9)]
 [!code-csharp[Formatting.Numeric.Standard#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#9)]
 [!code-vb[Formatting.Numeric.Standard#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#9)]  
  
 [К таблице](#table)  
  
<a name="NotesStandardFormatting"></a>   
## <a name="notes"></a>Примечания  
  
### <a name="control-panel-settings"></a>Настройки панели управления  
 Параметры элемента панели управления **Язык и региональные стандарты** влияют на выходную строку, получаемую в результате операции форматирования. Эти параметры используются для инициализации объекта <xref:System.Globalization.NumberFormatInfo>, связанного с языком и региональными параметрами текущего потока, откуда берутся значения, используемые для управления форматированием. Результирующие строки будут различаться на компьютерах с разными параметрами.  
  
 Кроме того Если <xref:System.Globalization.CultureInfo.%23ctor%28System.String%29?displayProperty=nameWithType> конструктор используется для создания нового экземпляра <xref:System.Globalization.CultureInfo> , представляющий язык и региональные параметры, как текущую культуру системы, настройки, заданные в **язык и региональные стандарты** на панели управления будут применяться к новому <xref:System.Globalization.CultureInfo> объекта. Можно воспользоваться конструктором <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> для создания объекта <xref:System.Globalization.CultureInfo>, который не отражает настройки системы.  
  
### <a name="numberformatinfo-properties"></a>Свойства NumberFormatInfo  
 На форматирование влияют свойства текущего объекта <xref:System.Globalization.NumberFormatInfo>, который неявно определяется на основе языка и региональных параметров текущего потока или явно задается параметром <xref:System.IFormatProvider> метода, который вызывает форматирование. Укажите объект <xref:System.Globalization.NumberFormatInfo> или объект <xref:System.Globalization.CultureInfo> для этого параметра.  
  
> [!NOTE]
>  Дополнительные сведения о настройке шаблонов или строк, используемых в форматировании числовых значений см. статью о классе <xref:System.Globalization.NumberFormatInfo>.  
  
### <a name="integral-and-floating-point-numeric-types"></a>Целочисленные типы и типы с плавающей запятой  
 Некоторые описания спецификаторов стандартных числовых форматов относятся к целочисленным типам и типам с плавающей запятой. Целочисленные типы — это <xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64> и <xref:System.Numerics.BigInteger>. Числовыми типами с плавающей запятой являются <xref:System.Decimal>, <xref:System.Single> и <xref:System.Double>.  
  
### <a name="floating-point-infinities-and-nan"></a>Бесконечности действительных чисел с плавающей запятой и NaN  
 Если, вне зависимости от строки формата, значение типа с плавающей запятой <xref:System.Single> или <xref:System.Double> является положительной бесконечностью, отрицательной бесконечностью или не является числом (NaN), отформатированная строка будет содержать значение соответствующего свойства (<xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol%2A>, <xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol%2A> или <xref:System.Globalization.NumberFormatInfo.NaNSymbol%2A>) применимого в настоящий момент объекта <xref:System.Globalization.NumberFormatInfo>.  
  
<a name="example"></a>   
## <a name="example"></a>Пример  
 В следующем примере с помощью языка и региональных параметров "en-US" и всех описателей стандартных числовых форматов форматируется целочисленное значение и числовое значение с плавающей запятой. В этом примере используются два числовых типа (<xref:System.Double> и <xref:System.Int32>), но аналогичные результаты были бы получены для любых других числовых типов (<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>, <xref:System.Numerics.BigInteger>, <xref:System.Decimal> и <xref:System.Single>).  
  
 [!code-csharp[system.x.tostring-and-culture#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.X.ToString-and-Culture/cs/xts.cs#1)]
 [!code-vb[system.x.tostring-and-culture#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.X.ToString-and-Culture/vb/xts.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Globalization.NumberFormatInfo>  
 [Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md)  
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)  
 [Практическое руководство. Добавление к числу начальных нулей](../../../docs/standard/base-types/how-to-pad-a-number-with-leading-zeros.md)  
 [Пример. Служебная программа форматирования для .NET Framework 4](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)  
 [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md)
