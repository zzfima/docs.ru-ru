---
title: Формы и базовый обзор рисунка
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
ms.openlocfilehash: 44104bec478f1fbb10acc0e591af43ea95fecdc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141332"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Обзор фигур и базовых средств рисования в приложении WPF
Эта тема дает обзор того, <xref:System.Windows.Shapes.Shape> как рисовать с объектами. A <xref:System.Windows.Shapes.Shape> — это <xref:System.Windows.UIElement> тип, позволяющий нарисовать фигуру на экране. Поскольку они являются <xref:System.Windows.Shapes.Shape> элементами uI, объекты могут использоваться внутри <xref:System.Windows.Controls.Panel> элементов и большинства элементов управления.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет несколько уровней доступа к службам для работы с графикой и службам рендеринга. В верхнем <xref:System.Windows.Shapes.Shape> слое объекты просты в использовании и предоставляют множество полезных функций, таких как компоновка и участие в системе [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] событий.  

<a name="shapes"></a>
## <a name="shape-objects"></a>Объекты фигур  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет ряд готовых к <xref:System.Windows.Shapes.Shape> использованию объектов.  Все объекты <xref:System.Windows.Shapes.Shape> формы наследуют сяизм от класса. Доступные объекты <xref:System.Windows.Shapes.Path>формы <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline>включают, <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Line>, , , и . <xref:System.Windows.Shapes.Shape>объекты имеют следующие общие свойства.  
  
- <xref:System.Windows.Shapes.Shape.Stroke%2A>: Описывает, как окрашен контур формы.  
  
- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Описывает толщину контура фигуры.  
  
- <xref:System.Windows.Shapes.Shape.Fill%2A>: Описывает, как окрашен интерьер формы.  
  
