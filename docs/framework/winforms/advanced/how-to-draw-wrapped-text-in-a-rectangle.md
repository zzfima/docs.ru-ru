---
title: "Практическое руководство. Многострочный вывод текста в прямоугольнике | Microsoft Docs"
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
  - "строки [Windows Forms], рисование в прямоугольнике"
  - "текст [Windows Forms], рисование в прямоугольнике"
  - "Windows Forms, рисование текста в прямоугольнике"
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Многострочный вывод текста в прямоугольнике
Чтобы нарисовать текст с переносом по строкам внутри прямоугольника, можно воспользоваться перегруженным методом <xref:System.Drawing.Graphics.DrawString%2A> класса <xref:System.Drawing.Graphics>, который принимает параметр <xref:System.Drawing.Rectangle> или <xref:System.Drawing.RectangleF>.  Также потребуется использовать объекты <xref:System.Drawing.Brush> и <xref:System.Drawing.Font>.  
  
 Чтобы нарисовать текст с переносом по строкам внутри прямоугольника, можно также воспользоваться перегруженным методом <xref:System.Windows.Forms.TextRenderer.DrawText%2A> класса <xref:System.Windows.Forms.TextRenderer>, который принимает параметр <xref:System.Drawing.Rectangle> и <xref:System.Windows.Forms.TextFormatFlags>.  Также потребуется использовать объекты <xref:System.Drawing.Color> и <xref:System.Drawing.Font>.  
  
 На следующем рисунке показан текст, выведенный в прямоугольнике с помощью метода <xref:System.Drawing.Graphics.DrawString%2A>.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")  
  
### Рисование текста с переносом по словам в прямоугольнике с помощью GDI\+  
  
1.  Используйте перегруженный метод <xref:System.Drawing.Graphics.DrawString%2A> и передавайте ему нужный текст, объекты <xref:System.Drawing.Rectangle> или <xref:System.Drawing.RectangleF>, а также <xref:System.Drawing.Font> и <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### Рисование текста с переносом по словам в прямоугольнике с помощью GDI  
  
1.  Используйте значение из перечисления <xref:System.Windows.Forms.TextFormatFlags>, чтобы указать, что при выводе текста с помощью перегруженного метода <xref:System.Windows.Forms.TextRenderer.DrawText%2A> текст должен переноситься по словам. При этом методу передаются нужный текст, а также объекты <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> и <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## Компиляция кода  
 Для выполнения приведенных примеров требуются следующие компоненты.  
  
-   Объект <xref:System.Windows.Forms.PaintEventArgs> `e`, являющийся параметром обработчика события <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Практическое руководство. Разработка шрифтов и их семейств](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)   
 [Практическое руководство. Рисование текста в указанной позиции](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)