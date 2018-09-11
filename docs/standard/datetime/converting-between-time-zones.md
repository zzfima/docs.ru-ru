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
ms.openlocfilehash: 0c77832a4c578ddb2c8a427b133e53ab4ab5c5e3
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44267301"
---
# <a name="converting-times-between-time-zones"></a>Преобразование времени из одного часового пояса в другой

Обработка различий между часовыми поясами становится все более важной для всех приложений, которые работают с датами и временем. Приложение больше не могут считать, что все значения времени могут быть выражены по местному времени, которое становится доступным время <xref:System.DateTime> структуры. Например, веб-страница, которая отображает текущее время в восточной части США, будет содержать недостоверные сведения для пользователей в восточной Азии. В этом разделе объясняется, как преобразовать время из одного часового пояса в другой, а также как преобразовать <xref:System.DateTimeOffset> значения с ограниченной поддержкой часовых поясов.

## <a name="converting-to-coordinated-universal-time"></a>Преобразование во время в формате UTC

Время в формате UTC — это высокоточный, атомарный стандарт времени. Часовые пояса выражаются как положительные или отрицательные смещения относительно времени в формате UTC. Таким образом, время в формате UTC предоставляет тип времени, свободного от часовых поясов, или нейтрального времени часового пояса. Использование времени в формате UTC рекомендовано, когда важна совместимость даты и времени между компьютерами. (Дополнительные сведения и рекомендации по использованию значения даты и времени, см. в разделе [кодирования рекомендации по использованию даты и времени в .NET Framework](https://msdn.microsoft.com/library/ms973825.aspx).) Преобразование отдельных часовых поясов во время в формате UTC упрощает сравнение времен.

> [!NOTE]
> Также можно сериализовать <xref:System.DateTimeOffset> структуры для однозначного представления одного момента времени. Так как <xref:System.DateTimeOffset> объекты хранят значение даты и времени вместе с его смещением относительно времени UTC, они всегда представляют определенный момент времени в связи в формат UTC.

Самым простым способом преобразования времени в формате UTC является вызов `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> метод. Точное преобразование, выполненное с помощью метода зависит от значения `dateTime` параметра <xref:System.DateTime.Kind%2A> свойства, как показано в следующей таблице.

| `DateTime.Kind`            | Преобразование                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Преобразует местное время во время в формате UTC.                                                    |
| `DateTimeKind.Unspecified` | Предполагает, что параметр `dateTime` является местным временем и преобразовывает местное время в UTC. |
| `DateTimeKind.Utc`         | Возвращает неизмененный параметр `dateTime`.                                    |

Следующий код преобразовывает текущее местное время во время в формате UTC и выводит результат на консоль.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

> [!NOTE]
> <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> Метод не обязательно возвращает результаты, которые совпадают с <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=nameWithType> и <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> методы. Если узел локальный часовой пояс содержит несколько правил коррекции, <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> применяет соответствующее правило для определенной даты и времени. Два других метода всегда применяют последнее правило коррекции.

Если значение даты и времени не представляет время в формате UTC или местное время <xref:System.DateTime.ToUniversalTime%2A> метод скорее всего вернет ошибочный результат. Тем не менее, можно использовать <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> метода для преобразования даты и времени из заданного часового пояса. (Дополнительные сведения о получении <xref:System.TimeZoneInfo> , представляющий часовой пояс назначения, см. в разделе [поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) В следующем коде используется <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> метод для преобразования восточного стандартного времени в формате UTC.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Обратите внимание, что этот метод вызывает исключение <xref:System.ArgumentException> Если <xref:System.DateTime> объекта <xref:System.DateTime.Kind%2A> свойство и часовой пояс совпадают. Несоответствие возникает, если <xref:System.DateTime.Kind%2A> свойство <xref:System.DateTimeKind.Local?displayProperty=nameWithType> , но <xref:System.TimeZoneInfo> объект не представляет местный часовой пояс, или если <xref:System.DateTime.Kind%2A> свойство <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> , но <xref:System.TimeZoneInfo> не равен <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>.

Все эти методы принимают <xref:System.DateTime> значения как параметры и возвращаемые <xref:System.DateTime> значение. Для <xref:System.DateTimeOffset> значения, <xref:System.DateTimeOffset> структура имеет <xref:System.DateTimeOffset.ToUniversalTime%2A> экземпляр метода, который преобразует дату и время текущего экземпляра в формате UTC. В следующем примере вызывается <xref:System.DateTimeOffset.ToUniversalTime%2A> метод для преобразования местного времени и нескольких других случаях по Гринвичу (UTC).

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Преобразование времени в формате UTC в заданный часовой пояс

Чтобы преобразовать время UTC в местное время, см. в следующем разделе «преобразование в местное время в формате UTC». Чтобы преобразовать время UTC во время в любой часовой пояс, который вы указываете, вызовите <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> метод. Этот метод принимает два параметра:

* Время в формате UTC, которое требуется преобразовать. Это должен быть <xref:System.DateTime> которого <xref:System.DateTime.Kind%2A> свойству `Unspecified` или `Utc`.

* Часовой пояс, в который требуется преобразовать время в формате UTC.

Следующий код преобразует время в формате UTC в центральное стандартное время.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Преобразование времени в формате UTC в местное время

Чтобы преобразовать время UTC в местное время, вызовите <xref:System.DateTime.ToLocalTime%2A> метод <xref:System.DateTime> , время которого требуется выполнить преобразование. Точное поведение метода зависит от значения объекта в <xref:System.DateTime.Kind%2A> свойства, как показано в следующей таблице.

| `DateTime.Kind`            | Преобразование                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Возвращает <xref:System.DateTime> значение без изменений.                                      |
| `DateTimeKind.Unspecified` | Предполагается, что <xref:System.DateTime> значение в формате UTC и преобразует UTC в местное время. |
| `DateTimeKind.Utc`         | Преобразует <xref:System.DateTime> значение в местное время.                                 |

> [!NOTE]
> <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> Метод ведет себя идентично `DateTime.ToLocalTime` метод. Он принимает один параметр, которое является значением даты и времени для преобразования.

Можно также преобразовать время в любой заданный часовой пояс в местное время с помощью `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> метод. Этот метод рассматривается в следующем разделе.

## <a name="converting-between-any-two-time-zones"></a>Преобразование между любыми двумя часовыми поясами

Можно осуществлять преобразование между любыми двумя часовыми поясами с помощью любого из следующих двух `static` (`Shared` в Visual Basic) методов <xref:System.TimeZoneInfo> класса:

* <xref:System.TimeZoneInfo.ConvertTime%2A>

  Параметрами этого метода являются значение даты и времени, для преобразования, `TimeZoneInfo` , представляющий часовой пояс значения даты и времени, и `TimeZoneInfo` объект, представляющий часовой пояс, чтобы преобразовать значение даты и времени.

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  Параметры этого метода являются дату и время, которое требуется преобразовать, идентификатор даты и времени значение часового пояса и идентификатор часового пояса преобразовать значение даты и времени.

Оба метода требуют <xref:System.DateTime.Kind%2A> свойство значения даты и времени для преобразования и <xref:System.TimeZoneInfo> объекта или идентификатору часового пояса, представляющего его часовой пояс соответствуют друг с другом. В противном случае возникает исключение <xref:System.ArgumentException>. Например если `Kind` свойство значения даты и времени — `DateTimeKind.Local`, исключение возникает в том случае, если `TimeZoneInfo` объект, переданный как параметр методу не равно `TimeZoneInfo.Local`. Исключение вызывается также в том случае, если идентификатор, переданный как параметр метода не равно `TimeZoneInfo.Local.Id`.

В следующем примере используется <xref:System.TimeZoneInfo.ConvertTime%2A> метод для преобразования из гавайского стандартного времени в местное время.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Преобразование значений DateTimeOffset

Значения даты и времени, представленного <xref:System.DateTimeOffset> объекты не являются полностью часового пояса поясам, так как объект отсоединяется от его часовым поясом во время создания его экземпляра. Однако во многих случаях приложению достаточно преобразовать дату и время на основе двух различных значений смещения относительно времени в формате UTC, а не на основе времени конкретных часовых поясов. Чтобы выполнить это преобразование, можно вызвать текущего экземпляра <xref:System.DateTimeOffset.ToOffset%2A> метод. Единственным параметром данного метода — это смещение нового значения даты и времени, метод для возврата.

Например, если дата и время запроса пользователя к веб-странице известны и сериализованы в виде строки в формате мм/дд/гггг чч:мм:сс zzzz, то следующий метод `ReturnTimeOnServer` преобразует это значение даты и времени в значение даты и времени на веб-сервере.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

Если методу передается строка "9/1/2007 5:32:07 -05:00", которая представляет дату и время в часовом поясе, который раньше пояса UTC на пять часов, он возвращает строку "9/1/2007 3:32:07 -07:00" для сервера, расположенного в тихоокеанском стандартном часовом поясе США.

<xref:System.TimeZoneInfo> Класс также включает перегрузку <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> метод, который выполняет преобразование часовых поясов со <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> значения. Параметрами данного метода являются <xref:System.DateTimeOffset> и ссылка на часовой пояс, к которому будет преобразовать время. Этот метод возвращает <xref:System.DateTimeOffset> значение. Например `ReturnTimeOnServer` метод в предыдущем примере можно переписать следующим образом для вызова <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> метод.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>См. также

* <xref:System.TimeZoneInfo>
* [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
* [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
