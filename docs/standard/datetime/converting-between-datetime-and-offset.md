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
ms.openlocfilehash: 428553f75db2cca6705ac72873e86e120e94d134
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132594"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Взаимное преобразование структур DateTime и DateTimeOffset

Хотя структура <xref:System.DateTimeOffset> предоставляет большую степень осведомленности о часовых поясах, чем структура <xref:System.DateTime>, <xref:System.DateTime> параметры используются чаще в вызовах методов. По этой причине возможность преобразования значений <xref:System.DateTimeOffset> в <xref:System.DateTime> значения и наоборот особенно важна. В этом разделе показано, как выполнять эти преобразования таким образом, чтобы сохранить как можно больше сведений о часовом поясе.

> [!NOTE]
> Типы <xref:System.DateTime> и <xref:System.DateTimeOffset> имеют некоторые ограничения при представлении времени в часовых поясах. Со свойством <xref:System.DateTime.Kind%2A> <xref:System.DateTime> может отражать только время в формате UTC и местный часовой пояс системы. <xref:System.DateTimeOffset> отражает смещение времени от времени в формате UTC, но не отражает фактический часовой пояс, к которому относится это смещение. Дополнительные сведения о значениях времени и поддержке часовых поясов см. в разделе [Выбор между DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Преобразование DateTime в DateTimeOffset

Структура <xref:System.DateTimeOffset> предоставляет два эквивалентных способа выполнения <xref:System.DateTime> для <xref:System.DateTimeOffset> преобразования, которые подходят для большинства преобразований:

- Конструктор <xref:System.DateTimeOffset.%23ctor%2A>, который создает новый объект <xref:System.DateTimeOffset> на основе значения <xref:System.DateTime>.

- Оператор неявного преобразования, который позволяет присвоить <xref:System.DateTime>ное значение объекту <xref:System.DateTimeOffset>.

Для значений времени в формате UTC и локальных <xref:System.DateTime> значение свойства <xref:System.DateTimeOffset.Offset%2A> результирующего <xref:System.DateTimeOffset> точно отражает время UTC или смещение местного часового пояса. Например, следующий код преобразует время в формате UTC в эквивалентное <xref:System.DateTimeOffset> значение.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

В этом случае смещение переменной `utcTime2` равняется 00:00. Аналогичным образом следующий код преобразует местное время в эквивалентное <xref:System.DateTimeOffset> значение.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Однако для <xref:System.DateTime> значений, свойство <xref:System.DateTime.Kind%2A> которых <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, эти два метода преобразования создают значение <xref:System.DateTimeOffset>, смещение которого равно значению местного часового пояса. Это показано в следующем примере, который выполняется в тихоокеанском стандартном часовом поясе США.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Если <xref:System.DateTime> значение отражает дату и время, отличные от местного часового пояса или времени в формате UTC, можно преобразовать его в значение <xref:System.DateTimeOffset> и сохранить сведения о часовом поясе, вызвав перегруженный конструктор <xref:System.DateTimeOffset.%23ctor%2A>. Например, в следующем примере создается экземпляр объекта <xref:System.DateTimeOffset>, который отражает центральное стандартное время.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Второй параметр для перегруженной версии конструктора, объект <xref:System.TimeSpan>, представляющий смещение времени от UTC, должен быть получен путем вызова метода <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> соответствующего часового пояса. Единственным параметром метода является <xref:System.DateTime> значение, представляющее дату и время, которые необходимо преобразовать. Если часовой пояс поддерживает переход на летнее время, то этот параметр позволяет методу определять соответствующее смещение для конкретных даты и времени.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Преобразование DateTimeOffset в DateTime

Свойство <xref:System.DateTimeOffset.DateTime%2A> чаще всего используется для выполнения <xref:System.DateTimeOffset> <xref:System.DateTime> преобразования. Однако он возвращает <xref:System.DateTime> значение, свойством <xref:System.DateTime.Kind%2A> которого является <xref:System.DateTimeKind.Unspecified>, как показано в следующем примере.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Это означает, что при использовании свойства <xref:System.DateTimeOffset.DateTime%2A> все сведения о связи <xref:System.DateTimeOffset>ного значения с временем в формате UTC теряются. Это влияет на <xref:System.DateTimeOffset> значений, соответствующих времени в формате UTC или по местному времени системы, поскольку структура <xref:System.DateTimeOffset.DateTime%2A> отражает только два часовых пояса в своем свойстве <xref:System.DateTime.Kind%2A>.

Чтобы сохранить как можно больше сведений о часовом поясе при преобразовании <xref:System.DateTimeOffset> в <xref:System.DateTime> значение, можно использовать свойства <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> и <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>.

### <a name="converting-a-utc-time"></a>Преобразование времени в формате UTC

Чтобы указать, что преобразованное значение <xref:System.DateTimeOffset.DateTime%2A> является временем в формате UTC, можно получить значение свойства <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType>. Он отличается от свойства <xref:System.DateTimeOffset.DateTime%2A> двумя способами:

- Он возвращает <xref:System.DateTime> значение, свойство <xref:System.DateTime.Kind%2A> которого равно <xref:System.DateTimeKind.Utc>.

- Если значение свойства <xref:System.DateTimeOffset.Offset%2A> не равно <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, оно преобразует время в формат UTC.

> [!NOTE]
> Если приложению требуется, чтобы преобразованные <xref:System.DateTime>ные значения однозначно определяли один момент времени, следует рассмотреть возможность использования свойства <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> для управления всеми <xref:System.DateTimeOffset> <xref:System.DateTime> преобразований.

В следующем коде свойство <xref:System.DateTimeOffset.UtcDateTime%2A> используется для преобразования значения <xref:System.DateTimeOffset>, смещение которого равно <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, в значение <xref:System.DateTime>.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

В следующем коде используется свойство <xref:System.DateTimeOffset.UtcDateTime%2A> для выполнения преобразования часового пояса и преобразования типа для значения <xref:System.DateTimeOffset>.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Преобразование местного времени

Чтобы указать, что <xref:System.DateTimeOffset> значение представляет местное время, можно передать значение <xref:System.DateTime>, возвращаемое свойством <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType>, в метод`Shared` `static` (Visual Basic <xref:System.DateTime.SpecifyKind%2A>). Метод возвращает дату и время, переданные в нее в качестве первого параметра, но устанавливает свойство <xref:System.DateTime.Kind%2A> в значение, заданное вторым параметром. В следующем коде используется метод <xref:System.DateTime.SpecifyKind%2A> при преобразовании значения <xref:System.DateTimeOffset>, смещение которого соответствует значению местного часового пояса.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

Можно также использовать свойство <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> для преобразования значения <xref:System.DateTimeOffset> в локальное значение <xref:System.DateTime>. Свойство <xref:System.DateTime.Kind%2A> возвращаемого значения <xref:System.DateTime> имеет значение <xref:System.DateTimeKind.Local>. В следующем коде используется свойство <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> при преобразовании значения <xref:System.DateTimeOffset>, смещение которого соответствует значению местного часового пояса. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

При получении <xref:System.DateTime> значения с помощью свойства <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> метод доступа `get` свойства сначала преобразует значение <xref:System.DateTimeOffset> в формат UTC, а затем преобразует его в местное время, вызвав метод <xref:System.DateTimeOffset.ToLocalTime%2A>. Это означает, что можно извлечь значение из свойства <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>, чтобы выполнить преобразование часового пояса одновременно с выполнением преобразования типов. Это также означает, что при выполнении преобразования применяются правила коррекции местного часового пояса. В следующем коде показано использование свойства <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> для выполнения преобразования типа и часового пояса.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Универсальный метод преобразования

В следующем примере определяется метод с именем `ConvertFromDateTimeOffset`, который преобразует <xref:System.DateTimeOffset> значения в значения <xref:System.DateTime>. Основываясь на смещении, он определяет, является ли <xref:System.DateTimeOffset> значением временем в формате UTC, местным временем или другим временем, и соответствующим образом определяет свойство <xref:System.DateTime.Kind%2A> возвращаемого значения даты и времени.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

В следующем примере вызывается метод `ConvertFromDateTimeOffset` для преобразования значений <xref:System.DateTimeOffset>, представляющих время в формате UTC, местное время и время центрального стандартного часового пояса США.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Обратите внимание, что этот код делает два предположения, которые в зависимости от применения и источника значений даты и времени могут оказаться недопустимыми:

- Предполагается, что значение даты и времени, смещение которого равно <xref:System.TimeSpan.Zero?displayProperty=nameWithType> представляет время в формате UTC. На самом деле UTC не является временем в определенном часовом поясе, но оно является временем, по отношению к которому стандартизованы времена часовых поясов в мире. Часовые пояса также могут иметь смещение <xref:System.TimeSpan.Zero>.

- Предполагается, что значение даты и времени, смещение для которого равно смещению местного часового пояса, представляет местный часовой пояс. Поскольку значения даты и времени не связаны со своими исходными часовыми поясами, то это может не выполняться. Значение даты и времени может быть создано в другом часовом поясе с тем же самым смещением.

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
