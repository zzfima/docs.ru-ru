---
title: Общие сведения о классах Transform
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2D transform
- transform classes [WPF], 2D
- 2D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: c5f29404a301eb023ff24b2890531dede6440ec4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111963"
---
# <a name="transforms-overview"></a>Общие сведения о классах Transform
В этой теме описывается, как использовать 2D-классы <xref:System.Windows.Media.Transform> для <xref:System.Windows.FrameworkElement> вращения, масштабирования, перемещения (перевода) и перекоса объектов.  

<a name="whatIsATransformSection"></a>
## <a name="what-is-a-transform"></a>Что такое преобразование?  
 A <xref:System.Windows.Media.Transform> определяет, как отображать или трансформировать точки из одного пространства координат в другое пространство координат. Это отображение <xref:System.Windows.Media.Matrix>описывается преобразованием, которое представляет собой <xref:System.Double> набор из трех строк с тремя столбцов значениями.  
  
> [!NOTE]
> Фонд презентации Windows (WPF) использует матрицы для крупных строк. Векторы представляют собой массивы на основе строк, а не на основе столбцов.  
  
 В следующей таблице показана структура матрицы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="a-2d-transformation-matrix"></a>Матрица 2D-трансформации  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> По умолчанию: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> По умолчанию: 0.0|0,0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> По умолчанию: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> По умолчанию: 1.0|0,0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> По умолчанию: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> По умолчанию: 0.0|1.0|  
  
 Изменяя значения элементов матрицы, можно поворачивать, масштабировать, наклонять и перемещать объект. Например, если вы измените значение в первом столбце третьего ряда <xref:System.Windows.Media.Matrix.OffsetX%2A> (значение) на 100, его можно использовать для перемещения объекта 100 единиц вдоль оси x. Если изменить значение во втором столбце второй строки на 3, можно использовать его для растяжения объекта в три раза больше по сравнению с текущим размером. Если изменить оба значения, объект будет перемещен на 100 единиц по оси X, а его ширина будет увеличена в 3 раза. Поскольку Windows Presentation Foundation (WPF) поддерживает только преобразования affine, значения в правом столбце всегда 0, 0, 1.  
  
 Хотя Windows Presentation Foundation (WPF) позволяет напрямую манипулировать <xref:System.Windows.Media.Transform> значениями матрицы, он также предоставляет несколько классов, которые позволяют преобразовывать объект, не зная, как настроена базовая структура матрицы. Например, <xref:System.Windows.Media.ScaleTransform> класс позволяет масштабировать объект, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> устанавливая его и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> свойства, вместо того, чтобы манипулировать матрицей преобразования. Аналогичным <xref:System.Windows.Media.RotateTransform> образом, класс позволяет вращать объект, просто <xref:System.Windows.Media.RotateTransform.Angle%2A> установив его свойство.  
  
<a name="transformClassesSection"></a>
## <a name="transform-classes"></a>Классы преобразования  
 Фонд презентации Windows (WPF) <xref:System.Windows.Media.Transform> предоставляет следующие 2D-классы для общих операций преобразования:  
  
