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
ms.openlocfilehash: de8e5a03c769a22f3320c7785706555898bf8c1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401235"
---
# <a name="work-with-calendars"></a>Работа с календарями

Несмотря на то что значение даты и времени обозначает момент во времени, его строковое представление зависит от конкретного языка и региональных параметров. На него влияют как принятые стандарты обозначения даты и времени, так и используемый календарь. Эта тема исследует поддержку календарей в .NET и обсуждает использование классов календаря при работе со значениями дат.

## <a name="calendars-in-net"></a>Календари в .NET

Все календари в .NET <xref:System.Globalization.Calendar?displayProperty=nameWithType> вытекают из класса, который обеспечивает реализацию базового календаря. Одним из классов, наследующих от класса <xref:System.Globalization.Calendar>, является класс <xref:System.Globalization.EastAsianLunisolarCalendar> — базовый класс для всех лунно-солнечных календарей. .NET включает в себя следующие реализации календаря:

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

- Как календарь, используемый для конкретных языка и региональных параметров. Каждый объект <xref:System.Globalization.CultureInfo> имеет текущий календарь, то есть календарь, который объект использует в настоящий момент. Строковое представление значений даты и времени автоматически отражает используемые язык и региональные параметры и текущий календарь. Обычно текущий календарь является календарем по умолчанию для языка и региональных параметров. <xref:System.Globalization.CultureInfo>объекты также имеют дополнительные календари, которые включают дополнительные календари, которые может использовать культура.

- Как самостоятельный календарь, не зависящий от конкретных языка и региональных параметров. В таком случае методы <xref:System.Globalization.Calendar> используются для выражения дат и значений календаря.

Обратите внимание, что шесть классов календаря (<xref:System.Globalization.ChineseLunisolarCalendar>, <xref:System.Globalization.JapaneseLunisolarCalendar>, <xref:System.Globalization.JulianCalendar>, <xref:System.Globalization.KoreanLunisolarCalendar>, <xref:System.Globalization.PersianCalendar> и <xref:System.Globalization.TaiwanLunisolarCalendar>) можно использовать только как самостоятельные календари. Никакие языки и региональные параметры не используют их как календари по умолчанию или как дополнительные календари.

## <a name="calendars-and-cultures"></a>Календари и культуры

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

### <a name="instantiate-dates-based-on-a-calendar"></a>Мгновенные даты, основанные на календаре

Поскольку значения <xref:System.DateTime> и <xref:System.DateTimeOffset> основываются на григорианском календаре, необходимо вызвать перегруженный конструктор, включающий параметр типа <xref:System.Globalization.Calendar>, для создания значения даты, если требуется использовать значение дня, месяца или года по другому календарю. Можно также вызвать одну из перегрузок метода <xref:System.Globalization.Calendar.ToDateTime%2A?displayProperty=nameWithType> конкретного календаря для создания объекта <xref:System.DateTime> на основе значений конкретного календаря.

В следующем примере первое значение <xref:System.DateTime> создается путем передачи объекта <xref:System.Globalization.HebrewCalendar> конструктору <xref:System.DateTime>, а второе значение <xref:System.DateTime> создается путем вызова метода <xref:System.Globalization.HebrewCalendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>. Поскольку эти два значения создаются с одинаковыми значениями еврейского календаря, вызов метода <xref:System.DateTime.Equals%2A?displayProperty=nameWithType> показывает, что два значения <xref:System.DateTime> совпадают.

