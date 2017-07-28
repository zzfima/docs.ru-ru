---
title: "Практическое руководство. Создание фигуры с помощью PathGeometry | Microsoft Docs"
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
  - "классы, PathGeometry"
  - "графика [WPF], фигуры"
  - "класс PathGeometry"
  - "фигуры, создание с помощью класса PathGeometry"
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Создание фигуры с помощью PathGeometry
В этом примере показано, как создать фигуру с помощью класса <xref:System.Windows.Media.PathGeometry>.  Объекты <xref:System.Windows.Media.PathGeometry> составлены из одного или нескольких объектов <xref:System.Windows.Media.PathFigure>; каждый объект <xref:System.Windows.Media.PathFigure> представляет отдельную "фигуру" или форму.  Каждый объект <xref:System.Windows.Media.PathFigure> состоит из одного или нескольких объектов <xref:System.Windows.Media.PathSegment>, каждый из которых представляет переходную часть фигуры или формы.  Типы сегментов включают <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment> и <xref:System.Windows.Media.BezierSegment>.  
  
## Пример  
 В следующем примере <xref:System.Windows.Media.PathGeometry> используется для создания треугольника.  <xref:System.Windows.Media.PathGeometry> отображается при помощи элемента <xref:System.Windows.Shapes.Path>.  
  
 [!code-xml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 На следующем рисунке показана фигура, созданная в предыдущем примере.  
  
 ![Объект PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.png "wcpsdk\_graphicsmm\_pathgeometry\_triangle")  
Треугольник, созданный с помощью PathGeometry  
  
 Предыдущий пример продемонстрировал создание относительно простой фигуры, например треугольника.  <xref:System.Windows.Media.PathGeometry> может также быть использован для создания более сложных фигур, включая дуги и кривые.  Примеры см. в разделах [Создание эллиптической дуги](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Создание кривой Безье третьего порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md) и [Создание кривой Безье второго порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).  
  
 Этот пример является фрагментом большего примера; полный пример см. на веб\-странице [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## См. также  
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.GeometryDrawing>   
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989)