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
ms.openlocfilehash: fbb59dbe364763209f44a4e2241d1d5275036c40
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156027"
---
# <a name="converting-times-between-time-zones"></a>Преобразование времени из одного часового пояса в другой

Обработка различий между часовыми поясами становится все более важной для всех приложений, которые работают с датами и временем. Приложение больше не может считать, что все значения времени могут быть выражены в местном времени, что является временем, доступным в структуре <xref:System.DateTime>. Например, веб-страница, которая отображает текущее время в восточной части США, будет содержать недостоверные сведения для пользователей в восточной Азии. В этом разделе объясняется, как преобразовать время из одного часового пояса в другой, а также как преобразовать значения <xref:System.DateTimeOffset> с ограниченной поддержкой часовых поясов.

## <a name="converting-to-coordinated-universal-time"></a>Преобразование во время в формате UTC

Время в формате UTC — это высокоточный, атомарный стандарт времени. Часовые пояса выражаются как положительные или отрицательные смещения относительно времени в формате UTC. Таким образом, время в формате UTC предоставляет тип времени, свободного от часовых поясов, или нейтрального времени часового пояса. Использование времени в формате UTC рекомендовано, когда важна совместимость даты и времени между компьютерами. (Дополнительные сведения и другие рекомендации по датам и времени см. [в разделе Создание кода рекомендаций с использованием DateTime в .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973825(v=msdn.10)).) Преобразование отдельных часовых поясов в формат UTC упрощает сравнение времени.

> [!NOTE]
> Можно также сериализовать структуру <xref:System.DateTimeOffset>, чтобы однозначно представить один момент времени. Поскольку <xref:System.DateTimeOffset> объекты хранят значение даты и времени вместе со смещением относительно времени в формате UTC, они всегда представляют определенный момент времени в связи с временем в формате UTC.

