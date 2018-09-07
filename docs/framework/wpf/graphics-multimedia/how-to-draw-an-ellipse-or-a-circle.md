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
ms.openlocfilehash: ddeada8619d1b6c8970f1efb7cca1bc98773d0c5
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44079117"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="f11ec-102">Практическое руководство. Рисование эллипса или круга</span><span class="sxs-lookup"><span data-stu-id="f11ec-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="f11ec-103">В этом примере показано, как рисование эллипсов и кругов с помощью <xref:System.Windows.Shapes.Ellipse> элемент.</span><span class="sxs-lookup"><span data-stu-id="f11ec-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="f11ec-104">Чтобы нарисовать эллипс, создайте <xref:System.Windows.Shapes.Ellipse> элемент и указать его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="f11ec-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="f11ec-105">Используйте его <xref:System.Windows.Shapes.Shape.Fill%2A> свойство, чтобы указать <xref:System.Windows.Media.Brush> , используемый для закрашивания внутренней части эллипса.</span><span class="sxs-lookup"><span data-stu-id="f11ec-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="f11ec-106">Используйте его <xref:System.Windows.Shapes.Shape.Stroke%2A> свойство, чтобы указать <xref:System.Windows.Media.Brush> , используемый для рисования контура эллипса.</span><span class="sxs-lookup"><span data-stu-id="f11ec-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="f11ec-107"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Свойство задает толщину контура эллипса.</span><span class="sxs-lookup"><span data-stu-id="f11ec-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="f11ec-108">Чтобы нарисовать окружность, <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> из <xref:System.Windows.Shapes.Ellipse> элемент, равный друг с другом.</span><span class="sxs-lookup"><span data-stu-id="f11ec-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="f11ec-109">В следующем примере рисуется четыре <xref:System.Windows.Shapes.Ellipse> элементы внутри <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="f11ec-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f11ec-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f11ec-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="f11ec-111">Несмотря на то, что в этом примере используется <xref:System.Windows.Controls.Canvas> должен содержать кнопку с многоточием, можно использовать элементы эллипса (и все остальные элементы фигуры) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающий нетекстовое содержимое.</span><span class="sxs-lookup"><span data-stu-id="f11ec-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="f11ec-112">Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов-фигур](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="f11ec-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f11ec-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f11ec-113">See Also</span></span>  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [<span data-ttu-id="f11ec-114">Пример элементов-фигур</span><span class="sxs-lookup"><span data-stu-id="f11ec-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
