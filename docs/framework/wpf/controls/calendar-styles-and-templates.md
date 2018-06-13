---
title: Стили и шаблоны элемента Calendar
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Calendar
- templates [WPF], Calendar
- states [WPF], Calendar
- parts [WPF], Calendar
- Calendar [WPF], styles and templates
- ControlTemplate [WPF], Calendar
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
ms.openlocfilehash: 5398828d1526436ab5abbbd2e87515018b0cd8bf
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457528"
---
# <a name="calendar-styles-and-templates"></a>Стили и шаблоны элемента Calendar
В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Calendar> элемента управления. Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="calendar-parts"></a>Элементы календаря  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Calendar> элемента управления.  
  
|Отделение|Тип|Описание|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|Текущий отображаемый месяц или год в <xref:System.Windows.Controls.Calendar>.|  
|PART_Root|<xref:System.Windows.Controls.Panel>|Панель, которая содержит <xref:System.Windows.Controls.Primitives.CalendarItem>.|  
  
## <a name="calendar-states"></a>Состояния календаря  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Calendar> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|----------------------|---------------------------|-----------------|  
|Valid|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
  
## <a name="calendaritem-parts"></a>Части элемента календаря, имеющего  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Primitives.CalendarItem> элемента управления.  
  
|Отделение|Тип|Описание|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|Корневой элемент управления.|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|Кнопка, Отображение предыдущей страницы календаря, при щелчке.|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|Кнопка, Отображение следующей страницы календаря, при щелчке.|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|Кнопка, допускают переключение между режим месяц, год режим и режим десятилетия.|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|Где размещается содержимое, в режиме месяца.|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|Размещает содержимое в режиме года или десятилетия.|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|Перекрытие для отключенного состояния.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|<xref:System.Windows.DataTemplate> , Описывающий визуальную структуру.|  
  
## <a name="calendaritem-states"></a>Состояния элемента календаря, имеющего  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.CalendarItem> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Нормальное состояние|CommonStates|Состояние по умолчанию.|  
|Отключенное состояние|CommonStates|Состояние календаря при <xref:System.Windows.UIElement.IsEnabled%2A> свойство `false`.|  
|Valid|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|Valid|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
  
## <a name="calendardaybutton-parts"></a>CalendarDayButton частей  
 <xref:System.Windows.Controls.Primitives.CalendarDayButton> Управления не имеет именованных частей.  
  
## <a name="calendardaybutton-states"></a>CalendarDayButton состояний  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.CalendarDayButton> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|Отключено|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton> Отключена.|  
|MouseOver|CommonStates|Указатель мыши наведен на <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Нажато|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton> Нажата.|  
|Selected|SelectionStates|Кнопка нажата.|  
|Unselected|SelectionStates|Не выбран.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Кнопка имеет фокус.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Кнопка не имеет фокуса.|  
|Focused|FocusStates|Кнопка имеет фокус.|  
|Без фокуса ввода|FocusStates|Кнопка не имеет фокуса.|  
|Активная|ActiveStates|Кнопка активна.|  
|Неактивные|ActiveStates|Кнопка неактивна.|  
|RegularDay|DayStates|Представляет кнопку <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|Сегодня|DayStates|Представляет кнопку <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|NormalDay|BlackoutDayStates|Кнопка представляет день, который может быть выбран.|  
|BlackoutDay|BlackoutDayStates|Кнопка представляет день, который не может быть выбран.|  
|Valid|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
  
## <a name="calendarbutton-parts"></a>CalendarButton частей  
 <xref:System.Windows.Controls.Primitives.CalendarButton> Управления не имеет именованных частей.  
  
## <a name="calendarbutton-states"></a>CalendarButton состояний  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.CalendarButton> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|Отключено|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton> Отключена.|  
|MouseOver|CommonStates|Указатель мыши наведен на <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Нажато|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton> Нажата.|  
|Selected|SelectionStates|Кнопка нажата.|  
|Unselected|SelectionStates|Не выбран.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Кнопка имеет фокус.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Кнопка не имеет фокуса.|  
|Focused|FocusStates|Кнопка имеет фокус.|  
|Без фокуса ввода|FocusStates|Кнопка не имеет фокуса.|  
|Активная|ActiveStates|Кнопка активна.|  
|Неактивные|ActiveStates|Кнопка неактивна.|  
|Valid|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
  
## <a name="calendar-controltemplate-example"></a>Пример шаблона элемента управления Calendar  
 В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Calendar> управления и связанных типов.  
  
 [!code-xaml[ControlTemplateExamples#Calendar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
 В предыдущем примере используется один или несколько из следующих ресурсов.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Стили и шаблоны элемента управления](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
