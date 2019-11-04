---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 3e66b2306c11c54db14eb05cc6860257635cc653
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460353"
---
# <a name="datepicker"></a>DatePicker
Элемент управления <xref:System.Windows.Controls.DatePicker> позволяет пользователю выбрать дату, введя ее в текстовое поле, или с помощью раскрывающегося <xref:System.Windows.Controls.Calendar> элемента управления.  
  
 На следующем рисунке показан <xref:System.Windows.Controls.DatePicker>.  
  
 ![Элемент управления DatePicker](./media/ndp-datepicker.png "NDP_DatePicker")  
Элемент управления DatePicker  
  
 Многие свойства <xref:System.Windows.Controls.DatePicker> элемента управления предназначены для управления встроенными <xref:System.Windows.Controls.Calendar>и функционируют аналогично эквивалентному свойству в <xref:System.Windows.Controls.Calendar>. В частности, свойства <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>и <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> идентичны своим <xref:System.Windows.Controls.Calendar>ным аналогам. Для получения дополнительной информации см. <xref:System.Windows.Controls.Calendar>.  
  
 Пользователи могут вводить дату непосредственно в текстовое поле, которое задает свойство <xref:System.Windows.Controls.DatePicker.Text%2A>. Если <xref:System.Windows.Controls.DatePicker> не может преобразовать входную строку в допустимую дату, будет вызвано событие <xref:System.Windows.Controls.DatePicker.DateValidationError>. По умолчанию это вызывает исключение, но обработчик событий для <xref:System.Windows.Controls.DatePicker.DateValidationError> может установить для свойства <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> значение `false` и предотвратить возникновение исключения.  
  
## <a name="see-also"></a>См. также

- [Элементы управления](index.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
