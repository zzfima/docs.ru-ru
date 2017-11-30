---
title: "Разбор числовых строк в .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, numeric strings
- numeric strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c9bb58b0d7b45ca197653742844be01ac3bbe41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-numeric-strings-in-net"></a>Разбор числовых строк в NET
Все числовые типы имеют два статических метода синтаксического анализа — `Parse` и `TryParse`, которые можно использовать для преобразования строкового представления числа в числовой тип. Эти методы позволяют анализировать строки, которые были созданы с помощью строк формата, описанных в разделах [Строки стандартных числовых форматов](../../../docs/standard/base-types/standard-numeric-format-strings.md) и [Строки настраиваемых числовых форматов](../../../docs/standard/base-types/custom-numeric-format-strings.md). По умолчанию методы `Parse` и `TryParse` могут успешно преобразовывать строки, содержащие целые десятичные числа, только в целочисленные значения. Они могут успешно преобразовывать строки, содержащие целые и дробные десятичные числа, разделители групп и десятичные разделители, в значения с плавающей запятой. Если операцию выполнить не удалось, метод `Parse` создает исключение, а метод `TryParse` возвращает значение `false`.  
  
## <a name="parsing-and-format-providers"></a>Синтаксический анализ и поставщики формата  
 Как правило, строковые представления числовых значений зависят от языка и региональных параметров. Для различных языков и региональных параметров используются различные элементы численных строк, такие как обозначения денежной единицы, разделители групп (тысяч) и десятичные разделители. Методы анализа неявно или явно используют поставщик формата, распознающий эти различия для разных языков и региональных параметров. Если поставщик формата не задан в вызове `Parse` или `TryParse` метод, поставщик формата, связанный с текущей культурой потока ( <xref:System.Globalization.NumberFormatInfo> объект, возвращаемый <xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=nameWithType> свойства) используется.  
  
 Поставщик формата представлен <xref:System.IFormatProvider> реализации. Этот интерфейс содержит один элемент <xref:System.IFormatProvider.GetFormat%2A> метод, единственным параметром которого является <xref:System.Type> , представляющий тип для форматирования. Этот метод возвращает объект, предоставляющий сведения о форматировании. .NET поддерживает следующие два <xref:System.IFormatProvider> реализации для синтаксического анализа числовых строк:  
  
-   Объект <xref:System.Globalization.CultureInfo> которого <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> возвращает <xref:System.Globalization.NumberFormatInfo> объект, предоставляющий сведения о форматировании для определенного языка и региональных параметров.  
  
-   Объект <xref:System.Globalization.NumberFormatInfo> которого <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=nameWithType> метод возвращает сам себя.  
  
 В следующем примере предпринимается попытка преобразовать каждую строку массива <xref:System.Double> значение. Сначала предпринимается попытка выполнить анализ строки с помощью поставщика формата, отражающего правила для языка и региональных параметров "Английский (США)". Если эта операция создает <xref:System.FormatException>, предпринимается попытка выполнить синтаксический анализ строки с помощью поставщика формата, отражающего правила французский (Франция) языка и региональных параметров.  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## <a name="parsing-and-numberstyles-values"></a>Синтаксический анализ и значения NumberStyles  
 Элементы стиля (такие как пробелы, разделители групп и десятичного разделителя), которые могут обрабатывать операции синтаксического анализа определяются <xref:System.Globalization.NumberStyles> значение перечисления. По умолчанию строки, представляющие целые значения, обрабатываются с использованием <xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType> значение, которое позволяет использовать только цифры, начальные и конечные пробелы и знак в начале. Строки, представляющие значения с плавающей запятой, анализируются с использованием сочетания <xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType> и <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> значений; это смешанный стиль разрешает десятичные числа, начальные и конечные пробелы, знак в начале, десятичного разделителя, группы разделитель, а показатель степени. Путем вызова перегрузки `Parse` или `TryParse` метод, который содержит параметр типа <xref:System.Globalization.NumberStyles> и установив один или несколько <xref:System.Globalization.NumberStyles> флаги, можно выбрать элементы стиля, которые могут быть представлены в строке операции анализа успешно.  
  
 Например, строка, содержащая разделитель групп, не может быть преобразована в значение <xref:System.Int32> с помощью метода <xref:System.Int32.Parse%28System.String%29?displayProperty=nameWithType>. Однако преобразование пройдет успешно, если установить флаг <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>, как показано в следующем примере.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
