---
title: Эллипсы и дуги в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
ms.openlocfilehash: 93f82d35449c42772e9fbd1b7454364885b38769
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697209"
---
# <a name="ellipses-and-arcs-in-gdi"></a>Эллипсы и дуги в GDI+
Можно без труда нарисовать эллипсы и дуги с помощью <xref:System.Drawing.Graphics.DrawEllipse%2A> и <xref:System.Drawing.Graphics.DrawArc%2A> методы <xref:System.Drawing.Graphics> класса.  
  
## <a name="drawing-an-ellipse"></a>Рисование эллипса  
 Чтобы нарисовать эллипс, вам потребуется <xref:System.Drawing.Graphics> объекта и <xref:System.Drawing.Pen> объекта. <xref:System.Drawing.Graphics> Предоставляет <xref:System.Drawing.Graphics.DrawEllipse%2A> метод и <xref:System.Drawing.Pen> объект сохраняет атрибуты, например, ширина и цвет линии, используемый для визуализации эллипса. <xref:System.Drawing.Pen> Объект передается в качестве одного из аргументов <xref:System.Drawing.Graphics.DrawEllipse%2A> метод. Остальные аргументы, передаваемые <xref:System.Drawing.Graphics.DrawEllipse%2A> указать метод прямоугольник, ограничивающий эллипс. На следующем рисунке эллипс с ограничивающим его прямоугольником.  
  
 ![Эллипсы и дуги](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 В следующем примере рисуется эллипс; ограничивающий прямоугольник имеет ширину 80, в левом верхнем углу и высоты 40 (100, 50):  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A> — перегруженный метод <xref:System.Drawing.Graphics> класса, поэтому существует несколько способов передачи аргументов. Например, можно создать <xref:System.Drawing.Rectangle> и передать <xref:System.Drawing.Rectangle> для <xref:System.Drawing.Graphics.DrawEllipse%2A> метод в качестве аргумента:  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>Рисование дуги  
 Дуга является частью эллипса. Чтобы нарисовать дугу, вызовите <xref:System.Drawing.Graphics.DrawArc%2A> метод <xref:System.Drawing.Graphics> класса. Параметры <xref:System.Drawing.Graphics.DrawArc%2A> метод такие же, как параметры <xref:System.Drawing.Graphics.DrawEllipse%2A> метода, за исключением случаев, <xref:System.Drawing.Graphics.DrawArc%2A> требует начального угла и угла поворота. В следующем примере рисуется дуга с начальным углом 30 градусов и угол поворота, равный 180 градусов:  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 На следующем рисунке дуги, эллипс и ограничивающий прямоугольник.  
  
 ![Эллипсы и дуги](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [Практическое руководство. Создание пера](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
- [Практическое руководство. Рисование контурной фигуры](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
