---
title: "Практическое руководство. Создание фигуры с помощью PathGeometry"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 784a8df792ca4dc05e36f5b7e9ec93b02e0e639f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>Практическое руководство. Создание фигуры с помощью PathGeometry
В этом примере показано, как создать форму с помощью <xref:System.Windows.Media.PathGeometry> класса. <xref:System.Windows.Media.PathGeometry>объекты состоят из одного или нескольких <xref:System.Windows.Media.PathFigure> объектов, каждый из которых <xref:System.Windows.Media.PathFigure> представляет различные «рисунок» или фигуры. Каждый <xref:System.Windows.Media.PathFigure> состоит из одного или нескольких <xref:System.Windows.Media.PathSegment> объектов, каждый из которых представляет подключенных часть фигуры или формы. Типы сегментов включают <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, и <xref:System.Windows.Media.BezierSegment>.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.PathGeometry> для создания треугольника. <xref:System.Windows.Media.PathGeometry> Отображается с использованием <xref:System.Windows.Shapes.Path> элемента.  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 На следующем рисунке показана фигура, созданная в предыдущем примере.  
  
 ![Объект PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
Треугольник, созданных с помощью объект PathGeometry  
  
 В предыдущем примере показан способ создания относительно простой фигуры треугольника. Объект <xref:System.Windows.Media.PathGeometry> можно также использовать для создания более сложных фигур, включая дуги и кривые. Примеры см. в разделе [создать эллиптическую дугу](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [создайте кривую Безье третьего](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), и [создайте кривую Безье второго порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).  
  
 Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Образец геометрических объектов](http://go.microsoft.com/fwlink/?LinkID=159989)
