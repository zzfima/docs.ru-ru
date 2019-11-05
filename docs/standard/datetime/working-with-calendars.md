---
title: Работа с календарями
ms.date: 04/01/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- globalization [.NET], calendars
- calendars, global applications
- global applications, calendars
- world-ready applications, calendars
- international applications [.NET], calendars
- culture, calendars
ms.assetid: 0c1534e5-979b-4c8a-a588-1c24301aefb3
ms.openlocfilehash: 7795fa8d348a3053e6d999d007a558b418cafbd3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132521"
---
# <a name="working-with-calendars"></a>Работа с календарями

Несмотря на то что значение даты и времени обозначает момент во времени, его строковое представление зависит от конкретного языка и региональных параметров. На него влияют как принятые стандарты обозначения даты и времени, так и используемый календарь. В этом разделе рассматривается поддержка календарей в .NET и обсуждается использование классов календаря при работе со значениями дат.

## <a name="calendars-in-net"></a>Календари в .NET

Все календари в .NET являются производными от класса <xref:System.Globalization.Calendar?displayProperty=nameWithType>, который обеспечивает реализацию базового календаря. Одним из классов, наследующих от класса <xref:System.Globalization.Calendar>, является класс <xref:System.Globalization.EastAsianLunisolarCalendar> — базовый класс для всех лунно-солнечных календарей. .NET включает следующие реализации календаря:

- <xref:System.Globalization.ChineseLunisolarCalendar>. Представляет китайский лунно-солнечный календарь.

- <xref:System.Globalization.GregorianCalendar>. Представляет григорианский календарь. Этот календарь, в свою очередь, разделяется на подтипы (такие как арабский и ближневосточный французский), определяемые перечислением <xref:System.Globalization.GregorianCalendarTypes?displayProperty=nameWithType>. Свойство <xref:System.Globalization.GregorianCalendar.CalendarType%2A?displayProperty=nameWithType> определяет подтип григорианского календаря.

- <xref:System.Globalization.HebrewCalendar>. Представляет еврейский календарь.

- <xref:System.Globalization.HijriCalendar>. Представляет календарь Хиджра.

- <xref:System.Globalization.JapaneseCalendar>. Представляет японский календарь.

- <xref:System.Globalization.JapaneseLunisolarCalendar>. Представляет японский лунно-солнечный календарь.

- <xref:System.Globalization.JulianCalendar>Представляет юлианский календарь.

- <xref:System.Globalization.KoreanCalendar>. Представляет корейский календарь.

- <xref:System.Globalization.KoreanLunisolarCalendar>. Представляет корейский лунно-солнечный календарь.

- <xref:System.Globalization.PersianCalendar>. Представляет персидский календарь.

- <xref:System.Globalization.TaiwanCalendar>. Представляет тайваньский календарь.

- <xref:System.Globalization.TaiwanLunisolarCalendar>. Представляет тайваньский лунно-солнечный календарь.

- <xref:System.Globalization.ThaiBuddhistCalendar>. Представляет тай-буддистский календарь.

- <xref:System.Globalization.UmAlQuraCalendar>. Представляет саудовский календарь.

Календарь можно использовать одним из двух способов:

- Как календарь, используемый для конкретных языка и региональных параметров. Каждый объект <xref:System.Globalization.CultureInfo> имеет текущий календарь, то есть календарь, который объект использует в настоящий момент. Строковое представление значений даты и времени автоматически отражает используемые язык и региональные параметры и текущий календарь. Обычно текущий календарь является календарем по умолчанию для языка и региональных параметров. <xref:System.Globalization.CultureInfo> объекты также имеют дополнительные календари, которые включают дополнительные календари, которые может использовать язык и региональные параметры.

- Как самостоятельный календарь, не зависящий от конкретных языка и региональных параметров. В таком случае методы <xref:System.Globalization.Calendar> используются для выражения дат и значений календаря.

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

### <a name="instantiating-dates-based-on-a-calendar"></a>Создание экземпляров дат на основе календаря

