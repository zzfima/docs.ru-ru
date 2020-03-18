---
title: Как преобразовать строки в формат даты и времени
description: Ознакомьтесь с методами анализа строк, представляющих даты и время, и научитесь создавать строки в формате даты и времени из отдельных строк даты и строк времени.
ms.date: 02/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, date and time strings
- date and time strings
- ParseExact method
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- DateTime object
- time strings
ms.openlocfilehash: 9555304e570226b2ed3b040735cf099b5a018f93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156547"
---
# <a name="parsing-date-and-time-strings-in-net"></a>Синтаксический анализ строк даты и времени в .NET

Чтобы анализировать строки для преобразования их в объекты <xref:System.DateTime>, нужно указать, как значения даты и времени представлены в текстовом формате. Для различных языков и региональных параметров значения дня, месяца и года приводятся в разном порядке. В одних представлениях времени используется 24-часовой формат, в других же указываются значения AM и PM. В одних приложениях требуется только дата. В других — только время. А в некоторых нужно указывать и дату, и время. Методы преобразования строк в объекты <xref:System.DateTime> позволяют предоставлять подробные сведения о требуемых форматах и элементах дат и времени, которые необходимы для вашего приложения. Есть три подзадачи для правильного преобразования текста в <xref:System.DateTime>:

1. Укажите требуемый формат текста, представляющего дату и время.
1. Можно указать язык и региональные параметры для формата даты и времени.
1. Можно указать, как отсутствующие в тексте компоненты задаются в значениях даты и времени.

Методы <xref:System.DateTime.Parse%2A> и <xref:System.DateTime.TryParse%2A> позволяют преобразовать много стандартных представлений даты и времени. Методы <xref:System.DateTime.ParseExact%2A>и <xref:System.DateTime.TryParseExact%2A> позволяют преобразовать строковое представление, соответствующее шаблону, указанному в строке формата даты и времени. (Дополнительные сведения см. в статьях [Строки стандартных форматов даты и времени](standard-date-and-time-format-strings.md) и [Строки настраиваемых форматов даты и времени](custom-date-and-time-format-strings.md).)

Текущий объект <xref:System.Globalization.DateTimeFormatInfo> обеспечивает более точный контроль над тем, как текст должен интерпретироваться в качестве даты и времени. В свойствах <xref:System.Globalization.DateTimeFormatInfo> описываются разделители даты и времени, названия месяцев, дней и эр, а также формат для обозначения AM и PM. Объект <xref:System.Globalization.DateTimeFormatInfo> в текущем потоке представляет текущие язык и региональные параметры. Если требуется задать определенные язык и региональные параметры или настраиваемые параметры, укажите для метода анализа параметр <xref:System.IFormatProvider>. Для параметра <xref:System.IFormatProvider> следует указать объект <xref:System.Globalization.CultureInfo>, представляющий язык и региональные параметры, или объект <xref:System.Globalization.DateTimeFormatInfo>.

В тексте, представляющем дату и время, могут отсутствовать некоторые сведения. Например, большинство пользователей будет считать, что дата "12 марта" относится к текущему году. Аналогичным образом, "март 2018 г." представляет месяц март 2018 года. Текст, представляющий время, часто включает только часы, минуты и обозначение AM или PM.  При помощи методов анализа эти отсутствующие данные обрабатываются с использованием обоснованных значений по умолчанию:

- если указано только время, в части даты используется текущая дата;
- если указана только дата, в части времени задается полночь;
- если в дате не указан год, используется текущий год;
- если не указано число месяца, задается первое число месяца.

Если в строке есть дата, она должна включать месяц и день или год. Если указано время, значение должно содержать час и минуты или обозначение AM либо PM.

