---
title: "Практическое руководство. Создание кривой Безье третьего порядка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9d4e033ef18cfd33635ba34409c4edca87a7e23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-cubic-bezier-curve"></a>Практическое руководство. Создание кривой Безье третьего порядка
В этом примере демонстрируется создание кривой Безье третьего порядка. Чтобы создать кривой Безье третьего порядка, используйте <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, и <xref:System.Windows.Media.BezierSegment> классы.  Чтобы отобразить результирующей геометрии, используйте <xref:System.Windows.Shapes.Path> элемент, или использовать его с <xref:System.Windows.Media.GeometryDrawing> или <xref:System.Windows.Media.DrawingContext>. В следующих примерах кривой Безье третьего порядка строится от (10, 100) для (300, 100). Кривая имеет контрольные точки (100, 0) и (200, 200).  
  
## <a name="example"></a>Пример  
 [xaml]  
  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], может использовать сокращенный синтаксис разметки для описания пути.  
  
 [!code-xaml[GeometrySample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 [xaml]  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], также можно нарисовать кривую Безье третьего порядка с помощью тегов объектов. Следующий пример эквивалентен предыдущему примеру [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometrySample#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>См. также  
 [Создание эллиптической дуги](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)  
 [Создание LineSegment в PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)  
 [Создание кривой Безье третьего порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)  
 [Создание кривой Безье второго порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)
