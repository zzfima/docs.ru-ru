---
title: "Практическое руководство. Создание эллиптической дуги | Microsoft Docs"
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
  - "дуги, эллиптические"
  - "эллиптические дуги, создание"
  - "графика [WPF], эллиптические дуги"
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Создание эллиптической дуги
В этом примере демонстрируется процесс рисования эллиптической дуги.  Чтобы создать эллиптическую дугу, используйте классы <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure> и <xref:System.Windows.Media.ArcSegment>.  
  
## Пример  
 В приведенных ниже примерах рисуется эллиптическая дуга от точки \(10, 100\) до точки \(200, 100\).  Дуга имеет <xref:System.Windows.Media.ArcSegment.Size%2A> из 100 на 50 аппаратно\-независимых пикселей, <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45 градусов, параметр <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> `true` и <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> <xref:System.Windows.Media.SweepDirection>.  
  
 \[xaml\]  
  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для описания пути можно использовать синтаксис атрибута.  
  
 [!code-xml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 \[xaml\]  
  
 \(Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, облегченную версию <xref:System.Windows.Media.PathGeometry>.  Дополнительные сведения см. на странице [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)\).  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] также можно нарисовать эллиптическую дугу явным образом с помощью тегов объектов.  Ниже приведен пример, эквивалентный предшествующей разметке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Данный пример является частью большего примера.  Полный пример см. в разделе [Пример "Geometries"](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## См. также  
 [Создание кривой Безье второго порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)   
 [Создание кривой Безье третьего порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)