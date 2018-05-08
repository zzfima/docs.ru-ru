---
title: Обзор фигур и базовых средств рисования в приложении WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: adbf982da25ff445d277b7c1b5911217d9825c02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Обзор фигур и базовых средств рисования в приложении WPF
В этом разделе содержится обзор рисования с помощью <xref:System.Windows.Shapes.Shape> объектов. Объект <xref:System.Windows.Shapes.Shape> — это тип <xref:System.Windows.UIElement> , позволяющий нарисовать фигуру на экране. Так как они являются элементами пользовательского интерфейса, <xref:System.Windows.Shapes.Shape> объекты могут использоваться внутри <xref:System.Windows.Controls.Panel> элементы и элементы управления.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет несколько уровней доступа к службам для работы с графикой и службам рендеринга. На верхнем уровне <xref:System.Windows.Shapes.Shape> объектов просты в использовании и предоставляют множество полезных возможностей, таких как разметка и участие в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] системы событий.  
  
  
<a name="shapes"></a>   
## <a name="shape-objects"></a>Объекты фигур  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет ряд готовых к использованию <xref:System.Windows.Shapes.Shape> объектов.  Все объекты фигур наследуются от <xref:System.Windows.Shapes.Shape> класса. Доступные объекты фигур включают <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, и <xref:System.Windows.Shapes.Rectangle>. <xref:System.Windows.Shapes.Shape> объекты используют следующие общие свойства.  
  
-   <xref:System.Windows.Shapes.Shape.Stroke%2A>: Описывает способ рисования контура фигуры.  
  
-   <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Описывает толщину контура фигуры.  
  
-   <xref:System.Windows.Shapes.Shape.Fill%2A>: Описывает способ рисования внутренней области фигуры.  
  
