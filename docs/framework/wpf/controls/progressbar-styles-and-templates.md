---
title: "Стили и шаблоны элемента ProgressBar | Microsoft Docs"
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
  - "ControlTemplate [WPF], ProgressBar"
  - "части [WPF], ProgressBar"
  - "ProgressBar [WPF], стили и шаблоны"
  - "состояния [WPF], ProgressBar"
  - "стили [WPF], ProgressBar"
  - "шаблоны [WPF], ProgressBar"
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Стили и шаблоны элемента ProgressBar
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ProgressBar>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части ProgressBar  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.ProgressBar>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_Indicator|<xref:System.Windows.FrameworkElement>|Объект, указывающий ход выполнения.|  
|PART\_Track|<xref:System.Windows.FrameworkElement>|Объект, определяющий путь к индикатору хода выполнения.|  
|PART\_GlowRect|<xref:System.Windows.FrameworkElement>|Объект, оформляющий индикатор выполнения.|  
  
## Состояния ProgressBar  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.ProgressBar>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|---------------------|--------------------------|--------------|  
|Determinate|CommonStates|Элемент управления <xref:System.Windows.Controls.ProgressBar> показывает ход выполнения на основе свойства <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.|  
|Indeterminate|CommonStates|Элемент управления <xref:System.Windows.Controls.ProgressBar> показывает общий ход выполнения с помощью повторяющегося рисунка.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример шаблона ControlTemplate для элемента управления ProgressBar  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ProgressBar>.  
  
 [!code-xml[ControlTemplateExamples#ProgressBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
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