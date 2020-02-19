---
title: Общие сведения о преобразованиях объекта Brush
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], transformation properties
- properties [WPF], transformation
- transformation properties of brushes [WPF]
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
ms.openlocfilehash: 1d3a56014e0975f3616b7f90021b4290ced5daab
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453134"
---
# <a name="brush-transformation-overview"></a>Общие сведения о преобразованиях объекта Brush
Класс Brush предоставляет два свойства преобразования: <xref:System.Windows.Media.Brush.Transform%2A> и <xref:System.Windows.Media.Brush.RelativeTransform%2A>. Эти свойства позволяют выполнять поворот, масштабирование, наклон и преобразовывать содержимое кисти. В этом разделе описываются различия между этими двумя свойствами и приводятся примеры их использования.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>предварительные требования  
 Чтобы разобраться в этом разделе, пользователь должен понимать возможности преобразуемой кисти. Для <xref:System.Windows.Media.LinearGradientBrush> и <xref:System.Windows.Media.RadialGradientBrush>см. [Общие сведения о заполнении сплошными цветами и градиентами](painting-with-solid-colors-and-gradients-overview.md). Сведения о <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>или <xref:System.Windows.Media.VisualBrush>см. [в разделе Рисование с помощью изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md). Также необходимо иметь представление о двумерных преобразованиях, описанных в разделе [Общие сведения о преобразованиях](transforms-overview.md).  
  
<a name="transformversusrelativetransform"></a>   
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Различия между свойствами Transform и RelativeTransform  
 При применении преобразования к свойству <xref:System.Windows.Media.Brush.Transform%2A> кисти необходимо знать размер закрашиваемой области, если необходимо преобразовать содержимое кисти относительно ее центра. Предположим, что область рисования имеет ширину 200 аппаратно-независимых пикселей и высоту 150 пикселей.  Если вы использовали <xref:System.Windows.Media.RotateTransform> для поворота выходных данных кисти на 45 градусов относительно его центра, вы придаете <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform.CenterX%2A> 100 и <xref:System.Windows.Media.RotateTransform.CenterY%2A> 75.  
  
 При применении преобразования к свойству <xref:System.Windows.Media.Brush.RelativeTransform%2A> кисти это преобразование применяется к кисти до того, как ее выходные данные сопоставлены с закрашиваемой областью. Следующий список описывает порядок обработки и преобразования содержимого кисти.  
  
1. Обработка содержимого кисти. Для <xref:System.Windows.Media.GradientBrush>это означает определение области градиента. Для <xref:System.Windows.Media.TileBrush><xref:System.Windows.Media.TileBrush.Viewbox%2A> сопоставляется с <xref:System.Windows.Media.TileBrush.Viewport%2A>. Это становится результатом работы кисти.  
  
2. Проекция результата работы кисти на прямоугольник преобразования 1 x 1.  
  
3. Примените <xref:System.Windows.Media.Brush.RelativeTransform%2A>кисти, если таковая имеется.  
  
4. Проекция преобразованного результата работы на закрашиваемую область.  
  
