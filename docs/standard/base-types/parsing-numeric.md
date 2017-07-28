---
title: "Анализ числовых строк в .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "разбор строк, числовые строки"
  - "числовые строки"
  - "перечисления [.NET Framework], разбор строк"
  - "базовые типы, разбор строк"
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Анализ числовых строк в .NET Framework
Все числовые типы имеют два статических метода синтаксического анализа — `Parse` и `TryParse`, которые можно использовать для преобразования строкового представления числа в численное значение.  Эти методы позволяют анализировать строки, которые были созданы с помощью строк формата, описанных в разделах [Строки стандартных числовых форматов](../../../docs/standard/base-types/standard-numeric-format-strings.md) и [Строки настраиваемых числовых форматов](../../../docs/standard/base-types/custom-numeric-format-strings.md).  По умолчанию методы `Parse` и `TryParse` могут успешно преобразовывать строки, содержащие целые десятичные числа, только в целочисленные значения.  Они могут успешно преобразовывать строки, содержащие целые и дробные десятичные числа, разделители групп и десятичные разделители, в значения с плавающей запятой.  Если операцию не удалось выполнить, метод `Parse` вызывает исключение, а метод `TryParse` возвращает значение `false`.  
  
## Синтаксический анализ и поставщики формата  
 Часто строковое представление числовых значений различается в зависимости от языка и региональных параметров.  Для различных языков и региональных параметров могут использоваться различные элементы численных строк, такие как обозначение денежной единицы, разделители групп \(тысяч\) и десятичные разделители.  Методы анализа неявно или явно используют поставщик формата, распознающий эти различия для различных языков и региональных параметров.  Если поставщик формата не задан в вызове метода `Parse` или `TryParse`, используется поставщик формата, связанный с текущим языком и региональными параметрами \(объект <xref:System.Globalization.NumberFormatInfo>, возвращаемый свойством <xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=fullName>\).  
  
 Поставщик формата представлен реализацией интерфейса <xref:System.IFormatProvider>.  У этого интерфейса есть только один член — метод <xref:System.IFormatProvider.GetFormat%2A>, единственным параметром которого является объект <xref:System.Type>, представляющий тип для форматирования.  Этот метод возвращает объект, который предоставляет информацию форматирования.  Платформа .NET Framework поддерживает следующие две реализации интерфейса <xref:System.IFormatProvider> для синтаксического анализа числовых строк:  
  
-   Объект <xref:System.Globalization.CultureInfo>, метод <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=fullName> которого возвращает объект <xref:System.Globalization.NumberFormatInfo>, предоставляющий информацию форматирования в соответствии с языком и региональными параметрами.  
  
-   Объект <xref:System.Globalization.NumberFormatInfo>, метод <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=fullName> которого возвращает себя.  
  
 В следующем примере предпринимается попытка преобразовать каждую строку массива в значение типа <xref:System.Double>.  Сперва предпринимается попытка выполнить анализ строки с помощью поставщика формата, отражающего правила для языка и региональных параметров "Английский \(США\)".  Если в ходе операции создается исключение <xref:System.FormatException>, предпринимается попытка выполнить анализ строки с помощью поставщика формата, отражающего правила для языка и региональных параметров "Французский \(Франция\)".  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## Синтаксический анализ и значения NumberStyles  
 Элементы стиля, такие как пробелы, разделители групп и десятичные разделители, которые могут быть обработаны при синтаксическом анализе, определены значением перечисления <xref:System.Globalization.NumberStyles>.  По умолчанию строки, представляющие целые значения, обрабатываются с использованием значения <xref:System.Globalization.NumberStyles?displayProperty=fullName>, разрешающего только цифры, начальные и конечные пробелы и знак в начале.  Строки, представляющие значения с плавающей запятой, анализируются с использованием сочетания значений <xref:System.Globalization.NumberStyles?displayProperty=fullName> и <xref:System.Globalization.NumberStyles?displayProperty=fullName>. Такой смешанный стиль разрешает десятичные числа, начальные и конечные пробелы, знак в начале, разделители групп и показатель экспоненциального представления.  Вызвав перегрузку метода `Parse` или `TryParse`, включающего параметр типа <xref:System.Globalization.NumberStyles>, и установив один или несколько флажков <xref:System.Globalization.NumberStyles>, можно управлять элементами стиля, которые могут присутствовать в строке для успешного выполнения операции синтаксического анализа.  
  
 Например, строка, содержащая разделитель групп не может быть преобразована в значение <xref:System.Int32> с помощью метода <xref:System.Int32.Parse%28System.String%29?displayProperty=fullName>.  Однако преобразование пройдет успешно, если установить флаг <xref:System.Globalization.NumberStyles?displayProperty=fullName>, как показано в следующем примере.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
