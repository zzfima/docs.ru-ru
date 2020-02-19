---
title: Практическое руководство. Создание фигуры с помощью PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452049"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>Практическое руководство. Создание фигуры с помощью PathGeometry
В этом примере показано, как создать фигуру с помощью класса <xref:System.Windows.Media.PathGeometry>. <xref:System.Windows.Media.PathGeometry> объекты состоят из одного или нескольких объектов <xref:System.Windows.Media.PathFigure>; Каждый <xref:System.Windows.Media.PathFigure> представляет другую фигуру или форму. Каждая <xref:System.Windows.Media.PathFigure> сама по себе состоит из одного или нескольких объектов <xref:System.Windows.Media.PathSegment>, каждый из которых представляет собой подключенную часть рисунка или фигуры. К типам сегментов относятся <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>и <xref:System.Windows.Media.BezierSegment>.  
  
## <a name="example"></a>Пример  
 В следующем примере для создания треугольника используется <xref:System.Windows.Media.PathGeometry>. <xref:System.Windows.Media.PathGeometry> отображается с помощью элемента <xref:System.Windows.Shapes.Path>.  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 На следующем рисунке показана фигура, созданная в предыдущем примере.  
  
 ![Объект PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
Треугольник, созданный с помощью PathGeometry  
  
 В предыдущем примере показано, как создать относительно простую фигуру — треугольник. <xref:System.Windows.Media.PathGeometry> также можно использовать для создания более сложных фигур, включая дуги и кривые. Примеры см. в статьях [Создание эллиптической дуги](how-to-create-an-elliptical-arc.md), [Создание кривой Безье третьего порядка](how-to-create-a-cubic-bezier-curve.md)и [Создание кривой Безье квадратичных](how-to-create-a-quadratic-bezier-curve.md)кривых.  
  
 Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Общение сведения о классе Geometry](geometry-overview.md)
- [Пример геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
