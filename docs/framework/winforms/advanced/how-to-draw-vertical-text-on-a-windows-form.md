---
title: "Практическое руководство. Рисование текста по вертикали в Windows Forms | Microsoft Docs"
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
  - "StringFormat.FormatFlags"
  - "Graphics.DrawString"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "строки [Windows Forms], рисование вертикального"
  - "текст [Windows Forms], рисование"
  - "текст [Windows Forms], рисование вертикального"
  - "текст [Windows Forms], вертикальный текст"
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Рисование текста по вертикали в Windows Forms
В следующем примере кода показано, как с помощью метода <xref:System.Drawing.Graphics.DrawString%2A> класса <xref:System.Drawing.Graphics> рисовать на форме текст по вертикали.  
  
## Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## Компиляция кода  
 Этот метод нельзя вызывать в обработчике события <xref:System.Windows.Forms.Form.Load>.  Если размер формы был изменен или форма была скрыта другой формой, рисунок перерисовываться не будет.  Чтобы выполнять перерисовку автоматически, нужно переопределить метод <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   В системе не установлен шрифт Arial.  
  
## См. также  
 <xref:System.Drawing.Graphics.DrawString%2A>   
 <xref:System.Drawing.StringFormat.FormatFlags%2A>   
 <xref:System.Drawing.StringFormatFlags>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)