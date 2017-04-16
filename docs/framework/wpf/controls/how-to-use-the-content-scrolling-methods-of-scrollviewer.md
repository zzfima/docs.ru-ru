---
title: "Практическое руководство. Использование методов прокрутки содержимого ScrollViewer | Microsoft Docs"
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
  - "IScrollInfo - интерфейс"
  - "методы прокрутки"
  - "ScrollViewer - элемент управления, методы прокрутки"
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Использование методов прокрутки содержимого ScrollViewer
В этом примере показано использование методов прокрутки элемента <xref:System.Windows.Controls.ScrollViewer>.  Эти методы предоставляют постоянно увеличивающуюся прокрутку содержимого по строкам или по страницам в <xref:System.Windows.Controls.ScrollViewer>.  
  
## Пример  
 В следующем примере создается <xref:System.Windows.Controls.ScrollViewer> с именем `sv1`, который содержит дочерний элемент <xref:System.Windows.Controls.TextBlock>.  Так как элемент управления <xref:System.Windows.Controls.TextBlock> больше родительского элемента управления <xref:System.Windows.Controls.ScrollViewer>, отображается полоса прокрутки.  Элементы <xref:System.Windows.Controls.Button>, представляющие различные методы прокрутки, закреплены слева в отдельном элементе управления <xref:System.Windows.Controls.StackPanel>.  Каждая кнопка <xref:System.Windows.Controls.Button> в файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] вызывает связанный пользовательский метод, который управляет прокруткой в элементе управления <xref:System.Windows.Controls.ScrollViewer>.  
  
 [!code-xml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 В следующем примере используются методы <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> и <xref:System.Windows.Controls.ScrollViewer.LineDown%2A>.  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## См. также  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.StackPanel>