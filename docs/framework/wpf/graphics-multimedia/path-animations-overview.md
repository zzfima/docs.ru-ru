---
title: "Общие сведения об анимация с использованием пути | Microsoft Docs"
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
  - "анимации пути"
  - "анимации по путям"
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Общие сведения об анимация с использованием пути
<a name="introduction"></a>В этом разделе представлены анимации по путям, которые позволяют использовать геометрический путь для формирования выходных значений. Анимация с использованием пути можно использовать для перемещения и вращения объектов по сложному пути.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы разобраться в этом разделе, вы должны быть знакомы с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] возможностями анимаций. Общие сведения о функциональных возможностях анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Поскольку используется <xref:System.Windows.Media.PathGeometry> для определения анимации с использованием пути, также должны быть знакомы с <xref:System.Windows.Media.PathGeometry> и различные типы <xref:System.Windows.Media.PathSegment> объектов. Дополнительные сведения см. в разделе [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="what_is_a_path_animation"></a>   
## <a name="what-is-a-path-animation"></a>Что такое анимации пути  
 Анимации с использованием пути представляет собой тип <xref:System.Windows.Media.Animation.AnimationTimeline> , использующий <xref:System.Windows.Media.PathGeometry> качестве входных данных. Вместо параметра From, до или по свойству (как и для From/To/By анимации) или с помощью ключевых кадров (как для анимации по полным кадрам), определение геометрического пути и использовать его для задания `PathGeometry` свойства анимации пути. В ходе анимации пути считывает x, y и угла из пути и использует эту информацию для создания выходных.  
  
 Анимация с использованием пути очень полезны для анимации объекта по сложному пути. Один из способов перемещения объекта вдоль пути является использование <xref:System.Windows.Media.MatrixTransform> и <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> для преобразования объекта по сложному пути. В следующем примере демонстрируется этот метод с помощью <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> анимируемого объекта <xref:System.Windows.Media.MatrixTransform.Matrix%2A> свойство <xref:System.Windows.Media.MatrixTransform>. <xref:System.Windows.Media.MatrixTransform> применяется к кнопке и приводит к перемещению вдоль изогнутого пути. Поскольку <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> свойству `true`, прямоугольник поворачивается по касательной к пути.  
  
 [!code-xml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Дополнительные сведения о синтаксисе пути, который используется в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] пример, в разделе [синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Обзор. Полный пример см. [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Можно применить анимацию к свойству с помощью <xref:System.Windows.Media.Animation.Storyboard> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и кода, или с помощью <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метода в коде. Анимацию можно также использовать для создания <xref:System.Windows.Media.Animation.AnimationClock> и применить его к одному или нескольким свойствам. Дополнительные сведения о различных способах применения анимации см. в разделе [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="path-animation-types"></a>Типы анимации пути  
 Поскольку анимация создает значения свойств, существуют различные типы анимации для различных типов свойств. Для анимации свойства, которое принимает <xref:System.Double> (таких как <xref:System.Windows.Media.TranslateTransform.X%2A> свойство <xref:System.Windows.Media.TranslateTransform>), используйте анимацию, создающую <xref:System.Double> значения. Для анимации свойства, которое принимает <xref:System.Windows.Point>, используйте анимацию, создающую <xref:System.Windows.Point> значения и т. д.  
  
 Классы анимации пути принадлежат к <xref:System.Windows.Media.Animation> пространства имен и используется следующее соглашение об именовании:  
  
 *<>\>*`AnimationUsingPath`  
  
 Где * <> \> * является тип значения, которое класс анимирует.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет классы анимации по следующему пути.  
  
|Тип свойства|Соответствующий класс анимации пути|Пример|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Анимация объекта вдоль пути (двойная анимация)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Анимация объекта вдоль пути (матричная анимация)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Анимация объекта вдоль пути (точечная анимация)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 Объект <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> создает <xref:System.Windows.Media.Matrix> значения из его <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>. При использовании с <xref:System.Windows.Media.MatrixTransform>, <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> можно перемещать объект вдоль пути. Если задать <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> свойство <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> в `true`, оно также поворачивает объект вдоль кривых пути.  
  
 Объект <xref:System.Windows.Media.Animation.PointAnimationUsingPath> создает <xref:System.Windows.Point> значения из x-y координаты и его <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>. С помощью <xref:System.Windows.Media.Animation.PointAnimationUsingPath> для анимации свойства, которое принимает <xref:System.Windows.Point> значения, можно перемещать объект вдоль пути. Объект <xref:System.Windows.Media.Animation.PointAnimationUsingPath> не может поворачивать объекты.  
  
 Объект <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> создает <xref:System.Double> значения из его <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>. Установив <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> свойства, можно указать ли <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> использует координаты x, y координату или угол пути в качестве результата. Можно использовать <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Чтобы повернуть объект или переместить его вдоль оси x и оси y.  
  
<a name="pathanimationinput"></a>   
## <a name="path-animation-input"></a>Входные данные анимации пути  
 Каждый класс анимации пути предоставляет <xref:System.Windows.Media.PathGeometry> свойство для указания его входных данных. Анимации пути использует <xref:System.Windows.Media.PathGeometry> для создания выходных значений. <xref:System.Windows.Media.PathGeometry> позволяет описать нескольких сложных фигур, состоящих из дуг, кривых и линий.  
  
 В сердце <xref:System.Windows.Media.PathGeometry> — это коллекция <xref:System.Windows.Media.PathFigure> объектов; эти объекты названы таким образом, так как каждая фигура описывает дискретную форму в <xref:System.Windows.Media.PathGeometry>. Каждый <xref:System.Windows.Media.PathFigure> состоит из одного или нескольких <xref:System.Windows.Media.PathSegment> объектов, каждый из которых описывает сегмент фигуры.  
  
 Существует много типов сегментов.  
  
|Тип сегмента|Описание|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|Создание эллиптической дуги между двумя точками.|  
|<xref:System.Windows.Media.BezierSegment>|Создание кривой Безье третьего порядка между двумя точками.|  
|<xref:System.Windows.Media.LineSegment>|Создает линию между двумя точками.|  
|<xref:System.Windows.Media.PolyBezierSegment>|Создает набор кривых Безье третьего порядка.|  
|<xref:System.Windows.Media.PolyLineSegment>|Создает набор строк.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Создает набор кривых Безье второго порядка.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Создание кривой Безье второго порядка.|  
  
 Сегменты в <xref:System.Windows.Media.PathFigure> объединяются в одну геометрическую форму, которая использует конечную точку сегмента совпадает с начальной точкой следующего сегмента. <xref:System.Windows.Media.PathFigure.StartPoint%2A> свойство <xref:System.Windows.Media.PathFigure> указывает точку, из которой рисуется первый сегмент. Каждый последующий сегмент начинается в конечной точке предыдущего сегмента. Например, вертикальная линия из `10,50` для `10,150` может быть задан путем установки <xref:System.Windows.Media.PathFigure.StartPoint%2A> свойства `10,50` и создания <xref:System.Windows.Media.LineSegment> с <xref:System.Windows.Media.LineSegment.Point%2A> свойства `10,150`.  
  
 Дополнительные сведения о <xref:System.Windows.Media.PathGeometry> объектов, в разделе [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], также можно использовать специальный сокращенный синтаксис для задания <xref:System.Windows.Media.PathGeometry.Figures%2A> свойство <xref:System.Windows.Media.PathGeometry>. Дополнительные сведения см. в разделе [синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Обзор.  
  
 Дополнительные сведения о синтаксисе пути, который используется в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] пример, в разделе [синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Обзор.  
  
## <a name="see-also"></a>См. также  
 [Пример анимации пути перемещения](http://go.microsoft.com/fwlink/?LinkID=160028)   
 [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)   
 [Разделы руководства, посвященные анимации пути](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)   
 [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)