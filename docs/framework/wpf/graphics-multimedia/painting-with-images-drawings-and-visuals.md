---
title: "Рисование с помощью объектов Image, Drawing и Visual"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 01939eb8735e6764e0f0cba811091c7fdbd6797f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="painting-with-images-drawings-and-visuals"></a>Рисование с помощью объектов Image, Drawing и Visual
В этом разделе описывается использование <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, и <xref:System.Windows.Media.VisualBrush> объектов Закраска области с изображением, <xref:System.Windows.Media.Drawing>, или <xref:System.Windows.Media.Visual>.  
    
  
<a name="prereqs"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Для понимания этого раздела необходимо ознакомиться с различными типами кистей, имеющихся в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], и их основными возможностями. Общие сведения см. в разделе [Общие сведения о кистях WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  
  
<a name="image"></a>   
## <a name="paint-an-area-with-an-image"></a>Закрашивание области с помощью Image  
 <xref:System.Windows.Media.ImageBrush> Закрашивает область с <xref:System.Windows.Media.ImageSource>. Наиболее распространенным типом <xref:System.Windows.Media.ImageSource> для использования с <xref:System.Windows.Media.ImageBrush> — <xref:System.Windows.Media.Imaging.BitmapImage>, описывающей растрового изображения. Можно использовать <xref:System.Windows.Media.DrawingImage> для рисования с помощью <xref:System.Windows.Media.Drawing> , но проще использовать <xref:System.Windows.Media.DrawingBrush> вместо него. Дополнительные сведения о <xref:System.Windows.Media.ImageSource> объектов, в разделе [Imaging Обзор](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
 Рисование с <xref:System.Windows.Media.ImageBrush>, создание <xref:System.Windows.Media.Imaging.BitmapImage> и использовать его для загрузки содержимого точечного рисунка. Затем с помощью <xref:System.Windows.Media.Imaging.BitmapImage> для задания <xref:System.Windows.Media.ImageBrush.ImageSource%2A> свойство <xref:System.Windows.Media.ImageBrush>. Наконец, примените <xref:System.Windows.Media.ImageBrush> объекту рисования.  В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], можно просто задать <xref:System.Windows.Media.ImageBrush.ImageSource%2A> свойство <xref:System.Windows.Media.ImageBrush> на путь к загружаемому изображению.  
  
 Как и все <xref:System.Windows.Media.Brush> объектов, <xref:System.Windows.Media.ImageBrush> можно использовать для рисования объектов, таких как фигур, панелей, элементов управления и текста. На следующем рисунке показан некоторые эффекты, которые могут быть получены с <xref:System.Windows.Media.ImageBrush>.  
  
 ![Примеры вывода ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Объекты, заполненные при помощи ImageBrush  
  
 По умолчанию <xref:System.Windows.Media.ImageBrush> растягивает изображения до полного заполнения области закрашиваемой и может искажать изображение, если область рисования имеет отличные от изображения пропорции. Это поведение можно изменить, изменив <xref:System.Windows.Media.TileBrush.Stretch%2A> свойства со значения по умолчанию <xref:System.Windows.Media.Stretch.Fill> для <xref:System.Windows.Media.Stretch.None>, <xref:System.Windows.Media.Stretch.Uniform>, или <xref:System.Windows.Media.Stretch.UniformToFill>. Поскольку <xref:System.Windows.Media.ImageBrush> — это тип <xref:System.Windows.Media.TileBrush>, можно указать, как именно кисти заполняет область вывода и даже создавать шаблоны. Дополнительные сведения о дополнительных <xref:System.Windows.Media.TileBrush> возможности, см. [Обзор TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>   
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Пример. Заполнение объекта с помощью точечного рисунка  
 В следующем примере используется <xref:System.Windows.Media.ImageBrush> для закрашивания <xref:System.Windows.Controls.Panel.Background%2A> из <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## <a name="paint-an-area-with-a-drawing"></a>Закрашивание области с помощью Drawing  
 Объект <xref:System.Windows.Media.DrawingBrush> позволяет Закраска области с фигуры, текст, изображения и видео. Фигуры внутри кисти могут сами заполнять сплошной цвет, градиент, изображение или даже другим <xref:System.Windows.Media.DrawingBrush>. На следующем рисунке показано несколько способов использования <xref:System.Windows.Media.DrawingBrush>.  
  
 ![Примеры вывода DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Объекты, заполненные при помощи DrawingBrush  
  
 Объект <xref:System.Windows.Media.DrawingBrush> закрашивает область с <xref:System.Windows.Media.Drawing> объекта. Объект <xref:System.Windows.Media.Drawing> описывает отображаемое содержимое, например фигуры, растрового изображения, видео или строка текста. Различные типы рисунков описывают различные типы содержимого. Ниже приведен список различных типов объектов-рисунков.  
  
-   <xref:System.Windows.Media.GeometryDrawing>— Выводит фигуру.  
  
-   <xref:System.Windows.Media.ImageDrawing>— Выводит изображение.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing>— Выводит текст.  
  
-   <xref:System.Windows.Media.VideoDrawing>— Воспроизводит файл аудио и видео.  
  
-   <xref:System.Windows.Media.DrawingGroup>— Выводит другие рисунки. Для объединения рисунков в один составной используйте группирование рисунков.  
  
 Дополнительные сведения о <xref:System.Windows.Media.Drawing> объектов, в разделе [Общие сведения об объектах Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
 Как <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> растягивает его <xref:System.Windows.Media.DrawingBrush.Drawing%2A> для заполнения области вывода. Это поведение можно переопределить, изменив <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство из значения по умолчанию <xref:System.Windows.Media.Stretch.Fill>. Дополнительные сведения см. в описании свойства <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## <a name="example-paint-an-object-with-a-drawing"></a>Пример. Заполнение объекта с помощью рисунка  
 В следующем примере показано, как можно заполнить объект с помощью рисунка с изображением трех эллипсов. Объект <xref:System.Windows.Media.GeometryDrawing> используется для описания многоточие.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## <a name="paint-an-area-with-a-visual"></a>Закрашивание области с помощью Visual  
 Наиболее гибкая и мощная кистей <xref:System.Windows.Media.VisualBrush> закрашивает область с <xref:System.Windows.Media.Visual>. Объект <xref:System.Windows.Media.Visual> является графическим типом нижнего уровня, который служит в качестве предка многих полезных графических компонентов. Например <xref:System.Windows.Window>, <xref:System.Windows.FrameworkElement>, и <xref:System.Windows.Controls.Control> классы являются все типы <xref:System.Windows.Media.Visual> объектов. С помощью <xref:System.Windows.Media.VisualBrush>, вы можете отобразить области практически любыми [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] графический объект.  
  
> [!NOTE]
>  Несмотря на то что <xref:System.Windows.Media.VisualBrush> — это тип <xref:System.Windows.Freezable> объекта, он не может быть заморожен (доступным только для чтения) при его <xref:System.Windows.Media.VisualBrush.Visual%2A> свойству присвоено значение, отличное от `null`.  
  
 Существует два способа указать <xref:System.Windows.Media.VisualBrush.Visual%2A> содержимое <xref:System.Windows.Media.VisualBrush>.  
  
-   Создайте новый <xref:System.Windows.Media.Visual> и использовать его для задания <xref:System.Windows.Media.VisualBrush.Visual%2A> свойство <xref:System.Windows.Media.VisualBrush>. Пример см. в разделе [Пример. Заполнение объекта с помощью видео](#examplevisualbrush1) далее в этой статье.  
  
-   Использовать существующий <xref:System.Windows.Media.Visual>, который создает дубликат изображения целевого <xref:System.Windows.Media.Visual>. Затем можно использовать <xref:System.Windows.Media.VisualBrush> для создания интересных эффектов, например отражения и увеличения. Пример см. в разделе [Пример. Создание отражения](#examplevisualbrush2).  
  
 При определении нового <xref:System.Windows.Media.VisualBrush.Visual%2A> для <xref:System.Windows.Media.VisualBrush> и что <xref:System.Windows.Media.Visual> — <xref:System.Windows.UIElement> (например, в панели или элементе управления), система макета выполняется <xref:System.Windows.UIElement> и его дочерние элементы при <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> свойству `true`. Однако корневой <xref:System.Windows.UIElement> по существу изолирован от остальной системы: стили и внешний макет не могут переходить эту границу. Таким образом, следует явно указать размер корневого <xref:System.Windows.UIElement>, поскольку его единственным родительским объектом является <xref:System.Windows.Media.VisualBrush> и поэтому его размер не может автоматически сам по закрашиваемой области. Дополнительные сведения о макете в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] см. в разделе [Макет](../../../../docs/framework/wpf/advanced/layout.md).  
  
 Как <xref:System.Windows.Media.ImageBrush> и <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush> растягивает свое содержимое до заполнения области вывода. Это поведение можно переопределить, изменив <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство из значения по умолчанию <xref:System.Windows.Media.Stretch.Fill>. Дополнительные сведения см. в описании свойства <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="examplevisualbrush1"></a>   
## <a name="example-paint-an-object-with-a-visual"></a>Пример. Заполнение объекта с помощью видео  
 В следующем примере несколько элементов управления и панель используются для заполнения прямоугольника.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## <a name="example-create-a-reflection"></a>Пример. Создание отражения  
 В предыдущем примере показано, как создать новый <xref:System.Windows.Media.Visual> для использования в качестве фона. Можно также использовать <xref:System.Windows.Media.VisualBrush> для отображения существующего объекта visual; эта возможность позволяет создавать интересные визуальные эффекты, например отражения и увеличения. В следующем примере используется <xref:System.Windows.Media.VisualBrush> создание отражения <xref:System.Windows.Controls.Border> , содержащего несколько элементов. На следующей иллюстрации показан результат выполнения этого примера.  
  
 ![Объект отражены визуального объекта](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Отраженный объект Visual  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Дополнительные примеры, демонстрирующие увеличение частей экрана и создание отражений, см. в разделе [Пример VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049).  
  
<a name="tilebrush"></a>   
## <a name="tilebrush-features"></a>Функции TileBrush  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, и <xref:System.Windows.Media.VisualBrush> типов <xref:System.Windows.Media.TileBrush> объектов. <xref:System.Windows.Media.TileBrush>объекты предоставляют значительные возможности контроля над способ рисования области с изображения, рисунок или visual. Например, можно заполнить область не одним растянутым изображением, а элементами мозаики, которые образуют узор.  
  
 Объект <xref:System.Windows.Media.TileBrush> имеет три основных компонента: содержимое, плитки и в области вывода.  
  
 ![Компоненты TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Компоненты TileBrush с одним элементом мозаики  
  
 ![Компоненты мозаичного TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Компоненты TileBrush с несколькими элементами мозаики  
  
 Дополнительные сведения о возможностях мозаичного заполнения области <xref:System.Windows.Media.TileBrush> объектов, в разделе [Обзор TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 <xref:System.Windows.Media.TileBrush>  
 [Общие сведения об объекте TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [Общие сведения о кистях WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Общие сведения о масках непрозрачности](../../../../docs/framework/wpf/graphics-multimedia/opacity-masks-overview.md)  
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Образец ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005)  
 [Пример использования VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049)
