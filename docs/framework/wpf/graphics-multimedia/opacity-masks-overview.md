---
title: "Общие сведения о масках непрозрачности | Microsoft Docs"
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
  - "кисти, маски непрозрачности"
  - "маски, непрозрачность"
  - "непрозрачность, маски"
ms.assetid: 22367fab-5f59-4583-abfd-db2bf86eaef7
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения о масках непрозрачности
Маски непрозрачности позволяют делать части элемента либо видимыми, либо прозрачными, либо частично прозрачными.  Для создания маски непрозрачности, примените <xref:System.Windows.Media.Brush> к свойству <xref:System.Windows.UIElement.OpacityMask%2A> элемента или <xref:System.Windows.Media.Visual>.  Кисть сопоставляется с элементом или визуальным компонентом, и значение коэффициента непрозрачности каждого пикселя кисти используется, чтобы определить получающуюся в итоге непрозрачность каждого соответствующего пикселя элемента или visual.  
  
 В этом разделе содержатся следующие подразделы.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Предварительные требования](#prereqs)  
  
-   [Создание визуальных эффектов с помощью масок непрозрачности](#opacitymasks)  
  
-   [Создание маски непрозрачности](#creatingopacitymasks)  
  
-   [Использование градиента в качестве маски непрозрачности](#creatingopacitymaskswithgradients)  
  
-   [Задание позиции градиента для маски непрозрачности](#specifyinggradientcolors)  
  
-   [Использование изображения в качестве маски непрозрачности](#usingimageasopacitymask)  
  
-   [Создание маски непрозрачности из чертежа](#drawingbrushasopacitymask)  
  
-   [Связанные разделы](#seeAlsoToggle)  
  
<a name="prereqs"></a>   
## Предварительные требования  
 Этот обзор предполагает, что вы знакомы с объектами <xref:System.Windows.Media.Brush>.  Введение по использованию кистей содержится в разделе [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> и <xref:System.Windows.Media.DrawingBrush> см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="opacitymasks"></a>   
## Создание визуальных эффектов с помощью масок непрозрачности  
 Маска непрозрачности работает путем сопоставления ее содержимого с элементом или визуальным элементом.  [Альфа\-канал](GTMT) каждого из пикселей кисти затем используется для определения полученной непрозрачности соответствующих пикселей элемента или visual; фактический цвет кисти игнорируется.  Если данная часть кисти является прозрачной, соответствующая часть элемента или визуального элемента становится прозрачной.  Если данная часть кисти является непрозрачной, непрозрачность соответствующей части элемента или визуального элемента не меняется.  Непрозрачность, заданная маской непрозрачности, объединяется с любыми параметрами непрозрачности представленными в элементе или визуальном элементе.  Например, если элемент имеет коэффициент непрозрачности 25 процентов и маска непрозрачности применяется к переходу из полной непрозрачности к полной прозрачности, результатом является элемент, который переходит от коэффициента непрозрачности 25 процентов к полной прозрачности.  
  
> [!NOTE]
>  Хотя примеры в этом обзоре демонстрируют использование масок непрозрачности на элементах изображения, маска непрозрачности может применяться к любому элементу или <xref:System.Windows.Media.Visual>, включая панели и элементы управления.  
  
 Непрозрачность маски используются для создания интересных визуальных эффектов, таких как создание изображений или кнопок, которые исчезают, для добавления текстур элементам или для объединения градиентов, чтобы создавать стеклоподобные поверхности.  На следующем рисунке демонстрируется использование маски непрозрачности.  Клетчатый фон используется для отображения прозрачных частей маски.  
  
 ![Объект с маской непрозрачности LinearGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-opacitymask-imageexample.png "wcpsdk\_graphicsmm\_opacitymask\_imageexample")  
Пример использования маски непрозрачности  
  
<a name="creatingopacitymasks"></a>   
## Создание маски непрозрачности  
 Чтобы создать маску непрозрачности, создайте <xref:System.Windows.Media.Brush> и примените его к свойству <xref:System.Windows.UIElement.OpacityMask%2A> элемента или визуального элемента.  Можно использовать любой тип <xref:System.Windows.Media.Brush> в качестве маски непрозрачности.  
  
-   <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>: используется для того, чтобы сделать элемент или визуальный элемент исчезающим.  
  
     На следующем рисунке показан <xref:System.Windows.Media.LinearGradientBrush>, использующийся в качестве маски непрозрачности.  
  
     ![Объект с маской непрозрачности LinearGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-brushes-lineagradientopacitymasksingle.png "wcpsdk\_graphicsmm\_brushes\_lineagradientopacitymasksingle")  
Пример использования маски непрозрачности LinearGradientBrush  
  
-   <xref:System.Windows.Media.ImageBrush>: используется для создания текстуры и эффектов гладких или оборванных краев.  
  
     На следующем рисунке показан <xref:System.Windows.Media.ImageBrush>, использующийся в качестве маски непрозрачности.  
  
     ![Объект с маской непрозрачности ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-brushes-imageasopacitymasksingle.png "wcpsdk\_graphicsmm\_brushes\_imageasopacitymasksingle")  
Пример использования маски непрозрачности LinearGradientBrush  
  
-   <xref:System.Windows.Media.DrawingBrush>: Используется для создания сложных масок непрозрачности из шаблонов фигур, рисунков и градиентов.  
  
     На следующем рисунке показан <xref:System.Windows.Media.DrawingBrush>, использующийся в качестве маски непрозрачности.  
  
     ![Объект с маской непрозрачности DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-drawingbrushasopacitymask-single.png "wcpsdk\_drawingbrushasopacitymask\_single")  
Пример маски непрозрачности DrawingBrush  
  
 Градиентные кисти \(<xref:System.Windows.Media.LinearGradientBrush> и <xref:System.Windows.Media.RadialGradientBrush>\) хорошо подходят для использования в качестве маски непрозрачности.  Поскольку <xref:System.Windows.Media.SolidColorBrush> заполняет область одинаковым цветом, он делает плохие маски непрозрачности; использование <xref:System.Windows.Media.SolidColorBrush> эквивалентно установке свойства элемента или визуального элемента <xref:System.Windows.UIElement.OpacityMask%2A>.  
  
<a name="creatingopacitymaskswithgradients"></a>   
## Использование градиента в качестве маски непрозрачности  
 Для создания градиентной заливки вам необходимо указать две или более позиции градиента.  Каждая позиция градиента содержит описание цвета и позиции \(см.: [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) для получения дополнительных сведений о создании и использовании градиентов\).  Процесс такой же, как при использовании градиента в качестве маски непрозрачности, за исключением того, что вместо смешения цветов, градиент маски непрозрачности смешивает значения альфа\-канала.  Таким образом, фактический цвет содержимого градиента не имеет значения; только альфа\-канал или непрозрачность каждого цвета.  Пример.  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#LinearGradientOpacityMaskonImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/GradientBrushExample.xaml#lineargradientopacitymaskonimage)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#LinearGradientOpacityMaskonImage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/GradientBrushExample.xaml#lineargradientopacitymaskonimage)]  -->  
  
<a name="specifyinggradientcolors"></a>   
## Задание позиции градиента для маски непрозрачности  
 В предыдущем примере определенный системой цвет <xref:System.Windows.Media.Colors.Black%2A> используется в качестве начального цвета градиента.  Поскольку все цвета в классе <xref:System.Windows.Media.Colors>, кроме <xref:System.Windows.Media.Colors.Transparent%2A>, являются полностью непрозрачными, они могут использоваться чтобы просто определить начальный цвет для маски непрозрачности градиента.  
  
 Для дополнительного элемента управления сверх альфа\-значений при определении маски непрозрачности можно указать альфа\-канал цветов с помощью шестнадцатеричного формата [!INCLUDE[TLA#tla_argb](../../../../includes/tlasharptla-argb-md.md)] в разметке или с помощью метода <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=fullName>.  
  
<a name="argbsyntax"></a>   
### Указание непрозрачности цвета в "XAML"  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] используется шестнадцатеричный формат [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] для указания прозрачности отдельных цветов.  Шестнадцатеричный формат [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] использует следующий синтаксис.  
  
 `#`**aa** *rrggbb*  
  
 *aa* в предыдущей строке представляет двузначное шестнадцатеричное значение, используемое для указания непрозрачности цвета.  *rr*, *gg*, и *bb* представляют собой двузначные шестнадцатеричные значения, используемые для указания красной, зеленой и синей компоненты цвета.  Каждая шестнадцатеричная цифра может иметь значение от 0 до 9 либо от A до F.  0 соответствует наименьшему значению, а F — наибольшему.  Альфа\-значение 00 указывает на то, что цвет является полностью прозрачным, в то время как альфа\-значение FF создает цвет, который является полностью непрозрачным.  В следующем примере шестнадцатеричная форма записи [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] используется для задания двух цветов.  Первый — полностью непрозрачный, в то время как второй — полностью прозрачный.  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#AARRGGBBValueonOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/GradientBrushExample.xaml#aarrggbbvalueonopacitymask)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#AARRGGBBValueonOpacityMask](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/GradientBrushExample.xaml#aarrggbbvalueonopacitymask)]  -->  
  
<a name="usingimageasopacitymask"></a>   
## Использование изображения в качестве маски непрозрачности  
 Изображения также могут использоваться в качестве масок непрозрачности.  Следующее изображение показано в качестве примера.  Клетчатый фон используется для отображения прозрачных частей маски.  
  
 ![Объект с маской непрозрачности ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-imageasopacitymask.png "wcpsdk\_graphicsmm\_imageasopacitymask")  
Пример использования маски непрозрачности  
  
 Для использования изображения в качестве маски непрозрачности используйте <xref:System.Windows.Media.ImageBrush> для включения изображения.  При создании изображения, которое будет использоваться в качестве маски непрозрачности, сохраните рисунок в формате, поддерживающем несколько уровней прозрачности, например в [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)].  В следующем примере показан код, используемый для создания предыдущего рисунка.  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#UIElementOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/ImageBrushExample.xaml#uielementopacitymask)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#UIElementOpacityMask](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/ImageBrushExample.xaml#uielementopacitymask)]  -->  
  
<a name="tilingimageopacitymask"></a>   
### Использование мозаичного изображения в качестве маски непрозрачности  
 В следующем примере это же изображение используется с другим <xref:System.Windows.Media.ImageBrush>, но возможности заполнения кисти используются для создания мозаичных элементов изображения с 50 пикселями в квадрате.  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#TiledImageasOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/ImageBrushExample.xaml#tiledimageasopacitymask)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#TiledImageasOpacityMask](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/ImageBrushExample.xaml#tiledimageasopacitymask)]  -->  
  
<a name="drawingbrushasopacitymask"></a>   
## Создание маски непрозрачности из чертежа  
 Рисунки могут быть использованы как маски непрозрачности.  Фигуры, содержащиеся в рисунке, могут заполняться с градиентом, чистыми цветами, изображениями, или даже другими рисунками.  На следующем рисунке показан пример рисунка, используемого в качестве маски непрозрачности.  Клетчатый фон используется для отображения прозрачных частей маски.  
  
 ![Объект с маской непрозрачности DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-drawingbrushasopacitymask.png "wcpsdk\_drawingbrushasopacitymask")  
Пример маски непрозрачности DrawingBrush  
  
 Для использования рисунка в качестве маски непрозрачности используйте <xref:System.Windows.Media.DrawingBrush> для хранения рисунка.  В следующем примере показан код, используемый для создания предыдущего рисунка:  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#OpacityMaskfromDrawing](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/DrawingBrushExample.xaml#opacitymaskfromdrawing)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#OpacityMaskfromDrawing](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/DrawingBrushExample.xaml#opacitymaskfromdrawing)]  -->  
  
<a name="tileddrawingbrush"></a>   
### Использование мозаичного рисунка в качестве маски непрозрачности  
 Как и <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> могут быть сделаны для мозаичного отображения его рисунка.  В следующем примере кисть рисования используется для создания мозаичной маски непрозрачности.  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#TiledDrawingasOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/DrawingBrushExample.xaml#tileddrawingasopacitymask)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#TiledDrawingasOpacityMask](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/DrawingBrushExample.xaml#tileddrawingasopacitymask)]  -->  
  
## См. также  
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)