|Class|Описание|Пример|Рисунки|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Вращает элемент указанным. <xref:System.Windows.Media.RotateTransform.Angle%2A>|[Вращение объекта](how-to-rotate-an-object.md)|![Иллюстрация вращения](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Масштабирует элемент по <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> указанным и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> суммам.|[Масштабирование элемента](how-to-scale-an-element.md)|![Иллюстрация масштабирования](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Перекос элемента по <xref:System.Windows.Media.SkewTransform.AngleX%2A> указанным и <xref:System.Windows.Media.SkewTransform.AngleY%2A> суммам.|[Наклон элемента](how-to-skew-an-element.md)|![Иллюстрация отклонения](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Перемещает (переводит) элемент по <xref:System.Windows.Media.TranslateTransform.X%2A> указанным и <xref:System.Windows.Media.TranslateTransform.Y%2A> суммам.|[Перемещение элемента](how-to-translate-an-element.md)|![Иллюстрация изменения](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Для создания более сложных преобразований Фонд презентаций Windows (WPF) предоставляет следующие два класса:  
  
|Class|Описание|Пример|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Группирует <xref:System.Windows.Media.TransformGroup> несколько <xref:System.Windows.Media.Transform> объектов в один, который можно применить для преобразования свойств.|[Применение нескольких преобразований к объекту](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Создает пользовательские преобразования, которые не <xref:System.Windows.Media.Transform> предоставляются другими классами. Когда вы <xref:System.Windows.Media.MatrixTransform>используете, вы манипулируете матрицей напрямую.|[Использование MatrixTransform для создания пользовательских преобразований](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Фонд презентации Windows (WPF) также предоставляет 3D-трансформации. Дополнительные сведения см. в описании класса <xref:System.Windows.Media.Media3D.Transform3D>.  
  
<a name="transformationproperties"></a>
## <a name="common-transformation-properties"></a>Общие свойства преобразования  
 Одним из способов преобразования объекта <xref:System.Windows.Media.Transform> является декларирование соответствующего типа и применение его к свойству преобразования объекта. У различных типов объектов есть различные типы свойств преобразования. В следующей таблице перечислены несколько часто используемых типов Windows Presentation Foundation (WPF) и их свойства преобразования.  
  
|Тип|Свойства преобразования|  
|----------|-------------------------------|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.Brush.Transform%2A>, <xref:System.Windows.Media.Brush.RelativeTransform%2A>|  
|<xref:System.Windows.Media.ContainerVisual>|<xref:System.Windows.Media.ContainerVisual.Transform%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|  
|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.UIElement.RenderTransform%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A>|  
|<xref:System.Windows.Media.Geometry>|<xref:System.Windows.Media.Geometry.Transform%2A>|  
|<xref:System.Windows.Media.TextEffect>|<xref:System.Windows.Media.TextEffect.Transform%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.RenderTransform%2A>|  
  
<a name="transformcenter"></a>
## <a name="transformations-and-coordinate-systems"></a>Преобразования и системы координат  
 При преобразовании объекта преобразуется не только объект, но и пространство координат, в котором он существует. По умолчанию в качестве центральной точки для преобразования используется начало системы координат целевого объекта: (0, 0). Единственным исключением <xref:System.Windows.Media.TranslateTransform>является ; a <xref:System.Windows.Media.TranslateTransform> не имеет свойств центра для установки, поскольку эффект перевода одинаков независимо от того, где он находится в центре.  
  
 В следующем примере используется <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Shapes.Rectangle> для вращения элемента, типа <xref:System.Windows.FrameworkElement>, на 45 градусов о его центре по умолчанию, (0, 0). На следующем рисунке показан результат поворота.  
  
 ![Элемент FrameworkElement, повернутый на 45 градусов относительно точки (0, 0)](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Элемент Rectangle, повернутый на 45 градусов относительно точки (0,0)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 По умолчанию элемент поворачивается относительно левого верхнего угла: (0, 0). В <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.ScaleTransform>, <xref:System.Windows.Media.SkewTransform> и классы обеспечивают CenterX и CenterY свойства, которые позволяют указать точку, в которой преобразование применяется.  
  
 В следующем примере <xref:System.Windows.Media.RotateTransform> также используется <xref:System.Windows.Shapes.Rectangle> для вращения элемента на 45 градусов; однако, на <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> этот раз и <xref:System.Windows.Media.RotateTransform> свойства установлены таким образом, что имеет центр (25, 25). На следующем рисунке показан результат поворота.  
  
 ![Элемент Geometry, повернутый на 45 градусов относительно точки (25, 25)](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Элемент Rectangle, повернутый на 45 градусов относительно точки (25, 25)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>
## <a name="transforming-a-frameworkelement"></a>Преобразование элемента FrameworkElement  
 Чтобы применить преобразования <xref:System.Windows.FrameworkElement>к, <xref:System.Windows.Media.Transform> создайте и примените его <xref:System.Windows.FrameworkElement> к одному из двух свойств, которые обеспечивает класс:  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A>- Преобразование, которое применяется до прохождения макета. После применения преобразования система разметки обрабатывает преобразованные размер и положение элемента.  
  
- <xref:System.Windows.UIElement.RenderTransform%2A>- Преобразование, которое изменяет внешний вид элемента, но применяется после завершения прохода макета. Используя свойство <xref:System.Windows.UIElement.RenderTransform%2A> вместо <xref:System.Windows.FrameworkElement.LayoutTransform%2A> свойства, вы можете получить преимущества производительности.  
  
 Какое свойство следует использовать? Из-за преимуществ производительности, которые <xref:System.Windows.UIElement.RenderTransform%2A> он предоставляет, используйте свойство, когда это возможно, особенно при использовании анимированных <xref:System.Windows.Media.Transform> объектов. Используйте <xref:System.Windows.FrameworkElement.LayoutTransform%2A> свойство при масштабировании, повороте или перекосе, и вам нужно, чтобы родитель элемента приспособился к преобразованного размера элемента. Обратите внимание, что, когда <xref:System.Windows.FrameworkElement.LayoutTransform%2A> они <xref:System.Windows.Media.TranslateTransform> используются с свойством, объекты, как представляется, не влияют на элементы. Это вызвано тем, что система разметки возвращает преобразуемый элемент в исходное положение в ходе обработки.  
  
 Дополнительные сведения о разметке в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] см. в разделе [Общие сведения о разметке](../advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Пример: поворот элемента FrameworkElement на 45 градусов  
 В следующем примере <xref:System.Windows.Media.RotateTransform> используется для поворота кнопки по часовой стрелке на 45 градусов. Кнопка содержится <xref:System.Windows.Controls.StackPanel> в двух других кнопках.  
  
 По умолчанию, <xref:System.Windows.Media.RotateTransform> вращается вокруг точки (0, 0). Так как в примере не задана центральная точка, то кнопка поворачивается вокруг точки (0, 0), т. е. левого верхнего угла. Применяется <xref:System.Windows.Media.RotateTransform> к <xref:System.Windows.UIElement.RenderTransform%2A> свойству. На рисунке ниже показан результат преобразования.  
  
 ![Кнопка, преобразованная с использованием RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Поворот на 45 градусов по часовой стрелке вокруг левого верхнего угла  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 Следующий пример также <xref:System.Windows.Media.RotateTransform> использует для поворота кнопки 45 градусов <xref:System.Windows.UIElement.RenderTransformOrigin%2A> по часовой стрелке, но он также устанавливает кнопку (0,5, 0,5). Значение <xref:System.Windows.UIElement.RenderTransformOrigin%2A> свойства относительно размера кнопки. В результате кнопка поворачивается вокруг центра, а не вокруг левого верхнего угла. На рисунке ниже показан результат преобразования.  
  
 ![Кнопка, преобразованная относительно центра](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Поворот на 45 градусов по часовой стрелке вокруг центра  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 В следующем примере <xref:System.Windows.FrameworkElement.LayoutTransform%2A> вместо <xref:System.Windows.UIElement.RenderTransform%2A> свойства используется свойство для поворота кнопки.  При этом преобразование влияет на разметку кнопки, что приводит к запуску полного прохода системы разметки. Так как размер кнопки был изменен, то после поворота кнопки также изменяется ее положение. На рисунке ниже показан результат преобразования.  
  
 ![Кнопка, преобразованная с использованием LayoutTransform](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
Поворот кнопки с использованием LayoutTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>
## <a name="animating-transformations"></a>Анимация преобразований  
 Поскольку они <xref:System.Windows.Media.Animation.Animatable> наследуют <xref:System.Windows.Media.Transform> из класса, классы могут быть анимированы. Чтобы оживить анимацию <xref:System.Windows.Media.Transform>совместимого типа, к свойству, который вы хотите оживить.  
  
 Следующий пример <xref:System.Windows.Media.Animation.Storyboard> использует <xref:System.Windows.Media.Animation.DoubleAnimation> a <xref:System.Windows.Media.RotateTransform> и a, чтобы сделать <xref:System.Windows.Controls.Button> спин на месте, когда он нажал.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms) Дополнительные сведения об анимации см. в разделе [Общие сведения об эффектах анимации](animation-overview.md).  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Возможности объектов Freezable  
 Поскольку класс <xref:System.Windows.Freezable> наследует <xref:System.Windows.Media.Transform> несколько специальных функций: <xref:System.Windows.Media.Transform> объекты могут быть объявлены в качестве [ресурсов,](../../../desktop-wpf/fundamentals/xaml-resources-define.md)совместно распределенных между несколькими объектами, сделаны только для чтения, чтобы повысить производительность, клонировать и сделать поток безопасным. Для получения дополнительной информации о <xref:System.Windows.Freezable> различных функциях, предоставляемых объектами, см. [Freezable Objects Overview](../advanced/freezable-objects-overview.md)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [Как-к темам](transformations-how-to-topics.md)
- [2D Преобразует образец](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
