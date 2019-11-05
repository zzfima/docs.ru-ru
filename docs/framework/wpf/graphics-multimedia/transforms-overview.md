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
ms.openlocfilehash: ead1d114f773cba88e8b3e20f395019fbde3ee15
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458590"
---
# <a name="transforms-overview"></a>Общие сведения о классах Transform
В этом разделе описано, как использовать двумерные <xref:System.Windows.Media.Transform> классы для вращения, масштабирования, перемещения (преобразования) и наклона <xref:System.Windows.FrameworkElement> объектов.  

<a name="whatIsATransformSection"></a>   
## <a name="what-is-a-transform"></a>Что такое преобразование?  
 <xref:System.Windows.Media.Transform> определяет, как сопоставлять или преобразовывать точки из одного пространства координат в другое пространство координат. Это сопоставление описывается <xref:System.Windows.Media.Matrix>преобразования, которое представляет собой коллекцию из трех строк с тремя столбцами <xref:System.Double> значений.  
  
> [!NOTE]
> В Windows Presentation Foundation (WPF) используются основные матрицы строк. Векторы представляют собой массивы на основе строк, а не на основе столбцов.  
  
 В следующей таблице показана структура матрицы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="a-2-d-transformation-matrix"></a>Матрица двумерного преобразования  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> По умолчанию: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> По умолчанию: 0.0|0,0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> По умолчанию: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> По умолчанию: 1.0|0,0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> По умолчанию: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> По умолчанию: 0.0|1,0|  
  
 Изменяя значения элементов матрицы, можно поворачивать, масштабировать, наклонять и перемещать объект. Например, если изменить значение в первом столбце третьей строки (значение <xref:System.Windows.Media.Matrix.OffsetX%2A>) на 100, можно использовать его для перемещения объектов 100 по оси x. Если изменить значение во втором столбце второй строки на 3, можно использовать его для растяжения объекта в три раза больше по сравнению с текущим размером. Если изменить оба значения, объект будет перемещен на 100 единиц по оси X, а его ширина будет увеличена в 3 раза. Поскольку Windows Presentation Foundation (WPF) поддерживает только аффинное преобразование, значения в правом столбце всегда имеют значение 0, 0, 1.  
  
 Хотя Windows Presentation Foundation (WPF) позволяет напрямую манипулировать значениями матрицы, она также предоставляет несколько <xref:System.Windows.Media.Transform> классов, позволяющих преобразовывать объект, не зная, как настроена базовая структура матрицы. Например, класс <xref:System.Windows.Media.ScaleTransform> позволяет масштабировать объект, устанавливая его свойства <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>, вместо того, чтобы манипулировать матрицей преобразования. Аналогичным образом класс <xref:System.Windows.Media.RotateTransform> позволяет поворачивать объект, просто устанавливая его свойство <xref:System.Windows.Media.RotateTransform.Angle%2A>.  
  
<a name="transformClassesSection"></a>   
## <a name="transform-classes"></a>Классы преобразования  
 Windows Presentation Foundation (WPF) предоставляет следующие двумерные классы <xref:System.Windows.Media.Transform> для общих операций преобразования:  
  
