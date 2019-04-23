---
title: Практическое руководство. Рисование единый B&#233;сплайна Безье
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: ebb53e7df979a553ed4a44deba34345c9ecac772
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59171682"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="a4bba-102">Практическое руководство. Рисование единый B&#233;сплайна Безье</span><span class="sxs-lookup"><span data-stu-id="a4bba-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="a4bba-103">Сплайн Безье определяется четырех точек: начальной точки, две контрольные точки и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a4bba-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4bba-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a4bba-104">Example</span></span>  
 <span data-ttu-id="a4bba-105">В следующем примере рисуется сплайн Безье с начальной точкой (10, 100) и конечной точки (200, 100).</span><span class="sxs-lookup"><span data-stu-id="a4bba-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="a4bba-106">Элемент управления указывает, являются (100, 10) и (150, 150).</span><span class="sxs-lookup"><span data-stu-id="a4bba-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="a4bba-107">Ниже показан получившийся сплайн Безье, а также его начальную точку, контрольные точки и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a4bba-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="a4bba-108">На рисунке также выпуклая оболочка сплайна, которая представляет собой многоугольник, получаемый при соединении четырех точек с помощью прямых линий.</span><span class="sxs-lookup"><span data-stu-id="a4bba-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 ![Иллюстрация сплайна Безье.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a4bba-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a4bba-110">Compiling the Code</span></span>  
 <span data-ttu-id="a4bba-111">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="a4bba-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4bba-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a4bba-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="a4bba-113">Сплайны Безье в GDI+</span><span class="sxs-lookup"><span data-stu-id="a4bba-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="a4bba-114">Практическое руководство. Рисование последовательности сплайнов Безье</span><span class="sxs-lookup"><span data-stu-id="a4bba-114">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)
