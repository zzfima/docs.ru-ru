---
title: "Стили и шаблоны элемента TextBox | Microsoft Docs"
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
  - "ControlTemplate [WPF], TextBox"
  - "части [WPF], TextBox"
  - "состояния [WPF], TextBox"
  - "стили [WPF], TextBox"
  - "шаблоны [WPF], TextBox"
  - "TextBox [WPF], стили и шаблоны"
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Стили и шаблоны элемента TextBox
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.TextBox>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части TextBox  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.TextBox>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_ContentHost|<xref:System.Windows.FrameworkElement>|Визуальный элемент, который может содержать элемент <xref:System.Windows.FrameworkElement>.  В этом элементе отображается текст, содержащийся в элементе управления <xref:System.Windows.Controls.TextBox>.|  
  
## Состояния TextBox  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.TextBox>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|---------------------|--------------------------|--------------|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|  
|Disabled|CommonStates|Элемент управления отключен.|  
|ReadOnly|CommonStates|Пользователь не может изменять текст в элементе управления <xref:System.Windows.Controls.TextBox>.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Unfocused|FocusStates|Элемент управления не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример ControlTemplate TextBox  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xml[ControlTemplateExamples#TextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
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