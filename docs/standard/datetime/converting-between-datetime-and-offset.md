---
title: "Взаимное преобразование структур DateTime и DateTimeOffset | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "преобразование значений DateTimeOffset и DateTime"
  - "преобразование времени"
  - "Date - тип данных, преобразование"
  - "даты [платформа .NET Framework], преобразование"
  - "DateTime - структура, преобразование"
  - "DateTimeOffset - структура, преобразование"
  - "преобразование локального времени"
  - "часовые пояса [платформа .NET Framework], преобразования"
  - "время в формате UTC, преобразование"
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Взаимное преобразование структур DateTime и DateTimeOffset
Хотя структура <xref:System.DateTimeOffset> обеспечивает лучшую поддержку часовых поясов, чем структура <xref:System.DateTime>, параметры <xref:System.DateTime> чаще используются в вызовах методов.  Таким образом возможность преобразования значений <xref:System.DateTimeOffset> в значения <xref:System.DateTime> и наоборот играет особенно важную роль.  В этом разделе показано, как выполнять эти преобразования таким образом, чтобы сохранять как можно больше сведений о часовом поясе.  
  
> [!NOTE]
>  Типы <xref:System.DateTime> и <xref:System.DateTimeOffset> имеют некоторые ограничения при представлении времени в часовых поясах.  Благодаря свойству <xref:System.DateTime.Kind%2A> объект <xref:System.DateTime> может автоматически устанавливать только время в формате UTC и время в местном часовом поясе системы.  <xref:System.DateTimeOffset> автоматически устанавливает смещение времени от времени UTC, но не устанавливает фактический часовой пояс, к которому относится это смещение.  Дополнительные сведения о значениях времени и поддержке часовых поясов см. в разделе [Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).  
  
## Преобразование DateTime в DateTimeOffset  
 Структура <xref:System.DateTimeOffset> предоставляет два равнозначных способа выполнения преобразования <xref:System.DateTime> в <xref:System.DateTimeOffset>, которые подходят для большинства преобразований:  
  
-   Конструктор <xref:System.DateTimeOffset.%23ctor%2A>, который создает новый объект <xref:System.DateTimeOffset> на основе значения <xref:System.DateTime>.  
  
-   Оператор неявного преобразования, позволяющий назначить значение <xref:System.DateTime> объекту <xref:System.DateTimeOffset>.  
  
 Для времени UTC и местных значений <xref:System.DateTime>, свойство <xref:System.DateTimeOffset.Offset%2A> результирующего значения <xref:System.DateTimeOffset> точно отражает время UTC или смещение местного часового пояса.  Например, следующий код преобразует время UTC в эквивалентное значение <xref:System.DateTimeOffset>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]  
  
 В этом случае смещение переменной `utcTime2` равняется 00:00.  Аналогичным образом следующий код преобразует местное время в эквивалентное значение <xref:System.DateTimeOffset>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]  
  
 Однако для значений <xref:System.DateTime>, свойство <xref:System.DateTime.Kind%2A> которых имеет значение <xref:System.DateTimeKind?displayProperty=fullName>, эти два метода преобразования возвращают значение <xref:System.DateTimeOffset>, смещением которого является смещение этого часового пояса.  Это показано в приведенном ниже примере, который выполняется в тихоокеанском стандартном часовом поясе США.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]  
  
 Если значение <xref:System.DateTime> отражает дату и время в часовом поясе, отличном от местного часового пояса или от UTC, то можно преобразовать его в значение <xref:System.DateTimeOffset> и сохранить сведения о его часовом поясе, вызвав перегруженный конструктор <xref:System.DateTimeOffset.%23ctor%2A>.  Например, в следующем примере создается экземпляр <xref:System.DateTimeOffset>, который отражает центральное стандартное время.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]  
  
 Вторым параметром в этом перегруженном конструкторе является объект <xref:System.TimeSpan>, представляющий смещение времени от UTC, который должен быть извлечен посредством вызова метода <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=fullName> соответствующего часового пояса.  Единственным параметром данного метода является значение <xref:System.DateTime>, представляющее дату и время, которые требуется преобразовать.  Если часовой пояс поддерживает переход на летнее время, то этот параметр позволяет методу определять соответствующее смещение для конкретных даты и времени.  
  
## Преобразование DateTimeOffset в DateTime  
 Свойство <xref:System.DateTimeOffset.DateTime%2A> чаще всего используется для выполнения преобразования <xref:System.DateTimeOffset> в <xref:System.DateTime>.  Тем не менее, оно возвращает значение <xref:System.DateTime>, свойством <xref:System.DateTime.Kind%2A> которого является <xref:System.DateTimeKind>, как показано в следующем примере.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]  
  
 Это означает, что все сведения о связи значения <xref:System.DateTimeOffset> с UTC будут потеряны при преобразовании, когда используется свойство <xref:System.DateTimeOffset.DateTime%2A>.  Это влияет на значения <xref:System.DateTimeOffset>, которые соответствуют времени UTC или локальному времени системы, так как структура <xref:System.DateTimeOffset.DateTime%2A> отражает только эти два часовых пояса в свойстве <xref:System.DateTime.Kind%2A>.  
  
 Чтобы сохранить как можно больше сведений о часовом поясе при преобразовании <xref:System.DateTimeOffset> в значение <xref:System.DateTime>, можно использовать свойства <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName> и <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName>.  
  
