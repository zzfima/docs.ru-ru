---
title: "Стили и шаблоны элемента Frame | Microsoft Docs"
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
  - "ControlTemplate [WPF], Frame"
  - "Фрейм [WPF], стили и шаблоны"
  - "части [WPF], Frame"
  - "состояния [WPF], Frame"
  - "стили [WPF], Frame"
  - "шаблоны [WPF], Frame"
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Стили и шаблоны элемента Frame
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Frame>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части Frame  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.Frame>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_FrameCP|<xref:System.Windows.Controls.ContentPresenter>|Область содержимого.|  
  
## Состояния Frame  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.Frame>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример шаблона элемента управления ControlTemplate элемента Frame  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Frame>.  
  
 [!code-xml[ControlTemplateExamples#Frame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
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