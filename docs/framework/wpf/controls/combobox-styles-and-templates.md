---
title: "Стили и шаблоны элемента ComboBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ComboBox [WPF], styles and templates
- states [WPF], ComboBox
- ControlTemplate [WPF], ComboBox
- styles [WPF], ComboBox
- templates [WPF], ComboBox
- parts [WPF], ComboBox
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd89d2150b2623a749614ab01aa767997dc4bdf3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="combobox-styles-and-templates"></a>Стили и шаблоны элемента ComboBox
В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.ComboBox> элемента управления. Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="combobox-parts"></a>Части поля со списком  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.ComboBox> элемента управления.  
  
|Отделение|Тип|Описание|  
|-|-|-|  
|PART_EditableTextBox|<xref:System.Windows.Controls.TextBox>|Содержит текст <xref:System.Windows.Controls.ComboBox>.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Раскрывающийся список, содержащий элементы в поле со списком.|  
  
 При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ComboBox>, шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer>. ( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.ComboBox>; <xref:System.Windows.Controls.ScrollViewer> разрешает прокрутку в элементе управления).  Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым потомком <xref:System.Windows.Controls.ScrollViewer>, вы должны предоставить <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.  
  
## <a name="combobox-states"></a>Поле со списком состояний  
 В следующей таблице перечислены состояния для <xref:System.Windows.Controls.ComboBox> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|Отключено|CommonStates|Элемент управления отключен.|  
|MouseOver|CommonStates|Указатель мыши находится над <xref:System.Windows.Controls.ComboBox> элемента управления.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|FocusedDropDown|FocusStates|В раскрывающемся списке для <xref:System.Windows.Controls.ComboBox> имеет фокус.|  
|Valid|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|Для редактирования|EditStates|Значение свойства <xref:System.Windows.Controls.ComboBox.IsEditable%2A> — `true`.|  
|Недоступными для редактирования|EditStates|Значение свойства <xref:System.Windows.Controls.ComboBox.IsEditable%2A> — `false`.|  
  
## <a name="comboboxitem-parts"></a>Части руководство.  
 <xref:System.Windows.Controls.ComboBoxItem> Управления не имеет именованных частей.  
  
## <a name="comboboxitem-states"></a>Состояния руководство.  
 В следующей таблице перечислены состояния для <xref:System.Windows.Controls.ComboBoxItem> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|Отключено|CommonStates|Элемент управления отключен.|  
|MouseOver|CommonStates|Указатель мыши находится над <xref:System.Windows.Controls.ComboBox> элемента управления.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|Selected|SelectionStates|В настоящее время выбран элемент.|  
|Unselected|SelectionStates|Элемент не выбран.|  
|SelectedUnfocused|SelectionStates|Элемент выбран, но не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
  
## <a name="combobox-controltemplate-example"></a>Пример шаблона элемента управления ComboBox  
 В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ComboBox> управления и связанных типов.  
  
 [!code-xaml[ControlTemplateExamples#ComboBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
 В предыдущем примере используется один или несколько из следующих ресурсов.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Стили и шаблоны элемента управления](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
