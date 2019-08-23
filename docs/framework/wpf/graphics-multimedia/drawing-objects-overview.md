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
ms.openlocfilehash: d739865a692fa5ef448eba91369015580e5eda97
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916311"
---
# <a name="drawing-objects-overview"></a>Обзор объектов Drawing
В этом разделе <xref:System.Windows.Media.Drawing> представлены объекты и описано, как использовать их для эффективного рисования фигур, точечных рисунков, текста и мультимедиа. Используйте <xref:System.Windows.Media.Drawing> объекты при создании коллекции картинок, закрасьте их <xref:System.Windows.Media.DrawingBrush>с помощью объекта <xref:System.Windows.Media.Visual> или используйте объекты.  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>Что такое объект-рисунок?  
 <xref:System.Windows.Media.Drawing> Объект описывает видимое содержимое, например фигуру, Растровое изображение, видео или строку текста. Различные типы рисунков описывают различные типы содержимого. Ниже приведен список различных типов объектов-рисунков.  
  
- <xref:System.Windows.Media.GeometryDrawing>— Рисует фигуру.  
  
- <xref:System.Windows.Media.ImageDrawing>— Рисует изображение.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>— Рисует текст.  
  
- <xref:System.Windows.Media.VideoDrawing>— Воспроизводит звуковой файл или видеофайл.  
  
- <xref:System.Windows.Media.DrawingGroup>— Рисует другие рисунки. Для объединения рисунков в один составной используйте группирование рисунков.  
  
 <xref:System.Windows.Media.Drawing>объекты являются универсальными; Существует множество способов использования <xref:System.Windows.Media.Drawing> объекта.  
  
- Его можно отобразить в виде изображения с помощью <xref:System.Windows.Media.DrawingImage> <xref:System.Windows.Controls.Image> и элемента управления.  
  
- Его можно использовать с, <xref:System.Windows.Media.DrawingBrush> чтобы закрасить объект, например, <xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page>объекта.  
  
- Его можно использовать для описания внешнего вида <xref:System.Windows.Media.DrawingVisual>.  
  
