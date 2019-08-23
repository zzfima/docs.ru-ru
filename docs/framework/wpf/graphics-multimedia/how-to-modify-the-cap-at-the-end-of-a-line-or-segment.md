---
title: Практическое руководство. Изменение завершения отрезка в конце линии или сегмента
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 53487417636dae8d855fe70b7b9255351a2dfb1e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916138"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="993a9-102">Практическое руководство. Изменение завершения отрезка в конце линии или сегмента</span><span class="sxs-lookup"><span data-stu-id="993a9-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="993a9-103">В этом примере показано, как изменить фигуру в начале или в конце открытого <xref:System.Windows.Shapes.Shape> элемента.</span><span class="sxs-lookup"><span data-stu-id="993a9-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="993a9-104">Чтобы изменить ограничение в начале открытого <xref:System.Windows.Shapes.Shape>объекта, используйте его <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="993a9-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="993a9-105">Чтобы изменить ограничение в конце открытого <xref:System.Windows.Shapes.Shape>объекта, используйте его <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="993a9-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="993a9-106">Чтобы просмотреть доступные концы строк, см <xref:System.Windows.Media.PenLineCap> . перечисление.</span><span class="sxs-lookup"><span data-stu-id="993a9-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="993a9-107">Это свойство влияет только на открытую фигуру, например <xref:System.Windows.Shapes.Line>, на <xref:System.Windows.Shapes.Polyline>, или на открытый <xref:System.Windows.Shapes.Path> элемент.</span><span class="sxs-lookup"><span data-stu-id="993a9-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="993a9-108">В следующем примере рисуются <xref:System.Windows.Shapes.Polyline> четыре элемента и используется другой набор фигур на концах каждого из них.</span><span class="sxs-lookup"><span data-stu-id="993a9-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="993a9-109">Пример</span><span class="sxs-lookup"><span data-stu-id="993a9-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="993a9-110">Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="993a9-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="993a9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="993a9-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
