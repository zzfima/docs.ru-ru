---
title: 'Оптимизация производительности: двумерная графика и обработка изображений'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], performance
- drawing [WPF], optimizing performance
- imaging [WPF], optimizing performance
- shapes [WPF], optimizing performance
- 2D graphics [WPF]
- images [WPF], optimizing performance
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
ms.openlocfilehash: eb3686367873276587572addda436471cd1abf27
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291802"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Оптимизация производительности: двумерная графика и обработка изображений
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет широкий спектр функциональных возможностей двумерной графики и изображений, которые можно оптимизировать для требований приложения. Этот раздел содержит сведения об оптимизации производительности в этих областях.  

<a name="Drawing_and_Shapes"></a>
## <a name="drawing-and-shapes"></a>Рисование и фигуры  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет <xref:System.Windows.Media.Drawing> как <xref:System.Windows.Shapes.Shape> объекты, так и объекты для представления графического содержания рисунка. Однако <xref:System.Windows.Media.Drawing> объекты являются <xref:System.Windows.Shapes.Shape> более простыми конструкциями, чем объекты, и обеспечивают более высокую производительность.  
  
 A <xref:System.Windows.Shapes.Shape> позволяет нарисовать графическую форму на экране. Поскольку они являются <xref:System.Windows.FrameworkElement> производными от класса, <xref:System.Windows.Shapes.Shape> объекты могут быть использованы внутри панелей и большинства элементов управления.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет несколько уровней доступа к службам для работы с графикой и службам рендеринга. В верхнем <xref:System.Windows.Shapes.Shape> слое объекты просты в использовании и предоставляют множество полезных функций, таких как макет и обработка событий. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет ряд готовых к использованию объектов Shape. Все объекты <xref:System.Windows.Shapes.Shape> формы наследуют сяизм от класса. Доступные объекты <xref:System.Windows.Shapes.Path>формы <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline>включают, <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Line>, , , и .  
  
 <xref:System.Windows.Media.Drawing>объекты, с другой стороны, <xref:System.Windows.FrameworkElement> не вытекают из класса и обеспечивают более легкую реализацию для визуализации форм, изображений и текста.  
  
 Существует четыре типа <xref:System.Windows.Media.Drawing> объектов:  
  
- <xref:System.Windows.Media.GeometryDrawing>Рисует фигуру.  
  
- <xref:System.Windows.Media.ImageDrawing>Рисует изображение.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>Рисует текст.  
  
- <xref:System.Windows.Media.DrawingGroup>Рисует другие рисунки. Для объединения рисунков в один составной рисунок используйте группирование рисунков.  
  
 Объект <xref:System.Windows.Media.GeometryDrawing> используется для визуализации содержимого геометрии. Класс <xref:System.Windows.Media.Geometry> и конкретные классы, которые <xref:System.Windows.Media.CombinedGeometry>вытекают из него, такие как , <xref:System.Windows.Media.EllipseGeometry>и <xref:System.Windows.Media.PathGeometry>, обеспечивают средства для рендеринга 2D графики и предоставления хит-тестирования и отсечения поддержки. Геометрические объекты можно использовать, например, для определения области элемента управления или для определения области усечения, применяемой к изображению. Геометрические объекты могут быть простыми, такими как прямоугольники и круги, или сложными, созданными из двух или более геометрических объектов. Более сложные геометрические области могут <xref:System.Windows.Media.PathSegment>быть созданы путем <xref:System.Windows.Media.BezierSegment>объединения <xref:System.Windows.Media.QuadraticBezierSegment>производных объектов, таких как <xref:System.Windows.Media.ArcSegment>, и .  
  
 На первый <xref:System.Windows.Media.Geometry> взгляд класс <xref:System.Windows.Shapes.Shape> и класс похожи. Оба используются в визуализации 2D графики и оба имеют аналогичные <xref:System.Windows.Media.EllipseGeometry> конкретные классы, которые вытекают из них, например, и <xref:System.Windows.Shapes.Ellipse>. Однако существуют важные различия между этими двумя наборами классов. С одной <xref:System.Windows.Media.Geometry> из них классу не хватает <xref:System.Windows.Shapes.Shape> некоторых функциональных возможностей класса, таких как способность рисовать сам. Чтобы нарисовать геометрический объект, для выполнения операции рисования должен использоваться другой класс, например DrawingContext, Drawing или Path (стоит отметить, что Path является Shape). Рендеринг свойств, таких как заполнение, штрих и толщина хода, находятся на классе, который рисует объект геометрии, в то время как объект формы содержит эти свойства. Один из способов думать об этом различии заключается в том, что объект геометрии определяет область, например, круг, в то время как объект формы определяет область, определяет, как этот регион заполняется и очерчен, и участвует в системе макета.  
  
 Поскольку <xref:System.Windows.Shapes.Shape> объекты <xref:System.Windows.FrameworkElement> вытекают из класса, их использование может значительно повысить потребление памяти в приложении. Если вам действительно не <xref:System.Windows.FrameworkElement> нужны функции для графического контента, рассмотрите возможность использования объектов с легким весом. <xref:System.Windows.Media.Drawing>  
  
 Для получения <xref:System.Windows.Media.Drawing> дополнительной информации об объектах [см.](../graphics-multimedia/drawing-objects-overview.md)  
  
