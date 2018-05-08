---
title: Замкнутые и незамкнутые кривые в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 47f420184ac384ab11054d1cc3e767ab7f618234
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="open-and-closed-curves-in-gdi"></a>Замкнутые и незамкнутые кривые в GDI+
На следующем рисунке показано две кривые: открытая и закрытая.  
  
 ![Замкнутые и незамкнутые кривые](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")  
  
## <a name="managed-interface-for-curves"></a>Управляемый интерфейс для кривых  
 Замкнутых кривых есть внутренняя область, поэтому можно заполнить кисти. <xref:System.Drawing.Graphics> Класса в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет следующие методы для заполнения замкнутые фигуры и кривых: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, и <xref:System.Drawing.Graphics.FillRegion%2A>. При вызове одного из этих методов, необходимо передать тип кисти (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, или <xref:System.Drawing.Drawing2D.PathGradientBrush>) в качестве аргумента.  
  
 <xref:System.Drawing.Graphics.FillPie%2A> Метод является вспомогательным для <xref:System.Drawing.Graphics.DrawArc%2A> метод. Так же, как <xref:System.Drawing.Graphics.DrawArc%2A> метод формирует части контура эллипса, <xref:System.Drawing.Graphics.FillPie%2A> метод заполняет внутреннюю часть эллипса часть. В следующем примере рисуется дуга и заполняет внутреннюю часть эллипса соответствующей части:  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 На следующем рисунке дуга и закрашенный сектор.  
  
 ![Замкнутые и незамкнутые кривые](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")  
  
 <xref:System.Drawing.Graphics.FillClosedCurve%2A> Метод является вспомогательным для <xref:System.Drawing.Graphics.DrawClosedCurve%2A> метод. Оба метода автоматически закрывать кривой, подключившись к начальной точке конечной точки. В следующем примере рисуется кривой, проходящей через (0, 0), (60, 20) и (40, 50). Затем кривая автоматически закрывается путем подключения (40, 50) до начальной точки (0, 0), а внутренняя область заполняется сплошным цветом.  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <xref:System.Drawing.Graphics.FillPath%2A> Метод заполняет внутреннюю часть различных частей пути. Если часть контура не образует замкнутую кривую, <xref:System.Drawing.Graphics.FillPath%2A> метод автоматически замыкает эту часть пути до его заполнения. В следующем примере рисование и Заливка контура, состоит из дуги, фундаментальный сплайн, строка и сектора:  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 Ниже показан путь с и без сплошной заливки. Обратите внимание, что текст в строке описанные, но не заданы, <xref:System.Drawing.Graphics.DrawPath%2A> метод. Это <xref:System.Drawing.Graphics.FillPath%2A> метод закрашиваются символов в строке.  
  
 ![Строка в пути](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Практическое руководство. Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Построение и рисование контуров](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