>  Операция синтаксического анализа всегда использует правила форматирования конкретного языка и региональных параметров.  Если не задать язык и региональные параметры, передав объект <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.NumberFormatInfo>, используются язык и региональные параметры, связанные с текущим потоком.  
  
 В следующей таблице перечислены члены перечисления <xref:System.Globalization.NumberStyles> и описано их влияние на операцию синтаксического анализа.  
  
|Значение NumberStyles|Влияние на анализируемую строку|  
|---------------------------|-------------------------------------|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Разрешены только цифры.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Разрешены десятичный разделитель и дробные числа.  Для целых чисел в качестве дробного числа разрешен только ноль.  Допустимые десятичные разделители определяются свойством <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=fullName> или <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Знак "e" или "E" может использоваться для указания на экспоненциальное представление.  Дополнительные сведения см. в разделе <xref:System.Globalization.NumberStyles>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Разрешены начальные пробелы.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Разрешены конечные пробелы.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Разрешен знак плюс или минус перед числом.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Разрешен знак плюс или минус, следующий за числом.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Для обозначения отрицательных значений можно использовать скобки.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Разрешен разделитель групп.  Символ разделения групп определяется свойством <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=fullName> или <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Разрешено обозначение денежной единицы.  Обозначение денежной единицы определяется свойством <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Анализируемая строка интерпретируется как шестнадцатеричное число.  Оно может включать знаки шестнадцатеричного формата 0\-9, A\-F и a\-f.  Этот флажок можно использовать только для анализа целых значений.|  
  
 Кроме того, перечисление <xref:System.Globalization.NumberStyles> предоставляет следующие смешанные стили, включающие несколько флажков <xref:System.Globalization.NumberStyles>.  
  
|Составное значение NumberStyles|Включает члены|  
|-------------------------------------|--------------------|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Включает стили <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> и <xref:System.Globalization.NumberStyles?displayProperty=fullName>.  Это стиль по умолчанию, используемый для анализа целых значений.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Включает стили <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> и <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Включает стили <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> и <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Включает все стили, кроме <xref:System.Globalization.NumberStyles?displayProperty=fullName> и <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Включает все стили, кроме <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Включает стили <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> и <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
  
## Синтаксический анализ и цифры в Юникоде  
 Стандарт Юникод определяет кодовые точки для цифр в различных системах письма.  Например, кодовые точки в диапазоне от U\+0030 до U\+0039 представляют основные цифры от 0 до 9, кодовые точки в диапазоне от U\+09E6 до U\+09EF представляют бенгальские цифры от 0 до 9, а кодовые точки в диапазоне от U\+FF10 до U\+FF19 представляют полноширинные цифры от 0 до 9.  Однако методами синтаксического анализа распознаются только основные цифры от 0 до 9 \(кодовые точки от U\+0030 до U\+0039\).  Если методу анализа чисел передается строка, содержащая любые другие цифры, метод создает исключение <xref:System.FormatException>.  
  
 В следующем примере используется метод <xref:System.Int32.Parse%2A?displayProperty=fullName> для анализа строк, состоящий их цифр различных систем письма.  Как показывает вывод, попытка анализа основных цифр завершается успешно, но попытка анализа полноширинных, арабо\-индийских и бенгальских цифр заканчивается неудачей.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## См. также  
 <xref:System.Globalization.NumberStyles>   
 [Разбор строк](../../../docs/standard/base-types/parsing-strings.md)   
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)