### Преобразование времени UTC  
 Чтобы указать, что преобразуемое значение <xref:System.DateTimeOffset.DateTime%2A> является временем UTC, можно получить значение свойства <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName>.  Оно отличается от свойства <xref:System.DateTimeOffset.DateTime%2A> двумя особенностями:  
  
-   Оно возвращает значение <xref:System.DateTime>, свойством <xref:System.DateTime.Kind%2A> которого является <xref:System.DateTimeKind>.  
  
-   Если значение свойства <xref:System.DateTimeOffset.Offset%2A> не равно <xref:System.TimeSpan.Zero?displayProperty=fullName>, то оно преобразуется во время UTC.  
  
> [!NOTE]
>  Если для приложения необходимо, чтобы преобразованные значения <xref:System.DateTime> однозначно идентифицировали единственный момент времени, то следует использовать свойство <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName> для обработки всех преобразований из <xref:System.DateTimeOffset> в <xref:System.DateTime>.  
  
 Следующий код использует свойство <xref:System.DateTimeOffset.UtcDateTime%2A> для преобразования значения <xref:System.DateTimeOffset>, смещение которого равно <xref:System.TimeSpan.Zero?displayProperty=fullName>, в значение <xref:System.DateTime>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]  
  
 Следующий код использует свойство <xref:System.DateTimeOffset.UtcDateTime%2A> для преобразования часового пояса и преобразования типов значения <xref:System.DateTimeOffset>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]  
  
### Преобразование локального времени  
 Чтобы указать, что значение <xref:System.DateTimeOffset> представляет локальное время, можно передать значение <xref:System.DateTime>, возвращенное свойством <xref:System.DateTimeOffset.DateTime%2A?displayProperty=fullName> в метод `static` \(`Shared` в Visual Basic\) <xref:System.DateTime.SpecifyKind%2A>.  Этот метод возвращает дату и время, переданные ему в качестве первого параметра, но устанавливает для свойства <xref:System.DateTime.Kind%2A> значение, указанное ему в качестве второго параметра.  В следующем коде используется метод <xref:System.DateTime.SpecifyKind%2A> при преобразовании значения <xref:System.DateTimeOffset>, смещение которого соответствует смещению местного часового пояса.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]  
  
 Также можно использовать свойство <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> для преобразования значения <xref:System.DateTimeOffset> к локальному значению <xref:System.DateTime>.  Свойством <xref:System.DateTime.Kind%2A> возвращаемого значения <xref:System.DateTime> является <xref:System.DateTimeKind>.  В следующем коде используется свойство <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> при преобразовании значения <xref:System.DateTimeOffset>, смещение которого соответствует смещению местного часового пояса.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]  
  
 При извлечении значения <xref:System.DateTime> с помощью свойства <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> метод доступа `get` свойства сначала преобразует значение <xref:System.DateTimeOffset> в UTC, а затем преобразует его в локальное время посредством вызова метода <xref:System.DateTimeOffset.ToLocalTime%2A>.  Это означает, что вы можете получить значение свойства <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> для выполнения преобразования в момент выполнения преобразования типов.  Это также означает, что при выполнении преобразования применяются правила коррекции местного часового пояса.  Следующий код иллюстрирует использование свойства <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> для выполнения преобразования и типа, и часового пояса.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]  
  
### Метод преобразования общего назначения  
 В следующем примере определяется метод с именем `ConvertFromDateTimeOffset`, который преобразует значения <xref:System.DateTimeOffset> в значения <xref:System.DateTime>.  В зависимости от смещения, он определяет является ли значение <xref:System.DateTimeOffset> временем UTC, локальным временем или другим временем, и соответствующим образом определяет свойство <xref:System.DateTime.Kind%2A> возвращаемого значения даты и времени.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]  
  
 В следующем примере вызывается метод `ConvertFromDateTimeOffset` для преобразования значений <xref:System.DateTimeOffset>, представляющих время UTC, местное время и время центрального стандартного часового пояса США.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]  
  
 Обратите внимание, что этот код делает два предположения, которые в зависимости от применения и источника значений даты и времени могут оказаться недопустимыми:  
  
-   Предполагается, что значение даты и времени, смещение которого равно <xref:System.TimeSpan.Zero?displayProperty=fullName>, представляет время UTC.  На самом деле UTC не является временем в определенном часовом поясе, но оно является временем, по отношению к которому стандартизованы времена часовых поясов в мире.  Часовые пояса также могут иметь смещение <xref:System.TimeSpan.Zero>.  
  
-   Предполагается, что значение даты и времени, смещение для которого равно смещению местного часового пояса, представляет местный часовой пояс.  Поскольку значения даты и времени не связаны со своими исходными часовыми поясами, то это может не выполняться. Значение даты и времени может быть создано в другом часовом поясе с тем же самым смещением.  
  
## См. также  
 [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)