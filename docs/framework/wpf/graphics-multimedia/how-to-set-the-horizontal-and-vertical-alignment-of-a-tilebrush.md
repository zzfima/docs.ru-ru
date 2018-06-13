---
title: Практическое руководство. Установка горизонтального и вертикального выравнивания объекта TileBrush
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], alignment of
- vertical alignment of TileBrushes [WPF]
- aligning [WPF], TileBrushes
- horizontal alignment of Tilebrushes [WPF]
ms.assetid: 65ae89bd-9246-4c9e-bde4-2fb991d4060d
ms.openlocfilehash: 4352067f149a1af25cd0a04a12596693188445fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563601"
---
# <a name="how-to-set-the-horizontal-and-vertical-alignment-of-a-tilebrush"></a>Практическое руководство. Установка горизонтального и вертикального выравнивания объекта TileBrush
В этом примере показано, как управлять горизонтальным и вертикальным выравниванием содержимого фрагмента мозаики. Для управления выравниванием по горизонтали и вертикали <xref:System.Windows.Media.TileBrush>, использовать его <xref:System.Windows.Media.TileBrush.AlignmentX%2A> и <xref:System.Windows.Media.TileBrush.AlignmentY%2A> свойства.  
  
 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> И <xref:System.Windows.Media.TileBrush.AlignmentY%2A> свойства <xref:System.Windows.Media.TileBrush> используются при следующих условий верно:  
  
-   <xref:System.Windows.Media.TileBrush.Stretch%2A> Свойство <xref:System.Windows.Media.Stretch.Uniform> или <xref:System.Windows.Media.Stretch.UniformToFill> и <xref:System.Windows.Media.TileBrush.Viewbox%2A> и <xref:System.Windows.Media.TileBrush.Viewport%2A> имеют различные пропорции.  
  
-   <xref:System.Windows.Media.TileBrush.Stretch%2A> Свойство <xref:System.Windows.Media.Stretch.None> и <xref:System.Windows.Media.TileBrush.Viewbox%2A> и <xref:System.Windows.Media.TileBrush.Viewport%2A> имеют разный размер.  
  
## <a name="example"></a>Пример  
 Следующий пример Выравнивает содержимое <xref:System.Windows.Media.DrawingBrush>, который представляет собой тип <xref:System.Windows.Media.TileBrush>, в верхнем левом углу его мозаики. Для выравнивания содержимого в примере устанавливается <xref:System.Windows.Media.TileBrush.AlignmentX%2A> свойство <xref:System.Windows.Media.DrawingBrush> для <xref:System.Windows.Media.AlignmentX.Left> и <xref:System.Windows.Media.TileBrush.AlignmentY%2A> свойства <xref:System.Windows.Media.AlignmentY.Top>. В этом примере формируются следующие данные:  
  
 ![TileBrush с верхней&#45;левому краю](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm_TileBrushAlignmentExampleTopLeft")  
Объект TileBrush с содержимым, выровненным по левому верхнему углу  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## <a name="example"></a>Пример  
 Следующий пример Выравнивает содержимое <xref:System.Windows.Media.DrawingBrush> в правом нижнем углу его мозаики посредством установки <xref:System.Windows.Media.TileBrush.AlignmentX%2A> свойства <xref:System.Windows.Media.AlignmentX.Right> и <xref:System.Windows.Media.TileBrush.AlignmentY%2A> свойства <xref:System.Windows.Media.AlignmentY.Bottom>. В этом примере выводятся следующие данные.  
  
 ![TileBrush с нижней&#45;правой выравнивание](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm_TileBrushAlignmentExampleBottomRight")  
Объект TileBrush с содержимым, выровненным по правому нижнему углу  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## <a name="example"></a>Пример  
 Следующий пример Выравнивает содержимое <xref:System.Windows.Media.DrawingBrush> в левом верхнем углу его мозаики посредством установки <xref:System.Windows.Media.TileBrush.AlignmentX%2A> свойства <xref:System.Windows.Media.AlignmentX.Left> и <xref:System.Windows.Media.TileBrush.AlignmentY%2A> свойства <xref:System.Windows.Media.AlignmentY.Top>. Кроме того, задается <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.TileMode%2A> из <xref:System.Windows.Media.DrawingBrush> для создания шаблона мозаики. В этом примере выводятся следующие данные.  
  
 ![Объект Мозаичная кисть TileBrush с верхней&#45;левому краю](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm_TileBrushAlignmentExampleTopLeftTiled")  
Шаблон мозаики с содержимым, выровненным по левому верхнему углу базового фрагмента мозаики  
  
 На рисунке базовый фрагмент мозаики выделен цветом, чтобы можно было увидеть, как выравнивается содержимое. Обратите внимание, что <xref:System.Windows.Media.TileBrush.AlignmentX%2A> политика не оказывает влияния так как содержимое <xref:System.Windows.Media.DrawingBrush> полностью заполняет базовый мозаичный элемент по горизонтали.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## <a name="example"></a>Пример  
 Последний пример Выравнивает содержимое <xref:System.Windows.Media.DrawingBrush> к правому нижнему углу базовой плитке, задав <xref:System.Windows.Media.TileBrush.AlignmentX%2A> свойства <xref:System.Windows.Media.AlignmentX.Right> и <xref:System.Windows.Media.TileBrush.AlignmentY%2A> свойства <xref:System.Windows.Media.AlignmentY.Bottom>. В этом примере выводятся следующие данные.  
  
 ![Объект Мозаичная кисть TileBrush с нижней&#45;правой выравнивание](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm_TileBrushAlignmentExampleBottomRightTiled")  
Шаблон мозаики с содержимым, выровненным по правому нижнему углу базового фрагмента мозаики  
  
 Опять же <xref:System.Windows.Media.TileBrush.AlignmentX%2A> политика не оказывает влияния так как содержимое <xref:System.Windows.Media.DrawingBrush> полностью заполняет базовый мозаичный элемент по горизонтали.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 В примерах используется <xref:System.Windows.Media.DrawingBrush> объектов, чтобы продемонстрировать, как <xref:System.Windows.Media.TileBrush.AlignmentX%2A> и <xref:System.Windows.Media.TileBrush.AlignmentY%2A> используются свойства. Эти свойства ведут себя одинаково для всех кистей мозаики: <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.ImageBrush>, и <xref:System.Windows.Media.VisualBrush>. Дополнительные сведения о мозаичных кистях для рисования см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 [Заливка с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
