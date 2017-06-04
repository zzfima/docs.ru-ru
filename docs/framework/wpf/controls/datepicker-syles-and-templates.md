---
title: "Стили и шаблоны элемента DatePicker | Microsoft Docs"
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
  - "ControlTemplate [WPF], DatePicker"
  - "DatePicker [WPF], стили и шаблоны"
  - "части [WPF], DatePicker"
  - "состояния [WPF], DatePicker"
  - "стили [WPF], DatePicker"
  - "шаблоны [WPF], DatePicker"
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Стили и шаблоны элемента DatePicker
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.DatePicker>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части DatePicker  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.DatePicker>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_Root|<xref:System.Windows.Controls.Grid>|Корень элемента управления.|  
|PART\_Button|<xref:System.Windows.Controls.Button>|Кнопка, открывающая и закрывающая элемент управления <xref:System.Windows.Controls.Calendar>.|  
|PART\_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|Текстовое поле, в котором можно ввести дату.|  
|PART\_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Всплывающее окно для элемента управления <xref:System.Windows.Controls.DatePicker>.|  
  
## Состояние DatePicker  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.DatePicker>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|Disabled|CommonStates|Элемент управления <xref:System.Windows.Controls.DatePicker> отключен.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Части DatePickerTextBox  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_Watermark|<xref:System.Windows.Controls.ContentControl>|Элемент, содержащий начальный текст в элементе управления <xref:System.Windows.Controls.DatePicker>.|  
|PART\_ContentElement|<xref:System.Windows.FrameworkElement>|Визуальный элемент, который может содержать элемент <xref:System.Windows.FrameworkElement>.  В этом элементе отображается текст, содержащийся в элементе управления <xref:System.Windows.Controls.TextBox>.|  
  
## Состояния DatePickerTextBox  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|Disabled|CommonStates|Элемент управления <xref:System.Windows.Controls.Primitives.DatePickerTextBox> отключен.|  
|MouseOver|CommonStates|Указатель мыши наведен на элемент управления <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|ReadOnly|CommonStates|Пользователь не может изменять текст в элементе управления <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Unfocused|FocusStates|Элемент управления не имеет фокуса.|  
|Watermarked|WatermarkStates|В элементе управления отображается начальный текст.  Элемент управления <xref:System.Windows.Controls.Primitives.DatePickerTextBox> находится в состоянии, когда пользователь не ввел текст и не выбрал дату.|  
|Unwatermarked|WatermarkStates|Пользователь ввел текст в элемент управления <xref:System.Windows.Controls.Primitives.DatePickerTextBox> или выбрал дату в элементе управления <xref:System.Windows.Controls.DatePicker>.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример шаблона ControlTemplate для элемента управления DatePicker  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.DatePicker>.  
  
 [!code-xml[ControlTemplateExamples#DatePicker](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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