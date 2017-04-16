---
title: "Общие сведения о классах Transform | Microsoft Docs"
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
  - "классы двумерных преобразований"
  - "классы, двумерное преобразование"
  - "FrameworkElement - объекты, поворот"
  - "FrameworkElement - объекты, масштабирование"
  - "FrameworkElement - объекты, наклон"
  - "FrameworkElement - объекты, преобразование"
  - "классы преобразования, двумерные"
  - "преобразования, сведения о преобразованиях"
  - "Transform, сведения о Transform"
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Общие сведения о классах Transform
В этом разделе описывается использование класса [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> для поворота, масштабирования, сдвига и наклона объектов <xref:System.Windows.FrameworkElement>.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="whatIsATransformSection"></a>   
## Что такое Transform  
 <xref:System.Windows.Media.Transform> определяет способ сопоставления или преобразования точек из одного координатного пространства в другое.  Это сопоставление описано преобразованием <xref:System.Windows.Media.Matrix>, которое представляет собой коллекцию из трех строк с тремя столбцами, содержащую значения типа <xref:System.Double>.  
  
> [!NOTE]
>  В [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] используются матрицы, основанные на строках.  Векторы представляют собой строки, а не столбцы.  
  
 В следующей таблице показана структура матрицы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Матрица двумерного преобразования  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Значение по умолчанию: 1,0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Значение по умолчанию: 0,0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Значение по умолчанию: 0,0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Значение по умолчанию: 1,0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Значение по умолчанию: 0,0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Значение по умолчанию: 0,0|1.0|  
  
 Управляя значениями матрицы, можно поворачивать, масштабировать, наклонять и перемещать объект.  Например, изменив значения в первом столбце третьей строки \(значение <xref:System.Windows.Media.Matrix.OffsetX%2A>\) на 100, можно переместить объект на 100 единиц вдоль оси X.  Изменив значение во втором столбце второй строки на 3, можно растянуть объект в высоту в три раза от текущего размера.  Изменив оба значения, можно переместить объект на 100 единиц вдоль оси Х и растянуть в высоту в три раза от текущего размера.  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] поддерживает только сходные преобразования, поэтому значения в правом столбце всегда равны 0, 0, 1.  
  
 Не смотря на то, что [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] дает возможность непосредственно управлять значениями матрицы, она также предоставляет несколько классов <xref:System.Windows.Media.Transform>, позволяющих преобразовывать объект, не зная структуры матрицы.  Например, класс <xref:System.Windows.Media.ScaleTransform> позволяет масштабировать объект с помощью определения его свойств <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> вместо управления матрицей преобразования.  Аналогично класс <xref:System.Windows.Media.RotateTransform> позволяет повернуть объект, просто задав его свойство <xref:System.Windows.Media.RotateTransform.Angle%2A>.  
  
<a name="transformClassesSection"></a>   
## Классы Transform  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] предоставляет следующие классы [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> для общих операций преобразования:  
  
|Класс|Описание|Пример|Иллюстрация|  
|-----------|--------------|------------|-----------------|  
|<xref:System.Windows.Media.RotateTransform>|Поворачивает элемент на значение, заданное в <xref:System.Windows.Media.RotateTransform.Angle%2A>.|[Вращение объекта](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object.md)||  
|<xref:System.Windows.Media.ScaleTransform>|Масштабирует элемент, используя коэффициенты, заданные в <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>.|[Масштабирование элемента](../../../../docs/framework/wpf/graphics-multimedia/how-to-scale-an-element.md)||  
|<xref:System.Windows.Media.SkewTransform>|Наклоняет элемент на коэффициенты, заданные в <xref:System.Windows.Media.SkewTransform.AngleX%2A> и <xref:System.Windows.Media.SkewTransform.AngleY%2A>.|[Отклонение элемента](../../../../docs/framework/wpf/graphics-multimedia/how-to-skew-an-element.md)||  
|<xref:System.Windows.Media.TranslateTransform>|Сдвигает элемент на расстояние, заданное в <xref:System.Windows.Media.TranslateTransform.X%2A> и <xref:System.Windows.Media.TranslateTransform.Y%2A>.|[Смещение элемента](../../../../docs/framework/wpf/graphics-multimedia/how-to-translate-an-element.md)||  
  
 Для совершения более сложных преобразований [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] предоставляет следующие два класса:  
  
