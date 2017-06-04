---
title: "Практическое руководство. Рисование текста в указанной позиции | Microsoft Docs"
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
  - "рисование текста"
  - "рисование текста, указанное расположение [Windows Forms]"
  - "текст, рисование в указанном расположении [Windows Forms]"
  - "Windows Forms, рисование текста в указанном расположении"
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Рисование текста в указанной позиции
Иногда может потребоваться нарисовать текст в виде одной горизонтальной строки, которая начинается в указанной точке.  Для этого можно воспользоваться перегруженным методом <xref:System.Drawing.Graphics.DrawString%2A> класса <xref:System.Drawing.Graphics>, который принимает параметр <xref:System.Drawing.Point> или <xref:System.Drawing.PointF>.  Для работы метода <xref:System.Drawing.Graphics.DrawString%2A> также требуются объекты <xref:System.Drawing.Brush> и <xref:System.Drawing.Font>.  
  
 Кроме того, можно использовать перегруженный метод <xref:System.Windows.Forms.TextRenderer.DrawText%2A> класса <xref:System.Windows.Forms.TextRenderer>, принимающий в качестве параметра объект <xref:System.Drawing.Point>.  Методу <xref:System.Windows.Forms.TextRenderer.DrawText%2A> также требуются объекты <xref:System.Drawing.Color> и <xref:System.Drawing.Font>.  
  
 На следующем рисунке показан текст, выведенный в нужной точке с помощью перегруженного метода <xref:System.Drawing.Graphics.DrawString%2A>.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
### Рисование строки текста с использованием GDI\+  
  
1.  Используйте метод <xref:System.Drawing.Graphics.DrawString%2A> и передавайте ему нужный текст, объекты <xref:System.Drawing.Point> или <xref:System.Drawing.PointF>, а также <xref:System.Drawing.Font> и <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### Рисование строки текста с использованием GDI  
  
1.  Используйте метод <xref:System.Windows.Forms.TextRenderer.DrawText%2A> и передавайте ему нужный текст, объекты <xref:System.Drawing.Point>, <xref:System.Drawing.Font> и <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## Компиляция кода  
 Для выполнения приведенных примеров требуются следующие компоненты.  
  
-   Объект <xref:System.Windows.Forms.PaintEventArgs> `e`, являющийся параметром обработчика события <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Практическое руководство. Разработка шрифтов и их семейств](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)   
 [Практическое руководство. Многострочный вывод текста в прямоугольнике](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)