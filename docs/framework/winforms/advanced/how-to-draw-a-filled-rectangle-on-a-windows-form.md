---
title: "Практическое руководство. Рисование заполненного прямоугольника в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Graphics.FillRectangle"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "рисование прямоугольников"
  - "рисование, прямоугольники"
  - "прямоугольники, рисование"
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Рисование заполненного прямоугольника в Windows Forms
В этом примере на форме рисуется залитый прямоугольник.  
  
## Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## Компиляция кода  
 Этот метод нельзя вызывать в обработчике события <xref:System.Windows.Forms.Form.Load>.  Если размер формы был изменен или форма была скрыта другой формой, рисунок перерисовываться не будет.  Чтобы выполнять перерисовку автоматически, нужно переопределить метод <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
## Отказоустойчивость  
 Для любого объекта, потребляющего системные ресурсы \(например для объектов <xref:System.Drawing.Brush> и <xref:System.Drawing.Graphics>\), всегда нужно вызывать метод <xref:System.IDisposable.Dispose%2A>.  
  
## См. также  
 <xref:System.Drawing.Graphics.FillRectangle%2A>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Кисти и закрашенные фигуры в GDI\+](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)