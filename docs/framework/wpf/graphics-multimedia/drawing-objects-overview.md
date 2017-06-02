---
title: "Обзор объектов Drawing | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Drawing - объекты"
  - "DrawingGroup - объекты"
  - "объекты рисования, сведения о рисовании"
  - "GeometryDrawing - объекты"
  - "GlyphRunDrawing - объекты"
  - "ImageDrawing - объекты"
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Обзор объектов Drawing
В этом разделе представлены объекты <xref:System.Windows.Media.Drawing> и инструкции по их использованию для эффективного рисования фигур, точечных рисунков, текста и мультимедиа.  Используйте объекты <xref:System.Windows.Media.Drawing> при создании картинок, рисования при помощи <xref:System.Windows.Media.DrawingBrush> или использовании объектов <xref:System.Windows.Media.Visual>.  
  
   
  
<a name="whatisadrawingsection"></a>   
## Понятие объекта Drawing  
 Объект <xref:System.Windows.Media.Drawing> описывает отображаемое содержимое, такое как фигура, точечный рисунок, видео или строка текста.  Различные типы графических объектов описывают различные типы содержимого.  Ниже приведен список различных типов графических объектов.  
  
-   <xref:System.Windows.Media.GeometryDrawing> — выводит фигуру.  
  
-   <xref:System.Windows.Media.ImageDrawing> — выводит изображение.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> — выводит текст.  
  
-   <xref:System.Windows.Media.VideoDrawing> — воспроизводит аудио\- или видеофайл.  
  
-   <xref:System.Windows.Media.DrawingGroup> — выводит другие объекты Drawing.  Используйте группирование объектов Drawing для объединения объектов Drawing в один составной объект Drawing.  
  
 Объекты <xref:System.Windows.Media.Drawing> являются универсальными. Существует множество способов использования объекта <xref:System.Windows.Media.Drawing>.  
  
-   Можно отобразить его в виде изображения с помощью <xref:System.Windows.Media.DrawingImage> и элемента управления <xref:System.Windows.Controls.Image>.  
  
-   Можно использовать его с <xref:System.Windows.Media.DrawingBrush> для рисования объекта, например, <xref:System.Windows.Controls.Page.Background%2A> для <xref:System.Windows.Controls.Page>.  
  
-   Можно использовать его для описания внешнего вида <xref:System.Windows.Media.DrawingVisual>.  
  