<a name="StreamGeometry_Objects"></a>
## <a name="streamgeometry-objects"></a>Объекты StreamGeometry  
 Объект <xref:System.Windows.Media.StreamGeometry> является легкой <xref:System.Windows.Media.PathGeometry> альтернативой для создания геометрических фигур. Используйте, <xref:System.Windows.Media.StreamGeometry> когда вам нужно описать сложную геометрию. <xref:System.Windows.Media.StreamGeometry>оптимизирован для <xref:System.Windows.Media.PathGeometry> обработки многих объектов и работает <xref:System.Windows.Media.PathGeometry> лучше по сравнению с использованием многих отдельных объектов.  
  
 В следующем примере используется синтаксис <xref:System.Windows.Media.StreamGeometry> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]атрибутов для создания треугольного дюйма .  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Для получения <xref:System.Windows.Media.StreamGeometry> дополнительной информации об объектах см. [Create a Shape Using a StreamGeometry](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md)  
  
<a name="DrawingVisual_Objects"></a>
## <a name="drawingvisual-objects"></a>объекты DrawingVisual  
 Объект <xref:System.Windows.Media.DrawingVisual> представляет собой легкий класс рисования, который используется для визуализации форм, изображений или текста. Этот класс считается упрощенным, так как не предоставляет средств для работы с разметкой и обработку событий, что повышает его производительность. Поэтому этот класс идеально подходит для фоновых рисунков или клипов. Дополнительные сведения см. в разделе [Использование объектов DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>
## <a name="images"></a>Изображения  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]изображение обеспечивает значительное улучшение по сравнению с возможностями визуализации в предыдущих версиях Windows. Возможности визуализации, такие как отображение битовой карты или использование изображения на общем элементе управления, в основном обрабатывались интерфейсом Microsoft Windows Graphics Device Interface (GDI) или интерфейсом программирования приложений Microsoft Windows GDI (API). Эти AA предоставили базовую функциональность изображений, но не имели таких функций, как поддержка расширяемости кодека и поддержка изображений высокой точности. AIMAGE-аДИ WPF Imaging были переработаны для преодоления недостатков GDI и GDI и предоставления нового набора AA для отображения и использования изображений в приложениях.  
  
 При использовании изображений учитывайте следующие рекомендации, позволяющие повысить производительность.  
  
- Если в приложении требуется отображение эскизов, рассмотрите возможность создания версий изображений уменьшенного размера. По умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] загружает изображение и преобразует его до полного размера. Если требуется только эскиз изображения, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] напрасно преобразует изображение до полного размера, а затем масштабирует его до размера эскиза. Чтобы избежать этой лишней нагрузки, можно либо запросить в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] преобразование изображения в размер эскиза, либо настроить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для загрузки изображения размера эскиза.  
  
