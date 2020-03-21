---
title: Обзор объектов Drawing
ms.date: 03/30/2017
helpviewer_keywords:
- ImageDrawing objects [WPF]
- GlyphRunDrawing objects [WPF]
- GeometryDrawing objects [WPF]
- drawings [WPF], about drawings
- Drawing objects [WPF]
- DrawingGroup objects [WPF]
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
ms.openlocfilehash: 7a5d00eb2fb7c66e5e42d40893806e13717e1d2e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186539"
---
# <a name="drawing-objects-overview"></a>Обзор объектов Drawing
Эта тема <xref:System.Windows.Media.Drawing> представляет объекты и описывает, как использовать их для эффективного рисования форм, бит-карт, текста и носителей. Используйте <xref:System.Windows.Media.Drawing> объекты, когда вы <xref:System.Windows.Media.DrawingBrush>создаете <xref:System.Windows.Media.Visual> клип искусства, краски с , или использовать объекты.  

<a name="whatisadrawingsection"></a>
## <a name="what-is-a-drawing-object"></a>Что такое объект-рисунок?  
 Объект <xref:System.Windows.Media.Drawing> описывает видимое содержимое, такое как форма, бит-карта, видео или строка текста. Различные типы рисунков описывают различные типы содержимого. Ниже приведен список различных типов объектов-рисунков.  
  
- <xref:System.Windows.Media.GeometryDrawing>- Рисует форму.  
  
- <xref:System.Windows.Media.ImageDrawing>- Рисует изображение.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>- Рисует текст.  
  
- <xref:System.Windows.Media.VideoDrawing>— Воспроизведение аудио- или видеофайла.  
  
- <xref:System.Windows.Media.DrawingGroup>- Рисует другие рисунки. Для объединения рисунков в один составной рисунок используйте группирование рисунков.  
  
 <xref:System.Windows.Media.Drawing>объекты универсальны; Есть много способов, <xref:System.Windows.Media.Drawing> вы можете использовать объект.  
  
- Вы можете отобразить его <xref:System.Windows.Media.DrawingImage> как <xref:System.Windows.Controls.Image> изображение с помощью и управления.  
  
- Вы можете использовать <xref:System.Windows.Media.DrawingBrush> его с для рисования <xref:System.Windows.Controls.Page.Background%2A> объекта, <xref:System.Windows.Controls.Page>например, .  
  
- Вы можете использовать его для <xref:System.Windows.Media.DrawingVisual>описания внешнего вида .  
  
- Вы можете использовать его для перечисления <xref:System.Windows.Media.Visual>содержимого .  
  
 WPF предоставляет другие типы объектов, которые поддерживают рисование фигур, растровых изображений, текста и мультимедиа. Например, можно также <xref:System.Windows.Shapes.Shape> использовать объекты для <xref:System.Windows.Controls.MediaElement> рисования фигур, а элемент управления предоставляет другой способ добавления видео в приложение. Так когда вы <xref:System.Windows.Media.Drawing> должны использовать объекты? Когда вы можете пожертвовать функциями уровня фреймворка, чтобы получить преимущества в производительности или когда вам нужны <xref:System.Windows.Freezable> функции. Поскольку <xref:System.Windows.Media.Drawing> объектам не хватает поддержки [для ввода,](../advanced/layout.md)ввода и фокусировки, они обеспечивают преимущества производительности, <xref:System.Windows.Media.Visual> которые делают их идеальными для описания фона, искусства клипов и для низкоуровневого рисования с объектами.  
  
 Поскольку они <xref:System.Windows.Freezable> являются <xref:System.Windows.Media.Drawing> объектом типа, объекты приобретают несколько специальных функций, которые включают в себя следующие: они могут быть объявлены в качестве [ресурсов,](../../../desktop-wpf/fundamentals/xaml-resources-define.md)совместно распределенных между несколькими объектами, сделанные только для чтения, чтобы улучшить производительность, клонированы и сделаны безопасными для потоков. Для получения дополнительной информации <xref:System.Windows.Freezable> о различных [Freezable Objects Overview](../advanced/freezable-objects-overview.md)функциях, предоставляемых объектами, см.  
  
