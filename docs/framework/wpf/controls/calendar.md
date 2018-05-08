---
title: Календарь
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: b706ec6236b7e3e10865eee9fd32c2eb5a5e7db2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="calendar"></a>Календарь
Календарь, и позволяет пользователю выбрать дату с помощью визуального календаря.  
  
 Объект <xref:System.Windows.Controls.Calendar> элемент управления может использоваться сам по себе или в составе раскрывающемся <xref:System.Windows.Controls.DatePicker> элемента управления. Дополнительные сведения см. в разделе <xref:System.Windows.Controls.DatePicker>.  
  
 На следующем рисунке показано два <xref:System.Windows.Controls.Calendar> определяет одну с выбранными и затемненными датами.  
  
 ![Элементы управления календаря](../../../../docs/framework/wpf/controls/media/ndp-calendarcontrols.png "NDP_CalendarControls")  
Элементы управления календаря  
  
 Следующая таблица содержит сведения о задачах, которые обычно связаны с <xref:System.Windows.Controls.Calendar>.  
  
|Задача|Реализация|  
|----------|--------------------|  
|Укажите даты, не могут быть выбраны.|Используйте свойство <xref:System.Windows.Controls.Calendar.BlackoutDates%2A>.|  
|У <xref:System.Windows.Controls.Calendar> отображать месяц, год или десяти лет.|Задать <xref:System.Windows.Controls.Calendar.DisplayMode%2A> свойства месяц, год или десятилетие.|  
|Укажите, может ли пользователь выбрать дату, диапазон дат или несколько диапазонов дат.|Используйте <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.|  
|Укажите диапазон дат, <xref:System.Windows.Controls.Calendar> отображает.|Используйте <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> и <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A> свойства.|  
|Укажите, выделяется ли текущая дата.|Используйте свойство <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>. По умолчанию <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> — `true`.|  
|Изменить размер <xref:System.Windows.Controls.Calendar>.|Используйте <xref:System.Windows.Controls.Viewbox> или задать <xref:System.Windows.FrameworkElement.LayoutTransform%2A> свойства <xref:System.Windows.Media.ScaleTransform>. Обратите внимание, что если задать <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства <xref:System.Windows.Controls.Calendar>, фактического календаря не изменять свой размер.|  
  
 <xref:System.Windows.Controls.Calendar> Управления обеспечивает базовые возможности навигации с помощью клавиатуры или мыши. В следующей таблице перечислены с помощью клавиатуры.  
  
|Сочетание клавиш|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|Действие|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|СТРЕЛКА|<xref:System.Windows.Controls.CalendarMode.Month>|Изменения <xref:System.Windows.Controls.Calendar.SelectedDate%2A> свойство Если <xref:System.Windows.Controls.Calendar.SelectionMode%2A> не задано значение <xref:System.Windows.Controls.CalendarSelectionMode.None>.|  
|СТРЕЛКА|<xref:System.Windows.Controls.CalendarMode.Year>|Изменяет значение месяца для <xref:System.Windows.Controls.Calendar.DisplayDate%2A> свойства. Обратите внимание, что <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|СТРЕЛКА|<xref:System.Windows.Controls.CalendarMode.Decade>|Изменяет значение года для <xref:System.Windows.Controls.Calendar.DisplayDate%2A>. Обратите внимание, что <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|SHIFT + СТРЕЛКА|<xref:System.Windows.Controls.CalendarMode.Month>|Если <xref:System.Windows.Controls.Calendar.SelectionMode%2A> равно <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> или <xref:System.Windows.Controls.CalendarSelectionMode.None>, расширяет диапазон выбранных дат.|  
|ГЛАВНАЯ|<xref:System.Windows.Controls.CalendarMode.Month>|Изменения <xref:System.Windows.Controls.Calendar.SelectedDate%2A> первый день текущего месяца.|  
|ГЛАВНАЯ|<xref:System.Windows.Controls.CalendarMode.Year>|Изменяет значение месяца для <xref:System.Windows.Controls.Calendar.DisplayDate%2A> к первому месяцу года. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Не изменяется.|  
|ГЛАВНАЯ|<xref:System.Windows.Controls.CalendarMode.Decade>|Изменяет значение года для <xref:System.Windows.Controls.Calendar.DisplayDate%2A> на первый год десятилетия. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Не изменяется.|  
|END|<xref:System.Windows.Controls.CalendarMode.Month>|Изменения <xref:System.Windows.Controls.Calendar.SelectedDate%2A> в последний день текущего месяца.|  
|END|<xref:System.Windows.Controls.CalendarMode.Year>|Изменяет значение месяца для <xref:System.Windows.Controls.Calendar.DisplayDate%2A> последний месяц года. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Не изменяется.|  
|END|<xref:System.Windows.Controls.CalendarMode.Decade>|Изменяет значение года для <xref:System.Windows.Controls.Calendar.DisplayDate%2A> за прошлый год десятилетия. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Не изменяется.|  
|CTRL + СТРЕЛКА ВВЕРХ|Любой|Переключается на следующий больший <xref:System.Windows.Controls.Calendar.DisplayMode%2A>. Если <xref:System.Windows.Controls.Calendar.DisplayMode%2A> уже <xref:System.Windows.Controls.CalendarMode.Decade>, никаких действий.|  
|CTRL+СТРЕЛКА ВНИЗ|Любой|Переключается на следующий более мелкие <xref:System.Windows.Controls.Calendar.DisplayMode%2A>. Если <xref:System.Windows.Controls.Calendar.DisplayMode%2A> уже <xref:System.Windows.Controls.CalendarMode.Month>, никаких действий.|  
|ПРОБЕЛ или ввод|<xref:System.Windows.Controls.CalendarMode.Year> или <xref:System.Windows.Controls.CalendarMode.Decade>|Коммутаторы <xref:System.Windows.Controls.Calendar.DisplayMode%2A> для <xref:System.Windows.Controls.CalendarMode.Month> или <xref:System.Windows.Controls.CalendarMode.Year> представленный установлен фокус.|  
  
## <a name="see-also"></a>См. также  
 [Элементы управления](../../../../docs/framework/wpf/controls/index.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)
