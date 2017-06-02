---
title: "Практическое руководство. Создание кривой Безье второго порядка | Microsoft Docs"
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
  - "Кривые Безье, создание"
  - "графика [WPF], кривые Безье второго порядка"
  - "кривые Безье второго порядка, создание"
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Создание кривой Безье второго порядка
В этом примере демонстрируется создание кривой Безье второго порядка.  Чтобы создать кривую Безье второго порядка, используйте классы <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure> и <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
## Пример  
 В следующих примерах кривая Безье второго порядка строится от точки с координатами \(10,100\) до точки \(300,100\).  Кривая имеет контрольную точку с координатами \(200,200\).  
  
 \[xaml\]  
  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для описания пути можно использовать синтаксис атрибута.  
  
 [!code-xml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 \[xaml\]  
  
 \(Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, облегченную версию <xref:System.Windows.Media.PathGeometry>.  Дополнительные сведения см. на странице [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)\).  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] можно также создать кривую Безье второго порядка, используя синтаксис элемента объекта.  Ниже приведен эквивалент предыдущего примера кода [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Этот пример является фрагментом большего примера; полный пример см. на веб\-странице [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## См. также  
 [Создание эллиптической дуги](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)   
 [Создание кривой Безье третьего порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)