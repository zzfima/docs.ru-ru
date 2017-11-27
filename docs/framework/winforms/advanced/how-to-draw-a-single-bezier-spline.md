---
title: "Как: Draw один B &#233; сплайн Безье"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ebdba9e01824cc764a6ab759da049add180ba83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="deaaa-102">Как: Draw один B &#233; сплайн Безье</span><span class="sxs-lookup"><span data-stu-id="deaaa-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="deaaa-103">Сплайн Безье, определяемый четырьмя точками: начальной точкой, две контрольные точки и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="deaaa-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="deaaa-104">Пример</span><span class="sxs-lookup"><span data-stu-id="deaaa-104">Example</span></span>  
 <span data-ttu-id="deaaa-105">В следующем примере рисуется сплайн Безье с начальной точкой (10, 100) и конечной точки (200, 100).</span><span class="sxs-lookup"><span data-stu-id="deaaa-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="deaaa-106">Контрольными точками являются (100, 10) и (150, 150).</span><span class="sxs-lookup"><span data-stu-id="deaaa-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="deaaa-107">На следующем рисунке получившийся сплайн Безье, вместе с его начальную точку, контрольные точки и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="deaaa-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="deaaa-108">На рисунке также выпуклая оболочка сплайна, которая представляет собой многоугольник, получаемый при соединении четырех точек с прямыми линиями.</span><span class="sxs-lookup"><span data-stu-id="deaaa-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="deaaa-109">![Сплайн Безье](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="deaaa-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="deaaa-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="deaaa-110">Compiling the Code</span></span>  
 <span data-ttu-id="deaaa-111">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="deaaa-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deaaa-112">См. также</span><span class="sxs-lookup"><span data-stu-id="deaaa-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [<span data-ttu-id="deaaa-113">Сплайны Безье в GDI+</span><span class="sxs-lookup"><span data-stu-id="deaaa-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="deaaa-114">Практическое руководство. Рисование последовательности сплайнов Безье</span><span class="sxs-lookup"><span data-stu-id="deaaa-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
