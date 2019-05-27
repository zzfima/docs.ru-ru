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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed276d8026201af94a0259c4258d5c50fa67c0f3
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053244"
---
# <a name="working-with-calendars"></a>Работа с календарями

Несмотря на то что значение даты и времени обозначает момент во времени, его строковое представление зависит от конкретного языка и региональных параметров. На него влияют как принятые стандарты обозначения даты и времени, так и используемый календарь. В этом разделе описывается поддержка календарей в .NET и обсуждается использование классов календарей при работе со значениями даты.

## <a name="calendars-in-net"></a>Календари в .NET

Всех календарей в .NET являются производными от <xref:System.Globalization.Calendar?displayProperty=nameWithType> класс, который предоставляет базовую реализацию календаря. Одним из классов, наследующих от класса <xref:System.Globalization.Calendar>, является класс <xref:System.Globalization.EastAsianLunisolarCalendar> — базовый класс для всех лунно-солнечных календарей. .NET включает следующие реализации календарей:

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

* Как календарь, используемый для конкретных языка и региональных параметров. Каждый объект <xref:System.Globalization.CultureInfo> имеет текущий календарь, то есть календарь, который объект использует в настоящий момент. Строковое представление значений даты и времени автоматически отражает используемые язык и региональные параметры и текущий календарь. Обычно текущий календарь является календарем по умолчанию для языка и региональных параметров. <xref:System.Globalization.CultureInfo> объекты также имеют дополнительные календари, которые включают дополнительные календари, которые можно использовать язык и региональные параметры.

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

Однако существует одно важное исключение из этого правила. По умолчанию (неинициализированное) значение объекта <xref:System.DateTime> и объекта <xref:System.DateTimeOffset> равно значению <xref:System.Globalization.GregorianCalendar.MinSupportedDateTime%2A?displayProperty=nameWithType>. При попытке форматирования этой даты в календаре, который не поддерживает 1 января 0001 года нашей эры и вы не укажете описатель формата, он использует описатель формата «s» (шаблон сортируемого формата даты и времени) вместо описатель формата «G» (общий формат даты/времени шаблон). В результате операция форматирования не вызовет исключения <xref:System.ArgumentOutOfRangeException>. Вместо этого будет возвращена неподдерживаемая дата. Это продемонстрировано в следующем примере, отображающем значение <xref:System.DateTime.MinValue?displayProperty=nameWithType> во время установки текущих языка и региональных параметров в японские (Япония) с японским календарем и в арабские (Египет) с календарем Um Al Qura. Также текущие язык и региональные параметры устанавливаются в английские (США) и вызывается метод <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType> с каждым из этих объектов <xref:System.Globalization.CultureInfo>. В каждом случае дата отображается с помощью сортируемого шаблона даты и времени.

