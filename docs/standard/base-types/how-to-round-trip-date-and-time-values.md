---
title: "Практическое руководство. Обеспечение однозначности при сохранении и восстановлении значений даты и времени | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "значения даты и времени кругового пути"
  - "даты [платформа .NET Framework], значения кругового пути"
  - "часовые пояса [платформа .NET Framework], значения даты и времени кругового пути"
  - "время [платформа .NET Framework], значения кругового пути"
  - "строки форматирования [платформа .NET Framework], значения кругового пути"
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Обеспечение однозначности при сохранении и восстановлении значений даты и времени
Во многих приложениях значение даты и времени предназначено для однозначного определения одного момента времени.  В этом разделе демонстрируется сохранение и восстановление значения <xref:System.DateTime>, значения <xref:System.DateTimeOffset> и значения даты и времени с данными о часовом поясе таким образом, чтобы восстановленное значение определяло то же самое время, что и сохраненное значение.  
  
### Выполнение цикла обработки значения DataTime  
  
1.  Преобразуйте значение <xref:System.DateTime> в строковое представление посредством вызова метода <xref:System.DateTime.ToString%28System.String%29?displayProperty=fullName> со спецификатором формата "o".  
  
2.  Сохраните строковое представление значения <xref:System.DateTime> в файл или передайте его между процессами, доменами приложений или между компьютерами.  
  
3.  Получите строку, представляющую значение <xref:System.DateTime>.  
  
4.  Вызовите метод <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=fullName> и передайте <xref:System.Globalization.DateTimeStyles?displayProperty=fullName> в качестве значения параметра `styles`.  
  
 В следующем примере показано, как выполнить цикл обработки значения <xref:System.DateTime>.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 Во время цикла обработки значения <xref:System.DateTime> этот метод успешно сохраняет время для всех значений локального и универсального времени.  Например, если локальное значение <xref:System.DateTime> сохранено в системе в тихоокеанском стандартном часовом поясе США и восстановлено в системе в центральном стандартном часовом поясе США, то извлеченные дата и время будут на два часа больше исходного времени, что отражает разницу во времени между часовыми поясами в два часа.  Однако этот способ не всегда точен для неуказанного времени.  Любое значение <xref:System.DateTime>, свойством <xref:System.DateTime.Kind%2A> которого является <xref:System.DateTimeKind>, рассматривается как локальное время.  Если это не так, то <xref:System.DateTime> не будет успешно определять корректный момент времени.  Чтобы устранить это ограничение, нужно тесно связать значение даты и времени с его часовым поясом для операций сохранения и восстановления.  
  
### Выполнение цикла обработки значения DataTimeOffset  
  
1.  Преобразуйте значение <xref:System.DateTimeOffset> в строковое представление посредством вызова метода <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=fullName> со спецификатором формата "o".  
  
2.  Сохраните строковое представление значения <xref:System.DateTimeOffset> в файл или передайте его между процессами, доменами приложений или между компьютерами.  
  
3.  Получите строку, представляющую значение <xref:System.DateTimeOffset>.  
  
4.  Вызовите метод <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=fullName> и передайте <xref:System.Globalization.DateTimeStyles?displayProperty=fullName> в качестве значения параметра `styles`.  
  
 В следующем примере показано, как выполнить цикл обработки значения <xref:System.DateTimeOffset>.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 Этот метод всегда однозначно идентифицирует значение <xref:System.DateTimeOffset> как единственный момент времени.  Значение затем может быть преобразовано в универсальное синхронизированное время \(UTC\) посредством вызова метода <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=fullName>. Также может быть преобразовано во время в конкретном часовом поясе посредством вызова метода <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=fullName> или метода <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName>.  Основным ограничением этого способа являются арифметические действия с датами и временем, которые при выполнении их над значением <xref:System.DateTimeOffset>, представляющим время в определенном часовом поясе, могут возвратить неточные результаты для этого часового пояса.  Это происходит потому, что при создании значения <xref:System.DateTimeOffset> оно не связано со своим часовым поясом.  Таким образом, правила коррекции часового пояса не могут быть больше применены при выполнении вычислений с датами и временем.  Можно обойти эту проблему, определив пользовательский тип, который содержит значение даты и времени с его соответствующим часовым поясом.  
  
### Выполнение цикла обработки значения даты и времени вместе с его часовым поясом  
  
1.  Определите класс или структуру с двумя полями.  Первым полем является объект <xref:System.DateTime> или <xref:System.DateTimeOffset>, а вторым — объект <xref:System.TimeZoneInfo>.  Следующий пример является простой версией такого типа.  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  Пометьте класс атрибутом <xref:System.SerializableAttribute>.  
  
3.  Сериализуйте объект с помощью метода <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>.  
  
4.  Восстановите объект с помощью метода <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>.  
  
5.  Приведите \(в C\#\) или преобразуйте \(в Visual Basic\) десериализованный объект к объекту соответствующего типа.  
  
 В следующем примере показан цикл обработки объекта, который хранит дату и время вместе с данными часового пояса.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 Этот способ всегда должен однозначно отражать корректный момент времени до и после его сохранения и восстановления. Предоставленная реализация объединенных значения даты и времени и часового пояса не допускает рассинхронизации значения даты со значением часового пояса.  
  
## Компиляция кода  
 Для выполнения данных примеров требуются следующие компоненты:  
  
-   Чтобы следующие пространства имен были импортированы с помощью операторов C\# `using` или операторов [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports`:  
  
    -   <xref:System> \(только C\#\).  
  
    -   <xref:System.Globalization?displayProperty=fullName>.  
  
    -   <xref:System.IO?displayProperty=fullName>.  
  
    -   <xref:System.Runtime.Serialization?displayProperty=fullName>.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=fullName>.  
  
-   Ссылка на System.Core.dll.  
  
-   Каждый пример кода, отличный от класса `DateInTimeZone`, должен быть включен в класс или модуль Visual Basic, упакован в методы и должен вызываться из метода `Main`.  
  
## См. также  
 [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)   
 [Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)