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
ms.openlocfilehash: 6fc4e12bb7532019a0571095263b5447e4b0d1ed
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702520"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Практическое руководство. Рисование единый B&#233;сплайна Безье
Сплайн Безье определяется четырех точек: начальной точки, две контрольные точки и конечной точки.  
  
## <a name="example"></a>Пример  
 В следующем примере рисуется сплайн Безье с начальной точкой (10, 100) и конечной точки (200, 100). Элемент управления указывает, являются (100, 10) и (150, 150).  
  
 Ниже показан получившийся сплайн Безье, а также его начальную точку, контрольные точки и конечной точки. На рисунке также выпуклая оболочка сплайна, которая представляет собой многоугольник, получаемый при соединении четырех точек с помощью прямых линий.  
  
 ![Bezier Spline](./media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [Сплайны Безье в GDI+](bezier-splines-in-gdi.md)
- [Практическое руководство. Рисование последовательности сплайнов Безье](how-to-draw-a-sequence-of-bezier-splines.md)
