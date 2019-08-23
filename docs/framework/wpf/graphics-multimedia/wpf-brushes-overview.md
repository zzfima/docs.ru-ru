---
title: Общие сведения о кистях WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 29f0bc77306df5639c188295f9f5dff7f18b4706
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962850"
---
# <a name="wpf-brushes-overview"></a>Общие сведения о кистях WPF
Все, что видно на экране, видимо, так как оно было закрашено кистью. Например, кисть используется для описания фона кнопки, переднего плана текста и заливки фигуры. В этом разделе приводятся основные понятия [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] рисования с помощью кистей и примеры. Кисти позволяют заполнять объекты [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] различными изображениями, начиная с просто сплошного цвета и заканчивая сложными наборами шаблонов и изображений.  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a>Рисование с помощью кисти  
 <xref:System.Windows.Media.Brush> «Закрашивает» область с выходными данными. Различные кисти имеют различные типы выходных данных. Некоторые кисти закрашивать область сплошным цветом, другими — градиентом, узором, изображением или рисованием. На следующем рисунке показаны примеры каждого из различных <xref:System.Windows.Media.Brush> типов.  
  
 ![Типы кистей](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
Примеры кистей  
  
 Большинство визуальных объектов позволяют указать, как они рисуются. В следующей таблице перечислены некоторые распространенные объекты и свойства, с которыми можно использовать <xref:System.Windows.Media.Brush>.  
  
|Класс|Свойства кисти|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 В следующих разделах описываются различные <xref:System.Windows.Media.Brush> типы и приводится пример каждого из них.  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a>Заливка сплошным цветом  
 Рисует область сплошным <xref:System.Windows.Media.Color>цветом. <xref:System.Windows.Media.SolidColorBrush> Существует множество способов указания <xref:System.Windows.Media.SolidColorBrush.Color%2A> типа. Например, можно указать его альфа- <xref:System.Windows.Media.SolidColorBrush>, красный, синий и зеленый каналы или использовать один из <xref:System.Windows.Media.Colors> стандартных цветов, предоставленных классом.  
  
 В следующем примере используется <xref:System.Windows.Media.SolidColorBrush> для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования объекта <xref:System.Windows.Shapes.Rectangle>. На следующем рисунке показан закрашенный прямоугольник.  
  
 ![Прямоугольник, закрашенный с помощью SolidColorBrush](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
Прямоугольник, закрашенный с помощью SolidColorBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.SolidColorBrush> классе см. в разделе [Рисование с помощью сплошных цветов и градиентов](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a>Рисование с помощью линейного градиента  
 <xref:System.Windows.Media.LinearGradientBrush> Рисует область с линейным градиентом. Линейный градиент смешивает два или более цвета в линии, оси градиента. Объекты используются <xref:System.Windows.Media.GradientStop> для указания цветов в градиенте и их позиций.  
  
 В следующем примере используется <xref:System.Windows.Media.LinearGradientBrush> для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования объекта <xref:System.Windows.Shapes.Rectangle>. На следующем рисунке показан закрашенный прямоугольник.  
  
 ![Прямоугольник, закрашенный с помощью LinearGradientBrush](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
Прямоугольник, закрашенный с помощью LinearGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.LinearGradientBrush> классе см. в разделе [Рисование с помощью сплошных цветов и градиентов](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a>Рисование с помощью радиального градиента  
 <xref:System.Windows.Media.RadialGradientBrush> Рисует область с радиальным градиентом. Радиальный градиент смешивает два или более цвета в окружности. Как и в <xref:System.Windows.Media.LinearGradientBrush> случае с классом <xref:System.Windows.Media.GradientStop> , для указания цветов в градиенте и их позиций используются объекты.  
  
 В следующем примере используется <xref:System.Windows.Media.RadialGradientBrush> для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования объекта <xref:System.Windows.Shapes.Rectangle>. На следующем рисунке показан закрашенный прямоугольник.  
  
 ![Прямоугольник, закрашенный с помощью RadialGradientBrush](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
Прямоугольник, закрашенный с помощью RadialGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.RadialGradientBrush> классе см. в разделе [Рисование с помощью сплошных цветов и градиентов](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a>Рисование с помощью изображения  
 <xref:System.Windows.Media.ImageBrush> Закрашивает область с помощью <xref:System.Windows.Media.ImageSource>.  
  
 В следующем примере используется <xref:System.Windows.Media.ImageBrush> для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования объекта <xref:System.Windows.Shapes.Rectangle>. На следующем рисунке показан закрашенный прямоугольник.  
  
 ![Прямоугольник] , закрашенный ImageBrush (./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
Прямоугольник, закрашенный с помощью изображения  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Дополнительные сведения о классе см <xref:System.Windows.Media.ImageBrush> . в разделе [Рисование с помощью изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a>Рисование с помощью рисования  
 <xref:System.Windows.Media.DrawingBrush> Рисует область с помощью <xref:System.Windows.Media.Drawing>. <xref:System.Windows.Media.Drawing> Может содержать фигуры, изображения, текст и мультимедиа.  
  
 В следующем примере используется <xref:System.Windows.Media.DrawingBrush> для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования объекта <xref:System.Windows.Shapes.Rectangle>. На следующем рисунке показан закрашенный прямоугольник.  
  
 ![Прямоугольник, закрашенный с помощью DrawingBrush](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
Прямоугольник, закрашенный с помощью DrawingBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Дополнительные сведения о классе см <xref:System.Windows.Media.DrawingBrush> . в разделе [Рисование с помощью изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a>Рисование с помощью визуального элемента  
 <xref:System.Windows.Media.VisualBrush> Рисует область<xref:System.Windows.Media.Visual> с объектом. Примеры визуальных объектов: <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page>и <xref:System.Windows.Controls.MediaElement>. А <xref:System.Windows.Media.VisualBrush> также позволяет проецировать содержимое из одной части приложения в другую, оно очень полезно для создания эффектов отражения и увеличения фрагментов экрана.  
  
 В следующем примере используется <xref:System.Windows.Media.VisualBrush> для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования объекта <xref:System.Windows.Shapes.Rectangle>. На следующем рисунке показан закрашенный прямоугольник.  
  
 ![Прямоугольник, закрашенный с помощью VisualBrush](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
Прямоугольник, закрашенный с помощью VisualBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Дополнительные сведения о классе см <xref:System.Windows.Media.VisualBrush> . в разделе [Рисование с помощью изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a>Рисование с помощью стандартных и системных кистей  
 Для удобства Windows Presentation Foundation (WPF) предоставляет набор стандартных и системных кистей, которые можно использовать для рисования объектов.  
  
- Список доступных стандартных кистей см. в <xref:System.Windows.Media.Brushes> разделе класс. Пример, демонстрирующий использование предопределенной кисти, см. в разделе [Закраска области сплошным цветом](how-to-paint-an-area-with-a-solid-color.md).  
  
- Список доступных системных кистей см. в <xref:System.Windows.SystemColors> разделе класс. Пример см. в разделе [закрашивание области с помощью системной кисти](how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a>Общие функции кисти  
 <xref:System.Windows.Media.Brush>объекты предоставляют <xref:System.Windows.Media.Brush.Opacity%2A> свойство, которое можно использовать для того, чтобы сделать кисть прозрачной или частично прозрачной. Значение 0 делает кисть полностью прозрачной, <xref:System.Windows.Media.Brush.Opacity%2A> а значение 1 делает кисть полностью непрозрачной. <xref:System.Windows.Media.Brush.Opacity%2A> В следующем примере <xref:System.Windows.Media.Brush.Opacity%2A> свойство используется для создания непрозрачного 25- <xref:System.Windows.Media.SolidColorBrush> процентного значения.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Если кисть содержит частично прозрачные цвета, значение прозрачности цвета объединяется посредством умножения со значением прозрачности кисти. Например, если кисть имеет значение Opacity, равное 0,5, а цвет, используемый в кисти, также имеет значение Opacity, равное 0,5, то выходной цвет имеет значение непрозрачности, равное 0,25.  
  
> [!NOTE]
> Изменение значения прозрачности кисти более эффективно, чем изменение прозрачности всего элемента с помощью его <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> свойства.  
  
 Можно поворачивать, масштабировать, отклонять и преобразовывать содержимое кисти с помощью <xref:System.Windows.Media.Brush.Transform%2A> свойств или. <xref:System.Windows.Media.Brush.RelativeTransform%2A> Дополнительные сведения см. в разделе [Общие сведения о преобразовании кисти](brush-transformation-overview.md).  
  
 Так как они <xref:System.Windows.Media.Animation.Animatable> являются объектами <xref:System.Windows.Media.Brush> , объекты можно анимировать. Более подробную информацию см. в разделе [Общие сведения об эффектах анимации](animation-overview.md).  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a>Возможности объектов Freezable  
 Поскольку он наследуется от <xref:System.Windows.Freezable> класса <xref:System.Windows.Media.Brush> , класс предоставляет несколько специальных функций: <xref:System.Windows.Media.Brush> объекты могут быть объявлены как [ресурсы](../advanced/xaml-resources.md), совместно использоваться несколькими объектами и клонированы. Кроме того, все <xref:System.Windows.Media.Brush> типы, кроме <xref:System.Windows.Media.VisualBrush> , можно сделать доступными только для чтения, чтобы повысить производительность и обеспечить потокобезопасность.  
  
 Дополнительные сведения о различных возможностях, предоставляемых <xref:System.Windows.Freezable> объектами, см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).  
  
 Дополнительные сведения о том, <xref:System.Windows.Media.VisualBrush> почему объекты не могут быть заморожены <xref:System.Windows.Media.VisualBrush> , см. на странице типа.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [Общие сведения о закраске сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md)
- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
- [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md)
- [Пример использования кистей](https://go.microsoft.com/fwlink/?LinkID=159973)
- [Пример ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [Пример использования VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049)
- [Разделы практического руководства](brushes-how-to-topics.md)
- [Дополнительные рекомендации по повышению производительности](../advanced/optimizing-performance-other-recommendations.md)
