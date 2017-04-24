---
title: "Оптимизация производительности: двумерная графика и обработка изображений | Microsoft Docs"
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
  - "двумерная графика"
  - "рисование, оптимизация производительности"
  - "графика, производительность"
  - "изображения, оптимизация производительности"
  - "графика, оптимизация производительности"
  - "фигуры, оптимизация производительности"
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Оптимизация производительности: двумерная графика и обработка изображений
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет широкий спектр двумерных изображений и возможность обработки изображений, которую можно оптимизировать, если это требуется приложением.  Этот раздел содержит сведения об оптимизации производительности в этих областях.  
  
   
  
<a name="Drawing_and_Shapes"></a>   
## Рисование и фигуры  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет объекты <xref:System.Windows.Media.Drawing> и <xref:System.Windows.Shapes.Shape>, которые представляют собой содержимое графического изображения.  Однако объекты <xref:System.Windows.Media.Drawing> являются более простыми конструкциями, чем объекты <xref:System.Windows.Shapes.Shape>, и, соответственно, меньше влияют на производительность.  
  
 Объекты <xref:System.Windows.Shapes.Shape> позволяют нарисовать графическую фигуру на экране.  Так как объекты <xref:System.Windows.Shapes.Shape> являются производными от класса <xref:System.Windows.FrameworkElement>, то их можно использовать на панелях и в большинстве элементов управления.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет несколько уровней доступа к изображениям и службам отрисовки.  На верхнем слое объекты <xref:System.Windows.Shapes.Shape> просты в использовании и предоставляют множество полезных возможностей, таких как макет и обработка событий.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет ряд готовых к использованию объектов фигур.  Все объекты фигур наследуются от класса <xref:System.Windows.Shapes.Shape>.  Доступные объекты фигур включают в себя <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> и <xref:System.Windows.Shapes.Rectangle>.  
  
 С другой стороны, объекты <xref:System.Windows.Media.Drawing> не являются производными класса <xref:System.Windows.FrameworkElement> и предоставляют упрощенную реализацию отрисовки фигур, изображений и текста.  
  
 Существуют четыре типа объектов <xref:System.Windows.Media.Drawing>:  
  
-   объект <xref:System.Windows.Media.GeometryDrawing> рисует фигуру;  
  
-   объект <xref:System.Windows.Media.ImageDrawing> рисует изображение;  
  
-   объект <xref:System.Windows.Media.GlyphRunDrawing> выводит текст;  
  
