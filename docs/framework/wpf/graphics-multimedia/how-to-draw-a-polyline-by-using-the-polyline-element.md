---
title: "Практическое руководство. Рисование ломаной, используя элемент Polyline | Microsoft Docs"
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
  - "соединенные линии"
  - "рисование, ломаные линии"
  - "графика [WPF], ломаные линии"
  - "линии, соединение (см. ломаные линии)"
  - "ломаные линии, рисование"
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Рисование ломаной, используя элемент Polyline
В этом примере демонстрируется рисование ломаной, которая представляет собой последовательность соединенных линий, с помощью элемента <xref:System.Windows.Shapes.Polyline>.  
  
 Чтобы нарисовать ломаную, создайте элемент <xref:System.Windows.Shapes.Polyline> и используйте его свойство <xref:System.Windows.Shapes.Polyline.Points%2A> для указания вершины фигуры.  Наконец, используйте свойства <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> для описания структуры ломаной, поскольку линия без штриха является невидимой.  
  
> [!NOTE]
>  Так как элемент <xref:System.Windows.Shapes.Polyline> представляет собой не замкнутую фигуру, свойство <xref:System.Windows.Shapes.Shape.Fill%2A> не действует, даже если намеренно замкнуть контур фигуры.  Чтобы создать замкнутую фигуру с помощью свойства <xref:System.Windows.Shapes.Shape.Fill%2A>, используйте элемент <xref:System.Windows.Shapes.Polygon>.  
  
 В следующем примере рисуются два элемента <xref:System.Windows.Shapes.Polyline> внутри элемента управления <xref:System.Windows.Controls.Canvas>.  
  
## Пример  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] допустимым синтаксисом для точек является список, содержащий пары разделенных пробелом координат x и y.  
  
 [!code-xml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Хотя этот пример использует объект <xref:System.Windows.Controls.Canvas> для хранения ломаных, можно использовать элементы Polyline \(и все остальные элементы фигур\) с любым объектом <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающим нетекстовое содержимое.  
  
 Этот пример является фрагментом большего примера; полный пример см. на веб\-странице [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## См. также  
 <xref:System.Windows.Shapes.Polyline>   
 <xref:System.Windows.Shapes.Polygon>   
 <xref:System.Windows.Shapes.Shape>   
 [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037)   
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)