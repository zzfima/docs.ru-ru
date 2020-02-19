---
title: Практическое руководство. Рисование эллипса или круга
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 5f17615da4907cba6e25b68f2f934602c2f8a390
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452926"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="8459f-102">Практическое руководство. Рисование эллипса или круга</span><span class="sxs-lookup"><span data-stu-id="8459f-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="8459f-103">В этом примере показано, как рисовать эллипсы и окружности с помощью элемента <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="8459f-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="8459f-104">Чтобы нарисовать эллипс, создайте элемент <xref:System.Windows.Shapes.Ellipse> и укажите его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="8459f-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="8459f-105">Используйте его свойство <xref:System.Windows.Shapes.Shape.Fill%2A>, чтобы указать <xref:System.Windows.Media.Brush>, используемый для заполнения внутренней части эллипса.</span><span class="sxs-lookup"><span data-stu-id="8459f-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="8459f-106">Используйте его свойство <xref:System.Windows.Shapes.Shape.Stroke%2A>, чтобы указать <xref:System.Windows.Media.Brush>, используемый для рисования контура эллипса.</span><span class="sxs-lookup"><span data-stu-id="8459f-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="8459f-107">Свойство <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> задает толщину контура эллипса.</span><span class="sxs-lookup"><span data-stu-id="8459f-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="8459f-108">Чтобы нарисовать круг, сделайте <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> элемента <xref:System.Windows.Shapes.Ellipse> равными друг другу.</span><span class="sxs-lookup"><span data-stu-id="8459f-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="8459f-109">В следующем примере в <xref:System.Windows.Controls.Canvas>рисуется четыре элемента <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="8459f-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8459f-110">Пример</span><span class="sxs-lookup"><span data-stu-id="8459f-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="8459f-111">Хотя в этом примере используется <xref:System.Windows.Controls.Canvas> для хранения эллипсов, можно использовать элементы Ellipse (и все остальные элементы Shape) с любыми <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающими нетекстовое содержимое.</span><span class="sxs-lookup"><span data-stu-id="8459f-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="8459f-112">Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="8459f-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8459f-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8459f-113">See also</span></span>

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="8459f-114">Пример элементов Shape</span><span class="sxs-lookup"><span data-stu-id="8459f-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
