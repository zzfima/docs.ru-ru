---
title: Практическое руководство. Рисование последовательности B&#233;сплайны Безье
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 2b74b03137d5a450fb1e436a514877d1a17229ad
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654254"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="e4d8c-102">Практическое руководство. Рисование последовательности B&#233;сплайны Безье</span><span class="sxs-lookup"><span data-stu-id="e4d8c-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="e4d8c-103">Можно использовать <xref:System.Drawing.Graphics.DrawBeziers%2A> метод <xref:System.Drawing.Graphics> класса, чтобы нарисовать последовательность подключенных сплайнов Безье.</span><span class="sxs-lookup"><span data-stu-id="e4d8c-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4d8c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e4d8c-104">Example</span></span>  
 <span data-ttu-id="e4d8c-105">В следующем примере рисуется кривой, которая состоит из двух подключенных сплайнов Безье.</span><span class="sxs-lookup"><span data-stu-id="e4d8c-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="e4d8c-106">Конечная точка первого сплайна Безье является начальной точкой второй сплайна Безье.</span><span class="sxs-lookup"><span data-stu-id="e4d8c-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="e4d8c-107">На следующем рисунке показан подключенных сплайнов и семь точек:</span><span class="sxs-lookup"><span data-stu-id="e4d8c-107">The following illustration shows the connected splines along with the seven points:</span></span>  
  
 ![Рисунок, показывающий соединенные сплайны и семь точек.](./media/how-to-draw-a-sequence-of-bezier-splines/bezier-spline-seven-points.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e4d8c-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e4d8c-109">Compiling the Code</span></span>  
 <span data-ttu-id="e4d8c-110">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="e4d8c-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d8c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e4d8c-111">See also</span></span>
- [<span data-ttu-id="e4d8c-112">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4d8c-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="e4d8c-113">Сплайны Безье в GDI+</span><span class="sxs-lookup"><span data-stu-id="e4d8c-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="e4d8c-114">Построение и рисование кривых</span><span class="sxs-lookup"><span data-stu-id="e4d8c-114">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
