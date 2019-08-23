---
title: Рисование с помощью объектов Image, Drawing и Visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- painting [WPF], with images
- painting with visuals [WPF]
- brushes [WPF], painting with images
- brushes [WPF], painting with visuals
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
ms.openlocfilehash: e80132a5467f932e5569787f43427044ba2be256
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929606"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Рисование с помощью объектов Image, Drawing и Visual
В <xref:System.Windows.Media.ImageBrush>этом разделе описывается использование объектов, <xref:System.Windows.Media.DrawingBrush>и <xref:System.Windows.Media.VisualBrush> для <xref:System.Windows.Media.Drawing>закрашивания области <xref:System.Windows.Media.Visual>с изображением, или.  

<a name="prereqs"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Для понимания этого раздела необходимо ознакомиться с различными типами кистей, имеющихся в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], и их основными возможностями. Общие сведения см. в разделе [Общие сведения о кистях WPF](wpf-brushes-overview.md).  
  
<a name="image"></a>   
## <a name="paint-an-area-with-an-image"></a>Закрашивание области с помощью Image  
 <xref:System.Windows.Media.ImageBrush> Закрашивает область с помощью <xref:System.Windows.Media.ImageSource>. Наиболее распространенный тип <xref:System.Windows.Media.ImageSource> для использования <xref:System.Windows.Media.ImageBrush> с параметром — <xref:System.Windows.Media.Imaging.BitmapImage>, который описывает точечный рисунок. Можно использовать <xref:System.Windows.Media.DrawingImage> для рисования <xref:System.Windows.Media.Drawing> с помощью объекта, но проще использовать <xref:System.Windows.Media.DrawingBrush> вместо него. Дополнительные сведения об объектах <xref:System.Windows.Media.ImageSource> см. в разделе [Общие сведения](imaging-overview.md)о работе с образами.  
  
 Чтобы закрасить <xref:System.Windows.Media.ImageBrush>с помощью, <xref:System.Windows.Media.Imaging.BitmapImage> создайте и используйте его для загрузки содержимого растрового изображения. Затем используйте <xref:System.Windows.Media.Imaging.BitmapImage> для <xref:System.Windows.Media.ImageBrush.ImageSource%2A> задания свойства объекта <xref:System.Windows.Media.ImageBrush>. Наконец, примените <xref:System.Windows.Media.ImageBrush> к объекту, который требуется закрасить.  В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]можно также просто <xref:System.Windows.Media.ImageBrush.ImageSource%2A> задать для свойства объекта <xref:System.Windows.Media.ImageBrush> путь к загружаемому изображению.  
  
 Как и <xref:System.Windows.Media.Brush> все объекты <xref:System.Windows.Media.ImageBrush> , можно использовать для рисования объектов, таких как фигуры, панели, элементы управления и текст. На следующем рисунке показаны некоторые эффекты, которые можно достичь с помощью <xref:System.Windows.Media.ImageBrush>.  
  
 ![Примеры выходных данных ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Объекты, заполненные при помощи ImageBrush  
  
 По умолчанию <xref:System.Windows.Media.ImageBrush> растягивает изображение, чтобы полностью заполнить закрашиваемую область, возможно, искажение изображения, если окрашенная область имеет разную пропорцию изображения. Это поведение можно <xref:System.Windows.Media.TileBrush.Stretch%2A> изменить, изменив свойство со <xref:System.Windows.Media.Stretch.Fill> значения по умолчанию на <xref:System.Windows.Media.Stretch.None>, <xref:System.Windows.Media.Stretch.Uniform>или <xref:System.Windows.Media.Stretch.UniformToFill>. Поскольку <xref:System.Windows.Media.ImageBrush> является<xref:System.Windows.Media.TileBrush>типом, можно точно указать, как кисть изображения заполняет область вывода и даже создает закономерности. Дополнительные сведения о дополнительных <xref:System.Windows.Media.TileBrush> функциях см. в [обзоре TileBrush](tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>   
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Пример Закрашивание объекта с помощью растрового изображения  
 В следующем примере используется <xref:System.Windows.Media.ImageBrush> для <xref:System.Windows.Controls.Panel.Background%2A> рисования объекта <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## <a name="paint-an-area-with-a-drawing"></a>Закрашивание области с помощью Drawing  
 <xref:System.Windows.Media.DrawingBrush> Позволяет закрасить область с фигурами, текстом, изображениями и видео. Фигуры внутри кисти рисования могут быть окрашены сплошным цветом, градиентом, изображением или даже другим <xref:System.Windows.Media.DrawingBrush>. На следующем рисунке показаны некоторые способы использования <xref:System.Windows.Media.DrawingBrush>.  
  
 ![Примеры выходных данных DrawingBrush](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Объекты, заполненные при помощи DrawingBrush  
  
 <xref:System.Windows.Media.DrawingBrush> Рисует область<xref:System.Windows.Media.Drawing> с объектом. <xref:System.Windows.Media.Drawing> Объект описывает видимое содержимое, например фигуру, Растровое изображение, видео или строку текста. Различные типы рисунков описывают различные типы содержимого. Ниже приведен список различных типов объектов-рисунков.  
  
- <xref:System.Windows.Media.GeometryDrawing>— Рисует фигуру.  
  
- <xref:System.Windows.Media.ImageDrawing>— Рисует изображение.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>— Рисует текст.  
  
- <xref:System.Windows.Media.VideoDrawing>— Воспроизводит звуковой файл или видеофайл.  
  
- <xref:System.Windows.Media.DrawingGroup>— Рисует другие рисунки. Для объединения рисунков в один составной используйте группирование рисунков.  
  
 Дополнительные сведения об <xref:System.Windows.Media.Drawing> объектах см. в разделе [Общие сведения о объектах Drawing](drawing-objects-overview.md).  
  
 Как и <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush> , перетягивает его <xref:System.Windows.Media.DrawingBrush.Drawing%2A> в область вывода. Это поведение можно переопределить, изменив <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство на значение по умолчанию. <xref:System.Windows.Media.Stretch.Fill> Дополнительные сведения см. в описании свойства <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## <a name="example-paint-an-object-with-a-drawing"></a>Пример Заполнение объекта с помощью рисунка  
 В следующем примере показано, как можно заполнить объект с помощью рисунка с изображением трех эллипсов. <xref:System.Windows.Media.GeometryDrawing> Для описания эллипсов используется.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## <a name="paint-an-area-with-a-visual"></a>Закрашивание области с помощью Visual  
 Наиболее универсальная и мощная из всех кистей <xref:System.Windows.Media.VisualBrush> закрашивает область с помощью. <xref:System.Windows.Media.Visual> <xref:System.Windows.Media.Visual> — Это графический тип нижнего уровня, служащий предком многих полезных графических компонентов. Например, <xref:System.Windows.Window>классы, <xref:System.Windows.FrameworkElement>и <xref:System.Windows.Controls.Control> являются типами <xref:System.Windows.Media.Visual> объектов. С помощью можно закрасить области практически в любой [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] графический объект. <xref:System.Windows.Media.VisualBrush>  
  
> [!NOTE]
> Хотя <xref:System.Windows.Media.VisualBrush> является <xref:System.Windows.Media.VisualBrush.Visual%2A> `null`типом объекта, он не может быть заморожен (доступен только для чтения), если его свойство имеет значение, отличное от. <xref:System.Windows.Freezable>  
  
 Существует два способа указания <xref:System.Windows.Media.VisualBrush.Visual%2A> содержимого. <xref:System.Windows.Media.VisualBrush>  
  
- Создайте новый <xref:System.Windows.Media.Visual> и используйте его для <xref:System.Windows.Media.VisualBrush.Visual%2A> задания свойства объекта <xref:System.Windows.Media.VisualBrush>. Пример см. в [примере: Закрасьте объект с помощью визуального](#examplevisualbrush1) раздела, приведенного ниже.  
  
- Используйте существующий <xref:System.Windows.Media.Visual>, который создает дубликат изображения целевого объекта <xref:System.Windows.Media.Visual>. Затем можно использовать <xref:System.Windows.Media.VisualBrush> для создания интересных эффектов, таких как отражение и увеличение. Пример см. в [примере: Создание раздела отражения](#examplevisualbrush2) .  
  
 <xref:System.Windows.Media.VisualBrush.Visual%2A> При определении нового <xref:System.Windows.Media.VisualBrush> для и, который <xref:System.Windows.Media.Visual> является <xref:System.Windows.UIElement> (например, <xref:System.Windows.UIElement> панелью или элементом управления), система <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> макета выполняется в и ее дочерних элементах, если свойство имеет значение `true`. Однако корень <xref:System.Windows.UIElement> по сути изолирован от остальной части системы: стили и внешний макет не перейти эту границу. Поэтому следует явно указать размер корня <xref:System.Windows.UIElement>, так как его единственный родительский элемент <xref:System.Windows.Media.VisualBrush> — и, поэтому он не может автоматически масштабироваться до закрашиваемой области. Дополнительные сведения о макете в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] см. в разделе [Макет](../advanced/layout.md).  
  
 Как <xref:System.Windows.Media.ImageBrush> и <xref:System.Windows.Media.DrawingBrush> ,<xref:System.Windows.Media.VisualBrush> перетягивание содержимого для заполнения области вывода. Это поведение можно переопределить, изменив <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство на значение по умолчанию. <xref:System.Windows.Media.Stretch.Fill> Дополнительные сведения см. в описании свойства <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="examplevisualbrush1"></a>   
## <a name="example-paint-an-object-with-a-visual"></a>Пример Закрашивание объекта с помощью визуального элемента  
 В следующем примере несколько элементов управления и панель используются для заполнения прямоугольника.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## <a name="example-create-a-reflection"></a>Пример Создание отражения  
 В предыдущем примере показано, как создать новый <xref:System.Windows.Media.Visual> для использования в качестве фона. Можно также использовать <xref:System.Windows.Media.VisualBrush> для отображения существующего визуального элемента. Эта возможность позволяет создавать интересные визуальные эффекты, такие как отражение и увеличение. В следующем примере для создания <xref:System.Windows.Media.VisualBrush> отражения <xref:System.Windows.Controls.Border> , содержащего несколько элементов, используется объект. На следующей иллюстрации показан результат выполнения этого примера.  
  
 ![Отраженный визуальный объект](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Отраженный объект Visual  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Дополнительные примеры, демонстрирующие увеличение частей экрана и создание отражений, см. в разделе [Пример VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).  
  
<a name="tilebrush"></a>   
## <a name="tilebrush-features"></a>Функции TileBrush  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>и <xref:System.Windows.Media.VisualBrush> являются типами<xref:System.Windows.Media.TileBrush> объектов. <xref:System.Windows.Media.TileBrush>объекты предоставляют большой контроль над тем, как зарисовывается область с изображением, рисованием или визуальным элементом. Например, можно заполнить область не одним растянутым изображением, а элементами мозаики, которые образуют узор.  
  
 <xref:System.Windows.Media.TileBrush> Имеет три основных компонента: содержимое, плитки и область вывода.  
  
 ![Компоненты TileBrush](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Компоненты TileBrush с одним элементом мозаики  
  
 ![Компоненты мозаичного TileBrush](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Компоненты TileBrush с несколькими элементами мозаики  
  
 Дополнительные сведения о функциях <xref:System.Windows.Media.TileBrush> мозаичного заполнения объектов см. в [обзоре TileBrush](tilebrush-overview.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Общие сведения об объекте TileBrush](tilebrush-overview.md)
- [Общие сведения о кистях WPF](wpf-brushes-overview.md)
- [Общие сведения об обработке изображений](imaging-overview.md)
- [Обзор объектов Drawing](drawing-objects-overview.md)
- [Общие сведения о масках непрозрачности](opacity-masks-overview.md)
- [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md)
- [Пример ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [Пример использования VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049)
