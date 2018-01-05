---
title: "Как установить размер мозаики для TileBrush"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e9b746fe66635054dbd35463f727d28a8abd3d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="d95c6-102">Как установить размер мозаики для TileBrush</span><span class="sxs-lookup"><span data-stu-id="d95c6-102">How to: Set the Tile Size for a TileBrush</span></span>
<span data-ttu-id="d95c6-103">В этом примере показано, как установить размер мозаики для <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="d95c6-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="d95c6-104">По умолчанию <xref:System.Windows.Media.TileBrush> создает один фрагмент, который полностью заполняет область раскрашивания.</span><span class="sxs-lookup"><span data-stu-id="d95c6-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="d95c6-105">Это поведение можно переопределить, задав <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="d95c6-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>  
  
 <span data-ttu-id="d95c6-106"><xref:System.Windows.Media.TileBrush.Viewport%2A> Свойство указывает размер мозаики для <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="d95c6-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="d95c6-107">По умолчанию значение <xref:System.Windows.Media.TileBrush.Viewport%2A> свойства задается относительно размера закрашиваемой области.</span><span class="sxs-lookup"><span data-stu-id="d95c6-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="d95c6-108">Чтобы сделать <xref:System.Windows.Media.TileBrush.Viewport%2A> указывать абсолютный размер мозаики, задайте <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> свойства <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="d95c6-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d95c6-109">Пример</span><span class="sxs-lookup"><span data-stu-id="d95c6-109">Example</span></span>  
 <span data-ttu-id="d95c6-110">В следующем примере используется <xref:System.Windows.Media.ImageBrush>, тип <xref:System.Windows.Media.TileBrush>, для заполнения прямоугольника мозаикой.</span><span class="sxs-lookup"><span data-stu-id="d95c6-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="d95c6-111">В примере для фрагмента мозаики задаются размеры 50 % на 50 % от области вывода (прямоугольника).</span><span class="sxs-lookup"><span data-stu-id="d95c6-111">The example sets each tile to  50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="d95c6-112">В результате прямоугольник заполняется четырьмя проекциями изображения.</span><span class="sxs-lookup"><span data-stu-id="d95c6-112">As a result, the rectangle is painted with four projections of the image.</span></span>  
  
 <span data-ttu-id="d95c6-113">На следующей иллюстрации показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="d95c6-113">The following illustration shows the output that the example produces.</span></span>
  
 <span data-ttu-id="d95c6-114">![Пример мозаики с использованием кисти изображения](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")</span><span class="sxs-lookup"><span data-stu-id="d95c6-114">![Example of tiling with an image brush](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 <span data-ttu-id="d95c6-115">В следующем примере создается <xref:System.Windows.Media.ImageBrush>, задает его <xref:System.Windows.Media.TileBrush.Viewport%2A> для `0,0,25,25` и его <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> для <xref:System.Windows.Media.BrushMappingMode.Absolute>и использует их для раскрашивания другого прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="d95c6-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="d95c6-116">В результате кисть создает мозаику размером 25 пикселей в ширину и 25 пикселей в высоту.</span><span class="sxs-lookup"><span data-stu-id="d95c6-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>  
  
 <span data-ttu-id="d95c6-117">На следующей иллюстрации показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="d95c6-117">The following illustration shows the output that the example produces.</span></span>  
  
 <span data-ttu-id="d95c6-118">![Мозаичная кисть TileBrush с областью отображения 0, 0, 0,25, 0,25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")</span><span class="sxs-lookup"><span data-stu-id="d95c6-118">![A tiled TileBrush with a Viewport of 0,0,0.25,0.25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 <span data-ttu-id="d95c6-119">Следующий пример является частью большого примера.</span><span class="sxs-lookup"><span data-stu-id="d95c6-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="d95c6-120">Полный пример см. в разделе [ImageBrush образец](http://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="d95c6-120">For the complete sample, see [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
 <span data-ttu-id="d95c6-121">Несмотря на то, что в этом примере используется <xref:System.Windows.Media.ImageBrush> класса <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> ведут себя одинаково для других <xref:System.Windows.Media.TileBrush> объектов, то есть для <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="d95c6-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="d95c6-122">Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> , а другой <xref:System.Windows.Media.TileBrush> объектов, в разделе [Рисование с помощью изображения, рисунки и визуальные элементы](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="d95c6-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d95c6-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d95c6-123">See Also</span></span>  
 <xref:System.Windows.Media.TileBrush>  
 [<span data-ttu-id="d95c6-124">Заполнение с использованием изображений, рисунков и визуальных элементов</span><span class="sxs-lookup"><span data-stu-id="d95c6-124">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="d95c6-125">Создание различных шаблонов мозаики с помощью TileBrush</span><span class="sxs-lookup"><span data-stu-id="d95c6-125">Create Different Tile Patterns with a TileBrush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)
