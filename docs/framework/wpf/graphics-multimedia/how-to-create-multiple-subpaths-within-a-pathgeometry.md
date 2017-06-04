---
title: "Практическое руководство. Создание нескольких подконтуров внутри PathGeometry | Microsoft Docs"
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
  - "графика [WPF], подконтуры"
  - "несколько подконтуров"
  - "класс PathGeometry"
  - "подконтуры"
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Создание нескольких подконтуров внутри PathGeometry
В этом примере демонстрируется создание нескольких подконтуров в <xref:System.Windows.Media.PathGeometry>.  Чтобы создать несколько подконтуров, необходимо создать <xref:System.Windows.Media.PathFigure> для каждого субконтура.  
  
## Пример  
 В следующем примере создаются два подконтура, каждый из которых имеет форму треугольника.  
  
 [!code-xml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 В следующем примере показано, как создать несколько подконтуров с помощью <xref:System.Windows.Shapes.Path> и синтаксических атрибутов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Каждый `M` создает новый подконтур таким образом, чтобы каждый из создаваемых подконтуров в примере образовывал треугольник.  
  
 [!code-xml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 \(Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, облегченную версию <xref:System.Windows.Media.PathGeometry>.  Дополнительные сведения см. на странице [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)\).  
  
## См. также  
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)