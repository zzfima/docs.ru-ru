---
title: "Обзор фигур и базовых средств рисования в приложении WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "простое рисование"
  - "Shape - объекты"
  - "фигуры, сведения о фигурах"
  - "векторное рисование, общие сведения"
  - "векторы, рисование"
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Обзор фигур и базовых средств рисования в приложении WPF
В этом разделе содержится обзор рисования с помощью объектов <xref:System.Windows.Shapes.Shape>.  Объект <xref:System.Windows.Shapes.Shape> является типом объекта <xref:System.Windows.UIElement>, который позволяет нарисовать фигуру на экране.  Так как объекты <xref:System.Windows.Shapes.Shape> являются элементами пользовательского интерфейса, они могут использоваться внутри элементов <xref:System.Windows.Controls.Panel> и большинства элементов управления.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет несколько уровней доступа к изображениям и службам отрисовки.  На верхнем слое объекты <xref:System.Windows.Shapes.Shape> просты в использовании и предоставляют множество полезных возможностей, таких как разметка и участие в системе событий [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="shapes"></a>   
## Объекты фигур  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет ряд готовых к использованию объектов <xref:System.Windows.Shapes.Shape>.  Все объекты фигур наследуются от класса <xref:System.Windows.Shapes.Shape>.  Доступны объекты фигур <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> и <xref:System.Windows.Shapes.Rectangle>. Объекты <xref:System.Windows.Shapes.Shape> используют следующие общие свойства.  
  
-   <xref:System.Windows.Shapes.Shape.Stroke%2A>: описывает способ рисования контура фигуры.  
  
-   <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: описывает толщину контура фигуры.  
  
-   <xref:System.Windows.Shapes.Shape.Fill%2A>: описывает способ закрашивания внутренней части фигуры.  
  
-   Свойства данных, определяющие координаты и вершины, измеряемые в [аппаратно\-независимых пикселях](GTMT).  
  
 Поскольку объекты фигур являются производными класса <xref:System.Windows.UIElement>, они могут использоваться внутри панелей и большинства элементов управления.  Панель <xref:System.Windows.Controls.Canvas> особенно подходит для создания сложных рисунков, поскольку она поддерживает абсолютное позиционирование дочерних объектов.  
  
 Класс <xref:System.Windows.Shapes.Line> позволяет нарисовать линию между двумя точками.  В следующем примере показано несколько способов указания координат линии и свойств штриха.  
  
 [!code-xml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 На следующем рисунке показан отображаемый класс <xref:System.Windows.Shapes.Line>.  
  
 ![Иллюстрация линии](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.png "shape\_ovw\_line2")  
  
 Несмотря на то, что класс <xref:System.Windows.Shapes.Line> предоставляет свойство <xref:System.Windows.Shapes.Shape.Fill%2A>, его установка не влияет на объект, так как <xref:System.Windows.Shapes.Line> не имеет внутренней области.  
  
 Другой общей фигурой является <xref:System.Windows.Shapes.Ellipse>.  Создайте объект <xref:System.Windows.Shapes.Ellipse>, определив свойства <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> фигуры.  Чтобы нарисовать круг, определите объект <xref:System.Windows.Shapes.Ellipse> значения которого <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> равны.  
  
 [!code-xml[ShapeOverviews#ShapesOVW1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 На следующем рисунке показан пример отображаемого объекта <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Иллюстрация эллипса](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape\_ovw\_ellipse2")  
  
<a name="paths"></a>   
## Использование путей и геометрических фигур  
 Класс <xref:System.Windows.Shapes.Path> позволяет рисовать кривые линии и сложные фигуры.  Эти кривые линии и фигуры описываются с помощью объектов <xref:System.Windows.Media.Geometry>.  Чтобы использовать объект <xref:System.Windows.Shapes.Path>, создайте объект <xref:System.Windows.Media.Geometry> и используйте его, чтобы задать свойство <xref:System.Windows.Shapes.Path.Data%2A> объекта <xref:System.Windows.Shapes.Path>.  
  
 Имеется выбор из различных объектов <xref:System.Windows.Media.Geometry>.  Классы <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry> и <xref:System.Windows.Media.EllipseGeometry> описывают относительно простые фигуры.  Для создания более сложных фигур или кривых линий используйте класс <xref:System.Windows.Media.PathGeometry>.  
  
<a name="pathgeometry"></a>   
### PathGeometry и PathSegments  
 Объекты <xref:System.Windows.Media.PathGeometry> составлены из одного или нескольких объектов <xref:System.Windows.Media.PathFigure>; каждый объект <xref:System.Windows.Media.PathFigure> представляет отдельную "фигуру" или форму.  Каждый объект <xref:System.Windows.Media.PathFigure> состоит из одного или нескольких объектов <xref:System.Windows.Media.PathSegment>, каждый из которых представляет переходную часть фигуры или формы.  Типы сегментов включают следующие объекты: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment> и <xref:System.Windows.Media.ArcSegment>.  
  
 В следующем примере объект <xref:System.Windows.Shapes.Path> используется для рисования кривой Безье второго порядка.  
  
 [!code-xml[geometrysample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 На следующем рисунке показана отображенная фигура.  
  
 ![Иллюстрация пути](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.png "shape\_ovw\_path2")  
  
 Дополнительные сведения об объекте <xref:System.Windows.Media.PathGeometry> и других классах <xref:System.Windows.Media.Geometry> содержатся в разделе [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="pathdatastring"></a>   
### Сокращенный синтаксис XAML  
 Также в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] можно использовать специальный сокращенный синтаксис для описания объекта <xref:System.Windows.Shapes.Path>.  В следующем примере сокращенный синтаксис используется для рисования сложной фигуры.  
  
```xaml  
<Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 На следующем рисунке показан отображаемый объект <xref:System.Windows.Shapes.Path>.  
  
 ![Иллюстрация пути](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.png "shape\_ovw\_path")  
  
 Строка атрибута <xref:System.Windows.Shapes.Path.Data%2A> начинается с команды moveto, обозначенной M, которая устанавливает начальную точку пути в системе координат <xref:System.Windows.Controls.Canvas>.  Параметры данных <xref:System.Windows.Shapes.Path> вводятся с учетом регистра.  Заглавная буква M указывает абсолютное положение новой текущей точки.  Строчная буква m указывала бы относительные координаты.  Первый сегмент — это [кривая Безье](GTMT) третьего порядка, начинающаяся в точке \(100,200\) и заканчивающаяся в точке \(400,175\), он нарисован с использованием двух контрольных точек \(100,25\) и \(400,350\).  Этот сегмент определен командой C в строке атрибута <xref:System.Windows.Shapes.Path.Data%2A>.  Опять же заглавная буква C указывает абсолютный путь; строчная буква c указывала бы относительный путь.  
  
 Второй сегмент начинается с абсолютной команды горизонтали lineto, обозначенной буквой H, которая определяет, что линия проведена от предшествующей конечной точки подпути \(400,175\) к новой конечной точке \(280,175\).  Поскольку это команда горизонтали lineto, указанное значение является координатой *x*.  
  
 Полный синтаксис пути см. в ссылке в свойства <xref:System.Windows.Shapes.Path.Data%2A> и в разделе [Создание фигуры с помощью PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>   
## Рисование фигур  
 Объекты <xref:System.Windows.Media.Brush> используются для рисования свойств <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.Fill%2A> фигуры.  В следующем примере задается штриховка и заливка объекта <xref:System.Windows.Shapes.Ellipse>.  Обратите внимание, что допустимые входные данные свойств кисти могут быть либо ключевым словом, либо шестнадцатеричным значением цвета.  Для дополнительных сведений о доступных ключевых словах цветов см. свойства класса <xref:System.Windows.Media.Colors> в пространстве имен <xref:System.Windows.Media>.  
  
```  
  
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
  
```  
  
 На следующем рисунке показан отображенный объект <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Эллипс](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.png "shape\_ovw\_ellipsefill")  
  
 Кроме того, можно использовать синтаксис элемента свойства для явного создания объекта <xref:System.Windows.Media.SolidColorBrush> при рисовании фигуры сплошным цветом.  
  
```  
  
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 На следующем рисунке показана отображенная фигура.  
  
 ![Иллюстрация SolidColorBrush](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.png "shape\_ovw\_solidcolorbrush")  
  
 Можно также заштриховать фигуру или заполнить градиентами, изображениями, узорами и т.д.  Дополнительные сведения см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>   
## Растягиваемые фигуры  
 Все классы <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> и <xref:System.Windows.Shapes.Rectangle> имеют свойство <xref:System.Windows.Shapes.Shape.Stretch%2A>.  Это свойство определяет, как содержимое объекта <xref:System.Windows.Shapes.Shape> \(фигура, которая будет нарисована\) должно быть растянуто для заполнения пространства макета объекта <xref:System.Windows.Shapes.Shape>.  Пространство макета объекта <xref:System.Windows.Shapes.Shape> — это количество пространства, которое система выделила для размещения объекта <xref:System.Windows.Shapes.Shape> или явным заданием параметра <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>, или с учетом параметров <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.  Дополнительные сведения о макете в Windows Presentation Foundation содержатся в обзоре [Макет](../../../../docs/framework/wpf/advanced/layout.md).  
  
 Свойство растягивания принимает одно из следующих значений:  
  
-   <xref:System.Windows.Media.Stretch>: содержимое объекта <xref:System.Windows.Shapes.Shape> не растягивается.  
  
-   <xref:System.Windows.Media.Stretch>: содержимое объекта <xref:System.Windows.Shapes.Shape> растягивается для заполнения пространства макета.  Коэффициент пропорциональности не сохраняется.  
  
-   <xref:System.Windows.Media.Stretch>: содержимое объекта <xref:System.Windows.Shapes.Shape> растягивается, насколько это возможно для заполнения пространства макета с сохранением исходного коэффициента пропорциональности.  
  
-   <xref:System.Windows.Media.Stretch>: содержимое объекта <xref:System.Windows.Shapes.Shape> растягивается до полного заполнения пространства макета с сохранением исходного коэффициента пропорциональности.  
  
 Обратите внимание, что когда содержимое объекта <xref:System.Windows.Shapes.Shape> растянуто, контур объекта <xref:System.Windows.Shapes.Shape> рисуется после растягивания.  
  
 В следующем примере используется объект <xref:System.Windows.Shapes.Polygon> для рисования очень небольшого треугольника с вершинами \(0,0\), \(0,1\) и \(1,1\).  Свойства <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> объекта <xref:System.Windows.Shapes.Polygon> имеют значение 100, и для свойства растягивания установлено значение Fill.  В результате, содержимое объекта <xref:System.Windows.Shapes.Polygon> \(треугольник\) растягивается для заполнения большего пространства.  
  
```  
...  
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
...  
```  
  
```  
...  
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
...  
```  
  
<a name="transforms"></a>   
## Преобразование фигур  
 Класс <xref:System.Windows.Media.Transform> предоставляет средства для преобразования фигур в двумерной плоскости.  Различные типы преобразования включают поворот \(<xref:System.Windows.Media.RotateTransform>\), масштабирование \(<xref:System.Windows.Media.ScaleTransform>\), наклон \(<xref:System.Windows.Media.SkewTransform>\) и сдвиг \(<xref:System.Windows.Media.TranslateTransform>\).  
  
 Распространенным преобразованием фигуры является поворот.  Чтобы повернуть фигуру, создайте объект <xref:System.Windows.Media.RotateTransform> и укажите свойство <xref:System.Windows.Media.RotateTransform.Angle%2A>.  Значение свойства <xref:System.Windows.Media.RotateTransform.Angle%2A> 45 поворачивает элемент на 45 градусов по часовой стрелке; угол 90 поворачивает элемент на 90 градусов по часовой стрелке; и т. д.  Установите свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A>, если нужно управлять точкой вращения элемента.  Эти значения свойств выражены в координатном пространстве элемента, к которому применяется преобразование.  Свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> по умолчанию имеют нулевые значения.  Наконец, примените объект <xref:System.Windows.Media.RotateTransform> к элементу.  Если не требуется воздействия преобразования на макет, установите свойство <xref:System.Windows.UIElement.RenderTransform%2A> фигуры.  
  
 В следующем примере для поворота фигуры на 45 градусов относительно левого верхнего угла \(0,0\) используется объект <xref:System.Windows.Media.RotateTransform>.  
  
 [!code-xml[transformssample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 В следующем примере фигура поворачивается на 45 градусов, но в тот раз относительно точки \(25,50\).  
  
 [!code-xml[transformssample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 Ниже показаны результаты применения двух преобразований.  
  
 ![Вращения на 45 градусов с различными точками центра](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.png "wcpsdk\_graphicsmm\_rotatetransform45degrees")  
  
 В предыдущих примерах одно преобразование было применено к каждому объекту фигуры.  Чтобы применить несколько преобразований к фигуре \(или любому другому элементу пользовательского интерфейса\), используйте объект <xref:System.Windows.Media.TransformGroup>.  
  
## См. также  
 [двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Пошаговое руководство. Начало работы с WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)