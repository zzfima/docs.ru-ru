---
title: Многоугольники в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 3ac6b9b651e65a45612cf2bd8ff17990c5cfba0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525851"
---
# <a name="polygons-in-gdi"></a>Многоугольники в GDI+
Многоугольник — замкнутую фигуру с тремя или более прямые стороны. Например треугольник — многоугольник с тремя сторонами, прямоугольник — это многоугольник с четырех сторон и пятиугольник — это многоугольник с пятью сторонами. На следующем рисунке несколько многоугольников.  
  
 ![Многоугольники](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>Рисование многоугольника  
 Чтобы нарисовать многоугольник, нужно <xref:System.Drawing.Graphics> объекта, <xref:System.Drawing.Pen> объекта и массива <xref:System.Drawing.Point> (или <xref:System.Drawing.PointF>) объектов. <xref:System.Drawing.Graphics> Объект предоставляет <xref:System.Drawing.Graphics.DrawPolygon%2A> метод. <xref:System.Drawing.Pen> Объект хранит атрибуты, такие как ширина и цвет линии, используемой для подготовки к просмотру многоугольника, а массив <xref:System.Drawing.Point> объектов содержит все точки, чтобы быть соединенных прямых линий. <xref:System.Drawing.Pen> Объекта и массива из <xref:System.Drawing.Point> объекты передаются как аргументы для <xref:System.Drawing.Graphics.DrawPolygon%2A> метод. В следующем примере рисуется 3 сторонний многоугольник. Обратите внимание, что только три точки в `myPointArray`: (0, 0), (50, 30) и (30, 60). <xref:System.Drawing.Graphics.DrawPolygon%2A> Метод автоматически закрывает многоугольника путем рисования линии из (30, 60) обратно на начальную точку, (0, 0).  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 На следующем рисунке многоугольника.  
  
 ![Многоугольник](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Практическое руководство. Создание пера](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
