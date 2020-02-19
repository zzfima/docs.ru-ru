---
title: Как начертить линию
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452952"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="811c1-102">Как начертить линию</span><span class="sxs-lookup"><span data-stu-id="811c1-102">How to: Draw a Line</span></span>
<span data-ttu-id="811c1-103">В этом примере показано, как нарисовать линии с помощью элемента <xref:System.Windows.Shapes.Line>.</span><span class="sxs-lookup"><span data-stu-id="811c1-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="811c1-104">Чтобы нарисовать линию, создайте элемент <xref:System.Windows.Shapes.Line>.</span><span class="sxs-lookup"><span data-stu-id="811c1-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="811c1-105">Чтобы задать начальную точку, используйте его свойства <xref:System.Windows.Shapes.Line.X1%2A> и <xref:System.Windows.Shapes.Line.Y1%2A>. чтобы задать конечную точку, используйте его свойства <xref:System.Windows.Shapes.Line.X2%2A> и <xref:System.Windows.Shapes.Line.Y2%2A>.</span><span class="sxs-lookup"><span data-stu-id="811c1-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="811c1-106">Наконец, задайте его <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>, так как линия без штриха невидима.</span><span class="sxs-lookup"><span data-stu-id="811c1-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="811c1-107">Установка элемента <xref:System.Windows.Shapes.Shape.Fill%2A> для линии не оказывает никакого воздействия, так как линия не имеет внутренней части.</span><span class="sxs-lookup"><span data-stu-id="811c1-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="811c1-108">В следующем примере в элемент <xref:System.Windows.Controls.Canvas> выводится три строки.</span><span class="sxs-lookup"><span data-stu-id="811c1-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="811c1-109">Пример</span><span class="sxs-lookup"><span data-stu-id="811c1-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="811c1-110">Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="811c1-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="811c1-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="811c1-111">See also</span></span>

- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="811c1-112">Пример элементов Shape</span><span class="sxs-lookup"><span data-stu-id="811c1-112">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
