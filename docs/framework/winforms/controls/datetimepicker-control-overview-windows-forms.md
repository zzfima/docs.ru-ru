---
title: "Общие сведения об элементе управления DateTimePicker (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DateTimePicker"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления для даты и времени"
  - "DateTimePicker - элемент управления [Windows Forms], сведения"
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Общие сведения об элементе управления DateTimePicker (Windows Forms)
Элемент управления <xref:System.Windows.Forms.DateTimePicker> Windows Forms позволяет пользователю выбрать отдельный элемент в списке дат или времени.  Когда компонент используется для представления даты, он состоит из двух частей: раскрывающегося списка с датой, представленной в виде текста, и сетки, которая появляется при нажатии кнопки со стрелкой вниз, расположенной рядом со списком.  Сетка выглядит аналогично элементу управления <xref:System.Windows.Forms.MonthCalendar>, который используется для выбора нескольких дат.  Дополнительные сведения об элементе управления <xref:System.Windows.Forms.MonthCalendar> см. в разделе [Общие сведения об элементе управления MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md).  
  
## Ключевые свойства  
 Если требуется, чтобы <xref:System.Windows.Forms.DateTimePicker> отображался как элемент управления для выбора и изменения времени, а не даты, установите свойству <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> значение `true`, а свойству <xref:System.Windows.Forms.DateTimePicker.Format%2A> — значение <xref:System.Windows.Forms.DateTimePickerFormat>.  Дополнительные сведения см. в разделе [Практическое руководство. Отображение времени с помощью элемента управления DateTimePicker](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).  
  
 Если для свойства <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> задано значение `true`, рядом с выделенной датой в элементе управления отображается поле флажка.  При установленном флажке выделенное значение даты и времени можно обновить.  Если флажок снят, отображаемое значение недоступно.  
  
 Свойства элемента управления <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> и <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> определяют диапазон значений дат и времени.  Свойство <xref:System.Windows.Forms.DateTimePicker.Value%2A> содержит текущие дату и время, установленные для элемента управления.  Дополнительные сведения см. в разделе [Практическое руководство. Отображение и ввод дат с помощью элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md).  Значения могут отображаться в четырех форматах, которые задаются свойством <xref:System.Windows.Forms.DateTimePicker.Format%2A>: <xref:System.Windows.Forms.DateTimePickerFormat>, <xref:System.Windows.Forms.DateTimePickerFormat>, <xref:System.Windows.Forms.DateTimePickerFormat> или <xref:System.Windows.Forms.DateTimePickerFormat>.  При выборе пользовательского формата необходимо задать для свойства <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> соответствующую строку.  Дополнительные сведения см. в разделе [Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## См. также  
 [Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)   
 [Практическое руководство. Отображение и ввод дат с помощью элемента управления DateTimePicker в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)