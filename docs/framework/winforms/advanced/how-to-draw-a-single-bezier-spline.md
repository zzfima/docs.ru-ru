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
# <a name="how-to-draw-a-single-b233zier-spline"></a>Как: нарисовать один B&#233;сплайн Безье
Сплайн Безье, определяемый четырьмя точками: начальной точкой, две контрольные точки и конечной точки.  
  
## <a name="example"></a>Пример  
 В следующем примере рисуется сплайн Безье с начальной точкой (10, 100) и конечной точки (200, 100). Контрольными точками являются (100, 10) и (150, 150).  
  
 На следующем рисунке получившийся сплайн Безье, вместе с его начальную точку, контрольные точки и конечной точки. На рисунке также выпуклая оболочка сплайна, которая представляет собой многоугольник, получаемый при соединении четырех точек с прямыми линиями.  
  
 ![Сплайн Безье](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [Сплайны Безье в GDI+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [Практическое руководство. Рисование последовательности сплайнов Безье](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