[!code-csharp[Conceptual.Calendars#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/minsupporteddatetime1.cs#11)]
[!code-vb[Conceptual.Calendars#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/minsupporteddatetime1.vb#11)]

## <a name="working-with-eras"></a>Работа с эрами

В календарях даты обычно разделены на эры. Тем не менее <xref:System.Globalization.Calendar> классы в .NET не поддерживают каждый эры, определяемых календаря и большая часть <xref:System.Globalization.Calendar> классы поддерживают только одну эру. Только классы <xref:System.Globalization.JapaneseCalendar> и <xref:System.Globalization.JapaneseLunisolarCalendar> поддерживают несколько эр.

> [!IMPORTANT]
>  Эра Reiwa, новая эра <xref:System.Globalization.JapaneseCalendar> и <xref:System.Globalization.JapaneseLunisolarCalendar>, начинается с 1 мая 2019 г. Это изменение затрагивает все приложения, использующие эти календари. Ознакомьтесь со следующими статьями, Дополнительные сведения:
> - [Обработка новой эре японского календаря в .NET](https://devblogs.microsoft.com/dotnet/handling-a-new-era-in-the-japanese-calendar-in-net/), который Документирует, добавленных в .NET для поддержки календарей с несколько эр и рекомендации для использования при обработке нескольких эры календарей.
> - [Подготовка приложения для изменения японской эры](/windows/uwp/design/globalizing/japanese-era-change), который предоставляет данные для тестирования приложений на Windows для обеспечения их готовность к работе изменение эры.
> - [Сводка по новой японской эры обновления для .NET Framework](https://support.microsoft.com/help/4477957/new-japanese-era-updates-for-net-framework), перечисляя обновлениях платформы .NET Framework для отдельных версий Windows, которые связаны с новой эры японского календаря, заметок новые возможности .NET Framework для поддержки нескольких эры и включает в себя следует обратить внимание на в тестировании приложений.

Эру в большинстве календарей обозначает период очень много времени. Например, по григорианскому календарю, текущей эры охватывает более чем двумя тысячелетий. Для <xref:System.Globalization.JapaneseCalendar> и <xref:System.Globalization.JapaneseLunisolarCalendar>, два календари, поддерживающих несколько эр, это не так. Период reign императора соответствует эру. Поддержка несколько эр, особенно в том случае, если верхний предел текущей эры неизвестно, создает особые проблемы. 

### <a name="eras-and-era-names"></a>Эры и названия эр

В .NET, целые числа, обозначающие эры, поддерживаемые реализацией конкретного календаря, хранятся в обратном порядке в <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType> массива. Является текущей эры (которая прошла эра с последней диапазон времени) с нулевым индексом, а также для <xref:System.Globalization.Calendar> классов, поддерживающих несколько эр, каждый последующий индекс обозначает предыдущую эру. Статическое свойство <xref:System.Globalization.Calendar.CurrentEra?displayProperty=nameWithType> определяет индекс текущей эры в массиве <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType>; это константа, значение которой всегда ноль. Отдельные классы <xref:System.Globalization.Calendar> также включают статические поля, возвращающие значение текущей эры. Они перечислены в следующей таблице.

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

Имя, соответствующее номеру конкретной эры, которое можно получить, передав номер эры методу <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> или <xref:System.Globalization.DateTimeFormatInfo.GetAbbreviatedEraName%2A?displayProperty=nameWithType>. В следующем примере эти методы вызываются для получения информации о поддержке эр в классе <xref:System.Globalization.GregorianCalendar>. Он отображает дату григорианского календаря, который соответствует 1 января 1 второго года текущей эры, а также дата григорианского календаря, соответствующее 1 января 1 второго года каждой эре, поддерживаемой японского календаря.

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb)]

Кроме того, строка пользовательского формата даты и времени "g" включает имя эры календаря в строковое представлении даты и времени. Дополнительные сведения см. в разделе [настраиваемых форматов даты и времени строки](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).

### <a name="instantiating-a-date-with-an-era"></a>Создание даты с указанием эры

Для двух <xref:System.Globalization.Calendar> классов, поддерживающих несколько эр, дата, состоящая из определенный год, месяц и день месяца значения могут быть неоднозначными. Например, все эр, поддерживаемых <xref:System.Globalization.JapaneseCalendar> годы, номер которого равен 1. Обычно если эра не указана, методы даты и времени и календаря предполагают, что значения относятся к текущей эре. Это справедливо для <xref:System.DateTime.%23ctor%2A> и <xref:System.DateTimeOffset.%23ctor%2A> конструкторов, содержащих параметры типа <xref:System.Globalization.Calendar>, а также [JapaneseCalendar.ToDateTime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) и [JapaneseLunisolarCalendar.ToDateTime ](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) методы. В следующем примере создается дату, которая представляет 1 января 1 второго года неуказанных эры. Если при текущей эры эру Reiwa выполнения приведенного примера, дата интерпретируется как второй год Reiwa эры. Эра, 令和, предшествует году, в строку, возвращаемую <xref:System.DateTime.ToString(System.String,System.IFormatProvider)?displayProperty=nameWithType> метод и соответствует 1 января 2020 г., по григорианскому календарю. (Эра Reiwa начинается 2019 года по григорианскому календарю).

[!code-csharp[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/cs/program.cs)]
[!code-vb[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/vb/program.vb)]

Тем не менее если изменяется эру, цель этот код становится неоднозначным. Дата предназначен для представления второго года текущей эры, или его, предназначенной для представления второго года эры Хэйсэй? Существует два способа обойти эту двусмысленность:

- Создать экземпляр значение даты и времени, используя значение по умолчанию <xref:System.Globalization.GregorianCalendar> класса. Затем можно использовать японского календаря или японский лунно-солнечного календаря для строковым представлением даты, как показано в следующем примере.

   [!code-csharp[Insantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/cs/program.cs)]
   [!code-vb[Instantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/vb/program.vb)]

- Вызовите метод даты и времени, который явно указывает эру. Сюда входят следующие методы:

   - <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> Метод <xref:System.Globalization.JapaneseCalendar> или <xref:System.Globalization.JapaneseLunisolarCalendar> класса.

   - Объект <xref:System.DateTime> или <xref:System.DateTimeOffset> анализа метод, например <xref:System.DateTime.Parse%2A>, <xref:System.DateTime.TryParse%2A>, <xref:System.DateTime.ParseExact%2A>, или <xref:System.DateTime.TryParseExact%2A>, включающий в себя анализируемая строка и при необходимости <xref:System.Globalization.DateTimeStyles> аргумента, если текущий язык — японский — Япония (» ja-JP») и календарь данной культуры <xref:System.Globalization.JapaneseCalendar>. Строка для синтаксического анализа, должна включать эру.

   - Объект <xref:System.DateTime> или <xref:System.DateTimeOffset> синтаксического анализа метод, который включает в себя `provider` параметр типа <xref:System.IFormatProvider>. `provider` должен быть либо <xref:System.Globalization.CultureInfo> объекта, представляющего региональные параметры японский — Япония («ja-JP»), для которого текущий календарь <xref:System.Globalization.JapaneseCalendar> или <xref:System.Globalization.DateTimeFormatInfo> которого <xref:System.Globalization.DateTimeFormatInfo.Calendar> свойство <xref:System.Globalization.JapaneseCalendar>. Строка для синтаксического анализа, должна включать эру.

   В следующем примере три из этих методов для создания экземпляра даты и времени в эпоху Meiji, которая начала на 8 сентября 1868 до окончания на 29 июля 1912. 

   [!code-csharp[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/cs/program.cs)]
   [!code-vb[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/vb/program.vb)]

> [!TIP]
> При работе с календарями, поддерживающих несколько эр, *всегда* использовать для создания даты Дата по григорианскому календарю или указать эру при создании экземпляра даты и времени, на основе этого календаря.

При указании эру для <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> метод, укажите индекс эры в календаре <xref:System.Globalization.Calendar.Eras> свойство. Для календарей, в которых эр могут быть изменены Однако эти индексы не являются постоянными значениями; текущая эра хранится с индексом 0, а самая ранняя эра является индексом `Eras.Length - 1`. При добавлении новой эры в календаре, индексы предыдущих эры увеличиваться на единицу. Соответствующие эры индекса можно указать следующим образом:

- Для даты в текущей эре, всегда используйте календаря <xref:System.Globalization.Calendar.CurrentEra> свойство.

- Для дат в указанной эры, используйте <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> метод для извлечения индекса, который соответствует имени указанной эры. Это необходимо, <xref:System.Globalization.JapaneseCalendar> быть текущим календарем для объекта <xref:System.Globalization.CultureInfo> , представляющий региональных параметров ja-JP.  (Этот способ работает для <xref:System.Globalization.JapaneseLunisolarCalendar> , так как он поддерживает же эры как <xref:System.Globalization.JapaneseCalendar>.) Этот подход показан в предыдущем примере.

### <a name="calendars-eras-and-date-ranges-relaxed-range-checks"></a>Календари, эры и диапазоны дат: Диапазон нестрогой проверки

Очень очень похоже на отдельные календари установлена поддерживаемая диапазоны дат эр в <xref:System.Globalization.JapaneseCalendar> и <xref:System.Globalization.JapaneseLunisolarCalendar> классы также поддерживаются диапазоны. Ранее .NET использовать strict эры, диапазон проверяет, чтобы убедиться, что дату конкретной эры был в диапазоне от той эпохи, конечно. То есть, если дата находится вне диапазона указанной эры, метод вызывает <xref:System.ArgumentOutOfRangeException>. В настоящее время .NET использует нестрогой диапазонам проверки по умолчанию. Обновления для всех версий платформы .NET появились нестрогой эры диапазон проверки; При попытке создать экземпляр с датой конкретной эры, которая находится вне диапазона указанной эры «переполняет» в следующем эры, а исключение не создается.

В следующем примере предпринимается для создания даты 65th года Шова эры, который начата в 25 декабре, 1926 г. — и закончилась 7 января 1989 г. Эта дата соответствует 9 января 1990 г., который находится вне диапазона Шова эры в <xref:System.Globalization.JapaneseCalendar>. Как показано в выходных данных из примера, даты, отображенной в примере — 9 января 1990 г. второго года нашей эры Хэйсэй.

   [!code-csharp[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/cs/program.cs)]
   [!code-vb[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/vb/program.vb)]

Диапазон нестрогой проверки if являются нежелательно, можно восстановить strict диапазон проверки несколькими способами в зависимости от версии .NET, на котором выполняется приложение.

- **.NET core:** Можно добавить следующую команду, чтобы *. netcore.runtime.json* файл конфигурации:

   ```json
   "runtimeOptions": {
      "configProperties": {
         "Switch.System.Globalization.EnforceJapaneseEraYearRanges": true
      } 
   }
   ```

- **.NET framework 4.6 или более поздней версии:** Можно задать следующим переключателем AppContext.

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <configuration>
     <runtime>
       <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceJapaneseEraYearRanges=true" />
     </runtime>
   </configuration>
   ```

- **.NET framework 4.5.2 или более ранней версии:** Можно задать следующее значение реестра:

   |  |  |
   |--|--|
   |Ключ | HKEY_LOCAL_MACHINE\Software\Microsoft.NETFramework\AppContext |
   |name | Switch.System.Globalization.EnforceJapaneseEraYearRanges |
   |Тип | REG_SZ |
   |Значение | 1 |

С включены проверки strict диапазона, предыдущий пример создает <xref:System.ArgumentOutOfRangeException> и отображает следующие выходные данные:

```console
Unhandled Exception: System.ArgumentOutOfRangeException: Valid values are between 1 and 64, inclusive.
Parameter name: year
   at System.Globalization.GregorianCalendarHelper.GetYearOffset(Int32 year, Int32 era, Boolean throwOnError)
   at System.Globalization.GregorianCalendarHelper.ToDateTime(Int32 year, Int32 month, Int32 day, Int32 hour, Int32 minute, Int32 second, Int32 millisecond, Int32 era)
   at Example.Main()
```

### <a name="representing-dates-in-calendars-with-multiple-eras"></a>Представление дат в календарях с несколько эр

Если объект <xref:System.Globalization.Calendar> поддерживает эры и является текущим календарем объекта <xref:System.Globalization.CultureInfo>, эра включается в строковое представление даты и времени для полной даты, длинной даты и шаблонов короткой даты. В следующем примере показаны эти шаблоны даты при текущем языке и региональных параметрах "Японский (Япония)" и японском текущем календаре.

[!code-csharp[Conceptual.Calendars#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings1.cs#8)]
[!code-vb[Conceptual.Calendars#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings1.vb#8)]

> [!WARNING]
> <xref:System.Globalization.JapaneseCalendar> Класс — это единственный класс календаря в .NET, который поддерживает даты в нескольких эрах и при этом может быть текущим календарем для объекта <xref:System.Globalization.CultureInfo> объект — а именно объекта <xref:System.Globalization.CultureInfo> объект, представляющий культуру, японский (Япония).

Для всех календарей описатель пользовательского формата "g" добавляет эру в результирующую строку. В следующем примере используется строка пользовательского формата "мм-дд-гггг g", где в дату включается эра, при том что текущим является григорианский календарь.

[!code-csharp[Conceptual.Calendars#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings2.cs#9)]
[!code-vb[Conceptual.Calendars#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings2.vb#9)]

В случае когда строковое представление даты связано с календарем, который не является текущим, класс <xref:System.Globalization.Calendar> включает метод <xref:System.Globalization.Calendar.GetEra%2A?displayProperty=nameWithType>, который можно использовать с методами <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> и <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> для однозначного указания даты и эры. В следующем примере для демонстрации используется класс <xref:System.Globalization.JapaneseLunisolarCalendar>. Однако следует учесть, что если требуется включить в результирующую строку понятное имя или сокращенное имя вместо целого числа для эры, необходимо создать объект <xref:System.Globalization.DateTimeFormatInfo> и сделать календарь <xref:System.Globalization.JapaneseCalendar> его текущим календарем. (Календарь <xref:System.Globalization.JapaneseLunisolarCalendar> не может быть текущим календарем для какого-либо языка и региональных параметров, но в данном случае эры этих двух календарей совпадают.)

[!code-csharp[Conceptual.Calendars#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings3.cs#10)]
[!code-vb[Conceptual.Calendars#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings3.vb#10)]

В японских календари первый год эры называется Ганнэн (元年). Например вместо 1 Хэйсэй первого года эры Хэйсэй можно описать как Хэйсэй Ганнэн. .NET использует это соглашение, при форматировании операций для дат и времени строки, форматированные с следующий стандартный или пользовательский формат даты и времени при их использовании с <xref:System.Globalization.CultureInfo> , представляющий язык и региональные параметры японский — Япония («ja-JP») с <xref:System.Globalization.JapaneseCalendar> класса:

- [Полный шаблон даты](../base-types/standard-date-and-time-format-strings.md#LongDate), обозначаться стандартные Дата и время строка формата «D».
- [Шаблон полной даты длинного времени](../base-types/standard-date-and-time-format-strings.md#FullDateLongTime), обозначаться стандартные Дата и время строка формата «F».
- [Полная дата короткий шаблон времени](../base-types/standard-date-and-time-format-strings.md#FullDateShortTime), обозначаться стандартные Дата и время строка формата «f».
- [Шаблон года и месяца](../base-types/standard-date-and-time-format-strings.md#YearMonth), обозначаться Y» или «y» standard формата даты и времени строки.
- [«Ggy «年»» или «ggy年» [настраиваемых форматов даты и времени строка](../base-types/custom-date-and-time-format-strings.md).

Например, следующий пример отображает дату в первый год эры Хэйсэй в <xref:System.Globalization.JapaneseCalendar> .

   [!code-csharp[gannen](~/samples/snippets/standard/datetime/calendars/gannen/cs/program.cs)]
   [!code-vb[gannen](~/samples/snippets/standard/datetime/calendars/gannen/vb/gannen-fmt.vb)]

Если такое поведение является нежелательным в операциях форматирования, можно восстановить прежнее поведение, которое всегда представляет первый год эры как «1» вместо «Ганнэн», выполнив указанные ниже, в зависимости от версии .NET.

- **.NET core:** Можно добавить следующую команду, чтобы *. netcore.runtime.json* файл конфигурации:

   ```json
   "runtimeOptions": {
      "configProperties": {
         "Switch.System.Globalization.FormatJapaneseFirstYearAsANumber": true
      } 
   }
   ```

- **.NET framework 4.6 или более поздней версии:** Можно задать следующим переключателем AppContext.

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <configuration>
     <runtime>
       <AppContextSwitchOverrides value="Switch.System.Globalization.FormatJapaneseFirstYearAsANumber=true" />
     </runtime>
   </configuration>
   ```

- **.NET framework 4.5.2 или более ранней версии:** Можно задать следующее значение реестра:

   |  |  |
   |--|--|
   |Ключ | HKEY_LOCAL_MACHINE\Software\Microsoft.NETFramework\AppContext |
   |name | Switch.System.Globalization.FormatJapaneseFirstYearAsANumber |
   |Тип | REG_SZ |
   |Значение | 1 |

С поддержкой Ганнэн в операциях отключена форматирования предыдущий пример отображает следующие выходные данные:

```console
Japanese calendar date: 平成1年8月18日 (Gregorian: Friday, August 18, 1989)
```

.NET также было обновлено, чтобы даты и времени, в операциях синтаксического анализа поддерживает строки, содержащие года, как «1» или Ганнэн. Несмотря на то, что для этого нет необходимости, можно восстановить прежнее поведение для распознает только «1» в качестве первого года эры. Это можно сделать следующим образом, в зависимости от версии .NET:

- **.NET core:** Можно добавить следующую команду, чтобы *. netcore.runtime.json* файл конфигурации:

   ```json
   "runtimeOptions": {
      "configProperties": {
         "Switch.System.Globalization.EnforceLegacyJapaneseDateParsing": true
      } 
   }
   ```

- **.NET framework 4.6 или более поздней версии:** Можно задать следующим переключателем AppContext.

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <configuration>
     <runtime>
       <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceLegacyJapaneseDateParsing=true" />
     </runtime>
   </configuration>
   ```

- **.NET framework 4.5.2 или более ранней версии:** Можно задать следующее значение реестра:

   |  |  |
   |--|--|  
   |Ключ | HKEY_LOCAL_MACHINE\Software\Microsoft.NETFramework\AppContext |
   |name | Switch.System.Globalization.EnforceLegacyJapaneseDateParsing |
   |Тип | REG_SZ |
   |Значение | 1 | 

## <a name="see-also"></a>См. также

- [Практическое руководство. Отображение дат в календарях, отличных от григорианского](../../../docs/standard/base-types/how-to-display-dates-in-non-gregorian-calendars.md)
- [Пример. Служебная программа диапазон неделя календаря](https://code.msdn.microsoft.com/NET-Framework-4-Calendar-3360a84a)
- [Класс календаря](xref:System.Globalization.Calendar)
