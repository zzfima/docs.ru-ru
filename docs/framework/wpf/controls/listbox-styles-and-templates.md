---
title: Стили и шаблоны элемента ListBox
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
ms.openlocfilehash: cb7043a21020193a4b2a2569ec610f311834a698
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283755"
---
# <a name="listbox-styles-and-templates"></a>Стили и шаблоны элемента ListBox
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ListBox>. Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления. Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="listbox-parts"></a>Части ListBox  
 Элемент управления <xref:System.Windows.Controls.ListBox> не имеет именованных частей.  
  
 При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ListBox>шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в пределах <xref:System.Windows.Controls.ScrollViewer>. (<xref:System.Windows.Controls.ItemsPresenter> отображает каждый элемент в <xref:System.Windows.Controls.ListBox>; <xref:System.Windows.Controls.ScrollViewer> включает прокрутку в элементе управления).  Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым дочерним элементом <xref:System.Windows.Controls.ScrollViewer>, необходимо присвоить <xref:System.Windows.Controls.ItemsPresenter> имя, `ItemsPresenter`.  
  
## <a name="listbox-states"></a>Состояния ListBox  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.ListBox>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Valid|ValidationStates|Элемент управления является допустимым.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
  
## <a name="listboxitem-parts"></a>Части ListBoxItem  
 Элемент управления <xref:System.Windows.Controls.ListBoxItem> не имеет именованных частей.  
  
## <a name="listboxitem-states"></a>Состояния ListBoxItem  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.ListBox>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Нормальный|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|  
|Отключено.|CommonStates|Элемент отключен.|  
|Focused|FocusStates|Элемент имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент не имеет фокуса.|  
|Unselected|SelectionStates|Элемент не выбран.|  
|Выбранные|SelectionStates|Этот элемент сейчас выбран.|  
|SelectedUnfocused|SelectionStates|Элемент выбран, но не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
  
## <a name="listbox-controltemplate-example"></a>Пример шаблона элемента управления ControlTemplate для ListBox  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элементов управления <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-xaml[ControlTemplateExamples#ListBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
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
