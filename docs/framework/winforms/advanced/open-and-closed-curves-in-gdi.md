---
title: "Замкнутые и незамкнутые кривые в GDI+ | Microsoft Docs"
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
  - "кривые"
  - "кривые, рисование"
  - "кривые, заполнение"
  - "GDI+, кривые"
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Замкнутые и незамкнутые кривые в GDI+
На приведенном ниже рисунке изображены две кривые: открытая и замкнутая.  
  
 ![Замкнутые и незамкнутые кривые](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.png "Aboutgdip02\_art24")  
  
## Управляемый интерфейс для кривых  
 У замкнутых кривых есть внутренняя область, которую можно залить с использованием кисти.  Класс <xref:System.Drawing.Graphics> интерфейса [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] содержит следующие методы для заливки замкнутых фигур и кривых: <xref:System.Drawing.Graphics.FillRectangle%2A> \(прямые линии\), <xref:System.Drawing.Graphics.FillEllipse%2A> \(прямоугольники\), <xref:System.Drawing.Graphics.FillPie%2A> \(эллипсы\), <xref:System.Drawing.Graphics.FillPolygon%2A> \(многоугольники\), <xref:System.Drawing.Graphics.FillClosedCurve%2A> \(дуги\), <xref:System.Drawing.Graphics.FillPath%2A> \(фундаментальные сплайны\) и <xref:System.Drawing.Graphics.FillRegion%2A> \(сплайны Безье\).  При вызове одного из этих методов необходимо передавать им в качестве аргумента тип кисти \(<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush> или <xref:System.Drawing.Drawing2D.PathGradientBrush>\).  
  
 Метод <xref:System.Drawing.Graphics.FillPie%2A> является дополнением к методу <xref:System.Drawing.Graphics.DrawArc%2A>.  Метод <xref:System.Drawing.Graphics.DrawArc%2A> служит для рисования части контура эллипса, а метод <xref:System.Drawing.Graphics.FillPie%2A> — для заливки части внутренней области эллипса.  В приведенном ниже примере демонстрируется рисование дуги и заливка соответствующей части внутренней области эллипса.  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 На приведенном ниже рисунке изображена полученная дуга и залитый сектор.  
  
 ![Замкнутые и незамкнутые кривые](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.png "Aboutgdip02\_art25")  
  
 Метод <xref:System.Drawing.Graphics.FillClosedCurve%2A> является дополнением к методу <xref:System.Drawing.Graphics.DrawClosedCurve%2A>.  Оба метода автоматически замыкают кривую путем соединения конечной и начальной точки.  В приведенном ниже примере демонстрируется рисование кривой через точки с координатами \(0, 0\), \(60, 20\) и \(40, 50\).  Затем кривая автоматически замыкается путем соединения точки с координатами \(40, 50\) с начальной точкой с координатами \(0, 0\), а внутренняя область закрашивается сплошным цветом.  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 Метод <xref:System.Drawing.Graphics.FillPath%2A> заливает внутренние области различных частей контура.  Если часть контура не образует замкнутую кривую, метод <xref:System.Drawing.Graphics.FillPath%2A> автоматически замыкает эту часть контура перед началом заливки.  В приведенном ниже примере демонстрируются рисование и заливка контура, состоящего из дуги, фундаментального сплайна, строки и сектора.  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 На приведенном ниже рисунке изображен контур, залитый с использованием сплошного цвета, и вариант такого контура без заливки.  Обратите внимание, что метод <xref:System.Drawing.Graphics.DrawPath%2A> отображает текст строки в виде контуров символов, но не закрашивает эти контуры.  Внутренние области знаков строки закрашиваются методом <xref:System.Drawing.Graphics.FillPath%2A>.  
  
 ![Строка в пути](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.png "Aboutgdip02\_art26")  
  
## См. также  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Point?displayProperty=fullName>   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Построение и рисование контуров](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)