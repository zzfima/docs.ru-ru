---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 910ce09bfad6a46e3d96784b980ee4175c3d26a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="datepicker"></a>DatePicker
<xref:System.Windows.Controls.DatePicker> Управления позволяет пользователю выбрать дату, либо путем ввода его в текстовое поле или с помощью раскрывающегося списка <xref:System.Windows.Controls.Calendar> элемента управления.  
  
 На следующем рисунке показана <xref:System.Windows.Controls.DatePicker>.  
  
 ![Элемент управления DatePicker](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")  
Элемент управления DatePicker  
  
 Многие <xref:System.Windows.Controls.DatePicker> свойства элемента управления, для управления его встроенным <xref:System.Windows.Controls.Calendar>и функция идентично свойству эквивалент в <xref:System.Windows.Controls.Calendar>. В частности <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, и <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> свойства работать идентично их <xref:System.Windows.Controls.Calendar> аналоги. Дополнительные сведения см. в разделе <xref:System.Windows.Controls.Calendar>.  
  
 Пользователи могут ввести дату непосредственно в текстовое поле, которое задает <xref:System.Windows.Controls.DatePicker.Text%2A> свойства. Если <xref:System.Windows.Controls.DatePicker> не удается преобразовать введенную строку в допустимую дату <xref:System.Windows.Controls.DatePicker.DateValidationError> возникает событие. По умолчанию это приводит к возникновению исключения, но обработчик событий для <xref:System.Windows.Controls.DatePicker.DateValidationError> можно задать <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> свойства `false` и предотвратить возникновение исключения.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления](../../../../docs/framework/wpf/controls/index.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)
