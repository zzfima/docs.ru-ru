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
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>Как: рисование последовательности B&#233;сплайны Безье
Можно использовать <xref:System.Drawing.Graphics.DrawBeziers%2A> метод <xref:System.Drawing.Graphics> для отрисовки последовательность связанных сплайнов Безье.  
  
## <a name="example"></a>Пример  
 В следующем примере рисуется кривая, состоящая из двух соединенных сплайнов Безье. Конечная точка первого сплайна Безье является начальной точкой второй сплайна Безье.  
  
 На следующем рисунке соединенные сплайны и семь точек.  
  
 ![Сплайн Безье](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Сплайны Безье в GDI+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [Построение и рисование кривых](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
