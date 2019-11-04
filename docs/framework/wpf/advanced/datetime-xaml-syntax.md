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
ms.openlocfilehash: c9fb030e6f819b1ca463199a76acd32cb1865f33
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458942"
---
# <a name="datetime-xaml-syntax"></a>Синтаксис DateTime XAML
Некоторые элементы управления, такие как <xref:System.Windows.Controls.Calendar> и <xref:System.Windows.Controls.DatePicker>, имеют свойства, использующие тип <xref:System.DateTime>. Несмотря на то что начальные дата и время для этих элементов управления обычно указываются в коде программной части во время выполнения, их можно указать в коде XAML. Средство синтаксического анализа XAML WPF обрабатывает синтаксический анализ <xref:System.DateTime> значений с помощью встроенного синтаксиса текста XAML. В этом разделе описываются особенности синтаксиса текста <xref:System.DateTime> XAML.  

<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>Когда требуется использовать синтаксис DateTime XAML  
 Задание дат в XAML не всегда обязательно, а иногда даже может быть нежелательно. Например, можно использовать свойство <xref:System.DateTime.Now%2A?displayProperty=nameWithType> для инициализации даты во время выполнения, либо можно выполнить все настройки даты для календаря в коде программной части на основе вводимых пользователем данных. Однако существуют сценарии, в которых может потребоваться жестко закодировать даты в <xref:System.Windows.Controls.Calendar> и <xref:System.Windows.Controls.DatePicker> в шаблоне элемента управления. Для этих сценариев необходимо использовать синтаксис XAML <xref:System.DateTime>.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>Синтаксис DateTime XAML является собственным поведением  
 <xref:System.DateTime> — это класс, определенный в библиотеках базовых классов среды CLR. Из-за того, как библиотеки базовых классов связаны с остальной частью среды CLR, невозможно применить <xref:System.ComponentModel.TypeConverterAttribute> к классу и использовать преобразователь типов для обработки строк из XAML и преобразования их в <xref:System.DateTime> в объектной модели времени выполнения. Нет класса `DateTimeConverter`, предоставляющего поведение преобразования: поведение преобразования, описанное в этом разделе, является собственным для средства синтаксического анализа XAML WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>Строки формата для синтаксиса DateTime XAML  
 Можно указать формат <xref:System.DateTime> со строкой формата. Строки формата формализуют синтаксис текста, который может использоваться для создания значения. <xref:System.DateTime> значения для существующих элементов управления WPF, как правило, используют только компоненты даты <xref:System.DateTime>, а не компоненты времени.  
  
 При указании <xref:System.DateTime> в XAML можно использовать любые строки формата взаимозаменяемы.  
  
 Можно также использовать форматы и строки формата, которые не рассматриваются в этом разделе. С технической точки зрения XAML для любого <xref:System.DateTime> значения, которое задается и затем анализируется анализатором XAML WPF, использует внутренний вызов <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, поэтому можно использовать любую строку, принимаемую <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> для входных данных XAML. Для получения дополнительной информации см. <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> Синтаксис DateTime XAML всегда использует `en-us` как <xref:System.Globalization.CultureInfo> для собственного преобразования. На это не влияет <xref:System.Windows.FrameworkElement.Language%2A> значение или `xml:lang` значение в XAML, поскольку преобразование типа на уровне атрибута XAML действует без этого контекста. Не пытайтесь выполнять интерполяцию показанных здесь строк формата из-за различий региональных параметров, таких как порядок отображения дня и месяца. Показанные здесь строки формата — это именно те строки формата, которые используются при синтаксическом анализе XAML независимо от других параметров языка и региональных параметров.  
  
 В следующих разделах описаны некоторые распространенные строки формата <xref:System.DateTime>.  
  
### <a name="short-date-pattern-d"></a>Шаблон краткого формата даты (d)  
 Ниже показан краткий формат даты для <xref:System.DateTime> в XAML:  
  
 `M/d/YYYY`  
  
 Это самая простая форма, определяющая все необходимые сведения для типичного использования элементами управления WPF. На нее не влияют случайные смещения часового пояса (по сравнению с компонентом времени), и поэтому она предпочтительнее других форматов.  
  
 Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку.  
  
 `3/1/2010`  
  
 Для получения дополнительной информации см. <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Сортируемый шаблон даты и времени (s)  
 Ниже показан шаблон с возможностью сортировки <xref:System.DateTime> в XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку (все компоненты времени вводятся как 0).  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>Шаблон RFC1123 (r)  
 Шаблон RFC1123 удобен, поскольку он может быть строкой ввода из других генераторов данных, также использующих шаблон RFC1123, в ситуациях инвариантных значений языка и региональных параметров. Ниже показан шаблон <xref:System.DateTime> RFC1123 в XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку (все компоненты времени вводятся как 0).  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Другие форматы и шаблоны  
 Как упоминалось ранее, <xref:System.DateTime> в XAML можно указать как любую строку, допустимую в качестве входных данных для <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. К ним относятся другие формальные форматы (например <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) и форматы, которые не формально представляются как конкретная форма <xref:System.Globalization.DateTimeFormatInfo>. Например, форма `YYYY/mm/dd` допустима в качестве входных данных для <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. Этот раздел не является попыткой описать все возможные форматы: вместо этого рекомендуется использование шаблона короткого формата даты.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о языке XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
