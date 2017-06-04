---
title: "Общие сведения о преобразованиях объекта Brush | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "кисти, свойства преобразования"
  - "свойства, преобразование"
  - "свойства преобразования кистей"
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения о преобразованиях объекта Brush
Класс Brush предоставляет два свойства преобразования: <xref:System.Windows.Media.Brush.Transform%2A> и <xref:System.Windows.Media.Brush.RelativeTransform%2A>.  Данные свойства позволяют выполнять поворот, масштабирование, наклон и преобразование содержимого кисти.  В данном разделе описываются различия между этими двумя свойствами и приводятся примеры их использования.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Предварительные требования  
 Чтобы усвоить материал данного раздела, необходимо понимать возможности преобразуемой кисти.  Дополнительные сведения о <xref:System.Windows.Media.LinearGradientBrush> и <xref:System.Windows.Media.RadialGradientBrush> см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  Дополнительные сведения о классах <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush> см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  Кроме того, необходимо ознакомиться с двумерными преобразованиями, описанными в разделе [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
<a name="transformversusrelativetransform"></a>   
## Различия между свойствами Transform и RelativeTransform  
 При применении преобразования <xref:System.Windows.Media.Brush.Transform%2A> к свойству кисти необходимо знать размер закрашиваемой области, если требуется выполнить преобразование содержимого кисти относительно ее центра.  Предположим, что закрашиваемая область имеет ширину в 200 и высоту в 150 [аппаратно\-независимых пикселей](GTMT).  Если для поворота выходного значения кисти на 45 градусов вокруг его центра используется объект <xref:System.Windows.Media.RotateTransform>, то необходимо чтобы для <xref:System.Windows.Media.RotateTransform> значение свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> равнялось 100 и значение свойства <xref:System.Windows.Media.RotateTransform.CenterY%2A> равнялось 75.  
  
 Если выполняется преобразование свойства <xref:System.Windows.Media.Brush.RelativeTransform%2A> кисти, то данное преобразование применяется к кисти перед сопоставлением ее выходного значения закрашиваемой области.  В следующем списке представлен порядок, в соответствии с которым необходимо выполнять обработку и преобразование содержимого кисти:  
  
1.  Обработать содержимое кисти.  Для <xref:System.Windows.Media.GradientBrush> это означает определение области градиента.  Для <xref:System.Windows.Media.TileBrush> свойство <xref:System.Windows.Media.TileBrush.Viewbox%2A> сопоставляется со свойством <xref:System.Windows.Media.TileBrush.Viewport%2A>.  Это становится выходным значением кисти.  
  
2.  Спроецировать выходное значение кисти на прямоугольник преобразования 1 x 1.  
  
3.  Применить преобразование <xref:System.Windows.Media.Brush.RelativeTransform%2A> кисти, если таковое имеется.  
  
4.  Спроецировать преобразованное выходное значение на закрашиваемую область.  
  
5.  Применить преобразование <xref:System.Windows.Media.Transform> кисти, если таковое имеется.  
  
 Так как преобразование <xref:System.Windows.Media.Brush.RelativeTransform%2A> применяется при сопоставлении выходного значения кисти прямоугольнику 1 x 1, центр преобразований и значения смещения считаются относительными.  Например, если используется преобразование <xref:System.Windows.Media.RotateTransform> для поворота выходного значения кисти на 45 градусов вокруг его центра, то необходимо задать для данного преобразования <xref:System.Windows.Media.RotateTransform> для свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> значение 0.5 и для свойства <xref:System.Windows.Media.RotateTransform.CenterY%2A> значение 0.5.  
  
 На следующем рисунке показано выходное значение нескольких кистей, повернутых на 45 градусов с помощью свойств <xref:System.Windows.Media.Brush.RelativeTransform%2A> и <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 ![Свойства RelativeTransform и Transform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm\_brushrelativetransform\_transform\_small")  
  
<a name="relativetransformandtilebrush"></a>   
## Использование преобразования RelativeTransform с TileBrush  
 Так как мозаичные кисти являются более сложными, чем другие кисти, применение к ним преобразования <xref:System.Windows.Media.Brush.RelativeTransform%2A> может привести к непредсказуемым результатам.  Например, рассмотрим следующий рисунок.  
  
 ![Исходное изображение](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-1-original-image.png "graphicsmm\_reltransform\_1\_original\_image")  
  
 В следующем примере объект <xref:System.Windows.Media.ImageBrush> используется для закраски прямоугольной области приведенным выше изображением.  В нем преобразование <xref:System.Windows.Media.RotateTransform> применяется к свойству <xref:System.Windows.Media.Brush.RelativeTransform%2A> объекта <xref:System.Windows.Media.ImageBrush> и для его свойства <xref:System.Windows.Media.TileBrush.Stretch%2A> задано значение <xref:System.Windows.Media.Stretch> для сохранения пропорций рисунка при его растяжении для полного заполнения прямоугольника.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 В этом примере получается следующий результат:  
  
 ![Преобразованный вывод](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-6-output.png "graphicsmm\_reltransform\_6\_output")  
  
 Обратите внимание, что изображение искажено, хотя для свойства <xref:System.Windows.Media.TileBrush.Stretch%2A> кисти было задано значение <xref:System.Windows.Media.Stretch>.  Это произошло, потому что относительное преобразование применяется после сопоставления свойства <xref:System.Windows.Media.TileBrush.Viewbox%2A> кисти свойству <xref:System.Windows.Media.TileBrush.Viewport%2A>.  В следующем списке представлены все шаги процесса:  
  
1.  Спроецировать содержимое кисти \(<xref:System.Windows.Media.TileBrush.Viewbox%2A>\) на базу ее мозаичного заполнения \(<xref:System.Windows.Media.TileBrush.Viewport%2A>\) с помощью параметра <xref:System.Windows.Media.TileBrush.Stretch%2A> кисти.  
  
     ![Растянуть Viewbox для соответствия окну просмотра](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm\_reltransform\_2\_viewbox\_to\_viewport")  
  
2.  Спроецировать базу мозаичного заполнения на прямоугольник преобразования 1 x 1.  
  
     ![Сопоставление окна просмотра к преображение прямоугольника](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm\_reltransform\_3\_output\_to\_transform")  
  
3.  Применить преобразование <xref:System.Windows.Media.RotateTransform>.  
  
     ![Применить относительное преображение](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm\_reltransform\_4\_transform\_rotate")  
  
4.  Спроецировать преобразованную базу мозаичного заполнения на область закраски.  
  
     ![Спроецировать преобразованную кисть на закрашиваемую область](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm\_reltransform\_5\_transform\_to\_output")  
  
<a name="rotateexample"></a>   
## Пример. Поворот объекта ImageBrush на 45 градусов  
 В следующем примере преобразование <xref:System.Windows.Media.RotateTransform> применяется к свойству <xref:System.Windows.Media.Brush.RelativeTransform%2A> объекта <xref:System.Windows.Media.ImageBrush>.  Для объекта <xref:System.Windows.Media.RotateTransform> свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> оба задаются равными 0,5 и данные значения являются относительными координатами точки центра содержимого.  В результате содержимое кисти повернуто относительно его центра.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 В следующем примере также применяется преобразование <xref:System.Windows.Media.RotateTransform> к объекту <xref:System.Windows.Media.ImageBrush>, но вместо свойства <xref:System.Windows.Media.Brush.RelativeTransform%2A> используется свойство <xref:System.Windows.Media.Brush.Transform%2A>.  Чтобы повернуть кисть относительно ее центра, для объекта <xref:System.Windows.Media.RotateTransform> свойствам <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> должны быть присвоены абсолютные координаты.  Поскольку закрашиваемый кистью прямоугольник имеет размеры 175 на 90 пикселей, его центральная точка будет иметь координаты \(87.5, 45\).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 На следующем изображении показана кисть без преобразования, с преобразованием, примененным к свойству <xref:System.Windows.Media.Brush.RelativeTransform%2A> и с преобразованием, примененным к свойству <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 ![Параметры кисти RelativeTransform и Transform](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk\_graphicsmm\_transformandrelativetransform")  
  
 Данный пример является частью большего примера.  Полный код примера см. на веб\-странице [Пример Brushes](http://go.microsoft.com/fwlink/?LinkID=159973).  Дополнительные сведения о кистях см. в разделе [Общие сведения о кистях WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  
  
## См. также  
 <xref:System.Windows.Media.Brush.Transform%2A>   
 <xref:System.Windows.Media.Brush.RelativeTransform%2A>   
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.Brush>   
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)