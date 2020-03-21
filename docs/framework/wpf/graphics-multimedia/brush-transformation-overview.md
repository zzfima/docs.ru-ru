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
ms.openlocfilehash: deac1be2fd19703055b76af8173111b4453f0d6b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186519"
---
# <a name="brush-transformation-overview"></a>Общие сведения о преобразованиях объекта Brush
Класс brush предоставляет два <xref:System.Windows.Media.Brush.Transform%2A> свойства <xref:System.Windows.Media.Brush.RelativeTransform%2A>преобразования: и . Эти свойства позволяют выполнять поворот, масштабирование, наклон и преобразовывать содержимое кисти. В этом разделе описываются различия между этими двумя свойствами и приводятся примеры их использования.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы разобраться в этом разделе, пользователь должен понимать возможности преобразуемой кисти. Для <xref:System.Windows.Media.LinearGradientBrush> <xref:System.Windows.Media.RadialGradientBrush>и , [см. Картина с твердыми цветами и градиентов Обзор](painting-with-solid-colors-and-gradients-overview.md). Для <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush>, или , см. [Картина с изображениями, рисунки, и визуальные эффекты](painting-with-images-drawings-and-visuals.md). Также необходимо иметь представление о двумерных преобразованиях, описанных в разделе [Общие сведения о преобразованиях](transforms-overview.md).  
  
<a name="transformversusrelativetransform"></a>
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Различия между свойствами Transform и RelativeTransform  
 При применении преобразования к <xref:System.Windows.Media.Brush.Transform%2A> свойству кисти необходимо знать размер окрашенной области, если вы хотите преобразовать содержимое кисти в ее центре. Предположим, что область рисования имеет ширину 200 аппаратно-независимых пикселей и высоту 150 пикселей.  Если бы <xref:System.Windows.Media.RotateTransform> вы использовали для вращения вывода кисти на 45 градусов <xref:System.Windows.Media.RotateTransform.CenterX%2A> по центру, <xref:System.Windows.Media.RotateTransform.CenterY%2A> вы бы дали <xref:System.Windows.Media.RotateTransform> 100 и 75.  
  
 При нанесении преобразования к <xref:System.Windows.Media.Brush.RelativeTransform%2A> свойству кисти этот преобразование наносится на кисть до того, как ее выход будет отображен в окрашенную область. Следующий список описывает порядок обработки и преобразования содержимого кисти.  
  
1. Обработка содержимого кисти. Для <xref:System.Windows.Media.GradientBrush>, это означает определение области градиента. Для <xref:System.Windows.Media.TileBrush>, <xref:System.Windows.Media.TileBrush.Viewbox%2A> отображается на <xref:System.Windows.Media.TileBrush.Viewport%2A>. Это становится результатом работы кисти.  
  
2. Проекция результата работы кисти на прямоугольник преобразования 1 x 1.  
  
3. Нанесите <xref:System.Windows.Media.Brush.RelativeTransform%2A>кисть, если она есть.  
  
4. Проекция преобразованного результата работы на закрашиваемую область.  
  
