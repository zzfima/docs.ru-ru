---
title: "Практическое руководство. Изменение размера столбцов с помощью разделителя GridSplitter | Microsoft Docs"
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
  - "столбцы сетки, изменение размеров"
  - "GridSplitter - элемент управления, изменение размеров столбцов сетки"
  - "изменение размеров столбцов сетки"
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Изменение размера столбцов с помощью разделителя GridSplitter
Этот пример показывает создание вертикального <xref:System.Windows.Controls.GridSplitter> для увеличения пространства между двумя столбцами в <xref:System.Windows.Controls.Grid> без изменения размеров <xref:System.Windows.Controls.Grid>.  
  
## Пример  
 **Создание GridSplitter, располагающегося поверх края столбца**  
  
 Чтобы указать <xref:System.Windows.Controls.GridSplitter>, который изменяет размеры соседних столбцов в <xref:System.Windows.Controls.Grid>, задайте [вложенное свойство](GTMT) <xref:System.Windows.Controls.Grid.Column%2A> равным номеру столбца, размер которого вы хотите изменить.  Если <xref:System.Windows.Controls.Grid> имеет больше одной строки, задайте вложенному свойству <xref:System.Windows.Controls.Grid.RowSpan%2A> число строк.  Затем установите свойство <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> в <xref:System.Windows.HorizontalAlignment> или <xref:System.Windows.HorizontalAlignment> \(устанавливаемое выравнивание зависит от двух столбцов, размеры которых требуется изменить\).  Наконец, присвойте свойству <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> значение <xref:System.Windows.VerticalAlignment>.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 <xref:System.Windows.Controls.GridSplitter>, который не имеет своего собственного столбца, может быть скрыт другими элементами управления в <xref:System.Windows.Controls.Grid>.  Дополнительные сведения о том, как предотвратить эту проблему см. в разделе [Проверка видимости GridSplitter](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Как создать GridSplitter, занимающий столбец**  
  
 Чтобы указать <xref:System.Windows.Controls.GridSplitter>, который занимает столбец в <xref:System.Windows.Controls.Grid>, установите [вложенное свойство](GTMT) <xref:System.Windows.Controls.Grid.Column%2A> равным номеру столбца, размер которого требуется изменить.  Если ваш сетка имеет несколько строк, задайте вложенному свойству <xref:System.Windows.Controls.Grid.RowSpan%2A> число строк.  Затем установите <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> в <xref:System.Windows.HorizontalAlignment>, установите свойство <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> в <xref:System.Windows.VerticalAlignment>, и установите <xref:System.Windows.Controls.ColumnDefinition.Width%2A> столбца, содержащего <xref:System.Windows.Controls.GridSplitter> равным <xref:System.Windows.GridLength.Auto%2A>.  
  
 В следующем примере показано определение вертикального <xref:System.Windows.Controls.GridSplitter>, который занимает столбец и изменяет размеры столбцов по обе стороны от его.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## См. также  
 <xref:System.Windows.Controls.GridSplitter>   
 [Практические руководства](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)