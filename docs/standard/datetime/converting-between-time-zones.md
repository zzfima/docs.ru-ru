---
title: Преобразование времени из одного часового пояса в другой
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], converting
- time zones [.NET Framework], conversions
- UTC times, converting
- converting times
- local time conversions
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5b78e3985169954d71b479aa2e8a034f61afc01
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106976"
---
# <a name="converting-times-between-time-zones"></a>Преобразование времени из одного часового пояса в другой

Обработка различий между часовыми поясами становится все более важной для всех приложений, которые работают с датами и временем. Приложение больше не может считать, что все значения времени могут быть выражены в местном времени, которое является временем, доступным <xref:System.DateTime> в структуре. Например, веб-страница, которая отображает текущее время в восточной части США, будет содержать недостоверные сведения для пользователей в восточной Азии. В этом разделе объясняется, как преобразовать время из одного часового пояса в другой, а также как <xref:System.DateTimeOffset> преобразовать значения с ограниченной поддержкой часовых поясов.

## <a name="converting-to-coordinated-universal-time"></a>Преобразование во время в формате UTC

Время в формате UTC — это высокоточный, атомарный стандарт времени. Часовые пояса выражаются как положительные или отрицательные смещения относительно времени в формате UTC. Таким образом, время в формате UTC предоставляет тип времени, свободного от часовых поясов, или нейтрального времени часового пояса. Использование времени в формате UTC рекомендовано, когда важна совместимость даты и времени между компьютерами. (Дополнительные сведения и другие рекомендации по датам и времени см. [в разделе Создание кода рекомендаций с использованием DateTime в .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973825(v=msdn.10)).) Преобразование отдельных часовых поясов во время в формате UTC упрощает сравнение времен.

> [!NOTE]
> Можно также сериализовать <xref:System.DateTimeOffset> структуру для однозначного представления одного момента времени. Поскольку <xref:System.DateTimeOffset> объекты хранят значение даты и времени вместе со смещением от времени в формате UTC, они всегда представляют определенный момент времени в связи с временем в формате UTC.