|Класс|Описание|Пример|  
|-----------|--------------|------------|  
|<xref:System.Windows.Media.TransformGroup>|Группирует несколько объектов <xref:System.Windows.Media.TransformGroup> в один объект <xref:System.Windows.Media.Transform>, к которому затем можно применять преобразования свойств.|[Применение нескольких преобразований к объекту](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Создает настраиваемые преобразования, не предоставленные другими классами <xref:System.Windows.Media.Transform>.  При использовании <xref:System.Windows.Media.MatrixTransform> происходит непосредственное управление матрицей.|[Использование MatrixTransform для создания пользовательских преобразований](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] также предоставляет возможность преобразований [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)].  Дополнительные сведения см. в описании класса <xref:System.Windows.Media.Media3D.Transform3D>.  
  
<a name="transformationproperties"></a>   
## Общие свойства преобразований  
 Одним из способов преобразования объекта является объявление соответствующего типа <xref:System.Windows.Media.Transform> и применение его к свойству преобразования объекта.  Для различных типов объектов существуют различные типы свойств преобразования.  В следующей таблице перечислены несколько часто используемых типов [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] и их свойства преобразования.  
  
|Тип|Свойства преобразования|  
|---------|-----------------------------|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.Brush.Transform%2A>, <xref:System.Windows.Media.Brush.RelativeTransform%2A>|  
|<xref:System.Windows.Media.ContainerVisual>|<xref:System.Windows.Media.ContainerVisual.Transform%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|  
|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.UIElement.RenderTransform%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A>|  
|<xref:System.Windows.Media.Geometry>|<xref:System.Windows.Media.Geometry.Transform%2A>|  
|<xref:System.Windows.Media.TextEffect>|<xref:System.Windows.Media.TextEffect.Transform%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.RenderTransform%2A>|  
  
