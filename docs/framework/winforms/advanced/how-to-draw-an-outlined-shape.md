---
title: "Практическое руководство. Рисование линии или контурной фигуры | Microsoft Docs"
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
  - "Graphics.DrawEllipse"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "круги"
  - "круги, рисование"
  - "круглые формы"
  - "рисование, круглые формы"
  - "рисование, фигуры"
  - "эллипсы, рисование"
  - "формы, рисование круглых фигур"
  - "контурные фигуры, рисование"
  - "контурные фигуры, примеры"
  - "фигуры, рисование"
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Рисование линии или контурной фигуры
В этом примере на форме рисуются контуры эллипса и прямоугольника.  
  
## Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## Компиляция кода  
 Этот метод нельзя вызывать в обработчике события <xref:System.Windows.Forms.Form.Load>.  Если размер формы был изменен или форма была скрыта другой формой, рисунок перерисовываться не будет.  Чтобы выполнять перерисовку автоматически, нужно переопределить метод <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
## Отказоустойчивость  
 Для любого объекта, потребляющего системные ресурсы \(например для объектов <xref:System.Drawing.Pen> и <xref:System.Drawing.Graphics>\), всегда нужно вызывать метод <xref:System.IDisposable.Dispose%2A>.  
  
## См. также  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Drawing.Graphics.DrawRectangle%2A>   
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)