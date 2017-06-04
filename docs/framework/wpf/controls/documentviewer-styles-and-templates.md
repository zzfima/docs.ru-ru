---
title: "Стили и шаблоны элемента DocumentViewer | Microsoft Docs"
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
  - "ControlTemplate [WPF], DocumentViewer"
  - "DocumentViewer [WPF], стили и шаблоны"
  - "части [WPF], DocumentViewer"
  - "состояния [WPF], DocumentViewer"
  - "стили [WPF], DocumentViewer"
  - "шаблоны [WPF], DocumentViewer"
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Стили и шаблоны элемента DocumentViewer
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.DocumentViewer>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части DocumentViewer  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.DocumentViewer>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_ContentHost|<xref:System.Windows.Controls.ScrollViewer>|Область содержимого и прокрутки.|  
|PART\_FindToolBarHost|<xref:System.Windows.Controls.ContentControl>|Поле поиска \(по умолчанию расположено в нижней части окна\).|  
  
## Состояния DocumentViewer  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.DocumentViewer>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, и значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `false`.|  
|InvalidFocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Значение присоединенного свойства <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> равно `true`, если элемент управления не имеет фокус.|  
  
## Пример объекта "ControlTemplate" элемента управления "DocumentViewer"  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.DocumentViewer>.  
  
 [!code-xml[ControlTemplateExamples#DocumentViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
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