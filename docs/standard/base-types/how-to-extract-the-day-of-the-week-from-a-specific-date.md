---
title: "Практическое руководство. Извлечение дня недели из конкретной даты | Microsoft Docs"
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
  - "форматирование [платформа .NET Framework], даты"
  - "DateTime.DayOfWeek - свойство"
  - "DateTime.ToString - метод"
  - "даты [платформа .NET Framework], извлечение сведений о неделе"
  - "DateTimeOffset.DayOfWeek - свойство"
  - "даты [платформа .NET Framework], день недели"
  - "Weekday - функция"
  - "день недели [платформа .NET Framework]"
  - "извлечение дня недели"
  - "названия дней недели"
  - "WeekdayName - функция"
  - "числа [платформа .NET Framework], день недели"
  - "форматирование [платформа .NET Framework], время"
  - "DateTimeOffset.ToString - метод"
  - "полные названия дней недели"
ms.assetid: 1c9bef76-5634-46cf-b91c-9b9eb72091d7
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Извлечение дня недели из конкретной даты
Платформа .NET Framework упрощает определение дня недели и отображение локализованного дня для определенной даты. Значение перечисления, которое указывает день недели, соответствующий определенной дате, можно получить из свойства <xref:System.DateTime.DayOfWeek%2A> или <xref:System.DateTimeOffset.DayOfWeek%2A>. Напротив, получение названия дня недели — это операция форматирования, которую можно выполнить с помощью метода форматирования, например метода `ToString` значения даты и времени или метода <xref:System.String.Format%2A?displayProperty=fullName>. В этом разделе показано, как выполнить эти операции форматирования.  
  
### Извлечение числа, обозначающего день недели, из определенной даты  
  
1.  Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа <xref:System.DateTime> или <xref:System.DateTimeOffset>, используя статичный метод <xref:System.DateTime.Parse%2A?displayProperty=fullName> или <xref:System.DateTimeOffset.Parse%2A?displayProperty=fullName>.  
  
2.  Используйте свойство <xref:System.DateTime.DayOfWeek%2A?displayProperty=fullName> или <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=fullName> для получения значения типа <xref:System.DayOfWeek>, которое указывает день недели.  
  