-   Можно использовать его для перечисления содержимого <xref:System.Windows.Media.Visual>.  
  
 WPF предоставляет другие типы объектов, способных рисовать фигуры, точечные рисунки, текст и мультимедиа.  Например, можно также использовать объекты <xref:System.Windows.Shapes.Shape> для рисования фигур, и элемент управления <xref:System.Windows.Controls.MediaElement> предоставляет другой способ добавления видео в приложение.  В каких случаях следует использовать объекты <xref:System.Windows.Media.Drawing>?  Когда можно посвятить возможности уровня среды получению выигрыша в производительности или при необходимости в возможностях <xref:System.Windows.Freezable>.  Поскольку объекты <xref:System.Windows.Media.Drawing> не поддерживают ввод [Макет](../../../../docs/framework/wpf/advanced/layout.md) и фокусировку, они обеспечивают выигрыш в производительности, что делает их идеальным средством описания фоновых рисунков, картинок и низкоуровневых рисунков с объектами <xref:System.Windows.Media.Visual>.  
  
 Поскольку они являются объектами типа <xref:System.Windows.Freezable>, объекты <xref:System.Windows.Media.Drawing> приобретают несколько особых возможностей, к которым относятся следующие: они могут быть объявлены как [ресурсы](../../../../docs/framework/wpf/advanced/xaml-resources.md), которые совместно используются несколькими объектами, сделаны предназначенными только для чтения в целях повышения быстродействия, копированы, а также сделаны безопасными для использования в многопоточных программах.  Дополнительные сведения о различных возможностях, предоставляемых объектами класса <xref:System.Windows.Freezable>, см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## Рисование фигуры  
 Чтобы нарисовать фигуру, используется объект <xref:System.Windows.Media.GeometryDrawing>.  Его свойство <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> описывает фигуру, которую нужно нарисовать, его свойство <xref:System.Windows.Media.GeometryDrawing.Brush%2A> описывает способ закраски внутренней части фигуры, его свойство <xref:System.Windows.Media.GeometryDrawing.Pen%2A> описывает способ прорисовки его структуры.  
  
 В следующем примере <xref:System.Windows.Media.GeometryDrawing> используется для рисования фигуры.  Фигура описывается <xref:System.Windows.Media.GeometryGroup> и двумя объектами <xref:System.Windows.Media.EllipseGeometry>.  Внутренняя часть фигуры рисуется с помощью <xref:System.Windows.Media.LinearGradientBrush>, а ее контур — с помощью <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.  
  
 В этом примере создается следующий <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing двух эллипсов](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Полный пример см. в разделе [Создание GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-geometrydrawing.md).  
  
 Другие классы <xref:System.Windows.Media.Geometry>, такие как <xref:System.Windows.Media.PathGeometry>, позволяют создавать более сложные фигуры, создавая кривые и дуги.  Дополнительные сведения об объектах <xref:System.Windows.Media.Geometry> см. в разделе [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 Дополнительные сведения о других способах рисования фигур, не использующих объекты <xref:System.Windows.Media.Drawing>, содержатся в разделе [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## Рисование изображения  
 Для рисования изображения используется <xref:System.Windows.Media.ImageDrawing>.  Свойство объекта <xref:System.Windows.Media.ImageDrawing> <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> описывает изображение, которое нужно нарисовать, а его свойство <xref:System.Windows.Media.ImageDrawing.Rect%2A> определяет область, где рисуется изображение.  
  
 В следующем примере изображение рисуется в прямоугольнике, расположенном в точке \(75,75\), размером 100 на 100 [пикселей](GTMT).  На следующем рисунке показан <xref:System.Windows.Media.ImageDrawing>, созданный в примере.  Серая граница была добавлена, чтобы показать границы <xref:System.Windows.Media.ImageDrawing>.  
  
 ![ImageDrawing размером 100 на 100, отрисованный на &#40;75,75&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm\_simple\_imagedrawing\_offset")  
ImageDrawing размером 100 на 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Дополнительные сведения об изображениях см. в разделе [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
<a name="playmedia"></a>   
## Воспроизведение мультимедиа \(только код\)  
  
> [!NOTE]
>  Хотя можно объявить <xref:System.Windows.Media.VideoDrawing> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], можно загрузить и воспроизвести в нем мультимедиа только с помощью кода.  Чтобы воспроизвести видео в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], лучше используйте <xref:System.Windows.Controls.MediaElement>.  
  
 Для воспроизведения аудио\- и видеофайлов следует использовать <xref:System.Windows.Media.VideoDrawing> и <xref:System.Windows.Media.MediaPlayer>.  Существуют два способа загрузки и воспроизведения файлов мультимедиа.  Первый способ заключается в использовании <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing>, а второй — в создании собственных <xref:System.Windows.Media.MediaTimeline> для использования с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  При передаче файлов мультимедиа приложениям файл мультимедиа, в отличие от изображений, нельзя использовать в качестве ресурса проекта.  Вместо этого в файле проекта необходимо задать для типа мультимедиа значение `Content` и для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
 Чтобы воспроизвести мультимедиа, не создавая собственной <xref:System.Windows.Media.MediaTimeline>, выполните следующие действия.  
  
1.  Создайте объект <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2.  Используйте метод <xref:System.Windows.Media.MediaPlayer.Open%2A> для загрузки файла мультимедиа.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3.  Создайте таблицу <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4.  Укажите размер и расположение для отображения мультимедиа, задав свойство <xref:System.Windows.Media.VideoDrawing.Rect%2A> для <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5.  Укажите в свойстве <xref:System.Windows.Media.VideoDrawing.Player%2A> для <xref:System.Windows.Media.VideoDrawing> созданный объект <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6.  Используйте метод <xref:System.Windows.Media.MediaPlayer.Play%2A> созданного <xref:System.Windows.Media.MediaPlayer>, чтобы начать воспроизведение мультимедиа.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 В следующем примере <xref:System.Windows.Media.VideoDrawing> и <xref:System.Windows.Media.MediaPlayer> используются для однократного воспроизведения видеофайла.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Чтобы получить дополнительное управление временем для мультимедиа, используйте <xref:System.Windows.Media.MediaTimeline> с объектами <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing>.  <xref:System.Windows.Media.MediaTimeline> позволяет задать повтор воспроизведения видеофайла.  Чтобы использовать <xref:System.Windows.Media.MediaTimeline> с <xref:System.Windows.Media.VideoDrawing>, выполните следующие действия:  
  
1.  Объявите <xref:System.Windows.Media.MediaTimeline> и задайте ее временные характеристики.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2.  Создайте <xref:System.Windows.Media.MediaClock> из <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3.  Создайте <xref:System.Windows.Media.MediaPlayer> и используйте <xref:System.Windows.Media.MediaClock> для установки его свойства <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4.  Создайте <xref:System.Windows.Media.VideoDrawing> и задайте <xref:System.Windows.Media.MediaPlayer> значение свойства <xref:System.Windows.Media.VideoDrawing.Player%2A> объекта <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 В следующем примере <xref:System.Windows.Media.MediaTimeline> используется с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> для повторяющегося воспроизведения видео.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Обратите внимание, что при использовании <xref:System.Windows.Media.MediaTimeline>, используется интерактивный <xref:System.Windows.Media.Animation.ClockController>, который возвращается свойством <xref:System.Windows.Media.Animation.Clock.Controller%2A> для <xref:System.Windows.Media.MediaClock> и позволяет управлять воспроизведением мультимедиа, вместо интерактивных методов <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## Вывод текста  
 Чтобы вывести текст, используется <xref:System.Windows.Media.GlyphRunDrawing> и <xref:System.Windows.Media.GlyphRun>.  В следующем примере <xref:System.Windows.Media.GlyphRunDrawing> используется для вывода текста "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 <xref:System.Windows.Media.GlyphRun> является низкоуровневым объектом, предназначенным для использования с представлением документа фиксированного формата и скриптами печати.  Более простым способом вывода текста на экран является использование <xref:System.Windows.Controls.Label> или <xref:System.Windows.Controls.TextBlock>.  Дополнительные сведения о <xref:System.Windows.Media.GlyphRun> см. в обзоре [Знакомство с объектом GlyphRun и элементом Glyphs](../../../../docs/framework/wpf/advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md).  
  
<a name="compositedrawingssection"></a>   
## Составные объекты Drawing  
 <xref:System.Windows.Media.DrawingGroup> позволяет объединить несколько рисунков в один составной рисунок.  С помощью <xref:System.Windows.Media.DrawingGroup> можно объединить фигуры, рисунки и текст в один объект <xref:System.Windows.Media.Drawing>.  
  
 В следующем примере <xref:System.Windows.Media.DrawingGroup> используется для объединения двух объектов <xref:System.Windows.Media.GeometryDrawing> и объекта <xref:System.Windows.Media.ImageDrawing>.  В результате выполнения примера получается следующий результат:  
  
 ![DrawingGroup с множественными отрисовками](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.png "graphicsmm\_simple")  
Составной рисунок  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Объект <xref:System.Windows.Media.DrawingGroup> также позволяет принимать маски прозрачности, преобразования, эффекты растрового изображения и другие операции, которые применяются к его содержимому.  Операции <xref:System.Windows.Media.DrawingGroup> применяются в следующем порядке: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> и <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Ниже показан порядок, в котором выполняются операции <xref:System.Windows.Media.DrawingGroup>.  
  
 ![Порядок DrawingGroup для операций](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm\_drawinggroup\_order")  
Порядок операций DrawingGroup  
  
 В следующей таблице описаны свойства, которые можно использовать для обработки содержимого объекта <xref:System.Windows.Media.DrawingGroup>.  
  
|Свойство.|Описание|Иллюстрация|  
|---------------|--------------|-----------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Изменяет непрозрачность выбранной части содержимого <xref:System.Windows.Media.DrawingGroup>.  Пример см. в разделе [How to: Control the Opacity of a Drawing](http://msdn.microsoft.com/ru-ru/68580652-7d32-4d27-93cc-a5148cf4d5ee).||  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Однородно изменяет непрозрачность содержимого <xref:System.Windows.Media.DrawingGroup>.  Это свойство позволяет сделать <xref:System.Windows.Media.Drawing> прозрачным или частично прозрачным.  Пример см. в разделе [How to: Apply an Opacity Mask to a Drawing](http://msdn.microsoft.com/ru-ru/d77b420b-9be2-479c-a45e-82f4da30eb9f).||  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Применяет <xref:System.Windows.Media.Effects.BitmapEffect> к содержимому <xref:System.Windows.Media.DrawingGroup>.  Пример см. в разделе [How to: Apply a BitmapEffect to a Drawing](http://msdn.microsoft.com/ru-ru/c5b1de83-8d09-47fb-96db-5f174471f4b5).||  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Обрезает содержимое <xref:System.Windows.Media.DrawingGroup> вне границ области, заданной с помощью <xref:System.Windows.Media.Geometry>.  Пример см. в разделе [How to: Clip a Drawing](http://msdn.microsoft.com/ru-ru/1f7d8a2c-c3c2-42cb-a542-e6796f9fb058).||  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Привязывает [аппаратно\-независимые пиксели](GTMT) к пикселям устройства, следуя указанным правилам.  Это свойство нужно, чтобы гарантировать, что детализированные графики отображаются резко на дисплеях с низким разрешением.  Пример см. в разделе [Применение GuidelineSet к рисованию](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-a-guidelineset-to-a-drawing.md).||  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Преобразует содержимое <xref:System.Windows.Media.DrawingGroup>.  Пример см. в разделе [How to: Apply a Transform to a Drawing](http://msdn.microsoft.com/ru-ru/0d525f2b-682d-4d67-9660-cf46929fbabd).||  
  
<a name="usingimagedrawing"></a>   
## Отображение объекта Drawing как изображения  
 Чтобы отобразить <xref:System.Windows.Media.Drawing> в элементе управления <xref:System.Windows.Controls.Image>, используйте объект <xref:System.Windows.Media.DrawingImage> элемента управления <xref:System.Windows.Controls.Image> в качестве источника <xref:System.Windows.Controls.Image.Source%2A> и установите для объекта <xref:System.Windows.Media.DrawingImage> свойство <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=fullName> для рисунка, который нужно отобразить.  
  
 В следующем примере используется объект <xref:System.Windows.Media.DrawingImage> и элемент управления <xref:System.Windows.Controls.Image> для отображения объекта <xref:System.Windows.Media.GeometryDrawing>.  В результате выполнения примера получается следующий результат:  
  
 ![GeometryDrawing двух эллипсов](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## Закраска объекта с помощью Drawing  
 <xref:System.Windows.Media.DrawingBrush> представляет собой тип кисти, которая закрашивает область объектом Drawing.  Можно использовать его для закраски практически любого графического объекта рисунком Drawing.  Свойство <xref:System.Windows.Media.Drawing> кисти <xref:System.Windows.Media.DrawingBrush> описывает ее <xref:System.Windows.Media.DrawingBrush.Drawing%2A>.  Для отображения <xref:System.Windows.Media.Drawing> с <xref:System.Windows.Media.DrawingBrush> добавьте его к кисти с помощью свойства кисти <xref:System.Windows.Media.Drawing> и используйте кисть для закраски графического объекта, например, элемента управления или панели.  
  
 В следующих примерах используется <xref:System.Windows.Media.DrawingBrush> для закраски <xref:System.Windows.Shapes.Shape.Fill%2A> фигуры <xref:System.Windows.Shapes.Rectangle> шаблоном, созданным из <xref:System.Windows.Media.GeometryDrawing>.  В результате выполнения примера получается следующий результат:  
  
 ![Мозаичная DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm\_drawingbrush\_geometrydrawing")  
Использование GeometryDrawing с DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 Класс <xref:System.Windows.Media.DrawingBrush> предоставляет ряд параметров для растягивается и мозаичного заполнения его содержимого.  Дополнительные сведения о <xref:System.Windows.Media.DrawingBrush> см. в обзоре [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="renderingwithvisualsection"></a>   
## Отображение Drawing с помощью Visual  
 <xref:System.Windows.Media.DrawingVisual> представляет собой тип объекта Visual, разработанный для отображения Drawing.  Работа непосредственно на уровне Visual является параметром для разработчиков, которым требуется построить настраиваемую графическую среду; это не описано в данном обзоре.  Дополнительные сведения см. в обзоре [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## Объекты DrawingContext  
 Класс <xref:System.Windows.Media.DrawingContext> позволяет заполнить <xref:System.Windows.Media.Visual> или <xref:System.Windows.Media.Drawing> содержимым Visual.  Многие такие низкоуровневые графические объекты используют <xref:System.Windows.Media.DrawingContext>, так как он очень эффективно описывает графическое содержимое.  
  
 Хотя методы рисования <xref:System.Windows.Media.DrawingContext> кажутся похожими на методы рисования типа <xref:System.Drawing.Graphics?displayProperty=fullName>, на самом деле их функционирование значительно отличается.  <xref:System.Windows.Media.DrawingContext> используется с графической системой режима сохранения, тогда как тип <xref:System.Drawing.Graphics?displayProperty=fullName> используется с графической системой режима интерпретации.  При использовании команд рисования объекта <xref:System.Windows.Media.DrawingContext> фактически хранится набор инструкций отрисовки \(хотя точный механизм хранения зависит от типа объекта, предоставляющего объект <xref:System.Windows.Media.DrawingContext>\), который позднее будет использован графической системой; рисование на экране не происходит в режиме реального времени.  Дополнительные сведения о том, как работает графическая система [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)], см. в разделе [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 Нельзя непосредственно создать экземпляр <xref:System.Windows.Media.DrawingContext>; однако можно получить контекст рисования из определенных методов, таких как <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=fullName> и <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=fullName>.  
  
<a name="enumeratevisualcontents"></a>   
## Перечисление содержимого Visual  
 В дополнение к другим применениям, объекты <xref:System.Windows.Media.Drawing> также предоставляют объектную модель для перечисления содержимого объекта <xref:System.Windows.Media.Visual>.  
  
 В следующем примере метод <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> используется для извлечения значения <xref:System.Windows.Media.DrawingGroup> объекта <xref:System.Windows.Media.Visual> и его перечисления.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## См. также  
 <xref:System.Windows.Media.Drawing>   
 <xref:System.Windows.Media.DrawingGroup>   
 [двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/drawings-how-to-topics.md)