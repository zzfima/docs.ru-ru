---
title: "Стили и шаблоны элемента ToolBar | Microsoft Docs"
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
  - "ControlTemplate [WPF], ToolBar"
  - "части [WPF], ToolBar"
  - "состояния [WPF], ToolBar"
  - "стили [WPF], ToolBar"
  - "шаблоны [WPF], ToolBar"
  - "ToolBar [WPF], стили и шаблоны"
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Стили и шаблоны элемента ToolBar
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ToolBar>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части ToolBar  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.ToolBar>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_ToolBarPanel|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|Объект, который содержит элементы управления в элементе управления <xref:System.Windows.Controls.ToolBar>.|  
|PART\_ToolBarOverflowPanel|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Объект, содержащий элементы управления, которые выходят за пределы области элемента управления <xref:System.Windows.Controls.ToolBar>.|  
  
 При создании шаблона <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ToolBar> шаблон может содержать часть <xref:System.Windows.Controls.ItemsPresenter> в элементе управления <xref:System.Windows.Controls.ScrollViewer>.  \(Элемент управления <xref:System.Windows.Controls.ItemsPresenter> отображает каждый элемент в элементе управления <xref:System.Windows.Controls.ToolBar>; элемент управления <xref:System.Windows.Controls.ScrollViewer> обеспечивает прокрутку в элементе управления\).  Если элемент управления <xref:System.Windows.Controls.ItemsPresenter> не является непосредственным дочерним элементом элемента управления <xref:System.Windows.Controls.ScrollViewer>, необходимо присвоить элементу управления <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.  
  
## Состояния ToolBar  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.ToolBar>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример шаблона ControlTemplate ToolBar  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xml[ControlTemplateExamples#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 В предыдущем примере используется один или несколько следующих ресурсов.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. на веб\-странице [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## См. также  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Стили и шаблоны элемента Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)