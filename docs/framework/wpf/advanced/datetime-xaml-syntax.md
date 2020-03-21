---
title: Синтаксис DateTime XAML
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: 57b73d3b80f0392b99aacfbfac4d8709f72d52e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186332"
---
# <a name="datetime-xaml-syntax"></a>Синтаксис DateTime XAML
Некоторые элементы <xref:System.Windows.Controls.Calendar> управления, такие как <xref:System.Windows.Controls.DatePicker> <xref:System.DateTime> и, имеют свойства, которые используют тип. Несмотря на то что начальные дата и время для этих элементов управления обычно указываются в коде программной части во время выполнения, их можно указать в коде XAML. Парсер WPF XAML обрабатывает разбор <xref:System.DateTime> значений с помощью встроенного синтаксиса текста XAML. Эта тема описывает специфику <xref:System.DateTime> синтаксиса текста XAML.  

<a name="where_datetime_xaml_syntax_is_used"></a>
## <a name="when-to-use-datetime-xaml-syntax"></a>Когда требуется использовать синтаксис DateTime XAML  
 Задание дат в XAML не всегда обязательно, а иногда даже может быть нежелательно. Например, можно использовать <xref:System.DateTime.Now%2A?displayProperty=nameWithType> свойство для инициализации даты во время выполнения, или можно сделать все корректировки даты для календаря в коде сзади на основе пользовательского ввода. Тем не менее, есть сценарии, где вы <xref:System.Windows.Controls.Calendar> <xref:System.Windows.Controls.DatePicker> можете жесткого кода даты в и в шаблоне управления. Для <xref:System.DateTime> этих сценариев необходимо использовать синтаксис XAML.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>Синтаксис DateTime XAML является собственным поведением  
 <xref:System.DateTime>— это класс, определяемый в библиотеках базового класса CLR. Из-за того, как библиотеки базового класса соотносятся с <xref:System.ComponentModel.TypeConverterAttribute> остальной частью CLR, невозможно применить к классу и <xref:System.DateTime> использовать преобразователь типа для обработки строк xAML и преобразования их в модель объекта времени выполнения. Нет класса `DateTimeConverter`, предоставляющего поведение преобразования: поведение преобразования, описанное в этом разделе, является собственным для средства синтаксического анализа XAML WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>
## <a name="format-strings-for-datetime-xaml-syntax"></a>Строки формата для синтаксиса DateTime XAML  
 Можно указать формат <xref:System.DateTime> строки формата. Строки формата формализуют синтаксис текста, который может использоваться для создания значения. <xref:System.DateTime>значения для существующих элементов управления WPF обычно <xref:System.DateTime> используют только компоненты даты, а не компоненты времени.  
  
 При указании <xref:System.DateTime> в XAML можно использовать любую строку формата взаимозаменяемо.  
  
 Можно также использовать форматы и строки формата, которые не рассматриваются в этом разделе. Технически, XAML для <xref:System.DateTime> любого значения, которое указано, а затем разобрано WPF XAML parser использует внутренний <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>вызов, поэтому вы можете использовать любую строку, принятую <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> для ввода XAML. Дополнительные сведения см. в разделе <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> Синтаксис DateTime XAML `en-us` всегда <xref:System.Globalization.CultureInfo> используется в качестве преобразования. Это не зависит <xref:System.Windows.FrameworkElement.Language%2A> от `xml:lang` значения или значения в XAML, потому что конверсия уровня атрибутов XAML действует без этого контекста. Не пытайтесь выполнять интерполяцию показанных здесь строк формата из-за различий региональных параметров, таких как порядок отображения дня и месяца. Показанные здесь строки формата — это именно те строки формата, которые используются при синтаксическом анализе XAML независимо от других параметров языка и региональных параметров.  
  
 В следующих разделах <xref:System.DateTime> описаны некоторые общие строки формата.  
  
### <a name="short-date-pattern-d"></a>Шаблон краткого формата даты (d)  
 Ниже показан формат короткой <xref:System.DateTime> даты для XAML:  
  
 `M/d/YYYY`  
  
 Это самая простая форма, определяющая все необходимые сведения для типичного использования элементами управления WPF. На нее не влияют случайные смещения часового пояса (по сравнению с компонентом времени), и поэтому она предпочтительнее других форматов.  
  
 Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку.  
  
 `3/1/2010`  
  
 Дополнительные сведения см. в разделе <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Сортируемый шаблон даты и времени (s)  
 Ниже показана сортируемая <xref:System.DateTime> закономерность в XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку (все компоненты времени вводятся как 0).  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>Шаблон RFC1123 (r)  
 Шаблон RFC1123 удобен, поскольку он может быть строкой ввода из других генераторов данных, также использующих шаблон RFC1123, в ситуациях инвариантных значений языка и региональных параметров. Ниже показан амодель RFC1123 <xref:System.DateTime> в XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку (все компоненты времени вводятся как 0).  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Другие форматы и шаблоны  
 Как указывалось <xref:System.DateTime> ранее, в XAML может быть указан как <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>любая строка, которая является приемлемой в качестве ввода для . Это включает в себя другие <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>формализованные форматы (например), и форматы, которые не формализованы в качестве конкретной <xref:System.Globalization.DateTimeFormatInfo> формы. Например, форма `YYYY/mm/dd` приемлема в <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>качестве ввода для . Этот раздел не является попыткой описать все возможные форматы: вместо этого рекомендуется использование шаблона короткого формата даты.  
  
## <a name="see-also"></a>См. также раздел

- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
