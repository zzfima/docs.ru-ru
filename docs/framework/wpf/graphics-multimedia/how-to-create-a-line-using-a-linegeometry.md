---
title: "Практическое руководство. Создание отрезка с помощью LineGeometry | Microsoft Docs"
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
  - "классы, LineGeometry"
  - "графика [WPF], линии"
  - "LineGeometry - класс"
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Создание отрезка с помощью LineGeometry
В этом примере показано использование класса <xref:System.Windows.Media.LineGeometry> для описания отрезка.  <xref:System.Windows.Media.LineGeometry> определяется начальной и конечной точками.  
  
## Пример  
 В следующем примере показано создание и отображение объекта класса <xref:System.Windows.Media.LineGeometry>.  Элемент <xref:System.Windows.Shapes.Path> используется для отображения отрезка.  Поскольку отрезок не имеет области, <xref:System.Windows.Shapes.Shape.Fill%2A> объекта <xref:System.Windows.Shapes.Path> не указывается; вместо этого используются свойства <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
LineGeometry, построенная от точки с координатами \(10,20\) до точки с координатами \(100,130\)  
  
 В числе других простых геометрических классов — <xref:System.Windows.Media.LineGeometry> и <xref:System.Windows.Media.EllipseGeometry>.  Эти геометрические объекты, равно как и более сложные, могут создаваться с помощью <xref:System.Windows.Media.PathGeometry> или <xref:System.Windows.Media.StreamGeometry>.  Дополнительные сведения см. в разделе [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
## См. также  
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Создание составной фигуры](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [Создание фигуры с помощью PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)