Поскольку значения <xref:System.DateTime> и <xref:System.DateTimeOffset> основываются на григорианском календаре, необходимо вызвать перегруженный конструктор, включающий параметр типа <xref:System.Globalization.Calendar>, для создания значения даты, если требуется использовать значение дня, месяца или года по другому календарю. Можно также вызвать одну из перегрузок метода <xref:System.Globalization.Calendar.ToDateTime%2A?displayProperty=nameWithType> конкретного календаря для создания объекта <xref:System.DateTime> на основе значений конкретного календаря.

В следующем примере первое значение <xref:System.DateTime> создается путем передачи объекта <xref:System.Globalization.HebrewCalendar> конструктору <xref:System.DateTime>, а второе значение <xref:System.DateTime> создается путем вызова метода <xref:System.Globalization.HebrewCalendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>. Поскольку эти два значения создаются с одинаковыми значениями еврейского календаря, вызов метода <xref:System.DateTime.Equals%2A?displayProperty=nameWithType> показывает, что два значения <xref:System.DateTime> совпадают.

[!code-csharp[Conceptual.Calendars#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatehcdate1.cs#4)]
[!code-vb[Conceptual.Calendars#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatehcdate1.vb#4)]

### <a name="representing-dates-in-the-current-calendar"></a>Представление дат в текущем календаре

Методы форматирования даты и времени при преобразовании дат в строки всегда используют текущий календарь. Это значит, что строковое представление года, месяца и дня месяца отражают текущий календарь, а не обязательно григорианский календарь.

В следующем примере показано, как текущий календарь влияет на строковое представление даты. Текущий язык и региональные параметры изменяются на "Китайский (традиционное письмо, Тайвань)", затем создается значение даты. Затем отображается текущий календарь и дата, текущий календарь изменяется на <xref:System.Globalization.TaiwanCalendar>, текущий календарь и дата отображаются снова. При первом отображении даты она представляется как дата григорианского календаря. При отображении даты во второй раз она представляется как дата тайваньского календаря.

[!code-csharp[Conceptual.Calendars#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/currentcalendar1.cs#5)]
[!code-vb[Conceptual.Calendars#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/currentcalendar1.vb#5)]

### <a name="representing-dates-in-a-non-current-calendar"></a>Представление дат в нетекущем календаре

Чтобы представить дату с помощью календаря, который не является текущим для языка и региональных параметров, необходимо вызвать методы нужного объекта <xref:System.Globalization.Calendar>. Например, методы <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> и <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> преобразуют значения года, месяца и дня в значения, соответствующие определенному календарю.

> [!WARNING]
> Поскольку некоторые календари не являются дополнительными календарями ни для какого языка и региональных параметров, указание дат по этим календарям всегда требует вызова методов календаря. Это верно для всех календарей, унаследованных от классов <xref:System.Globalization.EastAsianLunisolarCalendar>, <xref:System.Globalization.JulianCalendar> и <xref:System.Globalization.PersianCalendar>.

В следующем примере используется объект <xref:System.Globalization.JulianCalendar> для создания даты 9 января 1905 года по юлианскому календарю. При отображении этой даты по календарю по умолчанию (григорианскому), она представляется как 22 января 1905 года. Вызов отдельных методов <xref:System.Globalization.JulianCalendar> позволяет отобразить дату по юлианскому календарю.

[!code-csharp[Conceptual.Calendars#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/noncurrentcalendar1.cs#6)]
[!code-vb[Conceptual.Calendars#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/noncurrentcalendar1.vb#6)]

### <a name="calendars-and-date-ranges"></a>Календари и диапазоны дат

Самая ранняя дата, поддерживаемая календарем, отображается свойством <xref:System.Globalization.Calendar.MinSupportedDateTime%2A?displayProperty=nameWithType> этого календаря. Для класса <xref:System.Globalization.GregorianCalendar> эта дата — 1 января 0001 года нашей эры. Большинство других календарей в .NET поддерживают более позднюю дату. При попытке работы с датой и временем, меньшими самой ранней поддерживаемой календарем даты, возникнет исключение <xref:System.ArgumentOutOfRangeException>.

Однако существует одно важное исключение из этого правила. По умолчанию (неинициализированное) значение объекта <xref:System.DateTime> и объекта <xref:System.DateTimeOffset> равно значению <xref:System.Globalization.GregorianCalendar.MinSupportedDateTime%2A?displayProperty=nameWithType>. Если вы попытаетесь отформатировать эту дату в календаре, не поддерживающем 1 января 0001 года нашей эры и не предоставляется описатель формата, в методе форматирования используется описатель формата "s" (шаблон даты и времени с сортировкой) вместо описателя формата "G" (общий шаблон даты и времени). В результате операция форматирования не вызовет исключения <xref:System.ArgumentOutOfRangeException>. Вместо этого будет возвращена неподдерживаемая дата. Это продемонстрировано в следующем примере, отображающем значение <xref:System.DateTime.MinValue?displayProperty=nameWithType> во время установки текущих языка и региональных параметров в японские (Япония) с японским календарем и в арабские (Египет) с календарем Um Al Qura. Также текущие язык и региональные параметры устанавливаются в английские (США) и вызывается метод <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType> с каждым из этих объектов <xref:System.Globalization.CultureInfo>. В каждом случае дата отображается с помощью сортируемого шаблона даты и времени.

[!code-csharp[Conceptual.Calendars#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/minsupporteddatetime1.cs#11)]
[!code-vb[Conceptual.Calendars#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/minsupporteddatetime1.vb#11)]

## <a name="working-with-eras"></a>Работа с Эр

В календарях даты обычно разделены на эры. Однако <xref:System.Globalization.Calendar> классы в .NET не поддерживают каждую эру, определенную календарем, и большинство классов <xref:System.Globalization.Calendar> поддерживают только одну эру. Только классы <xref:System.Globalization.JapaneseCalendar> и <xref:System.Globalization.JapaneseLunisolarCalendar> поддерживают несколько эр.

> [!IMPORTANT]
> Эпоха Реива, Новая эра в <xref:System.Globalization.JapaneseCalendar> и <xref:System.Globalization.JapaneseLunisolarCalendar>, начинается 1 мая 2019. Это изменение затрагивает все приложения, использующие эти календари. Дополнительные сведения см. в следующих статьях:
>
> - [Обработка новой эры в японском календаре в .NET](https://devblogs.microsoft.com/dotnet/handling-a-new-era-in-the-japanese-calendar-in-net/), которая документирует функции, добавленные в .NET для поддержки календарей с несколькими Эр, и обсуждаются рекомендации по обработке календарей с несколькими эрами.
> - [Подготовьте свое приложение к изменению японской эры](/windows/uwp/design/globalizing/japanese-era-change), которое содержит сведения о тестировании приложений в Windows, чтобы гарантировать их готовность к изменению эры.
> - [Сводка новых обновлений японской эры для .NET Framework](https://support.microsoft.com/help/4477957/new-japanese-era-updates-for-net-framework), в которой перечислены .NET Framework обновления для отдельных версий Windows, связанных с новой эре японского календаря, заметок о новых функциях .NET Framework для поддержки нескольких эпох, а также о том, как Ищите в тестируемых приложениях.

Эра в большинстве календарей обозначает очень длинный период времени. Например, в григорианском календаре текущая эра охватывает более двух тысячелетий. Для <xref:System.Globalization.JapaneseCalendar> и <xref:System.Globalization.JapaneseLunisolarCalendar>два календаря, которые поддерживают несколько эр, это не так. Эра соответствует периоду Reign императора. Поддержка нескольких Эр, особенно если верхний предел текущей эры неизвестен, создает особые трудности.

### <a name="eras-and-era-names"></a>Эры и названия Эр

В .NET целые числа, представляющие эры, поддерживаемые конкретной реализацией календаря, хранятся в обратных последовательностях в массиве <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType>. Текущая эра (эра с последним диапазоном времени) имеет нулевой индекс, а для <xref:System.Globalization.Calendar> классов, которые поддерживают несколько эр, каждый последовательный индекс отражает предыдущую эру. Статическое свойство <xref:System.Globalization.Calendar.CurrentEra?displayProperty=nameWithType> определяет индекс текущей эры в массиве <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType>; это константа, значение которой всегда ноль. Отдельные классы <xref:System.Globalization.Calendar> также включают статические поля, возвращающие значение текущей эры. Они перечислены в следующей таблице.

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

Имя, соответствующее номеру конкретной эры, которое можно получить, передав номер эры методу <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> или <xref:System.Globalization.DateTimeFormatInfo.GetAbbreviatedEraName%2A?displayProperty=nameWithType>. В следующем примере эти методы вызываются для получения информации о поддержке эр в классе <xref:System.Globalization.GregorianCalendar>. Она отображает дату григорианского календаря, которая соответствует 1 января второго года текущей эры, а также дату григорианского календаря, которая соответствует 1 января второго года каждой поддерживаемой эры в японском календаре.

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb)]

Кроме того, строка пользовательского формата даты и времени "g" включает имя эры календаря в строковое представлении даты и времени. Дополнительные сведения см. в разделе [строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).

### <a name="instantiating-a-date-with-an-era"></a>Создание экземпляра даты с помощью эры

Для двух <xref:System.Globalization.Calendar> классов, поддерживающих несколько эр, Дата, состоящая из определенного года, месяца и дня значения месяца, может быть неоднозначной. Например, все эры, поддерживаемые <xref:System.Globalization.JapaneseCalendar>, имеют годы, число которых равно 1. Обычно если эра не указана, методы даты и времени и календаря предполагают, что значения относятся к текущей эре. Это справедливо для конструкторов <xref:System.DateTime.%23ctor%2A> и <xref:System.DateTimeOffset.%23ctor%2A>, которые включают параметры типа <xref:System.Globalization.Calendar>, а также методы [жапанесекалендар. ToDateTime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) и [жапанеселунисоларкалендар. ToDateTime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) . В следующем примере создается экземпляр даты, представляющей 1 января второго года неуказанной эры. Если вы выполняете пример, когда эра Реива является текущая эра, Дата интерпретируется как второй год эры Реива. Эра, 令和, предшествует году в строке, возвращенной методом <xref:System.DateTime.ToString(System.String,System.IFormatProvider)?displayProperty=nameWithType>, и соответствует 1 января 2020 в григорианском календаре. (Реива эпоха начинается в 2019 григорианского календаря.)

[!code-csharp[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/cs/program.cs)]
[!code-vb[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/vb/program.vb)]

Однако при изменении эры цель этого кода станет неоднозначным. Дата, предназначенная для представления второго года текущей эры, или она должна представлять второй год эры Хэйсэй? Избежать этой неоднозначности можно двумя способами:

- Создайте экземпляр значения даты и времени с помощью класса <xref:System.Globalization.GregorianCalendar> по умолчанию. Затем можно использовать Японский календарь или японский лунного календаря для представления строк дат, как показано в следующем примере.

  [!code-csharp[Insantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/cs/program.cs)]
  [!code-vb[Instantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/vb/program.vb)]

- Вызовите метод даты и времени, который явно указывает эру. Включены следующие методы:

  - Метод <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> класса <xref:System.Globalization.JapaneseCalendar> или <xref:System.Globalization.JapaneseLunisolarCalendar>.

  - Метод синтаксического анализа <xref:System.DateTime> или <xref:System.DateTimeOffset>, например <xref:System.DateTime.Parse%2A>, <xref:System.DateTime.TryParse%2A>, <xref:System.DateTime.ParseExact%2A>или <xref:System.DateTime.TryParseExact%2A>, который содержит строку для синтаксического анализа и, при необходимости, аргумент <xref:System.Globalization.DateTimeStyles>, если текущий язык и региональные параметры являются японскими ("ja-JP"), а этот календарь является <xref:System.Globalization.JapaneseCalendar>. Анализируемая строка должна включать эру.

  - Метод синтаксического анализа <xref:System.DateTime> или <xref:System.DateTimeOffset>, который включает параметр `provider` типа <xref:System.IFormatProvider>. `provider` должен быть <xref:System.Globalization.CultureInfo>ным объектом, представляющим язык и региональные параметры ("ja-JP"), текущий календарь которых <xref:System.Globalization.JapaneseCalendar>, или объект <xref:System.Globalization.DateTimeFormatInfo>, свойство <xref:System.Globalization.DateTimeFormatInfo.Calendar> которого <xref:System.Globalization.JapaneseCalendar>. Анализируемая строка должна включать эру.

  В следующем примере используются три из этих методов для создания экземпляра даты и времени в эпоху Меижи, которая началась 8 сентября 1868 и заканчивается 29 июля 1912.

  [!code-csharp[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/cs/program.cs)]
  [!code-vb[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/vb/program.vb)]

> [!TIP]
> При работе с календарями, поддерживающими несколько эр, *всегда* используйте дату григорианского задания для создания экземпляра даты или укажите эру при создании экземпляра даты и времени на основе этого календаря.

При указании эры для метода <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> вы предоставляете индекс эры в свойстве <xref:System.Globalization.Calendar.Eras> календаря. Однако для календарей, Эр которых может изменяться, эти индексы не являются постоянными значениями. Текущая эра имеет индекс 0, а самая старая эра — по индексу `Eras.Length - 1`. При добавлении новой эры в календарь индексы предыдущих Эр увеличиваются на единицу. Вы можете указать соответствующий индекс эры следующим образом:

- Для дат в текущей эре всегда используйте свойство <xref:System.Globalization.Calendar.CurrentEra> календаря.

- Для дат в указанной эре используйте метод <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType>, чтобы получить индекс, соответствующий указанному названию эры. Для этого необходимо, чтобы <xref:System.Globalization.JapaneseCalendar> был текущим календарем <xref:System.Globalization.CultureInfo> объекта, представляющего культуру ja-JP.  (Этот метод работает также для <xref:System.Globalization.JapaneseLunisolarCalendar>, так как он поддерживает те же эры, что и <xref:System.Globalization.JapaneseCalendar>.) Этот подход показан в предыдущем примере.

### <a name="calendars-eras-and-date-ranges-relaxed-range-checks"></a>Календари, эры и диапазоны дат: нестрогие проверки диапазона

Во многом так же, как в отдельных календарях поддерживаются диапазоны дат, эры в классах <xref:System.Globalization.JapaneseCalendar> и <xref:System.Globalization.JapaneseLunisolarCalendar> также имеют поддерживаемые диапазоны. Ранее в .NET использовались долгосрочные проверки диапазона эры, чтобы гарантировать, что дата, относящаяся к эре, была в диапазоне этой эры. То есть, если дата находится за пределами диапазона указанной эры, метод создает исключение <xref:System.ArgumentOutOfRangeException>. В настоящее время .NET по умолчанию использует ослабленную проверку по диапазонам. Обновления для всех версий .NET предоставили более строгие проверки диапазона эры; попытка создать экземпляр даты, относящейся к эре, которая находится за пределами диапазона указанной эры "переполняет" до следующей эры, и исключение не создается.

В следующем примере предпринимается попытка создать экземпляр даты в 65th году эры Шова, которая началась 25 декабря 1926 и закончилась 7 января 1989. Эта дата соответствует 9 января 1990, который находится вне диапазона эры Шова в <xref:System.Globalization.JapaneseCalendar>. Как видно из выходных данных примера, Дата, показанная в примере, — 9 января 1990 г. во втором году эры Хэйсэй.

  [!code-csharp[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/cs/program.cs)]
  [!code-vb[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/vb/program.vb)]

Если нежелательные проверки диапазона нежелательно, можно восстановить строгие проверки диапазона несколькими способами в зависимости от версии .NET, в которой выполняется приложение:

- **.NET Core:** В файл конфигурации *. netcore. Runtime. JSON* можно добавить следующий код:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceJapaneseEraYearRanges": true
    }
  }
  ```

- **.NET Framework 4,6 или более поздней версии:** Можно задать следующий параметр AppContext:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceJapaneseEraYearRanges=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 или более ранней версии:** Можно задать следующее значение реестра:

   |  |  |
   |--|--|
   |Раздел | HKEY_LOCAL_MACHINE\Software\Microsoft\.Нетфрамеворк\аппконтекст |
   |Название | Switch. System. Globalization. Енфорцежапанесирайеарранжес |
   |Type | REG_SZ |
   |значения | true |

Если включена поддержка оптимистических проверок диапазона, в предыдущем примере возникает исключение <xref:System.ArgumentOutOfRangeException> и отображаются следующие выходные данные:

```console
Unhandled Exception: System.ArgumentOutOfRangeException: Valid values are between 1 and 64, inclusive.
Parameter name: year
   at System.Globalization.GregorianCalendarHelper.GetYearOffset(Int32 year, Int32 era, Boolean throwOnError)
   at System.Globalization.GregorianCalendarHelper.ToDateTime(Int32 year, Int32 month, Int32 day, Int32 hour, Int32 minute, Int32 second, Int32 millisecond, Int32 era)
   at Example.Main()
```

### <a name="representing-dates-in-calendars-with-multiple-eras"></a>Представление дат в календарях с несколькими Эр

Если объект <xref:System.Globalization.Calendar> поддерживает эры и является текущим календарем объекта <xref:System.Globalization.CultureInfo>, эра включается в строковое представление даты и времени для полной даты, длинной даты и шаблонов короткой даты. В следующем примере показаны эти шаблоны даты при текущем языке и региональных параметрах "Японский (Япония)" и японском текущем календаре.

[!code-csharp[Conceptual.Calendars#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings1.cs#8)]
[!code-vb[Conceptual.Calendars#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings1.vb#8)]

> [!WARNING]
> Класс <xref:System.Globalization.JapaneseCalendar> является единственным классом календаря в .NET, который поддерживает даты более чем в одной эре и может быть текущим календарем <xref:System.Globalization.CultureInfo> объекта, в частности, объекта <xref:System.Globalization.CultureInfo>, который представляет японский язык (Япония).

Для всех календарей описатель пользовательского формата "g" добавляет эру в результирующую строку. В следующем примере используется строка пользовательского формата "мм-дд-гггг g", где в дату включается эра, при том что текущим является григорианский календарь.

[!code-csharp[Conceptual.Calendars#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings2.cs#9)]
[!code-vb[Conceptual.Calendars#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings2.vb#9)]

В случае когда строковое представление даты связано с календарем, который не является текущим, класс <xref:System.Globalization.Calendar> включает метод <xref:System.Globalization.Calendar.GetEra%2A?displayProperty=nameWithType>, который можно использовать с методами <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> и <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> для однозначного указания даты и эры. В следующем примере для демонстрации используется класс <xref:System.Globalization.JapaneseLunisolarCalendar>. Однако следует учесть, что если требуется включить в результирующую строку понятное имя или сокращенное имя вместо целого числа для эры, необходимо создать объект <xref:System.Globalization.DateTimeFormatInfo> и сделать календарь <xref:System.Globalization.JapaneseCalendar> его текущим календарем. (Календарь <xref:System.Globalization.JapaneseLunisolarCalendar> не может быть текущим календарем для какого-либо языка и региональных параметров, но в данном случае эры этих двух календарей совпадают.)

[!code-csharp[Conceptual.Calendars#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings3.cs#10)]
[!code-vb[Conceptual.Calendars#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings3.vb#10)]

В японских календарях первый год эры называется Ганнен (元年). Например, вместо эры 1 первый год эры Хэйсэй можно описать как эру Ганнен. .NET использует это соглашение в операциях форматирования для дат и времени, отформатированных со следующими стандартными или настраиваемыми строками формата даты и времени, когда они используются с <xref:System.Globalization.CultureInfo> объектом, представляющим язык и региональные параметры "ja-JP" с <xref:System.Globalization.JapaneseCalendar> см

- [Шаблон длинной даты](../base-types/standard-date-and-time-format-strings.md#LongDate), обозначенный строкой стандартного формата даты и времени "D".
- [Шаблон полной даты длинного времени](../base-types/standard-date-and-time-format-strings.md#FullDateLongTime), обозначенный строкой стандартного формата даты и времени "F".
- [Шаблон полной даты и короткий формат времени](../base-types/standard-date-and-time-format-strings.md#FullDateShortTime), обозначенные строкой "f" стандартного формата даты и времени.
- [Шаблон "год/месяц](../base-types/standard-date-and-time-format-strings.md#YearMonth)", обозначенный строкой "y" или "y" стандартного формата даты и времени.
- [ [Строка настраиваемого формата даты и времени](../base-types/custom-date-and-time-format-strings.md)"ГГИ" 年 "" или "гги年".

Например, в следующем примере отображается дата в первом году эры эры в <xref:System.Globalization.JapaneseCalendar>.

  [!code-csharp[gannen](~/samples/snippets/standard/datetime/calendars/gannen/cs/program.cs)]
  [!code-vb[gannen](~/samples/snippets/standard/datetime/calendars/gannen/vb/gannen-fmt.vb)]

Если это поведение нежелательно в операциях форматирования, можно восстановить предыдущее поведение, которое всегда представляет первый год эры как "1", а не "Ганнен", выполнив следующие действия в зависимости от версии .NET:

- **.NET Core:** В файл конфигурации *. netcore. Runtime. JSON* можно добавить следующий код:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.FormatJapaneseFirstYearAsANumber": true
    }
  }
  ```

- **.NET Framework 4,6 или более поздней версии:** Можно задать следующий параметр AppContext:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.FormatJapaneseFirstYearAsANumber=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 или более ранней версии:** Можно задать следующее значение реестра:

   |  |  |
   |--|--|
   |Раздел | HKEY_LOCAL_MACHINE\Software\Microsoft\.Нетфрамеворк\аппконтекст |
   |Название | Switch. System. Globalization. Форматжапанесефирстеарасанумбер |
   |Type | REG_SZ |
   |значения | true |

Если поддержка ганнен в операциях форматирования отключена, в предыдущем примере выводятся следующие выходные данные:

```console
Japanese calendar date: 平成1年8月18日 (Gregorian: Friday, August 18, 1989)
```

Платформа .NET также была обновлена так, что операции синтаксического анализа даты и времени поддерживают строки, содержащие год, представленный как "1" или Ганнен. Хотя это делать не нужно, можно восстановить предыдущее поведение, чтобы распознать только "1" в качестве первого года эры. Это можно сделать следующим образом в зависимости от версии .NET:

- **.NET Core:** В файл конфигурации *. netcore. Runtime. JSON* можно добавить следующий код:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceLegacyJapaneseDateParsing": true
    }
  }
  ```

- **.NET Framework 4,6 или более поздней версии:** Можно задать следующий параметр AppContext:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceLegacyJapaneseDateParsing=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 или более ранней версии:** Можно задать следующее значение реестра:

   |  |  |
   |--|--|  
   |Раздел | HKEY_LOCAL_MACHINE\Software\Microsoft\.Нетфрамеворк\аппконтекст |
   |Название | Switch. System. Globalization. Енфорцелегацижапанеседатепарсинг |
   |Type | REG_SZ |
   |значения | true | 

## <a name="see-also"></a>См. также

- [Пошаговое руководство. Отображение дат в календарях, отличных от григорианского](../../../docs/standard/base-types/how-to-display-dates-in-non-gregorian-calendars.md)
- [Пример: служебная программа диапазона календарных недель](https://code.msdn.microsoft.com/NET-Framework-4-Calendar-3360a84a)
- [Класс Calendar](xref:System.Globalization.Calendar)