- Его можно использовать для перечисления содержимого <xref:System.Windows.Media.Visual>.  
  
 WPF предоставляет другие типы объектов, которые поддерживают рисование фигур, растровых изображений, текста и мультимедиа. Например, можно также использовать <xref:System.Windows.Shapes.Shape> объекты для рисования фигур, <xref:System.Windows.Controls.MediaElement> а элемент управления предоставляет другой способ добавления видео в приложение. Итак, когда следует использовать <xref:System.Windows.Media.Drawing> объекты? Если вы можете пожертвовать функциями уровня инфраструктуры, чтобы повысить производительность или необходимость <xref:System.Windows.Freezable> использования функций. Поскольку <xref:System.Windows.Media.Drawing> объекты не поддерживают [Макет](../advanced/layout.md), ввод и фокус, они предоставляют преимущества для повышения производительности, которые делают их идеальными для описания фона, картинок и для низкоуровневых изображений с <xref:System.Windows.Media.Visual> объектами.  
  
 Так как они являются объектом <xref:System.Windows.Freezable> типа, <xref:System.Windows.Media.Drawing> объекты получают несколько специальных функций, в том числе следующие: они могут быть объявлены как [ресурсы](../advanced/xaml-resources.md), совместно использоваться несколькими объектами и доступны только для чтения для повышения производительности, клонирования и является потокобезопасным. Дополнительные сведения о различных функциях, предоставляемых <xref:System.Windows.Freezable> объектами, см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Рисование фигуры  
 Чтобы нарисовать фигуру, используйте <xref:System.Windows.Media.GeometryDrawing>. <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> Свойство геометрического рисунка описывает рисуемую форму, ее <xref:System.Windows.Media.GeometryDrawing.Brush%2A> свойство описывает, как должна быть окрашена внутренняя часть фигуры, а ее <xref:System.Windows.Media.GeometryDrawing.Pen%2A> свойство описывает способ отрисовки ее контура.  
  
 В следующем примере используется <xref:System.Windows.Media.GeometryDrawing> для рисования фигуры. Фигура описывается <xref:System.Windows.Media.GeometryGroup> и двумя <xref:System.Windows.Media.EllipseGeometry> объектами. Внутренняя часть фигуры рисуется с <xref:System.Windows.Media.LinearGradientBrush> помощью, а ее контур рисуется <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>с помощью.  
  
 В этом примере создается следующее <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing с двумя эллипсами](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Объект GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Полный пример см. в разделе [Создание GeometryDrawing](how-to-create-a-geometrydrawing.md).  
  
 Другие <xref:System.Windows.Media.Geometry> классы, такие как <xref:System.Windows.Media.PathGeometry> , позволяют создавать более сложные фигуры путем создания кривых и дуг. Дополнительные сведения об объектах <xref:System.Windows.Media.Geometry> см. в разделе [Общие сведения о геометрии](geometry-overview.md).  
  
 Дополнительные сведения о других способах рисования фигур, которые не используют <xref:System.Windows.Media.Drawing> объекты, см. [в статье Общие сведения о фигурах и базовом рисовании в WPF](shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Рисование изображения  
 Для рисования изображения используется объект <xref:System.Windows.Media.ImageDrawing>. Свойство объекта описывает изображение для рисования, а его <xref:System.Windows.Media.ImageDrawing.Rect%2A> свойство определяет область, в которой рисуется изображение. <xref:System.Windows.Media.ImageDrawing> <xref:System.Windows.Media.ImageDrawing.ImageSource%2A>  
  
 В следующем примере изображение рисуется в прямоугольнике, расположенном в точке (75,75) и имеющем размер 100 на 100 пикселей. На следующем рисунке показан <xref:System.Windows.Media.ImageDrawing> пример, созданный в примере. Добавлена серая граница для отображения границ объекта <xref:System.Windows.Media.ImageDrawing>.  
  
 ![100 на 100 ImageDrawing нарисована &#40;в 75,&#41; 75](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing размером 100 на 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Дополнительную информацию об изображениях см. в разделе [Общие сведения об изображениях](imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Воспроизведение мультимедиа (только код)  
  
> [!NOTE]
> Хотя можно объявить <xref:System.Windows.Media.VideoDrawing> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], вы можете загружать и воспроизводить свои носители только с помощью кода. Чтобы воспроизвести видео в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], <xref:System.Windows.Controls.MediaElement> используйте вместо него.  
  
 Чтобы воспроизвести аудио- <xref:System.Windows.Media.VideoDrawing> или видеофайл, используйте <xref:System.Windows.Media.MediaPlayer>и. Есть два способа загрузки и воспроизведения мультимедиа. Первый <xref:System.Windows.Media.MediaPlayer> — использовать <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.VideoDrawing> и сам по себе, а второй способ — создать <xref:System.Windows.Media.MediaPlayer> собственный для использования с и <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
> При распространении мультимедиа с приложением, в отличие от изображений, файл мультимедиа нельзя использовать как ресурс проекта. Вместо этого в файле проекта необходимо выбрать тип мультимедиа `Content` и задать для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
 Чтобы воспроизвести носитель без создания собственного <xref:System.Windows.Media.MediaTimeline>, выполните следующие действия.  
  
1. Создание объекта <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. <xref:System.Windows.Media.MediaPlayer.Open%2A> Используйте метод для загрузки файла мультимедиа.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Создайте таблицу <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Укажите размер и расположение для рисования носителя, задав <xref:System.Windows.Media.VideoDrawing.Rect%2A> свойство <xref:System.Windows.Media.VideoDrawing>объекта.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Задайте свойство объекта с созданным <xref:System.Windows.Media.MediaPlayer>вами. <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.VideoDrawing.Player%2A>  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Используйте метод объекта, <xref:System.Windows.Media.MediaPlayer> чтобы начать воспроизведение мультимедиа. <xref:System.Windows.Media.MediaPlayer.Play%2A>  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 В следующем примере используется <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer> и для воспроизведения видеофайла один раз.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Чтобы получить дополнительный контроль времени для носителя, используйте объект <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> с объектами и <xref:System.Windows.Media.VideoDrawing> . <xref:System.Windows.Media.MediaTimeline> Позволяет указать, следует ли повторять воспроизведение видео. Чтобы использовать <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.VideoDrawing>с, выполните следующие действия.  
  
1. Объявите <xref:System.Windows.Media.MediaTimeline> и задайте его поведение времени.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Создайте объект <xref:System.Windows.Media.MediaClock> <xref:System.Windows.Media.MediaTimeline>из.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Создайте и используйте для задания его <xref:System.Windows.Media.MediaPlayer.Clock%2A> свойства. <xref:System.Windows.Media.MediaClock> <xref:System.Windows.Media.MediaPlayer>  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Создайте объект <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer> и присвойте ему <xref:System.Windows.Media.VideoDrawing.Player%2A> свойство объекта <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 В следующем примере <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> с помощью используется с и <xref:System.Windows.Media.VideoDrawing> , чтобы воспроизвести видео повторно.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Обратите внимание, что при использовании <xref:System.Windows.Media.MediaTimeline>среды используется интерактивный <xref:System.Windows.Media.Animation.ClockController> метод, возвращенный <xref:System.Windows.Media.Animation.Clock.Controller%2A> <xref:System.Windows.Media.MediaClock> из свойства объекта для управления воспроизведением мультимедиа вместо интерактивных методов <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Рисование текста  
 Для рисования текста используются <xref:System.Windows.Media.GlyphRunDrawing> <xref:System.Windows.Media.GlyphRun>и. В следующем примере используется <xref:System.Windows.Media.GlyphRunDrawing> для рисования текста «Hello World».  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Объект <xref:System.Windows.Media.GlyphRun> является объектом низкого уровня, предназначенным для использования с представлением документов с фиксированным форматом и сценариями печати. Более простой способ отображения текста на экране — использовать <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBlock>или. Дополнительные сведения о см <xref:System.Windows.Media.GlyphRun>. в разделе Общие сведения о [объекте GlyphRun и элементе Glyphs](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) Overview.  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Составные рисунки  
 <xref:System.Windows.Media.DrawingGroup> Позволяет объединить несколько рисунков в один составной рисунок. С помощью <xref:System.Windows.Media.DrawingGroup>можно объединить фигуры, изображения и текст в один <xref:System.Windows.Media.Drawing> объект.  
  
 В следующем примере используется <xref:System.Windows.Media.DrawingGroup> для объединения двух <xref:System.Windows.Media.GeometryDrawing> объектов и <xref:System.Windows.Media.ImageDrawing> объекта. В этом примере формируются следующие данные:  
  
 ![DrawingGroup с несколькими рисунками](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Составной рисунок  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 А <xref:System.Windows.Media.DrawingGroup> также позволяет применять маски непрозрачности, преобразования, растровые эффекты и другие операции с содержимым. <xref:System.Windows.Media.DrawingGroup>операции применяются в следующем порядке: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>,, и <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 На следующем рисунке показан порядок <xref:System.Windows.Media.DrawingGroup> применения операций.  
  
 ![DrawingGroup порядок операций](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Порядок операций для DrawingGroup  
  
 В следующей таблице описаны свойства, которые можно использовать для управления <xref:System.Windows.Media.DrawingGroup> содержимым объекта.  
  
|Свойство.|Описание|Рисунки|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Изменяет прозрачность выбранных частей <xref:System.Windows.Media.DrawingGroup> содержимого. Пример см. в статье [Практическое руководство. Управление прозрачностью рисунка](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)).|![DrawingGroup с маской непрозрачности ](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Равномерно изменяет прозрачность <xref:System.Windows.Media.DrawingGroup> содержимого. Используйте это свойство, чтобы сделать <xref:System.Windows.Media.Drawing> прозрачным или частично прозрачным. Пример см. в статье [Практическое руководство. Применение маски непрозрачности к изображению](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90)).|![DrawingGroups с различными параметрами прозрачности ](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Применяет <xref:System.Windows.Media.DrawingGroup>ксодержимому <xref:System.Windows.Media.Effects.BitmapEffect> . Пример см. в статье [Практическое руководство. Применение BitmapEffect к рисованию](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)).|![DrawingGroup с BlurBitmapEffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Вырезает <xref:System.Windows.Media.Geometry>содержимое в регион, который вы описываете с помощью. <xref:System.Windows.Media.DrawingGroup> Пример см. в статье [Практическое руководство. Обрезка рисунка](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) .|![DrawingGroup с определенной областью обрезки ](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Привязывает аппаратно-независимые пиксели к пикселям устройства, следуя указанным правилам. Это свойство полезно для обеспечения резкой отрисовки высокодетализированной графики на дисплеях с низким разрешением. Пример см. в разделе [Применение GuidelineSet к рисунку](how-to-apply-a-guidelineset-to-a-drawing.md).|![DrawingGroup c GuidelineSet и без него ](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Преобразует <xref:System.Windows.Media.DrawingGroup> содержимое. Пример см. в статье [Практическое руководство. Применение преобразования к рисованию](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)).|![Повернутая DrawingGroup](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Отображение рисунка в виде изображения  
 Чтобы отобразить объект <xref:System.Windows.Media.Drawing> <xref:System.Windows.Controls.Image> с элементом <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> <xref:System.Windows.Media.DrawingImage> управления <xref:System.Windows.Media.DrawingImage> , используйте в качестве элемента управления <xref:System.Windows.Controls.Image.Source%2A> и задайте для свойства объекта <xref:System.Windows.Controls.Image> отображаемый рисунок.  
  
 В следующем примере используется <xref:System.Windows.Media.DrawingImage> <xref:System.Windows.Controls.Image> и элемент управления для вывода <xref:System.Windows.Media.GeometryDrawing>. В этом примере формируются следующие данные:  
  
 ![GeometryDrawing с двумя эллипсами](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Объект DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Заполнение объекта с помощью рисунка  
 <xref:System.Windows.Media.DrawingBrush> — Это тип кисти, которая закрашивает область объектом-рисунком. Этот объект можно использовать для закраски практически любого графического объекта с помощью рисунка. Свойство объекта описывает его<xref:System.Windows.Media.DrawingBrush.Drawing%2A>. <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.Drawing> Чтобы отобразить объект <xref:System.Windows.Media.Drawing> <xref:System.Windows.Media.DrawingBrush>с помощью, добавьте его в <xref:System.Windows.Media.Drawing> кисть с помощью свойства кисти и используйте кисть для рисования графического объекта, такого как элемент управления или панель.  
  
 В следующих примерах используется <xref:System.Windows.Media.DrawingBrush> для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования объекта <xref:System.Windows.Shapes.Rectangle> с шаблоном, созданным из <xref:System.Windows.Media.GeometryDrawing>. В этом примере формируются следующие данные:  
  
 ![Мозаичная DrawingBrush](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
GeometryDrawing с DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 <xref:System.Windows.Media.DrawingBrush> Класс предоставляет разнообразные параметры для растяжения и мозаичного заполнения его содержимого. Дополнительные сведения о см <xref:System.Windows.Media.DrawingBrush>. в разделе Общие сведения о [рисовании с помощью изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md) .  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Рисование с помощью объектов Visual  
 <xref:System.Windows.Media.DrawingVisual> — Это тип визуального объекта, предназначенного для отрисовки рисунка. Работа непосредственно на визуальном уровне является инструментом для разработчиков, которым требуется построить настраиваемую графическую среду, и не описывается в этом обзоре. Дополнительные сведения см. в разделе [Использование объектов DrawingVisual](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>Объекты DrawingContext  
 Класс позволяет заполнить <xref:System.Windows.Media.Visual> или<xref:System.Windows.Media.Drawing> с помощью визуального содержимого. <xref:System.Windows.Media.DrawingContext> Многие такие графические объекты более низкого уровня используют объект <xref:System.Windows.Media.DrawingContext> , так как он очень эффективно описывает графическое содержимое.  
  
 Несмотря на <xref:System.Windows.Media.DrawingContext> то, что методы рисования выглядят аналогично методам <xref:System.Drawing.Graphics?displayProperty=nameWithType> рисования типа, они на самом деле сильно отличаются. <xref:System.Windows.Media.DrawingContext>используется с графической системой с сохранением режима, а <xref:System.Drawing.Graphics?displayProperty=nameWithType> тип используется с графической системой в режиме интерпретации. При использовании <xref:System.Windows.Media.DrawingContext> команд рисования объекта вы фактически сохраняете набор инструкций по отрисовке (хотя точный механизм хранения зависит от типа объекта, который <xref:System.Windows.Media.DrawingContext>предоставляет), который впоследствии будет использоваться графической системой; не рисуются на экране в режиме реального времени. Дополнительные сведения о работе графической системы Windows Presentation Foundation (WPF) см. в разделе [Общие сведения о отрисовке графики в WPF](wpf-graphics-rendering-overview.md).  
  
 Вы никогда непосредственно не создаете экземпляр <xref:System.Windows.Media.DrawingContext>, однако можете получить контекст рисования с помощью определенных методов, например <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> и <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Перечисление содержимого визуального элемента  
 Наряду с другими своими возможностями, объекты <xref:System.Windows.Media.Drawing> также предоставляют объектную модель для перечисления содержимого <xref:System.Windows.Media.Visual>.  
  
 В следующем примере метод <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> используется для извлечения значения <xref:System.Windows.Media.DrawingGroup> из <xref:System.Windows.Media.Visual> и перечисления содержимого группы.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
- [Общие сведения о классе Geometry](geometry-overview.md)
- [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md)
- [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md)
- [Разделы практического руководства](drawings-how-to-topics.md)
