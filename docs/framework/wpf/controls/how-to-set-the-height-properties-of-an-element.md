---
title: "Практическое руководство. Установка свойств высоты элемента | Microsoft Docs"
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
  - "свойства высоты"
  - "Panel - элемент управления, свойства высоты элементов"
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Установка свойств высоты элемента
## Пример  
 В данном примере визуально показывается разница в получаемом изображении в результате задания четырех связанных с высотой свойств в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Класс <xref:System.Windows.FrameworkElement> предоставляет четыре свойства, описывающих характеристики высоты элемента.  Эти четыре свойства могут конфликтовать, и в этом случае значение, которое получает приоритет, определяется следующим образом: значение <xref:System.Windows.FrameworkElement.MinHeight%2A> получает приоритет перед значением <xref:System.Windows.FrameworkElement.MaxHeight%2A>, которое, в свою очередь, получает приоритет перед значением <xref:System.Windows.FrameworkElement.Height%2A>.  Четвертое свойство <xref:System.Windows.FrameworkElement.ActualHeight%2A> доступно только для чтения и сообщает о фактической высоте, определенной при взаимодействии с процессом макета.  
  
 В следующих примерах [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] элемент <xref:System.Windows.Shapes.Rectangle> \(`rect1`\) представлен в качестве дочернего элемента объекта <xref:System.Windows.Controls.Canvas>.  Можно изменить свойства высоты <xref:System.Windows.Shapes.Rectangle> с помощью нескольких элементов <xref:System.Windows.Controls.ListBox>, представляющих значения свойств <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A> и <xref:System.Windows.FrameworkElement.Height%2A>.  Таким образом визуально отображается приоритет каждого свойства.  
  
 [!code-xml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 В следующих примерах кода программной части обрабатываются события, которые создаются событием <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>.  Каждый обработчик берет значение из <xref:System.Windows.Controls.ListBox>, анализирует его как <xref:System.Double> и применяет это значение к указанному свойству высоты.  Значения высоты также преобразуются в строку и записываются в различные элементы <xref:System.Windows.Controls.TextBlock> \(определение этих элементов не представлено в выбранном XAML\).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Полный код примера см. в разделе [Пример свойств высоты](http://go.microsoft.com/fwlink/?LinkID=159993).  
  
## См. также  
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.FrameworkElement.ActualHeight%2A>   
 <xref:System.Windows.FrameworkElement.MaxHeight%2A>   
 <xref:System.Windows.FrameworkElement.MinHeight%2A>   
 <xref:System.Windows.FrameworkElement.Height%2A>   
 [Установка свойств ширины элемента](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Height Properties Sample](http://go.microsoft.com/fwlink/?LinkID=159993)