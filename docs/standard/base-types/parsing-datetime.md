---
title: "Анализ строк даты и времени в .NET Framework | Microsoft Docs"
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
  - "базовые типы, разбор строк"
  - "строки даты и времени"
  - "DateTime - объект"
  - "перечисления [платформа .NET Framework], разбор строк"
  - "ParseExact - метод"
  - "разбор строк, строки даты и времени"
  - "строки времени"
ms.assetid: 43bae51e-9b1d-41a6-a187-772c0d096d90
caps.latest.revision: 24
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 24
---
# Анализ строк даты и времени в .NET Framework
Методы синтаксического анализа преобразовывают строковое представление даты и времени в эквивалентный объект <xref:System.DateTime>.  Методы <xref:System.DateTime.Parse%2A> и <xref:System.DateTime.TryParse%2A> преобразовывают любое из нескольких общих представлений даты и времени.  Методы <xref:System.DateTime.ParseExact%2A> и <xref:System.DateTime.TryParseExact%2A> преобразуют строковое представление, соответствующее шаблону, заданному строкой формата даты и времени. \(См. разделы, посвященные [строкам стандартного формата даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) и [строкам настраиваемого формата даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).\)  
  
 На синтаксический анализ влияют свойства поставщика формата, который предоставляет такие сведения как строки, используемые для разделителей даты и времени, обозначения месяцев, дней и периодов.  Поставщик формата является текущим объектом <xref:System.Globalization.DateTimeFormatInfo>, неявно предоставляемый языком и региональными параметрами текущего потока или явно заданный параметром <xref:System.IFormatProvider> метода разбора.  Для параметра <xref:System.IFormatProvider> укажите объект <xref:System.Globalization.CultureInfo>, представляющий язык и региональные параметры, или объект <xref:System.Globalization.DateTimeFormatInfo>.  
  
 Для выполнения синтаксического анализа строковое представление даты должно содержать месяц и, по крайней мере, день или год.  Строковое представление времени должно содержать часы и, по крайней мере, минуты или обозначение AM\/PM.  Однако при разборе опущенных компонентов для них указываются значения по умолчанию, если это возможно.  Опущенная дата по умолчанию становится текущей датой, опущенный год по умолчанию становится текущим годом, опущенный день месяца по умолчанию становится первым днем месяца, а опущенное время по умолчанию задается как полночь.  
  
 Если строковое представление указывает только время, то при разборе возвращается объект <xref:System.DateTime> с его свойствами <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A>, которым присвоены соответствующие значения свойства <xref:System.DateTime.Today%2A>.  Тем не менее, если константа <xref:System.Globalization.DateTimeStyles> указана в методе разбора, то свойствам год, месяц и день присваиваются значения `1`.  
  
 Помимо компонента даты и времени строковое представление даты и времени может содержать смещение, которое указывает на сколько время отличается от универсального синхронизированного времени \(UTC\).  Например, строка "14\/02\/2007 5:32:00 \-7: 00" определяет время, которое на семь часов меньше чем UTC.  Если смещение не задано в строковом представлении времени, то при разборе возвращается объект <xref:System.DateTime> со значением свойства <xref:System.DateTime.Kind%2A> заданным как <xref:System.DateTimeKind?displayProperty=fullName>.  Если смещение задано, то при разборе возвращается объект <xref:System.DateTime> со значением свойства <xref:System.DateTime.Kind%2A>, заданным как <xref:System.DateTimeKind>, а его значение настраивается на местный часовой пояс компьютера.  Такое поведение можно изменить, используя константу <xref:System.Globalization.DateTimeStyles> вместе с методом разбора.  
  
 Поставщик формата также используется для интерпретации неоднозначных числовых дат.  Например, не ясно какие компоненты даты в строке "02\/03\/04" соответствуют месяцу, дню и году.  В этом случае компоненты интерпретируются согласно их порядку расположения в схожих форматах даты в поставщике формата.  
  
## Разбор  
 В следующем примере кода показано использование метода **Parse** для преобразования строки в **DateTime**.  В этом примере для разбора используется язык и региональные параметры, связанные с текущим потоком.  Если <xref:System.Globalization.CultureInfo>, связанному с текущими языком и региональными параметрами, не удается выполнить синтаксический анализ входной строки, то создается исключение <xref:System.FormatException>.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 Также можно задать **CultureInfo** один из языков и региональных параметров, определяемых этим объектом, или можно указать один из стандартных объектов <xref:System.Globalization.DateTimeFormatInfo>, возвращаемый свойством <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>.  В следующем примере кода поставщик формата используется для разбора строки на немецком языке в **DateTime**.  Для обеспечения успешного разбора строки, **CultureInfo**, представляющий немецкий язык и региональные параметры \(de\-DE\), определен и передан вместе с разбираемой строкой.  Это устраняет необходимость задания каких\-либо параметров в **CurrentCulture** потока **CurrentThread**.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 Хотя можно использовать перегрузки метода <xref:System.DateTime.Parse%2A> для задания поставщиков пользовательских форматов, такой метод не поддерживает использование поставщиков нестандартных форматов.  Для разбора даты и времени, выраженного в нестандартном формате, используйте метод <xref:System.DateTime.ParseExact%2A>.  
  
 В следующем примере кода используется перечисление <xref:System.Globalization.DateTimeStyles> для того, чтобы указать, что в **DateTime** не требуется возвращать текущие дату и время для полей, не определенных в строке.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## Метод ParseExact  
 Метод <xref:System.DateTime.ParseExact%2A?displayProperty=fullName> преобразует строку, которая соответствует указанному шаблону, в объект **DateTime**.  Когда этому методу передается строка, не соответствующая указанному шаблону, то создается исключение <xref:System.FormatException>.  Можно задать один из стандартных спецификаторов формата даты и времени или ограниченное сочетание пользовательских спецификаторов формата для даты и времени.  При использовании пользовательских спецификаторов формата можно сконструировать пользовательскую строку распознавания.  Сведения об описателях см. в разделах, посвященных [строкам стандартного формата даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) и [строкам настраиваемого формата даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 Каждая перегрузка метода <xref:System.DateTime.ParseExact%2A> также имеет параметр <xref:System.IFormatProvider>, который, как правило, при форматировании строк предоставляет сведения о языке и региональных параметрах.  Как правило, этот объект <xref:System.IFormatProvider> является объектом <xref:System.Globalization.CultureInfo>, который представляет стандартные язык и региональные параметры, или объект <xref:System.Globalization.DateTimeFormatInfo>, возвращаемый свойством <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>.  Однако в отличие от других функций разбора даты и времени, этот метод также поддерживает <xref:System.IFormatProvider>, который определяет нестандартный формат даты и времени.  
  
 В следующем примере кода методу **ParseExact** передается предназначенный для разбора строковый объект, затем передается спецификатор формата, стоящий перед объектом **CultureInfo**.  Этот метод **ParseExact** может выполнять разбор строк только с шаблоном длинной даты на американском английском \(en\-US\) языке.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## См. также  
 [Разбор строк](../../../docs/standard/base-types/parsing-strings.md)   
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)   
 [Преобразование типов в .NET Framework](../../../docs/standard/base-types/type-conversion.md)