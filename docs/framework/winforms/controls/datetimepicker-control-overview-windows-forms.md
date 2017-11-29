---
title: "Общие сведения об элементе управления DateTimePicker (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a97eecc43614c84867e9dbdd527dbebd7dfd426e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="datetimepicker-control-overview-windows-forms"></a>Общие сведения об элементе управления DateTimePicker (Windows Forms)
Windows Forms <xref:System.Windows.Forms.DateTimePicker> управления позволяет пользователю выбрать один элемент из списка дат или времени. Используемый для представления даты, он отображается в виде двух частей: раскрывающегося списка с даты, представленной в тексте и сетки, которая появляется, если щелкнуть стрелку вниз рядом со списком. Сетка выглядит аналогично <xref:System.Windows.Forms.MonthCalendar> элемента управления, который может использоваться для выбора нескольких дат. Дополнительные сведения о <xref:System.Windows.Forms.MonthCalendar> управления см. в разделе [Обзор элемента управления MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md).  
  
## <a name="key-properties"></a>Ключевые свойства  
 Если вы хотите <xref:System.Windows.Forms.DateTimePicker> отображаться как элемент управления для выбора или изменение значений времени вместо даты, задайте <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> свойства `true` и <xref:System.Windows.Forms.DateTimePicker.Format%2A> свойства <xref:System.Windows.Forms.DateTimePickerFormat.Time>. Дополнительные сведения см. [как: время отображения с помощью элемента управления DateTimePicker](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).  
  
 Когда <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> свойству `true`, отображаться флажок рядом с выбранной даты в элементе управления. Если флажок установлен, можно обновить выбранное значение даты и времени. Если флажок снят, отображаемое значение недоступно.  
  
 Элемент управления <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> и <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> определяют диапазон значений даты и времени. <xref:System.Windows.Forms.DateTimePicker.Value%2A> Свойство содержит текущую дату и время, имеет значение элемента управления. Дополнительные сведения см. в разделе [как: набор и возвращают даты с помощью элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md). Значения могут отображаться в четырех форматов, которые задаются <xref:System.Windows.Forms.DateTimePicker.Format%2A> свойство: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>, или <xref:System.Windows.Forms.DateTimePickerFormat.Custom>. Если установлен пользовательский формат, необходимо задать <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> свойства соответствующую строку. Дополнительные сведения см. в разделе [как: Отображение даты в формате с помощью элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)  
 [Практическое руководство. Отображение и ввод дат с помощью элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
