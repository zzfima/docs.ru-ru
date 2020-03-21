---
title: Синтаксис разметки пути
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: adcedcea6c8d6d988021cbbccf87bd25a042fd16
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181850"
---
# <a name="path-markup-syntax"></a>Синтаксис разметки пути
Пути обсуждаются в [формах и базовом рисовании в обзоре WPF](shapes-and-basic-drawing-in-wpf-overview.md) и [обзоре геометрии,](geometry-overview.md)однако эта тема подробно описывает мощный и сложный мини-язык, который можно использовать для более компактного использования [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]геометрии путей.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы понять эту тему, вы должны <xref:System.Windows.Media.Geometry> быть знакомы с основными особенностями объектов. Для получения дополнительной [информации](geometry-overview.md)смотрите обзор геометрии .  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>Мини-языки StreamGeometry и PathFigureCollection  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет два класса, которые предоставляют мини-языки <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.PathFigureCollection>для описания геометрических путей: и .  
  
- При настройке свойства <xref:System.Windows.Media.StreamGeometry> типа <xref:System.Windows.Media.Geometry>используется мини-язык, <xref:System.Windows.UIElement.Clip%2A> например <xref:System.Windows.UIElement> свойство <xref:System.Windows.Shapes.Path.Data%2A> <xref:System.Windows.Shapes.Path> элемента или свойства элемента. В следующем примере используется синтаксис атрибутов для создания <xref:System.Windows.Media.StreamGeometry>.  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- Вы используете <xref:System.Windows.Media.PathFigureCollection> мини-язык <xref:System.Windows.Media.PathGeometry.Figures%2A> при настройке свойства <xref:System.Windows.Media.PathGeometry>. В следующем примере используется синтаксис <xref:System.Windows.Media.PathGeometry>атрибута для создания <xref:System.Windows.Media.PathFigureCollection> для .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Как видно из предыдущих примеров мини-языки очень похожи. Это всегда можно использовать <xref:System.Windows.Media.PathGeometry> в любой ситуации, <xref:System.Windows.Media.StreamGeometry>когда вы могли бы использовать ; так что один из них вы должны использовать? Используйте, <xref:System.Windows.Media.StreamGeometry> когда вам не нужно изменять путь после его создания; использовать, <xref:System.Windows.Media.PathGeometry> если вам нужно изменить путь.  
  
 Для получения дополнительной информации о различиях между <xref:System.Windows.Media.PathGeometry> объектами и <xref:System.Windows.Media.StreamGeometry> [объектами](geometry-overview.md)см.  
  
### <a name="a-note-about-white-space"></a>Примечание о пробелах  
 В следующих разделах для краткости в примерах синтаксиса показан один пробел, но допускается использовать по нескольку пробелов везде, где указан один пробел.  
  
 Два числа на самом деле не должны быть разделены запятой или белым пространством, но это может быть сделано только тогда, когда результирующая строка однозначна. Например, `2..3` на самом деле два числа: "2". и 3. Аналогичным `2-3` образом, "2" и "-3". Пробелы до и после команд ставить необязательно.  
  
### <a name="syntax"></a>Синтаксис  
 Синтаксис [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] использования атрибута для <xref:System.Windows.Media.StreamGeometry> a <xref:System.Windows.Media.FillRule> состоит из факультативного значения и одного или нескольких описаний фигуры.  
  
|Использование атрибута XAML на StreamGeometry|  
|-----------------------------------------|  
|`<``figureDescription` *объектное* `="` `fillRule` *object* `figureDescription`свойство`" ... />`|  
  
 Синтаксис [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] использования атрибута для a <xref:System.Windows.Media.PathFigureCollection> состоит из одного или нескольких описаний фигуры.  
  
|Использование атрибута XAML на PathFigureCollection|  
|-----------------------------------------------|  
|`<``figureDescription` *объектное свойство* `="` `figureDescription` *object*`" ... />`|  
  
