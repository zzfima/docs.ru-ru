---
title: "Практическое руководство. Рисование текста в указанной позиции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text a a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aab9570b98caec5b3975a5b3ff6f1e62d4ad303b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-at-a-specified-location"></a>Практическое руководство. Рисование текста в указанной позиции
При выполнении пользовательской отрисовки, можно нарисовать текст в одной горизонтальной строки, начиная с заданной точки. Можно рисовать текст таким образом, используя <xref:System.Drawing.Graphics.DrawString%2A> перегруженным методом <xref:System.Drawing.Graphics> класс, который принимает <xref:System.Drawing.Point> или <xref:System.Drawing.PointF> параметра. <xref:System.Drawing.Graphics.DrawString%2A> Также требует <xref:System.Drawing.Brush> и<xref:System.Drawing.Font>  
  
 Можно также использовать <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженным методом <xref:System.Windows.Forms.TextRenderer> , который принимает <xref:System.Drawing.Point>. <xref:System.Windows.Forms.TextRenderer.DrawText%2A>также требуется <xref:System.Drawing.Color> и <xref:System.Drawing.Font>.  
  
 На следующем рисунке показан текст, выведенный в заданной точке с помощью <xref:System.Drawing.Graphics.DrawString%2A> перегруженный метод.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Чтобы нарисовать линию текста с использованием GDI +  
  
1.  Используйте <xref:System.Drawing.Graphics.DrawString%2A> метод, передав текст, который будет <xref:System.Drawing.Point> или <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, и <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Чтобы нарисовать линию текста с использованием GDI  
  
1.  Используйте <xref:System.Windows.Forms.TextRenderer.DrawText%2A> метод, передав текст, который будет <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, и <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущих примеров требуются:  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Практическое руководство. Разработка шрифтов и их семейств](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [Практическое руководство. Многострочный вывод текста в прямоугольнике](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
