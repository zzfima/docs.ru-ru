---
title: "Стили и шаблоны элемента TreeView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ControlTemplate [WPF], TreeView"
  - "части [WPF], TreeView"
  - "состояния [WPF], TreeView"
  - "стили [WPF], TreeView"
  - "шаблоны [WPF], TreeView"
  - "TreeView [WPF], стили и шаблоны"
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Стили и шаблоны элемента TreeView
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.TreeView>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части TreeView  
 Элемент управления <xref:System.Windows.Controls.TreeView> не имеет именованных частей.  
  
 При создании шаблона <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.TreeView> шаблон может содержать часть <xref:System.Windows.Controls.ItemsPresenter> в элементе управления <xref:System.Windows.Controls.ScrollViewer>.  \(Элемент управления <xref:System.Windows.Controls.ItemsPresenter> отображает каждый элемент в элементе управления <xref:System.Windows.Controls.TreeView>; элемент управления <xref:System.Windows.Controls.ScrollViewer> обеспечивает прокрутку в элементе управления\).  Если элемент управления <xref:System.Windows.Controls.ItemsPresenter> не является непосредственным дочерним элементом элемента управления <xref:System.Windows.Controls.ScrollViewer>, необходимо присвоить элементу управления <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.  
  
## Состояния TreeView  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.TreeView>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Части TreeViewItem  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.TreeViewItem>.  
  
|Часть|Тип|Описание|  
|-----------|---------|--------------|  
|PART\_Header|<xref:System.Windows.FrameworkElement>|Визуальный элемент, включающий содержимое заголовка элемента управления <xref:System.Windows.Controls.TreeView>.|  
  
## Состояния TreeViewItem  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.TreeViewItem>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|---------------------|--------------------------|--------------|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши наведен на элемент управления <xref:System.Windows.Controls.TreeViewItem>.|  
|Disabled|CommonStates|Элемент управления <xref:System.Windows.Controls.TreeViewItem> отключен.|  
|Focused|FocusStates|Элемент управления <xref:System.Windows.Controls.TreeViewItem> имеет фокус.|  
|Unfocused|FocusStates|Элемент управления <xref:System.Windows.Controls.TreeViewItem> не имеет фокуса.|  
|разреженный|ExpansionStates|Элемент управления <xref:System.Windows.Controls.TreeViewItem> развернут.|  
|Collapsed|ExpansionStates|Элемент управления <xref:System.Windows.Controls.TreeViewItem> свернут.|  
|HasItems|HasItemsStates|Элемент управления <xref:System.Windows.Controls.TreeViewItem> имеет элементы.|  
|NoItems|HasItemsStates|Элемент управления <xref:System.Windows.Controls.TreeViewItem> не имеет элементов.|  
|Выбран|SelectionStates|Элемент управления <xref:System.Windows.Controls.TreeViewItem> выбран.|  
|SelectedInactive|SelectionStates|Элемент управления <xref:System.Windows.Controls.TreeViewItem> выбран, но не активен.|  
|Не выбран|SelectionStates|Элемент управления <xref:System.Windows.Controls.TreeViewItem> не выбран.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример шаблона элемента управления ControlTemplate элемента TreeView  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.TreeView> и связанных с ним типов.  
  
 [!code-xml[ControlTemplateExamples#TreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
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