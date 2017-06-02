---
title: "Практическое руководство. Рисование отдельного сплайна Безье | Microsoft Docs"
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
  - "сплайны Безье, рисование"
  - "рисование, сплайны Безье"
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Рисование отдельного сплайна Безье
Сплайн Безье задается четырьмя точками: начальной, двумя контрольными и конечной.  
  
## Пример  
 В приведенном ниже примере демонстрируется рисование сплайна Безье из начальной точки с координатами \(10, 100\) в конечную точку с координатами \(200, 200\),  если контрольные точки имеют координаты \(100, 10\) и \(150, 150\).  
  
 На следующем рисунке показаны получившийся сплайн Безье, а также его начальная точка, конечная точка и контрольные точки.  Также показана выпуклая оболочка сплайна, которая представляет собой многоугольник, получаемый при соединении четырех указанных точек отрезками прямых.  
  
 ![Сплайн Безье](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 <xref:System.Drawing.Graphics.DrawBezier%2A>   
 [Сплайны Безье в GDI\+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)   
 [Практическое руководство. Рисование последовательности сплайнов Безье](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)