Самый простой способ преобразовать время в формат UTC — вызвать метод `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType>. Точное преобразование, выполняемое методом, зависит от значения свойства <xref:System.DateTime.Kind%2A> параметра `dateTime`, как показано в следующей таблице.

| `DateTime.Kind`            | Преобразование                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Преобразует местное время во время в формате UTC.                                                    |
| `DateTimeKind.Unspecified` | Предполагает, что параметр `dateTime` является местным временем и преобразовывает местное время в UTC. |
| `DateTimeKind.Utc`         | Возвращает неизмененный параметр `dateTime`.                                    |

Следующий код преобразовывает текущее местное время во время в формате UTC и выводит результат на консоль.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

Если значение даты и времени не представляет местное время или UTC, то <xref:System.DateTime.ToUniversalTime%2A> метод, скорее всего, вернет ошибочный результат. Однако можно использовать метод <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> для преобразования даты и времени из указанного часового пояса. (Дополнительные сведения о получении объекта <xref:System.TimeZoneInfo>, представляющего часовой пояс назначения, см. в разделе [Поиск часовых поясов, определенных в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) В следующем коде используется метод <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> для преобразования восточного стандартного времени в формат UTC.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Обратите внимание, что этот метод создает исключение <xref:System.ArgumentException>, если свойство <xref:System.DateTime.Kind%2A> объекта <xref:System.DateTime> и часовой пояс не совпадают. Несоответствие возникает, если свойство <xref:System.DateTime.Kind%2A> <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, но объект <xref:System.TimeZoneInfo> не представляет местный часовой пояс, или если свойство <xref:System.DateTime.Kind%2A> имеет значение <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, но объект <xref:System.TimeZoneInfo> не равен <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>.

Все эти методы принимают <xref:System.DateTime> значения в качестве параметров и возвращают значение <xref:System.DateTime>. Для <xref:System.DateTimeOffset> значений структура <xref:System.DateTimeOffset> содержит метод <xref:System.DateTimeOffset.ToUniversalTime%2A> экземпляра, который преобразует дату и время текущего экземпляра в формат UTC. В следующем примере вызывается метод <xref:System.DateTimeOffset.ToUniversalTime%2A> для преобразования местного времени и нескольких других значений времени в формат UTC.

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Преобразование времени в формате UTC в заданный часовой пояс

Для преобразования времени в формате UTC в местное время см. следующий раздел "преобразование времени UTC в местное время". Для преобразования времени в формате UTC во время в любом часовом поясе вызовите метод <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>. Этот метод принимает два параметра:

- Время в формате UTC, которое требуется преобразовать. Это должно быть <xref:System.DateTime> значение, для свойства <xref:System.DateTime.Kind%2A> которого установлено значение `Unspecified` или `Utc`.

- Часовой пояс, в который требуется преобразовать время в формате UTC.

Следующий код преобразует время в формате UTC в центральное стандартное время.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Преобразование времени в формате UTC в местное время

Для преобразования времени в формате UTC в местное время вызовите метод <xref:System.DateTime.ToLocalTime%2A> объекта <xref:System.DateTime>, время которого нужно преобразовать. Точное поведение метода зависит от значения свойства <xref:System.DateTime.Kind%2A> объекта, как показано в следующей таблице.

| `DateTime.Kind`            | Преобразование                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Возвращает неизмененное значение <xref:System.DateTime>.                                      |
| `DateTimeKind.Unspecified` | Предполагается, что <xref:System.DateTime> значение равно UTC и преобразует UTC в местное время. |
| `DateTimeKind.Utc`         | Преобразует значение <xref:System.DateTime> в местное время.                                 |

> [!NOTE]
> Метод <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> ведет себя идентично методу `DateTime.ToLocalTime`. Он принимает один параметр, который представляет собой значение даты и времени для преобразования.

Можно также преобразовать время в любом заданном часовом поясе в местное время с помощью метода <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> `static` (`Shared` в Visual Basic). Этот метод рассматривается в следующем разделе.

## <a name="converting-between-any-two-time-zones"></a>Преобразование между любыми двумя часовыми поясами

Преобразование между любыми двумя часовыми поясами можно выполнить с помощью любого из следующих двух методов `static` (`Shared` в Visual Basic) класса <xref:System.TimeZoneInfo>:

- <xref:System.TimeZoneInfo.ConvertTime%2A>

  Параметры этого метода — это значение даты и времени для преобразования, объект `TimeZoneInfo`, представляющий часовой пояс значения даты и времени, и объект `TimeZoneInfo`, представляющий часовой пояс для преобразования значения даты и времени в.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  Параметры этого метода — это значение даты и времени для преобразования, идентификатор часового пояса значения даты и времени и идентификатор часового пояса, в который необходимо преобразовать значение даты и времени.

Для обоих методов требуется, чтобы свойство <xref:System.DateTime.Kind%2A> значения даты и времени было преобразовано, а объект <xref:System.TimeZoneInfo> или идентификатор часового пояса, представляющий его часовой пояс, соответствовал друг другу. В противном случае возникает исключение <xref:System.ArgumentException>. Например, если свойство `Kind` значения даты и времени имеет `DateTimeKind.Local`, исключение возникает, если объект `TimeZoneInfo`, переданный в качестве параметра в метод, не равен `TimeZoneInfo.Local`. Исключение также создается, если идентификатор, переданный в качестве параметра в метод, не равен `TimeZoneInfo.Local.Id`.

В следующем примере используется метод <xref:System.TimeZoneInfo.ConvertTime%2A> для преобразования из Гавайского стандартного времени в местное время.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Преобразование значений DateTimeOffset

Значения даты и времени, представленные <xref:System.DateTimeOffset> объектами, не имеют полной осведомленности о часовых поясах, так как объект не связан с часовым поясом во время создания экземпляра. Однако во многих случаях приложению достаточно преобразовать дату и время на основе двух различных значений смещения относительно времени в формате UTC, а не на основе времени конкретных часовых поясов. Чтобы выполнить это преобразование, можно вызвать метод <xref:System.DateTimeOffset.ToOffset%2A> текущего экземпляра. Единственным параметром метода является смещение нового значения даты и времени, возвращаемого методом.

Например, если дата и время запроса пользователя к веб-странице известны и сериализованы в виде строки в формате мм/дд/гггг чч:мм:сс zzzz, то следующий метод `ReturnTimeOnServer` преобразует это значение даты и времени в значение даты и времени на веб-сервере.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)]

Если методу передается строка "9/1/2007 5:32:07 -05:00", которая представляет дату и время в часовом поясе, который раньше пояса UTC на пять часов, он возвращает строку "9/1/2007 3:32:07 -07:00" для сервера, расположенного в тихоокеанском стандартном часовом поясе США.

Класс <xref:System.TimeZoneInfo> также включает перегрузку метода <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>, который выполняет преобразование часовых поясов с <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> значениями. Параметры метода являются <xref:System.DateTimeOffset> значением и ссылкой на часовой пояс, к которому необходимо преобразовать время. Вызов метода возвращает значение <xref:System.DateTimeOffset>. Например, метод `ReturnTimeOnServer` в предыдущем примере можно переписывать следующим образом для вызова метода <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29>.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>См. также раздел

- <xref:System.TimeZoneInfo>
- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
