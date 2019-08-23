---
title: 'Оптимизация производительности: Двумерная графика и изображения'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], performance
- drawing [WPF], optimizing performance
- imaging [WPF], optimizing performance
- shapes [WPF], optimizing performance
- 2-D graphics [WPF]
- images [WPF], optimizing performance
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
ms.openlocfilehash: 764e7e802ccaff50b76229b9441380bfe77fefb5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933354"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Оптимизация производительности: Двумерная графика и изображения
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет широкий спектр функциональных возможностей двумерной графики и изображений, которые можно оптимизировать для требований приложения. Этот раздел содержит сведения об оптимизации производительности в этих областях.  

<a name="Drawing_and_Shapes"></a>   
## <a name="drawing-and-shapes"></a>Рисование и фигуры  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет объекты <xref:System.Windows.Shapes.Shape> и для представления графического содержимого. <xref:System.Windows.Media.Drawing> Однако объекты являются более простыми конструкциями <xref:System.Windows.Shapes.Shape> , чем объекты, и предоставляют лучшие характеристики производительности. <xref:System.Windows.Media.Drawing>  
  
 <xref:System.Windows.Shapes.Shape> Позволяет нарисовать на экране графическую фигуру. Поскольку они являются производными от <xref:System.Windows.FrameworkElement> класса, <xref:System.Windows.Shapes.Shape> объекты можно использовать внутри панелей и большинства элементов управления.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет несколько уровней доступа к службам для работы с графикой и службам рендеринга. На верхнем уровне <xref:System.Windows.Shapes.Shape> объекты просты в использовании и предоставляют множество полезных функций, таких как обработка макета и событий. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет ряд готовых к использованию объектов Shape. Все объекты Shape наследуются <xref:System.Windows.Shapes.Shape> от класса. Доступные объекты фигур: <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon> ,<xref:System.Windows.Shapes.Polyline>и .<xref:System.Windows.Shapes.Rectangle>  
  
 <xref:System.Windows.Media.Drawing>объекты, с другой стороны, не являются производными от <xref:System.Windows.FrameworkElement> класса и предоставляют облегченную реализацию для отрисовки фигур, изображений и текста.  
  
 Существует четыре типа <xref:System.Windows.Media.Drawing> объектов:  
  
- <xref:System.Windows.Media.GeometryDrawing>Рисует фигуру.  
  
- <xref:System.Windows.Media.ImageDrawing>Рисует изображение.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>Рисует текст.  
  
- <xref:System.Windows.Media.DrawingGroup>Рисует другие рисунки. Для объединения рисунков в один составной используйте группирование рисунков.  
  
 <xref:System.Windows.Media.GeometryDrawing> Объект используется для отрисовки геометрического содержимого. Класс и конкретные классы, производные от него, такие как <xref:System.Windows.Media.CombinedGeometry>, <xref:System.Windows.Media.EllipseGeometry>и <xref:System.Windows.Media.PathGeometry>, предоставляют средства для отрисовки двухмерной графики, а также обеспечивают поддержку проверки попадания и обрезки. <xref:System.Windows.Media.Geometry> Геометрические объекты можно использовать, например, для определения области элемента управления или для определения области усечения, применяемой к изображению. Геометрические объекты могут быть простыми, такими как прямоугольники и круги, или сложными, созданными из двух или более геометрических объектов. Более сложные геометрические области можно создавать с <xref:System.Windows.Media.PathSegment>помощью Объединенных объектов, таких как <xref:System.Windows.Media.ArcSegment>, <xref:System.Windows.Media.BezierSegment>и <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
 На поверхности <xref:System.Windows.Media.Geometry> класс <xref:System.Windows.Shapes.Shape> и класс весьма похожи. Оба используются в отрисовке двухмерной графики и имеют похожие конкретные классы, которые являются производными от них, например <xref:System.Windows.Media.EllipseGeometry> и. <xref:System.Windows.Shapes.Ellipse> Однако существуют важные различия между этими двумя наборами классов. Для одного <xref:System.Windows.Media.Geometry> класса не хватает некоторых функциональных возможностей <xref:System.Windows.Shapes.Shape> класса, таких как возможность рисования самого себя. Чтобы нарисовать геометрический объект, для выполнения операции рисования должен использоваться другой класс, например DrawingContext, Drawing или Path (стоит отметить, что Path является Shape). Свойства рендеринга, такие как заливка (fill), штрих (stroke) и толщина штриха (stroke thickness), находятся в классе, который рисует этот геометрический объект, в то время как объект Shape содержит эти свойства. Чтобы понять это различие, представьте, что геометрический объект определяет область, например круг, а объект Shape определяет область, определяет, как эта область заполняется и обводится, а также участвует в системе макета.  
  
 Поскольку <xref:System.Windows.Shapes.Shape> объекты являются производными <xref:System.Windows.FrameworkElement> от класса, их использование может значительно увеличить потребление памяти в приложении. Если вам действительно не нужны <xref:System.Windows.FrameworkElement> функции для вашего графического содержимого, рассмотрите возможность использования более легких <xref:System.Windows.Media.Drawing> объектов.  
  
 Дополнительные сведения об объектах <xref:System.Windows.Media.Drawing> см. в разделе [Общие сведения об объектах Drawing](../graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>   
## <a name="streamgeometry-objects"></a>Объекты StreamGeometry  
 Объект является упрощенной <xref:System.Windows.Media.PathGeometry> альтернативой для создания геометрических фигур. <xref:System.Windows.Media.StreamGeometry> Используйте, <xref:System.Windows.Media.StreamGeometry> если необходимо описать сложную геометрию. <xref:System.Windows.Media.StreamGeometry>оптимизирован для обработки большого числа <xref:System.Windows.Media.PathGeometry> объектов и работает лучше по сравнению с использованием нескольких <xref:System.Windows.Media.PathGeometry> отдельных объектов.  
  
 В следующем примере используется синтаксис атрибутов для создания треугольного <xref:System.Windows.Media.StreamGeometry> элемента [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]в.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Дополнительные сведения <xref:System.Windows.Media.StreamGeometry> об объектах см. в разделе [Создание фигуры с помощью StreamGeometry](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>   
## <a name="drawingvisual-objects"></a>объекты DrawingVisual  
 <xref:System.Windows.Media.DrawingVisual> Объект является легковесным классом рисования, который используется для отрисовки фигур, изображений или текста. Этот класс считается упрощенным, так как не предоставляет средств для работы с разметкой и обработку событий, что повышает его производительность. Поэтому этот класс идеально подходит для фоновых рисунков или клипов. Дополнительные сведения см. в разделе [Использование объектов DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>   
## <a name="images"></a>Изображений  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Создание образов позволяет значительно улучшить возможности работы с образами в предыдущих версиях Windows. Возможности обработки изображений, например вывод растрового изображения или использование изображения в общем элементе управления, в основном управлялись интерфейсом графических устройств (GDI) Microsoft Windows или Microsoft Windows GDI и программным интерфейсом (API). Эти API обеспечивали базовые функции обработки изображений, но в них отсутствовали такие возможности, как поддержка расширяемости кодеков и изображений высокого качества. API обработки изображений WPF был переработан для преодоления недостатков GDI и GDI+ и теперь предоставляет новый набор API для отображения и использования изображений в приложениях.  
  
 При использовании изображений учитывайте следующие рекомендации, позволяющие повысить производительность.  
  
- Если в приложении требуется отображение эскизов, рассмотрите возможность создания версий изображений уменьшенного размера. По умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] загружает изображение и преобразует его до полного размера. Если требуется только эскиз изображения, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] напрасно преобразует изображение до полного размера, а затем масштабирует его до размера эскиза. Чтобы избежать этой лишней нагрузки, можно либо запросить в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] преобразование изображения в размер эскиза, либо настроить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для загрузки изображения размера эскиза.  
  
