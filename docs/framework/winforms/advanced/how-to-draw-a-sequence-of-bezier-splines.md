---
title: Как выполнить Рисование последовательности B&#233;сплайны Безье
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 45e56113334be4c384ef6f615d3062ed7f098ad1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572894"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>Как выполнить Рисование последовательности B&#233;сплайны Безье
Можно использовать <xref:System.Drawing.Graphics.DrawBeziers%2A> метод <xref:System.Drawing.Graphics> класса, чтобы нарисовать последовательность подключенных сплайнов Безье.  
  
## <a name="example"></a>Пример  
 В следующем примере рисуется кривой, которая состоит из двух подключенных сплайнов Безье. Конечная точка первого сплайна Безье является начальной точкой второй сплайна Безье.  
  
 На следующем рисунке подключенных сплайнов и семь точек.  
  
 ![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Сплайны Безье в GDI+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)
- [Построение и рисование кривых](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
