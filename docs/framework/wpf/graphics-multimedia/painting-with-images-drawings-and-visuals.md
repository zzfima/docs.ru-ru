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
ms.openlocfilehash: e0e5e386b32425c87502d18a24e758193c14a5b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186924"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Рисование с помощью объектов Image, Drawing и Visual
Эта тема описывает, <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>как <xref:System.Windows.Media.VisualBrush> использовать , и объекты, <xref:System.Windows.Media.Drawing>чтобы нарисовать область с изображением, a , или <xref:System.Windows.Media.Visual>.  

<a name="prereqs"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Для понимания этого раздела необходимо ознакомиться с различными типами кистей, имеющихся в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], и их основными возможностями. Общие сведения см. в разделе [Общие сведения о кистях WPF](wpf-brushes-overview.md).  
  
<a name="image"></a>
## <a name="paint-an-area-with-an-image"></a>Закрашивание области с помощью Image  
 Краска <xref:System.Windows.Media.ImageBrush> области с <xref:System.Windows.Media.ImageSource>. Наиболее распространенный <xref:System.Windows.Media.ImageSource> тип <xref:System.Windows.Media.ImageBrush> использования <xref:System.Windows.Media.Imaging.BitmapImage>с является , который описывает bitmap графических. Вы можете <xref:System.Windows.Media.DrawingImage> использовать для <xref:System.Windows.Media.Drawing> рисования с помощью объекта, но проще использовать <xref:System.Windows.Media.DrawingBrush> вместо него. Для получения <xref:System.Windows.Media.ImageSource> дополнительной информации [Imaging Overview](imaging-overview.md)об объектах см.  
  
 Для рисования <xref:System.Windows.Media.ImageBrush>с <xref:System.Windows.Media.Imaging.BitmapImage> , создать и использовать его для загрузки содержимого биткарты. Затем используйте <xref:System.Windows.Media.Imaging.BitmapImage> для <xref:System.Windows.Media.ImageBrush.ImageSource%2A> установки <xref:System.Windows.Media.ImageBrush>свойства . Наконец, <xref:System.Windows.Media.ImageBrush> нанесите на объект, который вы хотите нарисовать.  В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], вы также <xref:System.Windows.Media.ImageBrush.ImageSource%2A> можете просто <xref:System.Windows.Media.ImageBrush> установить свойство с пути изображения для загрузки.  
  
 Как <xref:System.Windows.Media.Brush> и все <xref:System.Windows.Media.ImageBrush> объекты, можно использовать для покраски таких объектов, как формы, панели, элементы управления и текст. Ниже приведены иллюстрации показаны некоторые <xref:System.Windows.Media.ImageBrush>эффекты, которые могут быть достигнуты с .  
  
 ![Примеры вывода ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Объекты, заполненные при помощи ImageBrush  
  
 По умолчанию, <xref:System.Windows.Media.ImageBrush> растягивает свое изображение, чтобы полностью заполнить область окрашены, возможно, искажая изображение, если окрашенные области имеет другое соотношение сторон, чем изображение. Вы можете изменить это <xref:System.Windows.Media.TileBrush.Stretch%2A> поведение, изменив <xref:System.Windows.Media.Stretch.Fill> <xref:System.Windows.Media.Stretch.None>свойство от его значения по умолчанию до, <xref:System.Windows.Media.Stretch.Uniform>или <xref:System.Windows.Media.Stretch.UniformToFill>. Поскольку <xref:System.Windows.Media.ImageBrush> это <xref:System.Windows.Media.TileBrush>тип, вы можете точно указать, как кисть изображения заполняет область вывода и даже создает шаблоны. Для получения дополнительной <xref:System.Windows.Media.TileBrush> информации о расширенных функциях, см. [TileBrush Overview](tilebrush-overview.md)  
  
<a name="fillingpanelwithimage"></a>
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Пример. Заполнение объекта с помощью точечного рисунка  
 Следующий пример <xref:System.Windows.Media.ImageBrush> использует для <xref:System.Windows.Controls.Panel.Background%2A> рисования <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>
## <a name="paint-an-area-with-a-drawing"></a>Закрашивание области с помощью Drawing  
 A <xref:System.Windows.Media.DrawingBrush> позволяет рисовать область с формами, текстом, изображениями и видео. Формы внутри кисти чертежа могут быть сами окрашены в <xref:System.Windows.Media.DrawingBrush>сплошной цвет, градиент, изображение, или даже другой. Ниже приведена иллюстрация демонстрирует <xref:System.Windows.Media.DrawingBrush>некоторые виды использования .  
  
 ![Примеры вывода DrawingBrush](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Объекты, заполненные при помощи DrawingBrush  
  
 Нарисована <xref:System.Windows.Media.DrawingBrush> область с <xref:System.Windows.Media.Drawing> объектом. Объект <xref:System.Windows.Media.Drawing> описывает видимое содержимое, такое как форма, бит-карта, видео или строка текста. Различные типы рисунков описывают различные типы содержимого. Ниже приведен список различных типов объектов-рисунков.  
  
- <xref:System.Windows.Media.GeometryDrawing>- Рисует форму.  
  
- <xref:System.Windows.Media.ImageDrawing>- Рисует изображение.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>- Рисует текст.  
  
- <xref:System.Windows.Media.VideoDrawing>— Воспроизведение аудио- или видеофайла.  
  
- <xref:System.Windows.Media.DrawingGroup>- Рисует другие рисунки. Для объединения рисунков в один составной рисунок используйте группирование рисунков.  
  
 Для получения <xref:System.Windows.Media.Drawing> дополнительной информации [Drawing Objects Overview](drawing-objects-overview.md)об объектах см.  
  
 Как <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> тянется <xref:System.Windows.Media.DrawingBrush.Drawing%2A> его заполнить свою область вывода. Это поведение можно переопределить, <xref:System.Windows.Media.TileBrush.Stretch%2A> изменив свойство из параметра по <xref:System.Windows.Media.Stretch.Fill>умолчанию. Дополнительные сведения см. в описании свойства <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="fillingareawithdrawingbrushexample"></a>
## <a name="example-paint-an-object-with-a-drawing"></a>Пример. Заполнение объекта с помощью рисунка  
 В следующем примере показано, как можно заполнить объект с помощью рисунка с изображением трех эллипсов. A <xref:System.Windows.Media.GeometryDrawing> используется для описания эллипсов.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>
## <a name="paint-an-area-with-a-visual"></a>Закрашивание области с помощью Visual  
 Самый универсальный и мощный из <xref:System.Windows.Media.VisualBrush> всех кистей, <xref:System.Windows.Media.Visual>краски области с . A <xref:System.Windows.Media.Visual> является низкоуровневым графическим типом, который служит предком многих полезных графических компонентов. Например, <xref:System.Windows.Window>, <xref:System.Windows.FrameworkElement>и <xref:System.Windows.Controls.Control> классы все <xref:System.Windows.Media.Visual> типы объектов. С <xref:System.Windows.Media.VisualBrush>помощью , вы можете [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] покрасить области практически с любым графическим объектом.  
  
> [!NOTE]
> Хотя <xref:System.Windows.Media.VisualBrush> это тип <xref:System.Windows.Freezable> объекта, он не может быть заморожен <xref:System.Windows.Media.VisualBrush.Visual%2A> (сделано только читать), `null`когда его свойство установлено на значение, кроме .  
  
 Существует два способа указать <xref:System.Windows.Media.VisualBrush.Visual%2A> содержание <xref:System.Windows.Media.VisualBrush>.  
  
- Создайте <xref:System.Windows.Media.Visual> новый и используйте его <xref:System.Windows.Media.VisualBrush>для установки <xref:System.Windows.Media.VisualBrush.Visual%2A> свойства . Пример см. в разделе [Пример. Заполнение объекта с помощью видео](#examplevisualbrush1) далее в этой статье.  
  
- Используйте <xref:System.Windows.Media.Visual>существующую, которая создает дубликат изображения цели. <xref:System.Windows.Media.Visual> Затем можно использовать <xref:System.Windows.Media.VisualBrush> для создания интересных эффектов, таких как отражение и увеличение. Пример см. в разделе [Пример. Создание отражения](#examplevisualbrush2).  
  
 Когда вы <xref:System.Windows.Media.VisualBrush.Visual%2A> определяете <xref:System.Windows.Media.VisualBrush> новое <xref:System.Windows.Media.Visual> для <xref:System.Windows.UIElement> и это (например, панель или элемент <xref:System.Windows.UIElement> управления), система компоновки работает на и его элементы ребенка, когда <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> свойство установлено `true`на . Тем не <xref:System.Windows.UIElement> менее, корень по существу изолирован от остальной части системы: стили и внешний макет не могут пронизывать эту границу. Таким образом, вы должны четко указать размер корня, <xref:System.Windows.UIElement>потому что его единственным родителем является <xref:System.Windows.Media.VisualBrush> и, следовательно, он не может автоматически размер себя области окрашены. Дополнительные сведения о макете в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] см. в разделе [Макет](../advanced/layout.md).  
  
 Как <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>и <xref:System.Windows.Media.VisualBrush> , тянется его содержание, чтобы заполнить его выходной области. Это поведение можно переопределить, <xref:System.Windows.Media.TileBrush.Stretch%2A> изменив свойство из параметра по <xref:System.Windows.Media.Stretch.Fill>умолчанию. Дополнительные сведения см. в описании свойства <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="examplevisualbrush1"></a>
## <a name="example-paint-an-object-with-a-visual"></a>Пример. Заполнение объекта с помощью видео  
 В следующем примере несколько элементов управления и панель используются для заполнения прямоугольника.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>
## <a name="example-create-a-reflection"></a>Пример. Создание отражения  
 Предыдущий пример показал, как <xref:System.Windows.Media.Visual> создать новый для использования в качестве фона. Вы также можете <xref:System.Windows.Media.VisualBrush> использовать для отображения существующего визуального; эта возможность позволяет создавать интересные визуальные эффекты, такие как отражения и увеличение. В следующем примере используется для <xref:System.Windows.Media.VisualBrush> <xref:System.Windows.Controls.Border> создания отражения элемента, содержащего несколько элементов. На следующей иллюстрации показан результат выполнения этого примера.  
  
 ![Отраженный объект Visual](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Отраженный объект Visual  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Дополнительные примеры, демонстрирующие увеличение частей экрана и создание отражений, см. в разделе [Пример VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).  
  
<a name="tilebrush"></a>
## <a name="tilebrush-features"></a>Функции TileBrush  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>и <xref:System.Windows.Media.VisualBrush> являются <xref:System.Windows.Media.TileBrush> типами объектов. <xref:System.Windows.Media.TileBrush>объекты предоставляют вам большой контроль над тем, как область окрашена изображением, рисунком или визуальным. Например, можно заполнить область не одним растянутым изображением, а элементами мозаики, которые образуют узор.  
  
 A <xref:System.Windows.Media.TileBrush> имеет три основных компонента: содержимое, плитки и область вывода.  
  
 ![Компоненты TileBrush](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Компоненты TileBrush с одним элементом мозаики  
  
 ![Компоненты мозаичного TileBrush](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Компоненты TileBrush с несколькими элементами мозаики  
  
 Для получения дополнительной информации <xref:System.Windows.Media.TileBrush> об особенностях плитки объектов см. [TileBrush Overview](tilebrush-overview.md)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Общие сведения об объекте TileBrush](tilebrush-overview.md)
- [Общие сведения о кистях WPF](wpf-brushes-overview.md)
- [Общие сведения об обработке изображений](imaging-overview.md)
- [Общие сведения об объектах Drawing](drawing-objects-overview.md)
- [Общие сведения о масках непрозрачности](opacity-masks-overview.md)
- [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md)
- [Пример использования ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [Пример использования VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
