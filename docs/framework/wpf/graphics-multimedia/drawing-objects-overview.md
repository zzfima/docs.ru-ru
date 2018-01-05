---
title: "Обзор объектов Drawing"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ImageDrawing objects [WPF]
- GlyphRunDrawing objects [WPF]
- GeometryDrawing objects [WPF]
- drawings [WPF], about drawings
- Drawing objects [WPF]
- DrawingGroup objects [WPF]
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: abdc98a6fbf48a30f2f5702e7c2d78396381de6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="drawing-objects-overview"></a>Обзор объектов Drawing
В этом разделе описываются <xref:System.Windows.Media.Drawing> объектов и описывается, как их использовать для эффективного рисования фигур, точечных рисунков, текста и мультимедиа. Используйте <xref:System.Windows.Media.Drawing> объектов при создании коллекции картинок, рисование с <xref:System.Windows.Media.DrawingBrush>, или используйте <xref:System.Windows.Media.Visual> объектов.  
  
 
  
<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>Что такое объект-рисунок?  
 Объект <xref:System.Windows.Media.Drawing> описывает отображаемое содержимое, например фигуры, растрового изображения, видео или строка текста. Различные типы рисунков описывают различные типы содержимого. Ниже приведен список различных типов объектов-рисунков.  
  
-   <xref:System.Windows.Media.GeometryDrawing>— Выводит фигуру.  
  
-   <xref:System.Windows.Media.ImageDrawing>— Выводит изображение.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing>— Выводит текст.  
  
-   <xref:System.Windows.Media.VideoDrawing>— Воспроизводит файл аудио и видео.  
  
-   <xref:System.Windows.Media.DrawingGroup>— Выводит другие рисунки. Для объединения рисунков в один составной используйте группирование рисунков.  
  
 <xref:System.Windows.Media.Drawing>объекты являются универсальными. Существует множество способов, которые можно использовать <xref:System.Windows.Media.Drawing> объекта.  
  
-   Отображаются как изображение с помощью <xref:System.Windows.Media.DrawingImage> и <xref:System.Windows.Controls.Image> элемента управления.  
  
-   Вы можете использовать его с <xref:System.Windows.Media.DrawingBrush> для рисования объекта, таких как <xref:System.Windows.Controls.Page.Background%2A> из <xref:System.Windows.Controls.Page>.  
  
-   Его можно использовать для описания вида <xref:System.Windows.Media.DrawingVisual>.  
  