|Class|Описание|Пример|Рисунки|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Поворачивает элемент на указанный <xref:System.Windows.Media.RotateTransform.Angle%2A>.|[Вращение объекта](how-to-rotate-an-object.md)|![Поворот иллюстрации](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Масштабирует элемент по заданному <xref:System.Windows.Media.ScaleTransform.ScaleX%2A>у и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>ным суммам.|[Масштабирование элемента](how-to-scale-an-element.md)|![Иллюстрация масштабирования](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Наклоняет элемент на указанное количество <xref:System.Windows.Media.SkewTransform.AngleX%2A> и <xref:System.Windows.Media.SkewTransform.AngleY%2A>.|[Наклон элемента](how-to-skew-an-element.md)|![Иллюстрация наклона](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Перемещает (преобразует) элемент на заданную <xref:System.Windows.Media.TranslateTransform.X%2A> и <xref:System.Windows.Media.TranslateTransform.Y%2A> суммы.|[Перемещение элемента](how-to-translate-an-element.md)|![Иллюстрация преобразования](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Для создания более сложных преобразований Windows Presentation Foundation (WPF) предоставляет следующие два класса:  
  
|Class|Описание|Пример|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Группирует несколько <xref:System.Windows.Media.TransformGroup> объектов в одну <xref:System.Windows.Media.Transform>, которую затем можно применить к свойствам преобразования.|[Применение нескольких преобразований к объекту](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Создает пользовательские преобразования, которые не предоставляются другими классами <xref:System.Windows.Media.Transform>. При использовании <xref:System.Windows.Media.MatrixTransform>вы напрямую управляете матрицей.|[Использование MatrixTransform для создания пользовательских преобразований](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF) также предоставляет трехмерные преобразования. Дополнительные сведения см. в описании класса <xref:System.Windows.Media.Media3D.Transform3D>.  
  
<a name="transformationproperties"></a>   
## <a name="common-transformation-properties"></a>Общие свойства преобразования  
 Один из способов преобразования объекта — объявить соответствующий тип <xref:System.Windows.Media.Transform> и применить его к свойству преобразования объекта. У различных типов объектов есть различные типы свойств преобразования. В следующей таблице перечислены несколько часто используемых типов Windows Presentation Foundation (WPF) и их свойства преобразования.  
  
|Type|Свойства преобразования|  
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
 При преобразовании объекта преобразуется не только объект, но и пространство координат, в котором он существует. По умолчанию в качестве центральной точки для преобразования используется начало системы координат целевого объекта: (0, 0). Единственным исключением является <xref:System.Windows.Media.TranslateTransform>. у <xref:System.Windows.Media.TranslateTransform> нет свойств центра для установки, так как результат перевода одинаков, независимо от того, где он находится в центре.  
  
 В следующем примере используется <xref:System.Windows.Media.RotateTransform> для поворота элемента <xref:System.Windows.Shapes.Rectangle>, типа <xref:System.Windows.FrameworkElement>, на 45 градусов относительно центра по умолчанию, (0, 0). На следующем рисунке показан результат поворота.  
  
 ![Элемент FrameworkElement, повернутый на 45 градусов относительно точки (0, 0)](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Элемент Rectangle, повернутый на 45 градусов относительно точки (0,0)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 По умолчанию элемент поворачивается относительно левого верхнего угла: (0, 0). Классы <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.ScaleTransform>и <xref:System.Windows.Media.SkewTransform> предоставляют свойства CenterX и Center, позволяющие указать точку, в которой применяется преобразование.  
  
 В следующем примере также используется <xref:System.Windows.Media.RotateTransform> для поворота элемента <xref:System.Windows.Shapes.Rectangle> на 45 градусов; Однако на этот раз свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> задаются так, чтобы у <xref:System.Windows.Media.RotateTransform> был центр (25, 25). На следующем рисунке показан результат поворота.  
  
 ![Элемент Geometry, повернутый на 45 градусов относительно точки (25, 25)](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Элемент Rectangle, повернутый на 45 градусов относительно точки (25, 25)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## <a name="transforming-a-frameworkelement"></a>Преобразование элемента FrameworkElement  
 Чтобы применить преобразования к <xref:System.Windows.FrameworkElement>, создайте <xref:System.Windows.Media.Transform> и примените его к одному из двух свойств, предоставляемых классом <xref:System.Windows.FrameworkElement>.  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A> — преобразование, которое применяется перед проходом макета. После применения преобразования система разметки обрабатывает преобразованные размер и положение элемента.  
  
- <xref:System.Windows.UIElement.RenderTransform%2A> — преобразование, изменяющее внешний вид элемента, но применяемое после завершения прохода макета. Используя свойство <xref:System.Windows.UIElement.RenderTransform%2A>, а не свойство <xref:System.Windows.FrameworkElement.LayoutTransform%2A>, можно получить преимущества производительности.  
  
 Какое свойство следует использовать? Из-за преимуществ производительности, предоставляемых ею, используйте свойство <xref:System.Windows.UIElement.RenderTransform%2A>, если это возможно, особенно при использовании анимированных объектов <xref:System.Windows.Media.Transform>. Используйте свойство <xref:System.Windows.FrameworkElement.LayoutTransform%2A> при масштабировании, повороте или наклоне, а также необходимо, чтобы родительский элемент элемента подпревратился в преобразованный размер элемента. Обратите внимание, что при использовании со свойством <xref:System.Windows.FrameworkElement.LayoutTransform%2A> <xref:System.Windows.Media.TranslateTransform> объекты не оказывают влияния на элементы. Это вызвано тем, что система разметки возвращает преобразуемый элемент в исходное положение в ходе обработки.  
  
 Дополнительные сведения о разметке в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] см. в разделе [Общие сведения о разметке](../advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Пример: поворот элемента FrameworkElement на 45 градусов  
 В следующем примере используется <xref:System.Windows.Media.RotateTransform> для поворота кнопки по часовой стрелке на 45 градусов. Кнопка содержится в <xref:System.Windows.Controls.StackPanel> с двумя другими кнопками.  
  
 По умолчанию <xref:System.Windows.Media.RotateTransform> поворачивается относительно точки (0, 0). Так как в примере не задана центральная точка, то кнопка поворачивается вокруг точки (0, 0), т. е. левого верхнего угла. <xref:System.Windows.Media.RotateTransform> применяется к свойству <xref:System.Windows.UIElement.RenderTransform%2A>. На рисунке ниже показан результат преобразования.  
  
 ![Кнопка, преобразованная с использованием RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Поворот на 45 градусов по часовой стрелке вокруг левого верхнего угла  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 В следующем примере также используется <xref:System.Windows.Media.RotateTransform> для поворота кнопки 45 градусов по часовой стрелке, но также устанавливается <xref:System.Windows.UIElement.RenderTransformOrigin%2A> для кнопки (0,5, 0,5). Значение свойства <xref:System.Windows.UIElement.RenderTransformOrigin%2A> задается относительно размера кнопки. В результате кнопка поворачивается вокруг центра, а не вокруг левого верхнего угла. На рисунке ниже показан результат преобразования.  
  
 ![Кнопка, преобразованная относительно центра](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Поворот на 45 градусов по часовой стрелке вокруг центра  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 В следующем примере для поворота кнопки используется свойство <xref:System.Windows.FrameworkElement.LayoutTransform%2A>, а не свойство <xref:System.Windows.UIElement.RenderTransform%2A>.  При этом преобразование влияет на разметку кнопки, что приводит к запуску полного прохода системы разметки. Так как размер кнопки был изменен, то после поворота кнопки также изменяется ее положение. На рисунке ниже показан результат преобразования.  
  
 ![Кнопка, преобразованная с использованием LayoutTransform](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
Поворот кнопки с использованием LayoutTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## <a name="animating-transformations"></a>Анимация преобразований  
 Поскольку они наследуются от класса <xref:System.Windows.Media.Animation.Animatable>, классы <xref:System.Windows.Media.Transform> могут быть анимированы. Чтобы анимировать <xref:System.Windows.Media.Transform>, примените анимацию совместимого типа к свойству, которое необходимо анимировать.  
  
 В следующем примере используется <xref:System.Windows.Media.Animation.Storyboard> и <xref:System.Windows.Media.Animation.DoubleAnimation> с <xref:System.Windows.Media.RotateTransform>, чтобы <xref:System.Windows.Controls.Button> при нажатии прокрутки.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Полный пример см. в разделе [Примеры двумерных преобразований](https://go.microsoft.com/fwlink/?LinkID=158252). Дополнительные сведения об анимации см. в разделе [Общие сведения об эффектах анимации](animation-overview.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Возможности объектов Freezable  
 Так как он наследуется от класса <xref:System.Windows.Freezable>, класс <xref:System.Windows.Media.Transform> предоставляет несколько специальных функций: <xref:System.Windows.Media.Transform> объекты могут быть объявлены как [ресурсы](../../../desktop-wpf/fundamentals/xaml-resources-define.md), совместно использоваться несколькими объектами, как доступные только для чтения, чтобы повысить производительность, клонировать и сделать потокобезопасными. Дополнительные сведения о различных функциях, предоставляемых <xref:System.Windows.Freezable> объектами, см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [Разделы практического руководства](transformations-how-to-topics.md)
- [Пример двумерных преобразований](https://go.microsoft.com/fwlink/?LinkID=158252)
