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
ms.openlocfilehash: 0731595dc25b1afb4b3dbcc7eedbfb92ef32d267
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58126283"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Практическое руководство. Рисование единый B&#233;сплайна Безье
Сплайн Безье определяется четырех точек: начальной точки, две контрольные точки и конечной точки.  
  
## <a name="example"></a>Пример  
 В следующем примере рисуется сплайн Безье с начальной точкой (10, 100) и конечной точки (200, 100). Элемент управления указывает, являются (100, 10) и (150, 150).  
  
 Ниже показан получившийся сплайн Безье, а также его начальную точку, контрольные точки и конечной точки. На рисунке также выпуклая оболочка сплайна, которая представляет собой многоугольник, получаемый при соединении четырех точек с помощью прямых линий.  
  
 ![Иллюстрация сплайна Безье.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [Сплайны Безье в GDI+](bezier-splines-in-gdi.md)
- [Практическое руководство. Рисование последовательности сплайнов Безье](how-to-draw-a-sequence-of-bezier-splines.md)