|Термин|Описание|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> Определяет, <xref:System.Windows.Media.StreamGeometry> использует <xref:System.Windows.Media.FillRule.EvenOdd> <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A>ли или .<br /><br /> -   `F0`определяет правило <xref:System.Windows.Media.FillRule.EvenOdd> заполнения.<br />-   `F1`определяет правило <xref:System.Windows.Media.FillRule.Nonzero> заполнения.<br /><br /> Если вы опустевите эту команду, подпуть <xref:System.Windows.Media.FillRule.EvenOdd>использует поведение по умолчанию, которое находится под этим вопросом. Если эта команда используется, ее необходимо размещать вначале.|  
|*figureDescription*|Фигура, состоящая из команды перемещения, команд рисования и необязательной команды закрытия.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Команда перемещения, которая указывает начальную точку фигуры. Смотрите раздел [«Команда перемещения».](#themovecommand)|  
|*drawCommands*|Одна или несколько команд рисования, описывающих содержимое фигуры. Смотрите раздел [Команды рисования.](#drawcommands)|  
|*closeCommand*|Необязательная команда, которая закрывает фигуру. Смотрите раздел [«Близкое командование».](#closecommand)|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a>Команда перемещения  
 Задает начальную точку новой фигуры.  
  
|Синтаксис|  
|------------|  
|`M`*startPoint*<br /><br /> — или —<br /><br /> `m`*startPoint*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Начальная точка новой фигуры.|  
  
 Верхний `M` регистр `startPoint` указывает, что это абсолютное значение; в нижнем `m` регистре указывается, что `startPoint` это смещение с предыдущей точкой, или (0,0), если его не существует. Если после команды перемещения указано несколько точек, будет нарисована линия к этим точкам, как в случае указания команды рисования линии.  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a>Команды рисования  
 Команда рисования может состоять из нескольких команд формы. Имеются следующие команды формы: линия, горизонтальная линия, вертикальная линия, кривая Безье третьего порядка, кривая Безье второго порядка, гладкая кривая Безье третьего порядка, гладкая кривая Безье второго порядка и эллиптическая дуга.  
  
 Все команды можно вводить как прописными, так и строчными буквами. Прописными буквами определяются абсолютные значения, а строчными —относительные. Контрольная точка для этого сегмента указывается относительно конечной точки в предыдущем примере. При последовательном вводе более одной команды одного и того же типа можно пропустить дубликат ввода команды; например, `L 100,200 300,400` эквивалентно `L 100,200 L 300,400`. В следующей таблице описаны команды **перемещения** и **рисования.**  
  
### <a name="line-command"></a>Команда рисования линии  
 Создает прямую линию между текущей и заданной конечной точками. `l 20 30`и `L 20,30` являются примерами действительных **линейных** команд.  
  
|Синтаксис|  
|------------|  
|`L`*endPoint*<br /><br /> — или —<br /><br /> `l`*endPoint*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*Конечной точки*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Конечная точка строки.|  

Верхний `L` регистр `endPoint` указывает, что это абсолютное значение; в нижнем `l` регистре указывается, что `endPoint` это смещение с предыдущей точкой, или (0,0), если его не существует.

### <a name="horizontal-line-command"></a>Команда рисования горизонтальной линии  
 Создает горизонтальную линию между текущей точкой и заданной координатой X. `H 90` — пример допустимой команды рисования горизонтальной линии.

|Синтаксис|  
|------------|  
|`H`  *X*<br /><br /> — или —<br /><br /> `h`  *X*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*X*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Координата X конечной точки линии.|  
  
Верхний `H` регистр `x` указывает, что это абсолютное значение; в нижнем `h` регистре указывается, что `x` это смещение с предыдущей точкой, или (0,0), если его не существует.
  
### <a name="vertical-line-command"></a>Команда рисования вертикальной линии  
 Создает вертикальную линию между текущей точкой и заданной координатой Y. `v 90` — пример допустимой команды рисования вертикальной линии.

|Синтаксис|  
|------------|  
|`V`  *Y*<br /><br /> — или —<br /><br /> `v`  *Y*|  
  
|Термин|Описание|  
|----------|-----------------|  
|*Y*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Координата Y конечной точки линии.|  

Верхний `V` регистр `y` указывает, что это абсолютное значение; в нижнем `v` регистре указывается, что `y` это смещение с предыдущей точкой, или (0,0), если его не существует.  

### <a name="cubic-bezier-curve-command"></a>Команда рисования кривой Безье третьего порядка  
 Создает кубическую кривую Безье между текущей точкой и`controlPoint`указанной `controlPoint`конечной точкой, используя две указанные контрольные точки (1 и 2). `C 100,200 200,400 300,200` — пример допустимой команды рисования кривой линии.  
  
|Синтаксис|  
|------------|  
|`C``controlPoint`1`controlPoint`2`endPoint`<br /><br /> — или —<br /><br /> `c``controlPoint`1`controlPoint`2`endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Первая контрольная точка кривой, которая определяет начальную касательную к кривой.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Вторая контрольная точка кривой, которая определяет конечную касательную к кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Точка для рисования кривой.|  
  
### <a name="quadratic-bezier-curve-command"></a>Команда рисования кривой Безье второго порядка  
 Создает квадратную кривую Безье между текущей точкой и указанной`controlPoint`конечной точкой с помощью указанной контрольной точки (). `q 100,200 300,200` — пример допустимой команды рисования кривой Безье второго порядка.  
  
|Синтаксис|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> — или —<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Контрольная точка кривой, которая определяет начальную и конечную касательные к кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Точка для рисования кривой.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Команда рисования гладкой кривой Безье третьего порядка  
 Создает кривую Безье третьего порядка между текущей и заданной конечной точками. Предполагается, что первая контрольная точка является отражением второй контрольной точки предыдущей команды относительно текущей точки. Если нет предыдущей команды или если предыдущая команда не является командой рисования кривой Безье третьего порядка или командой рисования гладкой кривой Безье третьего порядка, считается, что первая контрольная точка совпадает с текущей точкой. Вторая контрольная точка, контрольная точка для конца `controlPoint`кривой, указана 2. Например, `S 100,200 200,300` является допустимой гладкой кубической командой кривой Безье.  
  
|Синтаксис|  
|------------|  
|`S``controlPoint`2`endPoint`<br /><br /> — или —<br /><br /> `s``controlPoint`2`endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Контрольная точка кривой, которая определяет конечную касательную к кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Точка для рисования кривой.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>Команда рисования гладкой кривой Безье второго порядка  
 Создает кривую Безье второго порядка между текущей и заданной конечной точками. Предполагается, что контрольная точка является отражением контрольной точки предыдущей команды относительно текущей точки. Если нет предыдущей команды или если предыдущая команда не является командой рисования кривой Безье второго порядка или командой рисования гладкой кривой Безье второго порядка, считается, что контрольная точка совпадает с текущей точкой.  
  
|Синтаксис|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> — или —<br /><br /> `t` `controlPoint` `endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Контрольная точка кривой, которая определяет начальную касательную к кривой.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Точка для рисования кривой.|  
  
### <a name="elliptical-arc-command"></a>Команда рисования эллиптической дуги  
 Создает эллиптическую дугу между текущей и заданной конечной точками.  
  
|Синтаксис|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> — или —<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> Радиусы арки X и Y.|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Поворот эллипса в градусах.|  
|`isLargeArcFlag`|Значение 1, если угол дуги должен быть 180 градусов или больше, в противном случае — значение 0.|  
|`sweepDirectionFlag`|Значение 1, если дуга рисуется в направлении положительного угла, в противном случае — значение 0.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Точка, в которую рисуется дуга.|  
  
<a name="closecommand"></a>
## <a name="the-close-command"></a>Команда закрытия  
 Заканчивает текущую фигуру и создает линию, соединяющую текущую точку с начальной точкой фигуры. Эта команда создает соединительную линию (угол) между последним и первым сегментами фигуры.  
  
|Синтаксис|  
|------------|  
|`Z`<br /><br /> — или —<br /><br /> `z`|  

<a name="pointsyntax"></a>
## <a name="point-syntax"></a>Синтаксис точки  
 Описывает x- и y-координаты точки, где (0,0) находится верхний левый угол.
  
|Синтаксис|  
|------------|  
|`x` `,` `y`<br /><br /> — или —<br /><br /> `x` `y`|  
  
|Термин|Описание|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Координата X точки.|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Координата Y точки.|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a>Специальные значения  
 Вместо стандартных числовых значений можно использовать следующие специальные значения. Эти значения чувствительны к регистру.  
  
 Infinity  
 Представляет <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.  
  
 -бесконечность  
 Представляет <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.  
  
 NaN  
 Представляет <xref:System.Double.NaN?displayProperty=nameWithType>.  
  
 Можно также использовать экспоненциальное представление чисел. Например, `+1.e17` — допустимое значение.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [Общие сведения о фигурах и базовых средствах рисования в WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Общие сведения о геометрических фигурах](geometry-overview.md)
- [Как-к темам](geometries-how-to-topics.md)
