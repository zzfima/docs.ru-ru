---
title: "Работа с календарями"
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
- globalization [.NET Framework], calendars
- calendars, global applications
- global applications, calendars
- world-ready applications, calendars
- international applications [.NET Framework], calendars
- culture, calendars
ms.assetid: 0c1534e5-979b-4c8a-a588-1c24301aefb3
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c3a54d5222edca0b42f30c33584f0f62aa96f9e2
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="working-with-calendars"></a>Работа с календарями

Несмотря на то что значение даты и времени обозначает момент во времени, его строковое представление зависит от конкретного языка и региональных параметров. На него влияют как принятые стандарты обозначения даты и времени, так и используемый календарь. В этом разделе описывается поддержка календарей в .NET и обсуждается использование классов календарей при работе со значениями даты.

## <a name="calendars-in-net"></a>Календари в .NET

Все календари в .NET, являются производными от <xref:System.Globalization.Calendar?displayProperty=nameWithType> класс, предоставляющий базовую реализацию календаря. Одним из классов, наследующих от класса <xref:System.Globalization.Calendar>, является класс <xref:System.Globalization.EastAsianLunisolarCalendar> — базовый класс для всех лунно-солнечных календарей. .NET включает следующие реализации календарей.

* <xref:System.Globalization.ChineseLunisolarCalendar>. Представляет китайский лунно-солнечный календарь.

* <xref:System.Globalization.GregorianCalendar>. Представляет григорианский календарь. Этот календарь, в свою очередь, разделяется на подтипы (такие как арабский и ближневосточный французский), определяемые перечислением <xref:System.Globalization.GregorianCalendarTypes?displayProperty=nameWithType>. Свойство <xref:System.Globalization.GregorianCalendar.CalendarType%2A?displayProperty=nameWithType> определяет подтип григорианского календаря.

* <xref:System.Globalization.HebrewCalendar>. Представляет еврейский календарь.

* <xref:System.Globalization.HijriCalendar>. Представляет календарь Хиджра.

* <xref:System.Globalization.JapaneseCalendar>. Представляет японский календарь.

* <xref:System.Globalization.JapaneseLunisolarCalendar>. Представляет японский лунно-солнечный календарь.

* <xref:System.Globalization.JulianCalendar>Представляет юлианский календарь.

* <xref:System.Globalization.KoreanCalendar>. Представляет корейский календарь.

* <xref:System.Globalization.KoreanLunisolarCalendar>. Представляет корейский лунно-солнечный календарь.

* <xref:System.Globalization.PersianCalendar>. Представляет персидский календарь.

* <xref:System.Globalization.TaiwanCalendar>. Представляет тайваньский календарь.

* <xref:System.Globalization.TaiwanLunisolarCalendar>. Представляет тайваньский лунно-солнечный календарь.

* <xref:System.Globalization.ThaiBuddhistCalendar>. Представляет тай-буддистский календарь.

* <xref:System.Globalization.UmAlQuraCalendar>. Представляет саудовский календарь.

Календарь можно использовать одним из двух способов:

* Как календарь, используемый для конкретных языка и региональных параметров. Каждый объект <xref:System.Globalization.CultureInfo> имеет текущий календарь, то есть календарь, который объект использует в настоящий момент. Строковое представление значений даты и времени автоматически отражает используемые язык и региональные параметры и текущий календарь. Обычно текущий календарь является календарем по умолчанию для языка и региональных параметров. Объекты <xref:System.Globalization.CultureInfo> также имеют дополнительные календари, которые могут использоваться для языка и региональных параметров.

* Как самостоятельный календарь, не зависящий от конкретных языка и региональных параметров. В таком случае методы <xref:System.Globalization.Calendar> используются для выражения дат и значений календаря.

Обратите внимание, что шесть классов календаря (<xref:System.Globalization.ChineseLunisolarCalendar>, <xref:System.Globalization.JapaneseLunisolarCalendar>, <xref:System.Globalization.JulianCalendar>, <xref:System.Globalization.KoreanLunisolarCalendar>, <xref:System.Globalization.PersianCalendar> и <xref:System.Globalization.TaiwanLunisolarCalendar>) можно использовать только как самостоятельные календари. Никакие языки и региональные параметры не используют их как календари по умолчанию или как дополнительные календари.

## <a name="calendars-and-cultures"></a>Календари и языки и региональные параметры

