---
title: Общие сведения об элементе управления MonthCalendar
ms.date: 03/30/2017
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
ms.openlocfilehash: a9b56164339d03b380a564b21855f6d94ec06af5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734940"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>Общие сведения об элементе управления MonthCalendar (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.MonthCalendar> представляет собой интуитивно понятный графический интерфейс, позволяющий пользователям просматривать и устанавливать сведения о датах. Элемент управления отображает календарь: сетку, содержащую пронумерованные дни месяца, упорядоченные по столбцам в соответствии с днями недели с выделенным диапазоном дат. Вы можете выбрать другой месяц, нажимая кнопки со стрелками с обеих сторон заголовка месяца. В отличие от аналогичного элемента управления <xref:System.Windows.Forms.DateTimePicker> можно выбрать более одной даты с этим элементом управления. Дополнительные сведения об элементе управления <xref:System.Windows.Forms.DateTimePicker> см. в разделе [элемент управления DateTimePicker](datetimepicker-control-windows-forms.md).  
  
## <a name="configuring-the-monthcalendar-control"></a>Настройка элемента управления MonthCalendar  
 Внешний вид элемента управления <xref:System.Windows.Forms.MonthCalendar> очень настраиваемый. По умолчанию сегодняшняя дата отображается в круге, а также отмечается в нижней части сетки. Эту функцию можно изменить, задав для свойств <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> и <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> значение `false`. Вы также можете добавить в календарь номера недель, задав для свойства <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> значение `true`. Установив свойство <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>, можно отобразить несколько месяцев по горизонтали и по вертикали. По умолчанию воскресенье отображается в качестве первого дня недели, но любой день можно назначить с помощью свойства <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A>.  
  
 Можно также задать отображение определенных дат полужирным шрифтом на один раз, ежегодно или ежемесячно, добавив <xref:System.DateTime> объекты в свойства <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>и <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>. Дополнительные сведения см. в разделе [как отображать отдельные дни полужирным шрифтом с помощью элемента управления Windows Forms MonthCalendar](display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 Ключевым свойством элемента управления <xref:System.Windows.Forms.MonthCalendar> является <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, диапазон дат, выбранный в элементе управления. Значение <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> не может превышать максимальное число дней, которое может быть выбрано, задано в свойстве <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A>. Самые ранние и последние даты, которые пользователь может выбрать, определяются свойствами <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> и <xref:System.Windows.Forms.MonthCalendar.MinDate%2A>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.MonthCalendar>
- [Элемент управления MonthCalendar](monthcalendar-control-windows-forms.md)
