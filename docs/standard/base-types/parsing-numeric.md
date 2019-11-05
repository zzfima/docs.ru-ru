---
title: Синтаксический анализ числовых строк в .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, numeric strings
- numeric strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
ms.openlocfilehash: ac44282a06b2b3710d3a9e5390c7a514c1632c3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127600"
---
# <a name="parsing-numeric-strings-in-net"></a>Синтаксический анализ числовых строк в .NET
Все числовые типы имеют два статических метода синтаксического анализа — `Parse` и `TryParse`, которые можно использовать для преобразования строкового представления числа в числовой тип. Эти методы позволяют анализировать строки, которые были созданы с помощью строк формата, описанных в разделах [Строки стандартных числовых форматов](../../../docs/standard/base-types/standard-numeric-format-strings.md) и [Строки настраиваемых числовых форматов](../../../docs/standard/base-types/custom-numeric-format-strings.md). По умолчанию методы `Parse` и `TryParse` могут успешно преобразовывать строки, содержащие целые десятичные числа, только в целочисленные значения. Они могут успешно преобразовывать строки, содержащие целые и дробные десятичные числа, разделители групп и десятичные разделители, в значения с плавающей запятой. Если операцию выполнить не удалось, метод `Parse` создает исключение, а метод `TryParse` возвращает значение `false`.  
  
## <a name="parsing-and-format-providers"></a>Синтаксический анализ и поставщики формата  
 Как правило, строковые представления числовых значений зависят от языка и региональных параметров. Для различных языков и региональных параметров используются различные элементы численных строк, такие как обозначения денежной единицы, разделители групп (тысяч) и десятичные разделители. Методы анализа неявно или явно используют поставщик формата, распознающий эти различия для разных языков и региональных параметров. Если поставщик формата не задан в вызове метода `Parse` или `TryParse`, используется поставщик формата, связанный с текущим языком и региональными параметрами (объект <xref:System.Globalization.NumberFormatInfo>, возвращаемый свойством <xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=nameWithType>).  
  
 Поставщик формата представлен реализацией интерфейса <xref:System.IFormatProvider>. Этот интерфейс содержит только один элемент — метод <xref:System.IFormatProvider.GetFormat%2A>, единственным параметром которого является объект <xref:System.Type>, представляющий тип для форматирования. Этот метод возвращает объект, предоставляющий сведения о форматировании. .NET поддерживает следующие две реализации <xref:System.IFormatProvider> для синтаксического анализа числовых строк:  
  
- объект <xref:System.Globalization.CultureInfo>, у которого метод <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> возвращает объект <xref:System.Globalization.NumberFormatInfo>, предоставляющий сведения о форматировании, связанные с языком и региональными параметрами;  
  
- объект <xref:System.Globalization.NumberFormatInfo>, у которого метод <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=nameWithType> возвращает сам этот объект.  
  
 В следующем примере код пытается преобразовать каждую строку массива в значение <xref:System.Double>. Сначала предпринимается попытка выполнить анализ строки с помощью поставщика формата, отражающего правила для языка и региональных параметров "Английский (США)". Если эта операция создает исключение <xref:System.FormatException>, предпринимается попытка выполнить синтаксический анализ строки на основе поставщика формата для языка и региональных параметров "Французский (Франция)".  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## <a name="parsing-and-numberstyles-values"></a>Синтаксический анализ и значения NumberStyles  
 Распознаваемые при синтаксическом анализе элементы стиля (например, пробелы, разделители групп и десятичные разделители) определяются значением перечисления <xref:System.Globalization.NumberStyles>. По умолчанию строки, представляющие целочисленные значения, анализируются с использованием значения <xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>, которое допускает только цифры, начальные и конечные пробелы и знак в начале. Строки, представляющие значения с плавающей запятой, анализируются с использованием сочетания значений <xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType> и <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>. Такой смешанный стиль поддерживает десятичные числа, начальные и конечные пробелы, знак в начале, десятичный разделитель, разделитель групп и показатель степени. Вызвав перегрузку метода `Parse` или `TryParse`, содержащего параметр типа <xref:System.Globalization.NumberStyles>, и установив один или несколько флагов <xref:System.Globalization.NumberStyles>, можно управлять выбором элементов стиля, допускаемых в строке для синтаксического анализа.  
  
 Например, строка, содержащая разделитель групп, не может быть преобразована в значение <xref:System.Int32> с помощью метода <xref:System.Int32.Parse%28System.String%29?displayProperty=nameWithType>. Однако преобразование пройдет успешно, если установить флаг <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>, как показано в следующем примере.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
