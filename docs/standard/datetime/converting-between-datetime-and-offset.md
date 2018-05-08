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
ms.openlocfilehash: dec0e5138ecf08783f11d21cd28d7291d27ea68d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Взаимное преобразование структур DateTime и DateTimeOffset

Несмотря на то что <xref:System.DateTimeOffset> структура обеспечивает более высокую степень сведения о часовом поясе, чем <xref:System.DateTime> структуры <xref:System.DateTime> параметры наиболее часто используются в вызовах метода. По этой причине возможность преобразования <xref:System.DateTimeOffset> значения <xref:System.DateTime> значениям и наоборот особенно важен. В этом разделе показано, как выполнять эти преобразования таким образом, чтобы сохранять столько сведения о часовом поясе, насколько это возможно.

> [!NOTE]
> Как <xref:System.DateTime> и <xref:System.DateTimeOffset> типы имеют некоторые ограничения при представлении времени в часовых поясах. С его <xref:System.DateTime.Kind%2A> свойства <xref:System.DateTime> может отражают только по Гринвичу (UTC) и местный часовой пояс компьютера. <xref:System.DateTimeOffset> отражает смещение времени от времени UTC, но не отражает фактическое часовой пояс, к которому, смещение относится. Дополнительные сведения о значениях времени и поддержке часовых поясов см. в разделе [Choosing Between DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Преобразование DateTime в DateTimeOffset

<xref:System.DateTimeOffset> Структура предоставляет два равнозначных способа выполнения <xref:System.DateTime> для <xref:System.DateTimeOffset> преобразования, которые подходят для большинства преобразований:

* <xref:System.DateTimeOffset.%23ctor%2A> Конструктор, который создает новую <xref:System.DateTimeOffset> объекта, основанного на <xref:System.DateTime> значение.

* Оператор неявного преобразования, который позволяет связать <xref:System.DateTime> значение <xref:System.DateTimeOffset> объекта.

Для времени UTC и местных <xref:System.DateTime> значения, <xref:System.DateTimeOffset.Offset%2A> результирующего <xref:System.DateTimeOffset> значение точно отражает смещение пояса UTC или местного времени. Например, следующий код преобразует время в формате UTC в его эквивалент <xref:System.DateTimeOffset> значение.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

В этом случае смещение переменной `utcTime2` равняется 00:00. Аналогичным образом, следующий код преобразует местного времени в его эквивалент <xref:System.DateTimeOffset> значение.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Однако для <xref:System.DateTime> значения которого <xref:System.DateTime.Kind%2A> свойство <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, эти два метода преобразования возвращают <xref:System.DateTimeOffset> которого является смещение для местного часового пояса. Это показано в приведенном ниже примере, который выполняется в тихоокеанском стандартном часовом поясе США.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Если <xref:System.DateTime> значение отражает дату и время в нечто, отличное от местного часового пояса или в формате UTC, то можно преобразовать в <xref:System.DateTimeOffset> и сохранить его данные часового пояса путем вызова перегруженных <xref:System.DateTimeOffset.%23ctor%2A> конструктор. Например, в следующем примере создается <xref:System.DateTimeOffset> объект, который отражает центральное стандартное время.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Второй параметр этой перегрузки конструктора <xref:System.TimeSpan> , представляющий смещение по времени от времени UTC, должны быть получены путем вызова <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> метод время соответствующего часового пояса. Единственным параметром метода является <xref:System.DateTime> значение, представляющее дату и время для преобразования. Если часовой пояс поддерживает переход на летнее время, то этот параметр позволяет методу определять соответствующее смещение для конкретных даты и времени.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Преобразование DateTimeOffset в DateTime

<xref:System.DateTimeOffset.DateTime%2A> Свойство чаще всего используется для выполнения <xref:System.DateTimeOffset> для <xref:System.DateTime> преобразования. Тем не менее, она возвращает <xref:System.DateTime> которого <xref:System.DateTime.Kind%2A> свойство <xref:System.DateTimeKind.Unspecified>, как показано в следующем примере.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Это означает, что все сведения о <xref:System.DateTimeOffset> связь этого значения в формат UTC будут потеряны при преобразовании при <xref:System.DateTimeOffset.DateTime%2A> используется свойство. Это влияет на <xref:System.DateTimeOffset> значения, которые соответствуют времени UTC или местного времени компьютера, так как <xref:System.DateTimeOffset.DateTime%2A> структура отражает только этих двух часовых поясов в его <xref:System.DateTime.Kind%2A> свойство.

Для сохранения столько сведения о часовом поясе, насколько это возможно, при преобразовании <xref:System.DateTimeOffset> для <xref:System.DateTime> значения, можно использовать <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> и <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойства.

### <a name="converting-a-utc-time"></a>Преобразование времени UTC

Чтобы указать, что преобразуемое <xref:System.DateTimeOffset.DateTime%2A> значение в формате UTC, можно извлечь значение <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> свойства. Она отличается от <xref:System.DateTimeOffset.DateTime%2A> свойство двумя способами:

* Он возвращает <xref:System.DateTime> которого <xref:System.DateTime.Kind%2A> свойство <xref:System.DateTimeKind.Utc>.

* Если <xref:System.DateTimeOffset.Offset%2A> значение свойства не равно <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, он преобразует время в формате UTC.

> [!NOTE]
> Если приложения необходимо, чтобы преобразовать <xref:System.DateTime> значения однозначно идентифицирует единственный момент времени, следует рассмотреть возможность использования <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> свойства для обработки всех <xref:System.DateTimeOffset> для <xref:System.DateTime> преобразования.

В следующем коде используется <xref:System.DateTimeOffset.UtcDateTime%2A> свойство для преобразования <xref:System.DateTimeOffset> значение которого равно смещению <xref:System.TimeSpan.Zero?displayProperty=nameWithType> для <xref:System.DateTime> значение.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

В следующем коде используется <xref:System.DateTimeOffset.UtcDateTime%2A> свойство для преобразования и преобразования типов на <xref:System.DateTimeOffset> значение.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Преобразование локального времени

Чтобы указать, что <xref:System.DateTimeOffset> значение представляет собой местное время, можно передать <xref:System.DateTime> значения, возвращенного <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> свойства `static` (`Shared` в Visual Basic) <xref:System.DateTime.SpecifyKind%2A> метод. Метод возвращает дату и время, переданного в качестве первого параметра, но задает <xref:System.DateTime.Kind%2A> свойство для значения, указанного в его втором параметре. В следующем коде используется <xref:System.DateTime.SpecifyKind%2A> метод при преобразовании <xref:System.DateTimeOffset> значение смещение которого соответствует смещению местного часового пояса.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

Можно также использовать <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойство для преобразования <xref:System.DateTimeOffset> к локальному <xref:System.DateTime> значение. <xref:System.DateTime.Kind%2A> Свойство возвращаемого <xref:System.DateTime> значение <xref:System.DateTimeKind.Local>. В следующем коде используется <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойство при преобразовании <xref:System.DateTimeOffset> значение смещение которого соответствует смещению местного часового пояса. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

При извлечении <xref:System.DateTime> с использованием <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойство, свойство `get` доступа сначала преобразует <xref:System.DateTimeOffset> значение в формате UTC, затем преобразует его в местное время, вызвав <xref:System.DateTimeOffset.ToLocalTime%2A> метод. Это означает, что можно получить значение из <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойства для выполнения преобразования в то же время выполнения преобразования типов. Это также означает, что при выполнении преобразования применяются правила коррекции местного часового пояса. Следующий код иллюстрирует использование <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойства для выполнения тип и преобразования.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Метод преобразования общего назначения

В следующем примере определяется метод с именем `ConvertFromDateTimeOffset` , преобразующий <xref:System.DateTimeOffset> значения <xref:System.DateTime> значения. На основании его смещение, определяет ли <xref:System.DateTimeOffset> значение время в формате UTC, местное время или другое время и определяет возвращаемый даты и времени значение <xref:System.DateTime.Kind%2A> свойства соответствующим образом.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

В следующем примере вызывается `ConvertFromDateTimeOffset` метод преобразования <xref:System.DateTimeOffset> значения, представляющие время в формате UTC в местное время и время в США США.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Обратите внимание, что этот код делает два предположения, которые в зависимости от применения и источника значений даты и времени могут оказаться недопустимыми:

* Предполагается, что значения которого смещение даты и времени <xref:System.TimeSpan.Zero?displayProperty=nameWithType> представляет время UTC. На самом деле UTC не является временем в определенном часовом поясе, но оно является временем, по отношению к которому стандартизованы времена часовых поясов в мире. Часовые пояса также может иметь смещение <xref:System.TimeSpan.Zero>.

* Предполагается, что значение даты и времени, смещение для которого равно смещению местного часового пояса, представляет местный часовой пояс. Поскольку значения даты и времени не связаны со своими исходными часовыми поясами, то это может не выполняться. Значение даты и времени может быть создано в другом часовом поясе с тем же самым смещением.

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
