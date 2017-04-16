---
title: "Стили и шаблоны элемента ContextMenu | Microsoft Docs"
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
  - "ContextMenu [WPF], стили и шаблоны"
  - "ControlTemplate [WPF], ContextMenu"
  - "части [WPF], ContextMenu"
  - "состояния [WPF], ContextMenu"
  - "стили [WPF], ContextMenu"
  - "шаблоны [WPF], ContextMenu"
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Стили и шаблоны элемента ContextMenu
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ContextMenu>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части ContextMenu  
 Элемент управления <xref:System.Windows.Controls.ContextMenu> не имеет именованных частей.  
  
 При создании шаблона <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ContextMenu> шаблон может содержать часть <xref:System.Windows.Controls.ItemsPresenter> в элементе управления <xref:System.Windows.Controls.ScrollViewer>.  \(Элемент управления <xref:System.Windows.Controls.ItemsPresenter> отображает каждый элемент в элементе управления <xref:System.Windows.Controls.ContextMenu>; элемент управления <xref:System.Windows.Controls.ScrollViewer> обеспечивает прокрутку в элементе управления\).  Если элемент управления <xref:System.Windows.Controls.ItemsPresenter> не является непосредственным дочерним элементом элемента управления <xref:System.Windows.Controls.ScrollViewer>, необходимо присвоить элементу управления <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.  
  
## Состояния ContextMenu  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.ContextMenu>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример ControlTemplate ContextMenu  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ContextMenu>.  
  
 [!code-xml[ControlTemplateExamples#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 Элемент управления <xref:System.Windows.Controls.ControlTemplate> использует следующие ресурсы.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. на веб\-странице [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## См. также  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Стили и шаблоны элемента Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)