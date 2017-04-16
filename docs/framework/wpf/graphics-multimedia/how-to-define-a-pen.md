---
title: "Практическое руководство. Определение пера | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "создание, перья"
  - "перья, определение"
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 2
---
# Практическое руководство. Определение пера
В этом примере показано, как использовать <xref:System.Windows.Media.Pen>, чтобы описать контур фигуры.  Для создания простого <xref:System.Windows.Media.Pen> требуется лишь указать его <xref:System.Windows.Media.Pen.Thickness%2A> и <xref:System.Windows.Media.Pen.Brush%2A>.  Можно создать более сложное перо путем задания <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A> и <xref:System.Windows.Media.Pen.EndLineCap%2A>.  
  
## Пример  
 В следующем примере используется <xref:System.Windows.Media.Pen> для описания контура фигуры, определенной <xref:System.Windows.Media.GeometryDrawing>.  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 ![Вывод пера](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.png "graphicsmm\_simple\_pen")  
GeometryDrawing