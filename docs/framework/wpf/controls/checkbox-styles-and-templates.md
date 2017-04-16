---
title: "Стили и шаблоны элемента CheckBox | Microsoft Docs"
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
  - "CheckBox [WPF], стили и шаблоны"
  - "ControlTemplate [WPF], CheckBox"
  - "части [WPF], CheckBox"
  - "состояния [WPF], CheckBox"
  - "стили [WPF], CheckBox"
  - "шаблоны [WPF], CheckBox"
ms.assetid: bfdaec96-d101-4d3d-864d-c27e6b621d03
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Стили и шаблоны элемента CheckBox
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.CheckBox>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части CheckBox  
 Элемент управления <xref:System.Windows.Controls.CheckBox> не имеет именованных частей.  
  
## Состояния CheckBox  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.CheckBox>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|---------------------|--------------------------|--------------|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|  
|Pressed|CommonStates|Элемент управления нажат.|  
|Disabled|CommonStates|Элемент управления отключен.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Unfocused|FocusStates|Элемент управления не имеет фокуса.|  
|Установлен|CheckStates|Параметр <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `true`.|  
|Снят|CheckStates|Параметр <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `false`.|  
|Indeterminate|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> равно `true`, а <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> равно `null`.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример шаблона ControlTemplate CheckBox  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.CheckBox>.  
  
 [!code-xml[ControlTemplateExamples#CheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
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