---
title: "Стили и шаблоны элемента ListView | Microsoft Docs"
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
  - "ControlTemplate [WPF], ListView"
  - "ListView [WPF], стили и шаблоны"
  - "части [WPF], ListView"
  - "состояния [WPF], ListView"
  - "стили [WPF], ListView"
  - "шаблоны [WPF], ListView"
ms.assetid: d2387356-2171-4785-822a-7247e024b4ee
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Стили и шаблоны элемента ListView
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ListView>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части ListView  
 Элемент управления <xref:System.Windows.Controls.ListView> не имеет именованных частей.  
  
 При создании шаблона <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ListView> шаблон может содержать часть <xref:System.Windows.Controls.ItemsPresenter> в элементе управления <xref:System.Windows.Controls.ScrollViewer>.  \(Элемент управления <xref:System.Windows.Controls.ItemsPresenter> отображает каждый элемент в элементе управления <xref:System.Windows.Controls.ListView>; элемент управления <xref:System.Windows.Controls.ScrollViewer> обеспечивает прокрутку в элементе управления\).  Если элемент управления <xref:System.Windows.Controls.ItemsPresenter> не является непосредственным дочерним элементом элемента управления <xref:System.Windows.Controls.ScrollViewer>, необходимо присвоить элементу управления <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.  
  
## Состояния ListView  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.ListView>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Части ListViewItem  
 Элемент управления <xref:System.Windows.Controls.ListViewItem> не имеет именованных частей.  
  
## Состояния ListViewItem  
 В следующей таблице перечислены состояния элемента управления <xref:System.Windows.Controls.ListViewItem>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|Disabled|CommonStates|Элемент управления отключен.|  
|MouseOver|CommonStates|Указатель мыши наведен на элемент управления <xref:System.Windows.Controls.ComboBox>.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Unfocused|FocusStates|Элемент управления не имеет фокуса.|  
|Выбран|SelectionStates|Элемент выбран.|  
|Не выбран|SelectionStates|Элемент не выбран.|  
|SelectedUnfocused|SelectionStates|Элемент выбран, но не имеет фокус.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Примеры шаблона ControlTemplate для элемента управления ListView  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ListView> и связанных с ним типов.  
  
 [!code-xml[ControlTemplateExamples#ListView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listview.xaml#listview)]  
  
 В примерах <xref:System.Windows.Controls.ControlTemplate> используется один или несколько следующих ресурсов.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. на веб\-странице [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## См. также  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Стили и шаблоны элемента Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)