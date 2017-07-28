---
title: "Общие сведения о кистях WPF | Microsoft Docs"
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
  - "кисти, сведения о кистях"
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Общие сведения о кистях WPF
Все отображаемые на экране объекты являются видимыми, так как они нарисованы кистью.  Например, кисть используется для описания фона кнопки, основного цвета текста и заполнения фигуры.  В этом разделе представлены механизмы рисования с помощью кистей [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и примеры.  Кисти позволяют рисовать как простые одноцветные объекты [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], так и объекты со сложными наборами шаблонов и изображений.  
  
<a name="paintingwithbrush"></a>   
## Рисование с помощью кисти  
 <xref:System.Windows.Media.Brush> "рисует" область с выходными данными.  Различные кисти имеют разные типы вывода.  Некоторые кисти закрашивают область сплошным цветом, другим — градиентом, узором, изображением или рисунком.  На следующем рисунке приведены примеры каждого из типов <xref:System.Windows.Media.Brush>.  
  
 ![Типы кистей](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushtypes.png "graphicsmm\_brushtypes")  
Примеры кисти  
  
 Большинство визуальных объектов позволяет указать способ их рисования.  В следующей таблице перечислены некоторые общие объекты и свойства, с которыми можно использовать <xref:System.Windows.Media.Brush>.  
  
|Класс|Свойства кисти|  
|-----------|--------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 В следующих разделах описаны различные типы <xref:System.Windows.Media.Brush>, а также приведены примеры для каждого из них.  
  
<a name="paintwithsolidcolorbrush"></a>   
## Закраска сплошным цветом  
 <xref:System.Windows.Media.SolidColorBrush> закрашивает область сплошным <xref:System.Windows.Media.Color>.  Существует несколько способов указания <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush>: например, можно указать его альфа\-канал, красный, синий и зеленый каналы или воспользоваться одним из цветов, предоставленных классом <xref:System.Windows.Media.Colors>.  
  
 В следующем примере <xref:System.Windows.Media.SolidColorBrush> используется для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> фигуры <xref:System.Windows.Shapes.Rectangle>.  Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, закрашенный с помощью SolidColorBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm\_brush\_ovw\_solidcolorbrush")  
Прямоугольник, закрашенный с помощью SolidColorBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Дополнительные сведения о классе <xref:System.Windows.Media.SolidColorBrush> см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## Закрашивание линейным градиентом  
 <xref:System.Windows.Media.LinearGradientBrush> закрашивает область линейным градиентом.  Линейный градиент сочетает два или более цветов через линию, являющуюся осью градиента.  Используйте объекты <xref:System.Windows.Media.GradientStop> для указания цветов градиента и их позиции.  
  
 В следующем примере <xref:System.Windows.Media.LinearGradientBrush> используется для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> фигуры <xref:System.Windows.Shapes.Rectangle>.  Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, закрашенный с помощью LinearGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-lineargradientbrush.png "graphicsmm\_brush\_ovw\_lineargradientbrush")  
Прямоугольник, закрашенный с помощью LinearGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Дополнительные сведения о классе <xref:System.Windows.Media.LinearGradientBrush> см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## Закрашивание с помощью радиального градиента  
 <xref:System.Windows.Media.RadialGradientBrush> закрашивает область радиальным градиентом.  Радиальный градиент сочетает несколько цветов через окружность.  Как и при использовании класса <xref:System.Windows.Media.LinearGradientBrush>, необходимо использовать объекты <xref:System.Windows.Media.GradientStop> для указания цветов в градиенте и их позиций.  
  
 В следующем примере <xref:System.Windows.Media.RadialGradientBrush> используется для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> фигуры <xref:System.Windows.Shapes.Rectangle>.  Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, закрашенный с использованием RadialGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-radialgradientbrush.png "graphicsmm\_brush\_ovw\_radialgradientbrush")  
Прямоугольник, закрашенный с использованием RadialGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Дополнительные сведения о классе <xref:System.Windows.Media.RadialGradientBrush> см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## Рисование с помощью изображения  
 <xref:System.Windows.Media.ImageBrush> закрашивает область с помощью <xref:System.Windows.Media.ImageSource>.  
  
 В следующем примере используется <xref:System.Windows.Media.ImageBrush> для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> объекта <xref:System.Windows.Shapes.Rectangle>.  Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, созданный при помощи ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-imagebrush.png "graphicsmm\_brush\_ovw\_imagebrush")  
Прямоугольник, закрашенный с использованием изображения  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Дополнительные сведения о классе <xref:System.Windows.Media.ImageBrush> см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>   
## Закрашивание рисованием  
 <xref:System.Windows.Media.DrawingBrush> закрашивает область с помощью <xref:System.Windows.Media.Drawing>.  <xref:System.Windows.Media.Drawing> может содержать фигуры, изображения, текст и мультимедийные данные.  
  
 В следующем примере <xref:System.Windows.Media.DrawingBrush> используется для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> фигуры <xref:System.Windows.Shapes.Rectangle>.  Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, закрашенный с помощью DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-drawingbrush.png "graphicsmm\_brush\_ovw\_drawingbrush")  
