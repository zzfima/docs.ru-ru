---
title: "календарь | Microsoft Docs"
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
  - "Календарь - элемент управления [WPF]"
  - "элементы управления [WPF], календарь"
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# календарь
Элемент управления "Календарь" позволяет выбрать дату с помощью визуального календаря.  
  
 Элемент управления <xref:System.Windows.Controls.Calendar> может использоваться самостоятельно или в качестве раскрывающейся части элемента управления <xref:System.Windows.Controls.DatePicker>.  Дополнительные сведения см. в разделе <xref:System.Windows.Controls.DatePicker>.  
  
 На следующем рисунке показаны два элемента управления <xref:System.Windows.Controls.Calendar>: один с выбранными и затемненными датами, а другой без.  
  
 ![Элементы управления календаря](../../../../docs/framework/wpf/controls/media/ndp-calendarcontrols.png "NDP\_CalendarControls")  
Элементы управления "Календарь"  
  
 В следующей таблице приведены сведения о задачах, которые обычно связаны с элементом управления <xref:System.Windows.Controls.Calendar>.  
  
|Задача|Реализация|  
|------------|----------------|  
|Указание дат, которые не могут быть выбраны.|Используйте свойство <xref:System.Windows.Controls.Calendar.BlackoutDates%2A>.|  
|Элемент управления <xref:System.Windows.Controls.Calendar> должен отображать месяц, целый год или десятилетие.|Установите для свойства <xref:System.Windows.Controls.Calendar.DisplayMode%2A> значения для месяца, года или десятилетия.|  
|Указание, может ли пользователь выбрать дату, диапазон дат или несколько диапазонов дат.|Используйте свойство <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.|  
|Указание диапазона дат, которые отображаются элементом управления <xref:System.Windows.Controls.Calendar>.|Используйте свойства <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> и <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A>.|  
|Указание, выделяется ли текущая дата.|Используйте свойство <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>.  По умолчанию параметр <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> имеет значение `true`.|  
|Изменение размера элемента управления <xref:System.Windows.Controls.Calendar>.|Используйте элемент управления <xref:System.Windows.Controls.Viewbox> или задайте для свойства <xref:System.Windows.FrameworkElement.LayoutTransform%2A> значение <xref:System.Windows.Media.ScaleTransform>.  Обратите внимание, что при задании свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> элемента управления <xref:System.Windows.Controls.Calendar> фактический размер календаря не изменяется.|  
  
 Элемент управления <xref:System.Windows.Controls.Calendar> обеспечивает базовые возможности навигации с помощью мыши или клавиатуры.  Сведения о навигации с помощью клавиатуры приводятся в следующей таблице.  
  
|Сочетание клавиш|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|Действие|  
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|  
|СТРЕЛКА|<xref:System.Windows.Controls.CalendarMode>|Изменяет значение свойства <xref:System.Windows.Controls.Calendar.SelectedDate%2A> если свойству<xref:System.Windows.Controls.Calendar.SelectionMode%2A> не задано значение <xref:System.Windows.Controls.CalendarSelectionMode>.|  
|СТРЕЛКА|<xref:System.Windows.Controls.CalendarMode>|Изменяет значение месяца для свойства <xref:System.Windows.Controls.Calendar.DisplayDate%2A>.  Обратите внимание, что значение свойства <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|СТРЕЛКА|<xref:System.Windows.Controls.CalendarMode>|Изменяет значение года для свойства <xref:System.Windows.Controls.Calendar.DisplayDate%2A>.  Обратите внимание, что значение свойства <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|SHIFT \+ СТРЕЛКА|<xref:System.Windows.Controls.CalendarMode>|Если свойству<xref:System.Windows.Controls.Calendar.SelectionMode%2A> не задано значение поля <xref:System.Windows.Controls.CalendarSelectionMode> или <xref:System.Windows.Controls.CalendarSelectionMode>, расширяет диапазон выделенных дат.|  
|HOME|<xref:System.Windows.Controls.CalendarMode>|Изменяет значение свойства <xref:System.Windows.Controls.Calendar.SelectedDate%2A> на первую дату текущего месяца.|  
|HOME|<xref:System.Windows.Controls.CalendarMode>|Изменяет значение месяца для свойства <xref:System.Windows.Controls.Calendar.DisplayDate%2A> на первый месяц года.  Значение свойства <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|HOME|<xref:System.Windows.Controls.CalendarMode>|Изменяет значение года для свойства <xref:System.Windows.Controls.Calendar.DisplayDate%2A> на первый год десятилетия.  Значение свойства <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|END|<xref:System.Windows.Controls.CalendarMode>|Изменяет значение свойства <xref:System.Windows.Controls.Calendar.SelectedDate%2A> на последнюю дату текущего месяца.|  
|END|<xref:System.Windows.Controls.CalendarMode>|Изменяет значение месяца для свойства <xref:System.Windows.Controls.Calendar.DisplayDate%2A> на последний месяц года.  Значение свойства <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|END|<xref:System.Windows.Controls.CalendarMode>|Изменяет значение года для свойства <xref:System.Windows.Controls.Calendar.DisplayDate%2A> на последний год десятилетия.  Значение свойства <xref:System.Windows.Controls.Calendar.SelectedDate%2A> не изменяется.|  
|CTRL \+ СТРЕЛКА ВВЕРХ|Any|Переключается на следующий больший режим отображения <xref:System.Windows.Controls.Calendar.DisplayMode%2A>.  Если значение параметра <xref:System.Windows.Controls.Calendar.DisplayMode%2A> уже равно <xref:System.Windows.Controls.CalendarMode>, действия не выполняются.|  
|CTRL\+СТРЕЛКА ВНИЗ|Any|Переключается на следующий меньший режим отображения <xref:System.Windows.Controls.Calendar.DisplayMode%2A>.  Если значение параметра <xref:System.Windows.Controls.Calendar.DisplayMode%2A> уже равно <xref:System.Windows.Controls.CalendarMode>, действия не выполняются.|  
|ПРОБЕЛ или ВВОД|<xref:System.Windows.Controls.CalendarMode> или <xref:System.Windows.Controls.CalendarMode>|Переключает <xref:System.Windows.Controls.Calendar.DisplayMode%2A> на <xref:System.Windows.Controls.CalendarMode> или <xref:System.Windows.Controls.CalendarMode>, представленный элементом, который имеет фокус.|  
  
## См. также  
 [Элементы управления](../../../../docs/framework/wpf/controls/index.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)