---
title: "Практическое руководство. Получение смещения визуального объекта | Microsoft Docs"
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
  - "получение значений смещения из визуальных объектов"
  - "значения смещения, получение из визуальных объектов"
  - "извлечение значений смещения из визуальных объектов"
  - "визуальные объекты, получение значений смещения"
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Получение смещения визуального объекта
Данные примеры показывают, как извлечь значение смещения визуального объекта, заданное относительно родительского объекта, а также любого предка или потомка.  
  
## Пример  
 В следующем примере разметки показан объект <xref:System.Windows.Controls.TextBlock>, для которого значение свойства <xref:System.Windows.FrameworkElement.Margin%2A> равно 4.  
  
 [!code-xml[VisualSnippets#VisualSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 В следующем примере показано, как использовать метод <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> для извлечения смещения объекта <xref:System.Windows.Controls.TextBlock>.  Значения смещения содержатся в возвращаемом значении <xref:System.Windows.Vector>.  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 Смещение учитывает значение свойства <xref:System.Windows.FrameworkElement.Margin%2A>.  В этом случае значение свойства <xref:System.Windows.Vector.X%2A> равно 4, и значение свойства <xref:System.Windows.Vector.Y%2A> также равно 4.  
  
 Возвращаемое значение смещения задано относительно родителя объекта класса <xref:System.Windows.Media.Visual>.  Если требуется вернуть значение смещения, заданное не относительно родителя объекта класса <xref:System.Windows.Media.Visual>, то необходимо использовать метод <xref:System.Windows.Media.Visual.TransformToAncestor%2A>.  
  
## Получение смещения относительно предка  
 В следующем примере разметки показан объект <xref:System.Windows.Controls.TextBlock>, вложенный в два объекта <xref:System.Windows.Controls.StackPanel>.  
  
 [!code-xml[VisualSnippets#VisualSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 На следующем рисунке показаны результаты разметки.  
  
 ![Значения смещения объектов](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset\_01")  
 Объект TextBlock, вложенный в два объекта StackPanel  
  
 В следующем примере кода показано, как использовать метод <xref:System.Windows.Media.Visual.TransformToAncestor%2A> для извлечения значения смещения объекта <xref:System.Windows.Controls.TextBlock> по отношению к объекту класса <xref:System.Windows.Window>.  Значения смещения содержатся в значении, возвращаемом структурой <xref:System.Windows.Media.GeneralTransform>.  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 Смещение учитывает значения свойства <xref:System.Windows.FrameworkElement.Margin%2A> для всех объектов класса <xref:System.Windows.Window>.  В этом случае значение свойства <xref:System.Windows.Vector.X%2A> равно 28 \(16 \+ 8 \+ 4\), и значение свойства <xref:System.Windows.Vector.Y%2A> также равно 28.  
  
 Возвращаемое значение смещения задано относительно предка объекта <xref:System.Windows.Media.Visual>.  Если требуется вернуть значение смещения, заданное относительно потомка <xref:System.Windows.Media.Visual>, то необходимо использовать метод <xref:System.Windows.Media.Visual.TransformToDescendant%2A>.  
  
## Получение смещения относительно потомка  
 В следующем примере разметки показан объект <xref:System.Windows.Controls.TextBlock>, содержащийся в объекте <xref:System.Windows.Controls.StackPanel>.  
  
 [!code-xml[VisualSnippets#VisualSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 В следующем примере кода показано, как использовать метод <xref:System.Windows.Media.Visual.TransformToDescendant%2A> для извлечения значения смещения объекта <xref:System.Windows.Controls.StackPanel> по отношению к его дочернему объекту <xref:System.Windows.Controls.TextBlock>.  Значения смещения содержатся в значении, возвращаемом структурой <xref:System.Windows.Media.GeneralTransform>.  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 В смещении учитывается значения свойства <xref:System.Windows.FrameworkElement.Margin%2A> для всех объектов.  В этом случае значение свойства <xref:System.Windows.Vector.X%2A> равно \-4, и значение свойства <xref:System.Windows.Vector.Y%2A> также равно –4.  Значения смещения являются отрицательными, поскольку родительский объект имеет отрицательное значение смещения по отношению к его дочернему объекту.  
  
## См. также  
 <xref:System.Windows.Media.Visual>   
 <xref:System.Windows.Media.VisualTreeHelper>   
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)