Прямоугольник, закрашенный с помощью DrawingBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Дополнительные сведения о классе <xref:System.Windows.Media.DrawingBrush> см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>   
## Закрашивание с помощью Visual  
 <xref:System.Windows.Media.VisualBrush> закрашивает область с помощью объекта <xref:System.Windows.Media.Visual>.  В число объектов Visual входят объекты <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page> и <xref:System.Windows.Controls.MediaElement>.  <xref:System.Windows.Media.VisualBrush> также позволяет переносить содержимое из одной части приложения в другую область, что может быть полезным при создании эффекта отражения и увеличения части экрана.  
  
 В следующем примере <xref:System.Windows.Media.VisualBrush> используется для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> фигуры <xref:System.Windows.Shapes.Rectangle>.  Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, закрашенный с использованием VisualBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-visualbrush.png "graphicsmm\_brush\_ovw\_visualbrush")  
Прямоугольник, закрашенный с использованием VisualBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Дополнительные сведения о классе <xref:System.Windows.Media.VisualBrush> см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## Рисование с помощью готовых и системных кистей  
 Для удобства [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] предоставляет набор готовых и система кистей, которые можно использовать для закрашивания объектов.  
  
-   Список доступных готовых кистей содержится в описании класса <xref:System.Windows.Media.Brushes>.  Пример, демонстрирующий использование готовой кисти, см. в разделе [Закраска области сплошным цветом](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-solid-color.md).  
  
-   Список доступных системных кистей содержится в описании класса <xref:System.Windows.SystemColors>.  Пример см. в разделе [Закраска области с помощью системной кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## Общие средства кисти  
 Объекты <xref:System.Windows.Media.Brush> предоставляют свойство <xref:System.Windows.Media.Brush.Opacity%2A>, которое может быть использовано для создания прозрачной или частично прозрачной кисти.  Значение <xref:System.Windows.Media.Brush.Opacity%2A>, равное 0, делает кисть полностью прозрачной, а значение <xref:System.Windows.Media.Brush.Opacity%2A>, равное 1, делает кисть полностью непрозрачной.  В следующем пример свойство <xref:System.Windows.Media.Brush.Opacity%2A> используется, чтобы сделать <xref:System.Windows.Media.SolidColorBrush> непрозрачным на 25 процентов.  
  
 [!code-xml[BrushOverviewExamples_snip#OpacityExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Если кисть содержит частично прозрачные цвета, значение непрозрачности цвета определяется путем умножения на значение непрозрачности кисти.  Например, если кисть имеет значение непрозрачности, равное 0.5, а цвет, используемый кистью, также имеет значение непрозрачности 0.5, то выходной цвет имеет значение непрозрачности, равное 0.25.  
  
> [!NOTE]
>  Эффективнее изменить значение непрозрачности кисти, чем прозрачность целого элемента через его свойство <xref:System.Windows.UIElement.Opacity%2A?displayProperty=fullName>.  
  
 Содержимое кисти можно поворачивать, масштабировать, наклонять и преобразовывать с помощью свойств <xref:System.Windows.Media.Brush.Transform%2A> или <xref:System.Windows.Media.Brush.RelativeTransform%2A>.  Дополнительные сведения см. в разделе [Общие сведения о преобразованиях объекта Brush](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Как объекты <xref:System.Windows.Media.Animation.Animatable>, объекты <xref:System.Windows.Media.Brush> могут быть анимированы.  Дополнительные сведения см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
### Возможности объектов Freezable  
 Поскольку он наследуется от класса <xref:System.Windows.Freezable>, класс <xref:System.Windows.Media.Brush> предоставляет несколько особенных возможностей: объекты класса <xref:System.Windows.Media.Brush> можно объявлять [ресурсами](../../../../docs/framework/wpf/advanced/xaml-resources.md), которые могут совместно использоваться несколькими объектами или клонироваться.  Кроме того, все типы <xref:System.Windows.Media.Brush>, за исключением <xref:System.Windows.Media.VisualBrush>, могут быть объявлены типами только для чтения для повышения производительности и обеспечения безопасности для потоков.  
  
 Дополнительные сведения о различных возможностях, предоставляемых объектами <xref:System.Windows.Freezable>, см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Для получения дополнительных сведений о том, почему объекты <xref:System.Windows.Media.VisualBrush> не могут быть заморожены, см. страницу описания типа <xref:System.Windows.Media.VisualBrush>.  
  
## См. также  
 <xref:System.Windows.Media.Brush>   
 <xref:System.Windows.Media.Brushes>   
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973)   
 [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005)   
 [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)   
 [Дополнительные рекомендации по повышению производительности](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)