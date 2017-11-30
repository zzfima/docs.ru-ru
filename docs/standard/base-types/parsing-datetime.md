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
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1beceb2b2d32c500e73cd7786c480fcd84c3001c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>Синтаксический анализ строк даты и времени в .NET
Методы анализа преобразовать строковое представление даты и времени в эквивалентное <xref:System.DateTime> объекта. <xref:System.DateTime.Parse%2A> И <xref:System.DateTime.TryParse%2A> методы преобразуют любой из нескольких общих представлений даты и времени. <xref:System.DateTime.ParseExact%2A> И <xref:System.DateTime.TryParseExact%2A> методы преобразуют строковое представление, которое соответствует шаблону, заданному строка формата даты и времени. (См. разделы [Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) и [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).)  
  
 На синтаксический анализ влияют свойства поставщика формата, который предоставляет такие сведения, как строки, используемые для разделителей даты и времени, обозначения месяцев, дней и периодов. Поставщик формата является текущим <xref:System.Globalization.DateTimeFormatInfo> объект, который предоставляется неявно, языком и региональными параметрами текущего потока или явно задается параметром <xref:System.IFormatProvider> параметр метода синтаксического анализа. Для <xref:System.IFormatProvider> параметр, укажите <xref:System.Globalization.CultureInfo> объект, представляющий язык и региональные параметры, или <xref:System.Globalization.DateTimeFormatInfo> объекта.  
  
 Для выполнения синтаксического анализа строковое представление даты должно содержать месяц и, по крайней мере, день или год. Строковое представление времени должно содержать часы и, по крайней мере, минуты или обозначение AM/PM. Однако при разборе опущенных компонентов для них указываются значения по умолчанию, если это возможно. Отсутствующая дата по умолчанию становится текущей датой, отсутствующий год по умолчанию становится текущим годом, отсутствующий день месяца по умолчанию становится первым днем месяца, а отсутствующие время по умолчанию задается как полночь.  
  
 Если строка, определяющая только время, то при разборе возвращается <xref:System.DateTime> объекта с его <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, и <xref:System.DateTime.Day%2A> заданы соответствующие значения <xref:System.DateTime.Today%2A> свойство. Однако если <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> указана константа метода анализа, полученный год, месяц и день задано значение `1`.  
  
 Помимо компонента даты и времени строковое представление даты и времени может содержать смещение, которое указывает, насколько время отличается от универсального синхронизированного времени (UTC). Например, строка "14/02/2007 5:32:00 -7: 00" определяет время, которое на семь часов меньше, чем UTC. Если смещение задано строковое представление времени, то при разборе возвращается <xref:System.DateTime> объекта с его <xref:System.DateTime.Kind%2A> свойство <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>. Если смещение задано, то при разборе возвращается <xref:System.DateTime> объекта с его <xref:System.DateTime.Kind%2A> свойство <xref:System.DateTimeKind.Local> и его значение настраивается местный часовой пояс компьютера. Это поведение можно изменить с помощью <xref:System.Globalization.DateTimeStyles> константу с использованием метода.  
  
 Поставщик формата также используется для интерпретации неоднозначных числовых дат. Например, неясно, какие компоненты даты в строке "02/03/04" соответствуют месяцу, дню и году. В этом случае компоненты интерпретируются согласно их порядку расположения в схожих форматах даты в поставщике формата.  
  
## <a name="parse"></a>Parse  
 В следующем примере кода показано использование **проанализировать** метод для преобразования строки в **DateTime**. В этом примере для разбора используется язык и региональные параметры, связанные с текущим потоком. Если <xref:System.Globalization.CultureInfo> связанную с текущим языком и региональными параметрами не удается преобразовать входную строку, <xref:System.FormatException> возникает исключение.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 Можно также указать **CultureInfo** задать один из языков и региональных параметров, определенных в этом объекте, или можно указать один из стандартных <xref:System.Globalization.DateTimeFormatInfo> объектов, возвращенных <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> свойство. В следующем примере кода используется поставщик формата для разбора строки на немецком языке в **DateTime**. Объект **CultureInfo** представляющий культуры de-DE, определен и передан в строке во время синтаксического анализа для обеспечения успешного разбора строкой. Это исключает любой параметр находится в **CurrentCulture** из **CurrentThread**.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 Тем не менее несмотря на то, что можно использовать перегрузки <xref:System.DateTime.Parse%2A> метод для указания поставщиков пользовательских форматов, метод не поддерживает использование поставщиков нестандартных форматов. Чтобы проанализировать дату и время, выраженное в нестандартном формате, используйте <xref:System.DateTime.ParseExact%2A> метод вместо него.  
  
 Следующий пример кода использует <xref:System.Globalization.DateTimeStyles> перечисления, чтобы указать, что текущие сведения о дате и времени, не должны быть добавлены к **DateTime** для полей, определенных в строке.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> Метод преобразует строку, которая соответствует указанному шаблону для **DateTime** объекта. Когда этому методу передается строка, не соответствующая указанному <xref:System.FormatException> возникает исключение. Можно задать один из стандартных описателей формата даты и времени или ограниченное сочетание пользовательских описателей формата для даты и времени. При использовании пользовательских описателей формата можно сконструировать пользовательскую строку распознавания. Сведения об описателях см. в разделах [Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) и [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 Каждой версии перегруженной <xref:System.DateTime.ParseExact%2A> также имеет метод <xref:System.IFormatProvider> параметр, который обычно предоставляет информацию о форматирование строки для конкретного языка и региональных параметров. Как правило, это <xref:System.IFormatProvider> объект <xref:System.Globalization.CultureInfo> , представляющий стандартный язык и региональные параметры или <xref:System.Globalization.DateTimeFormatInfo> объект, возвращаемый <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> свойство. Однако в отличие от других даты и времени синтаксического анализа функции, этот метод также поддерживает <xref:System.IFormatProvider> , определяющий нестандартный формат даты и времени.  
  
 В следующем примере кода **ParseExact** методу передается строковый объект для синтаксического анализа, затем спецификатор формата, за которым следует **CultureInfo** объекта. Это **ParseExact** метод могут только выполнять разбор строк полному шаблону данных в региональных параметров en US.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>См. также  
 [Анализ строк в .NET Framework](../../../docs/standard/base-types/parsing-strings.md)  
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)  
 [Преобразование типов в .NET](../../../docs/standard/base-types/type-conversion.md)
