---
title: Общие сведения об элементе управления DateTimePicker
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: 63271dd91116c1f68d426f3ed5aa710644ded928
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746939"
---
# <a name="datetimepicker-control-overview-windows-forms"></a>Общие сведения об элементе управления DateTimePicker (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.DateTimePicker> позволяет пользователю выбрать один элемент из списка дат или времени. При использовании для представления даты она появляется в двух частях: раскрывающемся списке с датой, представленной в тексте, и сетке, которая появляется при щелчке стрелки вниз рядом со списком. Сетка выглядит как элемент управления <xref:System.Windows.Forms.MonthCalendar>, который можно использовать для выбора нескольких дат. Дополнительные сведения об элементе управления <xref:System.Windows.Forms.MonthCalendar> см. в разделе [Общие сведения об элементе управления MonthCalendar](monthcalendar-control-overview-windows-forms.md).  
  
## <a name="key-properties"></a>Ключевые свойства  
 Если требуется, чтобы <xref:System.Windows.Forms.DateTimePicker> отображались как элемент управления для выбора или изменения времени вместо дат, установите для свойства <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> значение `true` а для свойства <xref:System.Windows.Forms.DateTimePicker.Format%2A> значение <xref:System.Windows.Forms.DateTimePickerFormat.Time>. Дополнительные сведения см. [в разделе инструкции. Отображение времени с помощью элемента управления DateTimePicker](how-to-display-time-with-the-datetimepicker-control.md).  
  
 Если свойство <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> имеет значение `true`, рядом с выбранной датой в элементе управления отображается флажок. Если флажок установлен, то выбранное значение даты и времени можно обновить. Если флажок пуст, значение отображается недоступно.  
  
 Свойства <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> и <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> элемента управления определяют диапазон дат и времени. Свойство <xref:System.Windows.Forms.DateTimePicker.Value%2A> содержит текущую дату и время, когда элементу управления присвоено значение. Дополнительные сведения см. [в разделе инструкции. Установка и возврат дат с помощью элемента управления Windows Forms DateTimePicker](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md). Значения могут отображаться в четырех форматах, заданных свойством <xref:System.Windows.Forms.DateTimePicker.Format%2A>: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>или <xref:System.Windows.Forms.DateTimePickerFormat.Custom>. Если выбран настраиваемый формат, необходимо задать для свойства <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> соответствующую строку. Дополнительные сведения см. в разделе [инструкции. Отображение даты в пользовательском формате с помощью элемента управления Windows Forms DateTimePicker](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## <a name="see-also"></a>См. также:

- [Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
- [Практическое руководство. Отображение и ввод дат с помощью элемента управления DateTimePicker в Windows Forms](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
