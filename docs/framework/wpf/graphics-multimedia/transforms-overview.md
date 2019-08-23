---
title: Общие сведения о классах Transform
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2-D transform
- transform classes [WPF], 2-D
- 2-D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: 89b781d3e5b88a66598a301a1d08cf7dfedd57a5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962902"
---
# <a name="transforms-overview"></a>Общие сведения о классах Transform
В этом разделе описывается, как использовать двумерные <xref:System.Windows.Media.Transform> классы для вращения, масштабирования, перемещения (преобразования) и наклона <xref:System.Windows.FrameworkElement> объектов.  

<a name="whatIsATransformSection"></a>   
## <a name="what-is-a-transform"></a>Что такое преобразование?  
 <xref:System.Windows.Media.Transform> Определяет, как сопоставлять или преобразовывать точки из одного пространства координат в другое пространство координат. Это сопоставление описывается преобразованием <xref:System.Windows.Media.Matrix>, которое представляет собой коллекцию из трех строк с тремя <xref:System.Double> столбцами значений.  
  
> [!NOTE]
> В Windows Presentation Foundation (WPF) используются основные матрицы строк. Векторы представляют собой массивы на основе строк, а не на основе столбцов.  
  
 В следующей таблице показана структура матрицы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="a-2-d-transformation-matrix"></a>Матрица двумерного преобразования  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> По умолчанию: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> По умолчанию: 0,0|0,0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> По умолчанию: 0,0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> По умолчанию: 1.0|0,0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> По умолчанию: 0,0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> По умолчанию: 0,0|1.0|  
  
 Изменяя значения элементов матрицы, можно поворачивать, масштабировать, наклонять и перемещать объект. Например, если изменить значение в первом столбце третьей строки ( <xref:System.Windows.Media.Matrix.OffsetX%2A> значение) на 100, можно использовать его для перемещения объектов 100 по оси x. Если изменить значение во втором столбце второй строки на 3, можно использовать его для растяжения объекта в три раза больше по сравнению с текущим размером. Если изменить оба значения, объект будет перемещен на 100 единиц по оси X, а его ширина будет увеличена в 3 раза. Поскольку Windows Presentation Foundation (WPF) поддерживает только аффинное преобразование, значения в правом столбце всегда имеют значение 0, 0, 1.  
  
 Хотя Windows Presentation Foundation (WPF) позволяет напрямую манипулировать значениями матрицы, она также предоставляет несколько <xref:System.Windows.Media.Transform> классов, позволяющих преобразовывать объект, не зная, как настроена базовая структура матрицы. Например, <xref:System.Windows.Media.ScaleTransform> класс позволяет масштабировать объект, устанавливая его <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> свойства и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> , вместо того чтобы манипулировать матрицей преобразования. Аналогичным <xref:System.Windows.Media.RotateTransform.Angle%2A> образом класспозволяетповорачиватьобъект,простоустанавливая<xref:System.Windows.Media.RotateTransform> его свойство.  
  
<a name="transformClassesSection"></a>   
## <a name="transform-classes"></a>Классы преобразования  
 Windows Presentation Foundation (WPF) предоставляет следующие двумерные <xref:System.Windows.Media.Transform> классы для общих операций преобразования:  
  
