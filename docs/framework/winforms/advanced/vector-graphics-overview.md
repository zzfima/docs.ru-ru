---
title: "Общие сведения о векторной графике | Microsoft Docs"
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
  - "системы координат"
  - "графика, векторная графика"
  - "включающие конечные точки"
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Общие сведения о векторной графике
Рисование линий, прямоугольников и других фигур с использованием интерфейса [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] происходит в некоторой системе координат.  Пользователь может выбрать одну из многих реализованных систем координат, но по умолчанию используется плоская декартова система координат, начало координат которой расположено в верхнем левом углу экрана, ось X направлена вправо, а ось Y — вниз.  Единицей измерения в заданной по умолчанию системе координат является пиксель \(минимальный элемент изображения\).  
  
## Структурные элементы интерфейса GDI\+  
 ![Векторная графика](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.png "AboutGdip02\_Art01")  
  
 Изображение на мониторе компьютера формируется как прямоугольный массив точек \(пикселей\), являющихся минимальными элементами изображения.  Количество пикселей, отображаемых на экране, зависит от типа монитора. Количество пикселей, отображаемых на экране конкретного монитора, может быть изменено пользователем в определенных пределах.  
  
 ![Векторная графика](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.png "AboutGdip02\_Art02")  
  
 При использовании интерфейса [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] для рисования линии, прямоугольника или формы необходимо указывать определенные ключевые данные, задающие параметры рисуемого элемент.  Например, отрезок задается координатами двух точек, а прямоугольник — точкой, шириной и высотой.  Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] взаимодействует с программным обеспечением драйвера экрана, чтобы определить, какие пиксели экрана должны быть высвечены, чтобы на экране возникло изображение линии, прямоугольника или кривой.  На приведенном ниже рисунке показаны пиксели, высвечиваемые, чтобы отобразить отрезок прямой линии от точки с координатами \(4, 2\) до точки с координатами \(12, 8\).  
  
 ![Векторная графика](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.png "AboutGdip02\_Art03")  
  
 За время развития компьютерной графики были выделены геометрические фигуры, наиболее полезные при создании двухмерных изображений.  Все эти элементы поддерживаются интерфейсом [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], ниже приведен их полный список.  
  
-   Строки  
  
-   Прямоугольники  
  
-   Эллипсы  
  
-   Дуги  
  
-   Многоугольники  
  
-   Фундаментальные сплайны  
  
-   Сплайны Безье  
  
## Методы рисования с помощью графических объектов  
 Класс <xref:System.Drawing.Graphics> интерфейса [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] содержит следующие методы для рисования элементов приведенного выше списка: <xref:System.Drawing.Graphics.DrawLine%2A> \(прямые линии\), <xref:System.Drawing.Graphics.DrawRectangle%2A> \(прямоугольники\), <xref:System.Drawing.Graphics.DrawEllipse%2A> \(эллипсы\), <xref:System.Drawing.Graphics.DrawPolygon%2A> \(многоугольники\), <xref:System.Drawing.Graphics.DrawArc%2A> \(дуги\), <xref:System.Drawing.Graphics.DrawCurve%2A> \(фундаментальные сплайны\) и <xref:System.Drawing.Graphics.DrawBezier%2A> \(сплайны Безье\).  Каждый из этих методов перегружен, это значит, что каждый метод может получать различные наборы параметров.  Например, один вариант метода <xref:System.Drawing.Graphics.DrawLine%2A> получает объект <xref:System.Drawing.Pen> и четыре целых числа, а другой вариант метода <xref:System.Drawing.Graphics.DrawLine%2A> \(с таким же названием\) получает объект <xref:System.Drawing.Pen> и два объекта <xref:System.Drawing.Point>.  
  
 Помимо перечисленных ранее методов для рисования линий, прямоугольников и сплайнов Безье существуют вспомогательные методы, выполняющие рисование нескольких подобных элементов \(линий, прямоугольников или сплайнов\) за один вызов: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A> и <xref:System.Drawing.Graphics.DrawBeziers%2A>.  Для метода <xref:System.Drawing.Graphics.DrawCurve%2A> также существует вспомогательный метод <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, замыкающий кривую путем соединения последней точки кривой с первой.  
  
 Все предназначенные для рисования методы класса <xref:System.Drawing.Graphics> используют объект <xref:System.Drawing.Pen>.  Чтобы нарисовать какой\-либо элемент, нужно создать как минимум два объекта: объект <xref:System.Drawing.Graphics> и объект <xref:System.Drawing.Pen>.  Объект <xref:System.Drawing.Pen> предназначен для хранения таких атрибутов рисуемого элемента, как ширина линии и цвет.  Объект <xref:System.Drawing.Pen> передается в каждый метод рисования в качестве одного из аргументов.  Например, один из вариантов метода <xref:System.Drawing.Graphics.DrawLine%2A> получает объект <xref:System.Drawing.Pen> и четыре целых числа, как это показано в приведенном ниже примере, в котором демонстрируется рисование прямоугольника с шириной 100, высотой 50 и координатами верхнего левого угла \(20, 10\).  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## См. также  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)