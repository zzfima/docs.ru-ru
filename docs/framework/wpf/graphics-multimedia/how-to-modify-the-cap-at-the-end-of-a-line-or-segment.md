---
title: Практическое руководство. Изменение завершения отрезка в конце линии или сегмента
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 462e32520393a1c23809cce8eb3c130c13bc882f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977682"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="d8ca3-102">Практическое руководство. Изменение завершения отрезка в конце линии или сегмента</span><span class="sxs-lookup"><span data-stu-id="d8ca3-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="d8ca3-103">В этом примере показано, как способы изменения фигуры в начале или конце открытой <xref:System.Windows.Shapes.Shape> элемент.</span><span class="sxs-lookup"><span data-stu-id="d8ca3-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="d8ca3-104">Изменение завершения отрезка в начале открытой <xref:System.Windows.Shapes.Shape>, использовать его <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="d8ca3-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="d8ca3-105">Изменение завершения отрезка в конце открытой <xref:System.Windows.Shapes.Shape>, использовать его <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="d8ca3-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="d8ca3-106">Для просмотра доступных отрезков, см. в разделе <xref:System.Windows.Media.PenLineCap> перечисления.</span><span class="sxs-lookup"><span data-stu-id="d8ca3-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8ca3-107">Это свойство влияет только на открытые фигуры, такие как <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, или открытый <xref:System.Windows.Shapes.Path> элемент.</span><span class="sxs-lookup"><span data-stu-id="d8ca3-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="d8ca3-108">В следующем примере рисуется четыре <xref:System.Windows.Shapes.Polyline> элементы и использует другой набор фигур на концах каждого из них.</span><span class="sxs-lookup"><span data-stu-id="d8ca3-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8ca3-109">Пример</span><span class="sxs-lookup"><span data-stu-id="d8ca3-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="d8ca3-110">Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов-фигур](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="d8ca3-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8ca3-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d8ca3-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