5. Нанесите <xref:System.Windows.Media.Transform>кисть, если она есть.  
  
 Поскольку <xref:System.Windows.Media.Brush.RelativeTransform%2A> значение кисти применяется в то время, когда выход кисти отображается на прямоугольнике 1 х 1, значение преобразования и смещения значений кажутся относительными. Например, если вы <xref:System.Windows.Media.RotateTransform> использовали для вращения вывода кисти на 45 градусов <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform.CenterX%2A> по центру, <xref:System.Windows.Media.RotateTransform.CenterY%2A> вы бы дали 0,5 и 0,5.  
  
 На следующей иллюстрации показан выход нескольких кистей, которые были <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A> повернуты на 45 градусов с использованием и свойств.  
  
 ![Свойства RelativeTransform и Transform](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>
## <a name="using-relativetransform-with-a-tilebrush"></a>Использование RelativeTransform с TileBrush  
 Поскольку щетки плитки являются более сложными, чем другие кисти, применение <xref:System.Windows.Media.Brush.RelativeTransform%2A> к одному может привести к неожиданным результатам. Например, рассмотрим следующий рисунок.  
  
 ![Исходное изображение](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 В следующем примере <xref:System.Windows.Media.ImageBrush> используется для нарисования прямоугольной области с предыдущим изображением. Он <xref:System.Windows.Media.RotateTransform> применяется к <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.Brush.RelativeTransform%2A> свойству объекта, и <xref:System.Windows.Media.TileBrush.Stretch%2A> устанавливает <xref:System.Windows.Media.Stretch.UniformToFill>его свойство, которое должно сохранить соотношение сторон изображения, когда он растягивается, чтобы полностью заполнить прямоугольник.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 В примере получается следующий вывод.  
  
 ![Преобразованный вывод](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Обратите внимание, что изображение искажено, даже <xref:System.Windows.Media.TileBrush.Stretch%2A> если <xref:System.Windows.Media.Stretch.UniformToFill>кисть была установлена на . Это потому, что относительная трансформация <xref:System.Windows.Media.TileBrush.Viewbox%2A> применяется после <xref:System.Windows.Media.TileBrush.Viewport%2A>кисти отображается на его . В следующем списке описан каждый шаг процесса:  
  
1. Проект содержимое кисти (<xref:System.Windows.Media.TileBrush.Viewbox%2A>) на<xref:System.Windows.Media.TileBrush.Viewport%2A>его базовую <xref:System.Windows.Media.TileBrush.Stretch%2A> плитку ( ) с помощью настройки кисти.  
  
     ![Растянуть Viewbox для соответствия окну просмотра](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. Проекция базового мозаичного элемента на прямоугольник преобразования 1 x 1.  
  
     ![Сопоставление окна просмотра к преображение прямоугольника](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. Применить <xref:System.Windows.Media.RotateTransform>.  
  
     ![Применить относительное преображение](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. Проекция преобразованного базового мозаичного элемента на закрашиваемую область.  
  
     ![Спроецировать преобразованную кисть на закрашиваемую область](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Пример. Поворот ImageBrush на 45 градусов  
 Следующий пример применяется <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.Brush.RelativeTransform%2A> к свойству <xref:System.Windows.Media.ImageBrush>. Свойства <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform.CenterX%2A> объекта и <xref:System.Windows.Media.RotateTransform.CenterY%2A> свойства установлены на 0,5, относительные координаты центральной точки содержимого. В результате содержимое кисти поворачивается относительно ее центра.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Следующий пример также <xref:System.Windows.Media.RotateTransform> применяется <xref:System.Windows.Media.ImageBrush>к , <xref:System.Windows.Media.Brush.Transform%2A> но использует <xref:System.Windows.Media.Brush.RelativeTransform%2A> свойство вместо свойства. Чтобы повернуть кисть о <xref:System.Windows.Media.RotateTransform> ее центре, объект <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> должны быть установлены в абсолютных координат. Так как прямоугольник, закрашиваемый с помощью кисти, имеет размеры 175 на 90 пикселей, его центральная точка будет иметь координаты (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 На следующей иллюстрации показана кисть без <xref:System.Windows.Media.Brush.RelativeTransform%2A> преобразования, с преобразованием, <xref:System.Windows.Media.Brush.Transform%2A> нанесенным на свойство, и с преобразованием, нанесенным на свойство.  
  
 ![Параметры кисти RelativeTransform и Transform](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Данный пример является частью большого примера. Для полного образца [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)см. Более подробные сведения о кистях см. в разделе [Общие сведения о кистях WPF](wpf-brushes-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [Общие сведения о закраске сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md)
- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
- [Общие сведения о классах Transform](transforms-overview.md)