[!code-csharp[Conceptual.Calendars#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatehcdate1.cs#4)]
[!code-vb[Conceptual.Calendars#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatehcdate1.vb#4)]

### <a name="represent-dates-in-the-current-calendar"></a>Представление дат в текущем календаре

Методы форматирования даты и времени при преобразовании дат в строки всегда используют текущий календарь. Это значит, что строковое представление года, месяца и дня месяца отражают текущий календарь, а не обязательно григорианский календарь.

В следующем примере показано, как текущий календарь влияет на строковое представление даты. Текущий язык и региональные параметры изменяются на "Китайский (традиционное письмо, Тайвань)", затем создается значение даты. Затем отображается текущий календарь и дата, текущий календарь изменяется на <xref:System.Globalization.TaiwanCalendar>, текущий календарь и дата отображаются снова. При первом отображении даты она представляется как дата григорианского календаря. При отображении даты во второй раз она представляется как дата тайваньского календаря.

[!code-csharp[Conceptual.Calendars#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/currentcalendar1.cs#5)]
[!code-vb[Conceptual.Calendars#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/currentcalendar1.vb#5)]

### <a name="represent-dates-in-a-non-current-calendar"></a>Представление дат в нетекущем календаре

Чтобы представить дату с помощью календаря, который не является текущим для языка и региональных параметров, необходимо вызвать методы нужного объекта <xref:System.Globalization.Calendar>. Например, методы <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> и <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> преобразуют значения года, месяца и дня в значения, соответствующие определенному календарю.

> [!WARNING]
> Поскольку некоторые календари не являются дополнительными календарями ни для какого языка и региональных параметров, указание дат по этим календарям всегда требует вызова методов календаря. Это верно для всех календарей, унаследованных от классов <xref:System.Globalization.EastAsianLunisolarCalendar>, <xref:System.Globalization.JulianCalendar> и <xref:System.Globalization.PersianCalendar>.

В следующем примере используется объект <xref:System.Globalization.JulianCalendar> для создания даты 9 января 1905 года по юлианскому календарю. При отображении этой даты по календарю по умолчанию (григорианскому), она представляется как 22 января 1905 года. Вызов отдельных методов <xref:System.Globalization.JulianCalendar> позволяет отобразить дату по юлианскому календарю.

[!code-csharp[Conceptual.Calendars#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/noncurrentcalendar1.cs#6)]
[!code-vb[Conceptual.Calendars#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/noncurrentcalendar1.vb#6)]

### <a name="calendars-and-date-ranges"></a>Календари и диапазоны дат

Самая ранняя дата, поддерживаемая календарем, отображается свойством <xref:System.Globalization.Calendar.MinSupportedDateTime%2A?displayProperty=nameWithType> этого календаря. Для класса <xref:System.Globalization.GregorianCalendar> эта дата — 1 января 0001 года нашей эры. Большинство других календарей в .NET поддерживают более позднюю дату. При попытке работы с датой и временем, меньшими самой ранней поддерживаемой календарем даты, возникнет исключение <xref:System.ArgumentOutOfRangeException>.

Однако существует одно важное исключение из этого правила. По умолчанию (неинициализированное) значение объекта <xref:System.DateTime> и объекта <xref:System.DateTimeOffset> равно значению <xref:System.Globalization.GregorianCalendar.MinSupportedDateTime%2A?displayProperty=nameWithType>. Если вы попытаетесь отформатировать эту дату в календаре, который не поддерживает 1 0001 января C.E. и вы не предоставляете спецификацию формата, метод форматирования использует s» (сортируемую дату/шаблон времени) формат ный разоснажитель вместо спецификации формата "G" (общая дата/время) формата. В результате операция форматирования не вызовет исключения <xref:System.ArgumentOutOfRangeException>. Вместо этого будет возвращена неподдерживаемая дата. Это продемонстрировано в следующем примере, отображающем значение <xref:System.DateTime.MinValue?displayProperty=nameWithType> во время установки текущих языка и региональных параметров в японские (Япония) с японским календарем и в арабские (Египет) с календарем Um Al Qura. Также текущие язык и региональные параметры устанавливаются в английские (США) и вызывается метод <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType> с каждым из этих объектов <xref:System.Globalization.CultureInfo>. В каждом случае дата отображается с помощью сортируемого шаблона даты и времени.

[!code-csharp[Conceptual.Calendars#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/minsupporteddatetime1.cs#11)]
[!code-vb[Conceptual.Calendars#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/minsupporteddatetime1.vb#11)]

## <a name="work-with-eras"></a>Работа с эрами

В календарях даты обычно разделены на эры. Однако <xref:System.Globalization.Calendar> классы в .NET не поддерживают каждую эпоху, <xref:System.Globalization.Calendar> определяемую календарем, и большинство классов поддерживают только одну эпоху. Только классы <xref:System.Globalization.JapaneseCalendar> и <xref:System.Globalization.JapaneseLunisolarCalendar> поддерживают несколько эр.

> [!IMPORTANT]
> Эра Рейвы, новая эра <xref:System.Globalization.JapaneseCalendar> <xref:System.Globalization.JapaneseLunisolarCalendar>в и , начинается 1 мая 2019 года. Это изменение затрагивает все приложения, использующие эти календари. Дополнительные сведения см. в этих статьях:
>
> - [Обработка новой эры в японском календаре в .NET](https://devblogs.microsoft.com/dotnet/handling-a-new-era-in-the-japanese-calendar-in-net/), которая документирует функции, добавленные в .NET для поддержки календарей с несколькими эпохами и обсуждает лучшие практики для использования при обработке календарей нескольких эпох.
> - [Подготовьте приложение к изменению японской эпохи,](/windows/uwp/design/globalizing/japanese-era-change)которое предоставляет информацию о тестировании приложений на Windows, чтобы обеспечить их готовность к изменению эпохи.
> - [Резюме новых обновлений японской эры для .NET Framework](https://support.microsoft.com/help/4477957/new-japanese-era-updates-for-net-framework), в котором перечислены обновления .NET Framework для отдельных версий Windows, связанные с новой японской календарной эрой, отмечаются новые функции .NET Framework для поддержки нескольких эпох и включает в себя вещи, которые следует искать при тестировании приложений.

Эпоха в большинстве календарей обозначает чрезвычайно длительный период времени. В григорианском календаре, например, нынешняя эпоха охватывает более двух тысячелетий. Для <xref:System.Globalization.JapaneseCalendar> и <xref:System.Globalization.JapaneseLunisolarCalendar>, два календаря, которые поддерживают несколько эр, это не так. Эпоха соответствует периоду правления императора. Поддержка нескольких эпох, особенно когда верхний предел нынешней эпохи неизвестна, создает особые проблемы.

### <a name="eras-and-era-names"></a>Имена эпохи и эпохи

В .NET целые число, представляющие тетеры, поддерживаемые определенной реализацией календаря, хранятся в обратном порядке в массиве. <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType> Нынешняя эра (которая является эпохой с последним диапазоном <xref:System.Globalization.Calendar> времени) находится на нулевом уровне индекса, а для классов, поддерживающих несколько эпох, каждый последовательный индекс отражает предыдущую эпоху. Статическое свойство <xref:System.Globalization.Calendar.CurrentEra?displayProperty=nameWithType> определяет индекс текущей эры в массиве <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType>; это константа, значение которой всегда ноль. Отдельные классы <xref:System.Globalization.Calendar> также включают статические поля, возвращающие значение текущей эры. Они перечислены в следующей таблице.

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

Имя, соответствующее номеру конкретной эры, которое можно получить, передав номер эры методу <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> или <xref:System.Globalization.DateTimeFormatInfo.GetAbbreviatedEraName%2A?displayProperty=nameWithType>. В следующем примере эти методы вызываются для получения информации о поддержке эр в классе <xref:System.Globalization.GregorianCalendar>. Он отображает григорианский календарный день, который соответствует 1 января второго года текущей эры, а также григорианский календарный день, который соответствует 1 января второго года каждой поддерживаемой японской календарной эры.

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb)]

Кроме того, строка пользовательского формата даты и времени "g" включает имя эры календаря в строковое представлении даты и времени. Для получения дополнительной [информации см.](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)

### <a name="instantiatie-a-date-with-an-era"></a>Мгновенное свидание с эпохой

Для двух <xref:System.Globalization.Calendar> классов, поддерживающих несколько времен, дата, состоящая из определенного года, месяца и дня месяца, может быть неоднозначной. Например, во всех герах, поддерживаемых <xref:System.Globalization.JapaneseCalendar> годами, число которых составляет 1. Обычно если эра не указана, методы даты и времени и календаря предполагают, что значения относятся к текущей эре. Это относится <xref:System.DateTime.%23ctor%2A> и <xref:System.DateTimeOffset.%23ctor%2A> к конструкторам, которые <xref:System.Globalization.Calendar>включают параметры типа, а также [japaneseCalendar.ToDateTime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) и [JapaneseLunisolarCalendar.ToDate](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) методы. Следующий пример мгновенно указывает дату, которая представляет 1 января второго года неустановленной эпохи. Если выполнить пример, когда эра Рейвы является текущая эра, дата интерпретируется как второй год эры Рейвы. Эпоха, No, предшествует году в строке возвращается <xref:System.DateTime.ToString(System.String,System.IFormatProvider)?displayProperty=nameWithType> методом и соответствует 1 января 2020 года, в григорианском календаре. (Эра Рейвы начинается в 2019 году по григорианскому календарю.)

[!code-csharp[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/cs/program.cs)]
[!code-vb[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/vb/program.vb)]

Однако, если эпоха меняется, цель этого кода становится двусмысленной. Является ли дата предназначена для представления второго года нынешней эры, или она предназначена для представления второго года эпохи Хэйсэй? Есть два способа избежать этой двусмысленности:

- Мгновенное значение даты и времени с <xref:System.Globalization.GregorianCalendar> помощью класса по умолчанию. Затем можно использовать японский календарь или японский лунисолнечный календарь для представления строки дат, как показано в следующем примере.

  [!code-csharp[Insantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/cs/program.cs)]
  [!code-vb[Instantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/vb/program.vb)]

- Вызов метода даты и времени, который явно определяет эпоху. Включены следующие методы:

  - Метод <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> <xref:System.Globalization.JapaneseCalendar> или <xref:System.Globalization.JapaneseLunisolarCalendar> класс.

  - A <xref:System.DateTime> <xref:System.DateTimeOffset> или разбор метод, <xref:System.DateTime.Parse%2A>таких <xref:System.DateTime.TryParse%2A> <xref:System.DateTime.ParseExact%2A>как <xref:System.DateTime.TryParseExact%2A>, , или , который включает в <xref:System.Globalization.DateTimeStyles> себя строку, которая будет разогнана и дополнительно аргумент, <xref:System.Globalization.JapaneseCalendar>если нынешняя культура японско-японской ("ja-JP") и календарь культуры является . Строка, которая должна быть разогнана должна включать эпоху.

  - Метод <xref:System.DateTime> <xref:System.DateTimeOffset> а или разбора, `provider` включающий параметр типа. <xref:System.IFormatProvider> `provider`должен быть <xref:System.Globalization.CultureInfo> либо объект, представляющий японо-японскую ("ja-JP") <xref:System.Globalization.DateTimeFormatInfo.Calendar> культуру, <xref:System.Globalization.JapaneseCalendar>текущий <xref:System.Globalization.JapaneseCalendar> <xref:System.Globalization.DateTimeFormatInfo> календарь которого, либо объект, собственностью которого является . Строка, которая должна быть разогнана должна включать эпоху.

  В следующем примере используются три из этих методов для мгновенного даты и времени в эпоху Мэйдзи, которая началась 8 сентября 1868 года и закончилась 29 июля 1912 года.

  [!code-csharp[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/cs/program.cs)]
  [!code-vb[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/vb/program.vb)]

> [!TIP]
> При работе с календарями, поддерживающими несколько эпох, *всегда* используйте григорианскую дату, чтобы мгновенно определить дату, или указать эпоху, когда вы мгновенно дате и времени на основе этого календаря.

При указании эпохи <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> метода вы предоставляете индекс эпохи <xref:System.Globalization.Calendar.Eras> в свойстве календаря. Однако для календарей, чьи эры могут быть изменены, эти индексы не являются постоянными значениями; текущая эра находится на индексе 0, `Eras.Length - 1`а самая старая эпоха находится на индексе . Когда новая эра добавляется к календарю, индексы предыдущих эпох увеличиваются на один. Соответствующий индекс эпохи можно предоставить следующим образом:

- Для дат в текущую эпоху всегда <xref:System.Globalization.Calendar.CurrentEra> используйте свойство календаря.

- Для дат в заданную <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> эпоху используйте метод для получения индекса, который соответствует заданной эпохе. Это требует, <xref:System.Globalization.JapaneseCalendar> чтобы текущий <xref:System.Globalization.CultureInfo> календарь объекта, представляющий культуру ja-JP.  (Этот метод работает <xref:System.Globalization.JapaneseLunisolarCalendar> и для того, чтобы поддерживать <xref:System.Globalization.JapaneseCalendar>те же эры, что и .) Предыдущий пример иллюстрирует этот подход.

### <a name="calendars-eras-and-date-ranges-relaxed-range-checks"></a>Календари, эры и диапазоны дат: Проверки диапазона расслабленных

Очень похоже на то, что отдельные календари <xref:System.Globalization.JapaneseCalendar> <xref:System.Globalization.JapaneseLunisolarCalendar> поддерживали диапазоны дат, эры в классах и классах также поддерживали диапазоны. Ранее .NET использовал строгие проверки диапазона эпохи, чтобы убедиться, что дата, относясь к эпохе, находится в пределах той эпохи. То есть, если дата находится за пределами диапазона указанной <xref:System.ArgumentOutOfRangeException>эпохи, метод бросает . В настоящее время .NET использует расслабленную проверку диапазона по умолчанию. Обновления для всех версий .NET ввели расслабленной проверки диапазона эпохи; попытка мгновенного времени конкретной даты, которая находится за пределами диапазона указанной эпохи "переливы" в следующую эпоху, и не выбрасывается.

Следующий пример пытается мгновенно учтивить дату в 65-м году эпохи Сёва, которая началась 25 декабря 1926 года и закончилась 7 января 1989 года. Эта дата соответствует 9 января 1990 года, который находится вне <xref:System.Globalization.JapaneseCalendar>диапазона эпохи Сая в . Как показано на примере, дата, показанная в этом примере, — 9 января 1990 года, на втором году эры Хэйсэй.

  [!code-csharp[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/cs/program.cs)]
  [!code-vb[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/vb/program.vb)]

Если непринужденные проверки диапазона нежелательны, вы можете восстановить строгие проверки диапазона несколькими способами, в зависимости от версии .NET, на которой работает приложение:

- **Ядро .NET:** Добавьте следующее в файл конфигурации *.netcore.runtime.json:*

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceJapaneseEraYearRanges": true
    }
  }
  ```

- **Рамочный 4.NET 4.6 или более позднее:** Установите следующий переключатель AppContext в файле *app.config:*

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceJapaneseEraYearRanges=true" />
    </runtime>
  </configuration>
  ```

- **Рамочная программа .NET 4.5.2 или ранее:** Установите следующее значение реестра:

   |  |  |
   |--|--|
   | **Клавиша** | **HKEY_LOCAL_MACHINE-Программное\\обеспечение»Microsoft . NETFramework-AppContext** |
   | **Название** | Switch.System.Globalization.EnforceJapaneseEraYearRanges |
   | **Тип** | REG_SZ |
   | **Значение** | Да |

При строгом включении проверки <xref:System.ArgumentOutOfRangeException> диапазона предыдущий пример бросает и отображает следующий выход:

```console
Unhandled Exception: System.ArgumentOutOfRangeException: Valid values are between 1 and 64, inclusive.
Parameter name: year
   at System.Globalization.GregorianCalendarHelper.GetYearOffset(Int32 year, Int32 era, Boolean throwOnError)
   at System.Globalization.GregorianCalendarHelper.ToDateTime(Int32 year, Int32 month, Int32 day, Int32 hour, Int32 minute, Int32 second, Int32 millisecond, Int32 era)
   at Example.Main()
```

### <a name="represent-dates-in-calendars-with-multiple-eras"></a>Представление дат в календарях с несколькими эрами

Если объект <xref:System.Globalization.Calendar> поддерживает эры и является текущим календарем объекта <xref:System.Globalization.CultureInfo>, эра включается в строковое представление даты и времени для полной даты, длинной даты и шаблонов короткой даты. В следующем примере показаны эти шаблоны даты при текущем языке и региональных параметрах "Японский (Япония)" и японском текущем календаре.

[!code-csharp[Conceptual.Calendars#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings1.cs#8)]
[!code-vb[Conceptual.Calendars#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings1.vb#8)]

> [!WARNING]
> Класс <xref:System.Globalization.JapaneseCalendar> является единственным классом календаря в .NET, который поддерживает даты в более <xref:System.Globalization.CultureInfo> чем одной эпохе <xref:System.Globalization.CultureInfo> и который может быть текущим календарем объекта - в частности, объекта, представляющего японскую (японскую) культуру.

Для всех календарей описатель пользовательского формата "g" добавляет эру в результирующую строку. В следующем примере используется строка пользовательского формата "мм-дд-гггг g", где в дату включается эра, при том что текущим является григорианский календарь.

[!code-csharp[Conceptual.Calendars#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings2.cs#9)]
[!code-vb[Conceptual.Calendars#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings2.vb#9)]

В случае когда строковое представление даты связано с календарем, который не является текущим, класс <xref:System.Globalization.Calendar> включает метод <xref:System.Globalization.Calendar.GetEra%2A?displayProperty=nameWithType>, который можно использовать с методами <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> и <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> для однозначного указания даты и эры. В следующем примере для демонстрации используется класс <xref:System.Globalization.JapaneseLunisolarCalendar>. Однако следует учесть, что если требуется включить в результирующую строку понятное имя или сокращенное имя вместо целого числа для эры, необходимо создать объект <xref:System.Globalization.DateTimeFormatInfo> и сделать календарь <xref:System.Globalization.JapaneseCalendar> его текущим календарем. (Календарь <xref:System.Globalization.JapaneseLunisolarCalendar> не может быть текущим календарем для какого-либо языка и региональных параметров, но в данном случае эры этих двух календарей совпадают.)

[!code-csharp[Conceptual.Calendars#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings3.cs#10)]
[!code-vb[Conceptual.Calendars#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings3.vb#10)]

В японских календарях первый год эпохи называется Ганнен( Например, вместо Heisei 1, первый год эры Хэйсэй можно описать как Heisei Gannen. .NET принимает эту конвенцию в форматировании операций для дат и времен, отформатированных <xref:System.Globalization.CultureInfo> со следующими стандартными или пользовательскими строками <xref:System.Globalization.JapaneseCalendar> даты и формата времени, когда они используются с объектом, представляющим японско-японскую ("ja-JP") культуру с классом:

- [Длинный шаблон даты,](../base-types/standard-date-and-time-format-strings.md#LongDate)указанный строкой стандартной даты и формата времени "D".
- [Полная дата длинная схема времени](../base-types/standard-date-and-time-format-strings.md#FullDateLongTime), указано на "F" стандартная дата и время форматстрокстроки.
- [Полная дата короткий шаблон времени](../base-types/standard-date-and-time-format-strings.md#FullDateShortTime), указанный "f" стандартная дата и время форматстроки строки.
- [Шаблон год/месяц,](../base-types/standard-date-and-time-format-strings.md#YearMonth)указанный строкой Y» или "y" стандартной даты и формата времени.
- «Ggy»» или «ggy» [пользовательские строки даты и формата времени.](../base-types/custom-date-and-time-format-strings.md)

Например, в следующем примере отображается дата в первый год <xref:System.Globalization.JapaneseCalendar>эры Хэйсэй в .

  [!code-csharp[gannen](~/samples/snippets/standard/datetime/calendars/gannen/cs/program.cs)]
  [!code-vb[gannen](~/samples/snippets/standard/datetime/calendars/gannen/vb/gannen-fmt.vb)]

Если такое поведение является нежелательным при форматировании операций, можно восстановить предыдущее поведение, которое всегда представляет собой первый год эпохи как "1", а не "Ганнен", делая следующее, в зависимости от версии .NET:

- **Ядро .NET:** Добавьте следующее в файл конфигурации *.netcore.runtime.json:*

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.FormatJapaneseFirstYearAsANumber": true
    }
  }
  ```

- **Рамочный 4.NET 4.6 или более позднее:** Установите следующий переключатель AppContext в файле *app.config:*

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.FormatJapaneseFirstYearAsANumber=true" />
    </runtime>
  </configuration>
  ```

- **Рамочная программа .NET 4.5.2 или ранее:** Установите следующее значение реестра:

   |  |  |
   |--|--|
   | **Клавиша** | **HKEY_LOCAL_MACHINE-Программное\\обеспечение»Microsoft . NETFramework-AppContext** |
   | **Название** | Switch.System.Globalization.FormatJapaneseFirstYearasANumber |
   | **Тип** | REG_SZ |
   | **Значение** | Да |

При отключении поддержки gannen при отключении операций форматирования предыдущий пример отображает следующий вывод:

```console
Japanese calendar date: 平成1年8月18日 (Gregorian: Friday, August 18, 1989)
```

.NET также был обновлен таким образом, чтобы строки поддержки операций даты и времени, содержащие год, представленный как "1" или Gannen. Хотя это не нужно делать, вы можете восстановить предыдущее поведение, чтобы распознать только "1" как первый год эпохи. Вы можете сделать это следующим образом, в зависимости от версии .NET:

- **Ядро .NET:** Добавьте следующее в файл конфигурации *.netcore.runtime.json:*

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceLegacyJapaneseDateParsing": true
    }
  }
  ```

- **Рамочный 4.NET 4.6 или более позднее:** Установите следующий переключатель AppContext в файле *app.config:*

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceLegacyJapaneseDateParsing=true" />
    </runtime>
  </configuration>
  ```

- **Рамочная программа .NET 4.5.2 или ранее:** Установите следующее значение реестра:

   |  |  |
   |--|--|
   | **Клавиша** | **HKEY_LOCAL_MACHINE-Программное\\обеспечение»Microsoft . NETFramework-AppContext** |
   | **Название** | Switch.System.Globalization.EnforceLegacyJapaneseDateParsing |
   | **Тип** | REG_SZ |
   | **Значение** | Да |

## <a name="see-also"></a>См. также раздел

- [Как: Отображение дат в негригорианских календарях](../../../docs/standard/base-types/how-to-display-dates-in-non-gregorian-calendars.md)
- [Пример: Утилита диапазона календарной недели](https://code.msdn.microsoft.com/NET-Framework-4-Calendar-3360a84a)
- [Класс календаря](xref:System.Globalization.Calendar)
