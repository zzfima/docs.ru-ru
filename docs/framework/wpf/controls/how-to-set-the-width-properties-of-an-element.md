---
title: "Практическое руководство. Установка свойств ширины элемента | Microsoft Docs"
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
  - "Panel - элемент управления, свойства ширины элементов"
  - "свойства ширины"
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Установка свойств ширины элемента
## Пример  
 В этом примере визуально показаны различия в поведении отрисовки между четырьмя свойствами, связными с шириной, в приложении [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Класс <xref:System.Windows.FrameworkElement> предоставляет четыре свойства, описывающих характеристики ширины элемента.  Эти четыре свойства могут конфликтовать, и в этом случае значение, которое получает приоритет, определяется следующим образом: значение <xref:System.Windows.FrameworkElement.MinWidth%2A> получает приоритет перед значением <xref:System.Windows.FrameworkElement.MaxWidth%2A>, которое, в свою очередь, получает приоритет перед значением <xref:System.Windows.FrameworkElement.Width%2A>.  Четвертое свойство <xref:System.Windows.FrameworkElement.ActualWidth%2A> доступно только для чтения и сообщает о фактической ширине, определенной при взаимодействии с процессом макета.  
  
 В следующих примерах [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] элемент <xref:System.Windows.Shapes.Rectangle> \(`rect1`\) представлен в качестве дочернего элемента объекта <xref:System.Windows.Controls.Canvas>.  Можно изменить свойства ширины <xref:System.Windows.Shapes.Rectangle> с помощью нескольких элементов <xref:System.Windows.Controls.ListBox>, представляющих значения свойств <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A> и <xref:System.Windows.FrameworkElement.Width%2A>.  Таким образом визуально отображается приоритет каждого свойства.  
  
 [!code-xml[WidthMinWidthMaxWidth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xml[WidthMinWidthMaxWidth#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 В следующих примерах кода программной части обрабатываются события, которые создаются событием <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>.  Каждый пользовательский метод принимает входное значение из элемента управления <xref:System.Windows.Controls.ListBox>, выполняет его синтаксический разбор как значения типа <xref:System.Double> и применяет это значение к указанному свойству ширины.  Значения ширины также преобразуются в строку и записываются в различные элементы <xref:System.Windows.Controls.TextBlock> \(определение этих элементов не представлено в выбранном XAML\).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Для полного кода примера см. [Пример "Width Properties Comparison"](http://go.microsoft.com/fwlink/?LinkID=160050).  
  
## См. также  
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.FrameworkElement.ActualWidth%2A>   
 <xref:System.Windows.FrameworkElement.MaxWidth%2A>   
 <xref:System.Windows.FrameworkElement.MinWidth%2A>   
 <xref:System.Windows.FrameworkElement.Width%2A>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Установка свойств высоты элемента](../../../../docs/framework/wpf/controls/how-to-set-the-height-properties-of-an-element.md)   
 [Width Properties Comparison Sample](http://go.microsoft.com/fwlink/?LinkID=160050)