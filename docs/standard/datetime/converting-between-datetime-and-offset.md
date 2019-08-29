---
title: Взаимное преобразование структур DateTime и DateTimeOffset
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime structure, converting
- time zones [.NET Framework], conversions
- UTC times, converting
- DateTimeOffset structure, converting
- converting DateTimeOffset and DateTime values
- dates [.NET Framework], converting
- converting times
- Date data type, converting
- local time conversions
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb91ed8edd0c5cd3cb1d051157596f311718195d
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107068"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Взаимное преобразование структур DateTime и DateTimeOffset

Хотя структура обеспечивает большую степень осведомленности о часовых поясах, <xref:System.DateTime> чем структура, <xref:System.DateTime> параметры чаще используются в вызовах методов. <xref:System.DateTimeOffset> По этой причине возможность преобразования <xref:System.DateTimeOffset> значений в <xref:System.DateTime> значения и наоборот особенно важна. В этом разделе показано, как выполнять эти преобразования таким образом, чтобы сохранить как можно больше сведений о часовом поясе.

> [!NOTE]
> <xref:System.DateTime> Итипы,иимеютнекоторыеограниченияприпредставлениивремени<xref:System.DateTimeOffset> в часовых поясах. С его <xref:System.DateTime.Kind%2A> <xref:System.DateTime> свойством можно отражать только время в формате UTC и местный часовой пояс системы. <xref:System.DateTimeOffset>отражает смещение времени от времени в формате UTC, но не отражает фактический часовой пояс, к которому относится это смещение. Дополнительные сведения о значениях времени и поддержке часовых поясов см. в разделе [Выбор между DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Преобразование DateTime в DateTimeOffset

Структура предоставляет два эквивалентных способа <xref:System.DateTime> <xref:System.DateTimeOffset> преобразования, которые подходят для большинства преобразований: <xref:System.DateTimeOffset>

- Конструктор, который создает новый <xref:System.DateTimeOffset> объект на основе <xref:System.DateTime> значения. <xref:System.DateTimeOffset.%23ctor%2A>

- Оператор неявного преобразования, который позволяет присвоить <xref:System.DateTime> значение <xref:System.DateTimeOffset> объекту.

Для времени в формате <xref:System.DateTime> UTC и локальных <xref:System.DateTimeOffset.Offset%2A> значений свойство результирующего <xref:System.DateTimeOffset> значения точно отражает время UTC или смещение местного часового пояса. Например, следующий код преобразует время в формате UTC в эквивалентное <xref:System.DateTimeOffset> значение.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

В этом случае смещение переменной `utcTime2` равняется 00:00. Аналогичным образом следующий код преобразует местное время в эквивалентное <xref:System.DateTimeOffset> ему значение.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Однако для <xref:System.DateTime> значений, свойство <xref:System.DateTime.Kind%2A> которых равно <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, эти два метода преобразования создают <xref:System.DateTimeOffset> значение, смещение которого равно значению местного часового пояса. Это показано в приведенном ниже примере, который выполняется в тихоокеанском стандартном часовом поясе США.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Если значение отражает дату и время, отличные от местного часового пояса или времени в формате UTC, можно преобразовать его <xref:System.DateTimeOffset> в значение и сохранить сведения о часовом поясе, <xref:System.DateTimeOffset.%23ctor%2A> вызвав перегруженный конструктор. <xref:System.DateTime> Например, в следующем примере создается экземпляр <xref:System.DateTimeOffset> объекта, который отражает центральное стандартное время.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Второй параметр для перегруженной версии конструктора, <xref:System.TimeSpan> объект, представляющий смещение времени от UTC, должен быть получен путем <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> вызова метода соответствующего часового пояса. Единственным параметром метода является <xref:System.DateTime> значение, представляющее дату и время, которые необходимо преобразовать. Если часовой пояс поддерживает переход на летнее время, то этот параметр позволяет методу определять соответствующее смещение для конкретных даты и времени.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Преобразование DateTimeOffset в DateTime

Свойство чаще всего используется <xref:System.DateTimeOffset> <xref:System.DateTime> для преобразования. <xref:System.DateTimeOffset.DateTime%2A> Однако он возвращает <xref:System.DateTime> значение, свойство которого <xref:System.DateTime.Kind%2A> равно <xref:System.DateTimeKind.Unspecified>, как показано в следующем примере.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Это означает, что все сведения о <xref:System.DateTimeOffset> связи значения со временем в формате UTC теряются <xref:System.DateTimeOffset.DateTime%2A> при преобразовании при использовании свойства. Это влияет <xref:System.DateTimeOffset> на значения, которые соответствуют времени в формате UTC или по местному времени системы <xref:System.DateTimeOffset.DateTime%2A> , поскольку структура отражает только два часовых пояса в <xref:System.DateTime.Kind%2A> своем свойстве.

Чтобы сохранить как можно больше сведений о часовом поясе при <xref:System.DateTimeOffset> преобразовании <xref:System.DateTime> в значение <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> , можно использовать свойства и <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> .

### <a name="converting-a-utc-time"></a>Преобразование времени в формате UTC

Чтобы указать, что преобразованное <xref:System.DateTimeOffset.DateTime%2A> значение является временем в формате UTC, можно получить значение <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> свойства. Он отличается от <xref:System.DateTimeOffset.DateTime%2A> свойства двумя способами:

- Он возвращает <xref:System.DateTime> значение, свойство <xref:System.DateTime.Kind%2A> которого равно <xref:System.DateTimeKind.Utc>.

- <xref:System.TimeSpan.Zero?displayProperty=nameWithType>Если значение <xref:System.DateTimeOffset.Offset%2A> свойства не равно, оно преобразует время в формат UTC.

> [!NOTE]
> Если приложению <xref:System.DateTime> требуется, чтобы преобразованные значения однозначно определяли один момент времени, следует <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> использовать <xref:System.DateTime> свойство для управления всеми <xref:System.DateTimeOffset> преобразованиями.

В следующем коде <xref:System.DateTimeOffset.UtcDateTime%2A> свойство используется для <xref:System.DateTimeOffset> преобразования значения <xref:System.DateTime> , смещение которого равно <xref:System.TimeSpan.Zero?displayProperty=nameWithType> значению.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

В следующем коде <xref:System.DateTimeOffset.UtcDateTime%2A> свойство используется для выполнения преобразования часового пояса и преобразования типа <xref:System.DateTimeOffset> для значения.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Преобразование местного времени

Чтобы указать, что <xref:System.DateTimeOffset> значение представляет местное время, можно <xref:System.DateTime> передать значение, возвращаемое <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> свойством, `static` в метод (`Shared` в Visual Basic) <xref:System.DateTime.SpecifyKind%2A> . Метод возвращает дату и время, переданные в нее в качестве первого параметра, но устанавливает <xref:System.DateTime.Kind%2A> свойство в значение, заданное вторым параметром. В следующем коде <xref:System.DateTime.SpecifyKind%2A> метод используется при <xref:System.DateTimeOffset> преобразовании значения, смещение которого соответствует значению местного часового пояса.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

Можно также использовать <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойство для <xref:System.DateTimeOffset> преобразования значения в локальное <xref:System.DateTime> значение. Возвращаемым <xref:System.DateTime.Kind%2A> <xref:System.DateTime> значением является <xref:System.DateTimeKind.Local>свойство. В следующем коде <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойство используется при <xref:System.DateTimeOffset> преобразовании значения, смещение которого соответствует значению местного часового пояса. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

При <xref:System.DateTime> извлечении значения `get` <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> с помощью свойства метод доступа свойства сначала преобразует <xref:System.DateTimeOffset> значение в <xref:System.DateTimeOffset.ToLocalTime%2A> формат UTC, а затем преобразует его в местное время, вызвав метод. Это означает, что можно извлечь значение из <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойства, чтобы выполнить преобразование часового пояса одновременно с выполнением преобразования типов. Это также означает, что при выполнении преобразования применяются правила коррекции местного часового пояса. В следующем коде показано использование <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойства для выполнения преобразования типа и часового пояса.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Универсальный метод преобразования

В следующем примере определяется метод с именем `ConvertFromDateTimeOffset` , который <xref:System.DateTimeOffset> преобразует значения <xref:System.DateTime> в значения. В зависимости от его смещения он определяет, является <xref:System.DateTimeOffset> ли значение временем в формате UTC, местным временем или другим временем, и соответствующим образом определяет <xref:System.DateTime.Kind%2A> свойство возвращаемого значения даты и времени.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

В приведенном ниже примере `ConvertFromDateTimeOffset` вызывается метод <xref:System.DateTimeOffset> для преобразования значений, представляющих время в формате UTC, местное время и время в США. США.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Обратите внимание, что этот код делает два предположения, которые в зависимости от применения и источника значений даты и времени могут оказаться недопустимыми:

- Предполагается, что значение даты и времени, смещение <xref:System.TimeSpan.Zero?displayProperty=nameWithType> которого представляет время в формате UTC. На самом деле UTC не является временем в определенном часовом поясе, но оно является временем, по отношению к которому стандартизованы времена часовых поясов в мире. Часовые пояса также могут иметь смещение <xref:System.TimeSpan.Zero>.

- Предполагается, что значение даты и времени, смещение для которого равно смещению местного часового пояса, представляет местный часовой пояс. Поскольку значения даты и времени не связаны со своими исходными часовыми поясами, то это может не выполняться. Значение даты и времени может быть создано в другом часовом поясе с тем же самым смещением.

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
