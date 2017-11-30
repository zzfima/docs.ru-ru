---
title: "Контуры в GDI+"
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
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e027228ea1cc047f213c28ac3a4984c2f0227c5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="graphics-paths-in-gdi"></a>Контуры в GDI+
Пути сформированном путем объединения линии, прямоугольники и простейших кривых. Вспомните из [Общие сведения о векторной графике](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) , основными строительными блоками доказали подходят для рисования изображений:  
  
-   Прямые линии  
  
-   Прямоугольники  
  
-   Многоточие  
  
-   Дуги  
  
-   Многоугольники  
  
-   Фундаментальные сплайны  
  
-   Сплайны Безье  
  
 В GDI + <xref:System.Drawing.Drawing2D.GraphicsPath> позволяет собирать последовательность таких блоков в одно целое. Вся последовательность линии, прямоугольники, многоугольники и кривых может быть нарисована путем однократного вызова <xref:System.Drawing.Graphics.DrawPath%2A> метод <xref:System.Drawing.Graphics> класса. Ниже показан путь, созданный путем объединения линии, дуги, сплайна Безье и фундаментальный сплайн.  
  
 ![Путь](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")  
  
## <a name="using-a-path"></a>С помощью пути  
 <xref:System.Drawing.Drawing2D.GraphicsPath> Класс предоставляет следующие методы для создания последовательности элементов для отображения: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (для сплайны), и <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>. Каждый из этих методов перегружена; то есть каждый метод поддерживает несколько различными списками параметров. Например, один из вариантов <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> метод получает четырех целых чисел, а другой вариант <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> метод получает два <xref:System.Drawing.Point> объектов.  
  
 Методы для добавления линии, прямоугольники и сплайнов Безье в пути имеют вспомогательные методы, выполняющие добавьте несколько элементов пути за один вызов: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, и <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>. Кроме того <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> методы существуют вспомогательные методы <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, добавьте замкнутой кривой или круговой путь.  
  
 Чтобы нарисовать контур, нужно <xref:System.Drawing.Graphics> объекта, <xref:System.Drawing.Pen> объекта и <xref:System.Drawing.Drawing2D.GraphicsPath> объекта. <xref:System.Drawing.Graphics> Объект предоставляет <xref:System.Drawing.Graphics.DrawPath%2A> метода и <xref:System.Drawing.Pen> объект хранит атрибуты, такие как ширина и цвет линии, используемой для подготовки к просмотру путь. <xref:System.Drawing.Drawing2D.GraphicsPath> Объект хранит последовательности, линий и кривых линий, составляющих путь. <xref:System.Drawing.Pen> Объекта и <xref:System.Drawing.Drawing2D.GraphicsPath> объекта передаются как аргументы для <xref:System.Drawing.Graphics.DrawPath%2A> метод. В следующем примере рисуется путь, состоящий из линии, эллипса и сплайна Безье:  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 Ниже показан путь.  
  
 ![Путь](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")  
  
 Помимо добавления линии, прямоугольники и кривых с путем, можно добавить пути в путь. Это позволяет объединять существующие пути для формирования больших и сложных пути.  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 Существуют два элемента, можно добавить в путь: строку и сектор. Сектор — часть внутреннюю часть эллипса. В следующем примере создается путь от дуга, фундаментальный сплайн, строка и сектора:  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 Ниже показан путь. Обратите внимание, что путь не должен быть подключен; дуга, фундаментальный сплайн, строка и круговой разделены.  
  
 ![Пути](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Практическое руководство. Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Построение и рисование контуров](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
