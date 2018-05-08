---
title: Общие сведения о кистях WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 794b17c5a7735201296958580540273879398e9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="wpf-brushes-overview"></a>Общие сведения о кистях WPF
Все элементы, видимые на экране отображается, так как они нарисованы кистью. Например кисть используется для описания фона кнопки, основного цвета текста и заполнения фигуры. В этом разделе представлены понятия, рисования с помощью [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] кисти и приводятся примеры. Кисти позволяют заполнять объекты [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] различными изображениями, начиная с просто сплошного цвета и заканчивая сложными наборами шаблонов и изображений.  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a>Рисование с помощью кисти  
 Объект <xref:System.Windows.Media.Brush> «рисует» область с выходными данными. Различные кисти имеют разные типы выходных данных. Некоторые кисти закрасить область сплошным цветом, другие пользователи с градиентом, шаблон, изображения или рисунка. Ниже приведены примеры каждой из различных <xref:System.Windows.Media.Brush> типов.  
  
 ![Типы кисти](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
Примеры кисти  
  
 Большинство визуальных объектов позволяют указать способ рисования. В следующей таблице перечислены некоторые общие объекты и свойства, которые можно использовать в <xref:System.Windows.Media.Brush>.  
  
|Класс|Свойства кисти|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 В следующих разделах описаны различные <xref:System.Windows.Media.Brush> типы и приведен пример.  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a>Заливкой сплошным цветом  
 Объект <xref:System.Windows.Media.SolidColorBrush> закрашивает область сплошным <xref:System.Windows.Media.Color>. Существует множество способов указания <xref:System.Windows.Media.SolidColorBrush.Color%2A> из <xref:System.Windows.Media.SolidColorBrush>: например, можно указать его альфа, красного, синий и зеленый каналы или использовать один из цветов, предоставленных <xref:System.Windows.Media.Colors> класса.  
  
 В следующем примере используется <xref:System.Windows.Media.SolidColorBrush> для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Rectangle>. Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, закрашенный с помощью SolidColorBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
Прямоугольник, закрашенный с помощью SolidColorBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.SolidColorBrush> см. в описании [Рисование с сплошные цвета и градиенты Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a>Рисование с линейным градиентом  
 Объект <xref:System.Windows.Media.LinearGradientBrush> закрашивает область с линейным градиентом. Линейный градиент сочетает два или более цветов через строку оси градиента. Вы используете <xref:System.Windows.Media.GradientStop> объекты для указания цветов и их позиций.  
  
 В следующем примере используется <xref:System.Windows.Media.LinearGradientBrush> для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Rectangle>. Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, закрашенный с помощью LinearGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
Прямоугольник, закрашенный с помощью LinearGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.LinearGradientBrush> см. в описании [Рисование с сплошные цвета и градиенты Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a>Рисования с применением радиального градиента  
 Объект <xref:System.Windows.Media.RadialGradientBrush> закрашивает область с применением радиального градиента. Радиальный градиент сочетает два или более цветов через окружность. Как и в <xref:System.Windows.Media.LinearGradientBrush> , использовать <xref:System.Windows.Media.GradientStop> объекты для указания цветов и их позиций.  
  
 В следующем примере используется <xref:System.Windows.Media.RadialGradientBrush> для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Rectangle>. Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, закрашенный с использованием RadialGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
Прямоугольник, закрашенный с использованием RadialGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.RadialGradientBrush> см. в описании [Рисование с сплошные цвета и градиенты Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a>Рисование с помощью изображения  
 <xref:System.Windows.Media.ImageBrush> Закрашивает область с <xref:System.Windows.Media.ImageSource>.  
  
 В следующем примере используется <xref:System.Windows.Media.ImageBrush> для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Rectangle>. Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, созданный при помощи ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
Прямоугольник, закрашенный с использованием образа  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> см. в описании [Рисование с помощью изображения, рисунки и визуальные элементы](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a>Рисование с рисунка  
 Объект <xref:System.Windows.Media.DrawingBrush> закрашивает область с <xref:System.Windows.Media.Drawing>. Объект <xref:System.Windows.Media.Drawing> может содержать фигуры, изображения, текст и мультимедиа.  
  
 В следующем примере используется <xref:System.Windows.Media.DrawingBrush> для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Rectangle>. Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, закрашенный с помощью DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
Прямоугольник, закрашенный с помощью DrawingBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.DrawingBrush> см. в описании [Рисование с помощью изображения, рисунки и визуальные элементы](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a>Рисования с помощью Visual  
 Объект <xref:System.Windows.Media.VisualBrush> закрашивает область с <xref:System.Windows.Media.Visual> объекта. Примеры визуальных объектов <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page>, и <xref:System.Windows.Controls.MediaElement>. Объект <xref:System.Windows.Media.VisualBrush> также позволяет переносить содержимое из одной части приложения в другую область; очень полезен для создания эффектов отражения или увеличении части экрана.  
  
 В следующем примере используется <xref:System.Windows.Media.VisualBrush> для закрашивания <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Rectangle>. Закрашенный прямоугольник показан на следующем рисунке.  
  
 ![Прямоугольник, закрашенный с использованием VisualBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
Прямоугольник, закрашенный с использованием VisualBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.VisualBrush> см. в описании [Рисование с помощью изображения, рисунки и визуальные элементы](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a>С помощью готовых и системные кисти рисования  
 Для удобства Windows Presentation Foundation (WPF) предоставляет набор предопределенных, и система кистей, можно использовать для рисования объектов.  
  
-   Список доступных готовых кистей см. в разделе <xref:System.Windows.Media.Brushes> класса. Пример, демонстрирующий использование готовой кисти см. в разделе [закрасить область сплошным цветом](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-solid-color.md).  
  
-   Список доступных системных кистей см. в разделе <xref:System.Windows.SystemColors> класса. Пример см. в разделе [Закраска области с помощью системной кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a>Общие средства кисти  
 <xref:System.Windows.Media.Brush> объекты предоставляют <xref:System.Windows.Media.Brush.Opacity%2A> свойство, которое может использоваться для сделать кисти прозрачным или полупрозрачным. <xref:System.Windows.Media.Brush.Opacity%2A> Значение 0, делает кисть полностью прозрачной, а <xref:System.Windows.Media.Brush.Opacity%2A> значение 1, делает кисть полностью непрозрачна. В следующем примере используется <xref:System.Windows.Media.Brush.Opacity%2A> свойства <xref:System.Windows.Media.SolidColorBrush> непрозрачности 25 процентов.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Если кисть содержит частично прозрачные цвета, значение непрозрачности цвета объединяется путем умножения значения непрозрачности кисти. Например если цвет, используемый кистью также имеет значение 0,5 непрозрачности кисти имеет значение 0,5, выходной цвет имеет значение непрозрачности 0,25.  
  
> [!NOTE]
>  Более эффективно, чтобы изменить значение непрозрачности кисти не требуется изменить степени непрозрачности весь элемент с помощью его <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> свойство.  
  
 Поворот, масштабирование, наклон и преобразовать содержимое кисти с использованием его <xref:System.Windows.Media.Brush.Transform%2A> или <xref:System.Windows.Media.Brush.RelativeTransform%2A> свойства. Дополнительные сведения см. в разделе [Обзор преобразования кисти](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Так как они являются <xref:System.Windows.Media.Animation.Animatable> объектов, <xref:System.Windows.Media.Brush> объекты могут быть анимированы. Более подробную информацию см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a>Возможности объектов Freezable  
 Так как он наследуется от <xref:System.Windows.Freezable> класса, <xref:System.Windows.Media.Brush> класс предоставляет несколько специальных возможностей: <xref:System.Windows.Media.Brush> объектов могут быть объявлены как [ресурсов](../../../../docs/framework/wpf/advanced/xaml-resources.md), совместно использоваться несколькими объектами и клонировать. Кроме того все <xref:System.Windows.Media.Brush> типов, за исключением <xref:System.Windows.Media.VisualBrush> доступным только для чтения для повышения производительности и обеспечения безопасности для потоков.  
  
 Дополнительные сведения о различных возможностях, предоставляемых <xref:System.Windows.Freezable> объектов, в разделе [Freezable Общие сведения об объектах](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Дополнительные сведения о том, почему <xref:System.Windows.Media.VisualBrush> объекты не могут быть заморожена, в разделе <xref:System.Windows.Media.VisualBrush> «тип».  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Brush>  
 <xref:System.Windows.Media.Brushes>  
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Заполнение с использованием изображений, рисунков и визуальных элементов](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Пример использования кистей](http://go.microsoft.com/fwlink/?LinkID=159973)  
 [Образец ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005)  
 [Пример использования VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)  
 [Дополнительные рекомендации по повышению производительности](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