> Операция синтаксического анализа всегда использует правила форматирования конкретного языка и региональных параметров. Если значения языка и региональных параметров не заданы в объекте <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.NumberFormatInfo>, используются язык и региональные параметры, связанные с текущим потоком.  
  
 В следующей таблице приводятся элементы перечисления <xref:System.Globalization.NumberStyles> и описано их влияние на операцию синтаксического анализа.  
  
|Значение NumberStyles|Влияние на анализируемую строку|  
|------------------------|---------------------------------------|  
|<xref:System.Globalization.NumberStyles.None?displayProperty=nameWithType>|Разрешены только цифры.|  
|<xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>|Разрешены десятичный разделитель и дробные числа. Для целых чисел в качестве дробного числа разрешен только ноль. Допустимые десятичные разделители определяются свойством <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=nameWithType> или <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>|Для указания экспоненциального представления может использоваться символ "e" или "E". Дополнительные сведения см. в статье <xref:System.Globalization.NumberStyles>.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>|Разрешены начальные пробелы.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>|Разрешены конечные пробелы.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>|Разрешен знак плюс или минус перед числом.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>|Разрешен знак плюс или минус, следующий за числом.|  
|<xref:System.Globalization.NumberStyles.AllowParentheses?displayProperty=nameWithType>|Для обозначения отрицательных значений можно использовать скобки.|  
|<xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>|Разрешен разделитель групп. Символ-разделитель групп определяется свойством <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=nameWithType> или <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.AllowCurrencySymbol?displayProperty=nameWithType>|Разрешено обозначение денежной единицы. Обозначение денежной единицы определяется свойством <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>|Анализируемая строка интерпретируется как шестнадцатеричное число. Он может включать символы шестнадцатеричного формата 0–9, A–F или a–f. Этот флаг используется только для анализа целых значений.|  
  
 Кроме того, перечисление <xref:System.Globalization.NumberStyles> предоставляет следующие смешанные стили, включающие несколько флагов <xref:System.Globalization.NumberStyles>.  
  
|Составное значение NumberStyles|Включает члены|  
|----------------------------------|----------------------|  
|<xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>|Включает стили <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType> и <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>. Это стиль по умолчанию, используемый для анализа целых значений.|  
|<xref:System.Globalization.NumberStyles.Number?displayProperty=nameWithType>|Включает стили <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType> и <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType>|Включает стили <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType> и <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Currency?displayProperty=nameWithType>|Включает все стили, кроме <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> и <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Any?displayProperty=nameWithType>|Включает все стили, кроме <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.HexNumber?displayProperty=nameWithType>|Включает стили <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType> и <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
  
## <a name="parsing-and-unicode-digits"></a>Синтаксический анализ и цифры в Юникоде  
 Стандарт Юникод определяет кодовые точки для цифр в различных системах письма. Например, кодовые точки в диапазоне от U+0030 до U+0039 представляют основные цифры от 0 до 9, кодовые точки в диапазоне от U+09E6 до U+09EF представляют бенгальские цифры от 0 до 9, а кодовые точки в диапазоне от U+FF10 до U+FF19 представляют полноширинные цифры от 0 до 9. Однако методами синтаксического анализа распознаются только основные цифры от 0 до 9 (кодовые точки от U+0030 до U+ 0039). Если методу анализа чисел передается строка, содержащая любые другие цифры, метод создает исключение <xref:System.FormatException>.  
  
 В примере ниже метод <xref:System.Int32.Parse%2A?displayProperty=nameWithType> используется для анализа строк, состоящих из цифр различных систем письма. Как показывает вывод, попытка анализа основных цифр завершается успешно, но попытка анализа полноширинных, арабо-индийских и бенгальских цифр заканчивается неудачей.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Globalization.NumberStyles>
- [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)
- [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)
