---
title: "DatePicker | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "элементы управления [WPF], DatePicker"
  - "DatePicker - элемент управления [WPF]"
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# DatePicker
Элемент управления <xref:System.Windows.Controls.DatePicker> позволяет пользователю выбрать дату посредством ее ввода в текстовое поле или использования элемента управления раскрывающегося списка <xref:System.Windows.Controls.Calendar>.  
  
 На следующем рисунке показан элемент управления <xref:System.Windows.Controls.DatePicker>.  
  
 ![Элемент управления DatePicker](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP\_DatePicker")  
Элемент управления DatePicker  
  
 Многие свойства элемента управления <xref:System.Windows.Controls.DatePicker> предназначены для управления его встроенным элементом управления <xref:System.Windows.Controls.Calendar>; эти свойства функционируют аналогично эквивалентному свойству элемента управления <xref:System.Windows.Controls.Calendar>.  В частности, свойства <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=fullName>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=fullName>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=fullName>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=fullName>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=fullName>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=fullName>и <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=fullName> функционируют аналогично соответствующим свойствам элемента управления <xref:System.Windows.Controls.Calendar>.  Дополнительные сведения см. в разделе <xref:System.Windows.Controls.Calendar>.  
  
 Пользователи могут вводить дату непосредственно в текстовое поле, которое задает свойство <xref:System.Windows.Controls.DatePicker.Text%2A>.  Если элементу управления <xref:System.Windows.Controls.DatePicker> не удается преобразовать введенную строку в допустимую дату, возникает событие <xref:System.Windows.Controls.DatePicker.DateValidationError>.  По умолчанию это приводит к исключению, но обработчик событий <xref:System.Windows.Controls.DatePicker.DateValidationError> может задать для свойства <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> значение `false` и предотвратить возникновение исключения.  
  
## См. также  
 [Элементы управления](../../../../docs/framework/wpf/controls/index.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)