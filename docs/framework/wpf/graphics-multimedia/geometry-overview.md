---
title: Общие сведения о классе Geometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometry classes [WPF]
- graphics [WPF], geometry classes
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
ms.openlocfilehash: f45c13e1af9bc2d1f75da11b13a2c03936b136c1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455011"
---
# <a name="geometry-overview"></a>Общие сведения о классе Geometry
В этом обзоре описано, как использовать классы [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> для описания фигур. В этом разделе также отличаются различия между <xref:System.Windows.Media.Geometry>ными объектами и <xref:System.Windows.Shapes.Shape> элементами.  

<a name="wcpsdk_graphics_geometry_introduction"></a>   
## <a name="what-is-a-geometry"></a>Что такое класс Geometry?  
 Класс <xref:System.Windows.Media.Geometry> и классы, производные от него, такие как <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry>и <xref:System.Windows.Media.CombinedGeometry>, позволяют описать геометрию двухмерной фигуры. Данные геометрические описания имеют множество применений, например определение фигуры для рисования на экране или определение областей проверки нажатия и областей обрезки. Геометрию можно даже использовать для определения пути анимации.  
  
 <xref:System.Windows.Media.Geometry> объекты могут быть простыми, например прямоугольниками и круговыми, или составными, созданными из двух или более геометрических объектов.  Более сложные геометрические объекты можно создавать с помощью классов <xref:System.Windows.Media.PathGeometry> и <xref:System.Windows.Media.StreamGeometry>, которые позволяют описывать дуги и кривые.  
  
 Так как <xref:System.Windows.Media.Geometry> является типом <xref:System.Windows.Freezable>, <xref:System.Windows.Media.Geometry> объекты предоставляют несколько специальных функций: они могут быть объявлены как [ресурсы](../../../desktop-wpf/fundamentals/xaml-resources-define.md), совместно используемые несколькими объектами, сделаны доступными только для чтения, чтобы повысить производительность, клонировать и сделать потокобезопасными. Дополнительные сведения о различных возможностях, предоставляемых <xref:System.Windows.Freezable> объектами, см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## <a name="geometries-vs-shapes"></a>Геометрические объекты и фигуры  
 Классы <xref:System.Windows.Media.Geometry> и <xref:System.Windows.Shapes.Shape> похожи на то, что они описывают двумерные фигуры (например, сравнение <xref:System.Windows.Media.EllipseGeometry> и <xref:System.Windows.Shapes.Ellipse>), но существуют важные различия.  
  
 Для одного класса <xref:System.Windows.Media.Geometry> наследуется от класса <xref:System.Windows.Freezable>, пока класс <xref:System.Windows.Shapes.Shape> наследует от <xref:System.Windows.FrameworkElement>. Поскольку они являются элементами, <xref:System.Windows.Shapes.Shape> объекты могут визуализировать себя и участвовать в системе макета, тогда как <xref:System.Windows.Media.Geometry> объекты не могут.  
  
 Хотя <xref:System.Windows.Shapes.Shape> объекты более удобны в работе, чем объекты <xref:System.Windows.Media.Geometry>, <xref:System.Windows.Media.Geometry> объекты являются более гибкими. Хотя объект <xref:System.Windows.Shapes.Shape> используется для отрисовки двухмерной графики, объект <xref:System.Windows.Media.Geometry> можно использовать для определения геометрической области для двухмерной графики, определения региона для обрезки или определения региона для проверки попадания, например.  
  
### <a name="the-path-shape"></a>Форма контура  
 Один <xref:System.Windows.Shapes.Shape>, класс <xref:System.Windows.Shapes.Path>, фактически использует <xref:System.Windows.Media.Geometry> для описания его содержимого. Установив свойство <xref:System.Windows.Shapes.Path.Data%2A> <xref:System.Windows.Shapes.Path> с <xref:System.Windows.Media.Geometry> и задав его свойства <xref:System.Windows.Shapes.Shape.Fill%2A> и <xref:System.Windows.Shapes.Shape.Stroke%2A>, можно отобразить <xref:System.Windows.Media.Geometry>.  
  
<a name="commonproperties"></a>   
## <a name="common-properties-that-take-a-geometry"></a>Общие свойства, принимающие объект класса Geometry  
 В предыдущих разделах упоминалось, что объекты класса Geometry могут использоваться с другими объектами для различных целей, например для рисования фигур, анимации и обрезки. В следующей таблице перечислены несколько классов, которые имеют свойства, принимающие объект <xref:System.Windows.Media.Geometry>.  
  
|Type|свойство;|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## <a name="simple-geometry-types"></a>Простые геометрические типы  
 Базовый класс для всех геометрических объектов является абстрактным классом <xref:System.Windows.Media.Geometry>.  Классы, производные от класса <xref:System.Windows.Media.Geometry>, можно группировать по трем категориям: простые геометрические объекты, геометрические объекты и составные геометрические объекты.  
  
 Простые геометрические классы включают <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>и <xref:System.Windows.Media.EllipseGeometry> и используются для создания простых геометрических фигур, таких как линии, прямоугольники и круги.  
  
- <xref:System.Windows.Media.LineGeometry> определяется путем указания начальной точки линии и конечной точки.  
  
- <xref:System.Windows.Media.RectangleGeometry> определяется структурой <xref:System.Windows.Rect>, указывающей ее относительное расположение и высоту и ширину. Скругленный прямоугольник можно создать, задав свойства <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> и <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>.  
  
- <xref:System.Windows.Media.EllipseGeometry> определяется центральной точкой, x-радиусом и y-радиусом.  Следующие примеры показывают, как создать простые геометрические объекты для отображения и для обрезки.  
  
 Такие же фигуры, как и более сложные фигуры, можно создать с помощью <xref:System.Windows.Media.PathGeometry> или объединить объекты Geometry, но эти классы предоставляют более простые средства для создания этих базовых геометрических фигур.  
  
 В следующем примере показано, как создать и визуализировать <xref:System.Windows.Media.LineGeometry>.  Как отмечалось ранее, объект <xref:System.Windows.Media.Geometry> не может рисовать себя, поэтому в примере используется форма <xref:System.Windows.Shapes.Path> для отрисовки строки.  Так как в строке нет области, установка свойства <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Path> не будет оказывать никакого влияния. Вместо этого задаются только свойства <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>. На следующем рисунке показан результат выполнения этого примера.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Объект LineGeometry, соединяющий точки (10,20) и (100,130)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 В следующем примере показано, как создать и отобразить <xref:System.Windows.Media.EllipseGeometry>.  В примерах для <xref:System.Windows.Media.EllipseGeometry.Center%2A> <xref:System.Windows.Media.EllipseGeometry> задается точка `50,50`, а для параметров x-радиус и y-радиус — значение `50`, что создает круг с диаметром 100.  Внутренняя часть эллипса рисуется путем присваивания значения свойству Fill элемента Path, в данном случае <xref:System.Windows.Media.Brushes.Gold%2A>. На следующем рисунке показан результат выполнения этого примера.  
  
 ![EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
Объект EllipseGeometry, нарисованный в точке (50,50)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 В следующем примере показано, как создать и визуализировать <xref:System.Windows.Media.RectangleGeometry>.  Расположение и размеры прямоугольника определяются структурой <xref:System.Windows.Rect>. Положение — `50,50`, высота и ширина — `25`. В результате получается квадрат. На следующем рисунке показан результат выполнения этого примера.  
  
 ![RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
Объект RectangleGeometry, нарисованный в точке 50,50  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 В следующем примере показано, как использовать <xref:System.Windows.Media.EllipseGeometry> в качестве области отсечения для изображения.  Объект <xref:System.Windows.Controls.Image> определяется <xref:System.Windows.FrameworkElement.Width%2A> 200 и <xref:System.Windows.FrameworkElement.Height%2A> 150.  <xref:System.Windows.Media.EllipseGeometry> с <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> значением 100, <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> значением 75 и <xref:System.Windows.Media.EllipseGeometry.Center%2A> значением 100, значение 75 устанавливается в свойство <xref:System.Windows.UIElement.Clip%2A> изображения.  Будет отображаться только часть изображения, находящаяся внутри эллипса. На следующем рисунке показан результат выполнения этого примера.  
  
 ![Изображение с обрезкой и без нее](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Использование объекта EllipseGeometry для обрезки элемента управления Image  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## <a name="path-geometries"></a>Геометрические объекты-контуры  
 Класс <xref:System.Windows.Media.PathGeometry> и его облегченный эквивалент, класс <xref:System.Windows.Media.StreamGeometry>, предоставляют средства для описания нескольких сложных фигур, состоящих из дуг, кривых и линий.  
  
 В сердце <xref:System.Windows.Media.PathGeometry> представляет собой коллекцию объектов <xref:System.Windows.Media.PathFigure>, так что их именованные, так как каждая фигура описывает дискретную форму в <xref:System.Windows.Media.PathGeometry>. Каждый <xref:System.Windows.Media.PathFigure> сам состоит из одного или нескольких <xref:System.Windows.Media.PathSegment> объектов, каждый из которых описывает сегмент фигуры.  
  
 Существует несколько типов сегментов.  
  
|Тип сегмента|Описание|Пример|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Создает эллиптическую дугу между двумя точками.|[Создание эллиптической дуги](how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Создает кривую Безье третьего порядка между двумя точками.|[Создание кривой Безье третьего порядка](how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Создает линию между двумя точками.|[Создание LineSegment в PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Создает набор кривых Безье третьего порядка.|См. страницу типа <xref:System.Windows.Media.PolyBezierSegment>.|  
|<xref:System.Windows.Media.PolyLineSegment>|Создает набор линий.|См. страницу типа <xref:System.Windows.Media.PolyLineSegment>.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Создает набор кривых Безье второго порядка.|См. страницу <xref:System.Windows.Media.PolyQuadraticBezierSegment>.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Создает кривую Безье второго порядка.|[Создание кривой Безье второго порядка](how-to-create-a-quadratic-bezier-curve.md).|  
  
 Сегменты в <xref:System.Windows.Media.PathFigure> объединяются в одну геометрическую форму, а конечная точка каждого сегмента является начальной точкой следующего сегмента. Свойство <xref:System.Windows.Media.PathFigure.StartPoint%2A> <xref:System.Windows.Media.PathFigure> указывает точку, из которой рисуется первый сегмент. Каждый последующий сегмент начинается в конечной точке предыдущего сегмента. Например, можно определить вертикальную линию от `10,50` до `10,150`, задав для свойства <xref:System.Windows.Media.PathFigure.StartPoint%2A> значение `10,50` и создав <xref:System.Windows.Media.LineSegment> с <xref:System.Windows.Media.LineSegment.Point%2A>ным значением свойства `10,150`.  
  
 В следующем примере создается простой <xref:System.Windows.Media.PathGeometry>, состоящий из одного <xref:System.Windows.Media.PathFigure> с <xref:System.Windows.Media.LineSegment> и отображается с помощью элемента <xref:System.Windows.Shapes.Path>. <xref:System.Windows.Media.PathFigure.StartPoint%2A> объекта <xref:System.Windows.Media.PathFigure> имеет значение `10,20`, а <xref:System.Windows.Media.LineSegment> определяется конечной точкой `100,130`. На следующем рисунке показаны <xref:System.Windows.Media.PathGeometry>, созданные в этом примере.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Контур PathGeometry, содержащий один LineSegment  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Этот пример следует сравнить с предыдущим <xref:System.Windows.Media.LineGeometry> примере.  Синтаксис, используемый для <xref:System.Windows.Media.PathGeometry>, является гораздо более подробным, чем используется для простого <xref:System.Windows.Media.LineGeometry>, и в этом случае может оказаться более разумным использовать класс <xref:System.Windows.Media.LineGeometry>, но подробный синтаксис <xref:System.Windows.Media.PathGeometry> позволяет создавать очень сложные геометрические области.  
  
 Более сложные геометрические объекты можно создавать с помощью сочетания объектов <xref:System.Windows.Media.PathSegment>.  
  
 В следующем примере для создания фигуры используются <xref:System.Windows.Media.BezierSegment>, <xref:System.Windows.Media.LineSegment>и <xref:System.Windows.Media.ArcSegment>. В примере сначала создается кривая Безье третьего порядка, определяющая четыре точки: начальную точку, которая является конечной точкой предыдущего сегмента, конечной точкой (<xref:System.Windows.Media.BezierSegment.Point3%2A>) и двумя контрольными точками (<xref:System.Windows.Media.BezierSegment.Point1%2A> и <xref:System.Windows.Media.BezierSegment.Point2%2A>).  Две контрольные точки кривой Безье третьего порядка ведут себя как магниты, притягивая к себе то, что без них было бы прямой линией. В результате получается кривая. Первая контрольная точка, <xref:System.Windows.Media.BezierSegment.Point1%2A>, влияет на начальную часть кривой; Вторая контрольная точка, <xref:System.Windows.Media.BezierSegment.Point2%2A>, влияет на конечную часть кривой.  
  
 Затем в примере добавляется <xref:System.Windows.Media.LineSegment>, который рисуется между конечной точкой предшествующего <xref:System.Windows.Media.BezierSegment>, предшествующего ей, до точки, указанной свойством <xref:System.Windows.Media.LineSegment>.  
  
 Затем в примере добавляется <xref:System.Windows.Media.ArcSegment>, который рисуется от конечной точки предыдущего <xref:System.Windows.Media.LineSegment> до точки, указанной свойством <xref:System.Windows.Media.ArcSegment.Point%2A>. В примере также указывается x-и y-радиус (<xref:System.Windows.Media.ArcSegment.Size%2A>), угол поворота (<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>), флаг, указывающий, насколько крупнее угол получающейся дуги (<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>), и значение, указывающее, в каком направлении дуга отображается (<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>). На следующей иллюстрации показана фигура, полученная в результате выполнения этого примера.  
  
 ![Объект PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
Объект PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 Еще более сложные геометрические объекты можно создавать с помощью нескольких <xref:System.Windows.Media.PathFigure> объектов в <xref:System.Windows.Media.PathGeometry>.  
  
 В следующем примере создается <xref:System.Windows.Media.PathGeometry> с двумя объектами <xref:System.Windows.Media.PathFigure>, каждый из которых содержит несколько <xref:System.Windows.Media.PathSegment>ных объектов.  Используется <xref:System.Windows.Media.PathFigure> из приведенного выше примера и <xref:System.Windows.Media.PathFigure> с <xref:System.Windows.Media.PolyLineSegment> и <xref:System.Windows.Media.QuadraticBezierSegment>.  <xref:System.Windows.Media.PolyLineSegment> определяется с помощью массива точек, а <xref:System.Windows.Media.QuadraticBezierSegment> определяется с помощью контрольной точки и конечной точки. На следующей иллюстрации показана фигура, полученная в результате выполнения этого примера.  
  
 ![Объект PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
Объект PathGeometry из нескольких фигур  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 Как и класс <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.StreamGeometry> определяет сложную геометрическую форму, которая может содержать кривые, дуги и линии. В отличие от <xref:System.Windows.Media.PathGeometry>, содержимое <xref:System.Windows.Media.StreamGeometry> не поддерживает привязку данных, анимацию или изменение. Используйте <xref:System.Windows.Media.StreamGeometry>, если необходимо описать сложную геометрию, но не требуется издержки на поддержку привязки данных, анимации или изменения. Из-за своей эффективности <xref:System.Windows.Media.StreamGeometry> класс хорошо подходит для описания декоративных элементов.  
  
 Пример см. в разделе [Создание фигуры с помощью класса StreamGeometry](how-to-create-a-shape-using-a-streamgeometry.md).  
  
### <a name="path-markup-syntax"></a>Синтаксис разметки пути  
 Типы <xref:System.Windows.Media.PathGeometry> и <xref:System.Windows.Media.StreamGeometry> поддерживают синтаксис атрибутов [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] с помощью специальной последовательности команд перемещения и рисования. Дополнительные сведения см. в разделе [Синтаксис разметки пути](path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## <a name="composite-geometries"></a>Составные геометрические объекты  
 Составные геометрические объекты можно создавать с помощью <xref:System.Windows.Media.GeometryGroup>, <xref:System.Windows.Media.CombinedGeometry>или путем вызова статического <xref:System.Windows.Media.Geometry> метода <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
- Объект <xref:System.Windows.Media.CombinedGeometry> и метод <xref:System.Windows.Media.Geometry.Combine%2A> выполняют логическую операцию для объединения области, определенной двумя объектами Geometry. <xref:System.Windows.Media.Geometry> объекты, не имеющие области, отбрасываются. Можно объединить только два объекта <xref:System.Windows.Media.Geometry> (хотя эти две геометрические объекты также могут быть составными геометрами).  
  
- Класс <xref:System.Windows.Media.GeometryGroup> создает слияние из содержащихся в нем объектов <xref:System.Windows.Media.Geometry> без объединения их области. В <xref:System.Windows.Media.GeometryGroup>можно добавить любое количество <xref:System.Windows.Media.Geometry> объектов. Пример см. в разделе [Создание составной фигуры](how-to-create-a-composite-shape.md).  
  
 Поскольку они не выполняют операцию объединения, использование <xref:System.Windows.Media.GeometryGroup> объектов обеспечивает преимущества производительности по сравнению с использованием <xref:System.Windows.Media.CombinedGeometry> объектов или метода <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
<a name="combindgeometriessection"></a>   
## <a name="combined-geometries"></a>Объединенные геометрические объекты  
 В предыдущем разделе упоминался объект <xref:System.Windows.Media.CombinedGeometry>, а метод <xref:System.Windows.Media.Geometry.Combine%2A> объединяет область, определенную объектами Geometry, которые они содержат. Перечисление <xref:System.Windows.Media.GeometryCombineMode> указывает, как объединяются геометрические объекты. Возможные значения свойства <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>: <xref:System.Windows.Media.GeometryCombineMode.Union>, <xref:System.Windows.Media.GeometryCombineMode.Intersect>, <xref:System.Windows.Media.GeometryCombineMode.Exclude>и <xref:System.Windows.Media.GeometryCombineMode.Xor>.  
  
 В следующем примере <xref:System.Windows.Media.CombinedGeometry> определяется режимом объединения UNION.  Как <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>, так и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги одного радиуса, но с смещением центров по 50.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Результаты режима объединения UNION](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 В следующем примере <xref:System.Windows.Media.CombinedGeometry> определяется режимом объединения <xref:System.Windows.Media.GeometryCombineMode.Xor>.  Как <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>, так и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги одного радиуса, но с смещением центров по 50.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Результаты режима объединения Xor](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 Дополнительные примеры см. в разделах [Создание составной фигуры](how-to-create-a-composite-shape.md) и [Создание сочетаний геометрических объектов](how-to-create-a-combined-geometry.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Возможности объектов Freezable  
 Поскольку он наследуется от класса <xref:System.Windows.Freezable>, класс <xref:System.Windows.Media.Geometry> предоставляет несколько специальных функций: <xref:System.Windows.Media.Geometry> объекты могут быть объявлены как [ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md), совместно использоваться несколькими объектами и доступными только для чтения для повышения производительности, клонирования и внесения. потокобезопасный. Дополнительные сведения о различных возможностях, предоставляемых <xref:System.Windows.Freezable> объектами, см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>   
## <a name="other-geometry-features"></a>Другие функции класса Geometry  
 Класс <xref:System.Windows.Media.Geometry> также предоставляет полезные служебные методы, например следующие:  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A> — получает область <xref:System.Windows.Media.Geometry>.  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A> — определяет, содержит ли геометрия другую <xref:System.Windows.Media.Geometry>.  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A> — определяет, содержит ли штрих <xref:System.Windows.Media.Geometry> указанную точку.  
  
 Полный список методов см. в описании класса <xref:System.Windows.Media.Geometry>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Синтаксис разметки пути](path-markup-syntax.md)
- [Разделы практического руководства](geometries-how-to-topics.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Обзор объектов Drawing](drawing-objects-overview.md)
