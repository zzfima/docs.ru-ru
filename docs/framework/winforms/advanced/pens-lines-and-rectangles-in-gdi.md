---
title: "Перья, линии и прямоугольники в GDI+ | Microsoft Docs"
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
  - "рисование, линии"
  - "рисование, прямоугольники"
  - "примеры [Windows Forms], рисование линий и фигур"
  - "примеры [Windows Forms], GDI+"
  - "примеры [Windows Forms], перья"
  - "GDI+, линии"
  - "GDI+, перья"
  - "GDI+, прямоугольники"
  - "линии"
  - "линии, штриховые"
  - "прямоугольники"
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Перья, линии и прямоугольники в GDI+
Чтобы нарисовать линию с помощью интерфейса [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], нужно создать два объекта: объект <xref:System.Drawing.Graphics> и объект <xref:System.Drawing.Pen>.  Объект <xref:System.Drawing.Graphics> содержит методы, непосредственно выполняющие рисование, а объект <xref:System.Drawing.Pen> служит хранилищем атрибутов, таких как цвет, ширина и стиль линии.  
  
## Рисование линии  
 Чтобы нарисовать линию, вызовите метод <xref:System.Drawing.Graphics.DrawLine%2A> объекта <xref:System.Drawing.Graphics>.  Объект <xref:System.Drawing.Pen> передается методу <xref:System.Drawing.Graphics.DrawLine%2A> в качестве одного из аргументов.  В приведенном ниже примере демонстрируется рисование отрезка, соединяющего точки с координатами \(4, 2\) и \(12, 6\).  
  
 [!code-csharp[LinesCurvesAndShapes#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 Метод <xref:System.Drawing.Graphics.DrawLine%2A> класса <xref:System.Drawing.Graphics> перегружен, поэтому для него поддерживается несколько способов передачи аргументов.  Например, можно создать два объекта <xref:System.Drawing.Point> и передать эти объекты <xref:System.Drawing.Point> методу <xref:System.Drawing.Graphics.DrawLine%2A> в качестве аргументов.  
  
 [!code-csharp[LinesCurvesAndShapes#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## Создание объекта Pen  
 При создании объекта <xref:System.Drawing.Pen> можно указать несколько атрибутов.  Например, один из конструкторов `Pen` позволяет указывать при создании объекта его цвет и ширину.  В приведенном ниже примере демонстрируется рисование синего отрезка толщиной 2 из точки с координатами \(0, 0\) в точку с координатами \(60, 30\).  
  
 [!code-csharp[LinesCurvesAndShapes#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## Штриховые линии и завершения отрезков  
 Объект <xref:System.Drawing.Pen> также разрешает изменять значения некоторых своих свойств, таких как <xref:System.Drawing.Pen.DashStyle%2A>, что позволяет задавать характеристики линии.  В приведенном ниже примере демонстрируется рисование отрезка штриховой линии из точки с координатами \(100, 50\) в точку с координатами \(300, 80\).  
  
 [!code-csharp[LinesCurvesAndShapes#44](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 Изменяя значения свойств объекта <xref:System.Drawing.Pen>, можно задать многие атрибуты линии.  Свойства <xref:System.Drawing.Pen.StartCap%2A> и <xref:System.Drawing.Pen.EndCap%2A> определяют вид конечных точек отрезка. Конец отрезка может быть плоским, квадратным, круглым, треугольным или иметь произвольную форму.  Свойство <xref:System.Drawing.Pen.LineJoin%2A> позволяет указывать, должны ли соединяемые линии соединяться под углом \(с выступающими острыми углами\), со скошенными, закругленными или обрезанными краями.  На приведенном ниже примере демонстрируются различные стили завершения и соединения линий.  
  
 ![Прямые линии](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.png "Aboutgdip02\_art04")  
  
## Рисование прямоугольника  
 Рисование прямоугольников в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] похоже на рисование линий.  Чтобы нарисовать прямоугольник, нужно создать два объекта: объект <xref:System.Drawing.Graphics> и объект <xref:System.Drawing.Pen>.  У объекта <xref:System.Drawing.Graphics> имеется метод <xref:System.Drawing.Graphics.DrawRectangle%2A>, а объект <xref:System.Drawing.Pen> предназначен для хранения таких атрибутов рисуемого элемента, как ширина линии и цвет.  Объект <xref:System.Drawing.Pen> передается методу <xref:System.Drawing.Graphics.DrawRectangle%2A> в качестве одного из аргументов.  В приведенном ниже примере демонстрируется рисование прямоугольника шириной 80 и высотой 40 точек, верхний левый угол которого расположен в точке с координатами \(100, 50\).  
  
 [!code-csharp[LinesCurvesAndShapes#45](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 Метод <xref:System.Drawing.Graphics.DrawRectangle%2A> класса <xref:System.Drawing.Graphics> перегружен, поэтому для него поддерживается несколько способов передачи аргументов.  Например, можно создать объект <xref:System.Drawing.Rectangle> и передать этот объект <xref:System.Drawing.Rectangle> в качестве аргумента методу <xref:System.Drawing.Graphics.DrawRectangle%2A>:  
  
 [!code-csharp[LinesCurvesAndShapes#46](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 Объект <xref:System.Drawing.Rectangle> содержит методы и свойства, позволяющие задавать и извлекать данные о прямоугольнике.  Например, методы <xref:System.Drawing.Rectangle.Inflate%2A> и <xref:System.Drawing.Rectangle.Offset%2A> позволяют изменять размер и расположение прямоугольника.  Метод <xref:System.Drawing.Rectangle.IntersectsWith%2A> позволяет определить, не пересекается ли данный прямоугольник с некоторым указанным прямоугольником, а метод <xref:System.Drawing.Rectangle.Contains%2A> позволяет определить, находится ли указанная точка внутри данного прямоугольника.  
  
## См. также  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Rectangle?displayProperty=fullName>   
 [Практическое руководство. Создание пера](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [Практическое руководство. Рисование линии в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)   
 [Практическое руководство. Рисование линии или контурной фигуры](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)