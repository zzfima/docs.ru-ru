---
title: Как выполнить Рисование единый B&#233;сплайна Безье
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 32fc09c7525b40daea8c8705c43100cea0c052bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676462"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="09938-102">Как выполнить Рисование единый B&#233;сплайна Безье</span><span class="sxs-lookup"><span data-stu-id="09938-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="09938-103">Сплайн Безье определяется четырех точек: начальной точки, две контрольные точки и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="09938-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09938-104">Пример</span><span class="sxs-lookup"><span data-stu-id="09938-104">Example</span></span>  
 <span data-ttu-id="09938-105">В следующем примере рисуется сплайн Безье с начальной точкой (10, 100) и конечной точки (200, 100).</span><span class="sxs-lookup"><span data-stu-id="09938-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="09938-106">Элемент управления указывает, являются (100, 10) и (150, 150).</span><span class="sxs-lookup"><span data-stu-id="09938-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="09938-107">Ниже показан получившийся сплайн Безье, а также его начальную точку, контрольные точки и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="09938-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="09938-108">На рисунке также выпуклая оболочка сплайна, которая представляет собой многоугольник, получаемый при соединении четырех точек с помощью прямых линий.</span><span class="sxs-lookup"><span data-stu-id="09938-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="09938-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="09938-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="09938-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="09938-110">Compiling the Code</span></span>  
 <span data-ttu-id="09938-111">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="09938-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09938-112">См. также</span><span class="sxs-lookup"><span data-stu-id="09938-112">See also</span></span>
- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="09938-113">Сплайны Безье в GDI+</span><span class="sxs-lookup"><span data-stu-id="09938-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)
- [<span data-ttu-id="09938-114">Практическое руководство. Рисование последовательности сплайнов Безье</span><span class="sxs-lookup"><span data-stu-id="09938-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
