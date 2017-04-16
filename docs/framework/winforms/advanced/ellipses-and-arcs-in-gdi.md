---
title: "Эллипсы и дуги в GDI+ | Microsoft Docs"
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
  - "дуги"
  - "рисование, дуги"
  - "рисование, эллипсы"
  - "эллипсы"
  - "GDI+, дуги"
  - "GDI+, эллипсы"
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Эллипсы и дуги в GDI+
Для рисования эллипсов и дуг служат методы <xref:System.Drawing.Graphics.DrawEllipse%2A> и <xref:System.Drawing.Graphics.DrawArc%2A> класса <xref:System.Drawing.Graphics>.  
  
## Рисование эллипса  
 Чтобы нарисовать эллипс, нужно создать два объекта: объект <xref:System.Drawing.Graphics> и объект <xref:System.Drawing.Pen>.  У объекта <xref:System.Drawing.Graphics> имеется метод <xref:System.Drawing.Graphics.DrawEllipse%2A>, а объект <xref:System.Drawing.Pen> предназначен для хранения таких атрибутов, как ширина и цвет линии, с помощью которой рисуется эллипс.  Объект <xref:System.Drawing.Pen> передается методу <xref:System.Drawing.Graphics.DrawEllipse%2A> в качестве одного из аргументов.  Остальные аргументы, передаваемые методу <xref:System.Drawing.Graphics.DrawEllipse%2A>, задают прямоугольник, ограничивающий этот эллипс.  На приведенном ниже рисунке изображен эллипс с ограничивающим его прямоугольником.  
  
 ![Эллипсы и дуги](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.png "Aboutgdip02\_art05")  
  
 В приведенном ниже примере демонстрируется рисование эллипса, вокруг которого описывается прямоугольник шириной 80 и высотой 40, верхний левый угол которого расположен в точке с координатами \(100, 50\).  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 Метод <xref:System.Drawing.Graphics.DrawEllipse%2A> класса <xref:System.Drawing.Graphics> перегружен, поэтому для него поддерживается несколько способов передачи аргументов.  Например, можно создать объект <xref:System.Drawing.Rectangle> и передать этот объект <xref:System.Drawing.Rectangle> в качестве аргумента методу <xref:System.Drawing.Graphics.DrawEllipse%2A>:  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## Рисование дуги  
 Дуга — это часть эллипса.  Чтобы нарисовать дугу, вызовите метод <xref:System.Drawing.Graphics.DrawArc%2A> класса <xref:System.Drawing.Graphics>.  Параметры метода <xref:System.Drawing.Graphics.DrawArc%2A> совпадают с параметрами метода <xref:System.Drawing.Graphics.DrawEllipse%2A> за тем исключением, что методу <xref:System.Drawing.Graphics.DrawArc%2A> требуются значения начального угла и углового размера дуги.  В приведенном ниже примере демонстрируется рисование дуги с начальным углом 30 градусов и с угловым размером 180 градусов.  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 На приведенном ниже рисунке изображена дуга, эллипс и ограничивающий их прямоугольник.  
  
 ![Эллипсы и дуги](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.png "Aboutgdip02\_art06")  
  
## См. также  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Практическое руководство. Создание пера](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [Практическое руководство. Рисование линии или контурной фигуры](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)