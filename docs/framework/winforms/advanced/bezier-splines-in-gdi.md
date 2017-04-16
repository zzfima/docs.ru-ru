---
title: "Сплайны Безье в GDI+ | Microsoft Docs"
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
  - "сплайны Безье"
  - "GDI+, сплайны Безье"
  - "сплайны, Безье"
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Сплайны Безье в GDI+
Сплайн Безье — это кривая, задаваемая четырьмя точками: двумя конечными точками \(p1 и p2\) и двумя контрольными точками \(c1 и c2\).  Кривая начинается в точке p1 и заканчивается в точке p2.  Кривая не проходит через контрольные точки. Эти точки действуют на кривую как магниты, растягивая кривую в нужных направлениях и влияя на ее изгиб.  На приведенном ниже рисунке демонстрируется кривая Безье и все ее конечные и контрольные точки.  
  
 ![Сплайны Безье](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.png "Aboutgdip02\_art11a")  
  
 Обратите внимание, что кривая начинается в точке p1 и дальше идет в направлении контрольной точки c1.  Касательная к кривой в точке p1 проходит через точку c1.  А касательная линия в конечной точке p2 проходит через точку c2.  
  
## Рисование сплайнов Безье  
 Чтобы нарисовать сплайн Безье, требуются объекты <xref:System.Drawing.Graphics> и <xref:System.Drawing.Pen>.  У экземпляра класса <xref:System.Drawing.Graphics> имеется метод <xref:System.Drawing.Graphics.DrawBezier%2A>, а в объекте <xref:System.Drawing.Pen> хранятся такие атрибуты, как толщина и цвет линии, с помощью которой выполняется рисование кривой.  Объект <xref:System.Drawing.Pen> передается методу <xref:System.Drawing.Graphics.DrawBezier%2A> в качестве одного из аргументов.  Остальные аргументы, передаваемые методу <xref:System.Drawing.Graphics.DrawBezier%2A>, задают конечные и контрольные точки сплайна.  В приведенном ниже примере демонстрируется рисование сплайна Безье из начальной точки с координатами \(0, 0\) в конечную точку с координатами \(100, 10\), если контрольные точки имеют координаты \(40, 20\) и \(80, 150\).  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 На приведенном ниже рисунке изображена описанная выше кривая, контрольные точки и две касательные.  
  
 ![Сплайны Безье](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.png "Aboutgdip02\_art12")  
  
 Сплайны Безье были впервые разработаны Пьером Безье для использования в автомобильной промышленности.  Эти кривые оказались востребованными во многих отраслях проектирования, в которых применяются компьютеры. Они также используются для задания контуров шрифтов.  С помощью сплайнов Безье можно создавать множество различных фигур, некоторые из которых показаны на приведенном ниже рисунке.  
  
 ![Пути](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.png "Aboutgdip02\_art13")  
  
## См. также  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Построение и рисование кривых](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)   
 [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Практическое руководство. Создание пера](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)