5. Примените <xref:System.Windows.Media.Transform>кисти, если таковая имеется.  
  
 Поскольку <xref:System.Windows.Media.Brush.RelativeTransform%2A> применяется, когда выходные данные кисти сопоставлены с прямоугольником 1 x 1, центр преобразования и значения смещения выглядят как относительные. Например, если вы использовали <xref:System.Windows.Media.RotateTransform> для поворота выходных данных кисти на 45 градусов относительно его центра, вы придаете <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform.CenterX%2A> 0,5 и <xref:System.Windows.Media.RotateTransform.CenterY%2A> 0,5.  
  
 На следующем рисунке показаны выходные данные нескольких кистей, повернутых на 45 градусов с помощью свойств <xref:System.Windows.Media.Brush.RelativeTransform%2A> и <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 ![Свойства RelativeTransform и Transform](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>   
## <a name="using-relativetransform-with-a-tilebrush"></a>Использование RelativeTransform с TileBrush  
 Поскольку мозаичные кисти сложнее, чем другие кисти, применение <xref:System.Windows.Media.Brush.RelativeTransform%2A> к одной может привести к непредвиденным результатам. Например, рассмотрим следующий рисунок.  
  
 ![Исходное изображение](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 В следующем примере используется <xref:System.Windows.Media.ImageBrush> для рисования прямоугольной области с предыдущим изображением. Он применяет <xref:System.Windows.Media.RotateTransform> к свойству <xref:System.Windows.Media.Brush.RelativeTransform%2A> объекта <xref:System.Windows.Media.ImageBrush> и задает для его свойства <xref:System.Windows.Media.TileBrush.Stretch%2A> значение <xref:System.Windows.Media.Stretch.UniformToFill>, которое должно сохранять пропорции изображения при его растяжении для полной заливки прямоугольника.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 В примере получается следующий вывод.  
  
 ![Преобразованные выходные данные](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Обратите внимание, что изображение искажается, несмотря на то, что для <xref:System.Windows.Media.TileBrush.Stretch%2A> кисти задано значение <xref:System.Windows.Media.Stretch.UniformToFill>. Это связано с тем, что относительное преобразование применяется после сопоставления <xref:System.Windows.Media.TileBrush.Viewbox%2A> кисти с <xref:System.Windows.Media.TileBrush.Viewport%2A>. В следующем списке описан каждый шаг процесса:  
  
1. Проецировать содержимое кисти (<xref:System.Windows.Media.TileBrush.Viewbox%2A>) на ее базовый элемент (<xref:System.Windows.Media.TileBrush.Viewport%2A>), используя параметр <xref:System.Windows.Media.TileBrush.Stretch%2A> кисти.  
  
     ![Растяжение Viewbox в соответствии с окном просмотра](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. Проекция базового мозаичного элемента на прямоугольник преобразования 1 x 1.  
  
     ![Сопоставьте окно просмотра с прямоугольником преобразования](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. Примените <xref:System.Windows.Media.RotateTransform>.  
  
     ![Применение относительного преобразования](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. Проекция преобразованного базового мозаичного элемента на закрашиваемую область.  
  
     ![Проецирование преобразованной кисти на выходную область](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>   
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Пример. Поворот ImageBrush на 45 градусов  
 Следующий пример применяет <xref:System.Windows.Media.RotateTransform> к свойству <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.ImageBrush>. Свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> объекта <xref:System.Windows.Media.RotateTransform> установлены в значение 0,5, относительные координаты центральной точки содержимого. В результате содержимое кисти поворачивается относительно ее центра.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 В следующем примере также применяется <xref:System.Windows.Media.RotateTransform> к <xref:System.Windows.Media.ImageBrush>, но вместо свойства <xref:System.Windows.Media.Brush.RelativeTransform%2A> используется свойство <xref:System.Windows.Media.Brush.Transform%2A>. Чтобы повернуть кисть по центру, <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> объекта <xref:System.Windows.Media.RotateTransform> должны быть установлены в абсолютные координаты. Так как прямоугольник, закрашиваемый с помощью кисти, имеет размеры 175 на 90 пикселей, его центральная точка будет иметь координаты (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 На следующем рисунке показана кисть без преобразования, преобразование применяется к свойству <xref:System.Windows.Media.Brush.RelativeTransform%2A> и преобразование, применяемое к свойству <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 ![Параметры RelativeTransform и преобразования кисти](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Данный пример является частью большого примера. Полный пример см. в разделе [Пример использования кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Более подробные сведения о кистях см. в разделе [Общие сведения о кистях WPF](wpf-brushes-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [Общие сведения о закрашивании сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md)
- [Рисование с помощью объектов Image, Drawing и Visual](painting-with-images-drawings-and-visuals.md)
- [Общие сведения о классах Transform](transforms-overview.md)
