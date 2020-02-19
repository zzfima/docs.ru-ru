---
title: Практическое руководство. Рисование прямоугольника
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 95191e9d90bc2ac32902399125d9a51192e897bf
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452939"
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="78c0f-102">Практическое руководство. Рисование прямоугольника</span><span class="sxs-lookup"><span data-stu-id="78c0f-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="78c0f-103">В этом примере показано, как нарисовать прямоугольник с помощью элемента <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="78c0f-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="78c0f-104">Чтобы нарисовать прямоугольник, создайте элемент <xref:System.Windows.Shapes.Rectangle> и укажите его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="78c0f-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="78c0f-105">Чтобы закрасить внутри прямоугольника, задайте его <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="78c0f-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="78c0f-106">Чтобы присвоить прямоугольнику структуру, используйте его свойства <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.</span><span class="sxs-lookup"><span data-stu-id="78c0f-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="78c0f-107">Чтобы задать скругленные углы прямоугольника, укажите необязательные свойства <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> и <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>.</span><span class="sxs-lookup"><span data-stu-id="78c0f-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="78c0f-108">Свойства <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> и <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> устанавливают радиус эллипса по оси x и оси y, который используется для закругления углов прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="78c0f-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="78c0f-109">В следующем примере в <xref:System.Windows.Controls.Canvas>рисуются два элемента <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="78c0f-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="78c0f-110">Первый прямоугольник имеет <xref:System.Windows.Media.Brushes.Blue%2A> внутренней.</span><span class="sxs-lookup"><span data-stu-id="78c0f-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="78c0f-111">Второй прямоугольник имеет <xref:System.Windows.Media.Brushes.Blue%2A> внутреннюю, <xref:System.Windows.Media.Brushes.Black%2A>ную структуру и скругленные углы.</span><span class="sxs-lookup"><span data-stu-id="78c0f-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78c0f-112">Пример</span><span class="sxs-lookup"><span data-stu-id="78c0f-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="78c0f-113">Несмотря на то, что в этом примере используется <xref:System.Windows.Controls.Canvas> для хранения прямоугольников, можно использовать элементы Rectangle (и все остальные элементы Shape) с любыми <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающими нетекстовое содержимое.</span><span class="sxs-lookup"><span data-stu-id="78c0f-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="78c0f-114">Фактически, прямоугольники особенно полезны для предоставления фона для частей <xref:System.Windows.Controls.Grid> панелей.</span><span class="sxs-lookup"><span data-stu-id="78c0f-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="78c0f-115">Пример см. в разделе [Общие сведения о таблице](../advanced/table-overview.md).</span><span class="sxs-lookup"><span data-stu-id="78c0f-115">For an example, see the [Table Overview](../advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="78c0f-116">Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="78c0f-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78c0f-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="78c0f-117">See also</span></span>

- <xref:System.Windows.Shapes.Rectangle>
- [<span data-ttu-id="78c0f-118">Пример элементов Shape</span><span class="sxs-lookup"><span data-stu-id="78c0f-118">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [<span data-ttu-id="78c0f-119">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="78c0f-119">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="78c0f-120">Table Overview</span><span class="sxs-lookup"><span data-stu-id="78c0f-120">Table Overview</span></span>](../advanced/table-overview.md)