|Класс|Описание|Пример|Рисунки|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Поворачивает элемент на указанный <xref:System.Windows.Media.RotateTransform.Angle%2A>объект.|[Вращение объекта](how-to-rotate-an-object.md)|![Иллюстрация вращения](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Масштабирует элемент по заданному <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> сумме.|[Масштабирование элемента](how-to-scale-an-element.md)|![Иллюстрация масштабирования](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Наклоняет элемент на указанные <xref:System.Windows.Media.SkewTransform.AngleX%2A> величины и. <xref:System.Windows.Media.SkewTransform.AngleY%2A>|[Наклон элемента](how-to-skew-an-element.md)|![Иллюстрация наклона](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Перемещает (преобразует) элемент по заданному <xref:System.Windows.Media.TranslateTransform.X%2A> и <xref:System.Windows.Media.TranslateTransform.Y%2A> сумме.|[Перемещение элемента](how-to-translate-an-element.md)|![Иллюстрация перемещения](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Для создания более сложных преобразований Windows Presentation Foundation (WPF) предоставляет следующие два класса:  
  
|Класс|Описание|Пример|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Группирует несколько <xref:System.Windows.Media.TransformGroup> объектов в один <xref:System.Windows.Media.Transform> , который затем можно применить к свойствам преобразования.|[Применение нескольких преобразований к объекту](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Создает пользовательские преобразования, которые не предоставляются другими <xref:System.Windows.Media.Transform> классами. При использовании <xref:System.Windows.Media.MatrixTransform>, вы напрямую управляете матрицей.|[Использование MatrixTransform для создания пользовательских преобразований](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF) также предоставляет трехмерные преобразования. Дополнительные сведения см. в описании класса <xref:System.Windows.Media.Media3D.Transform3D>.  
  
<a name="transformationproperties"></a>   
## <a name="common-transformation-properties"></a>Общие свойства преобразования  
 Один из способов преобразования объекта — объявить соответствующий <xref:System.Windows.Media.Transform> тип и применить его к свойству преобразования объекта. У различных типов объектов есть различные типы свойств преобразования. В следующей таблице перечислены несколько часто используемых типов Windows Presentation Foundation (WPF) и их свойства преобразования.  
  
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
 При преобразовании объекта преобразуется не только объект, но и пространство координат, в котором он существует. По умолчанию преобразование выравнивается по центру в источнике системы координат целевого объекта: (0, 0). Единственное исключение — <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Media.TranslateTransform> . свойство не имеет свойства центра, которое можно задать, так как результат перевода одинаков, независимо от того, где он находится в центре.  
  
 В следующем примере используется <xref:System.Windows.Media.RotateTransform> для <xref:System.Windows.Shapes.Rectangle> поворота <xref:System.Windows.FrameworkElement>элемента, типа, на 45 градусов относительно центра по умолчанию, (0, 0). На следующем рисунке показан результат поворота.  
  
 ![Объект FrameworkElement, повернутый на &#40;45 градусов относительно&#41; 0, 0](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Элемент Rectangle, повернутый на 45 градусов относительно точки (0,0)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 По умолчанию элемент поворачивается относительно левого верхнего угла: (0, 0). Классы <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.ScaleTransform> и<xref:System.Windows.Media.SkewTransform> предоставляют свойства CenterX и Center, позволяющие указать точку, в которой применяется преобразование.  
  
 В следующем примере также используется <xref:System.Windows.Media.RotateTransform> для <xref:System.Windows.Shapes.Rectangle> поворота элемента на 45 градусов, <xref:System.Windows.Media.RotateTransform.CenterX%2A> но на этот раз задаются свойства <xref:System.Windows.Media.RotateTransform.CenterY%2A> и, чтобы у объекта <xref:System.Windows.Media.RotateTransform> был центр (25, 25). На следующем рисунке показан результат поворота.  
  
 ![Геометрическая геометрия, повернутая на 45 градусов по &#40;25, 25&#41; ](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Элемент Rectangle, повернутый на 45 градусов относительно точки (25, 25)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## <a name="transforming-a-frameworkelement"></a>Преобразование элемента FrameworkElement  
 Чтобы применить преобразования к <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Media.Transform> создайте и примените его к одному из двух свойств, <xref:System.Windows.FrameworkElement> предоставляемых классом.  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A>— Преобразование, которое применяется перед проходом макета. После применения преобразования система разметки обрабатывает преобразованные размер и положение элемента.  
  
- <xref:System.Windows.UIElement.RenderTransform%2A>— Преобразование, изменяющее внешний вид элемента, но применяемое после завершения прохода макета. Используя <xref:System.Windows.UIElement.RenderTransform%2A> свойство вместо <xref:System.Windows.FrameworkElement.LayoutTransform%2A> свойства, можно получить преимущества производительности.  
  
 Какое свойство следует использовать? Из-за преимуществ производительности, предоставляемых ею, используйте <xref:System.Windows.UIElement.RenderTransform%2A> свойство везде, где это возможно, особенно при <xref:System.Windows.Media.Transform> использовании анимированных объектов. <xref:System.Windows.FrameworkElement.LayoutTransform%2A> Используйте свойство при масштабировании, повороте или наклоне, и необходимо, чтобы родительский элемент элемента подпревратился в преобразованный размер элемента. Обратите внимание, что при использовании со <xref:System.Windows.FrameworkElement.LayoutTransform%2A> <xref:System.Windows.Media.TranslateTransform> свойством объекты не оказывают влияния на элементы. Это вызвано тем, что система разметки возвращает преобразуемый элемент в исходное положение в ходе обработки.  
  
 Дополнительные сведения о разметке в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] см. в разделе [Общие сведения о разметке](../advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Пример Поворот элемента FrameworkElement 45 градусов  
 В следующем примере используется <xref:System.Windows.Media.RotateTransform> для поворота кнопки по часовой стрелке на 45 градусов. Кнопка содержится в элементе <xref:System.Windows.Controls.StackPanel> с двумя другими кнопками.  
  
 По умолчанию объект <xref:System.Windows.Media.RotateTransform> вращается вокруг точки (0, 0). Так как в примере не задана центральная точка, то кнопка поворачивается вокруг точки (0, 0), т. е. левого верхнего угла. <xref:System.Windows.Media.RotateTransform> Атрибут применяется ксвойству<xref:System.Windows.UIElement.RenderTransform%2A> . На рисунке ниже показан результат преобразования.  
  
 ![Кнопка, преобразованная с помощью RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Поворот на 45 градусов по часовой стрелке вокруг левого верхнего угла  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 В следующем примере также используется <xref:System.Windows.Media.RotateTransform> для поворота кнопки 45 градусов по часовой стрелке, но она также <xref:System.Windows.UIElement.RenderTransformOrigin%2A> задает для кнопки значение (0,5, 0,5). Значение <xref:System.Windows.UIElement.RenderTransformOrigin%2A> свойства определяется относительно размера кнопки. В результате кнопка поворачивается вокруг центра, а не вокруг левого верхнего угла. На рисунке ниже показан результат преобразования.  
  
 ![Кнопка, преобразованная относительно ее центра](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Поворот на 45 градусов по часовой стрелке вокруг центра  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 В следующем примере для поворота <xref:System.Windows.FrameworkElement.LayoutTransform%2A> кнопки используется свойство вместо <xref:System.Windows.UIElement.RenderTransform%2A> свойства.  При этом преобразование влияет на разметку кнопки, что приводит к запуску полного прохода системы разметки. Так как размер кнопки был изменен, то после поворота кнопки также изменяется ее положение. На рисунке ниже показан результат преобразования.  
  
 ![Кнопка, преобразованная с помощью LayoutTransform](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
Поворот кнопки с использованием LayoutTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## <a name="animating-transformations"></a>Анимация преобразований  
 Поскольку они наследуются <xref:System.Windows.Media.Animation.Animatable> от класса <xref:System.Windows.Media.Transform> , классы можно анимировать. Чтобы анимировать <xref:System.Windows.Media.Transform>, примените анимацию совместимого типа к свойству, которое необходимо анимировать.  
  
 В следующем примере с помощью <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.DoubleAnimation> и <xref:System.Windows.Media.RotateTransform> используется объект для создания <xref:System.Windows.Controls.Button> регулятора на месте при щелчке.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Полный пример см. в разделе [Примеры двумерных преобразований](https://go.microsoft.com/fwlink/?LinkID=158252). Дополнительные сведения об анимации см. в разделе [Общие сведения об эффектах анимации](animation-overview.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Возможности объектов Freezable  
 Поскольку он наследуется от <xref:System.Windows.Freezable> класса <xref:System.Windows.Media.Transform> , класс предоставляет несколько специальных функций: <xref:System.Windows.Media.Transform> объекты могут быть объявлены как [ресурсы](../advanced/xaml-resources.md), совместно используемые несколькими объектами, сделаны доступными только для чтения для повышения производительности, клонирования и является потокобезопасным. Дополнительные сведения о различных функциях, предоставляемых <xref:System.Windows.Freezable> объектами, см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [Разделы практического руководства](transformations-how-to-topics.md)
- [Пример двумерных преобразований](https://go.microsoft.com/fwlink/?LinkID=158252)