Чтобы переопределить эти значения по умолчанию, можно задать константу <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault>. Если вы используете эту константу, для всех отсутствующих параметров года, месяца или дня устанавливается значение `1`. Это демонстрирует [последний пример](#styles-example), в котором применяется <xref:System.DateTime.Parse%2A>.

Помимо компонента даты и времени строковое представление даты и времени может содержать смещение, которое указывает, насколько время отличается от универсального синхронизированного времени (UTC). Например, строка "14/02/2007 5:32:00 -7: 00" определяет время, которое на семь часов меньше, чем UTC. Если в строковом представлении времени не задано смещение, то синтаксический анализ возвращает объект <xref:System.DateTime>, свойство <xref:System.DateTime.Kind%2A> которого имеет значение <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>. Если смещение задано, то синтаксический анализ возвращает объект <xref:System.DateTime>, свойство <xref:System.DateTime.Kind%2A> которого имеет значение <xref:System.DateTimeKind.Local?displayProperty=nameWithType> и значение которого установлено с учетом местного часового пояса компьютера. Это поведение можно изменить, указав для метода анализа значение <xref:System.Globalization.DateTimeStyles>.
  
Поставщик формата также используется для интерпретации неоднозначных числовых дат. Например, в строке "02/03/04" неясно, какие компоненты соответствуют месяцу, дню и году. Такие компоненты интерпретируются согласно их порядку расположения в схожих форматах даты в поставщике формата.

## <a name="parse"></a>Анализ

Ниже приведен пример использования метода <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> для преобразования `string` в <xref:System.DateTime>. В этом примере используются язык и региональные параметры, связанные с текущим потоком. Если класс <xref:System.Globalization.CultureInfo>, связанный с текущим значением языка и региональных параметров, не может выполнить синтаксический анализ исходной строки, создается исключение <xref:System.FormatException>.

> [!TIP]
> Все примеры C# в этой статье выполняются в браузере. Нажмите кнопку **Выполнить**, чтобы просмотреть выходные данные. Вы можете поэкспериментировать, изменяя их значения.

> [!NOTE]
> Эти примеры для [C#](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/conversions) и [Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/how-to/conversions) см. в репозитории с документацией GitHub. Вы также можете скачать проект в виде ZIP-файла для [C#](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/conversions.zip) или [Visual Basic](https://github.com/dotnet/samples/raw/master/snippets/visualbasic/how-to/conversions.zip).

[!code-csharp-interactive[Parsing.DateAndTime#1](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#1)]
[!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#1)]

Кроме того, вы можете явно определить язык и региональные параметры, соглашения о форматировании для которых используются при анализе строки. Укажите один из стандартных объектов <xref:System.Globalization.DateTimeFormatInfo>, возвращенных свойством <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. В приведенном ниже примере поставщик формата используется для анализа строки на немецком языке в <xref:System.DateTime>. Для представления языка и региональных параметров <xref:System.Globalization.CultureInfo> создается `de-DE`. Этот объект `CultureInfo` обеспечивает успешный анализ определенной строки. Это устраняет необходимость задания каких-либо параметров в <xref:System.Threading.Thread.CurrentCulture> потока <xref:System.Threading.Thread.CurrentThread>.  
  
[!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#2)]
[!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#2)]

Для указания поставщиков пользовательских форматов можно использовать перегрузки метода <xref:System.DateTime.Parse%2A>. Но такой метод не поддерживает анализ нестандартных форматов. Вместо этого используйте метод <xref:System.DateTime.ParseExact%2A> для анализа даты и времени, выраженных в нестандартном формате.  

<a name="styles-example"></a>В приведенном ниже примере перечисление <xref:System.Globalization.DateTimeStyles> указывает, что текущие значения даты и времени не нужно добавлять в <xref:System.DateTime> для неуказанных полей.  

[!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#3)]
[!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#3)]

## <a name="parseexact"></a>ParseExact

Метод <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> позволяет преобразовать строку в объект <xref:System.DateTime>, если она соответствует одному из указанных шаблонов строк. Если в этот метод передается строка, не соответствующая ни одному из указанных шаблонов, создается исключение <xref:System.FormatException>. Можно задать один из стандартных описателей формата даты и времени или сочетание пользовательских описателей формата. При использовании пользовательских описателей формата можно сконструировать пользовательскую строку распознавания. Сведения об описателях см. в разделах [Строки стандартных форматов даты и времени](standard-date-and-time-format-strings.md) и [Строки настраиваемых форматов даты и времени](custom-date-and-time-format-strings.md).  

В приведенном ниже примере в метод <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> передается переназначенный для анализа строковый объект. Затем следует описатель формата, который сопровождается объектом <xref:System.Globalization.CultureInfo>. С помощью этого метода <xref:System.DateTime.ParseExact%2A> можно анализировать только строки, соответствующие шаблону полной даты для языка и региональных параметров `en-US`.  

[!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#4)]
[!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#4)]

При каждой перегрузке методов <xref:System.DateTime.Parse%2A> и <xref:System.DateTime.ParseExact%2A> также используется параметр <xref:System.IFormatProvider>, который предоставляет сведения о языке и региональных параметрах для форматирования строки. Этот объект <xref:System.IFormatProvider> является объектом <xref:System.Globalization.CultureInfo>, который представляет стандартные язык и региональные параметры, или объектом <xref:System.Globalization.DateTimeFormatInfo>, возвращаемым в свойстве <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>.  Кроме того, в методе <xref:System.DateTime.ParseExact%2A> используется дополнительная строка или аргумент массива строк для определения одного или нескольких настраиваемых форматов даты и времени.  

## <a name="see-also"></a>См. также раздел

- [Анализ строк в .NET Framework](parsing-strings.md)
- [Типы форматирования](formatting-types.md)
- [Преобразование типов в .NET](type-conversion.md)
- [Стандартные форматы даты и времени](standard-date-and-time-format-strings.md)
- [Строки настраиваемых форматов даты и времени](custom-date-and-time-format-strings.md)
