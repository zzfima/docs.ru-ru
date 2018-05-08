---
title: Общие сведения об анимация с использованием пути
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], paths
- path animations [WPF]
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
ms.openlocfilehash: 466e22a5b40ddb4f3674422ac7620832b44be51d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="path-animations-overview"></a>Общие сведения об анимация с использованием пути
<a name="introduction"></a> В этом разделе представлены общие сведения об анимациях по контуру, которые позволяют использовать геометрические контуры для формирования выходных значений. Анимации по контуру можно использовать для перемещения или вращения объектов по сложным траекториям.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы разобраться в этом разделе, необходимо ознакомиться с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] возможностями анимаций. Общие сведения о функциональных возможностях анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Так как вы используете <xref:System.Windows.Media.PathGeometry> объекта для определения анимации с использованием пути, также следует ознакомиться с <xref:System.Windows.Media.PathGeometry> и различные типы <xref:System.Windows.Media.PathSegment> объектов. Дополнительные сведения см. в разделе [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="what_is_a_path_animation"></a>   
## <a name="what-is-a-path-animation"></a>Что такое анимация по контуру?  
 Анимации пути — это тип <xref:System.Windows.Media.Animation.AnimationTimeline> , использующий <xref:System.Windows.Media.PathGeometry> качестве входных данных. Вместо задания для From, или по свойству (как и для From/To/By анимации) или с помощью ключевых кадров (как для полного кадра анимации), определяют геометрические путь и использовать его для задания `PathGeometry` свойства пути анимации. При выполнении анимации по контуру текущие данные о координатах X, Y и угле наклона используются для расчета выходных данных.  
  
 Метод анимации по контуру очень удобен при выполнении анимации объекта по сложной траектории. Один из способов перемещения объекта вдоль пути является использование <xref:System.Windows.Media.MatrixTransform> и <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> для преобразования объекта по сложному пути. Этот метод продемонстрирован в следующем примере с помощью <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> анимируемый объект <xref:System.Windows.Media.MatrixTransform.Matrix%2A> свойство <xref:System.Windows.Media.MatrixTransform>. <xref:System.Windows.Media.MatrixTransform> Применяется к кнопке и приводит к перемещению в пути кривой. Поскольку <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> свойству `true`, прямоугольник поворачивается вдоль касательной к пути.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Дополнительные сведения о синтаксисе пути, который используется в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] пример, в разделе [синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Обзор. Полный пример см. в разделе [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Примените анимации с использованием пути к свойству с помощью <xref:System.Windows.Media.Animation.Storyboard> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и кода, или с помощью <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метода в коде. Можно также использовать анимацию для создания <xref:System.Windows.Media.Animation.AnimationClock> и применить его к одному или нескольким свойствам. Дополнительные сведения о различных способах применения анимации см. в разделе [Общие сведения о методах анимации свойства](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="path-animation-types"></a>Типы анимаций по контуру  
 Так как при анимации создаются значения свойств, существуют различные типы анимаций для различных типов свойств. Для анимации свойства, которое принимает <xref:System.Double> (такие как <xref:System.Windows.Media.TranslateTransform.X%2A> свойство <xref:System.Windows.Media.TranslateTransform>), используйте анимацию, создающую <xref:System.Double> значения. Для анимации свойства, которое принимает <xref:System.Windows.Point>, используйте анимацию, создающую <xref:System.Windows.Point> значения и т. д.  
  
 Классы анимации пути принадлежат к <xref:System.Windows.Media.Animation> пространства имен и используется следующее соглашение об именовании:  
  
 *\<Тип>* `AnimationUsingPath`  
  
 Где *\<Type>* — тип значения, которое выполняет анимацию класса.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет следующие классы анимации по контуру.  
  
|Тип свойства|Соответствующий класс анимации по контуру|Пример|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Анимация объекта вдоль контура (двойная анимация)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Анимация объекта вдоль контура (матричная анимация)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Анимация объекта вдоль контура (точечная анимация)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 Объект <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> приводит к возникновению ошибки <xref:System.Windows.Media.Matrix> значения из его <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>. При использовании с <xref:System.Windows.Media.MatrixTransform>, <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> можно переместить объект вдоль пути. Если задать <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> свойство <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> для `true`, оно также поворачивает объект вдоль кривых пути.  
  
 Объект <xref:System.Windows.Media.Animation.PointAnimationUsingPath> приводит к возникновению ошибки <xref:System.Windows.Point> значения из x-y координаты и его <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>. С помощью <xref:System.Windows.Media.Animation.PointAnimationUsingPath> для анимации свойства, которое принимает <xref:System.Windows.Point> значения, можно переместить объект вдоль пути. Объект <xref:System.Windows.Media.Animation.PointAnimationUsingPath> нельзя вращать объекты.  
  
 Объект <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> приводит к возникновению ошибки <xref:System.Double> значения из его <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>. Установив <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> свойства, можно указать ли <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> использует координат x, координату по оси y или угол пути в качестве результата. Можно использовать <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Чтобы повернуть объект или переместить его вдоль оси x и оси y.  
  
<a name="pathanimationinput"></a>   
## <a name="path-animation-input"></a>Входные данные для анимации по контуру  
 Каждый класс анимации пути предоставляет <xref:System.Windows.Media.PathGeometry> свойство для указания входных данных. Использует путь анимация <xref:System.Windows.Media.PathGeometry> для создания выходных значений. <xref:System.Windows.Media.PathGeometry> Позволяет описать нескольких сложных фигур, состоящих из дуг, кривых и линий.  
  
 В основе <xref:System.Windows.Media.PathGeometry> — это совокупность <xref:System.Windows.Media.PathFigure> объектов; эти объекты названы таким образом, так как каждая фигура описывает дискретную форму в <xref:System.Windows.Media.PathGeometry>. Каждый <xref:System.Windows.Media.PathFigure> состоит из одного или нескольких <xref:System.Windows.Media.PathSegment> объектов, каждый из которых описывает сегмент фигуры.  
  
 Существует несколько типов сегментов.  
  
|Тип сегмента|Описание|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|Создает эллиптическую дугу между двумя точками.|  
|<xref:System.Windows.Media.BezierSegment>|Создает кривую Безье третьего порядка между двумя точками.|  
|<xref:System.Windows.Media.LineSegment>|Создает линию между двумя точками.|  
|<xref:System.Windows.Media.PolyBezierSegment>|Создает набор кривых Безье третьего порядка.|  
|<xref:System.Windows.Media.PolyLineSegment>|Создает набор линий.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Создает набор кривых Безье второго порядка.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Создает кривую Безье второго порядка.|  
  
 Сегменты в <xref:System.Windows.Media.PathFigure> объединяются в одну геометрическую форму, которая использует конечную точку сегмента совпадает с начальной точкой следующего сегмента. <xref:System.Windows.Media.PathFigure.StartPoint%2A> Свойство <xref:System.Windows.Media.PathFigure> указывает точку, из которого берется первый сегмент. Каждый последующий сегмент начинается в конечной точке предыдущего сегмента. Например, вертикальная линия из `10,50` для `10,150` можно определить, задав <xref:System.Windows.Media.PathFigure.StartPoint%2A> свойства `10,50` и создание <xref:System.Windows.Media.LineSegment> с <xref:System.Windows.Media.LineSegment.Point%2A> свойства `10,150`.  
  
 Дополнительные сведения о <xref:System.Windows.Media.PathGeometry> объектов, в разделе [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], также можно использовать специальный сокращенный синтаксис для задания <xref:System.Windows.Media.PathGeometry.Figures%2A> свойство <xref:System.Windows.Media.PathGeometry>. Дополнительные сведения см. в разделе [синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Обзор.  
  
 Дополнительные сведения о синтаксисе пути, который используется в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] пример, в разделе [синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Обзор.  
  
## <a name="see-also"></a>См. также  
 [Пример анимации вдоль пути](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)  
 [Практические руководства, посвященные анимации по контуру](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
