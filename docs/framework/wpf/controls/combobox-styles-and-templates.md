---
title: Стили и шаблоны элемента ComboBox
ms.date: 03/30/2017
helpviewer_keywords:
- ComboBox [WPF], styles and templates
- states [WPF], ComboBox
- ControlTemplate [WPF], ComboBox
- styles [WPF], ComboBox
- templates [WPF], ComboBox
- parts [WPF], ComboBox
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
ms.openlocfilehash: 92671001733f525188ba3c7bcf3ed3c55615e301
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283791"
---
# <a name="combobox-styles-and-templates"></a>Стили и шаблоны элемента ComboBox
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ComboBox>. Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления. Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="combobox-parts"></a>Части поля со списком  
 В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.ComboBox>.  
  
|Отделение|Введите|Описание|  
|-|-|-|  
|PART_EditableTextBox|<xref:System.Windows.Controls.TextBox>|Содержит текст <xref:System.Windows.Controls.ComboBox>.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Раскрывающийся список, содержащий элементы в поле со списком.|  
  
 При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ComboBox>шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в пределах <xref:System.Windows.Controls.ScrollViewer>. (<xref:System.Windows.Controls.ItemsPresenter> отображает каждый элемент в <xref:System.Windows.Controls.ComboBox>; <xref:System.Windows.Controls.ScrollViewer> включает прокрутку в элементе управления).  Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым дочерним элементом <xref:System.Windows.Controls.ScrollViewer>, необходимо присвоить <xref:System.Windows.Controls.ItemsPresenter> имя, `ItemsPresenter`.  
  
## <a name="combobox-states"></a>Состояния ComboBox  
 В следующей таблице перечислены состояния для элемента управления <xref:System.Windows.Controls.ComboBox>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Нормальный|CommonStates|Состояние по умолчанию.|  
|Отключено.|CommonStates|Элемент управления отключен.|  
|MouseOver|CommonStates|Указатель мыши находится над элементом управления <xref:System.Windows.Controls.ComboBox>.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|фокуседдропдовн|FocusStates|Раскрывающийся список для <xref:System.Windows.Controls.ComboBox> имеет фокус.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
|Editable|едитстатес|Значение свойства <xref:System.Windows.Controls.ComboBox.IsEditable%2A> — `true`.|  
|Недоступными|едитстатес|Значение свойства <xref:System.Windows.Controls.ComboBox.IsEditable%2A> — `false`.|  
  
## <a name="comboboxitem-parts"></a>Комбобокситем части  
 Элемент управления <xref:System.Windows.Controls.ComboBoxItem> не имеет именованных частей.  
  
## <a name="comboboxitem-states"></a>Состояния Комбобокситем  
 В следующей таблице перечислены состояния для элемента управления <xref:System.Windows.Controls.ComboBoxItem>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Нормальный|CommonStates|Состояние по умолчанию.|  
|Отключено.|CommonStates|Элемент управления отключен.|  
|MouseOver|CommonStates|Указатель мыши находится над элементом управления <xref:System.Windows.Controls.ComboBox>.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|Выбранные|SelectionStates|Элемент выбран в данный момент.|  
|Unselected|SelectionStates|Элемент не выбран.|  
|SelectedUnfocused|SelectionStates|Элемент выбран, но не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
  
## <a name="combobox-controltemplate-example"></a>Пример поля ControlTemplate ComboBox  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ComboBox> и связанных типов.  
  
 [!code-xaml[ControlTemplateExamples#ComboBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
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
