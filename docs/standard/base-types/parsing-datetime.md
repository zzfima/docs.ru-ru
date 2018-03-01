---
title: "Анализ строк даты и времени в .NET Framework"
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
- parsing strings, date and time strings
- date and time strings
- ParseExact method
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- DateTime object
- time strings
ms.assetid: 43bae51e-9b1d-41a6-a187-772c0d096d90
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6e3ef01abdb615b2850b5a9d07e1208ee22eda95
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>Синтаксический анализ строк даты и времени в .NET
Методы синтаксического анализа позволяют преобразовать строковое представление даты и времени в эквивалентный объект <xref:System.DateTime>. Методы <xref:System.DateTime.Parse%2A> и <xref:System.DateTime.TryParse%2A> позволяют преобразовать любое из нескольких стандартных представлений даты и времени. Методы <xref:System.DateTime.ParseExact%2A>и <xref:System.DateTime.TryParseExact%2A> позволяют преобразовать строковое представление, соответствующее шаблону, указанному в строке формата даты и времени. (См. разделы [Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) и [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).)  
  
 На синтаксический анализ влияют свойства поставщика формата, который предоставляет такие сведения, как строки, используемые для разделителей даты и времени, обозначения месяцев, дней и периодов. Поставщиком формата является текущий объект <xref:System.Globalization.DateTimeFormatInfo>, который неявно предоставляется значением языка и региональных параметров текущего потока или явно установлен в параметре <xref:System.IFormatProvider> для метода синтаксического анализа. Для параметра <xref:System.IFormatProvider> следует указать объект <xref:System.Globalization.CultureInfo>, представляющий язык и региональные параметры, или объект <xref:System.Globalization.DateTimeFormatInfo>.  
  
 Для выполнения синтаксического анализа строковое представление даты должно содержать месяц и, по крайней мере, день или год. Строковое представление времени должно содержать часы и, по крайней мере, минуты или обозначение AM/PM. Однако при разборе опущенных компонентов для них указываются значения по умолчанию, если это возможно. Отсутствующая дата по умолчанию становится текущей датой, отсутствующий год по умолчанию становится текущим годом, отсутствующий день месяца по умолчанию становится первым днем месяца, а отсутствующие время по умолчанию задается как полночь.  
  
 Если строковое представление указывает только время, то синтаксический анализ возвращает объект <xref:System.DateTime>, свойства <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> и <xref:System.DateTime.Day%2A> которого получают значения из свойства <xref:System.DateTime.Today%2A>. Но если в методе синтаксического анализа указана константа <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault>, то свойства года, месяца и дня получают значение `1`.  
  
 Помимо компонента даты и времени строковое представление даты и времени может содержать смещение, которое указывает, насколько время отличается от универсального синхронизированного времени (UTC). Например, строка "14/02/2007 5:32:00 -7: 00" определяет время, которое на семь часов меньше, чем UTC. Если в строковом представлении времени не задано смещение, то синтаксический анализ возвращает объект <xref:System.DateTime>, свойство <xref:System.DateTime.Kind%2A> которого имеет значение <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>. Если смещение задано, то синтаксический анализ возвращает объект <xref:System.DateTime>, свойство <xref:System.DateTime.Kind%2A> которого имеет значение <xref:System.DateTimeKind.Local> и значение которого установлено с учетом местного часового пояса компьютера. Это поведение можно изменить, указав для метода синтаксического анализа константу <xref:System.Globalization.DateTimeStyles>.  
  
 Поставщик формата также используется для интерпретации неоднозначных числовых дат. Например, неясно, какие компоненты даты в строке "02/03/04" соответствуют месяцу, дню и году. В этом случае компоненты интерпретируются согласно их порядку расположения в схожих форматах даты в поставщике формата.  
  
## <a name="parse"></a>Parse  
 Следующий пример кода демонстрирует использование метода **Parse** для преобразования строки в значение **DateTime**. В этом примере для разбора используется язык и региональные параметры, связанные с текущим потоком. Если класс <xref:System.Globalization.CultureInfo>, связанный с текущим значением языка и региональных параметров, не может выполнить синтаксический анализ исходной строки, создается исключение <xref:System.FormatException>.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 Вы также можете указать **CultureInfo** с одним из значений языка и региональных параметров, определенных в этом объекте, или указать один из стандартных объектов <xref:System.Globalization.DateTimeFormatInfo>, возвращаемых свойством <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. Следующий пример кода использует поставщик формата для преобразования строки на немецком языке в значение **DateTime**. Чтобы гарантировать правильный анализ строки, мы создаем объект **CultureInfo**, представляющий немецкий язык и региональные параметры (de-DE), и передаем его с анализируемой строкой. Так мы исключаем из рассмотрения все настройки **CurrentCulture** для текущего потока (**CurrentThread**).  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 Для указания поставщиков пользовательских форматов можно использовать перегрузки метода <xref:System.DateTime.Parse%2A>. Но такой метод не позволяет применить поставщиков нестандартных форматов. Вместо этого используйте метод <xref:System.DateTime.ParseExact%2A> для анализа даты и времени, выраженных в нестандартном формате.  
  
 В следующем примере кода перечисление <xref:System.Globalization.DateTimeStyles> указывает, что текущие значения даты и времени не нужно добавлять в поля **DateTime**, не определенные в строке.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 Метод <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> позволяет преобразовать строку, которая соответствует указанному шаблону строки, в объект **DateTime**. Если в этот метод передается строка, не соответствующая указанному шаблону, создается исключение <xref:System.FormatException>. Можно задать один из стандартных описателей формата даты и времени или ограниченное сочетание пользовательских описателей формата для даты и времени. При использовании пользовательских описателей формата можно сконструировать пользовательскую строку распознавания. Сведения об описателях см. в разделах [Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) и [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 Каждая перегрузка метода <xref:System.DateTime.ParseExact%2A> также имеет параметр <xref:System.IFormatProvider>, который обычно предоставляет сведения о языке и региональных параметрах для форматирования строки. Как правило, этот объект <xref:System.IFormatProvider> является объектом <xref:System.Globalization.CultureInfo>, который представляет стандартный язык и региональные параметры, или объектом <xref:System.Globalization.DateTimeFormatInfo>, возвращаемым в свойстве <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. Но в отличие от других функций синтаксического анализа даты и времени, этот метод также поддерживает <xref:System.IFormatProvider>, который определяет нестандартный формат даты и времени.  
  
 В следующем примере кода в метод **ParseExact** передается переназначенный для анализа строковый объект, за которым следуют описатель формата и объект **CultureInfo**. Этот метод **ParseExact** можно использовать только для анализа строк, соответствующих шаблону полной даты по стандарту американского английского языка (en-US).  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>См. также  
 [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)  
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)  
 [Преобразование типов в .NET](../../../docs/standard/base-types/type-conversion.md)
