---
title: Стили и шаблоны элемента TreeView
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TreeView
- templates [WPF], TreeView
- parts [WPF], TreeView
- states [WPF], TreeView
- styles [WPF], TreeView
- TreeView [WPF], styles and templates
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
ms.openlocfilehash: f6dbe54324a5ad5e2f85719d819c035abfd644b1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460185"
---
# <a name="treeview-styles-and-templates"></a>Стили и шаблоны элемента TreeView
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.TreeView>. Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="treeview-parts"></a>Части TreeView  
 Элемент управления <xref:System.Windows.Controls.TreeView> не имеет именованных частей.  
  
 При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.TreeView>шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в пределах <xref:System.Windows.Controls.ScrollViewer>. (<xref:System.Windows.Controls.ItemsPresenter> отображает каждый элемент в <xref:System.Windows.Controls.TreeView>; <xref:System.Windows.Controls.ScrollViewer> включает прокрутку в элементе управления).  Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым дочерним элементом <xref:System.Windows.Controls.ScrollViewer>, необходимо присвоить <xref:System.Windows.Controls.ItemsPresenter> имя, `ItemsPresenter`.  
  
## <a name="treeview-states"></a>Состояния TreeView  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.TreeView>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
  
## <a name="treeviewitem-parts"></a>TreeViewItem части  
 В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.TreeViewItem>.  
  
|Отделение|Type|Описание|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|Визуальный элемент, содержащий содержимое заголовка элемента управления <xref:System.Windows.Controls.TreeView>.|  
  
## <a name="treeviewitem-states"></a>Состояния TreeViewItem  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.TreeViewItem>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|----------------------|---------------------------|-----------------|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши располагается на <xref:System.Windows.Controls.TreeViewItem>.|  
|Отключено.|CommonStates|<xref:System.Windows.Controls.TreeViewItem> отключена.|  
|Focused|FocusStates|<xref:System.Windows.Controls.TreeViewItem> имеет фокус.|  
|Без фокуса ввода|FocusStates|<xref:System.Windows.Controls.TreeViewItem> не имеет фокуса.|  
|Разреженный|експансионстатес|Элемент управления <xref:System.Windows.Controls.TreeViewItem> развернут.|  
|Свернуто|експансионстатес|Элемент управления <xref:System.Windows.Controls.TreeViewItem> свернут.|  
|HasItems|хаситемсстатес|<xref:System.Windows.Controls.TreeViewItem> содержит элементы.|  
|Элементов|хаситемсстатес|<xref:System.Windows.Controls.TreeViewItem> не содержит элементов.|  
|Выбранные|SelectionStates|Выбрано <xref:System.Windows.Controls.TreeViewItem>.|  
|селектединактиве|SelectionStates|<xref:System.Windows.Controls.TreeViewItem> выбран, но неактивен.|  
|Unselected|SelectionStates|<xref:System.Windows.Controls.TreeViewItem> не выбран.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
  
## <a name="treeview-controltemplate-example"></a>Пример ControlTemplate в TreeView  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.TreeView> и связанных с ним типов.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 В предыдущем примере используется один или несколько из следующих ресурсов.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стили и шаблоны элемента управления](control-styles-and-templates.md)
- [Настройка элементов управления](control-customization.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