3.  При необходимости приведите \(в C\#\) или преобразуйте \(в Visual Basic\) значение <xref:System.DayOfWeek> в целочисленный тип.  
  
 Следующий пример отображает целое число, представляющее день недели для определенной даты.  
  
 [!code-csharp[Formatting.Howto.WeekdayName#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/weekdaynumber7.cs#7)]
 [!code-vb[Formatting.Howto.WeekdayName#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/weekdaynumber7.vb#7)]  
  
### Извлечение сокращенного названия дня недели из определенной даты  
  
1.  Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа <xref:System.DateTime> или <xref:System.DateTimeOffset>, используя статичный метод <xref:System.DateTime.Parse%2A?displayProperty=fullName> или <xref:System.DateTimeOffset.Parse%2A?displayProperty=fullName>.  
  
2.  Вы можете извлечь сокращенное название дня недели для текущих или заданных региональных параметров:  
  
    1.  Чтобы извлечь сокращенное название дня недели для текущих региональных параметров, вызовите метод <xref:System.DateTime.ToString%28System.String%29?displayProperty=fullName> значения даты и времени или метод экземпляра <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=fullName> и передайте строку "ddd" в параметре `format`. В следующем примере показано использование метода <xref:System.DateTime.ToString%28System.String%29>.  
  
         [!code-csharp[Formatting.Howto.WeekdayName#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname1.cs#1)]
         [!code-vb[Formatting.Howto.WeekdayName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname1.vb#1)]  
  
    2.  Чтобы извлечь сокращенное название дня недели для заданных региональных параметров, вызовите метод <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName> значения даты и времени или метод экземпляра <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName>. Передайте строку "ddd" в параметре `format`. Передайте объект <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.DateTimeFormatInfo>, представляющий региональные параметры, для которых требуется получить название дня недели, в параметре `provider`. В следующем коде показан вызов метода <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> с использованием объекта <xref:System.Globalization.CultureInfo>, представляющего региональные параметры fr\-FR.  
  
         [!code-csharp[Formatting.Howto.WeekdayName#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname2.cs#2)]
         [!code-vb[Formatting.Howto.WeekdayName#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname2.vb#2)]  
  
### Извлечение полного названия дня недели из определенной даты  
  
1.  Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа <xref:System.DateTime> или <xref:System.DateTimeOffset>, используя статичный метод <xref:System.DateTime.Parse%2A?displayProperty=fullName> или <xref:System.DateTimeOffset.Parse%2A?displayProperty=fullName>.  
  
2.  Вы можете извлечь полное название дня недели для текущих или заданных региональных параметров:  
  
    1.  Чтобы извлечь полное название дня недели для текущих региональных параметров, вызовите метод <xref:System.DateTime.ToString%28System.String%29?displayProperty=fullName> значения даты и времени или метод экземпляра <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=fullName> и передайте строку "dddd" в параметре `format`. В следующем примере показано использование метода <xref:System.DateTime.ToString%28System.String%29>.  
  
         [!code-csharp[Formatting.Howto.WeekdayName#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname4.cs#4)]
         [!code-vb[Formatting.Howto.WeekdayName#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname4.vb#4)]  
  
    2.  Чтобы извлечь полное название дня недели для заданных региональных параметров, вызовите метод <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName> значения даты и времени или метод экземпляра <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName>. Передайте строку "dddd" в параметре `format`. Передайте объект <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.DateTimeFormatInfo>, представляющий региональные параметры, для которых требуется получить название дня недели, в параметре `provider`. В следующем коде показан вызов метода <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> с использованием объекта <xref:System.Globalization.CultureInfo>, представляющего региональные параметры es\-ES.  
  
         [!code-csharp[Formatting.Howto.WeekdayName#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname5.cs#5)]
         [!code-vb[Formatting.Howto.WeekdayName#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname5.vb#5)]  
  
## Пример  
 В этом примере показаны вызовы свойств <xref:System.DateTime.DayOfWeek%2A?displayProperty=fullName> и <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=fullName>, а также методов <xref:System.DateTime.ToString%2A?displayProperty=fullName> и <xref:System.DateTimeOffset.ToString%2A?displayProperty=fullName> для получения числа, представляющего день недели, сокращенное и полное название дня недели для определенной даты.  
  
 [!code-csharp[Formatting.Howto.WeekdayName#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/example6.cs#6)]
 [!code-vb[Formatting.Howto.WeekdayName#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example6.vb#6)]  
  
 Отдельные языки могут предоставлять возможности, дублирующие или дополняющие функции [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Например, Visual Basic предоставляет две такие функции:  
  
-   `Weekday`, которая возвращает число, обозначающее день недели для определенной даты. Функция считает порядковое значение первого дня недели равным 1, а свойство <xref:System.DateTime.DayOfWeek%2A?displayProperty=fullName> — равным 0.  
  
-   `WeekdayName`, которая возвращает название дня недели для текущих региональных параметров, которое соответствует определенному номеру дня недели.  
  
 В следующем примере показано использование функций `Weekday` и `WeekdayName` Visual Basic.  
  
 [!code-vb[Formatting.HowTo.WeekdayName#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example9.vb#9)]  
  
 Вы также можете использовать значение, возвращенное свойством <xref:System.DateTime.DayOfWeek%2A?displayProperty=fullName>, для получения названия дня недели для определенной даты. Для этого требуется просто вызвать метод <xref:System.Enum.ToString%2A> для значения <xref:System.DayOfWeek>, возвращенного свойством. Однако этот способ не позволяет получить локализованное название дня недели для текущих региональных параметров, как показано в следующем примере.  
  
 [!code-csharp[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/Howto1.cs#8)]
 [!code-vb[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/Howto1.vb#8)]  
  
## См. также  
 [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)   
 [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)