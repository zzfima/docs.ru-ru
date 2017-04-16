---
title: "Стили и шаблоны элемента ScrollViewer | Microsoft Docs"
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
  - "ControlTemplate [WPF], ScrollViewer"
  - "части [WPF], ScrollViewer"
  - "ScrollViewer [WPF], стили и шаблоны"
  - "состояния [WPF], ScrollViewer"
  - "стили [WPF], ScrollViewer"
  - "шаблоны [WPF], ScrollViewer"
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Стили и шаблоны элемента ScrollViewer
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ScrollViewer>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части ScrollViewer  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.ScrollViewer>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_ScrollContentPresenter|<xref:System.Windows.Controls.ScrollContentPresenter>|Заполнитель для содержимого в элементе управления <xref:System.Windows.Controls.ScrollViewer>.|  
|PART\_HorizontalScrollBar|<xref:System.Windows.Controls.Primitives.ScrollBar>|Класс <xref:System.Windows.Controls.Primitives.ScrollBar>, используемый для прокрутки содержимого по горизонтали.|  
|PART\_VerticalScrollBar|<xref:System.Windows.Controls.Primitives.ScrollBar>|Класс <xref:System.Windows.Controls.Primitives.ScrollBar>, используемый для прокрутки содержимого по вертикали.|  
  
## Состояния ScrollViewer  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.ScrollViewer>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример шаблона ControlTemplate ScrollViewer  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ScrollViewer>.  
  
 [!code-xml[ControlTemplateExamples#ScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
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