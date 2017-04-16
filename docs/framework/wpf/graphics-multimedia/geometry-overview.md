---
title: "Общие сведения о классе Geometry | Microsoft Docs"
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
  - "классы, геометрия"
  - "CombinedGeometry - класс"
  - "EllipseGeometry - класс"
  - "геометрические классы"
  - "графика, геометрические классы"
  - "LineGeometry - класс"
  - "класс PathGeometry"
  - "RectangleGeometry - класс"
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Общие сведения о классе Geometry
В данном обзоре объясняется, как использовать классы [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> для описания фигур.  Также в данном обзоре описаны различия между объектами класса <xref:System.Windows.Media.Geometry> и элементами класса <xref:System.Windows.Shapes.Shape>.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="wcpsdk_graphics_geometry_introduction"></a>   
## Понятие о классе Geometry  
 Класс <xref:System.Windows.Media.Geometry> и производные от него классы, например, <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry> и <xref:System.Windows.Media.CombinedGeometry> позволяют описывать геометрию двумерной фигуры.  Данные геометрические описания имеют множество применений. Например, их можно использовать при определении фигуры для вывода на экран или при проверки нажатия и задании областей отсечения.  Помимо этого геометрические описания можно использовать для определения пути анимации.  
  
 Объекты класса <xref:System.Windows.Media.Geometry> могут быть простыми, такими как прямоугольники и круги, или сложными, созданными из двух или более геометрических объектов.  Более сложные геометрические объекты могут быть созданы с помощью классов <xref:System.Windows.Media.PathGeometry> и <xref:System.Windows.Media.StreamGeometry>, позволяющих описывать дуги и кривые.  
  
 Поскольку класс <xref:System.Windows.Media.Geometry> является наследником класса <xref:System.Windows.Freezable>, то объекты класса <xref:System.Windows.Media.Geometry> обладают рядом специальных возможностей: их можно объявлять как [ресурсы](../../../../docs/framework/wpf/advanced/xaml-resources.md), которые могут совместно использоваться несколькими объектами, делать доступными только для чтения с целью повышения производительности, клонировать и делать потокобезопасными.  Дополнительные сведения о различных возможностях, предоставляемых объектами класса <xref:System.Windows.Freezable>, см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## ГеометрияФигуры  
 Сходство классов <xref:System.Windows.Media.Geometry> и <xref:System.Windows.Shapes.Shape> заключается в том, что они описывают двумерные фигуры \(к примеру, сравните классы <xref:System.Windows.Media.EllipseGeometry> и <xref:System.Windows.Shapes.Ellipse>\), но между ними существуют важные отличия.  
  
 Например, класс <xref:System.Windows.Media.Geometry> наследуется от класса <xref:System.Windows.Freezable>, а класс <xref:System.Windows.Shapes.Shape> наследуется от класса <xref:System.Windows.FrameworkElement>.  Поскольку последние являются элементами, объекты класса <xref:System.Windows.Shapes.Shape> могут отображаться сами и участвовать в системе макета, а объекты класса <xref:System.Windows.Media.Geometry> не могут.  
  
 Несмотря на то, что с объектами <xref:System.Windows.Shapes.Shape> легче работать, чем с объектами <xref:System.Windows.Media.Geometry>, объекты <xref:System.Windows.Media.Geometry> являются более универсальными.  Например, объект <xref:System.Windows.Shapes.Shape> можно использовать для отображения двумерной графики, а объект <xref:System.Windows.Media.Geometry> можно использовать для определения геометрической области для двумерной графики, определения области отсечения или определения области для проверки попадания курсора.  
  
### Подкласс Path класса Shape  
 Класс <xref:System.Windows.Shapes.Path> наследуется от класса <xref:System.Windows.Shapes.Shape> и фактически использует класс <xref:System.Windows.Media.Geometry> для описания своего содержимого.  Задав свойство <xref:System.Windows.Shapes.Path.Data%2A> класса <xref:System.Windows.Shapes.Path> с помощью <xref:System.Windows.Media.Geometry>, и задав его свойства <xref:System.Windows.Shapes.Shape.Fill%2A> и <xref:System.Windows.Shapes.Shape.Stroke%2A>, можно отобразить объект класса <xref:System.Windows.Media.Geometry>.  
  
<a name="commonproperties"></a>   
## Общие свойства, которые может принимать объект класса Geometry  
 В предыдущих разделах упоминалось, что объекты класса Geometry могут использоваться с другими объектами в различных целях, например, для рисования фигур, анимации и отсечения.  В следующей таблице перечислены несколько классов, имеющих свойства, которые может принимать объект класса <xref:System.Windows.Media.Geometry>.  
  
|Тип|Свойство.|  
|---------|---------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## Простые типы класса Geometry  
 Базовым классом для всех геометрических объектов является абстрактный класс <xref:System.Windows.Media.Geometry>.  Классы, являющиеся производными от класса <xref:System.Windows.Media.Geometry>, можно сгруппировать в три категории: простые объекты Geometry, объекты PathGeometry и составные объекты Geometry.  
  
 Простые геометрические классы включают классы <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry> и <xref:System.Windows.Media.EllipseGeometry> и используются для создания основных геометрических фигур, таких как линии, прямоугольники и окружности.  
  
-   Объект класса <xref:System.Windows.Media.LineGeometry> определяется путем задания для линии начальной и конечной точек.  
  
-   Объект класса <xref:System.Windows.Media.RectangleGeometry> определяется структурой <xref:System.Windows.Rect>, которая задает его относительное положение, высоту и ширину.  Можно создать скругленный прямоугольник, задав свойства <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> и <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>.  
  
-   Объект класса <xref:System.Windows.Media.EllipseGeometry> определяется центральной точкой, x\-радиусом и y\-радиусом.  В следующих примерах показано, как создать простые объекты Geometry для отрисовки на экране и для отсечения.  
  
 Эти же фигуры, а также более сложные фигуры, могут быть созданы с помощью класса <xref:System.Windows.Media.PathGeometry> или путем объединения геометрических объектов, но данные классы предоставляют более простые средства для создания основных геометрических фигур.  
  
 В следующем примере показано создание и отображение объекта класса <xref:System.Windows.Media.LineGeometry>.  Как было отмечено ранее, объект класса <xref:System.Windows.Media.Geometry> не может нарисовать сам себя, поэтому в примере используются фигуры класса <xref:System.Windows.Shapes.Path> для отображения линии.  Так как линия не имеет области, задание свойства <xref:System.Windows.Shapes.Shape.Fill%2A> класса <xref:System.Windows.Shapes.Path> никак не повлияет на объект. Вместо этого необходимо задать значения только для свойств <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.  На следующем рисунке представлен результат выполнения данного примера.  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
LineGeometry, построенная от точки с координатами \(10,20\) до точки с координатами \(100,130\)  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 В следующем примере демонстрируется создание и отображение объекта класса <xref:System.Windows.Media.EllipseGeometry>.  В данном примере свойство <xref:System.Windows.Media.EllipseGeometry.Center%2A> класса <xref:System.Windows.Media.EllipseGeometry> задается точкой с координатами `50,50`, а x\-радиус и y\-радиус задаются равными `50`. В результате получается круг диаметром 100.  Внутренняя часть эллипса закрашивается путем задания значения свойства Fill элемента Path, в данном случае <xref:System.Windows.Media.Brushes.Gold%2A>.  На следующем рисунке представлен результат выполнения данного примера.  
  
 ![EllipseGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-ellipse.png "graphicsmm\_ellipse")  
EllipseGeometry с центром в точке с координатами \(50,50\)  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 В следующем примере демонстрируется создание и отображение <xref:System.Windows.Media.RectangleGeometry>.  Положение и размеры прямоугольника определяются структурой <xref:System.Windows.Rect>.  Относительное положение задано координатой `50,50`, а высота и ширина равны `25`. В результате получается квадрат.  На следующем рисунке представлен результат выполнения данного примера.  
  
 ![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.png "graphicsmm\_rectangle")  
RectangleGeometry, нарисованный в точке с координатами 50,50  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 В следующем примере показано использование объекта класса <xref:System.Windows.Media.EllipseGeometry> в качестве области отсечения изображения.  Объект <xref:System.Windows.Controls.Image> определяется значением свойства <xref:System.Windows.FrameworkElement.Width%2A>, равным 200, и значением свойства <xref:System.Windows.FrameworkElement.Height%2A>, равным 150.  Объект <xref:System.Windows.Media.EllipseGeometry> со значением <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A>, равным 100, значением <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A>, равным 75, и значением <xref:System.Windows.Media.EllipseGeometry.Center%2A>, равным 100,75, задается свойством изображения <xref:System.Windows.UIElement.Clip%2A>.  Будет отображаться только часть изображения, находящаяся внутри эллипса.  На следующем рисунке представлен результат выполнения данного примера.  
  
 ![Изображение с и без обрезки](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipexample.png "graphicsmm\_clipexample")  
Использование объекта EllipseGeometry для отсечения элемента управления Image  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## Объекты PathGeometry  
 Класс <xref:System.Windows.Media.PathGeometry> и его облегченный эквивалент класс <xref:System.Windows.Media.StreamGeometry>, предоставляют средства для описания нескольких сложных фигур, состоящих из дуг, кривых и линий.  
  
 Внутри класса <xref:System.Windows.Media.PathGeometry> находится коллекция объектов <xref:System.Windows.Media.PathFigure>, названных таким образом, потому что каждая фигура описывает дискретную форму в классе <xref:System.Windows.Media.PathGeometry>.  Каждый объект <xref:System.Windows.Media.PathFigure> состоит из одного или нескольких объектов <xref:System.Windows.Media.PathSegment>, каждый из которых описывается сегмент фигуры.  
  
 Существует много типов сегментов.  
  
|Тип сегмента|Описание|Пример|  
|------------------|--------------|------------|  
|<xref:System.Windows.Media.ArcSegment>|Создает эллиптическую дугу между двумя точками.|[Создание эллиптической дуги](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Создает кривую Безье третьего порядка между двумя точками.|[Создание кривой Безье третьего порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Создает линию между двумя точками.|[Создание LineSegment в PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Создает набор кривых Безье третьего порядка.|См. в описании страницы типа класса <xref:System.Windows.Media.PolyBezierSegment>.|  
|<xref:System.Windows.Media.PolyLineSegment>|Создает набор линий.|См. в описании страницы типа класса <xref:System.Windows.Media.PolyLineSegment>.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Создает набор кривых Безье второго порядка.|См. в описании страницы типа класса <xref:System.Windows.Media.PolyQuadraticBezierSegment>.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Создает кривую Безье второго порядка.|[Создание кривой Безье второго порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).|  
  
 Сегменты объекта <xref:System.Windows.Media.PathFigure> объединяются в одну геометрическую форму, причем конечная точка каждого сегмента совпадает с начальной точкой следующего сегмента.  Свойство <xref:System.Windows.Media.PathFigure.StartPoint%2A> класса <xref:System.Windows.Media.PathFigure> задает точку, из которой рисуется первый сегмент.  Каждый последующий сегмент начинается в конечной точке предыдущего сегмента.  Например, вертикальную линию из точки с координатами `10,50` в точку с координатами `10,150` можно определить, задав для свойства <xref:System.Windows.Media.PathFigure.StartPoint%2A> значение `10,50` и создав объект <xref:System.Windows.Media.LineSegment> со свойством <xref:System.Windows.Media.LineSegment.Point%2A>, имеющим значение `10,150`.  
  
 В следующем примере создается простой объект <xref:System.Windows.Media.PathGeometry>, состоящий из одного объекта <xref:System.Windows.Media.PathFigure> с <xref:System.Windows.Media.LineSegment>, и отображается с помощью элемента <xref:System.Windows.Shapes.Path>.  Для объекта <xref:System.Windows.Media.PathFigure> свойство <xref:System.Windows.Media.PathFigure.StartPoint%2A> имеет значение `10,20`, а объект <xref:System.Windows.Media.LineSegment> задается с конечной точкой `100,130`.  На следующем рисунке показан объект <xref:System.Windows.Media.PathGeometry>, созданный в данном примере.  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
 Объект PathGeometry, содержащий один объект LineSegment  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Стоит сравнить этот пример с предыдущим примером <xref:System.Windows.Media.LineGeometry>.  Синтаксис, используемый для объектов <xref:System.Windows.Media.PathGeometry>, является гораздо более подробным, чем синтаксис, который используется для простых объектов <xref:System.Windows.Media.LineGeometry>, и в этом случае лучше использовать объект <xref:System.Windows.Media.LineGeometry>, но подробный синтаксис <xref:System.Windows.Media.PathGeometry> позволяет создавать очень сложные геометрические области.  
  
 Более сложные объекты Geometry можно создать с помощью комбинации объектов <xref:System.Windows.Media.PathSegment>.  
  
 В следующем примере для создания фигуры используются объекты <xref:System.Windows.Media.BezierSegment>, <xref:System.Windows.Media.LineSegment> и <xref:System.Windows.Media.ArcSegment>.  В примере сначала создается кривая Безье третьего порядка путем задания четырех точек: начальной точки, которая является конечной точкой предыдущего сегмента, конечной точки \(<xref:System.Windows.Media.BezierSegment.Point3%2A>\) и двух контрольных точек \(<xref:System.Windows.Media.BezierSegment.Point1%2A> и <xref:System.Windows.Media.BezierSegment.Point2%2A>\).  Две контрольные точки кривой Безье третьего порядка подобны магнитам, притягивающим к себе сегменты кривой \(в противном случае она была бы прямой\), создавая таким образом кривую.  Первая контрольная точка <xref:System.Windows.Media.BezierSegment.Point1%2A>, влияет на начальный участок кривой, а вторая контрольная точка <xref:System.Windows.Media.BezierSegment.Point2%2A>, влияет на конечный участок кривой.  
  
 На следующем шаге добавляется объект <xref:System.Windows.Media.LineSegment>, который отрисовывается из конечной точки предыдущего объекта <xref:System.Windows.Media.BezierSegment> в точку, заданную <xref:System.Windows.Media.LineSegment>.  
  
 Затем добавляется объект <xref:System.Windows.Media.ArcSegment>, который отрисовывается из конечной точки предыдущего <xref:System.Windows.Media.LineSegment> в точку, заданную <xref:System.Windows.Media.ArcSegment.Point%2A>.  В примере также указываются x и y радиусы дуги \(<xref:System.Windows.Media.ArcSegment.Size%2A>\), угол поворота \(<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>\), флаг, указывающий насколько большим должен быть угол полученной дуги \(<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>\), и значение, указывающее, в каком направлении строится дуга \(<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>\).  На следующем рисунке показана форма, созданная в данном примере.  
  
 ![Объект PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path2.png "graphicsmm\_path2")  
 Объект PathGeometry  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 С помощью нескольких объектов <xref:System.Windows.Media.PathFigure> в коллекции <xref:System.Windows.Media.PathGeometry> можно создать еще более сложные геометрические объекты.  
  
 В следующем примере создается объект <xref:System.Windows.Media.PathGeometry> с двумя объектами <xref:System.Windows.Media.PathFigure>, каждый из которых содержит несколько объектов <xref:System.Windows.Media.PathSegment>.  Используются <xref:System.Windows.Media.PathFigure> из предыдущего примера и <xref:System.Windows.Media.PathFigure> с <xref:System.Windows.Media.PolyLineSegment> и <xref:System.Windows.Media.QuadraticBezierSegment>.  Объект <xref:System.Windows.Media.PolyLineSegment> задан с помощью массива точек, а объект <xref:System.Windows.Media.QuadraticBezierSegment> задан с помощью контрольной точки и конечной точки.  На следующем рисунке показана форма, созданная в данном примере.  
  
 ![Объект PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path.png "graphicsmm\_path")  
Объект PathGeometry с несколькими фигурами  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### Объект StreamGeometry  
 Как и класс <xref:System.Windows.Media.PathGeometry>, класс <xref:System.Windows.Media.StreamGeometry> определяет сложную геометрическую форму, которая может содержать кривые, дуги и линии.  В отличие от объектов <xref:System.Windows.Media.PathGeometry>, содержимое <xref:System.Windows.Media.StreamGeometry> не поддерживает привязку данных, анимацию или изменения.  Объект используется <xref:System.Windows.Media.StreamGeometry> для описания сложной геометрии, но без служебных данных поддержки привязки данных, анимации или изменения.  Ввиду своей эффективности, класс <xref:System.Windows.Media.StreamGeometry> лучше всего подходит для описания декоративных элементов.  
  
 Пример см. в разделе [Создание фигуры с помощью StreamGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
### Синтаксис разметки пути  
 Типы <xref:System.Windows.Media.PathGeometry> и <xref:System.Windows.Media.StreamGeometry> поддерживают синтаксис атрибута [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] с использованием специальных последовательностей команд перемещения и рисования.  Дополнительные сведения см. в разделе [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## Составные объекты Geometry  
 Составные объекты Geometry можно создать с помощью <xref:System.Windows.Media.GeometryGroup>, <xref:System.Windows.Media.CombinedGeometry> или путем вызова статического метода <xref:System.Windows.Media.Geometry> <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
-   Объект <xref:System.Windows.Media.CombinedGeometry> и метод <xref:System.Windows.Media.Geometry.Combine%2A> выполняют логическую операцию объединения областей, определенных двумя объектами Geometry.  Объекты <xref:System.Windows.Media.Geometry>, не имеющие занимаемой области, отбрасываются.  Можно скомбинировать только два объекта <xref:System.Windows.Media.Geometry> \(хотя эти два объекта также могут быть составными\).  
  
-   Класс <xref:System.Windows.Media.GeometryGroup> создает объединение содержащихся в нем объектов <xref:System.Windows.Media.Geometry> без объединения занимаемых ими областей.  К объекту <xref:System.Windows.Media.GeometryGroup> можно добавить любое число объектов <xref:System.Windows.Media.Geometry>.  Пример см. в разделе [Создание составной фигуры](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md).  
  
 Поскольку они не выполняют операцию объединения, использование объектов <xref:System.Windows.Media.GeometryGroup> обеспечивает выигрыш в производительности по сравнению с использованием объектов <xref:System.Windows.Media.CombinedGeometry> или метода <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
<a name="combindgeometriessection"></a>   
## Комбинированные объекты Geometry  
 В предыдущем подразделе упоминалось, что объект <xref:System.Windows.Media.CombinedGeometry> и метод <xref:System.Windows.Media.Geometry.Combine%2A> объединяют области, занимаемые содержащимися в них объектами Geometry.  Перечисление <xref:System.Windows.Media.GeometryCombineMode> задает способ комбинирования объектов Geometry.  Возможны следующие значения свойства <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>: <xref:System.Windows.Media.GeometryCombineMode>, <xref:System.Windows.Media.GeometryCombineMode> <xref:System.Windows.Media.GeometryCombineMode> и <xref:System.Windows.Media.GeometryCombineMode>.  
  
 В следующем примере объект <xref:System.Windows.Media.CombinedGeometry> определен режимом объединения Union.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> задаются как круги с одинаковыми радиусами, но с центрами, смещенными на 50.  
  
 [!code-xml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Результаты объединенного режима Union](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.png "mil\_task\_combined\_geometry\_union")  
  
 В следующем примере объект <xref:System.Windows.Media.CombinedGeometry> определен режимом объединения <xref:System.Windows.Media.GeometryCombineMode>.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> задаются как круги с одинаковыми радиусами, но с центрами, смещенными на 50.  
  
 [!code-xml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Результаты объединенного режима Xor](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.png "mil\_task\_combined\_geometry\_xor")  
  
 Дополнительные примеры см. в разделах [Создание составной фигуры](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md) и [Создание объединенных геометрических объектов](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-combined-geometry.md).  
  
<a name="freezable_features"></a>   
## Возможности объектов Freezable  
 Поскольку класс наследуется от класса <xref:System.Windows.Freezable>, класс <xref:System.Windows.Media.Geometry> предоставляет несколько особенных возможностей: объекты класса <xref:System.Windows.Media.Geometry> можно объявлять как [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md), которые могут совместно использоваться несколькими объектами, делать доступными только для чтения с целью повышения производительности, клонировать и делать потокобезопасными.  Дополнительные сведения о различных возможностях, предоставляемых объектами класса <xref:System.Windows.Freezable>, см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>   
## Другие возможности объектов Geometry  
 Класс <xref:System.Windows.Media.Geometry> также предоставляет полезные служебные методы, например:  
  
-   <xref:System.Windows.Media.Geometry.GetArea%2A> — возвращает область, занимаемую объектом <xref:System.Windows.Media.Geometry>.  
  
-   <xref:System.Windows.Media.Geometry.FillContains%2A> — определяет, есть ли в объекте Geometry другие объекты <xref:System.Windows.Media.Geometry>.  
  
-   <xref:System.Windows.Media.Geometry.StrokeContains%2A> — определяет, содержит ли объект <xref:System.Windows.Media.Geometry> указанную точку.  
  
 Полный список методов см. в классе <xref:System.Windows.Media.Geometry>.  
  
## См. также  
 <xref:System.Windows.Media.Geometry>   
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.GeometryDrawing>   
 [двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)