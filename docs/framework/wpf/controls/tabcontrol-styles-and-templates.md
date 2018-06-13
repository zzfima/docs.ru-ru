---
title: Стили и шаблоны элемента TabControl
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TabControl
- TabControl [WPF], styles and templates [WPF]
- parts [WPF], TabControl
- styles [WPF], TabControl
- states [WPF], TabControl
- templates [WPF], TabControl
ms.assetid: f6b19a30-f10e-4fa1-96ce-f17a54092ab6
ms.openlocfilehash: b2de707a3ca37f9cb9c409c5513f6250faa9147d
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34456751"
---
# <a name="tabcontrol-styles-and-templates"></a>Стили и шаблоны элемента TabControl
В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.TabControl> элемента управления. Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="tabcontrol-parts"></a>Элементы управления TabControl  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.TabControl> элемента управления.  
  
|Отделение|Тип|Описание|  
|-|-|-|  
|PART_SelectedContentHost|<xref:System.Windows.Controls.ContentPresenter>|Объект, который отображает содержимое выбранного в данный момент <xref:System.Windows.Controls.TabItem>.|  
  
 При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.TabControl>, шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer>. ( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.TabControl>; <xref:System.Windows.Controls.ScrollViewer> разрешает прокрутку в элементе управления).  Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым потомком <xref:System.Windows.Controls.ScrollViewer>, вы должны предоставить <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.  
  
## <a name="tabcontrol-states"></a>Состояния элемента управления TabControl  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.TabControl> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|----------------------|---------------------------|-----------------|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|Отключено|CommonStates|Элемент управления отключен.|  
|Valid|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
  
## <a name="tabitem-parts"></a>TabItem частей  
 <xref:System.Windows.Controls.TabItem> Управления не имеет именованных частей.  
  
## <a name="tabitem-states"></a>TabItem состояний  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.TabItem> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|----------------------|---------------------------|-----------------|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен над элементом управления.|  
|Отключено|CommonStates|Элемент управления отключен.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|Selected|SelectionStates|Элемент управления выделен.|  
|Unselected|SelectionStates|Элемент управления не выбран.|  
|Valid|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
  
## <a name="tabcontrol-controltemplate-example"></a>Пример шаблона элемента управления TabControl  
 В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.TabControl> и <xref:System.Windows.Controls.TabItem> элементов управления.  
  
 [!code-xaml[ControlTemplateExamples#TabControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tabcontrol.xaml#tabcontrol)]  
  
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
