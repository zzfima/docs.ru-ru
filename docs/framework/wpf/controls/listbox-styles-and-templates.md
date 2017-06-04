---
title: "Стили и шаблоны элемента ListBox | Microsoft Docs"
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
  - "ControlTemplate [WPF], ListBox"
  - "ListBox [WPF], стили и шаблоны"
  - "части [WPF], ListBox"
  - "состояния [WPF], ListBox"
  - "стили [WPF], ListBox"
  - "шаблоны [WPF], ListBox"
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Стили и шаблоны элемента ListBox
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ListBox>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части ListBox  
 Элемент управления <xref:System.Windows.Controls.ListBox> не имеет именованных частей.  
  
 При создании шаблона <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ListBox> шаблон может содержать часть <xref:System.Windows.Controls.ItemsPresenter> в элементе управления <xref:System.Windows.Controls.ScrollViewer>.  \(Элемент управления <xref:System.Windows.Controls.ItemsPresenter> отображает каждый элемент в элементе управления <xref:System.Windows.Controls.ListBox>; элемент управления <xref:System.Windows.Controls.ScrollViewer> обеспечивает прокрутку в элементе управления\).  Если элемент управления <xref:System.Windows.Controls.ItemsPresenter> не является непосредственным дочерним элементом элемента управления <xref:System.Windows.Controls.ScrollViewer>, необходимо присвоить элементу управления <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.  
  
## Состояния ListBox  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.ListBox>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Valid|ValidationStates|Элемент управления является допустимым.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
  
## Части ListBoxItem  
 Элемент управления <xref:System.Windows.Controls.ListBoxItem> не имеет именованных частей.  
  
## Состояния ListBoxItem  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.ListBox>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|  
|Disabled|CommonStates|Элемент отключен.|  
|Focused|FocusStates|На элементе установлен фокус.|  
|Unfocused|FocusStates|Элемент не имеет фокус.|  
|Не выбран|SelectionStates|Элемент выбран.|  
|Выбран|SelectionStates|Элемент не выбран.|  
|SelectedUnfocused|SelectionStates|Элемент выбран, но не имеет фокус.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример ControlTemplate ListBox  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элементов управления <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-xml[ControlTemplateExamples#ListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
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