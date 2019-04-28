---
title: Практическое руководство. Закрашивание области с помощью Drawing
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 6b204ae631912181333e2559ebadcdc37e7693b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010089"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a><span data-ttu-id="37249-102">Практическое руководство. Закрашивание области с помощью Drawing</span><span class="sxs-lookup"><span data-stu-id="37249-102">How to: Paint an Area with a Drawing</span></span>
<span data-ttu-id="37249-103">Этот пример показывает, как можно закрасить область рисунком.</span><span class="sxs-lookup"><span data-stu-id="37249-103">This example shows how to paint an area with a drawing.</span></span> <span data-ttu-id="37249-104">Чтобы закрасить область рисунком, используйте <xref:System.Windows.Media.DrawingBrush> и одного или нескольких <xref:System.Windows.Media.Drawing> объектов.</span><span class="sxs-lookup"><span data-stu-id="37249-104">To paint an area with a drawing, you use a <xref:System.Windows.Media.DrawingBrush> and one or more <xref:System.Windows.Media.Drawing> objects.</span></span>   <span data-ttu-id="37249-105">В следующем примере используется <xref:System.Windows.Media.DrawingBrush> для закраски объекта рисунком из двух эллипсов.</span><span class="sxs-lookup"><span data-stu-id="37249-105">The following example uses a <xref:System.Windows.Media.DrawingBrush> to paint an object with a drawing of two ellipses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37249-106">Пример</span><span class="sxs-lookup"><span data-stu-id="37249-106">Example</span></span>  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 <span data-ttu-id="37249-107">На следующем рисунке показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="37249-107">The following illustration shows the example's output.</span></span>  
  
 <span data-ttu-id="37249-108">![Результат DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span><span class="sxs-lookup"><span data-stu-id="37249-108">![Output from a DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span></span>  
  
 <span data-ttu-id="37249-109">(Центр фигуры белого, по причинам, описанным в [управление заливкой составных фигур](how-to-control-the-fill-of-a-composite-shape.md).)</span><span class="sxs-lookup"><span data-stu-id="37249-109">(The center of the shape is white for reasons described in     [Control the Fill of a Composite Shape](how-to-control-the-fill-of-a-composite-shape.md).)</span></span>  
  
 <span data-ttu-id="37249-110">Установив <xref:System.Windows.Media.DrawingBrush> объекта <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.TileMode%2A> свойства, можно создать повторяющийся шаблон.</span><span class="sxs-lookup"><span data-stu-id="37249-110">By setting a <xref:System.Windows.Media.DrawingBrush> object's <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties, you can create a repeating pattern.</span></span> <span data-ttu-id="37249-111">Следующий пример выполняет заливку объекта шаблоном, созданным рисунком из двух эллипсов.</span><span class="sxs-lookup"><span data-stu-id="37249-111">The following example paints an object with a pattern created from a drawing of two ellipses.</span></span>  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 <span data-ttu-id="37249-112">На следующем рисунке показан мозаичный <xref:System.Windows.Media.DrawingBrush> выходных данных.</span><span class="sxs-lookup"><span data-stu-id="37249-112">The following illustration shows the tiled <xref:System.Windows.Media.DrawingBrush> output.</span></span>  
  
 <span data-ttu-id="37249-113">![Мозаичный результат работы DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span><span class="sxs-lookup"><span data-stu-id="37249-113">![Tiled output from a DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span></span>  
  
 <span data-ttu-id="37249-114">Дополнительные сведения о кистях для рисования см. в разделе [Рисование с помощью изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="37249-114">For more information about drawing brushes, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span> <span data-ttu-id="37249-115">Дополнительные сведения о <xref:System.Windows.Media.Drawing> объектов, см. в разделе [Обзор объектов Drawing](drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="37249-115">For more information about <xref:System.Windows.Media.Drawing> objects, see the [Drawing Objects Overview](drawing-objects-overview.md).</span></span>