- Всегда преобразуйте изображение в нужный размер, а не размер по умолчанию. Как упоминалось выше, запросите в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] преобразование изображения в нужный размер, а не в полный размер по умолчанию. Вы уменьшите не только рабочий набор приложения, но также и время ожидания выполнения.  
  
- Если это возможно, объединяйте изображения в одно изображение, например диафильм, состоящий из нескольких изображений.  
  
- Для получения дополнительной информации смотрите [обзор изображений](../graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 При анимации масштаба любой битной карты, высококачественный алгоритм перевыборки изображений по умолчанию иногда может потреблять достаточно системных ресурсов, чтобы вызвать деградацию частоты кадров, что фактически приводит к заиканию анимации. Установив свойство <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> <xref:System.Windows.Media.RenderOptions> объекта, <xref:System.Windows.Media.BitmapScalingMode.LowQuality>можно создать более плавную анимацию при масштабировании битовой карты. <xref:System.Windows.Media.BitmapScalingMode.LowQuality>режим уседает движку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] рендеринга перейти от оптимизированного с точки контроля алгоритма к оптимизированного для скорости алгоритма при обработке изображений.  
  
 В следующем примере показано, как установить <xref:System.Windows.Media.BitmapScalingMode> объект изображения.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] По умолчанию не кэширует отображеносодержимое содержимое <xref:System.Windows.Media.TileBrush> объектов, таких как <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush>. В статических сценариях, где <xref:System.Windows.Media.TileBrush> содержимое или использование в сцене не изменяется, это имеет смысл, так как он сохраняет видеопамять. Это не имеет большого <xref:System.Windows.Media.TileBrush> смысла, когда статическое содержимое используется нестатическим способом, например, когда статическое <xref:System.Windows.Media.DrawingBrush> или <xref:System.Windows.Media.VisualBrush> отображено на поверхности вращающегося 3D-объекта. Поведение по [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] умолчанию заключается в том, <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> чтобы повторно передать все содержимое или для каждого кадра, даже если содержимое неменяется.  
  
 Установив свойство <xref:System.Windows.Media.RenderOptions.CachingHint%2A> <xref:System.Windows.Media.RenderOptions> объекта, <xref:System.Windows.Media.CachingHint.Cache>можно повысить производительность, используя кэшированные версии объектов кисти.  
  
 Значения <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> свойств представляют значения относительного размера, <xref:System.Windows.Media.TileBrush> определяющие, когда объект должен быть регенерирован из-за изменений в масштабе. Например, установив <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> свойство до 2.0, кэш для единственного <xref:System.Windows.Media.TileBrush> должен быть регенерирован, когда его размер превышает в два раза больше текущего кэша.  
  
 Ниже приведен о том, как использовать опцию подсказки кэширования для . <xref:System.Windows.Media.DrawingBrush>  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>См. также

- [Улучшение производительности приложений WPF](optimizing-wpf-application-performance.md)
- [Планирование производительности приложения](planning-for-application-performance.md)
- [Использование преимуществ оборудования](optimizing-performance-taking-advantage-of-hardware.md)
- [Разметка и разработка](optimizing-performance-layout-and-design.md)
- [Поведение объекта](optimizing-performance-object-behavior.md)
- [Ресурсы приложения](optimizing-performance-application-resources.md)
- [Текст](optimizing-performance-text.md)
- [Привязка данных](optimizing-performance-data-binding.md)
- [Дополнительные рекомендации по повышению производительности](optimizing-performance-other-recommendations.md)
- [Советы и рекомендации по анимации](../graphics-multimedia/animation-tips-and-tricks.md)