>  Операция синтаксического анализа всегда использует правила форматирования конкретного языка и региональных параметров. Если не указать язык и региональные параметры, передав <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.NumberFormatInfo> объекта, используется язык и региональные параметры, связанные с текущим потоком.  
  
 В следующей таблице перечислены элементы <xref:System.Globalization.NumberStyles> перечисления и описывает их влияние на операции анализа.  
  
|Значение NumberStyles|Влияние на анализируемую строку|  
|------------------------|---------------------------------------|  
|<xref:System.Globalization.NumberStyles.None?displayProperty=nameWithType>|Разрешены только цифры.|  
|<xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>|Разрешены десятичный разделитель и дробные числа. Для целых чисел в качестве дробного числа разрешен только ноль. Допустимые десятичные разделители определяются <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=nameWithType> или <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=nameWithType> свойства.|  
|<xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>|Для указания экспоненциального представления может использоваться символ "e" или "E". В разделе <xref:System.Globalization.NumberStyles> для получения дополнительных сведений.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>|Разрешены начальные пробелы.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>|Разрешены конечные пробелы.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>|Разрешен знак плюс или минус перед числом.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>|Разрешен знак плюс или минус, следующий за числом.|  
|<xref:System.Globalization.NumberStyles.AllowParentheses?displayProperty=nameWithType>|Для обозначения отрицательных значений можно использовать скобки.|  
|<xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>|Разрешен разделитель групп. Символ-разделитель групп определяется <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=nameWithType> или <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=nameWithType> свойства.|  
|<xref:System.Globalization.NumberStyles.AllowCurrencySymbol?displayProperty=nameWithType>|Разрешено обозначение денежной единицы. Обозначение денежной единицы определяется <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=nameWithType> свойство.|  
|<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>|Анализируемая строка интерпретируется как шестнадцатеричное число. Он может включать символы шестнадцатеричного формата 0–9, A–F или a–f. Этот флаг используется только для анализа целых значений.|  
  
 Кроме того <xref:System.Globalization.NumberStyles> перечисление предоставляет следующие смешанные стили, включающие несколько <xref:System.Globalization.NumberStyles> флаги.  
  
|Составное значение NumberStyles|Включает члены|  
|----------------------------------|----------------------|  
|<xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>|Включает в себя <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, и <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType> стили. Это стиль по умолчанию, используемый для анализа целых значений.|  
|<xref:System.Globalization.NumberStyles.Number?displayProperty=nameWithType>|Включает в себя <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>, и <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> стили.|  
|<xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType>|Включает в себя <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>, и <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> стили.|  
|<xref:System.Globalization.NumberStyles.Currency?displayProperty=nameWithType>|Включает все стили, кроме <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> и <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Any?displayProperty=nameWithType>|Включает все стили, кроме <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.HexNumber?displayProperty=nameWithType>|Включает в себя <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, и <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType> стили.|  
  
## <a name="parsing-and-unicode-digits"></a>Синтаксический анализ и цифры в Юникоде  
 Стандарт Юникод определяет кодовые точки для цифр в различных системах письма. Например, кодовые точки в диапазоне от U+0030 до U+0039 представляют основные цифры от 0 до 9, кодовые точки в диапазоне от U+09E6 до U+09EF представляют бенгальские цифры от 0 до 9, а кодовые точки в диапазоне от U+FF10 до U+FF19 представляют полноширинные цифры от 0 до 9. Однако методами синтаксического анализа распознаются только основные цифры от 0 до 9 (кодовые точки от U+0030 до U+ 0039). Если методу анализа чисел передается строка, содержащая любые другие цифры, этот метод вызывает <xref:System.FormatException>.  
  
 В следующем примере используется <xref:System.Int32.Parse%2A?displayProperty=nameWithType> метода для синтаксического анализа строки, состоящие из цифр в различные системы письма. Как показывает вывод, попытка анализа основных цифр завершается успешно, но попытка анализа полноширинных, арабо-индийских и бенгальских цифр заканчивается неудачей.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Globalization.NumberStyles>  
 [Анализ строк в .NET Framework](../../../docs/standard/base-types/parsing-strings.md)  
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)
