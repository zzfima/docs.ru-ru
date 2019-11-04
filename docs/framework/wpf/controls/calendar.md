---
title: Календарь
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: e99a716e7ca8f7b2c9ed11543f37e0b8cb7422a6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460808"
---
# <a name="calendar"></a>Календарь
Календарь позволяет пользователю выбрать дату с помощью отображения визуального календаря.  
  
 Элемент управления <xref:System.Windows.Controls.Calendar> может использоваться самостоятельно или в виде раскрывающейся части элемента управления <xref:System.Windows.Controls.DatePicker>. Для получения дополнительной информации см. <xref:System.Windows.Controls.DatePicker>.  
  
 На следующем рисунке показаны два элемента управления <xref:System.Windows.Controls.Calendar>: один с выбранными значениями и датами отключения, а другой — без.  
  
 ![Элементы управления Calendar](./media/ndp-calendarcontrols.png "NDP_CalendarControls")  
Элементы управления календаря  
  
 В следующей таблице приведены сведения о задачах, которые обычно связаны с <xref:System.Windows.Controls.Calendar>.  
  
|Задача|Реализация|  
|----------|--------------------|  
|Укажите даты, которые не могут быть выбраны.|Используйте свойство <xref:System.Windows.Controls.Calendar.BlackoutDates%2A>.|  
|<xref:System.Windows.Controls.Calendar> отобразить месяц, целый год или десятилетие.|Задайте для свойства <xref:System.Windows.Controls.Calendar.DisplayMode%2A> значение месяц, год или десятилетие.|  
|Укажите, может ли пользователь выбрать дату, диапазон дат или несколько диапазонов дат.|Используйте <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.|  
|Укажите диапазон дат, отображаемых <xref:System.Windows.Controls.Calendar>.|Используйте свойства <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> и <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A>.|  
|Укажите, выделена ли текущая дата.|Используйте свойство <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>. По умолчанию <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> `true`.|  
|Измените размер <xref:System.Windows.Controls.Calendar>.|Используйте <xref:System.Windows.Controls.Viewbox> или задайте для свойства <xref:System.Windows.FrameworkElement.LayoutTransform%2A> значение <xref:System.Windows.Media.ScaleTransform>. Обратите внимание, что если задать свойства <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.Calendar>, реальный календарь не изменит свой размер.|  
  
 Элемент управления <xref:System.Windows.Controls.Calendar> обеспечивает базовую навигацию с помощью мыши или клавиатуры. В следующей таблице представлены сведения о переходе с помощью клавиатуры.  
  
|Сочетание клавиш|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|Действие|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|СПИСКОМ|<xref:System.Windows.Controls.CalendarMode.Month>|Изменяет свойство <xref:System.Windows.Controls.Calendar.SelectedDate%2A>, если свойство <xref:System.Windows.Controls.Calendar.SelectionMode%2A> не имеет значение <xref:System.Windows.Controls.CalendarSelectionMode.None>.|  
|СПИСКОМ|<xref:System.Windows.Controls.CalendarMode.Year>|Изменяет месяц свойства <xref:System.Windows.Controls.Calendar.DisplayDate%2A>. Обратите внимание, что <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|СПИСКОМ|<xref:System.Windows.Controls.CalendarMode.Decade>|Изменяет год <xref:System.Windows.Controls.Calendar.DisplayDate%2A>. Обратите внимание, что <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|SHIFT + СТРЕЛКА|<xref:System.Windows.Controls.CalendarMode.Month>|Если параметр <xref:System.Windows.Controls.Calendar.SelectionMode%2A> не имеет значение <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> или <xref:System.Windows.Controls.CalendarSelectionMode.None>, расширяет диапазон выбранных дат.|  
|ГЛАВНАЯ|<xref:System.Windows.Controls.CalendarMode.Month>|Изменяет <xref:System.Windows.Controls.Calendar.SelectedDate%2A> на первый день текущего месяца.|  
|ГЛАВНАЯ|<xref:System.Windows.Controls.CalendarMode.Year>|Изменяет месяц <xref:System.Windows.Controls.Calendar.DisplayDate%2A> на первый месяц года. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|ГЛАВНАЯ|<xref:System.Windows.Controls.CalendarMode.Decade>|Изменяет год <xref:System.Windows.Controls.Calendar.DisplayDate%2A> на первый год десятилетия. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|END|<xref:System.Windows.Controls.CalendarMode.Month>|Изменяет <xref:System.Windows.Controls.Calendar.SelectedDate%2A> на последний день текущего месяца.|  
|END|<xref:System.Windows.Controls.CalendarMode.Year>|Изменяет месяц <xref:System.Windows.Controls.Calendar.DisplayDate%2A> на последний месяц года. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|END|<xref:System.Windows.Controls.CalendarMode.Decade>|Изменяет год <xref:System.Windows.Controls.Calendar.DisplayDate%2A> на последний год десятилетия. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|CTRL + СТРЕЛКА ВВЕРХ|Любой|Переключается на следующие более крупные <xref:System.Windows.Controls.Calendar.DisplayMode%2A>. Если <xref:System.Windows.Controls.Calendar.DisplayMode%2A> уже <xref:System.Windows.Controls.CalendarMode.Decade>, никаких действий не происходит.|  
|CTRL+СТРЕЛКА ВНИЗ|Любой|Переключается на следующий <xref:System.Windows.Controls.Calendar.DisplayMode%2A>меньшего размера. Если <xref:System.Windows.Controls.Calendar.DisplayMode%2A> уже <xref:System.Windows.Controls.CalendarMode.Month>, никаких действий не происходит.|  
|ПРОБЕЛ или ввод|<xref:System.Windows.Controls.CalendarMode.Year> или <xref:System.Windows.Controls.CalendarMode.Decade>|Переключается <xref:System.Windows.Controls.Calendar.DisplayMode%2A> <xref:System.Windows.Controls.CalendarMode.Month> или <xref:System.Windows.Controls.CalendarMode.Year>, представленных элементом с сортировкой.|  
  
## <a name="see-also"></a>См. также

- [Элементы управления](index.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
