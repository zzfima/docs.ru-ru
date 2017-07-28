---
title: "Стили и шаблоны элемента Calendar | Microsoft Docs"
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
  - "Календарь [WPF], стили и шаблоны"
  - "ControlTemplate [WPF], календарь"
  - "части [WPF], календарь"
  - "состояния [WPF], календарь"
  - "стили [WPF], календарь"
  - "шаблоны [WPF], календарь"
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Стили и шаблоны элемента Calendar
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Calendar>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части Calendar  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.Calendar>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|Месяц или год, отображаемый в данный момент в элементе управления <xref:System.Windows.Controls.Calendar>.|  
|PART\_Root|<xref:System.Windows.Controls.Panel>|Панель, которая содержит элемент <xref:System.Windows.Controls.Primitives.CalendarItem>.|  
  
## Состояния Calendar  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.Calendar>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|---------------------|--------------------------|--------------|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Части CalendarItem  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.Primitives.CalendarItem>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_Root|<xref:System.Windows.FrameworkElement>|Корень элемента управления.|  
|PART\_PreviousButton|<xref:System.Windows.Controls.Button>|Кнопка, при нажатии которой отображается предыдущая страница календаря.|  
|PART\_NextButton|<xref:System.Windows.Controls.Button>|Кнопка, при нажатии которой отображается следующая страница календаря.|  
|PART\_HeaderButton|<xref:System.Windows.Controls.Button>|Кнопка, позволяющая переключение между режимами месяца, года и десятилетия.|  
|PART\_MonthView|<xref:System.Windows.Controls.Grid>|Размещает содержимое в режиме месяца.|  
|PART\_YearView|<xref:System.Windows.Controls.Grid>|Размещает содержимое в режиме года или десятилетия.|  
|PART\_DisabledVisual|<xref:System.Windows.FrameworkElement>|Наложение для состояния disabled.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|Шаблон <xref:System.Windows.DataTemplate>, описывающий визуальную структуру.|  
  
## Состояния CalendarItem  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.Primitives.CalendarItem>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Normal|CommonStates|Состояние по умолчанию.|  
|Disabled|CommonStates|Состояние календаря, когда значение свойства <xref:System.Windows.UIElement.IsEnabled%2A> равно `false`.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Части CalendarDayButton  
 Элемент управления <xref:System.Windows.Controls.Primitives.CalendarDayButton> не имеет именованных частей.  
  
## Состояния CalendarDayButton  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.Primitives.CalendarDayButton>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|Disabled|CommonStates|Элемент управления <xref:System.Windows.Controls.Primitives.CalendarDayButton> отключен.|  
|MouseOver|CommonStates|Указатель мыши наведен на элемент управления <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Pressed|CommonStates|Элемент управления <xref:System.Windows.Controls.Primitives.CalendarDayButton> нажат.|  
|Выбран|SelectionStates|Кнопка выбрана.|  
|Не выбран|SelectionStates|Кнопка не выбрана.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Кнопка имеет фокус.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Кнопка не имеет фокуса.|  
|Focused|FocusStates|Кнопка имеет фокус.|  
|Unfocused|FocusStates|Кнопка не имеет фокуса.|  
|Активно|ActiveStates|Кнопка активна.|  
|Неактивный|ActiveStates|Кнопка не активна.|  
|RegularDay|DayStates|Кнопка не представляет свойство <xref:System.DateTime.Today%2A?displayProperty=fullName>.|  
|Today|DayStates|Кнопка представляет свойство <xref:System.DateTime.Today%2A?displayProperty=fullName>.|  
|NormalDay|BlackoutDayStates|Кнопка представляет день, который можно выбрать.|  
|BlackoutDay|BlackoutDayStates|Кнопка представляет день, который нельзя выбрать.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Части CalendarButton  
 Элемент управления <xref:System.Windows.Controls.Primitives.CalendarButton> не имеет именованных частей.  
  
## Состояния CalendarButton  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.Primitives.CalendarButton>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|Disabled|CommonStates|Элемент управления <xref:System.Windows.Controls.Primitives.CalendarButton> отключен.|  
|MouseOver|CommonStates|Указатель мыши наведен на элемент управления <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Pressed|CommonStates|Элемент управления <xref:System.Windows.Controls.Primitives.CalendarButton> нажат.|  
|Выбран|SelectionStates|Кнопка выбрана.|  
|Не выбран|SelectionStates|Кнопка не выбрана.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Кнопка имеет фокус.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Кнопка не имеет фокуса.|  
|Focused|FocusStates|Кнопка имеет фокус.|  
|Unfocused|FocusStates|Кнопка не имеет фокуса.|  
|Активно|ActiveStates|Кнопка активна.|  
|Неактивный|ActiveStates|Кнопка не активна.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример шаблона ControlTemplate для элемента управления Calendar  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Calendar> и связанных с ним типов.  
  
 [!code-xml[ControlTemplateExamples#Calendar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
 В предыдущем примере используется один или несколько следующих ресурсов.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. по адресу          [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041) .  
  
## См. также  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Стили и шаблоны элемента Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)