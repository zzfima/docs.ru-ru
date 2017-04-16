---
title: "Рисование с помощью объектов Image, Drawing и Visual | Microsoft Docs"
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
  - "кисти, рисование с помощью рисунков"
  - "кисти, рисование с помощью изображений"
  - "кисти, рисование с помощью визуальных элементов"
  - "рисование с помощью визуальных элементов"
  - "рисование, с помощью рисунков"
  - "рисование, с помощью изображений"
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# Рисование с помощью объектов Image, Drawing и Visual
В этом разделе описывается использование объектов <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush> для рисования в области с помощью изображения, <xref:System.Windows.Media.Drawing> или <xref:System.Windows.Media.Visual>.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prereqs"></a>   
## Предварительные требования  
 Чтобы разобраться в этом разделе, необходимо ознакомиться с различными типами кистей, предоставляемых [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], и их основными функциями.  Общие сведения см. в разделе [Общие сведения о кистях WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  
  
<a name="image"></a>   
## Закрашивание области с помощью Image  
 <xref:System.Windows.Media.ImageBrush> закрашивает область с помощью <xref:System.Windows.Media.ImageSource>.  Наиболее распространенным типом <xref:System.Windows.Media.ImageSource> для использования с <xref:System.Windows.Media.ImageBrush> является <xref:System.Windows.Media.Imaging.BitmapImage>, который описывает растровую графику.  Можно использовать <xref:System.Windows.Media.DrawingImage> для рисования с помощью объекта <xref:System.Windows.Media.Drawing>, но проще воспользоваться <xref:System.Windows.Media.DrawingBrush>.  Дополнительные сведения об объектах <xref:System.Windows.Media.ImageSource> см. в разделе [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
 Для рисования с помощью <xref:System.Windows.Media.ImageBrush>, создайте <xref:System.Windows.Media.Imaging.BitmapImage> и используйте его для загрузки растрового содержимого.  Затем используйте <xref:System.Windows.Media.Imaging.BitmapImage>, чтобы задать свойство <xref:System.Windows.Media.ImageBrush.ImageSource%2A> для <xref:System.Windows.Media.ImageBrush>.  Наконец, примените <xref:System.Windows.Media.ImageBrush> к объекту рисования.  В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] можно просто задать путь к загружаемому изображению в свойстве <xref:System.Windows.Media.ImageBrush.ImageSource%2A> для <xref:System.Windows.Media.ImageBrush>.  
  
 Как и все объекты <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.ImageBrush> можно использовать для рисования таких объектов, как фигуры, панели, элементы управления и текст.  На следующем рисунке показаны некоторые эффекты, которых можно добиться с помощью <xref:System.Windows.Media.ImageBrush>.  
  
 ![Примеры вывода ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-imagebrushexamples.png "wcpsdk\_mmgraphics\_imagebrushexamples")  
Объекты, нарисованные с помощью ImageBrush  
  
 По умолчанию <xref:System.Windows.Media.ImageBrush> растягивает изображения до полного заполнения закрашиваемой области и может искажать изображение, если закрашиваемая область имеет отличные от изображения пропорции.  Такое поведение можно изменить путем изменения в свойстве <xref:System.Windows.Media.TileBrush.Stretch%2A> значения по умолчанию <xref:System.Windows.Media.Stretch> на <xref:System.Windows.Media.Stretch>, <xref:System.Windows.Media.Stretch> или <xref:System.Windows.Media.Stretch>.  Поскольку <xref:System.Windows.Media.ImageBrush> является типом <xref:System.Windows.Media.TileBrush>, можно точно указать, как кисть растровых изображений должна заполнять выходную область, и даже создавать шаблоны.  Сведения о дополнительных возможностях <xref:System.Windows.Media.TileBrush> см. в разделе [Общие сведения о TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>   
## Пример: закрашивание объекта с помощью точечного рисунка  
 В следующем примере используется <xref:System.Windows.Media.ImageBrush> для закрашивания <xref:System.Windows.Controls.Panel.Background%2A> объекта <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## Закрашивание области с помощью Drawing  
 <xref:System.Windows.Media.DrawingBrush> позволяет заполнять область фигурами, текстом, изображениями и видео.  Фигуры внутри кисти векторных изображений могут сами заполнять себя сплошным цветом, градиентном, изображением или даже другим <xref:System.Windows.Media.DrawingBrush>.  На следующем рисунке демонстрируются некоторые способы использования <xref:System.Windows.Media.DrawingBrush>.  
  
 ![Примеры вывода DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk\_mmgraphics\_drawingbrushexamples")  
Объекты, закрашенные с помощью DrawingBrush  
  
 <xref:System.Windows.Media.DrawingBrush> закрашивает область с помощью объекта <xref:System.Windows.Media.Drawing>.  Объект <xref:System.Windows.Media.Drawing> описывает отображаемое содержимое, такое как фигура, точечный рисунок, видео или строка текста.  Различные типы графических объектов описывают различные типы содержимого.  Ниже приведен список различных типов графических объектов.  
  
-   <xref:System.Windows.Media.GeometryDrawing> — выводит фигуру.  
  
-   <xref:System.Windows.Media.ImageDrawing> — выводит изображение.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> — выводит текст.  
  
-   <xref:System.Windows.Media.VideoDrawing> — воспроизводит аудио\- или видеофайл.  
  
-   <xref:System.Windows.Media.DrawingGroup> — выводит другие объекты Drawing.  Используйте группирование объектов Drawing для объединения объектов Drawing в один составной объект Drawing.  
  
 Дополнительные сведения об объектах <xref:System.Windows.Media.Drawing> см. в разделе [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
 Подобно <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> растягивает его <xref:System.Windows.Media.DrawingBrush.Drawing%2A> до заполнения выходной области.  Можно переопределить это поведение путем изменения свойства <xref:System.Windows.Media.TileBrush.Stretch%2A> из значения по умолчанию <xref:System.Windows.Media.Stretch>.  Дополнительные сведения см. в описании свойства <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## Пример: закрашивание объекта с помощью Drawing  
 В следующем примере показано закрашивание объекта тремя эллипсами.  <xref:System.Windows.Media.GeometryDrawing> используется для описания эллипсов.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## Закрашивание области с помощью Visual  
 Наиболее гибкая и мощная из всех кистей, <xref:System.Windows.Media.VisualBrush>, закрашивает область с помощью <xref:System.Windows.Media.Visual>.  <xref:System.Windows.Media.Visual> является графическим типом нижнего уровня, который служит в качестве предка многих полезных графических компонентов.  Например, классы <xref:System.Windows.Window>, <xref:System.Windows.FrameworkElement> и <xref:System.Windows.Controls.Control> представляют все типы объектов <xref:System.Windows.Media.Visual>.  Используя <xref:System.Windows.Media.VisualBrush>, можно закрашивать области практически любыми графическими объектами [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
> [!NOTE]
>  Хотя <xref:System.Windows.Media.VisualBrush> является типом объекта <xref:System.Windows.Freezable>, он не может быть заморожен \(сделан доступным только для чтения\), когда для его свойства <xref:System.Windows.Media.VisualBrush.Visual%2A> задано значение, отличное от `null`.  
  
 Существует два способа указать содержимое <xref:System.Windows.Media.VisualBrush.Visual%2A> для <xref:System.Windows.Media.VisualBrush>.  
  
-   Создайте новый <xref:System.Windows.Media.Visual> и используйте его, чтобы задать свойство <xref:System.Windows.Media.VisualBrush.Visual%2A> для <xref:System.Windows.Media.VisualBrush>.  Пример см. ниже в разделе [Пример: закрашивание объекта с помощью Visual](#examplevisualbrush1).  
  
-   Используйте существующий <xref:System.Windows.Media.Visual>, который создает дубликат изображения целевого <xref:System.Windows.Media.Visual>.  Затем можно воспользоваться <xref:System.Windows.Media.VisualBrush> для создания интересных эффектов, таких как отражение и увеличение.  Пример см. в разделе [Пример: создание отражения](#examplevisualbrush2).  
  
 В случае определения нового <xref:System.Windows.Media.VisualBrush.Visual%2A> для <xref:System.Windows.Media.VisualBrush>, если этот <xref:System.Windows.Media.Visual> представляет собой <xref:System.Windows.UIElement> \(такой как панель или элемент управления\), система макета выполняется для <xref:System.Windows.UIElement> и его дочерних элементов при заданном для свойства <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> значении `true`.  Однако корневой <xref:System.Windows.UIElement> по существу изолирован от остальной системы: стили и внешний макет не могут переходить эту границу.  В связи с этим следует явно указать размер корневого <xref:System.Windows.UIElement>, поскольку его единственным родительским объектом является <xref:System.Windows.Media.VisualBrush>, из\-за чего его размер не может быть автоматически подобран по размеру закрашиваемой области.  Дополнительные сведения о макете в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] см. в разделе [Макет](../../../../docs/framework/wpf/advanced/layout.md).  
  
 Подобно <xref:System.Windows.Media.ImageBrush> и <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush> растягивает свое содержимое до заполнения выходной области.  Можно переопределить это поведение путем изменения свойства <xref:System.Windows.Media.TileBrush.Stretch%2A> из значения по умолчанию <xref:System.Windows.Media.Stretch>.  Дополнительные сведения см. в описании свойства <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="examplevisualbrush1"></a>   
## Пример: закрашивание объекта с помощью Visual  
 В следующем примере несколько элементов управления и панель используются для закрашивания прямоугольника.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## Пример: создание отражения  
 В предыдущем примере показано, как создать новый объект <xref:System.Windows.Media.Visual> для использования в качестве фона.  Также можно использовать <xref:System.Windows.Media.VisualBrush> для отображения существующего объекта Visual; это позволяет создавать интересные визуальные эффекты, такие как отражение и увеличение.  В следующем примере <xref:System.Windows.Media.VisualBrush> используется для создания отражения <xref:System.Windows.Controls.Border>, содержащего несколько элементов.  На следующем рисунке показан результат данного примера.  
  
 ![Отраженный объект Visual](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.png "graphicsmm\_visualbrush\_reflection\_small")  
Отраженный объект Visual  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Дополнительные примеры к практическому руководству по увеличению частей экрана и созданию отражений см. в разделе [Пример VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049).  
  
<a name="tilebrush"></a>   
## Функциональные возможности TileBrush  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush> являются типами объектов <xref:System.Windows.Media.TileBrush>.  Объекты <xref:System.Windows.Media.TileBrush> предоставляют большое множество способов контролировать закрашивание области с помощью изображения, рисунка или визуального объекта.  Например, вместо простой закраски области одним растянутым изображением, можно закрасить область с помощью множества фрагментов изображения, создающих узор.  
  
 A <xref:System.Windows.Media.TileBrush> имеет три основных компонента: содержимое, базовый фрагмент и область вывода.  
  
 ![Компоненты TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk\_mmgraphics\_defaultcontentprojection2")  
Компоненты TileBrush с одним фрагментом  
  
 ![Компоненты мозаичного TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "graphicsmm\_tiledprojection")  
Компоненты TileBrush с несколькими фрагментами  
  
 Дополнительные сведения о возможностях мозаичного заполнения области объектами <xref:System.Windows.Media.TileBrush> см. в разделе [Общие сведения о TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md).  
  
## См. также  
 <xref:System.Windows.Media.ImageBrush>   
 <xref:System.Windows.Media.DrawingBrush>   
 <xref:System.Windows.Media.VisualBrush>   
 <xref:System.Windows.Media.TileBrush>   
 [Общие сведения о TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)   
 [Общие сведения о кистях WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)   
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Общие сведения о масках непрозрачности](../../../../docs/framework/wpf/graphics-multimedia/opacity-masks-overview.md)   
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005)   
 [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049)