---
title: Практическое руководство. Создание кривой Безье третьего порядка
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: c12bd84fcebb3acebb80bef5f4479ad535fd6691
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452114"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a>Практическое руководство. Создание кривой Безье третьего порядка
В этом примере показано, как создать кривую Безье третьего порядка. Чтобы создать кривую Безье третьего порядка, используйте классы <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>и <xref:System.Windows.Media.BezierSegment>.  Чтобы отобразить полученную геометрию, используйте элемент <xref:System.Windows.Shapes.Path> или используйте его с <xref:System.Windows.Media.GeometryDrawing> или <xref:System.Windows.Media.DrawingContext>. В следующих примерах кривая Безье третьего порядка рисуется от (10, 100) до (300, 100). Кривая имеет контрольные точки (100, 0) и (200, 200).  
  
## <a name="example"></a>Пример  
 [xaml]  
  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]можно использовать сокращенный синтаксис разметки для описания пути.  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 [xaml]  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]можно также нарисовать кривую Безье третьего порядка с помощью тегов объектов. Следующий пример эквивалентен предыдущему примеру [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>См. также раздел

- [Создание эллиптической дуги](how-to-create-an-elliptical-arc.md)
- [Создание LineSegment в PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [Создание кривой Безье третьего порядка](how-to-create-a-cubic-bezier-curve.md)
- [Создание кривой Безье второго порядка](how-to-create-a-quadratic-bezier-curve.md)
