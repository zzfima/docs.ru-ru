---
title: Практическое руководство. Рисование заполненного эллипса в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
ms.openlocfilehash: b892670031e795ecd27b194cdf2cf818f4af6254
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521437"
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a><span data-ttu-id="389f5-102">Практическое руководство. Рисование заполненного эллипса в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="389f5-102">How to: Draw a Filled Ellipse on a Windows Form</span></span>
<span data-ttu-id="389f5-103">В этом примере рисование заполненного эллипса в форме.</span><span class="sxs-lookup"><span data-stu-id="389f5-103">This example draws a filled ellipse on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="389f5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="389f5-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="389f5-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="389f5-105">Compiling the Code</span></span>  
 <span data-ttu-id="389f5-106">Этот метод нельзя вызывать <xref:System.Windows.Forms.Form.Load> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="389f5-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="389f5-107">Если формы был изменен или скрыта другой формой, рисунок перерисовываться не будет.</span><span class="sxs-lookup"><span data-stu-id="389f5-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="389f5-108">Чтобы сделать перерисовку автоматически, нужно переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="389f5-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="389f5-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="389f5-109">Robust Programming</span></span>  
 <span data-ttu-id="389f5-110">Следует всегда вызывать <xref:System.IDisposable.Dispose%2A> на все объекты, которые потребляют системные ресурсы, такие как <xref:System.Drawing.Brush> и <xref:System.Drawing.Graphics> объектов.</span><span class="sxs-lookup"><span data-stu-id="389f5-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="389f5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="389f5-111">See Also</span></span>  
 [<span data-ttu-id="389f5-112">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="389f5-112">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="389f5-113">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="389f5-113">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="389f5-114">Альфа-смешение цвета для линий и заливок</span><span class="sxs-lookup"><span data-stu-id="389f5-114">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="389f5-115">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="389f5-115">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
