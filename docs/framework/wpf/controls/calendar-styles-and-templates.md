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
ms.openlocfilehash: 64cb62a3459a3eeea6aa5e91b433a58a88ab08ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283556"
---
# <a name="calendar-styles-and-templates"></a>Стили и шаблоны элемента Calendar
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Calendar>. Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления. Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="calendar-parts"></a>Элементы календаря  
 В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.Calendar>.  
  
|Отделение|Введите|Описание|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|Отображаемый в данный момент месяц или год на <xref:System.Windows.Controls.Calendar>.|  
|PART_Root|<xref:System.Windows.Controls.Panel>|Панель, содержащая <xref:System.Windows.Controls.Primitives.CalendarItem>.|  
  
## <a name="calendar-states"></a>Состояния календаря  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Calendar>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|----------------------|---------------------------|-----------------|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
  
## <a name="calendaritem-parts"></a>Календаритем части  
 В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.Primitives.CalendarItem>.  
  
|Отделение|Введите|Описание|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|Корень элемента управления.|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|Кнопка, отображающая предыдущую страницу календаря при ее щелчке.|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|Кнопка, отображающая следующую страницу календаря при ее нажатии.|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|Кнопка, позволяющая переключение между режимом месяца, режимом года и режимом десятилетия.|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|Размещает содержимое в режиме «в месяц».|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|Размещает содержимое в режиме года или десятилетия.|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|Наложение для отключенного состояния.|  
|дайтитлетемплате|<xref:System.Windows.DataTemplate>|<xref:System.Windows.DataTemplate>, описывающий визуальную структуру.|  
  
## <a name="calendaritem-states"></a>Состояния Календаритем  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.CalendarItem>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Нормальное состояние|CommonStates|Состояние по умолчанию.|  
|Отключенное состояние|CommonStates|Состояние календаря, когда свойство <xref:System.Windows.UIElement.IsEnabled%2A> `false`.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
  
## <a name="calendardaybutton-parts"></a>Календардайбуттон части  
 Элемент управления <xref:System.Windows.Controls.Primitives.CalendarDayButton> не имеет именованных частей.  
  
## <a name="calendardaybutton-states"></a>Состояния Календардайбуттон  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.CalendarDayButton>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Нормальный|CommonStates|Состояние по умолчанию.|  
|Отключено.|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton> отключена.|  
|MouseOver|CommonStates|Указатель мыши располагается на <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Нажато|CommonStates|Нажата <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Выбранные|SelectionStates|Кнопка выбрана.|  
|Unselected|SelectionStates|Кнопка не выбрана.|  
|календарбуттонфокусед|календарбуттонфокусстатес|Кнопка имеет фокус.|  
|календарбуттонунфокусед|календарбуттонфокусстатес|Кнопка не имеет фокуса.|  
|Focused|FocusStates|Кнопка имеет фокус.|  
|Без фокуса ввода|FocusStates|Кнопка не имеет фокуса.|  
|Активно|активестатес|Кнопка активна.|  
|Неактивно|активестатес|Кнопка неактивна.|  
|регулардай|дайстатес|Кнопка не представляет <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|Сегодня|дайстатес|Кнопка представляет <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|нормалдай|блаккаутдайстатес|Кнопка представляет день, который можно выбрать.|  
|блаккаутдай|блаккаутдайстатес|Кнопка представляет день, который не может быть выбран.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
  
## <a name="calendarbutton-parts"></a>Календарбуттон части  
 Элемент управления <xref:System.Windows.Controls.Primitives.CalendarButton> не имеет именованных частей.  
  
## <a name="calendarbutton-states"></a>Состояния Календарбуттон  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.CalendarButton>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Нормальный|CommonStates|Состояние по умолчанию.|  
|Отключено.|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton> отключена.|  
|MouseOver|CommonStates|Указатель мыши располагается на <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Нажато|CommonStates|Нажата <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Выбранные|SelectionStates|Кнопка выбрана.|  
|Unselected|SelectionStates|Кнопка не выбрана.|  
|календарбуттонфокусед|календарбуттонфокусстатес|Кнопка имеет фокус.|  
|календарбуттонунфокусед|календарбуттонфокусстатес|Кнопка не имеет фокуса.|  
|Focused|FocusStates|Кнопка имеет фокус.|  
|Без фокуса ввода|FocusStates|Кнопка не имеет фокуса.|  
|Активно|активестатес|Кнопка активна.|  
|Неактивно|активестатес|Кнопка неактивна.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
  
## <a name="calendar-controltemplate-example"></a>Пример ControlTemplate для календаря  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Calendar> и связанных типов.  
  
 [!code-xaml[ControlTemplateExamples#Calendar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
 В предыдущем примере используется один или несколько из следующих ресурсов.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стили и шаблоны элемента управления](control-styles-and-templates.md)
- [Настройка элементов управления](control-customization.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md)