-   Свойства данных, определяющие координаты и вершины, измеряются в аппаратно-независимых пикселях.  
  
 Так как они являются производными от <xref:System.Windows.UIElement>, фигуры объекты могут использоваться внутри панелей и большинства элементов управления. <xref:System.Windows.Controls.Canvas> Панель — особенно подходит для создания сложных рисунков, поскольку она поддерживает абсолютное позиционирование дочерних объектов.  
  
 <xref:System.Windows.Shapes.Line> Позволяет нарисовать линию между двумя точками. В следующем примере показано несколько способов указания координат линии и свойств штриха.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 На следующем рисунке показаны создаваемые <xref:System.Windows.Shapes.Line>.  
  
 ![Рисунок линии](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Несмотря на то что <xref:System.Windows.Shapes.Line> класс предоставить <xref:System.Windows.Shapes.Shape.Fill%2A> значение его свойства не оказывает влияния поскольку <xref:System.Windows.Shapes.Line> нет области.  
  
 Другой общей фигурой является <xref:System.Windows.Shapes.Ellipse>.  Создание <xref:System.Windows.Shapes.Ellipse> , определив фигуры <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства. Рисование окружности, укажите <xref:System.Windows.Shapes.Ellipse> которого <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значения равны.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 На рисунке показан пример отображаемого объекта <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Рисунок эллипса](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a>Использование путей и геометрических фигур  
 <xref:System.Windows.Shapes.Path> Позволяет рисовать кривые линии и сложные фигуры. Эти кривые линии и фигуры описываются с помощью <xref:System.Windows.Media.Geometry> объектов. Для использования <xref:System.Windows.Shapes.Path>, создании <xref:System.Windows.Media.Geometry> и использовать его для задания <xref:System.Windows.Shapes.Path> объекта <xref:System.Windows.Shapes.Path.Data%2A> свойство.  
  
 Существуют разнообразные <xref:System.Windows.Media.Geometry> объектов для выбора. <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, И <xref:System.Windows.Media.EllipseGeometry> классы описывают относительно простые фигуры. Для создания более сложных фигур или кривых, используйте <xref:System.Windows.Media.PathGeometry>.  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a>Классы PathGeometry и PathSegment  
 <xref:System.Windows.Media.PathGeometry> объекты состоят из одного или нескольких <xref:System.Windows.Media.PathFigure> объектов, каждый из которых <xref:System.Windows.Media.PathFigure> представляет различные «рисунок» или фигуры. Каждый <xref:System.Windows.Media.PathFigure> состоит из одного или нескольких <xref:System.Windows.Media.PathSegment> объектов, каждый из которых представляет подключенных часть фигуры или формы. Следующие типы сегмента: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, и <xref:System.Windows.Media.ArcSegment>.  
  
 В следующем примере <xref:System.Windows.Shapes.Path> используется для рисования кривой Безье второго.  
  
 [!code-xaml[geometrysample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 На следующем рисунке показана преобразованная для просмотра фигура.  
  
 ![Рисунок пути](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Дополнительные сведения о <xref:System.Windows.Media.PathGeometry> , а другой <xref:System.Windows.Media.Geometry> классы, в разделе [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a>Сокращенный синтаксис XAML  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], может также использовать специальный сокращенный синтаксис для описания <xref:System.Windows.Shapes.Path>. В следующем примере сокращенный синтаксис используется для рисования сложной фигуры.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 На следующем рисунке показана представляемый <xref:System.Windows.Shapes.Path>.  
  
 ![Рисунок пути](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.PNG "shape_ovw_path")  
  
 <xref:System.Windows.Shapes.Path.Data%2A> Атрибут строка начинается с помощью команды «moveto» обозначается M, задающей начальную точку для пути в системе координат <xref:System.Windows.Controls.Canvas>. <xref:System.Windows.Shapes.Path> данные параметры зависят от регистра. Заглавная буква M указывает абсолютное положение новой текущей точки. Строчная буква m указывала бы относительные координаты. Первый сегмент представляет собой кубическую кривую Безье, которая начинается в точке (100, 200) и заканчивается в точке (400, 175). Эта кривая нарисована с помощью двух контрольных точек (100, 25) и (400, 350). Этот сегмент определен командой C в <xref:System.Windows.Shapes.Path.Data%2A> строке атрибута. Опять же, заглавная буква C указывает абсолютный путь; строчная буква c указывает относительный путь.  
  
 Второй сегмент начинается с команды lineto H, которая рисует горизонтальную линию от предыдущей точки пути (400, 175) до новой точки (280, 175). Поскольку это команда горизонтали «lineto", указанное значение является *x*-координации.  
  
 Полный синтаксис пути, в разделе <xref:System.Windows.Shapes.Path.Data%2A> ссылку и [создать фигуру с помощью объект PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a>Заполнение фигур  
 <xref:System.Windows.Media.Brush> объекты используются для заливки фигуры <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.Fill%2A>. В следующем примере, обводки и заполнения <xref:System.Windows.Shapes.Ellipse> указаны. Обратите внимание, что значения свойств кисти могут задаваться только в формате ключевого слова или шестнадцатеричного значения цвета. Дополнительные сведения о доступных ключевых словах цветов см. в разделе свойств <xref:System.Windows.Media.Colors> класса в <xref:System.Windows.Media> пространства имен.  
  
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
  
 На следующем рисунке показаны создаваемые <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Эллипс](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 Кроме того, можно использовать синтаксис элемента свойства для явного создания <xref:System.Windows.Media.SolidColorBrush> объекта для заливки фигуры сплошным цветом.  
  
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
  
 На рисунке ниже показана фигура, преобразованная для просмотра.  
  
 ![Иллюстрация SolidColorBrush](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")  
  
 Для заполнения фигуры также можно использовать штриховку, градиенты, изображения, шаблоны и многое другое. Дополнительные сведения см. в разделе [Рисование с сплошные цвета и градиенты Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a>Растягиваемые фигуры  
 <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, И <xref:System.Windows.Shapes.Rectangle> классы имеют <xref:System.Windows.Shapes.Shape.Stretch%2A> свойство. Это свойство определяет, каким образом <xref:System.Windows.Shapes.Shape> содержимое объекта (рисуемой фигуры) растягивается на всю <xref:System.Windows.Shapes.Shape> пространства макета объекта. Объект <xref:System.Windows.Shapes.Shape> пространства макета объекта — это объем пространства <xref:System.Windows.Shapes.Shape> выделяется системы макета, из-за либо явно <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> параметр или из-за его <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> параметры. Дополнительные сведения о макете в Windows Presentation Foundation см. в разделе [макета](../../../../docs/framework/wpf/advanced/layout.md) Обзор.  
  
 Свойство Stretch принимает одно из следующих значений.  
  
-   <xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> Не растягивается содержимое объекта.  
  
-   <xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягиваются для заполнения пространства макета.  Пропорции не сохраняются.  
  
-   <xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается настолько, насколько это возможно для заполнения пространства макета, сохраняя исходные пропорции.  
  
-   <xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается до полного заполнения пространства макета, сохраняя исходные пропорции.  
  
 Обратите внимание, что при <xref:System.Windows.Shapes.Shape> растягивается содержимое объекта, <xref:System.Windows.Shapes.Shape> после растягивания рисования контура объекта.  
  
 В следующем примере <xref:System.Windows.Shapes.Polygon> используется для рисования очень маленький треугольник от (0,0) (0,1) и (1,1). <xref:System.Windows.Shapes.Polygon> Объекта <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> установите значение 100, и ее stretch задано значение Fill. В результате <xref:System.Windows.Shapes.Polygon> содержимое объекта (треугольник) растягивается для заполнения большего пространства.  
  
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
## <a name="transforming-shapes"></a>Преобразование фигур  
 <xref:System.Windows.Media.Transform> Класс предоставляет средства для преобразования фигур на двумерной плоскости.  Различные типы преобразования включают поворот (<xref:System.Windows.Media.RotateTransform>), масштабирование (<xref:System.Windows.Media.ScaleTransform>), отклонение (<xref:System.Windows.Media.SkewTransform>) и преобразование (<xref:System.Windows.Media.TranslateTransform>).  
  
 Распространенным преобразованием фигуры является поворот.  Чтобы повернуть фигуру, создайте <xref:System.Windows.Media.RotateTransform> и укажите его <xref:System.Windows.Media.RotateTransform.Angle%2A>. <xref:System.Windows.Media.RotateTransform.Angle%2A> 45 поворачивает элемент на 45 градусов по часовой стрелке; угол 90 поворачивает элемент на 90 градусов по часовой стрелке; и т. д. Задать <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> свойства, если вы хотите точки, о котором поворачивать элемент управления. Эти значения свойств выражаются в системе координат преобразуемого элемента. <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> имеют значения по умолчанию равно нулю. Наконец, примените <xref:System.Windows.Media.RotateTransform> к элементу. Если вы не хотите преобразование влияет на макет, задайте фигуры <xref:System.Windows.UIElement.RenderTransform%2A> свойство.  
  
 В следующем примере <xref:System.Windows.Media.RotateTransform> используется для поворота фигуры 45 градусов относительно верхнего левого угла фигуры (0,0).  
  
 [!code-xaml[transformssample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 В следующем примере другая фигура поворачивается на 45 градусов, но на этот раз — вокруг точки (25, 50).  
  
 [!code-xaml[transformssample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 На следующем рисунке показаны результаты двух преобразований.  
  
 ![Поворот на 45 градусов вокруг различных точек](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 В предыдущих примерах к каждому объекту фигуры применяется одно преобразование. Чтобы применить несколько преобразований к фигуре (или любой другой элемент пользовательского интерфейса), используйте <xref:System.Windows.Media.TransformGroup>.  
  
## <a name="see-also"></a>См. также  
 [Двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Пошаговое руководство. Создание первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
