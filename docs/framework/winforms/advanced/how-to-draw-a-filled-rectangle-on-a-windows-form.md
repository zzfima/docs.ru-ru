---
title: Практическое руководство. Нарисовать закрашенный прямоугольник в форме Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
ms.openlocfilehash: 53fab93f47c16257b5ab2e336b43c6133a31d509
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716898"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="09e57-102">Практическое руководство. Нарисовать закрашенный прямоугольник в форме Windows</span><span class="sxs-lookup"><span data-stu-id="09e57-102">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="09e57-103">В этом примере рисование заполненного прямоугольника в форме.</span><span class="sxs-lookup"><span data-stu-id="09e57-103">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09e57-104">Пример</span><span class="sxs-lookup"><span data-stu-id="09e57-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="09e57-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="09e57-105">Compiling the Code</span></span>  
 <span data-ttu-id="09e57-106">Этот метод нельзя вызывать <xref:System.Windows.Forms.Form.Load> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="09e57-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="09e57-107">Если скрыта другой формой или изменении размера формы, рисунок перерисовываться не будет.</span><span class="sxs-lookup"><span data-stu-id="09e57-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="09e57-108">Чтобы сделать автоматическую перерисовку, нужно переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="09e57-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="09e57-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="09e57-109">Robust Programming</span></span>  
 <span data-ttu-id="09e57-110">Следует всегда вызывать <xref:System.IDisposable.Dispose%2A> на любые объекты, которые потребляют системные ресурсы, такие как <xref:System.Drawing.Brush> и <xref:System.Drawing.Graphics> объектов.</span><span class="sxs-lookup"><span data-stu-id="09e57-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e57-111">См. также</span><span class="sxs-lookup"><span data-stu-id="09e57-111">See also</span></span>
- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="09e57-112">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="09e57-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="09e57-113">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09e57-113">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="09e57-114">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="09e57-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="09e57-115">Кисти и закрашенные фигуры в GDI+</span><span class="sxs-lookup"><span data-stu-id="09e57-115">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
