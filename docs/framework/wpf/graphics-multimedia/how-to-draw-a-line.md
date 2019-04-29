---
title: Практическое руководство. Рисование линии
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: c11dfb9523834ec2e622cb2e62bd6982a1a78fd4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947658"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="58995-102">Практическое руководство. Рисование линии</span><span class="sxs-lookup"><span data-stu-id="58995-102">How to: Draw a Line</span></span>
<span data-ttu-id="58995-103">В этом примере показано, как рисование линий с помощью <xref:System.Windows.Shapes.Line> элемент.</span><span class="sxs-lookup"><span data-stu-id="58995-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="58995-104">Чтобы нарисовать линию, создайте <xref:System.Windows.Shapes.Line> элемент.</span><span class="sxs-lookup"><span data-stu-id="58995-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="58995-105">Используйте его <xref:System.Windows.Shapes.Line.X1%2A> и <xref:System.Windows.Shapes.Line.Y1%2A> свойства для задания начальной точки; и используйте его <xref:System.Windows.Shapes.Line.X2%2A> и <xref:System.Windows.Shapes.Line.Y2%2A> свойства для задания конечной точки.</span><span class="sxs-lookup"><span data-stu-id="58995-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="58995-106">Наконец, установите его <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> так, как в строку без штриха остается невидимым.</span><span class="sxs-lookup"><span data-stu-id="58995-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="58995-107">Параметр <xref:System.Windows.Shapes.Shape.Fill%2A> элемент строку, не оказывает влияния, так как строки не имеет внутренней части.</span><span class="sxs-lookup"><span data-stu-id="58995-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="58995-108">В следующем примере рисуется три строки внутри <xref:System.Windows.Controls.Canvas> элемент.</span><span class="sxs-lookup"><span data-stu-id="58995-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58995-109">Пример</span><span class="sxs-lookup"><span data-stu-id="58995-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="58995-110">Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов-фигур](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="58995-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58995-111">См. также</span><span class="sxs-lookup"><span data-stu-id="58995-111">See also</span></span>

- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="58995-112">Пример элементов-фигур</span><span class="sxs-lookup"><span data-stu-id="58995-112">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