Для любого языка и региональных параметров есть календарь по умолчанию, определенный свойством <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>. Свойство <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> возвращает массив объектов <xref:System.Globalization.Calendar>, содержащий все календари, поддерживаемые конкретным языком и региональными параметрами, включая календарь по умолчанию для этого языка и региональных параметров.

Следующий пример иллюстрирует свойства <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType> и <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>. В нем создаются объекты `CultureInfo` для языков и региональных параметров "Тайский (Таиланд)" и "Японский (Япония)", а также выводятся их календари по умолчанию и дополнительные календари. Обратите внимание, что в обоих случаях календарь по умолчанию для языка и региональных параметров также включается в коллекцию <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>.

[!code-csharp[Conceptual.Calendars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/calendarinfo1.cs#1)]
[!code-vb[Conceptual.Calendars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/calendarinfo1.vb#1)]

Календарь, используемый в настоящий момент каким-либо конкретным объектом <xref:System.Globalization.CultureInfo>, определяется свойством <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> языка и региональных параметров. Объект <xref:System.Globalization.DateTimeFormatInfo> языка и региональных параметров возвращается свойством <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. При создании языка и региональных параметров значение по умолчанию совпадает со значением свойства <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>. Однако текущий календарь языка и региональных параметров можно изменить на любой календарь из массива, возвращаемого свойством <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>. Если попытаться изменить текущий календарь на календарь, не входящий в значение свойства <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>, будет создано исключение <xref:System.ArgumentException>.

В следующем примере изменяется календарь, используемый для языка и региональных параметров "Арабский (Саудовская Аравия)". Сперва создается значение <xref:System.DateTime> и отображается с использованием текущего языка и региональных параметров (в данном случае "Английский (США)") и текущего календаря для языка и региональных параметров (в данном случае григорианского календаря). Затем текущий язык и региональные параметры изменяются на "Арабский (Саудовская Аравия)" и дата отображается с использованием календаря по умолчанию — саудовского календаря. Затем вызывается метод `CalendarExists`, чтобы определить, поддерживается ли календарь Хиджра языком и региональными параметрами "Арабский (Саудовская Аравия)". Поскольку этот календарь поддерживается, текущий календарь изменяется на календарь Хиджра и дата отображается снова. Обратите внимание, что в обоих случаях дата отображается с использованием текущего календаря текущего языка и региональных параметров.

[!code-csharp[Conceptual.Calendars#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/changecalendar2.cs#2)]
[!code-vb[Conceptual.Calendars#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/changecalendar2.vb#2)]

## <a name="dates-and-calendars"></a>Даты и календари

За исключением конструкторов, содержащих параметры типа <xref:System.Globalization.Calendar> и допускающих отображение элементов даты (месяц, день, год) по указанному календарю, значения <xref:System.DateTime> и <xref:System.DateTimeOffset> всегда приводятся по григорианскому календарю. Это означает, например, что свойство <xref:System.DateTime.Year%2A?displayProperty=nameWithType> возвращает год по григорианскому календарю, а свойство <xref:System.DateTime.Day%2A?displayProperty=nameWithType> возвращает день месяца по григорианскому календарю.

> [!IMPORTANT]
> Важно помнить, что есть разница между значением даты и его строковым представлением. Первое основывается на григорианском календаре, а последнее — на текущем календаре конкретного языка и региональных параметров.

Следующий пример иллюстрирует разницу между свойствами <xref:System.DateTime> и их соответствующими методами <xref:System.Globalization.Calendar>. В этом примере текущий язык и региональные параметры — "Арабский (Египет)", а текущий календарь — саудовский. Задано значение <xref:System.DateTime>, обозначающее пятнадцатый день седьмого месяца 2011 года. Очевидно, что это значение интерпретируется как дата григорианского календаря, поскольку именно эти значения возвращаются методом <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> при использовании стандартов инвариантного языка и региональных параметров. Строковое представление даты форматируется по стандартам текущего языка и региональных параметров и выглядит как 14/08/32, указывая соответствующую дату по саудовскому календарю. Затем члены `DateTime` и `Calendar` используются для возврата дня, месяца и года значения <xref:System.DateTime>. В любом случае, значения, возвращаемые членами <xref:System.DateTime>, отражают значения по григорианскому календарю, а значения, возвращаемые членами <xref:System.Globalization.UmAlQuraCalendar> отражают значения по саудовскому календарю.

[!code-csharp[Conceptual.Calendars#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/datesandcalendars2.cs#3)]
[!code-vb[Conceptual.Calendars#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/datesandcalendars2.vb#3)]

### <a name="instantiating-dates-based-on-a-calendar"></a>Создание дат на основе календаря

Поскольку значения <xref:System.DateTime> и <xref:System.DateTimeOffset> основываются на григорианском календаре, необходимо вызвать перегруженный конструктор, включающий параметр типа <xref:System.Globalization.Calendar>, для создания значения даты, если требуется использовать значение дня, месяца или года по другому календарю. Можно также вызвать одну из перегрузок метода <xref:System.Globalization.Calendar.ToDateTime%2A?displayProperty=nameWithType> конкретного календаря для создания объекта <xref:System.DateTime> на основе значений конкретного календаря.

В следующем примере первое значение <xref:System.DateTime> создается путем передачи объекта <xref:System.Globalization.HebrewCalendar> конструктору <xref:System.DateTime>, а второе значение <xref:System.DateTime> создается путем вызова метода <xref:System.Globalization.HebrewCalendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>. Поскольку эти два значения создаются с одинаковыми значениями еврейского календаря, вызов метода <xref:System.DateTime.Equals%2A?displayProperty=nameWithType> показывает, что два значения <xref:System.DateTime> совпадают.

[!code-csharp[Conceptual.Calendars#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatehcdate1.cs#4)]
[!code-vb[Conceptual.Calendars#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatehcdate1.vb#4)]

### <a name="representing-dates-in-the-current-calendar"></a>Представление дат текущего календаря

Методы форматирования даты и времени при преобразовании дат в строки всегда используют текущий календарь. Это значит, что строковое представление года, месяца и дня месяца отражают текущий календарь, а не обязательно григорианский календарь.

В следующем примере показано, как текущий календарь влияет на строковое представление даты. Текущий язык и региональные параметры изменяются на "Китайский (традиционное письмо, Тайвань)", затем создается значение даты. Затем отображается текущий календарь и дата, текущий календарь изменяется на <xref:System.Globalization.TaiwanCalendar>, текущий календарь и дата отображаются снова. При первом отображении даты она представляется как дата григорианского календаря. При отображении даты во второй раз она представляется как дата тайваньского календаря.

[!code-csharp[Conceptual.Calendars#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/currentcalendar1.cs#5)]
[!code-vb[Conceptual.Calendars#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/currentcalendar1.vb#5)]

### <a name="representing-dates-in-a-non-current-calendar"></a>Представление дат не текущего календаря

Чтобы представить дату с помощью календаря, который не является текущим для языка и региональных параметров, необходимо вызвать методы нужного объекта <xref:System.Globalization.Calendar>. Например, методы <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> и <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> преобразуют значения года, месяца и дня в значения, соответствующие определенному календарю.

> [!WARNING]
> Поскольку некоторые календари не являются дополнительными календарями ни для какого языка и региональных параметров, указание дат по этим календарям всегда требует вызова методов календаря. Это верно для всех календарей, унаследованных от классов <xref:System.Globalization.EastAsianLunisolarCalendar>, <xref:System.Globalization.JulianCalendar> и <xref:System.Globalization.PersianCalendar>.

В следующем примере используется объект <xref:System.Globalization.JulianCalendar> для создания даты 9 января 1905 года по юлианскому календарю. При отображении этой даты по календарю по умолчанию (григорианскому), она представляется как 22 января 1905 года. Вызов отдельных методов <xref:System.Globalization.JulianCalendar> позволяет отобразить дату по юлианскому календарю.

[!code-csharp[Conceptual.Calendars#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/noncurrentcalendar1.cs#6)]
[!code-vb[Conceptual.Calendars#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/noncurrentcalendar1.vb#6)]

### <a name="calendars-and-date-ranges"></a>Календари и диапазоны дат

Самая ранняя дата, поддерживаемая календарем, отображается свойством <xref:System.Globalization.Calendar.MinSupportedDateTime%2A?displayProperty=nameWithType> этого календаря. Для класса <xref:System.Globalization.GregorianCalendar> эта дата — 1 января 0001 года нашей эры. Большинство других календарей в .NET поддерживают более позднюю дату. При попытке работы с датой и временем, меньшими самой ранней поддерживаемой календарем даты, возникнет исключение <xref:System.ArgumentOutOfRangeException>.

Однако существует одно важное исключение из этого правила. По умолчанию (неинициализированное) значение объекта <xref:System.DateTime> и объекта <xref:System.DateTimeOffset> равно значению <xref:System.Globalization.GregorianCalendar.MinSupportedDateTime%2A?displayProperty=nameWithType>. Если вы попытаетесь форматирования этой даты в календаре, который не поддерживает 1 января 0001 года нашей эры и не имеют описатель формата, метод форматирования используется описатель формата «s» (шаблон времени и даты сортируемого) вместо описатель формата «G» (шаблон общие даты и времени). В результате операция форматирования не вызовет исключения <xref:System.ArgumentOutOfRangeException>. Вместо этого будет возвращена неподдерживаемая дата. Это продемонстрировано в следующем примере, отображающем значение <xref:System.DateTime.MinValue?displayProperty=nameWithType> во время установки текущих языка и региональных параметров в японские (Япония) с японским календарем и в арабские (Египет) с календарем Um Al Qura. Также текущие язык и региональные параметры устанавливаются в английские (США) и вызывается метод <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType> с каждым из этих объектов <xref:System.Globalization.CultureInfo>. В каждом случае дата отображается с помощью сортируемого шаблона даты и времени.

[!code-csharp[Conceptual.Calendars#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/minsupporteddatetime1.cs#11)]
[!code-vb[Conceptual.Calendars#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/minsupporteddatetime1.vb#11)]

## <a name="working-with-eras"></a>Работа с эрами

В календарях даты обычно разделены на эры. Тем не менее <xref:System.Globalization.Calendar> классы в .NET не поддерживают каждый эры, определяемый календаре, а большинство <xref:System.Globalization.Calendar> классы поддерживают только одну эру. Только классы <xref:System.Globalization.JapaneseCalendar> и <xref:System.Globalization.JapaneseLunisolarCalendar> поддерживают несколько эр.

### <a name="eras-and-era-names"></a>Эры и названия эр

В .NET, целые числа, обозначающие эры, поддерживаемые реализацией конкретного календаря, хранятся в обратном порядке в <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType> массива. Текущая эра хранится с индексом 0, а для классов <xref:System.Globalization.Calendar>, поддерживающих несколько эр, каждый последующий индекс обозначает предыдущую эру. Статическое свойство <xref:System.Globalization.Calendar.CurrentEra?displayProperty=nameWithType> определяет индекс текущей эры в массиве <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType>; это константа, значение которой всегда ноль. Отдельные классы <xref:System.Globalization.Calendar> также включают статические поля, возвращающие значение текущей эры. Они перечислены в следующей таблице.

| Класс календаря                                        | Поле текущей эры                                                 |
| ----------------------------------------------------- | ----------------------------------------------------------------- |
| <xref:System.Globalization.ChineseLunisolarCalendar>  | <xref:System.Globalization.ChineseLunisolarCalendar.ChineseEra>   |
| <xref:System.Globalization.GregorianCalendar>         | <xref:System.Globalization.GregorianCalendar.ADEra>               |
| <xref:System.Globalization.HebrewCalendar>            | <xref:System.Globalization.HebrewCalendar.HebrewEra>              |
| <xref:System.Globalization.HijriCalendar>             | <xref:System.Globalization.HijriCalendar.HijriEra>                |
| <xref:System.Globalization.JapaneseLunisolarCalendar> | <xref:System.Globalization.JapaneseLunisolarCalendar.JapaneseEra> |
| <xref:System.Globalization.JulianCalendar>            | <xref:System.Globalization.JulianCalendar.JulianEra>              |
| <xref:System.Globalization.KoreanCalendar>            | <xref:System.Globalization.KoreanCalendar.KoreanEra>              |
| <xref:System.Globalization.KoreanLunisolarCalendar>   | <xref:System.Globalization.KoreanLunisolarCalendar.GregorianEra>  |
| <xref:System.Globalization.PersianCalendar>           | <xref:System.Globalization.PersianCalendar.PersianEra>            |
| <xref:System.Globalization.ThaiBuddhistCalendar>      | <xref:System.Globalization.ThaiBuddhistCalendar.ThaiBuddhistEra>  |
| <xref:System.Globalization.UmAlQuraCalendar>          | <xref:System.Globalization.UmAlQuraCalendar.UmAlQuraEra>          |

Имя, соответствующее номеру конкретной эры, которое можно получить, передав номер эры методу <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> или <xref:System.Globalization.DateTimeFormatInfo.GetAbbreviatedEraName%2A?displayProperty=nameWithType>. В следующем примере эти методы вызываются для получения информации о поддержке эр в классе <xref:System.Globalization.GregorianCalendar>.

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs#7)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb#7)]

Кроме того, строка пользовательского формата даты и времени "g" включает имя эры календаря в строковое представлении даты и времени. Дополнительные сведения см. в разделе [строки форматов пользовательские значения даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).

### <a name="instantiating-a-date-with-an-era"></a>Создание даты с указанием эры

Для двух классов <xref:System.Globalization.Calendar>, поддерживающих несколько эр, дата, состоящая из указания года, месяца и дня месяца может быть неоднозначной. Например, во всех четырех эрах календаря <xref:System.Globalization.JapaneseCalendar> годы нумеруются от 1 до 15. Обычно если эра не указана, методы даты и времени и календаря предполагают, что значения относятся к текущей эре. Чтобы явно указать эру при создании даты для класса <xref:System.Globalization.Calendar>, поддерживающего несколько эр, можно вызвать метод <xref:System.Globalization.Calendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>. Этот метод позволяет явным образом указать эру вместе с календарным годом, месяцем, днем, часом, минутой, секундой и миллисекундой.

В следующем примере используется метод <xref:System.Globalization.Calendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType> для создания даты вида "первый день первого месяца второго года" в каждой эре, поддерживаемой классом <xref:System.Globalization.JapaneseCalendar>. Затем дата отображается в соответствии с японским и григорианским календарями. Также вызывается конструктор <xref:System.DateTime>, чтобы продемонстрировать, что методы, создающие значения дат без указания эры, создают даты в текущей эре.

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs#7)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb#7)]

### <a name="representing-dates-in-calendars-with-eras"></a>Представление дат в календарях, с указанием эры

Если объект <xref:System.Globalization.Calendar> поддерживает эры и является текущим календарем объекта <xref:System.Globalization.CultureInfo>, эра включается в строковое представление даты и времени для полной даты, длинной даты и шаблонов короткой даты. В следующем примере показаны эти шаблоны даты при текущем языке и региональных параметрах "Японский (Япония)" и японском текущем календаре.

[!code-csharp[Conceptual.Calendars#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings1.cs#8)]
[!code-vb[Conceptual.Calendars#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings1.vb#8)]

> [!WARNING]
> <xref:System.Globalization.JapaneseCalendar> Класс — единственный класс календаря в .NET, который поддерживает даты в нескольких эрах и при этом может быть текущим календарем объекта <xref:System.Globalization.CultureInfo> объект — в частности, объекта <xref:System.Globalization.CultureInfo> объект, представляющий региональные параметры, японский (Япония).

Для всех календарей описатель пользовательского формата "g" добавляет эру в результирующую строку. В следующем примере используется строка пользовательского формата "мм-дд-гггг g", где в дату включается эра, при том что текущим является григорианский календарь.

[!code-csharp[Conceptual.Calendars#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings2.cs#9)]
[!code-vb[Conceptual.Calendars#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings2.vb#9)]

В случае когда строковое представление даты связано с календарем, который не является текущим, класс <xref:System.Globalization.Calendar> включает метод <xref:System.Globalization.Calendar.GetEra%2A?displayProperty=nameWithType>, который можно использовать с методами <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> и <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> для однозначного указания даты и эры. В следующем примере для демонстрации используется класс <xref:System.Globalization.JapaneseLunisolarCalendar>. Однако следует учесть, что если требуется включить в результирующую строку понятное имя или сокращенное имя вместо целого числа для эры, необходимо создать объект <xref:System.Globalization.DateTimeFormatInfo> и сделать календарь <xref:System.Globalization.JapaneseCalendar> его текущим календарем. (Календарь <xref:System.Globalization.JapaneseLunisolarCalendar> не может быть текущим календарем для какого-либо языка и региональных параметров, но в данном случае эры этих двух календарей совпадают.)

[!code-csharp[Conceptual.Calendars#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings3.cs#10)]
[!code-vb[Conceptual.Calendars#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings3.vb#10)]

## <a name="see-also"></a>См. также

[Как: Отображение даты в календарях, отличных от григорианского](../../../docs/standard/base-types/how-to-display-dates-in-non-gregorian-calendars.md)
[образец: программа диапазона неделя календаря](http://code.msdn.microsoft.com/NET-Framework-4-Calendar-3360a84a)
