---
title: Как выполнить Рисование фундаментальных сплайнов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 9f2fd0f54c95ff2185c1a1d17785d300c97f7f4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739804"
---
# <a name="how-to-draw-cardinal-splines"></a>Как выполнить Рисование фундаментальных сплайнов
Фундаментальный сплайн представляет кривую, проходящую через заданные точки. Чтобы нарисовать фундаментальный сплайн, создайте <xref:System.Drawing.Graphics> и передать адрес массив точек для <xref:System.Drawing.Graphics.DrawCurve%2A> метод.  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>Рисование колоколообразной фундаментального сплайна  
  
-   Следующий пример выводит колоколообразной фундаментальный сплайн, проходящий через пять определенных точек. На следующем рисунке кривой и пять точек.  
  
     ![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>Рисование замкнутую кривую Кардинала  
  
-   Используйте <xref:System.Drawing.Graphics.DrawClosedCurve%2A> метод <xref:System.Drawing.Graphics> классе для рисования замкнутый фундаментальный сплайн. В замкнутой фундаментальной кривой продолжается с помощью последней точки в массиве и подключается с первой точки в массиве. В следующем примере рисуется замкнутый фундаментальный сплайн, проходящий через шесть определенных точек. Ниже показан замкнутый сплайн и шесть точек.  
  
 ![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>Изменение изгиба фундаментального сплайна  
  
-   Изменить способ изгиб фундаментального сплайна, передав аргумент натяжение <xref:System.Drawing.Graphics.DrawCurve%2A> метод. В следующем примере рисуется три фундаментальные сплайны, которые проходят через тот же набор точек. Ниже представлены три сплайна вместе со значениями натяжение. Обратите внимание, что если натяжение равно 0, точки соединенных прямых линий.  
  
 ![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и они требуют <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.  
  
## <a name="see-also"></a>См. также
- [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [Построение и рисование кривых](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