<a name="drawinggeometriessection"></a>
## <a name="draw-a-shape"></a>Рисование фигуры  
 Чтобы нарисовать фигуру, вы используете <xref:System.Windows.Media.GeometryDrawing>. Свойство рисунка <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> геометрии описывает форму для <xref:System.Windows.Media.GeometryDrawing.Brush%2A> рисования, его свойство описывает, как <xref:System.Windows.Media.GeometryDrawing.Pen%2A> должна быть окрашена внутренняя часть формы, а его свойство описывает, как следует рисовать его контур.  
  
 В следующем примере <xref:System.Windows.Media.GeometryDrawing> используется для рисования формы. Форма описывается и <xref:System.Windows.Media.GeometryGroup> двумя <xref:System.Windows.Media.EllipseGeometry> объектами. Интерьер формы окрашен с и <xref:System.Windows.Media.LinearGradientBrush> его контур обращается <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>с .  
  
 Этот пример создает <xref:System.Windows.Media.GeometryDrawing>следующее.  
  
 ![GeometryDrawing из двух эллипсов](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Объект GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Полный пример см. в разделе [Создание GeometryDrawing](how-to-create-a-geometrydrawing.md).  
  
 Другие <xref:System.Windows.Media.Geometry> классы, такие как <xref:System.Windows.Media.PathGeometry> позволяют создавать более сложные фигуры, создавая кривые и дуги. Для получения <xref:System.Windows.Media.Geometry> дополнительной [информации](geometry-overview.md)об объектах см.  
  
 Для получения дополнительной информации о других способах <xref:System.Windows.Media.Drawing> рисования фигур, не использовающих объекты, см. [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md)  
  
<a name="drawingimagessection"></a>
## <a name="draw-an-image"></a>Рисование изображения  
 Чтобы нарисовать изображение, <xref:System.Windows.Media.ImageDrawing>вы используете . Свойство <xref:System.Windows.Media.ImageDrawing> <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> объекта описывает изображение для рисования, а его <xref:System.Windows.Media.ImageDrawing.Rect%2A> свойство определяет область, в которой нарисовано изображение.  
  
 В следующем примере изображение рисуется в прямоугольнике, расположенном в точке (75,75) и имеющем размер 100 на 100 пикселей. На следующей <xref:System.Windows.Media.ImageDrawing> иллюстрации показан созданный примером. Серая граница была добавлена, чтобы <xref:System.Windows.Media.ImageDrawing>показать границы .  
  
 ![ImageDrawing размером 100 на 100 в точке &#40;75,75&#41;](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing размером 100 на 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Дополнительную информацию об изображениях см. в разделе [Общие сведения об изображениях](imaging-overview.md).  
  
<a name="playmedia"></a>
## <a name="play-media-code-only"></a>Воспроизведение мультимедиа (только код)  
  
> [!NOTE]
> Хотя вы можете <xref:System.Windows.Media.VideoDrawing> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]объявить в , вы можете только загрузить и воспроизвести его средства массовой информации с помощью кода. Для воспроизведения видео в, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]использовать <xref:System.Windows.Controls.MediaElement> вместо.  
  
 Для воспроизведения аудио- или <xref:System.Windows.Media.VideoDrawing> видеофайла используется <xref:System.Windows.Media.MediaPlayer>a и a . Есть два способа загрузки и воспроизведения мультимедиа. Во-первых, использовать <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> сами по себе, а второй <xref:System.Windows.Media.MediaTimeline> способ заключается <xref:System.Windows.Media.MediaPlayer> <xref:System.Windows.Media.VideoDrawing>в создании собственного использования с и .  
  
> [!NOTE]
> При распространении мультимедиа с приложением, в отличие от изображений, файл мультимедиа нельзя использовать как ресурс проекта. Вместо этого в файле проекта необходимо выбрать тип мультимедиа `Content` и задать для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
 Чтобы играть в носители, не создавая свой собственный, <xref:System.Windows.Media.MediaTimeline>вы выполняете следующие шаги.  
  
