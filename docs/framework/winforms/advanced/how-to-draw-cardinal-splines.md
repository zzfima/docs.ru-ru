---
title: "Практическое руководство. Рисование фундаментальных сплайнов | Microsoft Docs"
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
  - "фундаментальные сплайны, рисование"
  - "рисование, фундаментальные сплайны"
  - "графика, фундаментальные сплайны"
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Рисование фундаментальных сплайнов
Фундаментальный сплайн представляет собой гладкую кривую, проходящую через заданные точки.  Чтобы нарисовать фундаментальный сплайн, создайте объект <xref:System.Drawing.Graphics> и передайте адрес массива точек методу <xref:System.Drawing.Graphics.DrawCurve%2A>.  
  
### Рисование фундаментального сплайна в форме колокола  
  
-   В следующем примере рисуется фундаментальный сплайн в форме колокола, проходящий через пять заданных точек.  Кривая и пять указанных точек представлены на приведенном ниже рисунке.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### Рисование замкнутого фундаментального сплайна  
  
-   Чтобы нарисовать замкнутый фундаментальный сплайн, можно использовать метод <xref:System.Drawing.Graphics.DrawClosedCurve%2A> класса <xref:System.Drawing.Graphics>.  В замкнутом фундаментальном сплайне линия продолжается за последнюю точку и соединяет ее с первой точкой массива.  В следующем примере рисуется замкнутый фундаментальный сплайн, проходящий через шесть заданных точек.  На следующем рисунке представлены замкнутый сплайн и шесть заданных точек.  
  
 ![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### Изменение изгиба фундаментального сплайна  
  
-   Чтобы изменить изгиб фундаментального сплайна, необходимо передать методу <xref:System.Drawing.Graphics.DrawCurve%2A> нужное значение параметра натяжения.  В следующем примере показано, как можно нарисовать три фундаментальных сплайна, которые проходят через один и тот же набор точек.  На следующем рисунке представлены три сплайна вместе с соответствующими значениями параметра натяжения.  Обратите внимание, что в случае, когда параметр натяжения равен 0, точки соединяются прямыми линиями.  
  
 ![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Построение и рисование кривых](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)