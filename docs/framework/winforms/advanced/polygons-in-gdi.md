---
title: "Многоугольники в GDI+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "рисование, многоугольники"
  - "GDI+, многоугольники"
  - "многоугольники"
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Многоугольники в GDI+
Многоугольник — это замкнутая фигура с тремя или более сторонами, образованными отрезками прямых линий.  Например, треугольник — это многоугольник с тремя сторонами, прямоугольник — это многоугольник с четырьмя сторонами, а пятиугольник — это многоугольник с пятью сторонами.  На приведенном ниже рисунке изображены различные многоугольники.  
  
 ![Многоугольники](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.png "Aboutgdip02\_art07")  
  
## Рисование многоугольника  
 Чтобы нарисовать многоугольник, потребуются объекты <xref:System.Drawing.Graphics> и <xref:System.Drawing.Pen>, а также массив объектов <xref:System.Drawing.Point> \(или <xref:System.Drawing.PointF>\).  У объекта <xref:System.Drawing.Graphics> имеется метод <xref:System.Drawing.Graphics.DrawPolygon%2A>.  Объект <xref:System.Drawing.Pen> используется для хранения таких атрибутов, как толщина и цвет линии, используемой для построения многоугольника. Массив объектов <xref:System.Drawing.Point> содержит точки, которые должны быть соединены отрезками прямых.  Объект <xref:System.Drawing.Pen> и массив объектов <xref:System.Drawing.Point> передаются в качестве параметров методу <xref:System.Drawing.Graphics.DrawPolygon%2A>.  В приведенном ниже примере демонстрируется рисование многоугольника с тремя сторонами.  Обратите внимание, что в массив `myPointArray` включены только три точки: \(0, 0\), \(50, 30\) и \(30, 60\).  Метод <xref:System.Drawing.Graphics.DrawPolygon%2A> автоматически замыкает многоугольник, соединяя точки \(30, 60\) и \(0, 0\) прямой линией.  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 На приведенном ниже рисунке изображен полученный многоугольник.  
  
 ![Polygon](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.png "Aboutgdip02\_art08")  
  
## См. также  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Практическое руководство. Создание пера](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)