1. Создание объекта <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. Используйте <xref:System.Windows.Media.MediaPlayer.Open%2A> метод для загрузки файла мультимедиа.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Создайте таблицу <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Укажите размер и местоположение для рисования носителя, установив свойство <xref:System.Windows.Media.VideoDrawing.Rect%2A> . <xref:System.Windows.Media.VideoDrawing>  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Установите <xref:System.Windows.Media.VideoDrawing.Player%2A> свойство <xref:System.Windows.Media.VideoDrawing> с <xref:System.Windows.Media.MediaPlayer> созданным вами.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Используйте <xref:System.Windows.Media.MediaPlayer.Play%2A> <xref:System.Windows.Media.MediaPlayer> метод, чтобы начать воспроизведение средств массовой информации.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 В следующем примере используется a <xref:System.Windows.Media.VideoDrawing> и a <xref:System.Windows.Media.MediaPlayer> для воспроизведения видеофайла один раз.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Чтобы получить дополнительный контроль времени <xref:System.Windows.Media.MediaTimeline> над <xref:System.Windows.Media.MediaPlayer> носителями, используйте с и <xref:System.Windows.Media.VideoDrawing> объектов. Позволяет <xref:System.Windows.Media.MediaTimeline> указать, следует ли повторять видео. Чтобы использовать <xref:System.Windows.Media.MediaTimeline> с <xref:System.Windows.Media.VideoDrawing>, вы выполняете следующие шаги:  
  
1. Объявить <xref:System.Windows.Media.MediaTimeline> и установить его поведение времени.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Создать <xref:System.Windows.Media.MediaClock> из <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Создайте <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.MediaClock> используйте <xref:System.Windows.Media.MediaPlayer.Clock%2A> для установки своего свойства.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Создайте <xref:System.Windows.Media.VideoDrawing> и <xref:System.Windows.Media.MediaPlayer> присвоите <xref:System.Windows.Media.VideoDrawing.Player%2A> свойство <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 В следующем примере <xref:System.Windows.Media.MediaPlayer> используется <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaTimeline> с a и a для воспроизведения видео неоднократно.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Обратите внимание, что <xref:System.Windows.Media.MediaTimeline>при использовании, <xref:System.Windows.Media.Animation.ClockController> вы <xref:System.Windows.Media.Animation.Clock.Controller%2A> используете <xref:System.Windows.Media.MediaClock> интерактивный вернулся из свойства воспроизведения мультимедиа вместо интерактивных методов <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>
## <a name="draw-text"></a>Рисование текста  
 Чтобы нарисовать текст, <xref:System.Windows.Media.GlyphRun>вы используете a <xref:System.Windows.Media.GlyphRunDrawing> и a . В следующем примере <xref:System.Windows.Media.GlyphRunDrawing> используется для рисования текста "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 A <xref:System.Windows.Media.GlyphRun> — это низкоуровневый объект, предназначенный для использования с сценариями представления документов с фиксированным форматом и печати. Более простой способ нарисовать текст <xref:System.Windows.Controls.Label> на <xref:System.Windows.Controls.TextBlock>экране заключается в использовании или . Для получения <xref:System.Windows.Media.GlyphRun>дополнительной информации о , см. [Введение в GlyphRun объект и Glyphs Элемент](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) обзор.  
  
