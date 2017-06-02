---
title: "Синтаксис разметки пути | Microsoft Docs"
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
  - "класс PathGeometry"
  - "использование атрибутов в XAML"
  - "Использование атрибута XAML"
  - "классы, PathGeometry"
  - "графики, класс PathGeometry"
  - "Использование элемента объекта XAML"
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Синтаксис разметки пути
Пути рассматриваются в [фигур и базовых средств рисования в общие сведения о WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md) и [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md), однако в этом разделе подробно описывается мощное и сложное мини-языке, можно использовать для указания более объекты PathGeometry [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 В этом разделе содержатся следующие подразделы.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы разобраться в этом разделе, должны быть знакомы основные возможности <xref:System.Windows.Media.Geometry> объектов. Дополнительные сведения см. в разделе [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="abouthisdocument"></a>   
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>StreamGeometry и PathFigureCollection мини языки  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет два класса, предоставляющие мини языки для описания геометрических путей: <xref:System.Windows.Media.StreamGeometry> и <xref:System.Windows.Media.PathFigureCollection>.  
  
-   Используется <xref:System.Windows.Media.StreamGeometry> мини-языке при задании свойства типа <xref:System.Windows.Media.Geometry>, такие как <xref:System.Windows.UIElement.Clip%2A> свойство <xref:System.Windows.UIElement> или <xref:System.Windows.Shapes.Path.Data%2A> свойство <xref:System.Windows.Shapes.Path> элемент. В следующем примере используется синтаксис атрибутов для создания <xref:System.Windows.Media.StreamGeometry>.  
  
     [!code-xml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
-   Использовать <xref:System.Windows.Media.PathFigureCollection> мини-языке при задании <xref:System.Windows.Media.PathGeometry.Figures%2A> свойство <xref:System.Windows.Media.PathGeometry>. В следующем примере используется синтаксис атрибутов для создания <xref:System.Windows.Media.PathFigureCollection> для <xref:System.Windows.Media.PathGeometry>.  
  
     [!code-xml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Как видно из предыдущих примеров мини языки очень похожи. Всегда можно использовать <xref:System.Windows.Media.PathGeometry> в любой ситуации, где можно использовать <xref:System.Windows.Media.StreamGeometry>; поэтому какой из них следует использовать? Используйте <xref:System.Windows.Media.StreamGeometry> при не требуется изменять путь после его создания; используйте <xref:System.Windows.Media.PathGeometry> Если необходимо изменить путь.  
  
 Дополнительные сведения о различиях между <xref:System.Windows.Media.PathGeometry> и <xref:System.Windows.Media.StreamGeometry> объектов, в разделе [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
### <a name="a-note-about-white-space"></a>Примечание.  
 Для краткости в разделах синтаксиса отображается один пробел, но несколько пробелов также являются допустимыми, везде, где отображается один пробел.  
  
 Два числа не обязательно должны быть разделены запятыми или пробелами, но это может быть выполнено, только если результирующая строка является однозначным. Например `2..3` фактически представляет два числа: «2». И «.&3;». Аналогичным образом `2-3` — «2» и «-3». Пробелы не требуются до или после команды, либо.  
  
### <a name="syntax"></a>Синтаксис  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Использования синтаксиса для атрибута <xref:System.Windows.Media.StreamGeometry> состоит из необязательного <xref:System.Windows.Media.FillRule> значение и один или несколько следующих описаний.  
  
|Использование атрибута StreamGeometry XAML|  
|-----------------------------------------|  
|`<`*object* *property* `="`[                                         `fillRule`]                                          `figureDescription`[                                         `figureDescription`]*`" ... />`|  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Использования синтаксиса для атрибута <xref:System.Windows.Media.PathFigureCollection> состоит из описания на рисунке один или несколько.  
  
|Использование атрибута PathFigureCollection XAML|  
|-----------------------------------------------|  
|`<`*object* *property* `="` `figureDescription`[                                         `figureDescription`]*`" ... />`|  
  
|Термин|Описание|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=fullName><br /><br /> Указывает, является ли <xref:System.Windows.Media.StreamGeometry> использует <xref:System.Windows.Media.FillRule> или <xref:System.Windows.Media.FillRule><xref:System.Windows.Media.PathGeometry.FillRule%2A>.<br /><br /> -   `F0`Указывает <xref:System.Windows.Media.FillRule> правило заливки.<br />-   `F1`Указывает <xref:System.Windows.Media.FillRule> правило заливки.<br /><br /> Если опустить эту команду, во вложенном пути используется поведение по умолчанию, который является <xref:System.Windows.Media.FillRule>. При указании этой команды, сначала его необходимо размещать.|  
|*figureDescription*|Фигура, состоящая из команды перемещения, команд рисования и необязательной команды закрытия.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Команда перемещения, которая указывает начальную точку фигуры. В разделе [команды переместить](#themovecommand) раздел.|  
|*drawCommands*|Один или несколько команд рисования, описывающих содержимое фигуры. В разделе [команд рисования](#drawcommands) раздел.|  
|*closeCommand*|Необязательная команда закрытия, замыкает фигуру. В разделе [команда закрытия](#closecommand) раздел.|  
  
<a name="themovecommand"></a>   
## <a name="move-command"></a>Команда «Переместить»  
 Задает начальную точку новой фигуры.  
  
|Синтаксис|  
|------------|  
|`M`*начальной точки*<br /><br /> -или-<br /><br /> `m`*начальной точки*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*начальной точки*|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Начальная точка новой фигуры.|  
  
 Верхнерегистровая `M` указывает, что `startPoint` абсолютным значением; строчная буква `m` указывает, что `startPoint` содержит смещение относительно предыдущей точки или (0,0), если она не существует. Если после команды перемещения перечислено несколько точек, линия на эти точки на то, что вы указали командной строки.  
  
<a name="drawcommands"></a>   
## <a name="draw-commands"></a>Команды рисования  
 Команда рисования может состоять из нескольких команд формы. Доступны следующие команды формы: линия, горизонтальная линия, вертикальной линии, кривой Безье третьего порядка, кривая Безье второго порядка, гладкой кривой Безье третьего порядка, гладкой кривой Безье второго порядка и эллиптической дуги.  
  
 Каждая команда вводится с помощью прописной или строчной буквы: прописные буквы определяют абсолютные значения и строчные буквы обозначают относительные значения: контрольные точки для этого сегмента относительны конечная точка предыдущего примера. При последовательном вводе нескольких команд одного типа, можно опустить повторяющуюся команду запись; например `L 100,200 300,400` эквивалентно `L 100,200 L 300,400`. В следующей таблице описаны **перемещение** и **нарисовать** команды.  
  
### <a name="line-command"></a>Средства командной строки  
 Создание прямой линии между текущей точкой и заданной конечной точкой.                           `l 20 30`и `L 20,30` приведены примеры допустимых **строки** команды.  
  
|Синтаксис|  
|------------|  
|`L`*конечной точки*<br /><br /> -или-<br /><br /> `l`*конечной точки*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*Конечная точка*|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Конечная точка строки.|  
  
### <a name="horizontal-line-command"></a>Горизонтальная линия  
 Создание горизонтальной линии между текущей точкой и указанной оси x.                          `H 90`приведен пример допустимой команды горизонтальной линии.  
  
|Синтаксис|  
|------------|  
|`H`  *x*<br /><br /> -или-<br /><br /> `h`  *x*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*x*|<xref:System.Double?displayProperty=fullName><br /><br /> Координата конечной точки линии по оси x.|  
  
### <a name="vertical-line-command"></a>Вертикальная линия  
 Создание вертикальной линии между текущей точкой и указанной координату по оси y.                          `v 90`приведен пример допустимой команды вертикальной линии.  
  
|Синтаксис|  
|------------|  
|`V`  *y*<br /><br /> -или-<br /><br /> `v`  *y*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*y*|<xref:System.Double?displayProperty=fullName><br /><br /> Координата y конечной точки линии.|  
  
### <a name="cubic-bezier-curve-command"></a>Команда кривой Безье третьего порядка  
 Создание кривой Безье третьего порядка между текущей точкой и заданной конечной точкой с использованием двух заданных контрольных точек ( `controlPoint`1 и `controlPoint`2).                          `C 100,200 200,400 300,200`приведен пример команды допустимым кривой.  
  
|Синтаксис|  
|------------|  
|`C` `controlPoint`1`controlPoint`2`endPoint`<br /><br /> -или-<br /><br /> `c` `controlPoint`1`controlPoint`2`endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Первая контрольная точка кривой, которая определяет начальную касательную к кривой.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Вторая контрольная точка кривой, которая определяет конечную касательную кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Точка для рисования кривой.|  
  
### <a name="quadratic-bezier-curve-command"></a>Команда кривой Безье второго порядка  
 Создание кривой Безье второго порядка между текущей точкой и заданной конечной точкой с использованием заданной контрольной точки ( `controlPoint`).                          `q 100,200 300,200`приведен пример допустимой команды кривой Безье второго порядка.  
  
|Синтаксис|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> -или-<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Контрольная точка кривой, которая определяет начальную и конечную касательных кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Точка для рисования кривой.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Smooth кривая Безье третьего порядка  
 Создание кривой Безье третьего порядка между текущей точкой и заданной конечной точкой. Предполагается, что первой контрольной точки отражение второй контрольной точки предыдущей команды относительно текущей точки. Если нет предыдущей команды или если предыдущая команда не кривой Безье третьего или гладкой кривой Безье третьего, предположим, что первой контрольной точки принимается текущая точка. Вторая контрольная точка, контрольную точку для конечной точки кривой, задается `controlPoint`2. Например `S 100,200 200,300` является допустимым команда гладкой кривой Безье третьего порядка.  
  
|Синтаксис|  
|------------|  
|`S` `controlPoint`2`endPoint`<br /><br /> -или-<br /><br /> `s` `controlPoint`2`endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Контрольная точка кривой, которая определяет конечную касательную кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Точка для рисования кривой.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>Smooth кривая Безье второго порядка  
 Создание кривой Безье второго порядка между текущей точкой и заданной конечной точкой. Контрольной точки принимается отражение контрольной точки предыдущей команды относительно текущей точки. Если нет предыдущей команды или если предыдущая команда не была квадратичной кривой Безье или smooth команды кривой Безье второго порядка, контрольной точки принимается текущая точка.  
  
|Синтаксис|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> -или-<br /><br /> `t` `controlPoint` `endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Контрольная точка кривой, которая определяет начальную и касательной кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Точка для рисования кривой.|  
  
### <a name="elliptical-arc-command"></a>Команда эллиптической дуги  
 Создание эллиптической дуги между текущей точкой и заданной конечной точкой.  
  
|Синтаксис|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> -или-<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=fullName><br /><br /> Радиусы арки X и Y.|  
|`rotationAngle`|<xref:System.Double?displayProperty=fullName><br /><br /> Поворот эллипса в градусах.|  
|`isLargeArcFlag`|Значение 1, если угол дуги должен быть 180 градусов или выше. в противном случае — значение 0.|  
|`sweepDirectionFlag`|Значение 1, если дуги в направлении положительный угол; в противном случае — значение 0.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Точка, в которую рисуется дуга.|  
  
<a name="closecommand"></a>   
## <a name="the-close-command"></a>Команда «Закрыть»  
 Заканчивает текущую фигуру и создает линию, соединяющую текущей точки до начальной точки фигуры. Эта команда создает строку соединения (угол) между последнего сегмента и первый сегмент фигуры.  
  
|Синтаксис|  
|------------|  
|`Z`<br /><br /> -или-<br /><br /> `z`|  
  
<a name="pointsyntax"></a>   
## <a name="point-syntax"></a>Синтаксис точки  
 Описывает x и y координаты точки.  
  
|Синтаксис|  
|------------|  
|`x` `,` `y`<br /><br /> -или-<br /><br /> `x` `y`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=fullName><br /><br /> Координата x точки.|  
|`y`|<xref:System.Double?displayProperty=fullName><br /><br /> Координата y точки.|  
  
<a name="specialvalues"></a>   
## <a name="special-values"></a>Специальные значения  
 Вместо стандартного числового значения можно также использовать следующие специальные значения. Эти значения задаются с учетом регистра.  
  
 Бесконечность  
 Представляет <xref:System.Double.PositiveInfinity?displayProperty=fullName>.  
  
 -бесконечность  
 Представляет <xref:System.Double.NegativeInfinity?displayProperty=fullName>.  
  
 NaN  
 Представляет <xref:System.Double.NaN?displayProperty=fullName>.  
  
 Можно также использовать экспоненциальное представление чисел. Например `+1.e17` является допустимым значением.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.StreamGeometry>   
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Media.PathFigureCollection>   
 [Фигур и базовых средств рисования в общие сведения о WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Общие сведения о геометрии](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)