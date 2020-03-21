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
ms.openlocfilehash: 07628d26c8222c7c01f58826a36a15e13dc31ff4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181867"
---
# <a name="path-animations-overview"></a>Общие сведения об анимация с использованием пути
<a name="introduction"></a> В этом разделе представлены общие сведения об анимациях по контуру, которые позволяют использовать геометрические контуры для формирования выходных значений. Анимации по контуру можно использовать для перемещения или вращения объектов по сложным траекториям.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы понять эту тему, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вы должны быть знакомы с функциями анимации. Для введения в функции анимации, [см.](animation-overview.md)  
  
 Поскольку объект <xref:System.Windows.Media.PathGeometry> используется для определения анимации пути, <xref:System.Windows.Media.PathGeometry> вы также должны <xref:System.Windows.Media.PathSegment> быть знакомы с различными типами объектов. Для получения дополнительной [информации](geometry-overview.md)смотрите обзор геометрии .  
  
<a name="what_is_a_path_animation"></a>
## <a name="what-is-a-path-animation"></a>Что такое анимация по контуру?  
 Анимация пути — <xref:System.Windows.Media.Animation.AnimationTimeline> это тип, который использует в <xref:System.Windows.Media.PathGeometry> качестве ввода. Вместо установки From, To или By property (как это делается для анимации From/To/By) или использования ключевых кадров (как вы используете `PathGeometry` для анимации с ключевыми кадрами), вы определяете геометрический путь и используете его для установки свойства анимации пути. При выполнении анимации по контуру текущие данные о координатах X, Y и угле наклона используются для расчета выходных данных.  
  
 Метод анимации по контуру очень удобен при выполнении анимации объекта по сложной траектории. Один из способов перемещения объекта по <xref:System.Windows.Media.MatrixTransform> пути <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> заключается в использовании и преобразовании объекта по сложному пути. Следующий пример демонстрирует эту технику, используя <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> объект <xref:System.Windows.Media.MatrixTransform.Matrix%2A> для анимирования свойства <xref:System.Windows.Media.MatrixTransform>. Применяется <xref:System.Windows.Media.MatrixTransform> к кнопке и заставляет ее двигаться по изогнутому пути. Поскольку <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> свойство `true`настроено на то, что прямоугольник вращается по касательной пути.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Для получения дополнительной информации о синтаксисе пути, который используется в примере, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] см. [Path Markup Syntax](path-markup-syntax.md) Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)  
  
 Анимация пути к свойству можно <xref:System.Windows.Media.Animation.Storyboard> применить [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] с помощью кода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> или с помощью метода в коде. Вы также можете использовать анимацию <xref:System.Windows.Media.Animation.AnimationClock> пути для создания и применения ее к одному или несколько свойствам. Для получения дополнительной информации о различных методах применения анимации, [см.](property-animation-techniques-overview.md)  
  
<a name="animation_types"></a>
## <a name="path-animation-types"></a>Типы анимаций по контуру  
 Так как при анимации создаются значения свойств, существуют различные типы анимаций для различных типов свойств. Чтобы оживить свойство, которое принимает <xref:System.Double> <xref:System.Windows.Media.TranslateTransform.X%2A> (например, свойство), <xref:System.Windows.Media.TranslateTransform>вы <xref:System.Double> используете анимацию, которая производит значения. Чтобы оживить <xref:System.Windows.Point>свойство, которое занимает, вы <xref:System.Windows.Point> используете анимацию, которая производит значения, и так далее.  
  
 Классы анимации <xref:System.Windows.Media.Animation> пути относятся к пространству имен и используют следующую конвенцию имен:  
  
 * \<Тип>*`AnimationUsingPath`  
  
 Где * \<тип>* — это тип значения, который оживляет класс.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет следующие классы анимации по контуру.  
  
|Тип свойства|Соответствующий класс анимации по контуру|Пример|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Анимация объекта вдоль контура (двойная анимация)](how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Анимация объекта вдоль контура (матричная анимация)](how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Анимация объекта вдоль контура (точечная анимация)](how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 A <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> генерирует <xref:System.Windows.Media.Matrix> значения из <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>его . При использовании <xref:System.Windows.Media.MatrixTransform>с, <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> может переместить объект по пути. Если вы <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> установите <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> свойство к, `true`он также вращает объект вдоль кривых пути.  
  
 A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> генерирует <xref:System.Windows.Point> значения из x- и y-координаций его <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>. Используя <xref:System.Windows.Media.Animation.PointAnimationUsingPath> для анимировать свойство, <xref:System.Windows.Point> которое принимает значения, можно переместить объект по пути. A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> не может вращать объекты.  
  
 A <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> генерирует <xref:System.Double> значения из <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>его . Установив свойство, <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> можно указать, <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> использует ли X-координат, y-координирует или угол пути в качестве его вывода. Можно использовать <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> для поворота объекта или перемещения его вдоль оси x или y-оси.  
  
<a name="pathanimationinput"></a>
## <a name="path-animation-input"></a>Входные данные для анимации по контуру  
 Каждый класс анимации пути предоставляет свойство <xref:System.Windows.Media.PathGeometry> для определения его ввода. Анимация пути <xref:System.Windows.Media.PathGeometry> использует значение своих выходных значений. Класс <xref:System.Windows.Media.PathGeometry> позволяет описать несколько сложных фигур, которые состоят из дуг, кривых и линий.  
  
 В основе <xref:System.Windows.Media.PathGeometry> коллекции объектов; <xref:System.Windows.Media.PathFigure> эти объекты названы так потому, что <xref:System.Windows.Media.PathGeometry>каждая фигура описывает дискретную форму в . Каждый из <xref:System.Windows.Media.PathFigure> них <xref:System.Windows.Media.PathSegment> состоит из одного или нескольких объектов, каждый из которых описывает сегмент фигуры.  
  
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
  
 Сегменты в <xref:System.Windows.Media.PathFigure> a объединены в единую геометрическая форму, которая использует конечную точку сегмента в качестве отправной точки следующего сегмента. Свойство <xref:System.Windows.Media.PathFigure.StartPoint%2A> <xref:System.Windows.Media.PathFigure> определяет точку, из которой обращается первый сегмент. Каждый последующий сегмент начинается в конечной точке предыдущего сегмента. Например, вертикальная `10,50` `10,150` линия от к <xref:System.Windows.Media.PathFigure.StartPoint%2A> может `10,50` быть определена путем установки свойства и создания <xref:System.Windows.Media.LineSegment> с параметром <xref:System.Windows.Media.LineSegment.Point%2A> `10,150`свойства.  
  
 Для получения <xref:System.Windows.Media.PathGeometry> дополнительной [информации](geometry-overview.md)об объектах см.  
  
 В, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]вы также можете использовать специальный сокращенный <xref:System.Windows.Media.PathGeometry.Figures%2A> синтаксис, чтобы установить свойство <xref:System.Windows.Media.PathGeometry>. Для получения дополнительной информации смотрите обзор [Syntax Path Markup.](path-markup-syntax.md)  
  
 Для получения дополнительной информации о синтаксисе пути, который используется в примере, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] см. [Path Markup Syntax](path-markup-syntax.md)  
  
## <a name="see-also"></a>См. также раздел

- [Пример анимации по контуру](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Синтаксис разметки пути](path-markup-syntax.md)
- [Практические руководства, посвященные анимации по контуру](path-animation-how-to-topics.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md)