<a name="compositedrawingssection"></a>
## <a name="composite-drawings"></a>Составные рисунки  
 A <xref:System.Windows.Media.DrawingGroup> позволяет объединить несколько рисунков в один составной рисунок. С <xref:System.Windows.Media.DrawingGroup>помощью, вы можете объединить формы, изображения <xref:System.Windows.Media.Drawing> и текст в один объект.  
  
 В следующем примере <xref:System.Windows.Media.DrawingGroup> используется <xref:System.Windows.Media.GeometryDrawing> для <xref:System.Windows.Media.ImageDrawing> объединения двух объектов и объекта. В этом примере формируются следующие данные:  
  
 ![DrawingGroup с несколькими рисунками](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Составной рисунок  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Также <xref:System.Windows.Media.DrawingGroup> позволяет применять непрозрачные маски, преобразования, эффекты биткарты и другие операции к его содержимому. <xref:System.Windows.Media.DrawingGroup>операции применяются в следующем <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A> <xref:System.Windows.Media.DrawingGroup.Opacity%2A>порядке: <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>, , <xref:System.Windows.Media.DrawingGroup.Transform%2A> <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, , и тогда .  
  
 На следующей иллюстрации <xref:System.Windows.Media.DrawingGroup> показан порядок применения операций.  
  
 ![Порядок операций DrawingGroup](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Порядок операций DrawingGroup  
  
 В следующей таблице описаны свойства, <xref:System.Windows.Media.DrawingGroup> которые можно использовать для управления содержимым объекта.  
  
|Свойство|Описание|Рисунки|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Изменяет непрозрачность выбранных частей содержимого. <xref:System.Windows.Media.DrawingGroup> Пример см. в разделе [Практическое руководство. Управление прозрачностью рисунка](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)).|![Рисоваягруппа с непрозрачностью маски](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Равномерно изменяет непрозрачность содержимого. <xref:System.Windows.Media.DrawingGroup> Используйте это свойство, чтобы сделать прозрачным или частично прозрачным. <xref:System.Windows.Media.Drawing> Пример см. в разделе [Практическое руководство. Применение маски непрозрачности к рисунку](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90)).|![DrawingGroups с различными параметрами непрозрачности](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Применяется <xref:System.Windows.Media.Effects.BitmapEffect> к <xref:System.Windows.Media.DrawingGroup> содержимому. Пример см. в разделе [Практическое руководство. Применение BitmapEffect к рисунку](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)).|![DrawingGroup с BlurBitmapEffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Зажимает содержимое в <xref:System.Windows.Media.DrawingGroup> регион, который вы описываете <xref:System.Windows.Media.Geometry>с помощью . Пример см. в разделе [Практическое руководство. Обрезка рисунка](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) .|![DrawingGroup с определенной областью обрезки](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Привязывает аппаратно-независимые пиксели к пикселям устройства, следуя указанным правилам. Это свойство полезно для обеспечения резкой отрисовки высокодетализированной графики на дисплеях с низким разрешением. Пример см. в разделе [Применение GuidelineSet к рисунку](how-to-apply-a-guidelineset-to-a-drawing.md).|![DrawingGroup с и без GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Преобразует содержимое. <xref:System.Windows.Media.DrawingGroup> Пример см. в разделе [Практическое руководство. Применение преобразования к рисунку](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)).|![Повернутый DrawingGroup](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>
## <a name="display-a-drawing-as-an-image"></a>Отображение рисунка в виде изображения  
 Чтобы <xref:System.Windows.Media.Drawing> отобразить <xref:System.Windows.Controls.Image> элемент <xref:System.Windows.Media.DrawingImage> управления, <xref:System.Windows.Controls.Image> используйте <xref:System.Windows.Controls.Image.Source%2A> элемент <xref:System.Windows.Media.DrawingImage> управления и <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> установите свойство объекта на чертеж, который вы хотите отобразить.  
  
 В следующем примере <xref:System.Windows.Controls.Image> используется элемент <xref:System.Windows.Media.GeometryDrawing>управления <xref:System.Windows.Media.DrawingImage> и элемент управления для отображения. В этом примере формируются следующие данные:  
  
 ![GeometryDrawing из двух эллипсов](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Объект DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>
## <a name="paint-an-object-with-a-drawing"></a>Заполнение объекта с помощью рисунка  
 A <xref:System.Windows.Media.DrawingBrush> — это тип кисти, который рисует область с помощью рисунков. Этот объект можно использовать для закраски практически любого графического объекта с помощью рисунка. Свойство <xref:System.Windows.Media.Drawing> <xref:System.Windows.Media.DrawingBrush> описывает его <xref:System.Windows.Media.DrawingBrush.Drawing%2A>. Чтобы сделать <xref:System.Windows.Media.Drawing> <xref:System.Windows.Media.DrawingBrush>с помощью <xref:System.Windows.Media.Drawing> свойства кисти, добавьте ее в кисть и используйте кисть для рисования графического объекта, например элементуправления или панели.  
  
 Следующие примеры <xref:System.Windows.Media.DrawingBrush> используют <xref:System.Windows.Shapes.Shape.Fill%2A> для <xref:System.Windows.Shapes.Rectangle> рисования с узором, созданным из <xref:System.Windows.Media.GeometryDrawing>. В этом примере формируются следующие данные:  
  
 ![Мозаичная DrawingBrush](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
GeometryDrawing с DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 Класс <xref:System.Windows.Media.DrawingBrush> предоставляет различные варианты растяжения и плитки его содержания. Для получения <xref:System.Windows.Media.DrawingBrush>дополнительной информации о, см. [Картина с изображениями, рисунки и визуальные](painting-with-images-drawings-and-visuals.md) обзор.  
  
<a name="renderingwithvisualsection"></a>
## <a name="render-a-drawing-with-a-visual"></a>Рисование с помощью объектов Visual  
 A <xref:System.Windows.Media.DrawingVisual> — это тип визуального объекта, предназначенный для визуализации рисунка. Работа непосредственно на визуальном уровне является инструментом для разработчиков, которым требуется построить настраиваемую графическую среду, и не описывается в этом обзоре. Дополнительные сведения см. в разделе [Использование объектов DrawingVisual](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>
## <a name="drawingcontext-objects"></a>Объекты DrawingContext  
 Класс <xref:System.Windows.Media.DrawingContext> позволяет заполнить <xref:System.Windows.Media.Visual> или с <xref:System.Windows.Media.Drawing> визуальным содержанием. Многие такие низкоуровневые <xref:System.Windows.Media.DrawingContext> графические объекты используют, потому что он описывает графическое содержание очень эффективно.  
  
 Хотя <xref:System.Windows.Media.DrawingContext> методы рисования похожи на методы <xref:System.Drawing.Graphics?displayProperty=nameWithType> рисования типа, они на самом деле очень разные. <xref:System.Windows.Media.DrawingContext>используется с сохраненной графической системой режима, в <xref:System.Drawing.Graphics?displayProperty=nameWithType> то время как тип используется с непосредственной графической системой режима. При использовании <xref:System.Windows.Media.DrawingContext> команд рисования объекта фактически используется набор инструкций рендеринга (хотя точный механизм хранения зависит от <xref:System.Windows.Media.DrawingContext>типа объекта, который поставляет), который позже будет использоваться графической системой; вы не рисуете на экране в режиме реального времени. Для получения дополнительной информации о том, как работает графическая система Фонда презентации Windows (WPF), см. [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md)  
  
 Вы никогда непосредственно мгновенного <xref:System.Windows.Media.DrawingContext>; вы можете, однако, приобрести контекст чертежа из определенных методов, таких как <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> и <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>.  
  
<a name="enumeratevisualcontents"></a>
## <a name="enumerate-the-contents-of-a-visual"></a>Перечисление содержимого визуального элемента  
 В дополнение к другим <xref:System.Windows.Media.Drawing> видам использования, объекты также предоставляют объектную модель для перечисления <xref:System.Windows.Media.Visual>содержимого.  
  
 В следующем примере <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> используется метод <xref:System.Windows.Media.DrawingGroup> для <xref:System.Windows.Media.Visual> получения значения и перечисления его.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
- [Общие сведения о геометрических фигурах](geometry-overview.md)
- [Общие сведения о фигурах и базовых средствах рисования в WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md)
- [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md)
- [Как-к темам](drawings-how-to-topics.md)
