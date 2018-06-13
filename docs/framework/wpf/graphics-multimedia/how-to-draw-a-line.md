---
title: Как начертить линию
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: 1093e754912cd3ee3b8474ed7d190913079a9f9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560629"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="da92e-102">Как начертить линию</span><span class="sxs-lookup"><span data-stu-id="da92e-102">How to: Draw a Line</span></span>
<span data-ttu-id="da92e-103">В этом примере показано, как рисование линий с помощью <xref:System.Windows.Shapes.Line> элемента.</span><span class="sxs-lookup"><span data-stu-id="da92e-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="da92e-104">Чтобы нарисовать линию, создайте <xref:System.Windows.Shapes.Line> элемента.</span><span class="sxs-lookup"><span data-stu-id="da92e-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="da92e-105">Используйте его <xref:System.Windows.Shapes.Line.X1%2A> и <xref:System.Windows.Shapes.Line.Y1%2A> свойства для задания начальной точки; и использовать его <xref:System.Windows.Shapes.Line.X2%2A> и <xref:System.Windows.Shapes.Line.Y2%2A> свойства для задания конечной точки.</span><span class="sxs-lookup"><span data-stu-id="da92e-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="da92e-106">Наконец, установите его <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> так, как выполняется без внешних проявлений линия без штриха.</span><span class="sxs-lookup"><span data-stu-id="da92e-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="da92e-107">Параметр <xref:System.Windows.Shapes.Shape.Fill%2A> элемент для строки не делает ничего, так как строки не имеет внутренней части.</span><span class="sxs-lookup"><span data-stu-id="da92e-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="da92e-108">В следующем примере рисуются три линии внутри <xref:System.Windows.Controls.Canvas> элемента.</span><span class="sxs-lookup"><span data-stu-id="da92e-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da92e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="da92e-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="da92e-110">Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="da92e-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da92e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="da92e-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Line>  
 [<span data-ttu-id="da92e-112">Пример элементов фигуры</span><span class="sxs-lookup"><span data-stu-id="da92e-112">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)
