---
title: "Практическое руководство. Изменение размера строк с помощью разделителя GridSplitter | Microsoft Docs"
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
  - "строки сетки, изменение размеров"
  - "GridSplitter - элемент управления, изменение размеров строк сетки"
  - "изменение размеров строк сетки"
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Изменение размера строк с помощью разделителя GridSplitter
Этот пример показывает, как использовать горизонтальный <xref:System.Windows.Controls.GridSplitter> для распределения пространства между двумя строками в <xref:System.Windows.Controls.Grid> без изменения размеров <xref:System.Windows.Controls.Grid>.  
  
## Пример  
 **Создание GridSplitter, который располагается поверх края строки**  
  
 Чтобы указать <xref:System.Windows.Controls.GridSplitter>, который изменяет размеры соседних строк в <xref:System.Windows.Controls.Grid>, задайте [вложенное свойство](GTMT) <xref:System.Windows.Controls.Grid.Row%2A> равным номеру строки, размер которого вы хотите изменить.  Если ваш <xref:System.Windows.Controls.Grid> имеет более чем один столбец, задайте вложенному свойству <xref:System.Windows.Controls.Grid.ColumnSpan%2A> число столбцов.  Затем установите <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> в <xref:System.Windows.VerticalAlignment> или <xref:System.Windows.VerticalAlignment> \(выравнивание, которое вы установите зависит от двух строк, размеры которых вы хотите изменить\).  Наконец, установите свойство <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> равным <xref:System.Windows.HorizontalAlignment>.  
  
 В следующем примере показано определение горизонтального <xref:System.Windows.Controls.GridSplitter>, который изменяет размеры соседних строк.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterRowOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 <xref:System.Windows.Controls.GridSplitter>, который не содержит собственную строку, может быть скрыт другими элементами управления в <xref:System.Windows.Controls.Grid>.  Дополнительные сведения о том, как предотвратить эту проблему см. в разделе [Проверка видимости GridSplitter](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Как создать GridSplitter занимающий строку**  
  
 Чтобы указать <xref:System.Windows.Controls.GridSplitter>, который занимает строку в <xref:System.Windows.Controls.Grid>, задайте [вложенное свойство](GTMT) <xref:System.Windows.Controls.Grid.Row%2A> равным номеру строки, размер которой вы хотите изменить.  Если ваш <xref:System.Windows.Controls.Grid> имеет более чем один столбец, задайте вложенному свойству <xref:System.Windows.Controls.Grid.ColumnSpan%2A> число столбцов.  Затем установите <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> в <xref:System.Windows.VerticalAlignment>, установите свойство <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> в <xref:System.Windows.HorizontalAlignment>, и установите <xref:System.Windows.Controls.RowDefinition.Height%2A> строки, содержащего <xref:System.Windows.Controls.GridSplitter> равным <xref:System.Windows.GridLength.Auto%2A>.  
  
 В следующем примере показано определение горизонтального <xref:System.Windows.Controls.GridSplitter>, который занимает строку и изменяет размеры строк по обе стороны от него.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterEntireRowPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xml[GridSplitterRowColumn#GridSplitterEntireRowPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## См. также  
 <xref:System.Windows.Controls.GridSplitter>   
 [Практические руководства](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)