---
title: "Практическое руководство. Рисование последовательности сплайнов Безье | Microsoft Docs"
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
  - "сплайны Безье, рисование последовательности"
  - "сплайны, рисование кривых Безье"
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Рисование последовательности сплайнов Безье
Чтобы нарисовать последовательность связанных сплайнов Безье, необходимо воспользоваться методом <xref:System.Drawing.Graphics.DrawBeziers%2A> класса <xref:System.Drawing.Graphics>.  
  
## Пример  
 В следующем примере рисуется кривая, состоящая из двух соединенных сплайнов Безье.  Конечная точка первого сплайна Безье является начальной точкой для второго.  
  
 На следующем рисунке представлены соединенные сплайны и семь точек.  
  
 ![Сплайн Безье](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Сплайны Безье в GDI\+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)   
 [Построение и рисование кривых](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)