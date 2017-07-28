---
title: "Практическое руководство. Установка горизонтального и вертикального выравнивания объекта TileBrush | Microsoft Docs"
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
  - "выравнивание, TileBrush"
  - "выравнивание объектов TileBrush по горизонтали"
  - "TileBrush, выравнивание"
  - "выравнивание объектов TileBrush по вертикали"
ms.assetid: 65ae89bd-9246-4c9e-bde4-2fb991d4060d
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Установка горизонтального и вертикального выравнивания объекта TileBrush
В этом примере демонстрируется управление выравниванием по горизонтали и вертикали содержимого мозаики.  Для управления горизонтальным и вертикальным выравниванием объекта <xref:System.Windows.Media.TileBrush> используйте его свойства <xref:System.Windows.Media.TileBrush.AlignmentX%2A> и <xref:System.Windows.Media.TileBrush.AlignmentY%2A>.  
  
 Свойства <xref:System.Windows.Media.TileBrush.AlignmentX%2A> и <xref:System.Windows.Media.TileBrush.AlignmentY%2A> объекта <xref:System.Windows.Media.TileBrush> используются при выполнении одного из следующих условий:  
  
-   Свойство <xref:System.Windows.Media.TileBrush.Stretch%2A> имеет значение <xref:System.Windows.Media.Stretch> или <xref:System.Windows.Media.Stretch>, а свойство <xref:System.Windows.Media.TileBrush.Viewbox%2A> и <xref:System.Windows.Media.TileBrush.Viewport%2A> имеют разные [коэффициенты пропорциональности](GTMT).  
  
-   Свойство <xref:System.Windows.Media.TileBrush.Stretch%2A> имеет значение <xref:System.Windows.Media.Stretch>, а свойство <xref:System.Windows.Media.TileBrush.Viewbox%2A> и <xref:System.Windows.Media.TileBrush.Viewport%2A> имеют разные размеры.  
  
## Пример  
 В следующем примере содержимое объекта <xref:System.Windows.Media.DrawingBrush>, который является типом <xref:System.Windows.Media.TileBrush>, выравнивается по левому верхнему углу мозаики.  Для выравнивания содержимого в примере для свойства <xref:System.Windows.Media.TileBrush.AlignmentX%2A> объекта <xref:System.Windows.Media.DrawingBrush> устанавливается значение <xref:System.Windows.Media.AlignmentX>, а для свойства <xref:System.Windows.Media.TileBrush.AlignmentY%2A> — значение <xref:System.Windows.Media.AlignmentY>.  В результате выполнения примера получается следующий результат:  
  
 ![TileBrush с выравниванием по верхнему левому углу](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm\_TileBrushAlignmentExampleTopLeft")  
TileBrush с содержимым, выровненным по левому верхнему углу  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## Пример  
 В следующем примере содержимое <xref:System.Windows.Media.DrawingBrush> выравнивается по правому нижнему углу его мозаики посредством установки для свойства <xref:System.Windows.Media.TileBrush.AlignmentX%2A> значения <xref:System.Windows.Media.AlignmentX>, а для свойства <xref:System.Windows.Media.TileBrush.AlignmentY%2A> — значения <xref:System.Windows.Media.AlignmentY>.  В результате выполнения примера получается следующий результат.  
  
 ![TileBrush выравниванием по правому нижнему краю](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm\_TileBrushAlignmentExampleBottomRight")  
TileBrush с содержимым, выровненным по правому нижнему углу  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## Пример  
 В следующем примере содержимое <xref:System.Windows.Media.DrawingBrush> выравнивается по левому верхнему углу его мозаики посредством установки для свойства <xref:System.Windows.Media.TileBrush.AlignmentX%2A> значения <xref:System.Windows.Media.AlignmentX>, а для свойства <xref:System.Windows.Media.TileBrush.AlignmentY%2A> — значения <xref:System.Windows.Media.AlignmentY>.  Также для создания шаблона мозаики устанавливается свойство <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.TileMode%2A> объекта <xref:System.Windows.Media.DrawingBrush>.  В результате выполнения примера получается следующий результат.  
  
 ![Мозаичный TileBrush с выравниванием по верхнему левому углу](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm\_TileBrushAlignmentExampleTopLeftTiled")  
Шаблон мозаики с содержимым, выровненным по левому верхнему углу базовой мозаики  
  
 На рисунке выделена базовая мозаика, чтобы можно было видеть, как выравнивается содержимое.  Обратите внимание, что установка свойства <xref:System.Windows.Media.TileBrush.AlignmentX%2A> не оказывает влияния, так как содержимое объекта <xref:System.Windows.Media.DrawingBrush> полностью заполняет базовую мозаику по горизонтали.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## Пример  
 В последнем примере содержимое <xref:System.Windows.Media.DrawingBrush> выравнивается по правому нижнему углу его базового фрагмента путем установки для свойства <xref:System.Windows.Media.TileBrush.AlignmentX%2A> значения <xref:System.Windows.Media.AlignmentX>, а для свойства <xref:System.Windows.Media.TileBrush.AlignmentY%2A> — значения <xref:System.Windows.Media.AlignmentY>.  В результате выполнения примера получается следующий результат.  
  
 ![Мозаичный TileBrush выравниванием по правому нижнему краю](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm\_TileBrushAlignmentExampleBottomRightTiled")  
Шаблон мозаики с содержимым, выровненным по правому нижнему углу базовой мозаики  
  
 Установка свойства <xref:System.Windows.Media.TileBrush.AlignmentX%2A> не оказывает влияния, так как содержимое <xref:System.Windows.Media.DrawingBrush> полностью заполняет базовую мозаику по горизонтали.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 В примерах используются объекты <xref:System.Windows.Media.DrawingBrush> для демонстрации применения свойств <xref:System.Windows.Media.TileBrush.AlignmentX%2A> и <xref:System.Windows.Media.TileBrush.AlignmentY%2A>.  Поведение этих свойств идентично для всех кистей мозаики: <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.ImageBrush> и <xref:System.Windows.Media.VisualBrush>.  Дополнительные сведения о кистях мозаики см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## См. также  
 <xref:System.Windows.Media.DrawingBrush>   
 <xref:System.Windows.Media.ImageBrush>   
 <xref:System.Windows.Media.VisualBrush>   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)