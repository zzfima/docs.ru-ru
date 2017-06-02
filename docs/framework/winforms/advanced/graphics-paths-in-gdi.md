---
title: "Контуры в GDI+ | Microsoft Docs"
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
  - "рисование, пути"
  - "GDI+, рисование контуров"
  - "графика, пути"
  - "пути, рисование"
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Контуры в GDI+
Контуры формируются из прямых линий, прямоугольников и простейших кривых.  В разделе [Общие сведения о векторной графике](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) мы уже писали, что были выделены следующие элементы, которые больше всего подходят для рисования изображений:  
  
-   Строки  
  
-   Прямоугольники  
  
-   Эллипсы  
  
-   Дуги  
  
-   Многоугольники  
  
-   Фундаментальные сплайны  
  
-   Сплайны Безье  
  
 Объект <xref:System.Drawing.Drawing2D.GraphicsPath> интерфейса GDI\+ позволяет собирать последовательность таких элементов в одно целое.  После этого вся последовательность линий, прямоугольников, многоугольников и кривых может быть нарисована путем однократного вызова метода <xref:System.Drawing.Graphics.DrawPath%2A> класса <xref:System.Drawing.Graphics>.  На приведенном ниже рисунке изображен контур, созданный путем соединения отрезка прямой, дуги, сплайна Безье и основного сплайна.  
  
 ![Путь](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.png "Aboutgdip02\_art14")  
  
## Применение контуров  
 Класс <xref:System.Drawing.Drawing2D.GraphicsPath> содержит следующие методы для рисования последовательностей элементов приведенного выше списка: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> \(прямые линии\), <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A> \(прямоугольники\), <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A> \(эллипсы\), <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> \(дуги\), <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A> \(многоугольники\), <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> \(фундаментальные сплайны\) и <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A> \(сплайны Безье\).  Каждый из этих методов перегружен, это значит, что каждый метод может получать различные наборы параметров.  Например, один вариант метода <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> получает четыре целых числа, а другой вариант метода <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> получает два целых числа и объект <xref:System.Drawing.Point>.  
  
 Помимо перечисленных ранее методов для рисования линий, прямоугольников и сплайнов Безье существуют вспомогательные методы, выполняющие добавление к контуру нескольких элементов за один вызов: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.  Для методов <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> также существуют вспомогательные методы <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, позволяющие добавлять к контуру замкнутую кривую или сектор.  
  
 Чтобы нарисовать контур, нужно создать объекты <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen> и <xref:System.Drawing.Drawing2D.GraphicsPath>.  У объекта <xref:System.Drawing.Graphics> имеется метод <xref:System.Drawing.Graphics.DrawPath%2A>, а объект <xref:System.Drawing.Pen> предназначен для хранения таких атрибутов, как ширина и цвет линии, с помощью которой рисуется контур.  Объект <xref:System.Drawing.Drawing2D.GraphicsPath> служит хранилищем для последовательности прямых и кривых линий, составляющих путь.  Объекты <xref:System.Drawing.Pen> и <xref:System.Drawing.Drawing2D.GraphicsPath> передаются в качестве аргументов методу <xref:System.Drawing.Graphics.DrawPath%2A>.  Приведенный ниже пример демонстрирует рисование контура, состоящего из отрезка прямой, эллипса и сплайна Безье.  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 На приведенном ниже рисунке изображен полученный контур.  
  
 ![Путь](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.png "Aboutgdip02\_art15")  
  
 Кроме отрезков, прямоугольников и кривых к контуру можно добавлять другие контуры.  Это позволяет объединять существующие контуры и создавать большие и сложные контуры.  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 К контуру можно также добавлять еще два элемента: строку и сектор.  Сектор — это часть внутренней области эллипса.  В приведенном ниже примере демонстрируется создание контура из дуги, фундаментального сплайна, строки и сектора.  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 На приведенном ниже рисунке изображен полученный контур.  Обратите внимание, что компоненты контура не обязаны быть связанными — дуга, фундаментальный сплайн, строка и сектор отделены друг от друга.  
  
 ![Пути](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.png "Aboutgdip02\_Art16")  
  
## См. также  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 <xref:System.Drawing.Point?displayProperty=fullName>   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Построение и рисование контуров](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)