---
title: "Практическое руководство. Отрисовка текста в Windows Forms | Microsoft Docs"
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
  - "формы, рисование текста"
  - "текст, рисование"
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Отрисовка текста в Windows Forms
В следующем примере показано, как использовать метод <xref:System.Drawing.Graphics.DrawString%2A> класса <xref:System.Drawing.Graphics> для отрисовки текста на форме.  Для вывода текста на форму можно также использовать объект <xref:System.Windows.Forms.TextRenderer>.  Дополнительные сведения см. в разделе [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).  
  
## Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## Компиляция кода  
 Метод <xref:System.Drawing.Graphics.DrawString%2A> нельзя вызывать в обработчике события <xref:System.Windows.Forms.Form.Load>.  Если размер формы был изменен или форма была скрыта другой формой, рисунок перерисовываться не будет.  Чтобы выполнять перерисовку автоматически, нужно переопределить метод <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   В системе не установлен шрифт Arial.  
  
## См. также  
 <xref:System.Drawing.Graphics.DrawString%2A>   
 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>   
 <xref:System.Drawing.StringFormat.FormatFlags%2A>   
 <xref:System.Drawing.StringFormatFlags>   
 <xref:System.Windows.Forms.TextFormatFlags>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)