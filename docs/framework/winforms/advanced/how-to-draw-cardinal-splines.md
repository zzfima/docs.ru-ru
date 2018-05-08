---
title: Практическое руководство. Рисование фундаментальных сплайнов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 3ad06eb28e1d8e6b5d5f4a77e545f174d8a68d9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-cardinal-splines"></a>Практическое руководство. Рисование фундаментальных сплайнов
Фундаментальный сплайн представляет кривую, проходящую через заданные точки. Чтобы нарисовать фундаментальный сплайн, создайте <xref:System.Drawing.Graphics> и передать массив указывает на адрес <xref:System.Drawing.Graphics.DrawCurve%2A> метод.  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>Рисование колоколообразной фундаментальный сплайн  
  
-   Следующий пример выводит колоколообразной фундаментальный сплайн, проходящий через пять заданных точек. Кривая и пять точек на следующем рисунке.  
  
     ![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>Рисование замкнутый фундаментальный сплайн  
  
-   Используйте <xref:System.Drawing.Graphics.DrawClosedCurve%2A> метод <xref:System.Drawing.Graphics> для отрисовки замкнутый фундаментальный сплайн. В замкнутой фундаментальной сплайновой кривой продолжается за последнюю точку в массиве и подключается с первой точки в массиве. В следующем примере рисуется замкнутый фундаментальный сплайн, проходящий через шесть заданных точек. На следующем рисунке замкнутый сплайн и шесть точек.  
  
 ![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>Изменение изгиба фундаментальный сплайн  
  
-   Изменение способа изгиб фундаментальный сплайн, передавая значение параметра натяжения <xref:System.Drawing.Graphics.DrawCurve%2A> метод. В следующем примере рисуется три фундаментальные сплайны, которые проходят через один и тот же набор точек. Ниже представлены три сплайна вместе с соответствующими значениями параметра натяжения. Обратите внимание, что в случае, когда параметр натяжения равен 0, точки соединяются прямых линий.  
  
 ![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и требуют <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.  
  
## <a name="see-also"></a>См. также  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Построение и рисование кривых](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
