---
title: Практическое руководство. Рисование линии или контурной фигуры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
ms.openlocfilehash: b674c4d80ba6c70c0bdff6d020527a039e5c7baa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-an-outlined-shape"></a><span data-ttu-id="9a44e-102">Практическое руководство. Рисование линии или контурной фигуры</span><span class="sxs-lookup"><span data-stu-id="9a44e-102">How to: Draw an Outlined Shape</span></span>
<span data-ttu-id="9a44e-103">В этом примере рисование контуров эллипса и прямоугольника в форме.</span><span class="sxs-lookup"><span data-stu-id="9a44e-103">This example draws outlined ellipses and rectangles on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a44e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9a44e-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a44e-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9a44e-105">Compiling the Code</span></span>  
 <span data-ttu-id="9a44e-106">Этот метод нельзя вызывать <xref:System.Windows.Forms.Form.Load> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="9a44e-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="9a44e-107">Если формы был изменен или скрыта другой формой, рисунок перерисовываться не будет.</span><span class="sxs-lookup"><span data-stu-id="9a44e-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="9a44e-108">Чтобы сделать перерисовку автоматически, нужно переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="9a44e-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9a44e-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="9a44e-109">Robust Programming</span></span>  
 <span data-ttu-id="9a44e-110">Следует всегда вызывать <xref:System.IDisposable.Dispose%2A> на все объекты, которые потребляют системные ресурсы, такие как <xref:System.Drawing.Pen> и <xref:System.Drawing.Graphics> объектов.</span><span class="sxs-lookup"><span data-stu-id="9a44e-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a44e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9a44e-111">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Drawing.Graphics.DrawRectangle%2A>  
 [<span data-ttu-id="9a44e-112">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="9a44e-112">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="9a44e-113">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="9a44e-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="9a44e-114">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a44e-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
