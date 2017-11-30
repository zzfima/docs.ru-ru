---
title: "Практическое руководство. Обеспечение однозначности при сохранении и восстановлении значений даты и времени"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- round-trip date and time values
- dates [.NET Framework], round-trip values
- time zones [.NET Framework], round-trip date and time values
- time [.NET Framework], round-trip values
- formatting strings [.NET Framework], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 515a29e279cfa8fc100e0612fc19df7abc6a3b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-trip-date-and-time-values"></a>Практическое руководство. Обеспечение однозначности при сохранении и восстановлении значений даты и времени
Во многих приложениях значение даты и времени предназначено для однозначного определения одного момента времени. В этом разделе показано, как сохранять и восстанавливать <xref:System.DateTime> значение <xref:System.DateTimeOffset> значение и значение даты и времени с временем информации о зоне, чтобы восстановленное значение определяет то же время, что и сохраненное значение.  
  
### <a name="to-round-trip-a-datetime-value"></a>Выполнение цикла обработки значения DateTime  
  
1.  Преобразовать <xref:System.DateTime> значение в строковое представление, вызвав <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> метод с помощью описателя формата «o».  
  
2.  Сохраните строковое представление <xref:System.DateTime> в файл или передайте его между процессами, домен приложения или между компьютерами.  
  
3.  Получить строку, представляющую <xref:System.DateTime> значение.  
  
4.  Вызовите <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> и передайте <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> в качестве значения `styles` параметра.  
  
 Следующий пример иллюстрирует способ обратного преобразования <xref:System.DateTime> значение.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 При полной совместимости версий <xref:System.DateTime> значение, этот метод успешно сохраняет время локального и универсального времени. Например, если локальный <xref:System.DateTime> значение сохраняется в системе в США. тихоокеанском стандартном часовом поясе США и восстановлено в системе в центральном стандартном часовом поясе США, восстановленные дата и время будут на два часа больше исходного времени, что отражает разницу во времени между двумя часовыми поясами. Однако этот способ не всегда точен для неуказанного времени. Все <xref:System.DateTime> значения которого <xref:System.DateTime.Kind%2A> свойство <xref:System.DateTimeKind.Unspecified> обрабатываются, как если бы они были местного времени. Если это не так, <xref:System.DateTime> не будет успешно определять нужный момент времени. Чтобы устранить это ограничение, нужно тесно связать значение даты и времени с его часовым поясом для операций сохранения и восстановления.  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a>Выполнение цикла обработки значения DateTimeOffset  
  
1.  Преобразовать <xref:System.DateTimeOffset> значение в строковое представление, вызвав <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> метод с помощью описателя формата «o».  
  
2.  Сохраните строковое представление <xref:System.DateTimeOffset> в файл или передайте его между процессами, домен приложения или между компьютерами.  
  
3.  Получить строку, представляющую <xref:System.DateTimeOffset> значение.  
  
4.  Вызовите <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> и передайте <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> в качестве значения `styles` параметра.  
  
 Следующий пример иллюстрирует способ обратного преобразования <xref:System.DateTimeOffset> значение.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 Этот метод всегда однозначно идентифицирует <xref:System.DateTimeOffset> значение как единственный момент времени. Значение затем может быть преобразован в формате UTC, вызвав <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> метод, или его можно преобразовать во время в заданном часовом поясе, вызвав <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> или <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> метод. Основным ограничением этого метода является эту дату и время арифметические операции, при выполнении <xref:System.DateTimeOffset> значение, представляющее время в заданном часовом поясе, может возвратить неточные результаты для этого часового пояса. Это, поскольку при <xref:System.DateTimeOffset> создается значение, он отсоединяется от его часовым поясом. Таким образом, правила коррекции часового пояса не могут быть больше применены при выполнении вычислений с датами и временем. Можно обойти эту проблему, определив пользовательский тип, который содержит значение даты и времени с его соответствующим часовым поясом.  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a>Для обратного преобразования даты и времени значение с его часовым поясом  
  
1.  Определите класс или структуру с двумя полями. Первое поле имеет либо <xref:System.DateTime> или <xref:System.DateTimeOffset> , а второй — <xref:System.TimeZoneInfo> объекта. Следующий пример является простой версией такого типа.  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  Пометить класс с <xref:System.SerializableAttribute> атрибута.  
  
3.  Сериализация объекта с использованием <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> метод.  
  
4.  Восстановите объект с помощью <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> метод.  
  
5.  Приведите (в C#) или преобразуйте (в Visual Basic) Десериализованный объект к объекту соответствующего типа.  
  
 В следующем примере показано, как цикл обработки объекта, сохраняет сведения о дате и времени и часового пояса.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 Этот метод всегда должен однозначно отражать правильной точки времени оба до и после его сохранения и восстановления, что реализация комбинированный объект даты и времени и часового пояса не разрешают значения даты, будут синхронизироваться с значение часового пояса.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этих примеров требуются:  
  
-   Что импортируются следующие пространства имен с помощью C# `using` инструкций или [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` инструкции:  
  
    -   <xref:System>(Только C#).  
  
    -   <xref:System.Globalization?displayProperty=nameWithType>.  
  
    -   <xref:System.IO?displayProperty=nameWithType>.  
  
    -   <xref:System.Runtime.Serialization?displayProperty=nameWithType>.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.  
  
-   Ссылка на библиотеку System.Core.dll.  
  
-   Каждый пример кода, отличный от `DateInTimeZone` класса, должны включены в класс или модуль Visual Basic, упакован в методы и вызывать из `Main` метод.  
  
## <a name="see-also"></a>См. также  
 [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
