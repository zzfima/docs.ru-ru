---
title: "Практическое руководство. Определение прямоугольника с помощью класса RectangleGeometry | Microsoft Docs"
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
  - "классы, RectangleGeometry"
  - "графика [WPF], прямоугольники"
  - "RectangleGeometry - класс"
  - "прямоугольники, создание с помощью класса RectangleGeometry"
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Определение прямоугольника с помощью класса RectangleGeometry
Этот пример описывает способы использования класса <xref:System.Windows.Media.RectangleGeometry> для описания прямоугольника.  
  
## Пример  
 В следующем примере демонстрируется создание и отображение <xref:System.Windows.Media.RectangleGeometry>.  Относительное положение и размеры прямоугольника определяются структурой <xref:System.Windows.Rect>.  Относительное положение устанавливается равным `50,50`, а высота и ширина —равными `25`, что создает квадрат.  Внутренняя часть прямоугольника нарисована кистью <xref:System.Windows.Media.Brushes.LemonChiffon%2A>, а его контур — штрихом <xref:System.Windows.Media.Brushes.Black%2A> со значением толщины `1`.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.png "graphicsmm\_rectangle")  
RectangleGeometry  
  
 Несмотря на то, что в этом примере для отображения <xref:System.Windows.Media.RectangleGeometry> используется элемент <xref:System.Windows.Shapes.Path>, существует много других способов использования объектов <xref:System.Windows.Media.RectangleGeometry>.  Например, <xref:System.Windows.Media.RectangleGeometry> может использоваться для указания <xref:System.Windows.UIElement.Clip%2A> элемента <xref:System.Windows.UIElement> или <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> элемента <xref:System.Windows.Media.GeometryDrawing>.  
  
 В числе других простых геометрических классов — <xref:System.Windows.Media.LineGeometry> и <xref:System.Windows.Media.EllipseGeometry>.  Эти геометрические объекты, равно как и более сложные, могут создаваться с помощью <xref:System.Windows.Media.PathGeometry> или <xref:System.Windows.Media.StreamGeometry>.  
  
## См. также  
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Создание составной фигуры](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [Создание фигуры с помощью PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)