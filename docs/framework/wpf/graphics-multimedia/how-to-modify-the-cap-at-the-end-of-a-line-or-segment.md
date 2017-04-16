---
title: "Практическое руководство. Изменение завершения отрезка в конце линии или сегмента | Microsoft Docs"
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
  - "графика, Shape - законцовки"
  - "Shape - элементы, законцовки"
  - "Shape - элементы, концы"
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Изменение завершения отрезка в конце линии или сегмента
В этом примере демонстрируется изменение фигуры в начале или в конце открытого элемента <xref:System.Windows.Shapes.Shape>.  Для изменения завершения отрезка в начале открытой <xref:System.Windows.Shapes.Shape>, используйте свойство <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>.  Для изменения завершения отрезка в конце открытой <xref:System.Windows.Shapes.Shape> используйте свойство <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>.  Доступные завершения отрезков представлены в перечислении <xref:System.Windows.Media.PenLineCap>.  
  
> [!NOTE]
>  Это свойство влияет только на открытые фигуры, такие как <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline> или открытый элемент <xref:System.Windows.Shapes.Path>.  
  
 В следующем примере рисуется четыре элемента <xref:System.Windows.Shapes.Polyline> и используется разный набор фигур в конце каждого.  
  
## Пример  
 [!code-xml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Этот пример является фрагментом большего примера; полный пример см. на веб\-странице [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## См. также  
 <xref:System.Windows.Shapes.Polyline>   
 <xref:System.Windows.Media.PenLineCap>