-   объект <xref:System.Windows.Media.DrawingGroup> выводит другие объекты Drawing.  Используйте группирование объектов Drawing для объединения объектов Drawing в один составной объект Drawing.  
  
 Объект <xref:System.Windows.Media.GeometryDrawing> используется для отрисовки содержимого геометрического объекта.  Класс <xref:System.Windows.Media.Geometry> и устойчивые классы, производные от него, например <xref:System.Windows.Media.CombinedGeometry>, <xref:System.Windows.Media.EllipseGeometry> и <xref:System.Windows.Media.PathGeometry>, предоставляют средства для отрисовки двумерных изображений, а также обеспечивают поддержку проверки на попадание и отсечения.  Например, геометрические объекты можно использовать для определения области элемента управления или для определения отсекаемой области, применяемой к изображению.  Геометрические объекты могут быть простыми областями, такими как прямоугольники и круги, или сложными, созданными из двух или более геометрических объектов.  Более сложные геометрические области можно создать путем объединения объектов, производных от <xref:System.Windows.Media.PathSegment>, таких как <xref:System.Windows.Media.ArcSegment> <xref:System.Windows.Media.BezierSegment> и <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
 На первый взгляд классы <xref:System.Windows.Media.Geometry> и <xref:System.Windows.Shapes.Shape> весьма похожи.  Оба используются при отрисовке двумерных изображений и оба имеют похожие устойчивые классы, производные из них, например <xref:System.Windows.Media.EllipseGeometry> и <xref:System.Windows.Shapes.Ellipse>.  Однако между этими двумя наборами классов существуют важные различия.  Во\-первых, у класса <xref:System.Windows.Media.Geometry> отсутствует часть возможностей класса <xref:System.Windows.Shapes.Shape>, например, возможность рисования самого себя.  Чтобы нарисовать геометрический объект, другой класс, например DrawingContext, Drawing или Path \(стоит отметить, что Path является Shape\), должен использоваться для выполнения операции рисования.  Свойства отрисовки, например, заполнение, штриховка и толщина штриха, относятся к классу, который рисует геометрические объекты, в то время как объект фигуры содержит эти свойства.  Это различие видно в том, что геометрический объект определяет область, например, окружность, в то время как объект фигуры определяет область, то есть то, каким образом область заполняется, обводится и участвует в системе макета.  
  
 Поскольку объекты <xref:System.Windows.Shapes.Shape> являются производными от класса <xref:System.Windows.FrameworkElement>, их использование может значительно увеличить количество памяти, потребляемой приложением.  Если острой потребности именно в средствах <xref:System.Windows.FrameworkElement> для графического содержимого нет, рассмотрите возможность использования упрощенных объектов <xref:System.Windows.Media.Drawing>.  
  
 Дополнительные сведения об объектах <xref:System.Windows.Media.Drawing> см. в разделе общих сведений [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>   
## Объекты StreamGeometry  
 Объект <xref:System.Windows.Media.StreamGeometry> является упрощенной альтернативой <xref:System.Windows.Media.PathGeometry> для создания геометрических фигур.  Используйте объект <xref:System.Windows.Media.StreamGeometry> для описания сложной геометрии.  <xref:System.Windows.Media.StreamGeometry> оптимизирован для обработки большого количества объектов <xref:System.Windows.Media.PathGeometry> и выполняется быстрее по сравнению с использованием нескольких отдельных объектов <xref:System.Windows.Media.PathGeometry>.  
  
 В следующем примере используется синтаксис атрибута для создания треугольного <xref:System.Windows.Media.StreamGeometry> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Дополнительные сведения об объектах <xref:System.Windows.Media.StreamGeometry> см. в разделе [Создание фигуры с помощью StreamGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>   
## Объекты DrawingVisual  
 Объект <xref:System.Windows.Media.DrawingVisual> представляет собой упрощенный класс рисования, который используется для отрисовки фигур, изображений или текста.  Этот класс считается упрощенным, поскольку он не предоставляет макет или обработку событий, что повышает его производительность.  По этой причине эти объекты идеально подходят для фоновых рисунков и коллекций картинок.  Дополнительные сведения см. в разделе [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>   
## Изображения  
 Обработка изображений в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] значительно улучшилась по сравнению с возможностями обработки изображений в предыдущих версиях [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  Возможности обработки изображений, такие как отображение точечных рисунков или использование изображения на общем элементе управления в основном обрабатывались прикладными программными интерфейсами Microsoft Windows Graphics Device Interface \(GDI\) или Microsoft Windows GDI\+.  Эти интерфейсы API предоставляли базовые возможности обработки изображений, но были лишены таких функций как поддержка расширяемости кодеков и изображений высокого качества.  Интерфейс API обработки изображений WPF был переработан для преодоления недостатков GDI и GDI\+ и предоставления нового набора интерфейсов API для отображения и использования изображений в приложениях.  
  
 При использовании изображений рассмотрите следующие рекомендации, позволяющие повысить производительность:  
  
-   Если приложению требуется отображать эскизы, рассмотрите возможность создания версий изображений меньшего размера.  По умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] загружает предоставленное изображение и декодирует его до полного размера.  Если требуется только эскиз изображения, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] декодирует изображение до полного размера, а затем масштабирует его до размера эскиза.  Чтобы избежать этих лишних непроизводительных издержек можно настроить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на декодирование изображения до размера эскиза или настроить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на загрузку изображения эскиза \(размером не больше эскиза\).  
  
-   Всегда декодируйте изображение до нужного размера, а не до размера по умолчанию.  Как упоминалось выше, настройте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на декодирование изображения до нужного размера, а не до размера по умолчанию.  Этим можно не только уменьшить рабочее множество приложения, но и увеличить скорость выполнения.  
  
-   По возможности, объединяйте изображения в одно изображение, как, например, кинолента, которая состоит из нескольких изображений.  
  
-   Дополнительные сведения см. в разделе общих сведений [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
### Режим BitmapScalingMode  
 При анимации масштаба любого точечного рисунка, по умолчанию алгоритм передискретизации изображения высокого качества иногда может использовать столько системных ресурсов, что это приводит к снижению частоты кадров и, в конечном счете, к пропуску кадров в анимации.  Присвоив свойству <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> объекта <xref:System.Windows.Media.RenderOptions> значение <xref:System.Windows.Media.BitmapScalingMode>, можно создать более плавную анимацию при масштабировании растрового изображения.  Режим <xref:System.Windows.Media.BitmapScalingMode> инструктирует механизм отрисовки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] переключиться из алгоритма, настроенного на оптимальное качество, на алгоритм, настроенный на оптимальную скорость, при обработке изображений.  
  
 В следующем примере показана установка <xref:System.Windows.Media.BitmapScalingMode> для объекта изображения.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### Свойство CachingHint  
 По умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не кэширует готовое для просмотра содержимое объектов <xref:System.Windows.Media.TileBrush>, таких как <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush>.  В статических скриптах, где ни содержимое, ни использование <xref:System.Windows.Media.TileBrush> в сцене не изменяется, это имеет смысл, так как экономит видеопамять.  Это не имеет смысла, если <xref:System.Windows.Media.TileBrush> со статическим содержимым используется нестатическим образом — например, если статический <xref:System.Windows.Media.DrawingBrush> или <xref:System.Windows.Media.VisualBrush> сопоставлен с областью вращающегося трехмерного объекта.  Поведением [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по умолчанию является повторная отрисовка всего содержимого <xref:System.Windows.Media.DrawingBrush> или <xref:System.Windows.Media.VisualBrush> для каждого кадра, даже если содержимое не изменяется.  
  
 Присвоив свойству <xref:System.Windows.Media.RenderOptions.CachingHint%2A> объекта <xref:System.Windows.Media.RenderOptions> значение <xref:System.Windows.Media.CachingHint>, можно повысить производительность с помощью кэшированных версий объектов мозаичной кисти.  
  
 Значения свойств <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> и <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> являются относительными значениями размера, определяющими, когда нужно повторно создавать объект <xref:System.Windows.Media.TileBrush> из\-за изменения масштаба.  Например, если присвоить свойству <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> значение 2,0, то кэшу для <xref:System.Windows.Media.TileBrush> необходимо будет создаваться повторно только тогда, когда размер объекта в два раза превысит размер текущего кэша.  
  
 В следующем примере показано использование параметра кэшируемой подсказки для <xref:System.Windows.Media.DrawingBrush>.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## См. также  
 [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Планирование производительности приложения](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Использование преимуществ оборудования](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Поведение объекта](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Ресурсы приложения](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Привязка данных](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Дополнительные рекомендации по повышению производительности](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [Советы и рекомендации по анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)