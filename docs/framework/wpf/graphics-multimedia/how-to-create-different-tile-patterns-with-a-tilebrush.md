---
title: Как выполнить Создание различных шаблонов мозаики с помощью TileBrush
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: d6b6d4a20d43478131d3adb7c7d091214b3c5871
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722017"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="cf63f-102">Как выполнить Создание различных шаблонов мозаики с помощью TileBrush</span><span class="sxs-lookup"><span data-stu-id="cf63f-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="cf63f-103">В этом примере показано, как использовать <xref:System.Windows.Media.TileBrush.TileMode%2A> свойство <xref:System.Windows.Media.TileBrush> для создания шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf63f-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="cf63f-104"><xref:System.Windows.Media.TileBrush.TileMode%2A> Свойство позволяет указать, как содержимое <xref:System.Windows.Media.TileBrush> является повторяется, то есть, мозаикой для заполнения области вывода.</span><span class="sxs-lookup"><span data-stu-id="cf63f-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="cf63f-105">Чтобы создать шаблон, необходимо задать <xref:System.Windows.Media.TileBrush.TileMode%2A> для <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, или <xref:System.Windows.Media.TileMode.FlipXY>.</span><span class="sxs-lookup"><span data-stu-id="cf63f-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="cf63f-106">Необходимо также задать <xref:System.Windows.Media.TileBrush.Viewport%2A> из <xref:System.Windows.Media.TileBrush> , чтобы он был меньше, чем область закрашивания; в противном случае только одна Плитка производству, независимо от того, который <xref:System.Windows.Media.TileBrush.TileMode%2A> используется параметр.</span><span class="sxs-lookup"><span data-stu-id="cf63f-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf63f-107">Пример</span><span class="sxs-lookup"><span data-stu-id="cf63f-107">Example</span></span>  
 <span data-ttu-id="cf63f-108">В следующем примере создается пять <xref:System.Windows.Media.DrawingBrush> объекты, дает им каждый отдельный <xref:System.Windows.Media.TileBrush.TileMode%2A> параметр и использует их для рисования пяти прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="cf63f-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="cf63f-109">Несмотря на то, что в этом примере используется <xref:System.Windows.Media.DrawingBrush> для демонстрации <xref:System.Windows.Media.TileBrush.TileMode%2A> поведение, <xref:System.Windows.Media.TileBrush.TileMode%2A> работает одинаково для всех <xref:System.Windows.Media.TileBrush> объектов, то есть для <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, и <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="cf63f-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="cf63f-110">На следующей иллюстрации показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="cf63f-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="cf63f-111">![TileBrush мозаичного заполнения пример выходных данных](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="cf63f-111">![TileBrush tiling example output](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="cf63f-112">Шаблоны мозаики, созданные с помощью свойства TileMode</span><span class="sxs-lookup"><span data-stu-id="cf63f-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="cf63f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cf63f-113">See also</span></span>
- [<span data-ttu-id="cf63f-114">Установка размера плитки для объекта TileBrush</span><span class="sxs-lookup"><span data-stu-id="cf63f-114">Set the Tile Size for a TileBrush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)
- [<span data-ttu-id="cf63f-115">Заполнение с использованием изображений, рисунков и визуальных элементов</span><span class="sxs-lookup"><span data-stu-id="cf63f-115">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
