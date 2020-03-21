---
title: Обзор кистей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 7a9474b392052900952f5b677ad94b16025de8dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186575"
---
# <a name="wpf-brushes-overview"></a>Общие сведения о кистях WPF
Все видимое на экране видно, потому что оно было окрашено кистью. Например, для описания фона кнопки, переднего плана текста и заполнения формы используется кисть. Эта тема знакомит с [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] понятиями живописи кистями и приводит примеры. Кисти позволяют заполнять объекты [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] различными изображениями, начиная с просто сплошного цвета и заканчивая сложными наборами шаблонов и изображений.  
  
<a name="paintingwithbrush"></a>
## <a name="painting-with-a-brush"></a>Картина с кистью  
 "Красит" <xref:System.Windows.Media.Brush> область с ее выходом. Разные кисти имеют различные типы выводимых данных. Некоторые кисти рисуют область с твердым цветом, другие с градиентом, рисунком, изображением или рисунком. На следующей иллюстрации показаны <xref:System.Windows.Media.Brush> примеры каждого из различных типов.  
  
 ![Типы кистей](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
Примеры кисти  
  
 Большинство визуальных объектов позволяют указать, как они окрашены. В следующей таблице перечислены некоторые общие объекты и свойства, с помощью которых можно <xref:System.Windows.Media.Brush>использовать.  
  
|Class|Свойства кисти|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 В следующих разделах описывают различные <xref:System.Windows.Media.Brush> типы и приводятся примеры каждого из них.  
  
<a name="paintwithsolidcolorbrush"></a>
## <a name="paint-with-a-solid-color"></a>Краска с твердым цветом  
 Красит <xref:System.Windows.Media.SolidColorBrush> область <xref:System.Windows.Media.Color>твердым. Существует множество способов <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush>указать: например, можно указать его альфа-, красный, синий и зеленый каналы или использовать один из предопределенных цветов, предусмотренных <xref:System.Windows.Media.Colors> классом.  
  
 Следующий пример <xref:System.Windows.Media.SolidColorBrush> использует для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования <xref:System.Windows.Shapes.Rectangle>. На следующей иллюстрации изображен окрашенный прямоугольник.  
  
 ![Прямоугольник, закрашенный с помощью SolidColorBrush](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
Прямоугольник, окрашенный с помощью SolidColorBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Для получения дополнительной <xref:System.Windows.Media.SolidColorBrush> информации о классе, см [Картина с твердыми цветами и градиентов Обзор](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>
## <a name="paint-with-a-linear-gradient"></a>Краска с линейным градиентом  
 Краска <xref:System.Windows.Media.LinearGradientBrush> области с линейным градиентом. Линейный градиент смешивает два или более цветов вдоль линии, то есть оси градиента. Для <xref:System.Windows.Media.GradientStop> указания цветов в градиенте и их положениях используются объекты.  
  
 Следующий пример <xref:System.Windows.Media.LinearGradientBrush> использует для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования <xref:System.Windows.Shapes.Rectangle>. На следующей иллюстрации изображен окрашенный прямоугольник.  
  
 ![Прямоугольник, закрашенный с помощью LinearGradientBrush](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
Прямоугольник, окрашенный с помощью линейнойГрадентной щетки  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Для получения дополнительной <xref:System.Windows.Media.LinearGradientBrush> информации о классе, см [Картина с твердыми цветами и градиентов Обзор](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>
## <a name="paint-with-a-radial-gradient"></a>Краска с радиальным градиентом  
 Краска <xref:System.Windows.Media.RadialGradientBrush> области с радиальным градиентом. Радиальный градиент смешивает два или более цветов по кругу. Как и <xref:System.Windows.Media.LinearGradientBrush> в классе, вы используете <xref:System.Windows.Media.GradientStop> объекты для определения цветов в градиенте и их положения.  
  
 Следующий пример <xref:System.Windows.Media.RadialGradientBrush> использует для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования <xref:System.Windows.Shapes.Rectangle>. На следующей иллюстрации изображен окрашенный прямоугольник.  
  
 ![Прямоугольник, закрашенный с использованием RadialGradientBrush](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
Прямоугольник, окрашенный с помощью РадиалГрадientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Для получения дополнительной <xref:System.Windows.Media.RadialGradientBrush> информации о классе, см [Картина с твердыми цветами и градиентов Обзор](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>
## <a name="paint-with-an-image"></a>Краска с изображением  
 Краска <xref:System.Windows.Media.ImageBrush> области с <xref:System.Windows.Media.ImageSource>.  
  
 Следующий пример <xref:System.Windows.Media.ImageBrush> использует для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования <xref:System.Windows.Shapes.Rectangle>. На следующей иллюстрации изображен окрашенный прямоугольник.  
  
 ![Прямоугольник, созданный при помощи ImageBrush](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
Прямоугольник, окрашенный с помощью изображения  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Для получения дополнительной <xref:System.Windows.Media.ImageBrush> информации о классе, см [Картина с изображениями, рисунки и визуальные эффекты](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>
## <a name="paint-with-a-drawing"></a>Краска с рисунком  
 Красит <xref:System.Windows.Media.DrawingBrush> область с <xref:System.Windows.Media.Drawing>. А <xref:System.Windows.Media.Drawing> может содержать формы, изображения, текст и носители.  
  
 Следующий пример <xref:System.Windows.Media.DrawingBrush> использует для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования <xref:System.Windows.Shapes.Rectangle>. На следующей иллюстрации изображен окрашенный прямоугольник.  
  
 ![Прямоугольник, закрашенный с помощью DrawingBrush](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
Прямоугольник, окрашенный с помощью чертежной щетки  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Для получения дополнительной <xref:System.Windows.Media.DrawingBrush> информации о классе, см [Картина с изображениями, рисунки и визуальные эффекты](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>
## <a name="paint-with-a-visual"></a>Краска с визуальным  
 Нарисована <xref:System.Windows.Media.VisualBrush> область с <xref:System.Windows.Media.Visual> объектом. Примеры визуальных <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Page>объектов <xref:System.Windows.Controls.MediaElement>включают, и . Также <xref:System.Windows.Media.VisualBrush> позволяет проецировать содержимое из одной части приложения в другую область; это очень полезно для создания эффектов отражения и увеличительные части экрана.  
  
 Следующий пример <xref:System.Windows.Media.VisualBrush> использует для <xref:System.Windows.Shapes.Shape.Fill%2A> рисования <xref:System.Windows.Shapes.Rectangle>. На следующей иллюстрации изображен окрашенный прямоугольник.  
  
 ![Прямоугольник, закрашенный с использованием VisualBrush](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
Прямоугольник, окрашенный с помощью VisualBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Для получения дополнительной <xref:System.Windows.Media.VisualBrush> информации о классе, см [Картина с изображениями, рисунки и визуальные эффекты](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>
## <a name="paint-using-predefined-and-system-brushes"></a>Краска с помощью предопределенных и системных кистей  
 Для удобства Фонд презентации Windows (WPF) предоставляет набор предопределенных и системных кистей, которые можно использовать для покраски объектов.  
  
- Список доступных предопределенных кистей см. <xref:System.Windows.Media.Brushes> Например, с указанием того, как использовать предопределенную кисть, [см.](how-to-paint-an-area-with-a-solid-color.md)  
  
- Список доступных системных кистей см. <xref:System.Windows.SystemColors> Например, [см. Paint an Area с помощью системной кисти.](how-to-paint-an-area-with-a-system-brush.md)  
  
<a name="commonbrushfeatures"></a>
## <a name="common-brush-features"></a>Общие особенности кисти  
 <xref:System.Windows.Media.Brush>объекты <xref:System.Windows.Media.Brush.Opacity%2A> обеспечивают свойство, которое может быть использовано для того, чтобы сделать кисть прозрачной или частично прозрачной. Значение <xref:System.Windows.Media.Brush.Opacity%2A> 0 делает кисть полностью <xref:System.Windows.Media.Brush.Opacity%2A> прозрачной, в то время как значение 1 делает кисть полностью непрозрачной. В следующем примере <xref:System.Windows.Media.Brush.Opacity%2A> свойство <xref:System.Windows.Media.SolidColorBrush> делает 25 процентов непрозрачным.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Если кисть содержит частично прозрачные цвета, то непрозрачность цвета сочетается с умножением с непрозрачностью качества кисти. Например, если кисть имеет значение непрозрачности 0,5, а цвет, используемый в кисти, также имеет значение непрозрачности 0,5, выходной цвет имеет значение непрозрачности 0,25.  
  
> [!NOTE]
> Более эффективно изменять непрозрачность кисти, чем изменять непрозрачность всего элемента, используя <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> ее свойство.  
  
 Вы можете поворачивать, масштабировать, исказить и перевести <xref:System.Windows.Media.Brush.Transform%2A> <xref:System.Windows.Media.Brush.RelativeTransform%2A> содержимое кисти, используя ее или свойства. Для получения дополнительной информации смотрите [обзор трансформации кисти](brush-transformation-overview.md).  
  
 Поскольку <xref:System.Windows.Media.Animation.Animatable> они <xref:System.Windows.Media.Brush> являются объектами, объекты могут быть анимированы. Для получения дополнительной информации [см.](animation-overview.md)  
  
<a name="freezable_features"></a>
### <a name="freezable-features"></a>Возможности объектов Freezable  
 Поскольку класс наследует <xref:System.Windows.Freezable> из <xref:System.Windows.Media.Brush> класса, он <xref:System.Windows.Media.Brush> предоставляет несколько специальных функций: объекты могут быть объявлены в качестве [ресурсов,](../../../desktop-wpf/fundamentals/xaml-resources-define.md)общими между несколькими объектами и клонированы. Кроме того, <xref:System.Windows.Media.Brush> все <xref:System.Windows.Media.VisualBrush> типы, кроме, могут быть сделаны только для чтения, чтобы повысить производительность и сделать поток безопасным.  
  
 Для получения дополнительной информации <xref:System.Windows.Freezable> о различных функциях, предоставляемых объектами, см. [Freezable Objects Overview](../advanced/freezable-objects-overview.md)  
  
 Для получения дополнительной <xref:System.Windows.Media.VisualBrush> информации о том, почему объекты не могут быть заморожены, см. <xref:System.Windows.Media.VisualBrush>  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [Общие сведения о закраске сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md)
- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
- [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md)
- [Пример использования кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
- [Пример использования ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [Пример использования VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
- [Как-к темам](brushes-how-to-topics.md)
- [Дополнительные рекомендации по повышению производительности](../advanced/optimizing-performance-other-recommendations.md)