-   Его можно использовать для перечисления содержимого <xref:System.Windows.Media.Visual>.  
  
 WPF предоставляет другие типы объектов, которые поддерживают рисование фигур, растровых изображений, текста и мультимедиа. Например, можно также использовать <xref:System.Windows.Shapes.Shape> объектов для рисования фигур и <xref:System.Windows.Controls.MediaElement> элемент управления предоставляет еще один способ добавления видео в приложение. Поэтому когда следует использовать <xref:System.Windows.Media.Drawing> объектов? Когда можно пожертвовать возможностями уровня среды, чтобы повысить производительность, а также при необходимости <xref:System.Windows.Freezable> функции. Поскольку <xref:System.Windows.Media.Drawing> объектов не поддерживают [макета](../../../../docs/framework/wpf/advanced/layout.md), ввода и направления, они предоставляют выигрыш в производительности, делает его идеальным для описания фона, коллекция картинок и низкоуровневых рисунков с <xref:System.Windows.Media.Visual> объектов.  
  
 Так как они представляют собой тип <xref:System.Windows.Freezable> объекта, <xref:System.Windows.Media.Drawing> объектов получить несколько специальных функций, включая следующее: они могут быть объявлены как [ресурсов](../../../../docs/framework/wpf/advanced/xaml-resources.md), общие для нескольких объектов, доступным только для чтения для повышения производительность, клонировать и делать потокобезопасными. Дополнительные сведения о различных возможностях, предоставляемых <xref:System.Windows.Freezable> объектов, в разделе [Freezable Общие сведения об объектах](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Рисование фигуры  
 Чтобы нарисовать фигуру, используйте <xref:System.Windows.Media.GeometryDrawing>. Прорисовки <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> свойство описывает фигуру, чтобы нарисовать, его <xref:System.Windows.Media.GeometryDrawing.Brush%2A> свойство описывает, каким образом следует рисования внутренней области фигуры и его <xref:System.Windows.Media.GeometryDrawing.Pen%2A> свойство описывает, как должно отображаться его контура.  
  
 В следующем примере используется <xref:System.Windows.Media.GeometryDrawing> Рисование фигур. Описывается фигуры <xref:System.Windows.Media.GeometryGroup> и два <xref:System.Windows.Media.EllipseGeometry> объектов. Рисования внутренней области фигуры с <xref:System.Windows.Media.LinearGradientBrush> и его контур рисуется с <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.  
  
 Этот пример создает следующие <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing двух эллипсов](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Объект GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Полный пример см. в разделе [Создание GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-geometrydrawing.md).  
  
 Другие <xref:System.Windows.Media.Geometry> классов, таких как <xref:System.Windows.Media.PathGeometry> для создания более сложных фигур, создав кривые и дуги. Дополнительные сведения о <xref:System.Windows.Media.Geometry> объектов, в разделе [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 Дополнительные сведения о других способах рисования фигур, не использующих <xref:System.Windows.Media.Drawing> объектов, в разделе [фигур и базовых средств рисования в общие сведения о WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Рисование изображения  
 Чтобы нарисовать изображение, используйте <xref:System.Windows.Media.ImageDrawing>. <xref:System.Windows.Media.ImageDrawing> Объекта <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> свойство описывает изображения для отрисовки и его <xref:System.Windows.Media.ImageDrawing.Rect%2A> свойство определяет область, в которой рисуется изображение.  
  
 В следующем примере изображение рисуется в прямоугольнике, расположенном в точке (75,75) и имеющем размер 100 на 100 пикселей. На следующем рисунке показана <xref:System.Windows.Media.ImageDrawing> созданный в примере. Серая рамка был добавлен для отображения границы <xref:System.Windows.Media.ImageDrawing>.  
  
 ![100 на 100, нарисованная в ImageDrawing &#40; 75,75 &#41; ] (../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing размером 100 на 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Дополнительную информацию об изображениях см. в разделе [Общие сведения об изображениях](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Воспроизведение мультимедиа (только код)  
  
> [!NOTE]
>  Несмотря на то, что можно объявить <xref:System.Windows.Media.VideoDrawing> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], вы можете только загрузки и воспроизвести его мультимедиа с помощью кода. Чтобы воспроизвести видео в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], используйте <xref:System.Windows.Controls.MediaElement> вместо него.  
  
 Чтобы воспроизведение звука и видео, используйте <xref:System.Windows.Media.VideoDrawing> и <xref:System.Windows.Media.MediaPlayer>. Есть два способа загрузки и воспроизведения мультимедиа. Первый заключается в использовании <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> , а второй способ состоит в создании собственных <xref:System.Windows.Media.MediaTimeline> для использования с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  При распространении мультимедиа с приложением, в отличие от изображений, файл мультимедиа нельзя использовать как ресурс проекта. Вместо этого в файле проекта необходимо выбрать тип мультимедиа `Content` и задать для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
 Для воспроизведения файлов мультимедиа, не создавая собственной <xref:System.Windows.Media.MediaTimeline>, выполните следующие действия.  
  
1.  Создание объекта <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2.  Используйте <xref:System.Windows.Media.MediaPlayer.Open%2A> метод, чтобы загрузить файл мультимедиа.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3.  Создайте таблицу <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4.  Укажите размер и расположение для отображения мультимедиа, задав <xref:System.Windows.Media.VideoDrawing.Rect%2A> свойство <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5.  Задать <xref:System.Windows.Media.VideoDrawing.Player%2A> свойство <xref:System.Windows.Media.VideoDrawing> с <xref:System.Windows.Media.MediaPlayer> был создан.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6.  Используйте <xref:System.Windows.Media.MediaPlayer.Play%2A> метод <xref:System.Windows.Media.MediaPlayer> начала воспроизведения мультимедиа.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 В следующем примере используется <xref:System.Windows.Media.VideoDrawing> и <xref:System.Windows.Media.MediaPlayer> для воспроизведения видео файл один раз.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Чтобы получить дополнительное управление временем для мультимедиа, используйте <xref:System.Windows.Media.MediaTimeline> с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> объектов. <xref:System.Windows.Media.MediaTimeline> Позволяет указать, следует ли повторять видео. Для использования <xref:System.Windows.Media.MediaTimeline> с <xref:System.Windows.Media.VideoDrawing>, выполните следующие действия:  
  
1.  Объявите <xref:System.Windows.Media.MediaTimeline> и задайте ее временные характеристики.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2.  Создание <xref:System.Windows.Media.MediaClock> из <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3.  Создание <xref:System.Windows.Media.MediaPlayer> и использовать <xref:System.Windows.Media.MediaClock> для задания его <xref:System.Windows.Media.MediaPlayer.Clock%2A> свойство.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4.  Создание <xref:System.Windows.Media.VideoDrawing> и назначить <xref:System.Windows.Media.MediaPlayer> для <xref:System.Windows.Media.VideoDrawing.Player%2A> свойство <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 В следующем примере используется <xref:System.Windows.Media.MediaTimeline> с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> для воспроизведения видео.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Обратите внимание, что при использовании <xref:System.Windows.Media.MediaTimeline>, используется интерактивный <xref:System.Windows.Media.Animation.ClockController> , возвращенные <xref:System.Windows.Media.Animation.Clock.Controller%2A> свойство <xref:System.Windows.Media.MediaClock> управления воспроизведением мультимедиа, вместо интерактивных методов <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Рисование текста  
 Для рисования текста, используйте <xref:System.Windows.Media.GlyphRunDrawing> и <xref:System.Windows.Media.GlyphRun>. В следующем примере используется <xref:System.Windows.Media.GlyphRunDrawing> для рисования текста «Hello World».  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Объект <xref:System.Windows.Media.GlyphRun> является низкоуровневым объектом, предназначенным для использования с представлением документа фиксированного формата и скриптами печати. Более простой способ рисования текста на экран является использование <xref:System.Windows.Controls.Label> или <xref:System.Windows.Controls.TextBlock>. Дополнительные сведения о <xref:System.Windows.Media.GlyphRun>, в разделе [введение в объект GlyphRun и глифы элемент](../../../../docs/framework/wpf/advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) Обзор.  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Составные рисунки  
 Объект <xref:System.Windows.Media.DrawingGroup> позволяет объединить несколько рисунков в один составной рисунок. С помощью <xref:System.Windows.Media.DrawingGroup>, текст, изображения и фигуры можно объединить в один <xref:System.Windows.Media.Drawing> объекта.  
  
 В следующем примере используется <xref:System.Windows.Media.DrawingGroup> сочетание двух <xref:System.Windows.Media.GeometryDrawing> объектов и <xref:System.Windows.Media.ImageDrawing> объекта. В этом примере формируются следующие данные:  
  
 ![DrawingGroup с множественными отрисовками](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")  
Составной рисунок  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Объект <xref:System.Windows.Media.DrawingGroup> также позволяет применять маски непрозрачности, преобразования, эффекты растрового изображения и другие операции к его содержимому. <xref:System.Windows.Media.DrawingGroup>операции, применяются в следующем порядке: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>, а затем <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Ниже показан порядок, в котором <xref:System.Windows.Media.DrawingGroup> применяются операции.  
  
 ![Порядок DrawingGroup для операций](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Порядок операций для DrawingGroup  
  
 В следующей таблице описаны свойства, можно использовать для управления <xref:System.Windows.Media.DrawingGroup> содержимое объекта.  
  
|Свойство.|Описание:|Рисунки|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Изменяет непрозрачность отдельные фрагменты <xref:System.Windows.Media.DrawingGroup> содержимое. Пример см. в разделе [Практическое руководство. Управление прозрачностью рисунка](http://msdn.microsoft.com/en-us/68580652-7d32-4d27-93cc-a5148cf4d5ee).|![DrawingGroup с маской непрозрачности ](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Однородно изменяет непрозрачность <xref:System.Windows.Media.DrawingGroup> содержимое. Это свойство используется, чтобы сделать <xref:System.Windows.Media.Drawing> прозрачным или полупрозрачным. Пример см. в разделе [Практическое руководство. Применение маски непрозрачности к рисунку](http://msdn.microsoft.com/en-us/d77b420b-9be2-479c-a45e-82f4da30eb9f).|![DrawingGroups с различными параметрами прозрачности ](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Применяет <xref:System.Windows.Media.Effects.BitmapEffect> для <xref:System.Windows.Media.DrawingGroup> содержимое. Пример см. в разделе [Практическое руководство. Применение BitmapEffect к рисунку](http://msdn.microsoft.com/en-us/c5b1de83-8d09-47fb-96db-5f174471f4b5).|![DrawingGroup с BlurBitmapEffect](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Отсекает <xref:System.Windows.Media.DrawingGroup> содержимое области, заданной с помощью <xref:System.Windows.Media.Geometry>. Пример см. в разделе [Практическое руководство. Обрезка рисунка](http://msdn.microsoft.com/en-us/1f7d8a2c-c3c2-42cb-a542-e6796f9fb058) .|![DrawingGroup с определенной областью обрезки ](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Привязывает аппаратно-независимые пиксели к пикселям устройства, следуя указанным правилам. Это свойство полезно для обеспечения резкой отрисовки высокодетализированной графики на дисплеях с низким разрешением. Пример см. в разделе [Применение GuidelineSet к рисунку](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-a-guidelineset-to-a-drawing.md).|![DrawingGroup c GuidelineSet и без него ](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Преобразует <xref:System.Windows.Media.DrawingGroup> содержимое. Пример см. в разделе [Практическое руководство. Применение преобразования к рисунку](http://msdn.microsoft.com/en-us/0d525f2b-682d-4d67-9660-cf46929fbabd).|![Повернутая DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Отображение рисунка в виде изображения  
 Для отображения <xref:System.Windows.Media.Drawing> с <xref:System.Windows.Controls.Image> управления, используйте <xref:System.Windows.Media.DrawingImage> как <xref:System.Windows.Controls.Image> элемента управления <xref:System.Windows.Controls.Image.Source%2A> и задайте <xref:System.Windows.Media.DrawingImage> объекта <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> свойство в документ, который требуется отобразить.  
  
 В следующем примере используется <xref:System.Windows.Media.DrawingImage> и <xref:System.Windows.Controls.Image> управления для отображения <xref:System.Windows.Media.GeometryDrawing>. В этом примере формируются следующие данные:  
  
 ![GeometryDrawing двух эллипсов](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Объект DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Заполнение объекта с помощью рисунка  
 Объект <xref:System.Windows.Media.DrawingBrush> — это тип кисти, которая закрашивает область с графическим объектом. Этот объект можно использовать для закраски практически любого графического объекта с помощью рисунка. <xref:System.Windows.Media.Drawing> Свойство <xref:System.Windows.Media.DrawingBrush> описывает его <xref:System.Windows.Media.DrawingBrush.Drawing%2A>. Для подготовки к просмотру <xref:System.Windows.Media.Drawing> с <xref:System.Windows.Media.DrawingBrush>, добавьте его к кисти с использованием кисти <xref:System.Windows.Media.Drawing> свойство и использование кисти для заливки графических объектов, например, элемент управления или панели.  
  
 В следующих примерах используется <xref:System.Windows.Media.DrawingBrush> для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Rectangle> с шаблоном, созданным из <xref:System.Windows.Media.GeometryDrawing>. В этом примере формируются следующие данные:  
  
 ![Объект Мозаичная DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
GeometryDrawing с DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 <xref:System.Windows.Media.DrawingBrush> Класс предоставляет широкий набор параметров для растягивается и мозаичного заполнения его содержимого. Дополнительные сведения о <xref:System.Windows.Media.DrawingBrush>, в разделе [Рисование с помощью изображения, рисунки и визуальные элементы](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md) Обзор.  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Рисование с помощью объектов Visual  
 Объект <xref:System.Windows.Media.DrawingVisual> — это тип визуальный объект, предназначенный для отображения drawing. Работа непосредственно на визуальном уровне является инструментом для разработчиков, которым требуется построить настраиваемую графическую среду, и не описывается в этом обзоре. Дополнительные сведения см. в разделе [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>Объекты DrawingContext  
 <xref:System.Windows.Media.DrawingContext> Позволяет заполнять <xref:System.Windows.Media.Visual> или <xref:System.Windows.Media.Drawing> визуальное содержимое. Использовать многие такие объекты более низкого уровня графики <xref:System.Windows.Media.DrawingContext> , так как он очень эффективно описывает графическое содержимое.  
  
 Несмотря на то что <xref:System.Windows.Media.DrawingContext> методы рисования выглядеть методы рисования <xref:System.Drawing.Graphics?displayProperty=nameWithType> типа, они фактически сильно отличаются. <xref:System.Windows.Media.DrawingContext>— используется с сохраненного режима графической системы, а <xref:System.Drawing.Graphics?displayProperty=nameWithType> тип используется в режиме интерпретации система графики. При использовании <xref:System.Windows.Media.DrawingContext> команд рисования объекта, фактически хранится набор инструкций отрисовки (хотя точный механизм хранения зависит от типа объекта, предоставляющего <xref:System.Windows.Media.DrawingContext>), будет использоваться позже по графику системы; Рисование не выполняется на экране в режиме реального времени. Дополнительную информацию о том, как работает графическая система [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)], см. в разделе [Общие сведения об отрисовке графики WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 Вы нельзя непосредственно создать экземпляр <xref:System.Windows.Media.DrawingContext>; тем не менее, можно получить контекст рисования из определенных методов, таких как <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> и <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Перечисление содержимого визуального элемента  
 В дополнение к другим применениям <xref:System.Windows.Media.Drawing> объектов также предоставляют объектную модель для перечисления содержимого <xref:System.Windows.Media.Visual>.  
  
 В следующем примере используется <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> метод для извлечения <xref:System.Windows.Media.DrawingGroup> значение <xref:System.Windows.Media.Visual> и его перечисления.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 [Двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Заполнение с использованием изображений, рисунков и визуальных элементов](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/drawings-how-to-topics.md)
