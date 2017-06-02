---
title: "Общие сведения о TileBrush | Microsoft Docs"
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
  - "кисти, TileBrush"
  - "TileBrush"
ms.assetid: aa4a7b7e-d09d-44c2-8d61-310c50e08d68
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения о TileBrush
Объекты <xref:System.Windows.Media.TileBrush> предоставляют разработчику практически полный контроль над тем, как область закрашивается изображением, <xref:System.Windows.Media.Drawing> или <xref:System.Windows.Media.Visual>.  В этом разделе описано, как использовать возможности <xref:System.Windows.Media.TileBrush> для большего контроля над тем, как методы <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> или <xref:System.Windows.Media.VisualBrush> закрашивают область.  
  
   
  
<a name="prerequisite"></a>   
## Предварительные требования  
 Для понимания этого раздела, полезно разобраться с использованием основных возможностей класса <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> или <xref:System.Windows.Media.VisualBrush>.  Введение в эти типы см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="tilebrush"></a>   
## Закрашивание области с помощью мозаики  
 Объекты <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush> являются типами объектов <xref:System.Windows.Media.TileBrush>.  Мозаичная кисть предоставляет практически полный контроль над закрашиванием области с помощью изображения, рисунка или визуального объекта.  Например, вместо простой закраски области одним растянутым изображением, можно закрасить область с помощью множества фрагментов изображения, создающих узор.  
  
 Закрашивание области с помощью мозаичной кисти включает три компонента: содержимое, базовую мозаику и выходную область.  
  
 ![Компоненты TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk\_mmgraphics\_defaultcontentprojection2")  
Компоненты TileBrush с одним фрагментом  
  
 ![Компоненты мозаичного TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "graphicsmm\_tiledprojection")  
Компоненты TileBrush с TileMode фрагмента  
  
 Область вывода — это закрашиваемая область, например, <xref:System.Windows.Shapes.Shape.Fill%2A> для <xref:System.Windows.Shapes.Ellipse> или <xref:System.Windows.Controls.Control.Background%2A> для <xref:System.Windows.Controls.Button>.  В следующих разделах описаны другие два компонента <xref:System.Windows.Media.TileBrush>.  
  
<a name="brushcontent"></a>   
## Содержимое кисти  
 Существуют три различных типа <xref:System.Windows.Media.TileBrush> и каждый закрашивает различным типом содержимого.  
  
-   Если используется кисть <xref:System.Windows.Media.ImageBrush>, то содержимое — изображение. Свойство <xref:System.Windows.Media.ImageBrush.ImageSource%2A> задает содержимое <xref:System.Windows.Media.ImageBrush>.  
  
-   Если используется кисть <xref:System.Windows.Media.DrawingBrush>, то содержимое — рисунок.  Свойство <xref:System.Windows.Media.DrawingBrush.Drawing%2A> задает содержимое <xref:System.Windows.Media.DrawingBrush>.  
  
-   Если используется кисть <xref:System.Windows.Media.VisualBrush>, то содержимое — визуальный объект.  Свойство <xref:System.Windows.Media.VisualBrush.Visual%2A> задает содержимое <xref:System.Windows.Media.VisualBrush>.  
  
 Можно задать положение и размеры содержимого <xref:System.Windows.Media.TileBrush> с помощью свойства <xref:System.Windows.Media.TileBrush.Viewbox%2A>, хотя обычно используется значение <xref:System.Windows.Media.TileBrush.Viewbox%2A> по умолчанию.  По умолчанию <xref:System.Windows.Media.TileBrush.Viewbox%2A> настроен на полное включение содержимого кисти.  Дополнительные сведения о конфигурации <xref:System.Windows.Controls.Viewbox> см. на странице свойства <xref:System.Windows.Controls.Viewbox>.  
  
<a name="thebasetile"></a>   
## Базовая мозаика  
 <xref:System.Windows.Media.TileBrush> проецирует свое содержимое на базовую мозаику.  Свойство <xref:System.Windows.Media.TileBrush.Stretch%2A> управляет тем, как содержимое <xref:System.Windows.Media.TileBrush> растянуто для заполнения базовой мозаики.  Свойство <xref:System.Windows.Media.TileBrush.Stretch%2A> принимает следующие значения, определенные перечислением <xref:System.Windows.Media.Stretch>:  
  
-   <xref:System.Windows.Media.Stretch>: содержимое кисти не растягивается, чтобы заполнить фрагмент.  
  
-   <xref:System.Windows.Media.Stretch>: содержимое кисти масштабируется, чтобы заполнить фрагмент.  Поскольку высота и ширина содержимого масштабируются независимо друг от друга, исходные пропорции содержимого могут не сохраняться.  Это значит, содержимое кисти может быть перекошено, чтобы полностью заполнить выводимый фрагмент.  
  
-   <xref:System.Windows.Media.Stretch>: содержимое кисти масштабируется, чтобы уместиться внутри фрагмента.  Пропорции содержимого сохраняются.  
  
-   <xref:System.Windows.Media.Stretch>: содержимое кисти масштабируется таким образом, чтобы полностью заполнить область вывода, сохраняя пропорции содержимого.  
  
 На следующем рисунке показаны другие параметры <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
 ![Различные параметры растяжения TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-stretchenum.png "img\_mmgraphics\_stretchenum")  
  
 В следующем примере содержимое <xref:System.Windows.Media.ImageBrush> задается таким образом, что оно не растягивается для заполнения области вывода.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 По умолчанию <xref:System.Windows.Media.TileBrush> создает один фрагмент \(базовую мозаику\) и растягивает его для полного заполнения области вывода.  Можно изменить размер и положение базовой мозаики, задав значения свойствам <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>.  
  
<a name="basetilesize"></a>   
### Размер базовой мозаики  
 Свойство <xref:System.Windows.Media.TileBrush.Viewport%2A> определяет размер и положение базовой мозаики, а свойство <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> определяет, задан ли <xref:System.Windows.Media.TileBrush.Viewport%2A> с помощью абсолютных или относительных координат.  Если координаты относительные, они указываются относительно размера области вывода.  Точка \(0,0\) представляет верхний левый угол области вывода, а \(1,1\) представляет нижний правый угол области вывода.  Чтобы указать, что свойство <xref:System.Windows.Media.TileBrush.Viewport%2A> использует абсолютные координаты, присвойте свойству <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> значение <xref:System.Windows.Media.BrushMappingMode>.  
  
 На следующем рисунке показана разница между выводом <xref:System.Windows.Media.TileBrush> в относительных и абсолютных координатах <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>.  Обратите внимание на то, что на каждом рисунке показан шаблон заполнения; в следующем разделе описывается, как задать шаблон заполнения.  
  
 ![Абсолютные и относительные единицы окна просмотра](../../../../docs/framework/wpf/graphics-multimedia/media/absolute-and-relative-viewports.png "absolute\_and\_relative\_viewports")  
  
 В следующем примере изображение используется для создания мозаики с высотой и шириной 50%.  Базовая мозаика имеет координаты \(0,0\) на выходной области.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 В следующем примере размер мозаик <xref:System.Windows.Media.ImageBrush> задается равным 25 на 25 [аппаратно\-независимых пикселей](GTMT).  Поскольку <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> — абсолютные, размер мозаики <xref:System.Windows.Media.ImageBrush> всегда будет 25 на 25 пикселей, независимо от размера закрашиваемой области.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>   
### Поведение заполнения  
 <xref:System.Windows.Media.TileBrush> создает шаблон заполнения, когда его базовая мозаика не полностью заполняет область вывода и задан режим заполнения, отличный от <xref:System.Windows.Media.TileMode>.  Когда фрагмент мозаичной кисти не полностью заполняет область вывода, свойство <xref:System.Windows.Media.TileBrush.TileMode%2A> указывает, должен ли базовый фрагмент дублироваться для заполнения области вывода, и если да, то как.  Свойство <xref:System.Windows.Media.TileBrush.TileMode%2A> принимает следующие значения, определенные перечислением <xref:System.Windows.Media.TileMode>:  
  
-   <xref:System.Windows.Media.TileMode>: рисуется только базовая мозаика.  
  
-   <xref:System.Windows.Media.TileMode>: рисуется базовая мозаика, а оставшееся пространство заполняется ее повторением так, чтобы правый край фрагмента примыкал к левому краю следующего, аналогично для нижнего и верхнего краев.  
  
-   <xref:System.Windows.Media.TileMode>: аналогично <xref:System.Windows.Media.TileMode>, но разные столбцы мозаики зеркально отражаются по горизонтали.  
  
-   <xref:System.Windows.Media.TileMode>: аналогично <xref:System.Windows.Media.TileMode>, но разные строки мозаики зеркально отражаются по вертикали.  
  
-   Комбинация <xref:System.Windows.Media.TileMode>: сочетание <xref:System.Windows.Media.TileMode> и <xref:System.Windows.Media.TileMode>.  
  
 На следующем рисунке показаны другие режимы заполнения.  
  
 ![Различные параметры TileMode для TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-tilemodes.png "img\_mmgraphics\_tilemodes")  
  
 В следующем примере изображение используется для закраски прямоугольника шириной в 100 пикселей и высотой в 100 пикселей.  Область <xref:System.Windows.Media.TileBrush.Viewport%2A> кисти установлена в 0,0,0.25,0.25, размер базовой мозаики кисти равен 1\/4 области вывода.  Для свойства <xref:System.Windows.Media.TileBrush.TileMode%2A> кисти задано значение <xref:System.Windows.Media.TileMode>,  поэтому прямоугольник заполняется рядами мозаики.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## См. также  
 <xref:System.Windows.Media.ImageBrush>   
 <xref:System.Windows.Media.DrawingBrush>   
 <xref:System.Windows.Media.VisualBrush>   
 <xref:System.Windows.Media.TileBrush>   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)   
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005)   
 [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049)