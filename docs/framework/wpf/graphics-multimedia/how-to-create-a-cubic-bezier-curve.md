---
title: "Практическое руководство. Создание кривой Безье третьего порядка | Microsoft Docs"
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
  - "Кривые Безье, кубические"
  - "создание, кубические кривые Безье"
  - "кубические кривые Безье"
  - "кривые, кубические Безье"
  - "графика, кубические кривые Безье"
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Создание кривой Безье третьего порядка
В этом примере демонстрируется создание кривой Безье третьего порядка.  Чтобы создать кривую Безье третьего порядка, используйте классы <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure> и <xref:System.Windows.Media.BezierSegment>.  Чтобы отобразить получившиеся в результате геометрические фигуры, используйте элемент <xref:System.Windows.Shapes.Path>. Также его можно использовать с <xref:System.Windows.Media.GeometryDrawing> или <xref:System.Windows.Media.DrawingContext>.  В следующих примерах кривая Безье третьего порядка строится от \(10, 100\) до \(300, 100\).  Контрольные точки кривой имеют координаты \(100, 0\) и \(200, 200\).  
  
## Пример  
 \[xaml\]  
  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] можно использовать сокращенный синтаксис разметки для описания пути.  
  
 [!code-xml[GeometrySample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 \[xaml\]  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] также можно нарисовать кривую Безье третьего порядка с помощью тегов объекта.  Ниже приведен эквивалент предыдущего примера кода [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[GeometrySample#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Этот пример является фрагментом большего примера; полный пример см. на веб\-странице [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## См. также  
 [Создание эллиптической дуги](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)   
 [Создание LineSegment в PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)   
 [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)   
 [Создание кривой Безье второго порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)