- Свойства данных, определяющие координаты и вершины, измеряются в аппаратно-независимых пикселях.  
  
 Потому что <xref:System.Windows.UIElement>они вытекают из, формы объектов могут быть использованы внутри панелей и большинство элементов управления. Панель <xref:System.Windows.Controls.Canvas> является особенно хорошим выбором для создания сложных чертежей, поскольку она поддерживает абсолютное позиционирование своих детских объектов.  
  
 Класс <xref:System.Windows.Shapes.Line> позволяет провести линию между двумя точками. В следующем примере показано несколько способов указания координат линии и свойств штриха.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 Следующее изображение показывает <xref:System.Windows.Shapes.Line>отображенные .  
  
 ![Иллюстрация линии](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Хотя <xref:System.Windows.Shapes.Line> класс предоставляет <xref:System.Windows.Shapes.Shape.Fill%2A> свойство, установка не имеет <xref:System.Windows.Shapes.Line> никакого эффекта, поскольку не имеет области.  
  
 Другой распространенной <xref:System.Windows.Shapes.Ellipse>формой является .  Создайте, <xref:System.Windows.Shapes.Ellipse> определив <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> свойства и свойства фигуры. Чтобы нарисовать круг, <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> укажите, <xref:System.Windows.Shapes.Ellipse> чьи и значения равны.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 На следующем изображении показан пример <xref:System.Windows.Shapes.Ellipse>отрисованных.  
  
 ![Иллюстрация эллипса](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a>Использование путей и геометрических фигур  
 Класс <xref:System.Windows.Shapes.Path> позволяет рисовать кривые и сложные формы. Эти кривые и формы <xref:System.Windows.Media.Geometry> описаны с помощью объектов. Чтобы использовать <xref:System.Windows.Shapes.Path>, вы <xref:System.Windows.Media.Geometry> создаете и <xref:System.Windows.Shapes.Path> использовать его <xref:System.Windows.Shapes.Path.Data%2A> для установки свойства объекта.  
  
 Есть множество объектов <xref:System.Windows.Media.Geometry> на выбор. В <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry>, <xref:System.Windows.Media.EllipseGeometry> и классы описывают относительно простые формы. Для создания более сложных форм или <xref:System.Windows.Media.PathGeometry>кривых используйте .  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a>Классы PathGeometry и PathSegment  
 <xref:System.Windows.Media.PathGeometry>объекты состоят из одного <xref:System.Windows.Media.PathFigure> или нескольких объектов; каждая из них <xref:System.Windows.Media.PathFigure> представляет собой различную «фигуру» или форму. Каждый из них <xref:System.Windows.Media.PathFigure> сам <xref:System.Windows.Media.PathSegment> состоит из одного или нескольких объектов, каждый из которых представляет собой связанную часть фигуры или формы. Типы сегментов <xref:System.Windows.Media.LineSegment>включают <xref:System.Windows.Media.BezierSegment>в <xref:System.Windows.Media.ArcSegment>себя следующие: , , и .  
  
 В следующем примере <xref:System.Windows.Shapes.Path> используется для рисования квадратной кривой Безье.  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 На следующем рисунке показана преобразованная для просмотра фигура.  
  
 ![Иллюстрация пути](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Для получения <xref:System.Windows.Media.PathGeometry> дополнительной информации о других <xref:System.Windows.Media.Geometry> классах, см. [Geometry Overview](geometry-overview.md)  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a>Сокращенный синтаксис XAML  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], вы также можете использовать специальный сокращенный <xref:System.Windows.Shapes.Path>синтаксис для описания . В следующем примере сокращенный синтаксис используется для рисования сложной фигуры.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 Следующее изображение показывает <xref:System.Windows.Shapes.Path>отображенные .  
  
 ![Иллюстрация пути](./media/shape-ovw-path.PNG "shape_ovw_path")  
  
 Строка <xref:System.Windows.Shapes.Path.Data%2A> атрибута начинается с команды "moveto", указанной M, которая устанавливает отправную <xref:System.Windows.Controls.Canvas>точку для пути в системе координат . <xref:System.Windows.Shapes.Path>параметры данных чувствительны к случаям. Столица M указывает абсолютное местоположение для новой текущей точки. Строчная буква m указывала бы относительные координаты. Первый сегмент представляет собой кубическую кривую Безье, которая начинается в точке (100, 200) и заканчивается в точке (400, 175). Эта кривая нарисована с помощью двух контрольных точек (100, 25) и (400, 350). Этот сегмент указан командой C <xref:System.Windows.Shapes.Path.Data%2A> в строке атрибута. Опять же, заглавная буква C указывает абсолютный путь; строчная буква c указывает относительный путь.  
  
 Второй сегмент начинается с команды lineto H, которая рисует горизонтальную линию от предыдущей точки пути (400, 175) до новой точки (280, 175). Поскольку это горизонтальная команда "lineto", *x*указанное значение является x-координацией.  
  
 Для полного синтаксиса <xref:System.Windows.Shapes.Path.Data%2A> пути см. ссылку и [создайте форму с помощью траектории.](how-to-create-a-shape-by-using-a-pathgeometry.md)  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a>Заполнение фигур  
 <xref:System.Windows.Media.Brush>объекты используются для рисования формы <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.Fill%2A>. В следующем примере <xref:System.Windows.Shapes.Ellipse> указаны штрих и заливка. Обратите внимание, что значения свойств кисти могут задаваться только в формате ключевого слова или шестнадцатеричного значения цвета. Для получения дополнительной информации о доступных <xref:System.Windows.Media.Colors> ключевых <xref:System.Windows.Media> словах цвета см.  
  
```xaml
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
  
 Следующее изображение показывает <xref:System.Windows.Shapes.Ellipse>отображенные .  
  
 ![Эллипс](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 Кроме того, можно использовать синтаксис элемента <xref:System.Windows.Media.SolidColorBrush> свойств для явного создания объекта для рисования формы твердым цветом.  
  
```xaml
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
  
 ![Иллюстрация SolidColorBrush](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")  
  
 Для заполнения фигуры также можно использовать штриховку, градиенты, изображения, шаблоны и многое другое. Для получения дополнительной информации смотрите [картина с твердыми цветами и градиентами Обзор](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a>Растягиваемые фигуры  
 В <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline>, <xref:System.Windows.Shapes.Rectangle> и классы <xref:System.Windows.Shapes.Shape.Stretch%2A> все имеют свойство. Это свойство определяет, как содержимое <xref:System.Windows.Shapes.Shape> объекта (форма, подаваемый) растягивается для заполнения пространства макета <xref:System.Windows.Shapes.Shape> объекта. Пространство <xref:System.Windows.Shapes.Shape> компоновки объекта — <xref:System.Windows.Shapes.Shape> это количество пространства, выделенное системой <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> компоновки, из-за явных и настроек или из-за его <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> настроек. Дополнительную информацию о макете можно [Layout](../advanced/layout.md) узнать в Фонде презентации Windows, см.  
  
 Свойство Stretch принимает одно из следующих значений.  
  
- <xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> Содержимое объекта не растягивается.  
  
- <xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается, чтобы заполнить его пространство макета.  Пропорции не сохраняются.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается как можно больше, чтобы заполнить его пространство макета, сохраняя при этом его исходное соотношение сторон.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается, чтобы полностью заполнить его пространство макета, сохраняя при этом исходное соотношение сторон.  
  
 Обратите внимание, <xref:System.Windows.Shapes.Shape> что при растяжении содержимого объекта контур <xref:System.Windows.Shapes.Shape> объекта покрашивается после растяжения.  
  
 В следующем примере <xref:System.Windows.Shapes.Polygon> используется для рисования очень небольшого треугольника от (0,0) до (0,1) до (1,1). Объект <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> установлены до 100, и его свойство растяжения установлен для заполнения. В результате содержимое <xref:System.Windows.Shapes.Polygon> объекта (треугольник) растягивается, чтобы заполнить большее пространство.  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
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
```

<a name="transforms"></a>
## <a name="transforming-shapes"></a>Преобразование фигур  
 Класс <xref:System.Windows.Media.Transform> предоставляет средства для преобразования форм в двумерной плоскости.  Различные типы преобразования<xref:System.Windows.Media.RotateTransform>включают всебяи (), масштаб (,<xref:System.Windows.Media.ScaleTransform>перекос (),<xref:System.Windows.Media.SkewTransform>и перевод ().<xref:System.Windows.Media.TranslateTransform>  
  
 Распространенным преобразованием фигуры является поворот.  Чтобы повернуть форму, <xref:System.Windows.Media.RotateTransform> создать и <xref:System.Windows.Media.RotateTransform.Angle%2A>указать ее . 45 <xref:System.Windows.Media.RotateTransform.Angle%2A> вращает элемент на 45 градусов по часовой стрелке; угол 90 вращает элемент на 90 градусов по часовой стрелке; и так далее. Установите <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> свойства и свойства, если вы хотите контролировать точку, о которой элемент вращается. Эти значения свойств выражаются в системе координат преобразуемого элемента. <xref:System.Windows.Media.RotateTransform.CenterX%2A>и <xref:System.Windows.Media.RotateTransform.CenterY%2A> имеют значения по умолчанию в ноль. Наконец, <xref:System.Windows.Media.RotateTransform> примените элемент. Если вы не хотите, чтобы преобразование повлияло <xref:System.Windows.UIElement.RenderTransform%2A> на макет, установите свойство формы.  
  
 В следующем примере <xref:System.Windows.Media.RotateTransform> используется для вращения формы на 45 градусов в левом верхнем углу формы (0,0).  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 В следующем примере другая фигура поворачивается на 45 градусов, но на этот раз — вокруг точки (25, 50).  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 На следующем рисунке показаны результаты двух преобразований.  
  
 ![Повороты на 45 градусов с разными центральными точками](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 В предыдущих примерах к каждому объекту фигуры применяется одно преобразование. Чтобы применить несколько преобразований к форме (или <xref:System.Windows.Media.TransformGroup>любому другому элементу uI), используйте .  
  
## <a name="see-also"></a>См. также раздел

- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Общие сведения о закраске сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md)
- [Общие сведения о геометрических фигурах](geometry-overview.md)
- [Пошаговое руководство. Создание первого классического приложения WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
