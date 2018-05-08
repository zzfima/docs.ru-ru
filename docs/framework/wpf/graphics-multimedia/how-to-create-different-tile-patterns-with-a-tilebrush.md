---
title: Практическое руководство. Создание различных шаблонов с помощью TileBrush
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: 01004c66a8bd820f05e6e1f6c77a9fe7d30bca46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a>Практическое руководство. Создание различных шаблонов с помощью TileBrush
В этом примере показано, как использовать <xref:System.Windows.Media.TileBrush.TileMode%2A> свойство <xref:System.Windows.Media.TileBrush> для создания шаблона.  
  
 <xref:System.Windows.Media.TileBrush.TileMode%2A> Свойство позволяет указать, как содержимое <xref:System.Windows.Media.TileBrush> является повторяется, то есть, мозаичное заполнение области вывода. Чтобы создать шаблон, необходимо задать <xref:System.Windows.Media.TileBrush.TileMode%2A> для <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, или <xref:System.Windows.Media.TileMode.FlipXY>. Необходимо также задать <xref:System.Windows.Media.TileBrush.Viewport%2A> из <xref:System.Windows.Media.TileBrush> , чтобы оно было меньше, чем область закрашивания; в противном случае — только один фрагмент производству, независимо от того, что <xref:System.Windows.Media.TileBrush.TileMode%2A> используется параметр.  
  
## <a name="example"></a>Пример  
 В следующем примере создается пять <xref:System.Windows.Media.DrawingBrush> объектов, дает им каждый отдельный <xref:System.Windows.Media.TileBrush.TileMode%2A> установку и использует их для рисования пяти прямоугольников. Несмотря на то, что в этом примере используется <xref:System.Windows.Media.DrawingBrush> для демонстрации <xref:System.Windows.Media.TileBrush.TileMode%2A> поведение, <xref:System.Windows.Media.TileBrush.TileMode%2A> работает одинаково для всех <xref:System.Windows.Media.TileBrush> объектов, то есть для <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, и <xref:System.Windows.Media.DrawingBrush>.  
  
 На следующей иллюстрации показан результат выполнения этого примера.  
  
 ![Мозаичное заполнение в выходных данных примера TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")  
Шаблоны мозаики, созданные с помощью свойства TileMode  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a>См. также  
 [Установка размера плитки для объекта TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)  
 [Заполнение с использованием изображений, рисунков и визуальных элементов](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
