---
title: Строки стандартных форматов даты и времени
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- custom DateTime format string
- format specifiers, custom date and time
- format strings
- custom date and time format strings
- formatting [.NET Framework], time
- date and time strings
ms.assetid: bb79761a-ca08-44ee-b142-b06b3e2fc22b
ms.openlocfilehash: b67b00fdb4a5c484c112cc2f3321ce2268d4dad7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121712"
---
# <a name="standard-date-and-time-format-strings"></a>Строки стандартных форматов даты и времени

Строка стандартного формата даты и времени использует один описатель формата для определения текстового представления значения даты и времени. Любая строка формата даты и времени, содержащая более одного символа, включая пробел, интерпретируется как строка настраиваемого формата даты и времени. Дополнительные сведения см. в разделе [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md). Строку стандартного или пользовательского формата можно использовать двумя способами:

- Для определения строки, являющейся результатом операции форматирования.

- Для определения текстового представления значения даты и времени, которое можно преобразовать в значение <xref:System.DateTime> или <xref:System.DateTimeOffset> с помощью операции синтаксического анализа.

> [!TIP]
> Вы можете загрузить **служебную программу форматирования** — приложение Windows Forms для .NET Core, позволяющее применять строки формата к значениям даты и времени и числовым значениям и отображающее результирующую строку. Исходный код доступен для [C#](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs) и [Visual Basic](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-vb).

Строки стандартного формата даты и времени могут использоваться как со значением <xref:System.DateTime>, так и со значением <xref:System.DateTimeOffset>.

[!INCLUDE[C# interactive-note](~/includes/csharp-interactive-with-utc-partial-note.md)]

<a name="table"></a> В следующей таблице описаны спецификаторы стандартных форматов даты и времени. Если не указано иное, то описатель стандартного формата даты и времени выдает одинаковое строковое представление независимо от того, используется ли он со значением <xref:System.DateTime> или со значением <xref:System.DateTimeOffset>. Дополнительные сведения об использовании стандартных строк формата даты и времени см. в подразделе [Примечания](#Notes).

|Описатель формата|ОПИСАНИЕ|Примеры|
|----------------------|-----------------|--------------|
|"d"|Короткий шаблон даты.<br /><br /> Дополнительные сведения см. в подразделе [Описатель короткого формата даты (d)](#ShortDate).|2009-06-15T13:45:30 -> 6/15/2009 (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15/06/2009 (fr-FR)<br /><br /> 2009-06-15T13:45:30 -> 2009/06/15 (ja-JP)|
|"D"|Полный шаблон даты.<br /><br /> Дополнительные сведения см. в подразделе [Описатель полного формата даты (D)](#LongDate).|2009-06-15T13:45:30 -> Monday, June 15, 2009 (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15 июня 2009 г. (ru-RU)<br /><br /> 2009-06-15T13:45:30 -> Montag, 15. Juni 2009 (de-DE)|
|"f"|Полный шаблон даты и времени (короткий шаблон времени).<br /><br /> Дополнительная информация: [Описатель полного формата даты и краткого формата времени ("f")](#FullDateShortTime).|2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> den 15 juni 2009 13:45 (sv-SE)<br /><br /> 2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45 μμ (el-GR)|
|"F"|Полный шаблон даты и времени (полный шаблон времени).<br /><br /> Дополнительная информация: [Описатель полного формата даты и полного формата времени ("F")](#FullDateLongTime).|2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> den 15 juni 2009 13:45:30 (sv-SE)<br /><br /> 2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45:30 μμ (el-GR)|
|"g"|Общий шаблон даты и времени (короткий шаблон времени).<br /><br /> Дополнительная информация: [Описатель общего формата даты и краткого формата времени ("g")](#GeneralDateShortTime).|2009-06-15T13:45:30 -> 6/15/2009 1:45 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15/06/2009 13:45 (es-ES)<br /><br /> 2009-06-15T13:45:30 -> 2009/6/15 13:45 (zh-CN)|
|"G"|Общий шаблон даты и времени (полный шаблон времени).<br /><br /> Дополнительная информация: [Описатель общего формата даты и полного формата времени ("G")](#GeneralDateLongTime).|2009-06-15T13:45:30 -> 6/15/2009 1:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15/06/2009 13:45:30 (es-ES)<br /><br /> 2009-06-15T13:45:30 -> 2009/6/15 13:45:30 (zh-CN)|
|"M", "m"|Шаблон дней месяца.<br /><br /> Дополнительная информация: [Описатель формата месяца ("M", "m")](#MonthDay).|2009-06-15T13:45:30 -> June 15 (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15. juni (da-DK)<br /><br /> 2009-06-15T13:45:30 -> 15 Juni (id-ID)|
|"O", "o"|Шаблон обратного преобразования даты и времени.<br /><br /> Дополнительная информация: [Описатель формата обратного преобразования ("O", "o")](#Roundtrip).|Значения <xref:System.DateTime>:<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Local) --> 2009-06-15T13:45:30.0000000-07:00<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Utc) --> 2009-06-15T13:45:30.0000000Z<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Unspecified) --> 2009-06-15T13:45:30.0000000<br /><br /> Значения <xref:System.DateTimeOffset>:<br /><br /> 2009-06-15T13:45:30-07:00 --> 2009-06-15T13:45:30.0000000-07:00|
|"R", "r"|Шаблон RFC1123.<br /><br /> Дополнительная информация: [Описатель формата RFC1123 ("R", "r")](#RFC1123).|2009-06-15T13:45:30 -> Mon, 15 Jun 2009 20:45:30 GMT|
|"s"|Сортируемый шаблон времени и даты.<br /><br /> Дополнительная информация: [Описатель сортируемого формата ("s")](#Sortable).|2009-06-15T13:45:30 (DateTimeKind.Local) -> 2009-06-15T13:45:30<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Utc) -> 2009-06-15T13:45:30|
|"t"|Короткий шаблон времени.<br /><br /> Дополнительная информация: [Описатель короткого формата времени ("t")](#ShortTime).|2009-06-15T13:45:30 -> 1:45 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 13:45 (hr-HR)<br /><br /> 2009-06-15T13:45:30 -> 01:45 م (ar-EG)|
|"T"|Полный шаблон времени.<br /><br /> Дополнительная информация: [Описатель полного формата времени ("T")](#LongTime).|2009-06-15T13:45:30 -> 1:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 13:45:30 (hr-HR)<br /><br /> 2009-06-15T13:45:30 -> 01:45:30 م (ar-EG)|
|"u"|Универсальный сортируемый шаблон времени и даты.<br /><br /> Дополнительная информация: [Описатель универсального сортируемого формата ("u")](#UniversalSortable).|Со значением <xref:System.DateTime>: 2009-06-15T13:45:30 -> 2009-06-15 13:45:30Z<br /><br /> Со значением <xref:System.DateTimeOffset>: 2009-06-15T13:45:30 -> 2009-06-15 20:45:30Z|
|"U"|Универсальный полный шаблон даты и времени.<br /><br /> Дополнительная информация: [Описатель универсального полного формата ("U")](#UniversalFull).|2009-06-15T13:45:30 -> Monday, June 15, 2009 8:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> den 15 juni 2009 20:45:30 (sv-SE)<br /><br /> 2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 8:45:30 μμ (el-GR)|
|"Y", "y"|Шаблон месяца года.<br /><br /> Дополнительная информация: [Описатель формата месяца года ("Y")](#YearMonth).|2009-06-15T13:45:30 -> June, 2009 (en-US)<br /><br /> 2009-06-15T13:45:30 -> juni 2009 (da-DK)<br /><br /> 2009-06-15T13:45:30 -> Juni 2009 (id-ID)|
|Любой другой символ|Неизвестный описатель.|Создает исключение времени выполнения <xref:System.FormatException>.|

## <a name="how-standard-format-strings-work"></a>Как работают строки стандартного формата

В операции форматирования строка стандартного формата — это всего лишь псевдоним для строки пользовательского формата. Преимуществом использования псевдонима для ссылки на строку пользовательского формата является то, что при изменении строки пользовательского формата псевдоним может оставаться неизменным. Это важно, поскольку строковые представления значений даты и времени обычно зависят от региональных параметров. Например, строка стандартного формата "d" указывает, что значение даты и времени будет отображаться с использованием шаблона короткого формата даты. Для инвариантных региональных параметров таким шаблоном является "мм/дд/гггг". Для региональных параметров fr-FR это "дд/мм/гггг". Для региональных параметров ja-JP это "гггг/мм/дд".

Если строка стандартного формата в операции форматирования сопоставлена со строкой пользовательского формата для определенных региональных параметров, то приложение может определить конкретные региональные параметры, для которых строки пользовательского формата используются одним из следующих способов:

- Можно использовать региональные параметры по умолчанию (или текущие). Следующий пример отображает дату в формате короткой даты, соответствующем текущим региональным параметрам. В этом случае текущими региональными параметрами являются en-US.

  [!code-csharp-interactive[System.DateTime.Conceptual.Formatting#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/cs/StandardFormats1.cs#1)]
  [!code-vb[System.DateTime.Conceptual.Formatting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/vb/StandardFormats1.vb#1)]

- Можно передать объект <xref:System.Globalization.CultureInfo>, представляющий язык и региональные параметры, соответствующее которым форматирование будет использоваться методом с параметром <xref:System.IFormatProvider>. Следующий пример отображает дату в формате короткой даты, соответствующем региональным параметрам pt-BR.

  [!code-csharp[System.DateTime.Conceptual.Formatting#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/cs/StandardFormats1.cs#2)]
  [!code-vb[System.DateTime.Conceptual.Formatting#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/vb/StandardFormats1.vb#2)]

- Можно передать объект <xref:System.Globalization.DateTimeFormatInfo>, предоставляющий данные форматирования методу с параметром <xref:System.IFormatProvider>. В следующем примере дата отображается с помощью короткого формата даты из объекта <xref:System.Globalization.DateTimeFormatInfo>, соответствующего региональным параметрам hr-HR.

  [!code-csharp[System.DateTime.Conceptual.Formatting#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/cs/StandardFormats1.cs#3)]
  [!code-vb[System.DateTime.Conceptual.Formatting#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/vb/StandardFormats1.vb#3)]

> [!NOTE]
> Дополнительные сведения о настройке шаблонов или строк, используемых в форматировании значений даты и времени, см. в статье о классе <xref:System.Globalization.NumberFormatInfo>.

В некоторых случаях строка стандартного формата служит удобным сокращением длинной строки пользовательского формата, который является неизменяемым. В эту категорию попадают четыре строки стандартного формата: "O" (или "o"), "R" (или "r"), "s" и "u". Эти строки соответствуют строкам пользовательского формата, соответствующего инвариантным региональным параметрам. Они создают строковые представления значений даты и времени, которые, предположительно, совпадают для различных региональных параметров. В следующей таблице приведены сведения об этих четырех строках стандартных форматов даты и времени.

|Строка стандартного формата|Определена свойством DateTimeFormatInfo.InvariantInfo|Строка пользовательского формата|
|----------------------------|----------------------------------------------------------|--------------------------|
|"O" или "o"|Нет|гггг'-'мм'-'дд'T'чч':'мм':'сс'.'fffffffzz|
|"R" или "r"|<xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern%2A>|ддд, дд ммм гггг чч':'мм':'сс 'GMT'|
|"s"|<xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern%2A>|гггг'-'мм'-'дд'T'чч':'мм':'сс|
|"u"|<xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>|гггг'-'мм'-'дд чч':'мм':'сс'Z'|

Строки стандартного формата также можно использовать в операциях синтаксического анализа с методами <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> и <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, которые требуют для успешного выполнения операции синтаксического анализа, чтобы входная строка строго соответствовала определенному шаблону. Многие строки стандартного формата сопоставляются с несколькими строками пользовательского формата, поэтому значение даты и времени может быть представлено в разных форматах, при этом операция синтаксического анализа пройдет успешно. Определить одну или несколько строк пользовательского формата, соответствующих строке стандартного формата, можно, вызвав метод <xref:System.Globalization.DateTimeFormatInfo.GetAllDateTimePatterns%28System.Char%29?displayProperty=nameWithType>. В следующем примере показаны строки пользовательского формата, сопоставленные со строкой стандартного формата "d" (шаблон короткого формата даты).

[!code-csharp[Formatting.DateAndTime.Standard#17](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/stdandparsing1.cs#17)]
[!code-vb[Formatting.DateAndTime.Standard#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/stdandparsing1.vb#17)]

В следующих разделах представлены описатели стандартных форматов для значений <xref:System.DateTime> и <xref:System.DateTimeOffset>.

<a name="ShortDate"></a>

## <a name="the-short-date-d-format-specifier"></a>Описатель короткого формата даты ("d")

Описатель стандартного формата "d" представляет строку настраиваемого формата даты и времени, определяемую свойством <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType> для конкретного языка и региональных параметров. Например, строкой настраиваемого формата, возвращаемой свойством <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A> для инвариантного языка и региональных параметров, будет строка "ММ/дд/гггг".

В следующей таблице представлены свойства объекта <xref:System.Globalization.DateTimeFormatInfo>, обеспечивающие управление форматированием возвращаемой строки.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A>|Определяет общий формат результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A>|Определяет строку, разделяющую компоненты даты — год, месяц и день.|

В следующем примере описатель формата "d" используется для отображения значения даты и времени.

[!code-csharp[Formatting.DateAndTime.Standard#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#1)]
[!code-vb[Formatting.DateAndTime.Standard#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#1)]

[К таблице](#table)

<a name="LongDate"></a>

## <a name="the-long-date-d-format-specifier"></a>Описатель полного формата даты ("D")

Описатель стандартного формата "D" представляет строку настраиваемого формата даты и времени, определяемую текущим свойством <xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A?displayProperty=nameWithType>. Например, строкой пользовательского формата для инвариантных региональных параметров является "дддд, дд мммм гггг".

В следующей таблице представлены свойства объекта <xref:System.Globalization.DateTimeFormatInfo>, обеспечивающие управление форматированием возвращаемой строки.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A>|Определяет общий формат результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Определяет переведенные названия дней, которые могут входить в результирующую строку.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Определяет переведенные названия месяцев, которые могут входить в результирующую строку.|

В следующем примере описатель формата "D" используется для отображения значения даты и времени.

[!code-csharp[Formatting.DateAndTime.Standard#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#2)]
[!code-vb[Formatting.DateAndTime.Standard#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#2)]

[К таблице](#table)

<a name="FullDateShortTime"></a>

## <a name="the-full-date-short-time-f-format-specifier"></a>Описатель полного формата даты и краткого формата времени ("f")

Описатель стандартного формата "f" представляет сочетание полного формата даты ("D") и короткого формата времени ("t"), разделенных пробелом.

Форматирование результирующей строки определяется сведениями о форматировании в указанном объекте <xref:System.Globalization.DateTimeFormatInfo>. В следующей таблице представлены свойства объекта <xref:System.Globalization.DateTimeFormatInfo>, обеспечивающие управление форматированием возвращаемой строки. Настраиваемый описатель формата, возвращаемый свойствами <xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A?displayProperty=nameWithType> и <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType> некоторых языков и региональных параметров, может использовать не все свойства.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A>|Определяет формат компонента даты результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A>|Определяет формат компонента времени результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Определяет переведенные названия дней, которые могут входить в результирующую строку.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Определяет переведенные названия месяцев, которые могут входить в результирующую строку.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Определяет строку, разделяющую компоненты времени — часы, минуты и секунды.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.|

В следующем примере описатель формата "f" используется для отображения значения даты и времени.

[!code-csharp[Formatting.DateAndTime.Standard#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#3)]
[!code-vb[Formatting.DateAndTime.Standard#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#3)]

[К таблице](#table)

<a name="FullDateLongTime"></a>

## <a name="the-full-date-long-time-f-format-specifier"></a>Описатель полного формата даты и полного формата времени ("F")

Описатель стандартного формата "F" представляет строку настраиваемого формата даты и времени, определяемую текущим свойством <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType>. Например, строкой пользовательского формата для инвариантных региональных параметров является "дддд, дд мммм гггг чч:мм:сс".

В следующей таблице представлены свойства объекта <xref:System.Globalization.DateTimeFormatInfo>, обеспечивающие управление форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойством <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A> некоторых языков и региональных параметров, может использовать не все свойства.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A>|Определяет общий формат результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Определяет переведенные названия дней, которые могут входить в результирующую строку.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Определяет переведенные названия месяцев, которые могут входить в результирующую строку.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Определяет строку, разделяющую компоненты времени — часы, минуты и секунды.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.|

В следующем примере описатель формата "F" используется для отображения значения даты и времени.

[!code-csharp[Formatting.DateAndTime.Standard#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#4)]
[!code-vb[Formatting.DateAndTime.Standard#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#4)]

[К таблице](#table)

<a name="GeneralDateShortTime"></a>

## <a name="the-general-date-short-time-g-format-specifier"></a>Описатель общего формата даты и краткого формата времени ("g")

Описатель стандартного формата "g" представляет сочетание краткого формата даты ("d") и краткого формата времени ("t"), разделенных пробелом.

Форматирование результирующей строки определяется сведениями о форматировании в указанном объекте <xref:System.Globalization.DateTimeFormatInfo>. В следующей таблице представлены свойства объекта <xref:System.Globalization.DateTimeFormatInfo>, обеспечивающие управление форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойствами <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType> и <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType> некоторых языков и региональных параметров, может использовать не все свойства.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A>|Определяет формат компонента даты результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A>|Определяет формат компонента времени результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A>|Определяет строку, разделяющую компоненты даты — год, месяц и день.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Определяет строку, разделяющую компоненты времени — часы, минуты и секунды.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.|

В следующем примере описатель формата "g" используется для отображения значения даты и времени.

[!code-csharp[Formatting.DateAndTime.Standard#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#5)]
[!code-vb[Formatting.DateAndTime.Standard#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#5)]

[К таблице](#table)

<a name="GeneralDateLongTime"></a>

## <a name="the-general-date-long-time-g-format-specifier"></a>Описатель общего формата даты и полного формата времени ("G")

Описатель стандартного формата "G" представляет сочетание краткого формата даты ("d") и полного формата времени ("T"), разделенных пробелом.

Форматирование результирующей строки определяется сведениями о форматировании в указанном объекте <xref:System.Globalization.DateTimeFormatInfo>. В следующей таблице представлены свойства объекта <xref:System.Globalization.DateTimeFormatInfo>, обеспечивающие управление форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойствами <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType> и <xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A?displayProperty=nameWithType> некоторых языков и региональных параметров, может использовать не все свойства.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A>|Определяет формат компонента даты результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A>|Определяет формат компонента времени результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A>|Определяет строку, разделяющую компоненты даты — год, месяц и день.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Определяет строку, разделяющую компоненты времени — часы, минуты и секунды.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.|

В следующем примере описатель формата "G" используется для отображения значения даты и времени.

[!code-csharp[Formatting.DateAndTime.Standard#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#6)]
[!code-vb[Formatting.DateAndTime.Standard#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#6)]

[К таблице](#table)

<a name="MonthDay"></a>

## <a name="the-month-m-m-format-specifier"></a>Описатель формата месяца ("M", "m")

Описатель стандартного формата "M" или "m" представляет строку настраиваемого формата даты и времени, определяемую текущим свойством <xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern%2A?displayProperty=nameWithType>. Например, строкой пользовательского формата для инвариантных региональных параметров является "мммм дд".

В следующей таблице представлены свойства объекта <xref:System.Globalization.DateTimeFormatInfo>, обеспечивающие управление форматированием возвращаемой строки.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern%2A>|Определяет общий формат результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Определяет переведенные названия месяцев, которые могут входить в результирующую строку.|

В следующем примере описатель формата "m" используется для отображения значения даты и времени.

[!code-csharp[Formatting.DateAndTime.Standard#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#7)]
[!code-vb[Formatting.DateAndTime.Standard#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#7)]

[К таблице](#table)

<a name="Roundtrip"></a>

## <a name="the-round-trip-o-o-format-specifier"></a>Описатель формата обратного преобразования ("O", "o")

Описатель формата обратного преобразования ("O", "o") представляет строку настраиваемого формата даты и времени, используя шаблон, который сохраняет данные о часовом поясе и возвращает строковое значение, соответствующее стандарту ISO 8601. Для значений <xref:System.DateTime> этот спецификатор формата предназначен для сохранения значений даты и времени вместе со свойством <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> в тексте. Форматированная строка может быть преобразована обратно с помощью метода <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> или <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, если параметр `styles` имеет значение <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType>.

Описатель формата обратного преобразования "O" или "o" соответствует строке настраиваемого формата "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffK" для значений <xref:System.DateTime> и "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffzzz" — для значений <xref:System.DateTimeOffset>. В данной строке пары апострофов, разделяющие отдельные символы, такие как дефисы, двоеточия и букву "T", указывают, что отдельный символ является литералом, который не может быть изменен. Сами апострофы не отображаются в выходной строке.

Описатель формата обратного преобразования O или o (и строка настраиваемого формата "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffK") использует преимущества ISO 8601, а именно три способа представления сведений о часовом поясе для сохранения свойства <xref:System.DateTime.Kind%2A> значений <xref:System.DateTime>:

- Компонент часового пояса значений даты и времени типа <xref:System.DateTimeKind.Local?displayProperty=nameWithType> — это смещение от часового пояса от UTC (например, +01:00, -07:00). Все значения <xref:System.DateTimeOffset> также представлены в этом формате.

- Компонент часового пояса значений даты и времени типа <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> использует символ "Z" (т. е. нулевое смещение) для представления часового пояса UTC.

- Значения даты и времени типа <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> не содержат сведения о часовом поясе.

Так как стандартный описатель формата "O" и "o" соответствует международному стандарту, операция форматирования или синтаксического анализа, использующая описатель, всегда использует инвариантный региональный параметр и григорианский календарь.

Строки, передаваемые методам `Parse`, `TryParse`, `ParseExact` и `TryParseExact` классов <xref:System.DateTime> и <xref:System.DateTimeOffset>, можно анализировать с помощью описателя формата "O" или "o", если они не представлены в одном из этих форматов. Для объектов <xref:System.DateTime> вызываемая перегрузка синтаксического анализа также должна содержать параметр `styles` со значением <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType>. Обратите внимание, что при вызове метода синтаксического анализа с настраиваемой строкой формата, которая соответствует описателю формата "O" или "o", вы не получите те же результаты, что при использовании описателя "O" и "o". Это вызвано тем, что методы синтаксического анализа, использующие настраиваемую строку формата, не могут обработать строковое представление значений даты и времени без компонента часового пояса и не могут использовать символ "Z" для указания часового пояса UTC.

В следующем примере используется описатель формата "o" для отображения ряда значений <xref:System.DateTime> и <xref:System.DateTimeOffset> на компьютере в тихоокеанском стандартном часовом поясе США.

[!code-csharp[Formatting.DateAndTime.Standard#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/o1.cs#8)]
[!code-vb[Formatting.DateAndTime.Standard#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/o1.vb#8)]

В следующем примере описатель формата "o" используется для создания форматированной строки, а затем для восстановления первоначальных значений даты и времени путем вызова метода `Parse`.

[!code-csharp[Formatting.DateandTime.Standard#16](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Roundtrip1.cs#16)]
[!code-vb[Formatting.DateandTime.Standard#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/RoundTrip1.vb#16)]

[К таблице](#table)

<a name="RFC1123"></a>

## <a name="the-rfc1123-r-r-format-specifier"></a>Описатель формата RFC1123 ("R", "r")

Описатель стандартного формата "R" или "r" представляет строку настраиваемого формата даты и времени, определяемую текущим свойством <xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern%2A?displayProperty=nameWithType>. Шаблон отражает определенный стандарт. Свойство предназначено только для чтения. Таким образом, оно не изменяется в зависимости от используемых региональных параметров или предоставленного поставщика формата. Строкой пользовательского формата является "ддд, дд ммм гггг чч':'мм':'сс 'GMT'". Когда используется этот спецификатор стандартного формата, операция форматирования или разбора всегда использует инвариантные региональные параметры.

Результирующая строка обусловлена следующими свойствами объекта <xref:System.Globalization.DateTimeFormatInfo>, возвращаемого свойством <xref:System.Globalization.DateTimeFormatInfo.InvariantInfo%2A?displayProperty=nameWithType>, представляющим инвариант языка и региональных параметров.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern%2A>|Определяет формат результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames%2A>|Определяет сокращенные названия дней, которые могут входить в результирующую строку.|
|<xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames%2A>|Определяет сокращенные названия месяцев, которые могут входить в результирующую строку.|

Хотя стандарт RFC 1123 выражает время в формате UTC, операция форматирования не изменяет значение объекта <xref:System.DateTime>, подлежащего форматированию. Таким образом, необходимо преобразовать значение <xref:System.DateTime> в UTC, вызвав метод <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> до выполнения операции форматирования. В то же время для значений <xref:System.DateTimeOffset> преобразование выполняется автоматически; нет необходимости вызывать метод <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> перед операцией форматирования.

В следующем примере используется описатель формата "r" для отображения значений <xref:System.DateTime> и <xref:System.DateTimeOffset> на компьютере в тихоокеанском стандартном часовом поясе США.

[!code-csharp-interactive[Formatting.DateAndTime.Standard#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#9)]
[!code-vb[Formatting.DateAndTime.Standard#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#9)]

[К таблице](#table)

<a name="Sortable"></a>

## <a name="the-sortable-s-format-specifier"></a>Описатель сортируемого формата ("s")

Описатель стандартного формата "s" представляет строку настраиваемого формата даты и времени, определяемую свойством <xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern%2A?displayProperty=nameWithType>. Шаблон отражает определенный стандарт (ISO 8601). Свойство предназначено только для чтения. Таким образом, оно не изменяется в зависимости от используемых региональных параметров или предоставленного поставщика формата. Строкой пользовательского формата является "гггг'-'мм'-'дд'T'чч':'мм':'сс".

Описатель формата "s" предназначен для создания строк результатов, согласованно отсортированных по возрастанию или убыванию на основе значений даты и времени. Соответственно, хотя описатель стандартного формата "s" представляет значение даты и времени в согласованном формате, операция форматирования не изменяет значение объекта даты и времени, которое форматируется в соответствии с его свойством <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> или значением <xref:System.DateTimeOffset.Offset%2A?displayProperty=nameWithType>. Например, строки результатов, полученные при форматировании значений даты и времени 2014-11-15T18:32:17+00:00 и 2014-11-15T18:32:17+08:00, идентичны.

Когда используется этот спецификатор стандартного формата, операция форматирования или разбора всегда использует инвариантные региональные параметры.

В следующем примере используется описатель формата "s" для отображения значений <xref:System.DateTime> и <xref:System.DateTimeOffset> на компьютере в тихоокеанском стандартном часовом поясе США.

[!code-csharp-interactive[Formatting.DateAndTime.Standard#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#10)]
[!code-vb[Formatting.DateAndTime.Standard#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#10)]

[К таблице](#table)

<a name="ShortTime"></a>

## <a name="the-short-time-t-format-specifier"></a>Описатель короткого формата времени ("t")

Описатель стандартного формата "t" представляет строку настраиваемого формата даты и времени, определяемую текущим свойством <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType>. Например, строкой пользовательского формата для инвариантных региональных параметров является "чч:мм".

Форматирование результирующей строки определяется сведениями о форматировании в указанном объекте <xref:System.Globalization.DateTimeFormatInfo>. В следующей таблице представлены свойства объекта <xref:System.Globalization.DateTimeFormatInfo>, обеспечивающие управление форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойством <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType> некоторых языков и региональных параметров, может использовать не все свойства.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A>|Определяет формат компонента времени результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Определяет строку, разделяющую компоненты времени — часы, минуты и секунды.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.|

В следующем примере описатель формата "t" используется для отображения значения даты и времени.

[!code-csharp[Formatting.DateAndTime.Standard#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#11)]
[!code-vb[Formatting.DateAndTime.Standard#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#11)]

[К таблице](#table)

<a name="LongTime"></a>

## <a name="the-long-time-t-format-specifier"></a>Описатель полного формата времени ("T")

Описатель стандартного формата "T" представляет строку настраиваемого формата даты и времени, определяемую свойством <xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A?displayProperty=nameWithType> для конкретного языка и региональных параметров. Например, строкой пользовательского формата для инвариантных региональных параметров является "чч:мм:сс".

В следующей таблице представлены свойства объекта <xref:System.Globalization.DateTimeFormatInfo>, обеспечивающие управление форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойством <xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A?displayProperty=nameWithType> некоторых языков и региональных параметров, может использовать не все свойства.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A>|Определяет формат компонента времени результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Определяет строку, разделяющую компоненты времени — часы, минуты и секунды.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.|

В следующем примере описатель формата "T" используется для отображения значения даты и времени.

[!code-csharp[Formatting.DateAndTime.Standard#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#12)]
[!code-vb[Formatting.DateAndTime.Standard#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#12)]

[К таблице](#table)

<a name="UniversalSortable"></a>

## <a name="the-universal-sortable-u-format-specifier"></a>Описатель универсального сортируемого формата ("u")

Описатель стандартного формата "u" представляет строку настраиваемого формата даты и времени, определяемую свойством <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A?displayProperty=nameWithType>. Шаблон отражает определенный стандарт. Свойство предназначено только для чтения. Таким образом, оно не изменяется в зависимости от используемых региональных параметров или предоставленного поставщика формата. Строкой пользовательского формата является "гггг'-'мм'-'дд чч':'мм':'сс'Z'". Когда используется этот спецификатор стандартного формата, операция форматирования или разбора всегда использует инвариантные региональные параметры.

Хотя результирующая строка должна отображать время в формате UTC, преобразование первоначального значения <xref:System.DateTime> в процессе форматирования не выполняется. Таким образом, необходимо преобразовать значение <xref:System.DateTime> в UTC, вызвав метод <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> до выполнения операции форматирования.  В то же время для значений <xref:System.DateTimeOffset> преобразование выполняется автоматически; нет необходимости вызывать метод <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> перед операцией форматирования.

В следующем примере описатель формата "u" используется для отображения значения даты и времени.

[!code-csharp-interactive[Formatting.DateAndTime.Standard#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#13)]
[!code-vb[Formatting.DateAndTime.Standard#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#13)]

[К таблице](#table)

<a name="UniversalFull"></a>

## <a name="the-universal-full-u-format-specifier"></a>Описатель универсального полного формата ("U")

Описатель стандартного формата "U" представляет строку настраиваемого формата даты и времени, определяемую свойством <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> для конкретного языка и региональных параметров. Этот шаблон совпадает с шаблоном "F". Тем не менее, значение <xref:System.DateTime> автоматически преобразуется в формат UTC до форматирования.

В следующей таблице представлены свойства объекта <xref:System.Globalization.DateTimeFormatInfo>, обеспечивающие управление форматированием возвращаемой строки. Описатель настраиваемого формата, возвращаемый свойством <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A> некоторых языков и региональных параметров, может использовать не все свойства.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A>|Определяет общий формат результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Определяет переведенные названия дней, которые могут входить в результирующую строку.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Определяет переведенные названия месяцев, которые могут входить в результирующую строку.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Определяет строку, разделяющую компоненты времени — часы, минуты и секунды.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Определяет строку, указывающую на время в интервале от полуночи до полудня в 12-часовом формате указания времени.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Определяет строку, указывающую на время в интервале от полудня до полуночи в 12-часовом формате указания времени.|

Описатель формата "U" не поддерживается типом <xref:System.DateTimeOffset> и выдает исключение <xref:System.FormatException>, если он используется для форматирования значения <xref:System.DateTimeOffset>.

В следующем примере описатель формата "U" используется для отображения значения даты и времени.

[!code-csharp[Formatting.DateAndTime.Standard#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#14)]
[!code-vb[Formatting.DateAndTime.Standard#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#14)]

[К таблице](#table)

<a name="YearMonth"></a>

## <a name="the-year-month-y-y-format-specifier"></a>Описатель формата месяца года ("Y", "y")

Описатель стандартного формата "Y", "y" представляет строку настраиваемого формата даты и времени, определяемую свойством <xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern%2A?displayProperty=nameWithType> для конкретного языка и региональных параметров. Например, строкой пользовательского формата для инвариантных региональных параметров является "гггг мммм".

В следующей таблице представлены свойства объекта <xref:System.Globalization.DateTimeFormatInfo>, обеспечивающие управление форматированием возвращаемой строки.

|Свойство.|ОПИСАНИЕ|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern%2A>|Определяет общий формат результирующей строки.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Определяет переведенные названия месяцев, которые могут входить в результирующую строку.|

В следующем примере описатель формата "y" используется для отображения значения даты и времени.

[!code-csharp[Formatting.DateAndTime.Standard#15](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#15)]
[!code-vb[Formatting.DateAndTime.Standard#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#15)]

[К таблице](#table)

<a name="Notes"></a>

## <a name="notes"></a>Примечания

### <a name="control-panel-settings"></a>Настройки панели управления

Параметры элемента панели управления **Язык и региональные стандарты** влияют на выходную строку, получаемую в результате операции форматирования. Эти параметры используются для инициализации объекта <xref:System.Globalization.DateTimeFormatInfo>, связанного с текущими региональными параметрами потока, который предоставляет значения, используемые для управления форматированием. Результирующие строки будут различаться на компьютерах с разными параметрами.

Кроме того, если конструктор <xref:System.Globalization.CultureInfo.%23ctor%28System.String%29?displayProperty=nameWithType> используется для создания нового экземпляра объекта <xref:System.Globalization.CultureInfo> , представляющего язык и региональные параметры, аналогичные текущему языку и региональным параметрам системы, то все настройки, заданные в разделе **Язык и региональные стандарты** панели управления, будут применяться к новому объекту <xref:System.Globalization.CultureInfo> . Можно воспользоваться конструктором <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> для создания объекта <xref:System.Globalization.CultureInfo> , который не отражает настройки системы.

### <a name="datetimeformatinfo-properties"></a>Свойства DateTimeFormatInfo

На форматирование влияют свойства текущего объекта <xref:System.Globalization.DateTimeFormatInfo>, которые задаются либо неявно, языком и региональными параметрами текущего потока, либо явно, параметром <xref:System.IFormatProvider> метода, который вызывает форматирование. Для параметра <xref:System.IFormatProvider> приложение должно указать объект <xref:System.Globalization.CultureInfo>, представляющий региональные параметры, или объект <xref:System.Globalization.DateTimeFormatInfo>, представляющий соглашения о форматировании даты и времени для конкретных региональных параметров. Многие спецификаторы стандартных форматов даты и времени являются псевдонимами для шаблонов форматирования, которые определены свойствами текущего объекта <xref:System.Globalization.DateTimeFormatInfo>. Приложение может изменить результат, полученный некоторыми спецификаторами стандартных форматов даты и времени, изменив соответствующие шаблоны форматирования соответствующего свойства <xref:System.Globalization.DateTimeFormatInfo>.

## <a name="see-also"></a>См. также

- <xref:System.DateTime?displayProperty=nameWithType>
- <xref:System.DateTimeOffset?displayProperty=nameWithType>
- [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)
- [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
- [Пример: служебная программа форматирования .NET Core WinForms (C#)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs)
- [Пример: служебная программа форматирования .NET Core WinForms (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-vb)
