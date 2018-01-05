---
title: "Практическое руководство. Рисование прямоугольника"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58f29783e48aa7173010ffec6a65f9ac1d8a2b62
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="37883-102">Практическое руководство. Рисование прямоугольника</span><span class="sxs-lookup"><span data-stu-id="37883-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="37883-103">В этом примере показано, как рисование прямоугольника с помощью <xref:System.Windows.Shapes.Rectangle> элемента.</span><span class="sxs-lookup"><span data-stu-id="37883-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="37883-104">Чтобы нарисовать прямоугольник, создайте <xref:System.Windows.Shapes.Rectangle> элемент и указать его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="37883-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="37883-105">Чтобы рисовать внутри прямоугольника, задайте его <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="37883-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="37883-106">Чтобы предоставить структуру прямоугольник, используйте его <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="37883-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="37883-107">Чтобы предоставить прямоугольника скругленные углы, укажите необязательное <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> и <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="37883-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="37883-108"><xref:System.Windows.Shapes.Rectangle.RadiusX%2A> И <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> свойства заданы радиусы осей x и y для эллипса, который используется для скругления углов прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="37883-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="37883-109">В следующем примере два <xref:System.Windows.Shapes.Rectangle> элементы отображаются в <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="37883-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="37883-110">Первый прямоугольник имеет <xref:System.Windows.Media.Brushes.Blue%2A> внутренних.</span><span class="sxs-lookup"><span data-stu-id="37883-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="37883-111">Второй прямоугольник имеет <xref:System.Windows.Media.Brushes.Blue%2A> внутренних, <xref:System.Windows.Media.Brushes.Black%2A> структуры и прямоугольника с закругленными углами.</span><span class="sxs-lookup"><span data-stu-id="37883-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37883-112">Пример</span><span class="sxs-lookup"><span data-stu-id="37883-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="37883-113">Несмотря на то, что в этом примере используется <xref:System.Windows.Controls.Canvas> содержать прямоугольники, можно использовать элементы прямоугольник (и все остальные элементы фигур) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающую нетекстовых содержимое.</span><span class="sxs-lookup"><span data-stu-id="37883-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="37883-114">На самом деле это особенно полезно в качестве фона для частей прямоугольники <xref:System.Windows.Controls.Grid> панелей.</span><span class="sxs-lookup"><span data-stu-id="37883-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="37883-115">Пример см. в разделе [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md).</span><span class="sxs-lookup"><span data-stu-id="37883-115">For an example, see the [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="37883-116">Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="37883-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37883-117">См. также</span><span class="sxs-lookup"><span data-stu-id="37883-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Rectangle>  
 [<span data-ttu-id="37883-118">Пример элементов фигуры</span><span class="sxs-lookup"><span data-stu-id="37883-118">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [<span data-ttu-id="37883-119">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="37883-119">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="37883-120">Общие сведения о таблицах</span><span class="sxs-lookup"><span data-stu-id="37883-120">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