- Всегда преобразуйте изображение в нужный размер, а не размер по умолчанию. Как упоминалось выше, запросите в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] преобразование изображения в нужный размер, а не в полный размер по умолчанию. Вы уменьшите не только рабочий набор приложения, но также и время ожидания выполнения.  
  
- Если это возможно, объединяйте изображения в одно изображение, например диафильм, состоящий из нескольких изображений.  
  
- Более подробную информацию см. в разделе [Общие сведения об обработке изображений](../graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 При анимации масштабирования любого растрового изображения алгоритм повторной дискретизации изображения высокого качества по умолчанию иногда может использовать столько системных ресурсов, чтобы привести к снижению частоты кадров анимации и задержкам. Установив <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> свойство <xref:System.Windows.Media.RenderOptions> объекта в<xref:System.Windows.Media.BitmapScalingMode.LowQuality> значение, можно создать плавную анимацию при масштабировании растрового изображения. <xref:System.Windows.Media.BitmapScalingMode.LowQuality>режим указывает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] механизму визуализации переключаться с алгоритма, оптимизированного для качества, на алгоритм, оптимизированный для ускорения обработки изображений.  
  
 В следующем примере показано, <xref:System.Windows.Media.BitmapScalingMode> как задать для объекта Image.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 По умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не кэширует отображаемое <xref:System.Windows.Media.TileBrush> содержимое объектов, например <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush>. В статических сценариях, где ни содержимое, <xref:System.Windows.Media.TileBrush> ни использование в сцене не меняются, это имеет смысл, так как экономит видеопамять. Это не имеет смысла, если <xref:System.Windows.Media.TileBrush> с статическим содержимым используется нестатический способ, например, когда статический <xref:System.Windows.Media.DrawingBrush> объект или <xref:System.Windows.Media.VisualBrush> сопоставляется с поверхностью вращающегося трехмерного объекта. Поведение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по умолчанию для — повторное отображение всего содержимого <xref:System.Windows.Media.DrawingBrush> объекта или <xref:System.Windows.Media.VisualBrush> для каждого кадра, даже если содержимое не изменяется.  
  
 Установив <xref:System.Windows.Media.RenderOptions.CachingHint%2A> свойство <xref:System.Windows.Media.RenderOptions> объекта в<xref:System.Windows.Media.CachingHint.Cache> значение, можно повысить производительность, используя кэшированные версии объектов мозаичной кисти.  
  
 Значения свойств <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> <xref:System.Windows.Media.TileBrush> и — это значения относительного размера, которые определяют, когда объект должен быть повторно создан из-за изменения масштаба. <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> Например, установив <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> для свойства значение 2,0, кэш <xref:System.Windows.Media.TileBrush> для нужно будет повторно создавать только в том случае, если его размер превышает размер текущего кэша в два раза больше.  
  
 В следующем примере показано, как использовать параметр указания <xref:System.Windows.Media.DrawingBrush>кэширования для.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>См. также

- [Улучшение производительности приложений WPF](optimizing-wpf-application-performance.md)
- [Планирование производительности приложения](planning-for-application-performance.md)
- [Использование преимуществ оборудования](optimizing-performance-taking-advantage-of-hardware.md)
- [Разметка и разработка](optimizing-performance-layout-and-design.md)
- [Поведение объекта](optimizing-performance-object-behavior.md)
- [Ресурсы приложений](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Привязка данных](optimizing-performance-data-binding.md)
- [Дополнительные рекомендации по повышению производительности](optimizing-performance-other-recommendations.md)
- [Советы и рекомендации по анимации](../graphics-multimedia/animation-tips-and-tricks.md)
