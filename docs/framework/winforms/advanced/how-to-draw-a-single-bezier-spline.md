---
title: 'Как: нарисовать один B&#233;сплайн Безье'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 9e91b63275c37fc0cdde5721fddd114e1bf2264e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="f4a95-102">Как: нарисовать один B&#233;сплайн Безье</span><span class="sxs-lookup"><span data-stu-id="f4a95-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="f4a95-103">Сплайн Безье, определяемый четырьмя точками: начальной точкой, две контрольные точки и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f4a95-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4a95-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f4a95-104">Example</span></span>  
 <span data-ttu-id="f4a95-105">В следующем примере рисуется сплайн Безье с начальной точкой (10, 100) и конечной точки (200, 100).</span><span class="sxs-lookup"><span data-stu-id="f4a95-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="f4a95-106">Контрольными точками являются (100, 10) и (150, 150).</span><span class="sxs-lookup"><span data-stu-id="f4a95-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="f4a95-107">На следующем рисунке получившийся сплайн Безье, вместе с его начальную точку, контрольные точки и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f4a95-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="f4a95-108">На рисунке также выпуклая оболочка сплайна, которая представляет собой многоугольник, получаемый при соединении четырех точек с прямыми линиями.</span><span class="sxs-lookup"><span data-stu-id="f4a95-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="f4a95-109">![Сплайн Безье](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="f4a95-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f4a95-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f4a95-110">Compiling the Code</span></span>  
 <span data-ttu-id="f4a95-111">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="f4a95-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a95-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f4a95-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [<span data-ttu-id="f4a95-113">Сплайны Безье в GDI+</span><span class="sxs-lookup"><span data-stu-id="f4a95-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="f4a95-114">Практическое руководство. Рисование последовательности сплайнов Безье</span><span class="sxs-lookup"><span data-stu-id="f4a95-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
