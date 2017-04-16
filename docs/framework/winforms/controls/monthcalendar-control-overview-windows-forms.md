---
title: "Общие сведения об элементе управления MonthCalendar (Windows Forms) | Microsoft Docs"
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
  - "MonthCalendar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Calendar - элементы управления, Windows Forms"
  - "календари, элементы управления Windows Forms"
  - "MonthCalendar - элемент управления [Windows Forms], установка первого дня недели"
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения об элементе управления MonthCalendar (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.MonthCalendar> предоставляет пользователям понятный графический интерфейс для просмотра и задания сведений о дате.  Этот элемент управления выводит календарь: сетку, содержащую пронумерованные дни месяца, разбитые на столбцы по дням недели, с выделенным диапазоном дат.  Перейти к другому месяцу можно, нажав кнопку со стрелкой справа или слева от заголовка месяца.  В отличие от аналогичного элемента управления <xref:System.Windows.Forms.DateTimePicker>, с помощью этого элемента управления можно выделить несколько дат.  Дополнительные сведения об элементе управления <xref:System.Windows.Forms.DateTimePicker> см. в разделе [Элемент управления DateTimePicker](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md).  
  
## Конфигурирование элемента управления MonthCalendar  
 Внешний вид элемента управления <xref:System.Windows.Forms.MonthCalendar> можно настроить множеством способов.  По умолчанию текущая дата обводится кружком, а также отмечается в нижней части сетки.  Это используемое по умолчанию поведение можно изменить, присваивая свойствам <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> и <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> значение `false`.  В календарь можно также добавить номера недель, задав для свойства <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> значение `true`.  С помощью свойства <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> можно задать отображение нескольких месяцев по вертикали или по горизонтали.  По умолчанию в качестве первого дня недели отображается воскресенье, но с помощью свойства <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> любой день недели можно назначить первым.  
  
 Можно также задать единовременное, ежегодное или ежемесячное отображение полужирным шрифтом определенных дат, добавив объекты <xref:System.DateTime> в свойства <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> и <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>.  Дополнительные сведения см. в разделе [Практическое руководство. Отображение определенных дней полужирным шрифтом в элементе управления MonthCalendar в Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 Ключевым свойством элемента управления <xref:System.Windows.Forms.MonthCalendar> является свойство <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, представляющее собой диапазон дат, выделенных в элементе управления.  Значение <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> не может превышать максимального количества дней, которые можно выделить, заданного в свойстве <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A>.  Самая ранняя и самая поздняя даты, которые может выбрать пользователь, определяются свойствами <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> и <xref:System.Windows.Forms.MonthCalendar.MinDate%2A>.  
  
## См. также  
 <xref:System.Windows.Forms.MonthCalendar>   
 [Элемент управления MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)