Самый простой способ преобразовать время в формат UTC — вызвать `static` метод (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> . Точное преобразование, выполняемое методом, зависит от значения `dateTime` <xref:System.DateTime.Kind%2A> свойства параметра, как показано в следующей таблице.

| `DateTime.Kind`            | Преобразование                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Преобразует местное время во время в формате UTC.                                                    |
| `DateTimeKind.Unspecified` | Предполагает, что параметр `dateTime` является местным временем и преобразовывает местное время в UTC. |
| `DateTimeKind.Utc`         | Возвращает неизмененный параметр `dateTime`.                                    |

Следующий код преобразовывает текущее местное время во время в формате UTC и выводит результат на консоль.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

Если значение даты и времени не представляет ни местное время, ни время в формате UTC, <xref:System.DateTime.ToUniversalTime%2A> то, скорее всего, метод вернет ошибочный результат. Однако можно использовать <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> метод для преобразования даты и времени из указанного часового пояса. (Дополнительные сведения о получении <xref:System.TimeZoneInfo> объекта, представляющего часовой пояс назначения, см. в разделе Поиск часовых поясов, [определенных в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) В следующем коде используется <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> метод для преобразования восточного стандартного времени в формат UTC.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Обратите внимание, что этот <xref:System.ArgumentException> метод создает <xref:System.DateTime> исключение, <xref:System.DateTime.Kind%2A> если свойство объекта и часовой пояс не совпадают. Несоответствие возникает, если <xref:System.DateTime.Kind%2A> свойство имеет <xref:System.DateTimeKind.Local?displayProperty=nameWithType> значение <xref:System.DateTime.Kind%2A> <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> <xref:System.TimeZoneInfo> ,но<xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>объект не представляет местный часовой пояс, или если свойство имеет значение, но объектнеравен.<xref:System.TimeZoneInfo>

Все эти методы принимают <xref:System.DateTime> значения в качестве параметров и <xref:System.DateTime> возвращают значение. Для <xref:System.DateTimeOffset> значений <xref:System.DateTimeOffset> структура имеет<xref:System.DateTimeOffset.ToUniversalTime%2A> метод экземпляра, который преобразует дату и время текущего экземпляра в формат UTC. В следующем примере вызывается <xref:System.DateTimeOffset.ToUniversalTime%2A> метод для преобразования местного времени и нескольких других значений времени в формат UTC.

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Преобразование времени в формате UTC в заданный часовой пояс

Для преобразования времени в формате UTC в местное время см. следующий раздел "преобразование времени UTC в местное время". Для преобразования времени в формате UTC во время в любом назначенном часовом поясе вызовите <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> метод. Этот метод принимает два параметра:

- Время в формате UTC, которое требуется преобразовать. Это должно быть <xref:System.DateTime> значение, свойство <xref:System.DateTime.Kind%2A> `Unspecified` которого равно или `Utc`.

- Часовой пояс, в который требуется преобразовать время в формате UTC.

Следующий код преобразует время в формате UTC в центральное стандартное время.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Преобразование времени в формате UTC в местное время

Для преобразования времени в формате UTC в местное время <xref:System.DateTime.ToLocalTime%2A> вызовите метод <xref:System.DateTime> объекта, время которого необходимо преобразовать. Точное поведение метода зависит от значения <xref:System.DateTime.Kind%2A> свойства объекта, как показано в следующей таблице.

| `DateTime.Kind`            | Преобразование                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | <xref:System.DateTime> Возвращает значение без изменений.                                      |
| `DateTimeKind.Unspecified` | Предполагается, <xref:System.DateTime> что значение равно UTC и преобразует UTC в местное время. |
| `DateTimeKind.Utc`         | <xref:System.DateTime> Преобразует значение в местное время.                                 |

> [!NOTE]
> Метод ведет себя идентично `DateTime.ToLocalTime` методу. <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> Он принимает один параметр, который представляет собой значение даты и времени для преобразования.

Можно также преобразовать время в любом заданном часовом поясе в местное время с помощью `static` метода`Shared` (в Visual Basic <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> ). Этот метод рассматривается в следующем разделе.

## <a name="converting-between-any-two-time-zones"></a>Преобразование между любыми двумя часовыми поясами

Преобразование между любыми двумя часовыми поясами можно выполнить с помощью любого из `static` следующих`Shared` двух методов (в <xref:System.TimeZoneInfo> Visual Basic) класса:

- <xref:System.TimeZoneInfo.ConvertTime%2A>

  Параметры этого метода — это значение даты и времени для преобразования, `TimeZoneInfo` объект, представляющий часовой пояс значения даты и времени, `TimeZoneInfo` и объект, представляющий часовой пояс для преобразования значения даты и времени в.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  Параметры этого метода — это значение даты и времени для преобразования, идентификатор часового пояса значения даты и времени и идентификатор часового пояса, в который необходимо преобразовать значение даты и времени.

Для обоих методов требуется, <xref:System.DateTime.Kind%2A> чтобы свойство значения даты и времени было преобразовано, <xref:System.TimeZoneInfo> а объект или идентификатор часового пояса, представляющий его часовой пояс, соответствовал друг другу. В противном случае возникает исключение <xref:System.ArgumentException>. Например, если `Kind` свойство значения даты и времени равно `DateTimeKind.Local`, возникает `TimeZoneInfo` исключение, если объект, переданный в качестве `TimeZoneInfo.Local`параметра в метод, не равен. Исключение также создается, если идентификатор, переданный в качестве параметра в метод, не равен `TimeZoneInfo.Local.Id`.

В следующем примере используется <xref:System.TimeZoneInfo.ConvertTime%2A> метод для преобразования из Гавайского стандартного времени в местное время.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Преобразование значений DateTimeOffset

Значения даты и времени, представленные <xref:System.DateTimeOffset> объектами, не имеют полной осведомленности о часовых поясах, так как объект не связан с часовым поясом во время создания экземпляра. Однако во многих случаях приложению достаточно преобразовать дату и время на основе двух различных значений смещения относительно времени в формате UTC, а не на основе времени конкретных часовых поясов. Чтобы выполнить это преобразование, можно вызвать <xref:System.DateTimeOffset.ToOffset%2A> метод текущего экземпляра. Единственным параметром метода является смещение нового значения даты и времени, возвращаемого методом.

Например, если дата и время запроса пользователя к веб-странице известны и сериализованы в виде строки в формате мм/дд/гггг чч:мм:сс zzzz, то следующий метод `ReturnTimeOnServer` преобразует это значение даты и времени в значение даты и времени на веб-сервере.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

Если методу передается строка "9/1/2007 5:32:07 -05:00", которая представляет дату и время в часовом поясе, который раньше пояса UTC на пять часов, он возвращает строку "9/1/2007 3:32:07 -07:00" для сервера, расположенного в тихоокеанском стандартном часовом поясе США.

Класс также включает перегрузку <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> метода, который выполняет преобразование часовых поясов со <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> значениями. <xref:System.TimeZoneInfo> Параметры метода являются <xref:System.DateTimeOffset> значением и ссылкой на часовой пояс, к которому необходимо преобразовать время. Вызов метода возвращает <xref:System.DateTimeOffset> значение. Например, `ReturnTimeOnServer` метод в предыдущем примере можно переписывать следующим образом для <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> вызова метода.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>См. также

- <xref:System.TimeZoneInfo>
- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
