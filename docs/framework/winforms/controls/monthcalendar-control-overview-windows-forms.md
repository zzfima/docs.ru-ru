---
title: "Общие сведения об элементе управления MonthCalendar (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a22667e4227067dfbf0baaad1838ab520e0ac7e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="monthcalendar-control-overview-windows-forms"></a>Общие сведения об элементе управления MonthCalendar (Windows Forms)
Windows Forms <xref:System.Windows.Forms.MonthCalendar> управления предоставляет интуитивно понятный графический интерфейс для пользователей, для просмотра и задания сведений о дате. Отображает календарь: сетку, содержащую пронумерованные дни месяца, разбитые на столбцы по дням недели, с выбранным диапазоном дат. С помощью кнопок со стрелками слева от заголовка месяца можно выбрать другой месяц. В отличие от аналогичного <xref:System.Windows.Forms.DateTimePicker> элемента управления, можно выбрать несколько дат с этим элементом управления. Дополнительные сведения о <xref:System.Windows.Forms.DateTimePicker> управления см. в разделе [управления DateTimePicker](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md).  
  
## <a name="configuring-the-monthcalendar-control"></a>Настройка элемента управления MonthCalendar  
 <xref:System.Windows.Forms.MonthCalendar> Широкие возможности настройки внешнего вида элемента управления. По умолчанию сегодняшняя дата отображается как обведен и также отмечается в нижней части сетки. Этот компонент можно изменить, задав <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> и <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> свойства `false`. Можно также добавить номера недель к календарю, присвоив <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> свойства `true`. Установив <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> может иметь несколько месяцев, отображаемых по горизонтали и вертикали. По умолчанию отображается как первый день недели, воскресенье, но может быть назначен любой день с помощью <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> свойство.  
  
 Можно также задать для отображения в определенных дат полужирным единовременно, год или месяц, путем добавления <xref:System.DateTime> объектов <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>, и <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> свойства. Дополнительные сведения см. в разделе [как: отображение определенных дней полужирным с элементом управления Windows Forms MonthCalendar](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 Ключевое свойство <xref:System.Windows.Forms.MonthCalendar> управления <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, диапазон дат, выбранный в элементе управления. <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> Значение не может превышать максимальное количество дней, которые могут быть выбраны, установите в <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> свойство. Раннее и последнюю даты, пользователь может выбрать определяются <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> и <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> свойства.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.MonthCalendar>  
 [Элемент управления MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
