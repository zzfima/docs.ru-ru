---
title: Как установить размер мозаики для TileBrush
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186838"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="f9611-102">Как установить размер мозаики для TileBrush</span><span class="sxs-lookup"><span data-stu-id="f9611-102">How to: Set the Tile Size for a TileBrush</span></span>

<span data-ttu-id="f9611-103">В этом примере показано, как <xref:System.Windows.Media.TileBrush>установить размер плитки для .</span><span class="sxs-lookup"><span data-stu-id="f9611-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="f9611-104">По умолчанию, <xref:System.Windows.Media.TileBrush> производит одну плитку, которая полностью заполняет область, которую вы рисуете.</span><span class="sxs-lookup"><span data-stu-id="f9611-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="f9611-105">Это поведение можно переопределить, <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> установив и свойства.</span><span class="sxs-lookup"><span data-stu-id="f9611-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>

<span data-ttu-id="f9611-106">Свойство <xref:System.Windows.Media.TileBrush.Viewport%2A> определяет размер плитки для <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="f9611-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="f9611-107">По умолчанию значение <xref:System.Windows.Media.TileBrush.Viewport%2A> свойства относительно размера окрашенной площади.</span><span class="sxs-lookup"><span data-stu-id="f9611-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="f9611-108">Чтобы сделать свойство <xref:System.Windows.Media.TileBrush.Viewport%2A> указать абсолютный размер плитки, установите свойство <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> на <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="f9611-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>

## <a name="example"></a><span data-ttu-id="f9611-109">Пример</span><span class="sxs-lookup"><span data-stu-id="f9611-109">Example</span></span>

<span data-ttu-id="f9611-110">Следующий пример <xref:System.Windows.Media.ImageBrush>использует, тип <xref:System.Windows.Media.TileBrush>, для рисования прямоугольника с плиткой.</span><span class="sxs-lookup"><span data-stu-id="f9611-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="f9611-111">Пример устанавливает каждую плитку до 50 процентов на 50 процентов от выходной области (прямоугольник).</span><span class="sxs-lookup"><span data-stu-id="f9611-111">The example sets each tile to 50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="f9611-112">В результате прямоугольник заполняется четырьмя проекциями изображения.</span><span class="sxs-lookup"><span data-stu-id="f9611-112">As a result, the rectangle is painted with four projections of the image.</span></span>

<span data-ttu-id="f9611-113">На следующей иллюстрации показан выход, который приводит пример:</span><span class="sxs-lookup"><span data-stu-id="f9611-113">The following illustration shows the output that the example produces:</span></span>

![Прямоугольник с четырьмя вишнями, демонстрирующими плитку с изображением кисти.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

<span data-ttu-id="f9611-115">Следующий пример <xref:System.Windows.Media.ImageBrush>создает, <xref:System.Windows.Media.TileBrush.Viewport%2A> устанавливает `0,0,25,25` его <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute>к и его к, и использует его для того чтобы покрасить другой прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="f9611-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="f9611-116">В результате кисть создает мозаику размером 25 пикселей в ширину и 25 пикселей в высоту.</span><span class="sxs-lookup"><span data-stu-id="f9611-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>

<span data-ttu-id="f9611-117">На следующей иллюстрации показан выход, который приводит пример:</span><span class="sxs-lookup"><span data-stu-id="f9611-117">The following illustration shows the output that the example produces:</span></span>

![Прямоугольник с сорока восемью вишнями, демонстрирующими черепицу TileBrush с Viewport.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

<span data-ttu-id="f9611-119">Следующий пример является частью большого примера.</span><span class="sxs-lookup"><span data-stu-id="f9611-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="f9611-120">Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)</span><span class="sxs-lookup"><span data-stu-id="f9611-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>

<span data-ttu-id="f9611-121">Хотя этот пример <xref:System.Windows.Media.ImageBrush> использует <xref:System.Windows.Media.TileBrush.Viewport%2A> класс, <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> и свойства ведут <xref:System.Windows.Media.TileBrush> себя одинаково для <xref:System.Windows.Media.DrawingBrush> других <xref:System.Windows.Media.VisualBrush>объектов, то есть для и .</span><span class="sxs-lookup"><span data-stu-id="f9611-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="f9611-122">Для получения <xref:System.Windows.Media.ImageBrush> дополнительной информации о и других <xref:System.Windows.Media.TileBrush> объектов, см Картина с [изображениями, рисунки, и визуальные эффекты](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="f9611-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9611-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f9611-123">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="f9611-124">Заполнение с использованием изображений, рисунков и визуальных элементов</span><span class="sxs-lookup"><span data-stu-id="f9611-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="f9611-125">Создание различных шаблонов мозаики с помощью TileBrush</span><span class="sxs-lookup"><span data-stu-id="f9611-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
