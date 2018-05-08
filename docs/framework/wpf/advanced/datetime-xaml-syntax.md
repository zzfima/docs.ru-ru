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
ms.openlocfilehash: 286117cc0cce9fb54ea2c372360b13865fba77ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="datetime-xaml-syntax"></a>Синтаксис DateTime XAML
Некоторые элементы управления, такие как <xref:System.Windows.Controls.Calendar> и <xref:System.Windows.Controls.DatePicker>, имеют свойства, использующие <xref:System.DateTime> типа. Несмотря на то что начальные дата и время для этих элементов управления обычно указываются в коде программной части во время выполнения, их можно указать в коде XAML. Средство синтаксического анализа WPF XAML обрабатывает анализ <xref:System.DateTime> значения с помощью встроенных текстового синтаксиса XAML. В этом разделе описаны особенности <xref:System.DateTime> текстового синтаксиса XAML.  
  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>Когда требуется использовать синтаксис DateTime XAML  
 Задание дат в XAML не всегда обязательно, а иногда даже может быть нежелательно. Например, можно использовать <xref:System.DateTime.Now%2A?displayProperty=nameWithType> инициализацию даты во время выполнения, или можно сделать все корректировки дат календаря в кода на основе ввода пользователя. Однако существуют сценарии, где можно жестко закодировать дат в <xref:System.Windows.Controls.Calendar> и <xref:System.Windows.Controls.DatePicker> в шаблоне элемента управления. <xref:System.DateTime> Синтаксиса XAML должен использоваться в следующих случаях.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>Синтаксис DateTime XAML является собственным поведением  
 <xref:System.DateTime> — Это класс, который определен в библиотеках базовых классов среды CLR. Из-за связи библиотеки базовых классов с остальной части среды CLR, не удалось применить <xref:System.ComponentModel.TypeConverterAttribute> класс и использовать преобразователь типов для обработки строк из XAML и преобразовать их в <xref:System.DateTime> в объектной модели время выполнения. Нет класса `DateTimeConverter`, предоставляющего поведение преобразования: поведение преобразования, описанное в этом разделе, является собственным для средства синтаксического анализа XAML WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>Строки формата для синтаксиса DateTime XAML  
 Можно указать формат <xref:System.DateTime> со строкой формата. Строки формата формализуют синтаксис текста, который может использоваться для создания значения. <xref:System.DateTime> значения для существующих элементов управления WPF обычно только использование компонентов даты <xref:System.DateTime> и не компоненты времени.  
  
 При указании <xref:System.DateTime> в XAML, можно использовать любой из строк формата попеременно.  
  
 Можно также использовать форматы и строки формата, которые не рассматриваются в этом разделе. С технической точки зрения XAML для любого <xref:System.DateTime> значение, которое указывается, а затем анализируется средством синтаксического анализа WPF XAML использует внутренний вызов <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, поэтому можно использовать любую строку, принято <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> для своих входных данных. Дополнительные сведения см. в разделе <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  Всегда использует синтаксис DateTime XAML `en-us` как <xref:System.Globalization.CultureInfo> для его собственного преобразования. Это не зависит от <xref:System.Windows.FrameworkElement.Language%2A> значение или `xml:lang` значение в XAML-ФАЙЛЕ, так как преобразования типов на уровне атрибута XAML работает без этого контекста. Не пытайтесь выполнять интерполяцию показанных здесь строк формата из-за различий региональных параметров, таких как порядок отображения дня и месяца. Показанные здесь строки формата — это именно те строки формата, которые используются при синтаксическом анализе XAML независимо от других параметров языка и региональных параметров.  
  
 В следующих разделах описаны некоторые общие <xref:System.DateTime> строки формата.  
  
### <a name="short-date-pattern-d"></a>Шаблон краткого формата даты (d)  
 Ниже приведен краткий формат даты для <xref:System.DateTime> в XAML:  
  
 `M/d/YYYY`  
  
 Это самая простая форма, определяющая все необходимые сведения для типичного использования элементами управления WPF. На нее не влияют случайные смещения часового пояса (по сравнению с компонентом времени), и поэтому она предпочтительнее других форматов.  
  
 Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку.  
  
 `3/1/2010`  
  
 Дополнительные сведения см. в разделе <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Сортируемый шаблон даты и времени (s)  
 В следующем примере показаны сортируемого <xref:System.DateTime> шаблон в XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку (все компоненты времени вводятся как 0).  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>Шаблон RFC1123 (r)  
 Шаблон RFC1123 удобен, поскольку он может быть строкой ввода из других генераторов данных, также использующих шаблон RFC1123, в ситуациях инвариантных значений языка и региональных параметров. В следующем примере показаны RFC1123 <xref:System.DateTime> шаблон в XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку (все компоненты времени вводятся как 0).  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Другие форматы и шаблоны  
 Как уже говорилось ранее, <xref:System.DateTime> в XAML может быть указан как любая строка, которая является допустимым как входные для <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. Сюда входят другие форматы, документально оформленными принципами (например <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) и форматы, которые не формализованный как определенный <xref:System.Globalization.DateTimeFormatInfo> формы. Например, форма `YYYY/mm/dd` приемлем как входные для <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. Этот раздел не является попыткой описать все возможные форматы: вместо этого рекомендуется использование шаблона короткого формата даты.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
