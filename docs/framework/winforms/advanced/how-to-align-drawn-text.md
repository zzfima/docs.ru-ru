---
title: "Практическое руководство. Выравнивание рисуемого текста | Microsoft Docs"
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
  - "текст, выравнивание"
  - "Windows Forms, выравнивание нарисованного текста"
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Выравнивание рисуемого текста
При рисовании элементов может потребоваться выровнять текст по центру формы или элемента управления.  Чтобы выровнять текст, нарисованный с помощью метода <xref:System.Drawing.Graphics.DrawString%2A> или <xref:System.Windows.Forms.TextRenderer.DrawText%2A>, необходимо создать нужный объект форматирования и установить соответствующие параметры форматирования.  
  
### Рисование центрированного текста с использованием GDI\+ \(DrawString\)  
  
1.  Чтобы указать текст, требующий центрирования, используйте объект <xref:System.Drawing.StringFormat>, передаваемый методу <xref:System.Drawing.Graphics.DrawString%2A>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### Рисование центрированного текста с использованием GDI \(DrawText\)  
  
1.  Для переноса текста по строкам, а также для горизонтального и вертикального выравнивания текста по центру, используйте перечисление <xref:System.Windows.Forms.TextFormatFlags> и соответствующий метод <xref:System.Windows.Forms.TextRenderer.DrawText%2A>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## Компиляция кода  
 Предыдущие примеры кода предназначены для работы с Windows Forms, для них необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Практическое руководство. Разработка шрифтов и их семейств](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)