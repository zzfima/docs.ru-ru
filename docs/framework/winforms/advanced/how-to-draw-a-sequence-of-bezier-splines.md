---
title: 'Как: рисование последовательности B&#233;сплайны Безье'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 8439e08109630b9a59c8e0359aa4d18e5241412c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="bde21-102">Как: рисование последовательности B&#233;сплайны Безье</span><span class="sxs-lookup"><span data-stu-id="bde21-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="bde21-103">Можно использовать <xref:System.Drawing.Graphics.DrawBeziers%2A> метод <xref:System.Drawing.Graphics> для отрисовки последовательность связанных сплайнов Безье.</span><span class="sxs-lookup"><span data-stu-id="bde21-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bde21-104">Пример</span><span class="sxs-lookup"><span data-stu-id="bde21-104">Example</span></span>  
 <span data-ttu-id="bde21-105">В следующем примере рисуется кривая, состоящая из двух соединенных сплайнов Безье.</span><span class="sxs-lookup"><span data-stu-id="bde21-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="bde21-106">Конечная точка первого сплайна Безье является начальной точкой второй сплайна Безье.</span><span class="sxs-lookup"><span data-stu-id="bde21-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="bde21-107">На следующем рисунке соединенные сплайны и семь точек.</span><span class="sxs-lookup"><span data-stu-id="bde21-107">The following illustration shows the connected splines along with the seven points.</span></span>  
  
 <span data-ttu-id="bde21-108">![Сплайн Безье](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span><span class="sxs-lookup"><span data-stu-id="bde21-108">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bde21-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bde21-109">Compiling the Code</span></span>  
 <span data-ttu-id="bde21-110">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="bde21-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bde21-111">См. также</span><span class="sxs-lookup"><span data-stu-id="bde21-111">See Also</span></span>  
 [<span data-ttu-id="bde21-112">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bde21-112">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="bde21-113">Сплайны Безье в GDI+</span><span class="sxs-lookup"><span data-stu-id="bde21-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="bde21-114">Построение и рисование кривых</span><span class="sxs-lookup"><span data-stu-id="bde21-114">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
