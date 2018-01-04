---
title: "Эллипсы и дуги в GDI+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71126942f4cde37cc5d26bfba029c5f50f1065a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ellipses-and-arcs-in-gdi"></a>Эллипсы и дуги в GDI+
Можно легко создать эллипсы и дуги с помощью <xref:System.Drawing.Graphics.DrawEllipse%2A> и <xref:System.Drawing.Graphics.DrawArc%2A> методы <xref:System.Drawing.Graphics> класса.  
  
## <a name="drawing-an-ellipse"></a>Рисование эллипса  
 Чтобы нарисовать эллипс, нужно <xref:System.Drawing.Graphics> объекта и <xref:System.Drawing.Pen> объекта. <xref:System.Drawing.Graphics> Объект предоставляет <xref:System.Drawing.Graphics.DrawEllipse%2A> метода и <xref:System.Drawing.Pen> объект хранит атрибуты, такие как ширина и цвет линии, используемой для подготовки к просмотру эллипса. <xref:System.Drawing.Pen> Объекта передается в качестве одного из аргументов <xref:System.Drawing.Graphics.DrawEllipse%2A> метод. Остальные аргументы, передаваемые <xref:System.Drawing.Graphics.DrawEllipse%2A> указать метод прямоугольник, ограничивающий эллипс. На следующем рисунке эллипса вместе с его ограничивающего прямоугольника.  
  
 ![Эллипсы и дуги](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 В следующем примере рисуется эллипс; ограничивающий прямоугольник имеет ширину 80 высоту 40 и левом верхнем углу (100, 50):  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>— перегруженный метод <xref:System.Drawing.Graphics> класса, поэтому существует несколько способов передачи аргументов. Например, можно построить <xref:System.Drawing.Rectangle> и передать <xref:System.Drawing.Rectangle> для <xref:System.Drawing.Graphics.DrawEllipse%2A> метод в качестве аргумента:  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>Рисование дуги  
 Дуга является частью эллипса. Чтобы нарисовать дугу, вызовите <xref:System.Drawing.Graphics.DrawArc%2A> метод <xref:System.Drawing.Graphics> класса. Параметры <xref:System.Drawing.Graphics.DrawArc%2A> метода отличаются от параметров <xref:System.Drawing.Graphics.DrawEllipse%2A> метода, за исключением того, что <xref:System.Drawing.Graphics.DrawArc%2A> требует начального угла и угла поворота. В следующем примере рисуется дуга с начальным углом 30 градусов и угол поворота 180 градусов:  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 На следующем рисунке дуги, эллипс и ограничивающий прямоугольник.  
  
 ![Эллипсы и дуги](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Практическое руководство. Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Практическое руководство. Создание пера](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [Практическое руководство. Рисование контурной фигуры](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
