---
title: "Практическое руководство. Рисование заполненного эллипса в Windows Forms | Microsoft Docs"
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
  - "Graphics.FillEllipse"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "круги, рисование"
  - "круглые формы"
  - "рисование, эллипсы"
  - "эллипсы, рисование"
  - "формы, рисование эллипсов"
  - "фигуры, рисование"
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Рисование заполненного эллипса в Windows Forms
В этом примере на форме рисуется заполненный эллипс.  
  
## Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## Компиляция кода  
 Этот метод нельзя вызывать в обработчике события <xref:System.Windows.Forms.Form.Load>.  Если размер формы был изменен или форма была скрыта другой формой, рисунок перерисовываться не будет.  Чтобы выполнять перерисовку автоматически, нужно переопределить метод <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
## Отказоустойчивость  
 Для любого объекта, потребляющего системные ресурсы \(например для объектов <xref:System.Drawing.Brush> и <xref:System.Drawing.Graphics>\), всегда нужно вызывать метод <xref:System.IDisposable.Dispose%2A>.  
  
## См. также  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Альфа\-смешение цвета для линий и заливок](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)   
 [Использование кисти для заливки фигур](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)