<a name="transformcenter"></a>   
## Системы координат и преобразования  
 При преобразовании объекта происходит не просто его преобразование, а преобразование пространства координат, в котором существует объект.  По умолчанию преобразование располагается в начале системы координат целевого объекта: \(0,0\).  Единственным исключением является <xref:System.Windows.Media.TranslateTransform>; <xref:System.Windows.Media.TranslateTransform> не имеет свойства центра, так как результат преобразования не зависит от выбора центра преобразования.  
  
 В следующем примере используется класс <xref:System.Windows.Media.RotateTransform> для поворота элемента <xref:System.Windows.Shapes.Rectangle>, тип класса <xref:System.Windows.FrameworkElement>, на 45 градусов вокруг его центра по умолчанию, \(0,0\).  На следующем рисунке показан результат поворота.  
  
 ![FrameworkElement, повернутый на 45 градусов на &#40;0, 0&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm\_FE\_rotated\_about\_upperleft\_corner")  
Прямоугольный элемент, повернутый на 45 градусов относительно точки \(0,0\)  
  
 [!code-xml[Transforms_snip#TransformsFERotatedAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 По умолчанию элемент поворачивается вокруг верхнего левого угла, \(0,0\).  Класс <xref:System.Windows.Media.RotateTransform>, класс <xref:System.Windows.Media.ScaleTransform> и класс <xref:System.Windows.Media.SkewTransform> предоставляют свойства CenterX и CenterY, которые позволяют указать точку, в которой применяется преобразование.  
  
 В следующем примере также используется класс <xref:System.Windows.Media.RotateTransform> для поворота элемента <xref:System.Windows.Shapes.Rectangle> на 45 градусов; однако, в этом случае свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> заданы так, что класс <xref:System.Windows.Media.RotateTransform> имеет центр \(25, 25\).  На следующем рисунке показан результат поворота.  
  
 ![Геометрическая фигура, повернутая на 45 градусов относительно точки &#40;25, 25&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-center.png "graphicsmm\_FE\_rotated\_about\_center")  
Прямоугольный элемент, повернутый на 45 градусов относительно точки \(25, 25\)  
  
 [!code-xml[Transforms_snip#TransformsFERotatedAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## Преобразование FrameworkElement  
 Чтобы применить преобразования к <xref:System.Windows.FrameworkElement>, создайте <xref:System.Windows.Media.Transform> и примените его к одному из двух свойств, предоставленных классом <xref:System.Windows.FrameworkElement>:  
  
-   <xref:System.Windows.FrameworkElement.LayoutTransform%2A> – преобразование, применяемое перед проходом разметки.  После применения преобразования система макета обрабатывает преобразованные размер и положение элемента.  
  
-   <xref:System.Windows.UIElement.RenderTransform%2A> – преобразование, которое изменяет положение элемента, но применяется после завершения прохода разметки.  Используя свойства <xref:System.Windows.UIElement.RenderTransform%2A> вместо свойства <xref:System.Windows.FrameworkElement.LayoutTransform%2A>, можно увеличить производительность системы.  
  
 Какое свойство следует использовать?  Ввиду предоставляемого повышения производительности используйте свойство <xref:System.Windows.UIElement.RenderTransform%2A> везде, где это возможно, особенно при использовании анимированных объектов <xref:System.Windows.Media.Transform>.  При масштабировании, повороте или наклоне применяется свойство <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Также требуется, чтобы родитель изменяемого элемента изменил свой размер в соответствии с изменениями своего дочернего элемента.  Обратите внимание, что при использовании совместно со свойством <xref:System.Windows.FrameworkElement.LayoutTransform%2A> объекты <xref:System.Windows.Media.TranslateTransform> не вызывают видимых изменений в элементах.  Это происходит потому, что, в ходе преобразования, система макета возвращает преобразуемый элемент на его исходную позицию.  
  
 Дополнительные сведения о макетах [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] см. в разделе общих сведений [Макет](../../../../docs/framework/wpf/advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## Пример: Поворот элемента FrameworkElement на 45 градусов  
 В следующем примере используется класс <xref:System.Windows.Media.RotateTransform> для поворота кнопки на 45 градусов по часовой стрелке.  Кнопка содержится в классе <xref:System.Windows.Controls.StackPanel>, который имеет две другие кнопки.  
  
 По умолчанию класс <xref:System.Windows.Media.RotateTransform>, поворачивается вокруг точки \(0, 0\).  Поскольку в примере не задано значение центра, кнопка поворачивается вокруг точки \(0, 0\), то есть верхнего левого угла.  <xref:System.Windows.Media.RotateTransform> применяется к свойству <xref:System.Windows.UIElement.RenderTransform%2A>.  На следующей иллюстрации показан результат выполнения преобразования.  
  
 ![Преобразованная кнопка с использованием RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm\_RenderTransformWithDefaultCenter")  
Поворот по часовой стрелке на 45 градусов относительно левого верхнего угла  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 В следующем примере также используется класс <xref:System.Windows.Media.RotateTransform> для поворота кнопки на 45 градусов по часовой стрелке, а также задает значение \(0,5,0,5\) свойству кнопки <xref:System.Windows.UIElement.RenderTransformOrigin%2A>.  Значение свойства <xref:System.Windows.UIElement.RenderTransformOrigin%2A> связано с размером кнопки.  В результате, поворот выполняется относительно центра кнопки, а не ее верхнего левого угла.  На следующей иллюстрации показан результат выполнения преобразования.  
  
 ![Кнопка, преобразованная по центру](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm\_RenderTransformRelativeCenter")  
Поворот по часовой стрелке на 45 градусов относительно центра  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 В следующем примере для поворота кнопки используется свойство <xref:System.Windows.FrameworkElement.LayoutTransform%2A> вместо свойства <xref:System.Windows.UIElement.RenderTransform%2A>.  При этом преобразование влияет на макет кнопки, что запускает полный проход системы макета.  В результате кнопка повернута и ее расположение изменено, поскольку изменился ее размер.  На следующей иллюстрации показан результат выполнения преобразования.  
  
 ![Преобразованная кнопка с использованием LayoutTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-layouttransform.png "graphicsmm\_LayoutTransform")  
Для поворота кнопки использовалось свойство LayoutTransform  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## Анимируемые преобразования  
 Поскольку происходит наследование от класса <xref:System.Windows.Media.Animation.Animatable>, классы <xref:System.Windows.Media.Transform> должны быть анимированными.  Чтобы анимировать <xref:System.Windows.Media.Transform>, примените анимацию совместимого типа к требуемому свойству.  
  
 В следующем примере используется <xref:System.Windows.Media.Animation.Storyboard> и <xref:System.Windows.Media.Animation.DoubleAnimation> с <xref:System.Windows.Media.RotateTransform>, чтобы заставить <xref:System.Windows.Controls.Button> вращаться при нажатии.  
  
 [!code-xml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Полный пример см. на веб\-странице [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  Дополнительные сведения об анимации см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
## Возможности объектов Freezable  
 Поскольку класс наследуется от класса <xref:System.Windows.Freezable>, класс <xref:System.Windows.Media.Transform> имеет несколько особенных возможностей: объекты класса <xref:System.Windows.Media.Transform> можно объявлять [ресурсами](../../../../docs/framework/wpf/advanced/xaml-resources.md), которые: могут совместно использоваться несколькими объектами; их можно сделать доступными только для чтения с целью улучшения производительности, клонирования для того, чтобы сделать их потокобезопасными.  Дополнительные сведения о различных возможностях, предоставляемых объектами <xref:System.Windows.Freezable>, см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## См. также  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.Matrix>   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)   
 [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252)